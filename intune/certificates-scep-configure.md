---
title: "Configurer et gérer les certificats SCEP avec Intune"
titlesuffix: Azure portal
description: "Découvrez comment configurer votre infrastructure avant de créer et affecter des profils de certificat Intune SCEP."
keywords: 
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 1/18/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.reviewer: kmyrup
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 61193cc96f0ea22e9a80d24fe8ee0499e80d4202
ms.sourcegitcommit: 2c7794848777e73d6a9502b4e1000f0b07ac96bc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/01/2018
---
# <a name="configure-and-manage-scep-certificates-with-intune"></a>Configurer et gérer les certificats SCEP avec Intune
[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Cette rubrique vous montre comment configurer votre infrastructure, puis comment créer et affecter des profils de certificat SCEP (Simple Certificate Enrollment Protocol) avec Intune.

## <a name="configure-on-premises-infrastructure"></a>Configurer l’infrastructure locale

-    **Domaine Active Directory** : tous les serveurs répertoriés dans cette section (à l’exception du serveur du proxy d’application web) doivent être joints à votre domaine Active Directory.

-  **Autorité de certification** : une autorité de certification d’entreprise qui s’exécute sur une édition Entreprise de Windows Server 2008 R2 ou version ultérieure. Une autorité de certification autonome n'est pas prise en charge. Pour plus d’informations, consultez [Installer l’autorité de certification](http://technet.microsoft.com/library/jj125375.aspx).
    Si votre autorité de certification exécute Windows Server 2008 R2, vous devez [installer le correctif logiciel à partir de KB2483564](http://support.microsoft.com/kb/2483564/).

-  **Serveur NDES** : sur un serveur qui exécute Windows Server 2012 R2 ou version ultérieure, vous devez configurer le service d’inscription de périphérique réseau (NDES). Intune ne prend pas en charge le service NDES quand il s’exécute sur un serveur qui exécute également l’autorité de certification d’entreprise. Consultez le [Guide du service d’inscription de périphérique réseau](http://technet.microsoft.com/library/hh831498.aspx) pour obtenir des instructions sur la configuration de Windows Server 2012 R2 pour héberger le service d’inscription de périphérique réseau.
Le serveur NDES doit être joint au domaine qui héberge l’autorité de certification et ne doit pas se trouver sur le même serveur que l’autorité de certification. Vous trouverez plus d’informations sur le déploiement du serveur NDES dans une forêt distincte, un réseau isolé ou un domaine interne dans [Utilisation d’un module de stratégie avec le service d’inscription de périphérique réseau](https://technet.microsoft.com/library/dn473016.aspx).

-  **Microsoft Intune Certificate Connector** : utilisez le portail Azure pour télécharger le programme d’installation de **Certificate Connector** (**ndesconnectorssetup.exe**). Vous pouvez ensuite exécuter **ndesconnectorssetup.exe** sur le serveur hébergeant le rôle de service d’inscription de périphériques réseau (NDES) où vous souhaitez installer Certificate Connector. 
-  **Serveur proxy d’application web** (facultatif) : utilisez un serveur qui exécute Windows Server 2012 R2 ou version ultérieure comme serveur proxy d’application web (WAP). Cette configuration :
    -  Permet aux appareils de recevoir des certificats à l'aide d'une connexion Internet.
    -  Est une recommandation de sécurité lorsque les appareils se connectent via Internet pour recevoir et renouveler les certificats.

 > [!NOTE]           
> -    Le serveur qui héberge le proxy d'application web [doit installer une mise à jour](http://blogs.technet.com/b/ems/archive/2014/12/11/hotfix-large-uri-request-in-web-application-proxy-on-windows-server-2012-r2.aspx) qui permet la prise en charge des longues URL utilisées par le service d'inscription d'appareil réseau. Cette mise à jour est incluse dans le [correctif cumulatif de décembre 2014](http://support.microsoft.com/kb/3013769), ou individuellement à partir de l'article [KB3011135](http://support.microsoft.com/kb/3011135).
>-  En outre, le serveur qui héberge le proxy d’application web doit avoir un certificat SSL qui correspond au nom publié sur les clients externes, et approuver le certificat SSL utilisé sur le serveur NDES. Ces certificats permettent au serveur du proxy d'application web de mettre fin à la connexion SSL à partir des clients et de créer une nouvelle connexion SSL au serveur NDES.
    Pour plus d’informations sur les certificats du proxy d’application web, consultez la section **Planifier des certificats** dans [Planification de publication des applications à l’aide du proxy d’application web](https://technet.microsoft.com/library/dn383650.aspx) Pour obtenir des informations générales sur les serveurs proxy d’application web, consultez [Utilisation d’un proxy d’application web](http://technet.microsoft.com/library/dn584113.aspx).|

### <a name="network-requirements"></a>Conditions requises en matière de réseau

Depuis Internet jusqu’au réseau de périmètre, autorisez le port 443 depuis tous les hôtes/adresses IP sur Internet vers le serveur NDES.

Depuis le réseau de périmètre jusqu’au réseau approuvé, autorisez tous les ports et protocoles requis pour l’accès au domaine sur le serveur NDES joint au domaine. Le serveur NDES a besoin d’un accès aux serveurs de certificats, aux serveurs DNS, aux serveurs Configuration Manager et aux contrôleurs de domaine.

Nous vous recommandons de publier le serveur NDES via un proxy, comme le [proxy de l’application Azure AD](https://azure.microsoft.com/documentation/articles/active-directory-application-proxy-publish/), le [proxy de l’accès web](https://technet.microsoft.com/library/dn584107.aspx) ou un proxy tiers.


### <a name="certificates-and-templates"></a>Certificats et modèles

|Objet|Détails|
|----------|-----------|
|**Modèle de certificat**|Configurez ce modèle sur votre autorité de certification émettrice.|
|**Certificat d’authentification client**|Demandé auprès de votre autorité de certification émettrice ou de votre autorité de certification publique ; ce certificat doit être installé sur le serveur NDES.|
|**Certificat d’authentification serveur**|Demandé auprès de votre autorité de certification émettrice ou autorité de certification publique ; ce certificat doit être installé et lié dans IIS sur le serveur NDES.|
|**Certificat d’autorité de certification racine approuvée**|Vous devez exporter ce certificat en tant que fichier **.cer** à partir de l’autorité de certification racine ou de tout appareil qui approuve l’autorité de certification racine, puis l’affecter à des appareils à l’aide du profil de certificat d’autorité de certification approuvé.<br /><br />Vous utilisez un seul certificat d'autorité de certification racine approuvée par plateforme de système d'exploitation et l'associez à chaque profil de certificat racine approuvé que vous créez.<br /><br />Vous pouvez utiliser des certificats d'autorité de certification racine approuvée supplémentaires chaque fois que nécessaire. Par exemple, vous pouvez agir ainsi pour fournir une relation d'approbation à une autorité de certification qui signe les certificats d'authentification du serveur pour vos points d'accès Wi-Fi.|

### <a name="accounts"></a>Comptes

|Nom|Détails|
|--------|-----------|
|**Compte de service NDES**|Spécifiez un compte d'utilisateur de domaine à utiliser comme compte de service NDES.|

## <a name="configure-your-infrastructure"></a>Configurer votre infrastructure
Avant de configurer les profils de certificat, vous devez effectuer les tâches suivantes, ce qui nécessite la connaissance de Windows Server 2012 R2 et des services de certificats Active Directory :

**Étape 1** : créer un compte de service NDES

**Étape 2** : configurer les modèles de certificats sur l’autorité de certification

**Étape 3** : configurer les composants requis du serveur NDES

**Étape 4** : configurer NDES pour une utilisation avec Intune

**Étape 5** : activer, installer et configurer Intune Certificate Connector

#### <a name="step-1---create-an-ndes-service-account"></a>Étape 1 : créer un compte de service NDES

Créez un compte d'utilisateur de domaine à utiliser comme compte de service NDES. Vous spécifiez ce compte quand vous configurez des modèles sur l’autorité de certification émettrice avant d’installer et de configurer NDES. Vérifiez que l’utilisateur a les droits par défaut **d’ouverture d’une session locale**, **d’ouverture d’une session en tant que service** et **d’ouverture d’une session en tant que tâche**. Certaines organisations disposent de stratégies de sécurisation renforcée qui désactivent ces droits.

#### <a name="step-2---configure-certificate-templates-on-the-certification-authority"></a>Étape 2 : configurer les modèles de certificats sur l’autorité de certification
Dans cette tâche, vous allez :

-   Configurer un modèle de certificat pour NDES

-   Publier le modèle de certificat pour NDES

##### <a name="to-configure-the-certification-authority"></a>Pour configurer l'autorité de certification

1.  Ouvrez une session en tant qu’administrateur d’entreprise.

2.  Sur l'autorité de certification émettrice, utilisez le composant logiciel enfichable Modèles de certificats pour créer un modèle personnalisé ou copier un modèle existant, puis modifiez un modèle existant (comme le modèle de l'utilisateur), pour l'utiliser avec NDES.

    >[!NOTE]
    > Le modèle de certificat NDES doit être basé sur un modèle de certificat v2 (avec compatibilité de Windows 2003).

    Le modèle doit avoir les configurations suivantes :

    -   Spécifiez un **Nom complet du modèle** convivial pour le modèle.

    -   Sous l'onglet **Nom de l'objet** , sélectionnez **Fournir dans la demande**. (La sécurité est appliquée par le module de stratégie Intune pour NDES.)

    -   Sous l'onglet **Extensions** , vérifiez que **Description des stratégies d'application** inclut **Authentification du client**.

        > [!IMPORTANT]
        > Pour les modèles de certificats iOS et macOS, sous l’onglet **Extensions**, modifiez **Utilisation de la clé** et vérifiez que l’option **Signature faisant preuve de l’origine** n’est pas sélectionnée.

    -   Sous l’onglet **Sécurité** , ajoutez le compte de service NDES et attribuez-lui les autorisations **Inscription** sur le modèle. Les administrateurs Intune qui créent des profils SCEP exigent des droits **en lecture** pour pouvoir accéder au modèle durant la création des profils SCEP.

    > [!NOTE]
    > Pour révoquer des certificats, le compte de service NDES a besoin de droits *Émettre et gérer des certificats* pour chaque modèle de certificat utilisé par un profil de certificat.

3.  Examinez la **Période de validité** sous l'onglet **Général** du modèle. Par défaut, Intune utilise la valeur configurée dans le modèle. Toutefois, vous pouvez configurer l’autorité de certification pour permettre au demandeur de spécifier une valeur différente, que vous pouvez alors définir à partir de la console d’administration Intune. Si vous souhaitez toujours utiliser la valeur du modèle, ignorez le reste de l'étape.

    > [!IMPORTANT]
    > iOS et macOS utilisent toujours la valeur définie dans le modèle, indépendamment des autres configurations que vous effectuerez.

Voici les captures d’écran d’un exemple de configuration de modèle.

![Onglet Modèle, Traitement de la demande](.\media\scep_ndes_request_handling.png)

![Onglet Modèle, Nom du sujet](.\media\scep_ndes_subject_name.jpg)

![Onglet Modèle, Sécurité](.\media\scep_ndes_security.jpg)

![Onglet Modèle, Extensions](.\media\scep_ndes_extensions.jpg)

![Onglet Modèle, Conditions d’émission](.\media\scep_ndes_issuance_reqs.jpg)

>   [!IMPORTANT]
    > Pour les stratégies d’application, ajoutez uniquement les stratégies d’application requises. Confirmez vos choix avec vos administrateurs de sécurité.



Pour configurer l’autorité de certification et permettre au demandeur de spécifier la période de validité :

1. Sur l’autorité de certification, exécutez les commandes suivantes :
    - **certutil -setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE**
    - **net stop certsvc**
    - **net start certsvc**
2. Sur l'autorité de certification émettrice, utilisez le composant logiciel enfichable Autorité de Certification pour publier le modèle de certificat.
    Sélectionnez le nœud **Modèles de certificats**, cliquez sur **Action**-&gt; **Nouveau** &gt; **Modèle de certificat à délivrer**, puis sélectionnez le modèle que vous avez créé à l’étape 2.
3. Validez le modèle publié en l'affichant sous le dossier **Modèles de certificats** .


#### <a name="step-3---configure-prerequisites-on-the-ndes-server"></a>Étape 3 : configurer les composants requis du serveur NDES
Dans cette tâche, vous allez :

-   Ajouter NDES à un serveur Windows Server et configurer IIS pour prendre en charge NDES

-   Ajouter le compte de service NDES au groupe IIS_IUSR

-   Définir le SPN pour le compte de service NDES




   1.  Sur le serveur qui héberge NDES, connectez-vous en tant **qu’administrateur d’entreprise**, puis utilisez [l’Assistant Ajout de rôles et de fonctionnalités](https://technet.microsoft.com/library/hh831809.aspx) pour installer NDES :

    1.  Dans l'Assistant, sélectionnez **Services de certificats Active Directory** pour accéder aux services de rôle AD CS. Sélectionnez **Service d'inscription d'appareil réseau**, décochez **Autorité de certification**, puis terminez l'Assistant.

        > [!TIP]
        > Dans la page **Progression de l'installation** de l'Assistant, ne cliquez pas sur **Fermer**. Cliquez à la place sur le lien **Configurer les services de certificats Active Directory sur le serveur de destination**. Cette opération ouvre l'Assistant **Configuration AD CS** que vous utilisez pour la tâche suivante. Une fois l'Assistant Configuration AD CS ouvert, vous pouvez fermer l'Assistant Ajout de rôles et de fonctionnalités.

    2.  Lorsque NDES est ajouté au serveur, l'Assistant installe également IIS. Vérifiez qu'IIS a les configurations suivantes :

        -   **Serveur web** &gt; **Sécurité** &gt; **Filtrage des demandes**

        -   **Serveur web** &gt; **Développement d’applications** &gt; **ASP.NET 3.5**. L’installation d’ASP.NET 3.5 installe le .NET Framework 3.5. Quand vous installez .NET Framework 3.5, installez à la fois le **.NET Framework 3.5** et **Activation HTTP**.

        -   **Serveur web** &gt; **Développement d’applications** &gt; **ASP.NET 4.5**. L’installation d’ASP.NET 4.5 installe le .NET Framework 4.5. Lors de l’installation de .NET Framework 4.5, installez la fonctionnalité **.NET Framework 4.5** de base, **ASP.NET 4.5** et la fonctionnalité **Services WCF** &gt; **Activation HTTP**.

        -   **Outils de gestion** &gt; **IIS 6 Management Compatibility** &gt; **Compatibilité avec la métabase de données IIS 6**

        -   **Outils de gestion** &gt; **IIS 6 Management Compatibility** &gt; **Compatibilité WMI d’IIS 6**

  2.  Sur le serveur, ajoutez le compte de service NDES en tant que membre du groupe **IIS_IUSR**.

   3.  Dans une invite de commandes avec élévation de privilèges, exécutez la commande suivante pour définir le SPN du compte de service NDES :

`**setspn -s http/&lt;DNS name of NDES Server&gt; &lt;Domain name&gt;\&lt;NDES Service account name&gt;**`

   Par exemple, si votre serveur NDES se nomme **Serveur01**, votre domaine **Contoso.com**et le compte de service **ServiceNDES**, utilisez :

`**setspn –s http/Server01.contoso.com contoso\NDESService**`

#### <a name="step-4---configure-ndes-for-use-with-intune"></a>Étape 4 : configurer NDES pour une utilisation avec Intune
Dans cette tâche, vous allez :

-   Configurer NDES pour une utilisation avec l'autorité de certification émettrice

-   Lier le certificat du serveur d'authentification (SSL) dans IIS

-   Configurer le filtrage de demandes dans IIS


1.  Sur le serveur NDES, ouvrez l’Assistant Configuration des services de certificats Active Directory et procédez aux configurations suivantes :

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

3. Le serveur NDES reçoit de très longues URL (requêtes), qui nécessitent l’ajout de deux entrées au Registre :

    |Localisation|Valeur|Type|Niveau|
    |-------|-----|----|----|
    |HKLM\SYSTEM\CurrentControlSet\Services\HTTP\Parameters|MaxFieldLength|DWORD|65534 (décimal)|
    |HKLM\SYSTEM\CurrentControlSet\Services\HTTP\Parameters|MaxRequestBytes|DWORD|65534 (décimal)|


4. Dans le Gestionnaire IIS, sélectionnez **Site Web par défaut** -> **Filtrage des demandes** -> **Modifier un paramètre de fonction**, et modifiez **Longueur maximale des URL** et **Longueur maximale des chaînes de requête** en spécifiant *65534*, comme indiqué.

    ![Longueur maximale des URL et des requêtes IIS](.\media\SCEP_IIS_max_URL.png)

5.  Redémarrez le serveur. L’exécution de **iisreset** sur le serveur ne suffit pas pour finaliser ces changements.
6. Accédez à http://*FQDN*/certsrv/mscep/mscep.dll. Vous devez voir une page NDES similaire à la suivante :

    ![Page NDES test](.\media\SCEP_NDES_URL.png)

    Si vous obtenez une erreur **503 Service indisponible**, consultez l’Observateur d’événements. Il est probable que le pool d’applications soit arrêté en raison de l’absence d’un droit pour l’utilisateur NDES. Ces droits sont décrits dans la tâche 1.

##### <a name="to-install-and-bind-certificates-on-the-ndes-server"></a>Pour installer et lier des certificats sur le serveur NDES

1.  Sur votre serveur NDES, demandez et installez un certificat d' **authentification serveur** auprès de votre autorité de certification interne ou autorité de certification publique. Vous liez ensuite ce certificat SSL dans IIS.

    > [!TIP]
    > Après avoir lié le certificat SSL dans IIS, installez un certificat d’authentification client. Ce certificat peut être émis par toute autorité de certification approuvée par le serveur NDES. Bien qu’il ne s’agisse pas d’une bonne pratique, vous pouvez utiliser le même certificat pour l’authentification serveur et l’authentification client tant que le certificat a les deux utilisations améliorées de la clé. Passez en revue les étapes suivantes pour plus d'informations sur ces certificats d'authentification.

    1.  Après avoir obtenu le certificat d'authentification serveur, ouvrez le **Gestionnaire IIS**, sélectionnez le **Site web par défaut** dans le volet **Connexions** , puis cliquez sur **Liaisons** dans le volet **Actions** .

    2.  Cliquez sur **Ajouter**, définissez **Type** avec la valeur **https**, puis vérifiez que le port est **443**. (Seul le port 443 est pris en charge pour la version autonome d’Intune).

    3.  Pour **Certificat SSL**, spécifiez le certificat d'authentification serveur.

        > [!NOTE]
        > Si le serveur NDES utilise un nom interne et un nom externe pour une même adresse réseau, le certificat d'authentification serveur doit avoir un **Nom de l'objet** avec un nom de serveur public externe et un **Autre nom de l'objet** incluant le nom du serveur interne.

2.  Sur votre serveur NDES, demandez et installez un certificat d' **authentification client** auprès de votre autorité de certification interne ou d'une autorité de certification publique. Cela peut être le même certificat que le certificat d'authentification serveur si ce certificat possède les deux fonctions.

    Le certificat d'authentification client doit avoir les propriétés suivantes :

    **Utilisation améliorée de la clé** : doit inclure l’**Authentification du client**.

    **Nom de l’objet** : doit être équivalent au nom DNS du serveur sur lequel vous installez le certificat (serveur NDES).

##### <a name="to-configure-iis-request-filtering"></a>Pour configurer le filtrage des demandes IIS

1.  Sur le serveur NDES, ouvrez le **Gestionnaire IIS**, sélectionnez le **Site web par défaut** dans le volet **Connexions** , puis ouvrez **Filtrage des demandes**.

2.  Cliquez sur **Modifier les paramètres de la fonctionnalité**, puis définissez les valeurs :

    **Chaîne de requête (octets)** = **65534**

    **Longueur maximale des URL (octets)** = **65534**

3.  Vérifiez la clé de Registre suivante :

    **HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\HTTP\Parameters**

    Vérifiez que les valeurs suivantes sont définies en tant qu'entrées DWORD :

    Nom : **MaxFieldLength**, avec une valeur décimale de **65534**

    Nom : **MaxRequestBytes**, avec une valeur décimale de **65534**

4. Redémarrez le serveur NDES. Le serveur est maintenant prêt à prendre en charge Certificate Connector.

#### <a name="step-5---enable-install-and-configure-the-intune-certificate-connector"></a>Étape 5 : activer, installer et configurer Intune Certificate Connector
Dans cette tâche, vous allez :

- activer la prise en charge de NDES dans Intune ;
- Téléchargez, installez et configurez Certificat Connector sur le serveur hébergeant le rôle de service d’inscription de périphériques réseau (NDES) dans votre environnement. Pour optimiser l’évolutivité de l’implémentation NDES dans votre organisation, vous pouvez installer plusieurs serveurs NDES avec Microsoft Intune Certificate Connector sur chaque serveur NDES.

##### <a name="to-download-install-and-configure-the-certificate-connector"></a>Pour télécharger, installer et configurer Certificate Connector
![Téléchargement de Connector](./media/certificates-download-connector.png)   
 
1. Connectez-vous au portail Azure. 
2. Sélectionnez **Autres services** > **Surveillance + Gestion** > **Intune**.
3. Dans le panneau **Intune**, sélectionnez **Configuration de l’appareil**.
4. Dans le panneau **Configuration de l’appareil**, sélectionnez **Autorité de certification**.
5. Cliquez sur **Ajouter** et sélectionnez **Télécharger le fichier du connecteur**. Enregistrez le fichier téléchargé à un emplacement accessible à partir du serveur où vous effectuerez l’installation. 
6.  Une fois le téléchargement terminé, exécutez le programme d'installation téléchargé (**ndesconnectorssetup.exe**) sur le serveur hébergeant le rôle de service d’inscription de périphériques réseau (NDES). Le programme d’installation installe également le module de stratégie pour NDES et le service web CRP. (Le service web CRP, CertificateRegistrationSvc, s'exécute en tant qu'application dans IIS.)

    > [!NOTE]
    > Quand vous installez NDES pour la version autonome d’Intune, le service CRP est installé automatiquement avec Certificate Connector. Quand vous utilisez Intune avec Configuration Manager, vous installez le Point d’enregistrement de certificat comme rôle de système de site distinct.

3.  Quand vous êtes invité à entrer le certificat client pour le Certificate Connector, choisissez **Sélectionner**, puis sélectionnez le certificat **d'authentification client** installé sur votre serveur NDES à la tâche 3.

    Après avoir sélectionné le certificat d'authentification client, vous revenez au **Certificat client pour Microsoft Intune Certificate Connector** . Bien que le certificat sélectionné n'apparaisse pas, cliquez sur **Suivant** pour afficher les propriétés du certificat. Cliquez sur **Suivant**, puis cliquez sur **Installer**.

4.  Une fois l'Assistant terminé, mais avant de fermer l'Assistant, cliquez sur **Lancer l'interface utilisateur de Certificate Connector**.

    > [!TIP]
    > Si vous fermez l'Assistant avant de lancer l'interface utilisateur de Certificate Connector, vous pouvez le rouvrir en exécutant la commande suivante :
    >
    > **&lt;chemin_installation&gt;\NDESConnectorUI\NDESConnectorUI.exe**

5.  Dans l'interface utilisateur de **Certificate Connector** :

    Cliquez sur **Connexion** et entrez vos informations d’identification du service Intune ou les informations d’identification d’un administrateur client avec l’autorisation d’administration globale.

    > [!IMPORTANT]
    > Une licence Intune valide doit être affectée au compte d’utilisateur. Si le compte d’utilisateur ne dispose pas d’une licence Intune valide, NDESConnectorUI.exe échoue.

    Si votre organisation utilise un serveur proxy et que ce dernier est nécessaire au serveur NDES pour accéder à Internet, cliquez sur **Utiliser un serveur proxy**, puis indiquez le nom, le port et les informations d’identification de compte du serveur proxy pour vous connecter.

    Sélectionnez l'onglet **Avancé** , puis fournissez les informations d'identification d'un compte qui possède l'autorisation **Émettre et gérer des certificats** sur votre autorité de certification émettrice, puis cliquez sur **Appliquer**.

    Vous pouvez maintenant fermer l'interface utilisateur de Certificate Connector.

6.  Ouvrez une invite de commandes et tapez **services.msc**, appuyez sur **Entrée**, cliquez avec le bouton droit sur **Service du connecteur Intune**, puis cliquez sur **Redémarrer**.

Pour valider que le service s'exécute, ouvrez un navigateur et entrez l'URL suivante, ce qui doit retourner une erreur **403** :

**http:// &lt;nom_de_domaine_complet_de_votre_serveur_NDES&gt;/certsrv/mscep/mscep.dll**

## <a name="how-to-create-a-scep-certificate-profile"></a>Comment créer un profil de certificat SCEP

1. Dans le portail Azure, sélectionnez la charge de travail **Configurer des appareils**.
2. Dans le panneau **Configuration de l’appareil**, sélectionnez **Gérer** > **Profils**.
3. Dans le panneau des profils, sélectionnez **Créer un profil**.
4. Dans le panneau **Créer un profil**, entrez un **Nom** et une **Description** pour le profil de certificat SCEP.
5. Dans la liste déroulante **Plateforme**, sélectionnez la plateforme d’appareil pour ce certificat SCEP. Actuellement, vous pouvez sélectionner l’une des plateformes suivantes pour les paramètres de restriction de l’appareil :
    - **Android**
    - **iOS**
    - **MacOS**
    - **Windows Phone 8.1**
    - **Windows 8.1 et versions ultérieures**
    - **Windows 10 et versions ultérieures**
6. Dans la liste déroulante **Type de profil**, sélectionnez **Certificat SCEP**.
7. Dans le panneau **Certificat SCEP**, configurez les paramètres suivants :
    - **Période de validité du certificat** : si vous avez exécuté la commande **certutil - setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE** sur l’autorité de certification émettrice, ce qui autorise une période de validité personnalisée, vous pouvez spécifier le temps restant avant l’expiration du certificat.<br>Vous pouvez spécifier une valeur inférieure à la période de validité du modèle de certificat spécifié, mais pas une valeur supérieure. Par exemple, si la période de validité du certificat dans le modèle de certificat est de 2 ans, vous pouvez spécifier une valeur de 1 an mais pas une valeur de 5 ans. La valeur doit également être inférieure à la période de validité restante du certificat de l’autorité de certification émettrice. 
    - **Fournisseur de stockage de clés** (Windows Phone 8.1, Windows 8.1, Windows 10) : Spécifiez l’emplacement de stockage de la clé du certificat. Choisissez l'une des valeurs suivantes :
        - **Inscrire auprès du fournisseur de stockage de clés (KSP) du module de plateforme sécurisée (TPM) s’il est présent ; sinon, inscrire auprès du fournisseur de stockage de clés du logiciel**
        - **Inscrire auprès du fournisseur de stockage de clés (KSP) du module de plateforme sécurisée (TPM), sinon mettre en échec**
        - **Inscrire auprès de Passport, sinon mettre en échec (Windows 10 et versions ultérieures)**
        - **Inscrire auprès du fournisseur de stockage de clés du logiciel**
    - **Format du nom de l’objet** : dans la liste, sélectionnez comment Intune crée automatiquement le nom de l’objet dans la demande de certificat. Si le certificat est pour un utilisateur, vous pouvez également inclure l'adresse e-mail de cet utilisateur dans le nom de l'objet. Choisissez parmi :
        - **Non configuré**
        - **Nom commun**
        - **Nom commun (adresse e-mail incluse)**
        - **Nom commun comme adresse e-mail**
        - **IMEI (International Mobile Equipment Identity)**
        - **Numéro de série**
        - **Personnalisé** : lorsque vous sélectionnez cette option, un autre champ de liste déroulante s’affiche. Ce champ vous permet d’entrer un format de nom d’objet personnalisé. Les deux variables prises en charge pour le format personnalisé sont **Nom courant (cn)** et **Message électronique (e)**. En combinant une ou plusieurs ces variables avec des chaînes statiques, vous pouvez créer un format de nom d’objet personnalisé tel que celui-ci : **CN={{UserName}},E={{EmailAddress}},OU=Mobile,O=Finance Group,L=Redmond,ST=Washington,C=US** Dans cet exemple, vous avez créé un format de nom d’objet qui, en plus des variables CN et E, utilise des chaînes pour les valeurs Organizational Unit (Unité organisationnelle), Organization (Organisation), Location (Emplacement), State (État) et Country (Pays). [Cette rubrique](https://msdn.microsoft.com/library/windows/desktop/aa377160.aspx) illustre la fonction **CertStrToName** et ses chaînes prises en charge.
        
    - **Autre nom de l’objet** : spécifiez comment Intune crée automatiquement les valeurs pour l’autre nom de l’objet dans la demande de certificat. Par exemple, si vous avez sélectionné un type de certificat utilisateur, vous pouvez inclure le nom d'utilisateur principal (UPN) dans l'autre nom de l'objet. Si le certificat client est utilisé pour l’authentification sur un serveur de stratégie réseau, vous devez affecter le nom d’utilisateur principal à l’autre nom de l’objet. 
    - **Utilisation de la clé** : spécifiez les options d’utilisation de la clé pour le certificat. Vous pouvez choisir parmi les options suivantes : 
        - **Chiffrage de clés** : autorisez l’échange de clés uniquement quand la clé est chiffrée. 
        - **Signature numérique** : autorisez l’échange de clés uniquement quand une signature numérique contribue à protéger la clé. 
    - **Taille de la clé (bits)** : Sélectionnez le nombre de bits contenus dans la clé. 
    - **Algorithme de hachage** (Android, Windows Phone 8.1, Windows 8.1, Windows 10) : sélectionnez l’un des types d’algorithme de hachage disponibles avec ce certificat. Permet de sélectionner le niveau le plus élevé de sécurité pris en charge par les appareils se connectant. 
    - **Certificat racine** : choisissez un profil de certificat d’autorité de certification racine que vous avez précédemment configuré et attribué à l’utilisateur ou à l’appareil. Ce certificat d’autorité de certification doit être le certificat racine de l’autorité de certification qui émet le certificat que vous configurez dans ce profil de certificat. 
    - **Utilisation de la clé étendue** : sélectionnez **Ajouter** pour ajouter des valeurs pour le rôle prévu du certificat. Dans la plupart des cas, le certificat demande une **authentification client** pour que l’utilisateur ou l’appareil puisse être authentifié auprès d’un serveur. Toutefois, vous pouvez ajouter d'autres utilisations de la clé en fonction de vos besoins. 
    - **Paramètres d’inscription**
        - **Seuil de renouvellement (%)** : spécifiez le pourcentage de durée de vie restante du certificat avant que l’appareil ne demande le renouvellement du certificat.
        - **URL du serveur SCEP** : Spécifiez une ou plusieurs URL pour les serveurs NDES qui délivrent les certificats par le biais de SCEP. 
8. Lorsque vous avez terminé, revenez au panneau **Créer un profil** et appuyez sur **Créer**.

Le profil est créé et s’affiche dans le panneau de la liste des profils.

## <a name="how-to-assign-the-certificate-profile"></a>Comment affecter le profil de certificat

Considérez les éléments suivants avant d’attribuer des profils de certificat aux groupes :

- Quand vous attribuez des profils de certificat aux groupes, le fichier de certificat issu du profil de certificat d’autorité de certification approuvée est installé sur l’appareil. L’appareil utilise le profil de certificat SCEP pour créer une demande de certificat par l’appareil.
- Les profils de certificat s’installent uniquement sur les appareils exécutant la plateforme que vous utilisez quand vous créez le profil.
- Vous pouvez affecter des profils de certificat sur des regroupements d’utilisateurs ou d’appareils.
- Pour publier un certificat sur un appareil rapidement après l’inscription de l’appareil, affectez le profil de certificat à un groupe d’utilisateurs plutôt qu’à un groupe d’appareils. Si vous l’affectez à un groupe d’appareils, une inscription complète des appareils est préalablement nécessaire pour qu’ils puissent recevoir des stratégies.
- Même si vous affectez chaque profil séparément, vous devez également affecter l’autorité de certification racine approuvée et le profil SCEP ou PKCS. Dans le cas contraire, la stratégie de certificat SCEP ou PKCS échoue.

Pour plus d’informations sur la façon d’affecter des profils, consultez [Guide pratique pour attribuer des profils d’appareils](device-profile-assign.md).

