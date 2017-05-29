---
title: "Configurer et gérer les certificats PKCS avec Intune"
titleSuffix: Intune Azure preview
description: "Intune Azure en version préliminaire : découvrez comment configurer votre infrastructure avant de créer et affecter des certificats PKCS avec Intune."
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 04/22/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e189ebd1-6ca1-4365-9d5d-fab313b7e979
ms.reviewer: vinaybha
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 16fa26ae8ed06c4959807b30e430fd69fc503936
ms.contentlocale: fr-fr
ms.lasthandoff: 05/23/2017



---
# <a name="configure-and-manage-pkcs-certificates-with-intune"></a>Configurer et gérer les certificats PKCS avec Intune
[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Cette rubrique vous explique comment configurer votre infrastructure, puis comment créer et affecter des profils de certificat PKCS avec Intune.

Pour effectuer une authentification basée sur certificat dans votre organisation, vous avez besoin d’une autorité de certification d’entreprise.

Pour utiliser des profils de certificat PKCS en plus de l’autorité de certification d’entreprise, il vous faut également :

-   Un ordinateur capable de communiquer avec l’autorité de certification (ou vous pouvez utiliser l’ordinateur d’autorité de certification proprement dit)

-  Intune Certificate Connector, qui s'exécute sur l'ordinateur qui peut communiquer avec l'autorité de certification

## <a name="important-terms"></a>Termes importants


-    **Domaine Active Directory** : tous les serveurs répertoriés dans cette section (à l’exception du serveur du proxy d’application web) doivent être joints à votre domaine Active Directory.

-  **Autorité de certification** : autorité de certification d’entreprise qui s’exécute sur une édition Entreprise de Windows Server 2008 R2 ou version ultérieure. Une autorité de certification autonome n'est pas prise en charge. Pour savoir comment configurer une autorité de certification, consultez [Installer l'autorité de certification](http://technet.microsoft.com/library/jj125375.aspx).
    Si votre autorité de certification exécute Windows Server 2008 R2, vous devez [installer le correctif logiciel à partir de KB2483564](http://support.microsoft.com/kb/2483564/).

-  **Un ordinateur capable de communiquer avec l’autorité de certification** : en guise d’alternative, utilisez l’ordinateur d’autorité de certification proprement dit.
-  **Microsoft Intune Certificate Connector** : dans le portail Azure, vous téléchargez le programme d’installation de **Certificate Connector** (**ndesconnectorssetup.exe**). Vous pouvez ensuite exécuter **ndesconnectorssetup.exe** sur l'ordinateur où vous souhaitez installer Certificate Connector. Pour les profils de certificat PKCS, installez Certificate Connector sur l'ordinateur qui communique avec l'autorité de certification.
-  **Serveur proxy d’application web** (facultatif) : vous pouvez utiliser un serveur qui exécute Windows Server 2012 R2 ou version ultérieure comme serveur proxy d’application web. Cette configuration :
    -  Permet aux appareils de recevoir des certificats à l'aide d'une connexion Internet.
    -  Est une recommandation de sécurité lorsque les appareils se connectent via Internet pour recevoir et renouveler les certificats.

 > [!NOTE]           
> -    Le serveur qui héberge le proxy d’application web [doit installer une mise à jour](http://blogs.technet.com/b/ems/archive/2014/12/11/hotfix-large-uri-request-in-web-application-proxy-on-windows-server-2012-r2.aspx) qui permet la prise en charge des longues URL utilisées par le service d’inscription d’appareil réseau (NDES). Cette mise à jour est incluse dans le [correctif cumulatif de décembre 2014](http://support.microsoft.com/kb/3013769), ou individuellement à partir de l'article [KB3011135](http://support.microsoft.com/kb/3011135).
>-  En outre, le serveur qui héberge le proxy d’application web doit avoir un certificat SSL qui correspond au nom publié sur les clients externes, et approuver le certificat SSL utilisé sur le serveur NDES. Ces certificats permettent au serveur du proxy d'application web de mettre fin à la connexion SSL à partir des clients et de créer une nouvelle connexion SSL au serveur NDES.
    Pour plus d’informations sur les certificats du proxy d’application web, consultez la section **Planifier des certificats** dans [Planification de publication des applications à l’aide du proxy d’application web](https://technet.microsoft.com/library/dn383650.aspx) Pour obtenir des informations générales sur les serveurs proxy d’application web, consultez [Utilisation d’un proxy d’application web](http://technet.microsoft.com/library/dn584113.aspx).|


## <a name="certificates-and-templates"></a>Certificats et modèles

|Objet|Détails|
|----------|-----------|
|**Modèle de certificat**|Vous configurez ce modèle sur votre autorité de certification émettrice.|
|**Certificat d’autorité de certification racine approuvée**|Vous devez l’exporter en tant que fichier **.cer** à partir de l’autorité de certification émettrice ou de tout appareil qui approuve l’autorité de certification émettrice, puis l’affecter à des appareils à l’aide du profil de certificat d’autorité de certification approuvée.<br /><br />Vous utilisez un seul certificat d'autorité de certification racine approuvée par plateforme de système d'exploitation et l'associez à chaque profil de certificat racine approuvé que vous créez.<br /><br />Vous pouvez utiliser des certificats d'autorité de certification racine approuvée supplémentaires chaque fois que nécessaire. Par exemple, vous pouvez agir ainsi pour fournir une relation d'approbation à une autorité de certification qui signe les certificats d'authentification du serveur pour vos points d'accès Wi-Fi.|


## <a name="configure-your-infrastructure"></a>Configurer votre infrastructure
Pour pouvoir configurer des profils de certificat, vous devez d’abord effectuer les étapes suivantes. Pour suivre ces étapes, vous devez connaître Windows Server 2012 R2 et les services de certificats Active Directory (AD CS) :

- **Étape 1** : configurer les modèles de certificats sur l’autorité de certification.
- **Étape 2** : activer, installer et configurer Intune Certificate Connector.

## <a name="step-1---configure-certificate-templates-on-the-certification-authority"></a>Étape 1 : configurer les modèles de certificats sur l’autorité de certification

### <a name="to-configure-the-certification-authority"></a>Pour configurer l'autorité de certification

1.  Sur l’autorité de certification émettrice, utilisez le composant logiciel enfichable Modèles de certificats pour créer un modèle personnalisé ou copiez un modèle existant, puis modifiez-le (par exemple, le modèle Utilisateur) pour l’utiliser avec PKCS.

    Le modèle doit inclure les éléments suivants :

    -   Spécifiez un **Nom complet du modèle** convivial pour le modèle.

    -   Sous l'onglet **Nom de l'objet** , sélectionnez **Fournir dans la demande**. (La sécurité est appliquée par le module de stratégie Intune pour NDES.)

    -   Sous l'onglet **Extensions** , vérifiez que **Description des stratégies d'application** inclut **Authentification du client**.

        > [!IMPORTANT]
        > Pour les modèles de certificats iOS et macOS, sous l’onglet **Extensions**, modifiez **Utilisation de la clé** et vérifiez que l’option **Signature faisant preuve de l’origine** n’est pas sélectionnée.

2.  Examinez la **Période de validité** sous l'onglet **Général** du modèle. Par défaut, Intune utilise la valeur configurée dans le modèle. Toutefois, vous pouvez configurer l’autorité de certification pour permettre au demandeur de spécifier une valeur différente, que vous pouvez alors définir à partir de la console d’administration Intune. Si vous souhaitez toujours utiliser la valeur du modèle, ignorez le reste de l'étape.

    > [!IMPORTANT]
    > iOS et macOS utilisent toujours la valeur définie dans le modèle, indépendamment des autres configurations que vous effectuez.

    Pour configurer l’autorité de certification et permettre au demandeur de spécifier la période de validité, exécutez les commandes suivantes sur l’autorité de certification :

    a.  **certutil -setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE**

    b.  **net stop certsvc**

    c.  **net start certsvc**

3.  Sur l'autorité de certification émettrice, utilisez le composant logiciel enfichable Autorité de Certification pour publier le modèle de certificat.

    a.  Sélectionnez le nœud **Modèles de certificats**, cliquez sur **Action**-&gt; **Nouveau** &gt; **Modèle de certificat à délivrer**, puis sélectionnez le modèle que vous avez créé à l’étape 2.

    b.  Validez le modèle publié en l'affichant sous le dossier **Modèles de certificats** .

4.  Sur l’ordinateur de l’autorité de certification, vérifiez que l’ordinateur qui héberge Intune Certificate Connector a l’autorisation Inscription qui lui permet d’accéder au modèle utilisé pour créer le profil de certificat PKCS. Définissez cette autorisation sous l'onglet **Sécurité** des propriétés de l'ordinateur d'autorité de certification.

## <a name="step-2---enable-install-and-configure-the-intune-certificate-connector"></a>Étape 2 : activer, installer et configurer Intune Certificate Connector
Au cours de cette étape, vous allez :

- activer la prise en charge de Certificate Connector ;
- télécharger, installer et configurer Certificate Connector.

### <a name="to-enable-support-for-the-certificate-connector"></a>Pour activer la prise en charge de Certificate Connector

1.  Connectez-vous au portail Azure.
2.  Choisissez **Plus de services** > **Autres** > **Intune**.
3.  Dans le panneau **Intune**, choisissez **Configurer des appareils**.
2.  Dans le panneau **Configuration de l’appareil**, choisissez **Configuration** > **Autorité de certification**.
2.  Sous **Étape 1**, choisissez **Activer**.

### <a name="to-download-install-and-configure-the-certificate-connector"></a>Pour télécharger, installer et configurer Certificate Connector

1.  Dans le panneau **Configurer des appareils**, choisissez **Configuration** > **Autorité de certification**.
2.  Choisissez **Télécharger le connecteur de certificats**.
2.  Une fois le téléchargement terminé, exécutez le programme d’installation téléchargé (**ndesconnectorssetup.exe**).
  Exécutez le programme d’installation sur l’ordinateur qui peut se connecter à l’autorité de certification. Choisissez l’option Distribution PKCS (PFX), puis choisissez **Installer**. Une fois l’installation terminée, créez un profil de certificat comme décrit dans [Configuration des profils de certificat](certificates-configure.md).

3.  Quand vous êtes invité à entrer le certificat client pour Certificate Connector, choisissez **Sélectionner**, puis sélectionnez le certificat **d'authentification client** que vous avez installé.

    Après avoir sélectionné le certificat d'authentification client, vous revenez au **Certificat client pour Microsoft Intune Certificate Connector** . Bien que le certificat sélectionné n’apparaisse pas, choisissez **Suivant** pour afficher les propriétés du certificat. Choisissez ensuite **Suivant**, puis **Installer**.

4.  Une fois l'Assistant terminé, mais avant de fermer l'Assistant, cliquez sur **Lancer l'interface utilisateur de Certificate Connector**.

    > [!TIP]
    > Si vous fermez l'Assistant avant de lancer l'interface utilisateur de Certificate Connector, vous pouvez le rouvrir en exécutant la commande suivante :
    >
    > **&lt;chemin_installation&gt;\NDESConnectorUI\NDESConnectorUI.exe**

5.  Dans l'interface utilisateur de **Certificate Connector** :

    a. Choisissez **Connexion** et entrez vos informations d’identification d’administrateur du service Intune ou les informations d’identification d’un administrateur client doté de l’autorisation d’administration globale.

  <!--  If your organization uses a proxy server and the proxy is needed for the NDES server to access the Internet, click **Use proxy server** and then provide the proxy server name, port, and account credentials to connect.-->

    b. Sélectionnez l’onglet **Avancé** , puis fournissez les informations d’identification d’un compte qui possède l’autorisation **Émettre et gérer des certificats** sur votre autorité de certification émettrice.

    c. Choisissez **Appliquer**.

    Vous pouvez maintenant fermer l'interface utilisateur de Certificate Connector.

6.  Ouvrez une invite de commandes et tapez **services.msc**. Appuyez ensuite sur **Entrée**, cliquez avec le bouton droit sur **Service du connecteur Intune**, puis choisissez **Redémarrer**.

Pour valider que le service s'exécute, ouvrez un navigateur et entrez l'URL suivante, ce qui doit retourner une erreur **403** :

**http:// &lt;nom_de_domaine_complet_de_votre_serveur_NDES&gt;/certsrv/mscep/mscep.dll**


### <a name="how-to-create-a-pkcs-certificate-profile"></a>Comment créer un profil de certificat PKCS

Dans le portail Azure, sélectionnez la charge de travail **Configurer des appareils**.
2. Dans le panneau **Configuration de l’appareil**, choisissez **Gérer** > **Profils**.
3. Dans le panneau de profils, cliquez sur **Créer un profil**.
4. Dans le panneau **Créer un profil**, entrez un **Nom** et une **Description** pour le profil de certificat PKCS.
5. Dans la liste déroulante **Plateforme**, sélectionnez la plateforme d’appareil pour ce certificat PKCS :
    - **Android**
    - **Android for Work**
    - **iOS**
    - **Windows 10 et versions ultérieures**
6. Dans la liste déroulante **Type de profil**, choisissez **Certificat PKCS**.
7. Dans le panneau **Certificat PKCS**, configurez les paramètres suivants :
    - **Seuil de renouvellement (%)** : spécifiez le pourcentage de durée de vie restante du certificat avant que l’appareil ne demande le renouvellement du certificat.
    - **Période de validité du certificat** : si vous avez exécuté la commande **certutil - setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE** sur l’autorité de certification émettrice, ce qui autorise une période de validité personnalisée, vous pouvez spécifier le temps restant avant l’expiration du certificat.<br>Vous pouvez spécifier une valeur inférieure à la période de validité du modèle de certificat spécifié, mais pas une valeur supérieure. Par exemple, si la période de validité du certificat dans le modèle de certificat est de 2 ans, vous pouvez spécifier une valeur de 1 an mais pas une valeur de 5 ans. La valeur doit également être inférieure à la période de validité restante du certificat de l’autorité de certification émettrice.
    - **Fournisseur de stockage de clés** (Windows 10) : spécifiez l’emplacement de stockage de la clé du certificat. Choisissez l'une des valeurs suivantes :
        - **Inscrire auprès du fournisseur de stockage de clés (KSP) du module de plateforme sécurisée (TPM) s’il est présent ; sinon, inscrire auprès du fournisseur de stockage de clés du logiciel**
        - **Inscrire auprès du fournisseur de stockage de clés (KSP) du module de plateforme sécurisée (TPM), sinon mettre en échec**
        - **Inscrire auprès de Passport, sinon mettre en échec (Windows 10 et versions ultérieures)**
        - **Inscrire auprès du fournisseur de stockage de clés du logiciel**
    - **Autorité de certification** : autorité de certification d’entreprise qui s’exécute sur une édition Entreprise de Windows Server 2008 R2 ou version ultérieure. Une autorité de certification autonome n'est pas prise en charge. Pour savoir comment configurer une autorité de certification, consultez [Installer l'autorité de certification](http://technet.microsoft.com/library/jj125375.aspx). Si votre autorité de certification exécute Windows Server 2008 R2, vous devez [installer le correctif logiciel à partir de KB2483564](http://support.microsoft.com/kb/2483564/).
    - **Nom de l’autorité de certification** : entrez le nom de votre autorité de certification.
    - **Nom du modèle de certificat** : entrez le nom d’un modèle de certificat que doit utiliser le service d’inscription de périphériques réseau conformément à sa configuration et qui a été ajouté à une autorité de certification émettrice.
    Assurez-vous que le nom correspond exactement à l’un des modèles de certificat figurant dans le registre du serveur exécutant le service d’inscription de périphériques réseau. Assurez-vous que vous spécifiez le nom du modèle de certificat et non le nom d'affichage du modèle de certificat. 
    Pour rechercher les noms des modèles de certificats, accédez à la clé suivante : HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Cryptography\MSCEP. Les modèles de certificat s'affichent sous la forme des valeurs **EncryptionTemplate**, **GeneralPurposeTemplate**et **SignatureTemplate**. Par défaut, la valeur des trois modèles de certificat est IPSECIntermediateOffline, laquelle correspond au nom d’affichage du modèle **IPSec (requête hors connexion)**. 
    - **Format du nom de l’objet** : dans la liste, sélectionnez comment Intune crée automatiquement le nom de l’objet dans la demande de certificat. Si le certificat est pour un utilisateur, vous pouvez également inclure l'adresse de messagerie de cet utilisateur dans le nom de l'objet. Choisissez parmi :
        - **Non configuré**
        - **Nom commun**
        - **Nom commun (adresse e-mail incluse)**
        - **Nom commun comme adresse e-mail**
    - **Autre nom de l’objet** : spécifiez comment Intune crée automatiquement les valeurs pour l’autre nom de l’objet dans la demande de certificat. Par exemple, si vous avez sélectionné un type de certificat utilisateur, vous pouvez inclure le nom d'utilisateur principal (UPN) dans l'autre nom de l'objet. Si le certificat client est utilisé pour l'authentification sur un serveur de stratégie réseau, l'autre nom de l'objet doit être défini sur le nom d'utilisateur principal.
    - **Utilisation de la clé étendue** (Android) : choisissez **Ajouter** pour ajouter des valeurs pour le rôle prévu du certificat. Dans la plupart des cas, le certificat demande une **Authentification client** afin que l'utilisateur ou l'appareil puisse être authentifié sur un serveur. Toutefois, vous pouvez ajouter d'autres utilisations de la clé en fonction de vos besoins. 
    - **Certificat racine** (Android) : choisissez un profil de certificat d’autorité de certification racine que vous avez précédemment configuré et attribué à l’utilisateur ou à l’appareil. Ce certificat d'autorité de certification doit être le certificat racine de l'autorité de certification qui émet le certificat que vous configurez dans ce profil de certificat. Il s’agit du profil de certificat approuvé que vous avez créé précédemment.
8. Lorsque vous avez terminé, revenez au panneau **Créer un profil** et appuyez sur **Créer**.

Le profil est créé et s’affiche dans le panneau de la liste des profils.

## <a name="how-to-assign-the-certificate-profile"></a>Comment affecter le profil de certificat

Considérez les éléments suivants avant d’attribuer des profils de certificat aux groupes :

- Quand vous attribuez des profils de certificat aux groupes, le fichier de certificat issu du profil de certificat d’autorité de certification approuvée est installé sur l’appareil. L’appareil utilise le profil de certificat PKCS pour créer une demande de certificat par l’appareil.
- Les profils de certificat s’installent uniquement sur les appareils exécutant la plateforme que vous utilisez quand vous créez le profil.
- Vous pouvez affecter des profils de certificat sur des regroupements d’utilisateurs ou d’appareils.
- Pour publier un certificat sur un appareil rapidement après l’inscription de l’appareil, affectez le profil de certificat à un groupe d’utilisateurs plutôt qu’à un groupe d’appareils. Si vous l’affectez à un groupe d’appareils, une inscription complète des appareils est préalablement nécessaire pour qu’ils puissent recevoir des stratégies.
- Même si vous affectez chaque profil séparément, vous devez également affecter l’autorité de certification racine approuvée et le profil PKCS. Dans le cas contraire, la stratégie de certificat PKCS échoue.

Pour plus d’informations sur la façon d’affecter des profils, consultez [Guide pratique pour attribuer des profils d’appareils](device-profile-assign.md).

