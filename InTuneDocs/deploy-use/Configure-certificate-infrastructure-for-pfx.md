---
title: "Configurer l’infrastructure de certificat pour PFX |Microsoft Intune"
description: "Créez et déployez des profils de certificat .PFX."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 11/17/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2c543a02-44a5-4964-8000-a45e3bf2cc69
ms.reviewer: vinaybha
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 7d1f37a2ba2e634fb75058d33eaaccf3aa5845b0
ms.openlocfilehash: 8fc1cc718fd0edae8b8ec4a0a8dc25487eafda2b



---
# <a name="configure-certificate-infrastructure"></a>Configurer l’infrastructure de certificat
Cette rubrique décrit les éléments dont vous avez besoin pour créer et déployer des profils de certificat .PFX.

Pour effectuer une authentification basée sur certificat dans votre organisation, vous avez besoin d’une autorité de certification d’entreprise.

Pour utiliser des profils de certificat .PFX, en plus de l’autorité de certification d’entreprise, il vous faut également :

-   Un ordinateur capable de communiquer avec l’autorité de certification (ou vous pouvez utiliser l’ordinateur d’autorité de certification proprement dit)

-  Intune Certificate Connector, qui s'exécute sur l'ordinateur qui peut communiquer avec l'autorité de certification

## <a name="onpremises-infrastructure-description"></a>Description de l’infrastructure locale


-    **Domaine Active Directory** : tous les serveurs répertoriés dans cette section (à l’exception du serveur du proxy d’application web) doivent être joints à votre domaine Active Directory.

-  **Autorité de certification** : autorité de certification d’entreprise qui s’exécute sur une édition Entreprise de Windows Server 2008 R2 ou version ultérieure. Une autorité de certification autonome n'est pas prise en charge. Pour savoir comment configurer une autorité de certification, consultez [Installer l'autorité de certification](http://technet.microsoft.com/library/jj125375.aspx).
    Si votre autorité de certification exécute Windows Server 2008 R2, vous devez [installer le correctif logiciel à partir de KB2483564](http://support.microsoft.com/kb/2483564/).

-  **Un ordinateur capable de communiquer avec l’autorité de certification** : en guise d’alternative, utilisez l’ordinateur d’autorité de certification proprement dit.
-  **Microsoft Intune Certificate Connector** : vous utilisez la console d’administration Intune pour télécharger le programme d’installation de **Certificate Connector** (**ndesconnectorssetup.exe**). Vous pouvez ensuite exécuter **ndesconnectorssetup.exe** sur l'ordinateur où vous souhaitez installer Certificate Connector. Pour les profils de certificat .PFX, installez Certificate Connector sur l'ordinateur qui communique avec l'autorité de certification.
-  **Serveur proxy d’application web** (facultatif) : vous pouvez utiliser un serveur qui exécute Windows Server 2012 R2 ou version ultérieure comme serveur proxy d’application web. Cette configuration :
    -  Permet aux appareils de recevoir des certificats à l'aide d'une connexion Internet.
    -  Est une recommandation de sécurité lorsque les appareils se connectent via Internet pour recevoir et renouveler les certificats.

 > [!NOTE]           
> -    Le serveur qui héberge le proxy d’application web [doit installer une mise à jour](http://blogs.technet.com/b/ems/archive/2014/12/11/hotfix-large-uri-request-in-web-application-proxy-on-windows-server-2012-r2.aspx) qui permet la prise en charge des longues URL utilisées par le service d’inscription d’appareil réseau (NDES). Cette mise à jour est incluse dans le [correctif cumulatif de décembre 2014](http://support.microsoft.com/kb/3013769), ou individuellement à partir de l'article [KB3011135](http://support.microsoft.com/kb/3011135).
>-  En outre, le serveur qui héberge le proxy d’application web doit avoir un certificat SSL qui correspond au nom publié sur les clients externes, et approuver le certificat SSL utilisé sur le serveur NDES. Ces certificats permettent au serveur du proxy d'application web de mettre fin à la connexion SSL à partir des clients et de créer une nouvelle connexion SSL au serveur NDES.
    Pour plus d’informations sur les certificats du proxy d’application web, consultez la section **Planifier des certificats** dans [Planification de publication des applications à l’aide du proxy d’application web](https://technet.microsoft.com/library/dn383650.aspx) Pour obtenir des informations générales sur les serveurs proxy d’application web, consultez [Utilisation d’un proxy d’application web](http://technet.microsoft.com/library/dn584113.aspx).|


### <a name="certificates-and-templates"></a>Certificats et modèles

|Objet|Détails|
|----------|-----------|
|**Modèle de certificat**|Vous configurez ce modèle sur votre autorité de certification émettrice.|
|**Certificat d’autorité de certification racine approuvée**|Vous l'exportez en tant que fichier **.cer** à partir de l'autorité de certification émettrice ou de tout appareil qui approuve l'autorité de certification émettrice, puis le déployez sur des appareils à l'aide du profil de certificat d'autorité de certification approuvée.<br /><br />Vous utilisez un seul certificat d'autorité de certification racine approuvée par plateforme de système d'exploitation et l'associez à chaque profil de certificat racine approuvé que vous créez.<br /><br />Vous pouvez utiliser des certificats d'autorité de certification racine approuvée supplémentaires chaque fois que nécessaire. Par exemple, vous pouvez agir ainsi pour fournir une relation d'approbation à une autorité de certification qui signe les certificats d'authentification du serveur pour vos points d'accès Wi-Fi.|


## <a name="configure-your-infrastructure"></a>Configurer votre infrastructure
Pour pouvoir configurer des profils de certificat, vous devez d’abord effectuer les tâches suivantes. Pour effectuer ces tâches, vous devez connaître Windows Server 2012 R2 et les services de certificats Active Directory (AD CS) :

- **Tâche 1** : Configurer les modèles de certificats sur l’autorité de certification.
- **Tâche 2** : Activer, installer et configurer Intune Certificate Connector.

### <a name="task-1-configure-certificate-templates-on-the-certification-authority"></a>Tâche 1 : Configurer les modèles de certificats sur l'autorité de certification
Au cours de cette tâche, vous allez publier le modèle de certificat.

##### <a name="to-configure-the-certification-authority"></a>Pour configurer l'autorité de certification

1.  Sur l’autorité de certification émettrice, utilisez le composant logiciel enfichable Modèles de certificats pour créer un modèle personnalisé ou copiez un modèle existant, puis modifiez-le (par exemple le modèle Utilisateur), pour l’utiliser avec .PFX.

    Le modèle doit inclure les éléments suivants :

    -   Spécifiez un **Nom complet du modèle** convivial pour le modèle.

    -   Sous l'onglet **Nom de l'objet** , sélectionnez **Fournir dans la demande**. 

    -   Sous l'onglet **Extensions** , vérifiez que **Description des stratégies d'application** inclut **Authentification du client**.

        > [!IMPORTANT]
        > Pour les modèles de certificats iOS et Mac OS XOS, sous l’onglet **Extensions**, modifiez **Utilisation de la clé** et vérifiez que l’option **Signature faisant preuve de l’origine** n’est pas sélectionnée.

2.  Examinez la **Période de validité** sous l'onglet **Général** du modèle. Par défaut, Intune utilise la valeur configurée dans le modèle. Toutefois, vous pouvez configurer l’autorité de certification pour permettre au demandeur de spécifier une valeur différente, que vous pouvez alors définir à partir de la console d’administration Intune. Si vous souhaitez toujours utiliser la valeur du modèle, ignorez le reste de l'étape.

    > [!IMPORTANT]
    > Les plateformes iOS et Mac OS X utilisent toujours la valeur définie dans le modèle, indépendamment des autres configurations que vous effectuez.

    Pour configurer l’autorité de certification et permettre au demandeur de spécifier la période de validité, exécutez les commandes suivantes sur l’autorité de certification :

    a.  **certutil -setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE**

    b.  **net stop certsvc**

    c.  **net start certsvc**

3.  Sur l'autorité de certification émettrice, utilisez le composant logiciel enfichable Autorité de Certification pour publier le modèle de certificat.

    a.  Sélectionnez le nœud **Modèles de certificats**, cliquez sur **Action**-&gt; **Nouveau** &gt; **Modèle de certificat à délivrer**, puis sélectionnez le modèle que vous avez créé à l’étape 2.

    b.  Validez le modèle publié en l'affichant sous le dossier **Modèles de certificats** .

4.  Sur l’ordinateur de l’autorité de certification, vérifiez que l’ordinateur qui héberge Intune Certificate Connector a l’autorisation Inscription qui lui permet d’accéder au modèle utilisé pour créer le profil .PFX. Définissez cette autorisation sous l'onglet **Sécurité** des propriétés de l'ordinateur d'autorité de certification.

### <a name="task-2-enable-install-and-configure-the-intune-certificate-connector"></a>Tâche 2 : Activer, installer et configurer Intune Certificate Connector
Dans cette tâche, vous allez :

télécharger, installer et configurer Certificate Connector.

##### <a name="to-enable-support-for-the-certificate-connector"></a>Pour activer la prise en charge de Certificate Connector

1.  Ouvrez la [console d’administration Intune](https://manage.microsoft.com) et choisissez **Administration** &gt; **Certificate Connector**.

2.  Choisissez **Configurer On-premises Certificate Connector**.

3.  Sélectionnez **Activer Certificate Connector**, puis choisissez **OK**.

##### <a name="to-download-install-and-configure-the-certificate-connector"></a>Pour télécharger, installer et configurer Certificate Connector

1.  Ouvrez la [console d’administration Intune](https://manage.microsoft.com), puis choisissez **Administration** &gt; **Gestion des appareils mobiles** &gt; **Certificate Connector** &gt; **Télécharger Certificate Connector**.

2.  Une fois le téléchargement terminé, exécutez le programme d’installation téléchargé (**ndesconnectorssetup.exe**).

  Exécutez le programme d’installation sur l’ordinateur qui peut se connecter à l’autorité de certification. Choisissez l’option Distribution .PFX, puis choisissez **Installer**. Une fois l’installation terminée, créez un profil de certificat comme décrit dans [Configurer les profils de certificat](configure-intune-certificate-profiles.md).

   <!-- Not sure about step 3 below -->

3.  Quand vous êtes invité à entrer le certificat client pour Certificate Connector, choisissez **Sélectionner** et sélectionnez le certificat d’**authentification client** que vous avez installé pendant la tâche 3.

    Après avoir sélectionné le certificat d'authentification client, vous revenez au **Certificat client pour Microsoft Intune Certificate Connector** . Bien que le certificat sélectionné n’apparaisse pas, choisissez **Suivant** pour afficher les propriétés du certificat. Choisissez ensuite **Suivant**, puis **Installer**.

4.  Une fois l'Assistant terminé, mais avant de fermer l'Assistant, cliquez sur **Lancer l'interface utilisateur de Certificate Connector**.

    > [!TIP]
    > Si vous fermez l'Assistant avant de lancer l'interface utilisateur de Certificate Connector, vous pouvez le rouvrir en exécutant la commande suivante :
    >
    > **&lt;chemin_installation&gt;\NDESConnectorUI\NDESConnectorUI.exe**

5.  Dans l'interface utilisateur de **Certificate Connector** :

    a. Choisissez **Connexion** et entrez vos informations d’identification d’administrateur du service Intune ou les informations d’identification d’un administrateur client doté de l’autorisation d’administration globale.

    b. Sélectionnez l’onglet **Avancé** , puis fournissez les informations d’identification d’un compte qui possède l’autorisation **Émettre et gérer des certificats** sur votre autorité de certification émettrice.

    c. Choisissez **Appliquer**.

    Vous pouvez maintenant fermer l'interface utilisateur de Certificate Connector.

6.  Ouvrez une invite de commandes et tapez **services.msc**. Appuyez ensuite sur **Entrée**, cliquez avec le bouton droit sur **Service du connecteur Intune**, puis choisissez **Redémarrer**.


### <a name="next-steps"></a>Étapes suivantes
Vous êtes maintenant prêt à configurer des profils de certificat, comme décrit dans [Configurer les profils de certificat](Configure-Intune-certificate-profiles.md).



<!--HONumber=Nov16_HO3-->


