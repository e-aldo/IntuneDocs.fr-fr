---
title: "Configurer l’infrastructure de certificat pour SCEP"
description: "Infrastructure de création et de déploiement des profils de certificats SCEP."
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 11/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4ae137ae-34e5-4a45-950c-983de831270f
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: kmyrup
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 54b8a14c01e0a08e76843b02f00124117617540d
ms.sourcegitcommit: 3b397b1dcb780e2f82a3d8fba693773f1a9fcde1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/12/2017
---
# <a name="configure-certificate-infrastructure-for-scep"></a>Configurer l’infrastructure de certificat pour SCEP

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Cette rubrique décrit l’infrastructure dont vous avez besoin pour créer et déployer des profils de certificat SCEP.

### <a name="on-premises-infrastructure"></a>Infrastructure locale

-    **Domaine Active Directory** : tous les serveurs répertoriés dans cette section (à l’exception du serveur du proxy d’application web) doivent être joints à votre domaine Active Directory.

-  **Autorité de certification** : une autorité de certification d’entreprise qui s’exécute sur une édition Entreprise de Windows Server 2008 R2 ou version ultérieure. Une autorité de certification autonome n'est pas prise en charge. Pour savoir comment configurer une autorité de certification, consultez [Installer l'autorité de certification](http://technet.microsoft.com/library/jj125375.aspx).
    Si votre autorité de certification exécute Windows Server 2008 R2, vous devez [installer le correctif logiciel à partir de KB2483564](http://support.microsoft.com/kb/2483564/).
I
-  **Serveur NDES** : sur un serveur qui exécute Windows Server 2012 R2 ou version ultérieure, vous devez configurer le service d’inscription de périphérique réseau (NDES). Intune ne prend pas en charge le service NDES quand il s’exécute sur un serveur qui exécute également l’autorité de certification d’entreprise. Consultez le [Guide du service d’inscription de périphérique réseau](http://technet.microsoft.com/library/hh831498.aspx) pour obtenir des instructions sur la configuration de Windows Server 2012 R2 pour héberger le service d’inscription de périphérique réseau. Le serveur NDES doit être joint au domaine qui héberge l’autorité de certification et ne doit pas se trouver sur le même serveur que l’autorité de certification. Vous trouverez plus d’informations sur le déploiement du serveur NDES dans une forêt distincte, un réseau isolé ou un domaine interne dans [Utilisation d’un module de stratégie avec le service d’inscription de périphérique réseau](https://technet.microsoft.com/library/dn473016.aspx).

-  **Microsoft Intune Certificate Connector** : vous utilisez la console d’administration Intune pour télécharger le programme d’installation de **Certificate Connector** (**ndesconnectorssetup.exe**). Vous pouvez ensuite exécuter **ndesconnectorssetup.exe** sur l'ordinateur où vous souhaitez installer Certificate Connector.
-  **Serveur proxy d’application web** (facultatif) : vous pouvez utiliser un serveur qui exécute Windows Server 2012 R2 ou version ultérieure comme serveur proxy d’application web. Cette configuration :
    -  Permet aux appareils de recevoir des certificats à l'aide d'une connexion Internet.
    -  Est une recommandation de sécurité lorsque les appareils se connectent via Internet pour recevoir et renouveler les certificats.

 > [!NOTE]           
> -    Le serveur qui héberge le proxy d'application web [doit installer une mise à jour](https://blogs.technet.com/b/ems/archive/2014/12/11/hotfix-large-uri-request-in-web-application-proxy-on-windows-server-2012-r2.aspx) qui permet la prise en charge des longues URL utilisées par le service d'inscription d'appareil réseau. Cette mise à jour est incluse dans le [correctif cumulatif de décembre 2014](https://support.microsoft.com/kb/3013769), ou individuellement à partir de l'article [KB3011135](https://support.microsoft.com/kb/3011135).
>-  En outre, le serveur qui héberge le proxy d’application web doit avoir un certificat SSL qui correspond au nom publié sur les clients externes, et approuver le certificat SSL utilisé sur le serveur NDES. Ces certificats permettent au serveur du proxy d'application web de mettre fin à la connexion SSL à partir des clients et de créer une nouvelle connexion SSL au serveur NDES.
    Pour plus d’informations sur les certificats du proxy d’application web, consultez la section **Planifier des certificats** dans [Planification de publication des applications à l’aide du proxy d’application web](https://technet.microsoft.com/library/dn383650.aspx) Pour obtenir des informations générales sur les serveurs proxy d’application web, consultez [Utilisation d’un proxy d’application web](http://technet.microsoft.com/library/dn584113.aspx).|

### <a name="network-requirements"></a>Conditions requises en matière de réseau

Depuis Internet jusqu’au réseau de périmètre, autorisez le port 443 depuis tous les hôtes/adresses IP sur Internet vers le serveur NDES.

Depuis le réseau de périmètre jusqu’au réseau approuvé, autorisez tous les ports et protocoles requis pour l’accès au domaine sur le serveur NDES joint au domaine. Le serveur NDES a besoin d’un accès aux serveurs de certificats, aux serveurs DNS, aux serveurs Configuration Manager et aux contrôleurs de domaine.

Nous vous recommandons de publier le serveur NDES via un proxy, comme le [proxy de l’application Azure AD](https://azure.microsoft.com/documentation/articles/active-directory-application-proxy-publish/), le [proxy de l’accès web](https://technet.microsoft.com/library/dn584107.aspx) ou un proxy tiers.


### <a name="BKMK_CertsAndTemplates"></a> Certificats et modèles

|Objet|Détails|
|----------|-----------|
|**Modèle de certificat**|Vous configurez ce modèle sur votre autorité de certification émettrice.|
|**Certificat d’authentification client**|Demandé auprès de votre autorité de certification émettrice ou de votre autorité de certification publique, ce certificat doit être installé sur le serveur NDES.|
|**Certificat d’authentification serveur**|Demandé auprès de votre autorité de certification émettrice ou autorité de certification publique, ce certificat doit être installé et lié dans IIS sur le serveur NDES.|
|**Certificat d’autorité de certification racine approuvée**|Vous l’exportez en tant que fichier **.cer** à partir de l’autorité de certification racine ou de tout appareil qui approuve l’autorité de certification racine, puis le déployez sur des appareils à l’aide du profil de certificat d’autorité de certification approuvée.<br /><br />Vous utilisez un seul certificat d'autorité de certification racine approuvée par plateforme de système d'exploitation et l'associez à chaque profil de certificat racine approuvé que vous créez.<br /><br />Vous pouvez utiliser des certificats d'autorité de certification racine approuvée supplémentaires chaque fois que nécessaire. Par exemple, vous pouvez agir ainsi pour fournir une relation d'approbation à une autorité de certification qui signe les certificats d'authentification du serveur pour vos points d'accès Wi-Fi.|

### <a name="BKMK_Accounts"></a>Comptes

|Nom|Détails|
|--------|-----------|
|**Compte de service NDES**|Vous spécifiez un compte d'utilisateur de domaine à utiliser comme compte de service NDES.|

## <a name="BKMK_ConfigureInfrastructure"></a>Configurer votre infrastructure
Avant de configurer les profils de certificat, vous devez effectuer les tâches suivantes, ce qui nécessite la connaissance de Windows Server 2012 R2 et des services de certificats Active Directory :

**Tâche 1** : Créer un compte de service NDES

**Tâche 2** : Configurer les modèles de certificats sur l’autorité de certification

**Tâche 3** : Configurer les composants requis du serveur NDES

**Tâche 4** : Configurer NDES pour une utilisation avec Intune

**Tâche 5** : Activer, installer et configurer Intune Certificate Connector

### <a name="task-1---create-an-ndes-service-account"></a>Tâche 1 – Créer un compte de service NDES

Créez un compte d'utilisateur de domaine à utiliser comme compte de service NDES. Vous spécifiez ce compte lorsque vous configurez des modèles sur l'autorité de certification émettrice avant d'installer et de configurer NDES. Vérifiez que l’utilisateur a les droits par défaut **d’ouverture d’une session locale**, **d’ouverture d’une session en tant que service** et **d’ouverture d’une session en tant que tâche**. Certaines organisations disposent de stratégies de sécurisation renforcée qui désactivent ces droits.




### <a name="task-2---configure-certificate-templates-on-the-certification-authority"></a>Tâche 2 – Configurer les modèles de certificats sur l’autorité de certification
Dans cette tâche, vous allez :

-   Configurer un modèle de certificat pour NDES

-   Publier le modèle de certificat pour NDES

##### <a name="to-configure-the-certification-authority"></a>Pour configurer l'autorité de certification

1.  Ouvrez une session en tant qu’administrateur d’entreprise.

2.  Sur l'autorité de certification émettrice, utilisez le composant logiciel enfichable Modèles de certificats pour créer un modèle personnalisé ou copier un modèle existant, puis modifiez un modèle existant (comme le modèle de l'utilisateur), pour l'utiliser avec NDES.

    Le modèle doit avoir les configurations suivantes :

    -   Spécifiez un **Nom complet du modèle** convivial pour le modèle.

    -   Sous l'onglet **Nom de l'objet** , sélectionnez **Fournir dans la demande**. (La sécurité est appliquée par le module de stratégie Intune pour NDES.)

    -   Sous l'onglet **Extensions** , vérifiez que **Description des stratégies d'application** inclut **Authentification du client**.

        > [!IMPORTANT]
        > Pour les modèles de certificats iOS et Mac OS XOS, sous l’onglet **Extensions**, modifiez **Utilisation de la clé** et vérifiez que l’option **Signature faisant preuve de l’origine** n’est pas sélectionnée.

    -   Sous l’onglet **Sécurité** , ajoutez le compte de service NDES et attribuez-lui les autorisations **Inscription** sur le modèle. Les administrateurs Intune qui créent des profils SCEP exigent des droits **en lecture** afin de pouvoir accéder au modèle lors de la création des profils SCEP.

    > [!NOTE]
    > Pour révoquer des certificats, le compte de service NDES a besoin de droits *Émettre et gérer des certificats* pour chaque modèle de certificat utilisé par un profil de certificat.

3.  Examinez la **Période de validité** sous l'onglet **Général** du modèle. Par défaut, Intune utilise la valeur configurée dans le modèle. Toutefois, vous pouvez configurer l’autorité de certification pour permettre au demandeur de spécifier une valeur différente, que vous pouvez alors définir à partir de la console d’administration Intune. Si vous souhaitez toujours utiliser la valeur du modèle, ignorez le reste de l'étape.

    > [!IMPORTANT]
    > Les plateforme iOS et Mac OS X utilisent toujours la valeur définie dans le modèle, indépendamment des autres configurations que vous effectuez.

Voici les captures d’écran d’un exemple de configuration de modèle.

![Onglet Modèle, Traitement de la demande](..\media\scep_ndes_request_handling.png)

![Onglet Modèle, Nom du sujet](..\media\scep_ndes_subject_name.jpg)

![Onglet Modèle, Sécurité](..\media\scep_ndes_security.jpg)

![Onglet Modèle, Extensions](..\media\scep_ndes_extensions.jpg)

![Onglet Modèle, Conditions d’émission](..\media\scep_ndes_issuance_reqs.jpg)

>   [!IMPORTANT]
    > Pour les stratégies d’application (dans la 4e capture d’écran), ajoutez uniquement les stratégies d’application requises. Confirmez vos choix avec vos administrateurs de sécurité.



Pour configurer l'autorité de certification et permettre au demandeur de spécifier la période de validité, sur l'autorité de certification, exécutez les commandes suivantes :

   1.  **certutil -setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE**
   2.  **net stop certsvc**

   3.  **net start certsvc**

4.  Sur l'autorité de certification émettrice, utilisez le composant logiciel enfichable Autorité de Certification pour publier le modèle de certificat.

    1.  Sélectionnez le nœud **Modèles de certificats**, cliquez sur **Action**-&gt; **Nouveau** &gt; **Modèle de certificat à délivrer**, puis sélectionnez le modèle que vous avez créé à l’étape 2.

    2.  Validez le modèle publié en l'affichant sous le dossier **Modèles de certificats** .


### <a name="task-3---configure-prerequisites-on-the-ndes-server"></a>Tâche 3 – Configurer les composants requis du serveur NDES
Dans cette tâche, vous allez :

-   Ajouter NDES à un serveur Windows Server et configurer IIS pour prendre en charge NDES

-   Ajouter le compte de service NDES au groupe IIS_IUSR

-   Définir le SPN pour le compte de service NDES




   1.  Sur le serveur qui héberge NDES, vous devez ouvrir une session en tant qu' **Administrateur d'entreprise**, puis utilisez l' [Assistant Ajout de rôles et de fonctionnalités](https://technet.microsoft.com/library/hh831809.aspx) pour installer NDES :

    1.  Dans l'Assistant, sélectionnez **Services de certificats Active Directory** pour accéder aux services de rôle AD CS. Sélectionnez **Service d'inscription d'appareil réseau**, décochez **Autorité de certification**, puis terminez l'Assistant.

        > [!TIP]
        > Dans la page **Progression de l'installation** de l'Assistant, ne cliquez pas sur **Fermer**. Cliquez à la place sur le lien **Configurer les services de certificats Active Directory sur le serveur de destination**. Cette opération ouvre l'Assistant **Configuration AD CS** que vous utilisez pour la tâche suivante. Une fois l'Assistant Configuration AD CS ouvert, vous pouvez fermer l'Assistant Ajout de rôles et de fonctionnalités.

    2.  Lorsque NDES est ajouté au serveur, l'Assistant installe également IIS. Vérifiez qu'IIS a les configurations suivantes :

        -   **Serveur web** &gt; **Sécurité** &gt; **Filtrage des demandes**

        -   **Serveur web** &gt; **Développement d’applications** &gt; **ASP.NET 3.5**. L'installation d'ASP.NET 3.5 installe le .NET Framework 3.5. Quand vous installez .NET Framework 3.5, installez à la fois le **.NET Framework 3.5** et **Activation HTTP**.

        -   **Serveur web** &gt; **Développement d’applications** &gt; **ASP.NET 4.5**. L'installation d'ASP.NET 4.5 installe .NET Framework 4.5. Lors de l’installation de .NET Framework 4.5, installez la fonctionnalité **.NET Framework 4.5** de base, **ASP.NET 4.5** et la fonctionnalité **Services WCF** &gt; **Activation HTTP**.

        -   **Outils de gestion** &gt; **IIS 6 Management Compatibility** &gt; **Compatibilité avec la métabase de données IIS 6**

        -   **Outils de gestion** &gt; **IIS 6 Management Compatibility** &gt; **Compatibilité WMI d’IIS 6**

  2.  Sur le serveur, ajoutez le compte de service NDES en tant que membre du groupe **IIS_IUSR**.

   3.  Dans une invite de commandes avec élévation de privilèges, exécutez la commande suivante pour définir le SPN du compte de service NDES :

`**setspn -s http/&lt;DNS name of NDES Server&gt; &lt;Domain name&gt;\&lt;NDES Service account name&gt;**`

   Par exemple, si votre serveur NDES se nomme **Serveur01**, votre domaine **Contoso.com**et le compte de service **ServiceNDES**, utilisez :

`**setspn –s http/Server01.contoso.com contoso\NDESService**`

### <a name="task-4---configure-ndes-for-use-with-intune"></a>Tâche 4 – Configurer NDES pour une utilisation avec Intune
Dans cette tâche, vous allez :

-   Configurer NDES pour une utilisation avec l'autorité de certification émettrice

-   Lier le certificat du serveur d'authentification (SSL) dans IIS

-   Configurer le filtrage de demandes dans IIS

##### <a name="to-configure-ndes-for-use-with-intune"></a>Pour configurer NDES pour une utilisation avec Intune

1.  Sur le serveur NDES, ouvrez l'Assistant Configuration AD CS et procédez aux configurations suivantes.

    > [!TIP]
    > Si vous avez cliqué sur le lien de la tâche précédente, l'Assistant est déjà ouvert. Sinon, ouvrez le Gestionnaire de serveur pour accéder à la configuration de post-déploiement pour les services de certificats Active Directory.

    -   Dans la page **Services de rôle** Page, sélectionnez le **Service d'inscription d'appareil réseau**.

    -   Dans la page **Compte de service pour NDES** , spécifiez le compte de service NDES.

    -   Dans la page **Autorité de certification pour NDES** , cliquez sur **Sélectionner**, puis sélectionnez l'autorité de certification émettrice où vous avez configuré le modèle de certificat.

    -   Dans la page **Chiffrement pour NDES** , définissez la longueur de la clé pour répondre aux besoins de votre entreprise.

    Dans la page **Confirmation** , cliquez sur **Configurer** pour terminer l'Assistant.

2.  Une fois l'Assistant terminé, modifiez la clé de Registre suivante sur le serveur NDES :

    -   **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Cryptography\MSCEP\**

    Pour modifier cette clé, identifiez l’**Objet** du modèle de certificat, tel qu’indiqué sous l’onglet **Traitement de la demande**, puis modifiez l’entrée correspondante du Registre en remplaçant les données existantes par le nom du modèle de certificat (pas le nom d’affichage du modèle) que vous avez spécifié dans la tâche 1. Le tableau suivant mappe le rôle de modèle de certificat aux valeurs du Registre :

    |Rôle de modèle de certificat (onglet Traitement de la demande)|Valeur du Registre à modifier|Valeur indiquée dans la console d’administration Intune pour le profil SCEP|
    |--------------------------------------------------------------|--------------------------|------------------------------------------------------------------------------------------------------------|
    |Signature|SignatureTemplate|Signature numérique|
    |Chiffrement|EncryptionTemplate|Chiffrement de la clé|
    |Signature et chiffrement|GeneralPurposeTemplate|Chiffrement de la clé<br /><br />Signature numérique|
    Par exemple, si le rôle de votre modèle de certificat est **Chiffrement**, remplacez la valeur de **EncryptionTemplate** par le nom de votre modèle de certificat.

3. Le serveur NDES recevra de très longues URL (requêtes), qui nécessiteront l’ajout de deux entrées au Registre :

    |Emplacement|Valeur|Type|Niveau|
    |-------|-----|----|----|
    |HKLM\SYSTEM\CurrentControlSet\Services\HTTP\Parameters|MaxFieldLength|DWORD|65534 (décimal)|
    |HKLM\SYSTEM\CurrentControlSet\Services\HTTP\Parameters|MaxRequestBytes|DWORD|65534 (décimal)|


4. Dans le Gestionnaire IIS, cliquez sur **Site Web par défaut** -> **Filtrage des demandes** -> **Modifier un paramètre de fonction**, et modifiez **Longueur maximale des URL** et **Longueur maximale des chaînes de requête** en spécifiant *65534*, comme indiqué.

    ![Longueur maximale des URL et des requêtes IIS](..\media\SCEP_IIS_max_URL.png)

5.  Redémarrez le serveur. L’exécution de **iisreset** sur le serveur ne suffira pas pour finaliser ces modifications.
6. Accédez à http://*FQDN*/certsrv/mscep/mscep.dll. Vous devez voir une page NDES similaire à la suivante :

    ![Page NDES test](..\media\SCEP_NDES_URL.png)

    Si vous obtenez une erreur **503 Service indisponible**, consultez l’Observateur d’événements. Il est probable que le pool d’applications soit arrêté en raison de l’absence d’un droit pour l’utilisateur NDES. Ces droits sont décrits dans la tâche 1.

##### <a name="to-install-and-bind-certificates-on-the-ndes-server"></a>Pour installer et lier des certificats sur le serveur NDES

1.  Sur votre serveur NDES, demandez et installez un certificat d' **authentification serveur** auprès de votre autorité de certification interne ou autorité de certification publique. Vous allez ensuite lier ce certificat SSL dans IIS.

    > [!TIP]
    > Après avoir lié le certificat SSL dans IIS, vous allez également installer un certificat d'authentification client. Ce certificat peut être émis par toute autorité de certification approuvée par le serveur NDES. Bien que cette solution ne soit pas recommandée, vous pouvez utiliser le même certificat pour l'authentification serveur et l'authentification client aussi longtemps que le certificat possède les deux utilisations améliorées de la clé. Passez en revue les étapes suivantes pour plus d'informations sur ces certificats d'authentification.

    1.  Après avoir obtenu le certificat d'authentification serveur, ouvrez le **Gestionnaire IIS**, sélectionnez le **Site web par défaut** dans le volet **Connexions** , puis cliquez sur **Liaisons** dans le volet **Actions** .

    2.  Cliquez sur **Ajouter**, définissez **Type** avec la valeur **https**, puis vérifiez que le port est **443**. (Seul le port 443 est pris en charge pour la version autonome d’Intune).

    3.  Pour **Certificat SSL**, spécifiez le certificat d'authentification serveur.

        > [!NOTE]
        > Si le serveur NDES utilise un nom interne et un nom externe pour une même adresse réseau, le certificat d'authentification serveur doit avoir un **Nom de l'objet** avec un nom de serveur public externe et un **Autre nom de l'objet** incluant le nom du serveur interne.

2.  Sur votre serveur NDES, demandez et installez un certificat d' **authentification client** auprès de votre autorité de certification interne ou d'une autorité de certification publique. Cela peut être le même certificat que le certificat d'authentification serveur si ce certificat possède les deux fonctions.

    Le certificat d'authentification client doit avoir les propriétés suivantes :

    **Utilisation améliorée de la clé** : doit inclure l’**Authentification du client**.

    **Nom de l’objet** : doit être équivalent au nom DNS du serveur sur lequel vous installez le certificat (serveur NDES).

##### <a name="to-configure-iis-request-filtering"></a>Pour configurer le filtrage des demandes IIS

1.  Sur le serveur NDES, ouvrez le **Gestionnaire IIS**, sélectionnez le **Site web par défaut** dans le volet **Connexions** , puis ouvrez **Filtrage des demandes**.

2.  Cliquez sur **Modifier les paramètres de la fonctionnalité**, puis définissez les éléments suivants :

    **Chaîne de requête (octets)** = **65534**

    **Longueur maximale des URL (octets)** = **65534**

3.  Vérifiez la clé de Registre suivante :

    **HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\HTTP\Parameters**

    Vérifiez que les valeurs suivantes sont définies en tant qu'entrées DWORD :

    Nom : **MaxFieldLength**, avec une valeur décimale de **65534**

    Nom : **MaxRequestBytes**, avec une valeur décimale de **65534**

4.  Redémarrez le serveur NDES. Le serveur est maintenant prêt à prendre en charge Certificate Connector.

### <a name="task-5---enable-install-and-configure-the-intune-certificate-connector"></a>Tâche 5 – Activer, installer et configurer Intune Certificate Connector
Dans cette tâche, vous allez :

activer la prise en charge de NDES dans Intune ;

télécharger, installer et configurer Certificate Connector sur le serveur NDES.

##### <a name="to-enable-support-for-the-certificate-connector"></a>Pour activer la prise en charge de Certificate Connector

1.  Ouvrez la [console d’administration Intune](https://manage.microsoft.com), cliquez sur **Administration** &gt; **Certificate Connector**.

2.  Cliquez sur **Configurer On-premises Certificate Connector**.

3.  Sélectionnez **Activer Certificate Connector**, puis cliquez sur **OK**.

##### <a name="to-download-install-and-configure-the-certificate-connector"></a>Pour télécharger, installer et configurer Certificate Connector

1.  Ouvrez la [console d’administration Intune](https://manage.microsoft.com), puis cliquez sur **Administration** &gt; **Gestion des appareils mobiles** &gt; **Certificate Connector** &gt; **Télécharger Certificate Connector**.

2.  Une fois le téléchargement terminé, exécutez le programme d’installation téléchargé (**ndesconnectorssetup.exe**) sur un serveur Windows Server 2012 R2. Le programme d’installation installe également le module de stratégie pour NDES et le service web CRP. (Le service web CRP, CertificateRegistrationSvc, s'exécute en tant qu'application dans IIS.)

    > [!NOTE]
    > Quand vous installez NDES pour la version autonome d’Intune, le service CRP est installé automatiquement avec Certificate Connector. Quand vous utilisez Intune avec Configuration Manager, vous installez le Point d’enregistrement de certificat comme rôle de système de site distinct.

3.  Quand vous êtes invité à entrer le certificat client pour Certificate Connector, cliquez sur **Sélectionner**, puis sélectionnez le certificat d' **authentification client** installé sur votre serveur NDES à la tâche 3.

    Après avoir sélectionné le certificat d'authentification client, vous revenez au **Certificat client pour Microsoft Intune Certificate Connector** . Bien que le certificat sélectionné n'apparaisse pas, cliquez sur **Suivant** pour afficher les propriétés du certificat. Cliquez sur **Suivant**, puis cliquez sur **Installer**.

4.  Une fois l'Assistant terminé, mais avant de fermer l'Assistant, cliquez sur **Lancer l'interface utilisateur de Certificate Connector**.

    > [!TIP]
    > Si vous fermez l'Assistant avant de lancer l'interface utilisateur de Certificate Connector, vous pouvez le rouvrir en exécutant la commande suivante :
    >
    > **&lt;chemin_installation&gt;\NDESConnectorUI\NDESConnectorUI.exe**

5.  Dans l'interface utilisateur de **Certificate Connector** :

    Cliquez sur **Connexion** et entrez vos informations d’identification du service Intune ou les informations d’identification d’un administrateur client avec l’autorisation d’administration globale.

    Si votre organisation utilise un serveur proxy et que ce dernier est nécessaire au serveur NDES pour accéder à Internet, cliquez sur **Utiliser un serveur proxy**, puis indiquez le nom, le port et les informations d’identification de compte du serveur proxy pour vous connecter.

    Sélectionnez l'onglet **Avancé** , puis fournissez les informations d'identification d'un compte qui possède l'autorisation **Émettre et gérer des certificats** sur votre autorité de certification émettrice, puis cliquez sur **Appliquer**.

    Vous pouvez maintenant fermer l'interface utilisateur de Certificate Connector.

6.  Ouvrez une invite de commandes et tapez **services.msc**, appuyez sur **Entrée**, cliquez avec le bouton droit sur **Service du connecteur Intune**, puis cliquez sur **Redémarrer**.

Pour valider que le service s'exécute, ouvrez un navigateur et entrez l'URL suivante, ce qui doit retourner une erreur **403** :

**https:// &lt;nom_de_domaine_complet_de_votre_serveur_NDES&gt;/certsrv/mscep/mscep.dll**

## <a name="next-steps"></a>Étapes suivantes
Vous êtes maintenant prêt à configurer des profils de certificat, comme décrit dans [Configurer les profils de certificat](Configure-Intune-certificate-profiles.md).
