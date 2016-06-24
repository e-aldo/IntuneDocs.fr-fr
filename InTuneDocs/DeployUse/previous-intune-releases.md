---
# required metadata

title: Versions précédentes | Microsoft Intune
description:
keywords:
author: Lindavr
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 45dad14a-d412-488d-bb1e-ad990ea503df

# optional metadata

ROBOTS: noindex,nofollow
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Versions précédentes d’Intune

## Avril 2016
Toutes ces fonctionnalités sont également prises en charge pour les clients hybrides (Configuration Manager intégré à Intune).
### Gestion d'applications
- **Conformité MAM de l’utilisateur.**
Vous pouvez désormais afficher l’[état](monitor-mobile-app-management-policies-with-Microsoft-Intune.md) de vos stratégies de gestion d’applications pour n'importe quel utilisateur dans votre client Azure Active Directory (AAD). Les opérations à effectuer sont les suivantes :
   - Appareils
   - Applications sur l’appareil

   Valeurs d'état :

   **Activé** : indique que la stratégie a été déployée pour l'utilisateur, que l’application a été utilisée dans un contexte professionnel et qu’elle a reçu avec succès la stratégie.

    **Non activé :** indique que la stratégie a été déployée pour l’utilisateur, mais que l’application n’a pas été utilisée au moins une fois dans un contexte professionnel depuis.


- **Contrôles MAM pour empêcher la synchronisation des contacts Outlook (Android).**
Un nouveau paramètre est disponible pour la [gestion des applications mobiles](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) sans inscription de l'appareil. Ce paramètre vous permet d’empêcher une application de synchroniser les contacts avec le carnet d'adresses natif sur les appareils Android. Si ce paramètre est activé, les applications ciblées ne pourront plus enregistrer les contacts dans le carnet d'adresses natif. Si ce paramètre est désactivé, les applications ciblées pourront enregistrer les contacts dans le carnet d'adresses natif. Lorsque vous [réinitialisez de façon sélective un appareil ou une application](wipe-managed-company-app-data-with-Microsoft-Intune.md), les contacts déjà enregistrés dans le carnet d'adresses natif seront supprimés. Ce nouveau paramètre est initialement pris en charge par l'application Outlook sur les appareils Android.

### Gestion des appareils
- **Identification de numéros de téléphone pour les appareils appartenant à l'entreprise.** Les téléphones classés comme « appartenant à l’entreprise » sont identifiés avec leur numéro de téléphone complet, par exemple, lorsque vous exécutez un rapport d’inventaire des appareils mobiles. Les numéros de téléphone de type « BYOD » continuent d’être masqués avec **** ; seuls les 4 derniers chiffres s’affichent.


### Mises à jour de Portail d'entreprise
**Application Portail d’entreprise Android** Les utilisateurs qui n’ont pas inscrit leur appareil dans Intune et qui n’ont pas le bon certificat installé ne peuvent pas se connecter à l’application Portail d’entreprise Android. Le message suivant s’affiche : « Vous ne pouvez pas vous connecter, car il manque un certificat obligatoire à votre appareil ». Le message inclut un lien « Comment résoudre ce problème » permettant aux utilisateurs d’obtenir des instructions pour installer le certificat. Pour connaître les étapes que les utilisateurs finaux doivent suivre pour résoudre ce problème, consultez [Un certificat obligatoire est manquant sur votre appareil](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_cert_missing).

**Application Portail d’entreprise iOS** Une prise en charge a été ajoutée pour l’action Tirer pour actualiser permettant d’actualiser le contenu sur l’écran d’accueil, notamment les applications répertoriées, les appareils répertoriés et les informations sur les contacts informatiques. L'action Tirer pour actualiser ne vérifie pas les informations de conformité ou de stratégie, opération qui peut être effectuée en sélectionnant la vignette correspondant à votre appareil puis en appuyant sur le bouton **Sync**.

**Application Portail d’entreprise Windows 10 Mobile et Windows Phone 8.1** Quand les utilisateurs finaux installent des applications métier, ils bénéficient d’une expérience d’installation améliorée. Si l'installation de l'application prend beaucoup de temps, les utilisateurs peuvent synchroniser manuellement leur appareil pour forcer la reprise du processus de synchronisation. Pour obtenir les instructions de l’utilisateur final, consultez [Synchroniser votre appareil manuellement pour accélérer l’installation des applications](https://technet.microsoft.com/library/mt427782.aspx#BKMK_win10m_wp81_sync_manually).

**Site web du portail d’entreprise** Quand les utilisateurs Windows 10 Mobile et Windows Phone 8.1 installent des applications métier, les nouveaux états suivants apparaissent et leur fournissent plus de détails sur l’état de leur installation :

* **En attente de la synchronisation de l’appareil** : l'utilisateur a appuyé sur « Installer » et l'appareil tente à présent de se synchroniser avec l'infrastructure Intune. La synchronisation est nécessaire pour pouvoir finaliser l'installation. Le message « En attente de la synchronisation de l’appareil » contient également un lien sur lequel les utilisateurs peuvent cliquer pour obtenir des [instructions](https://technet.microsoft.com/library/mt590895.aspx#BKMK_iwp_sync_manually) sur la synchronisation manuelle de leur appareil avec Intune si le processus de synchronisation prend beaucoup de temps ou se bloque.
* **Téléchargement** : la demande de téléchargement de l'utilisateur est en cours de traitement et l’appareil télécharge et installe l'application.

Avant l'ajout de ces états, les utilisateurs étaient désorientés lorsque l’installation de l'application prenait beaucoup de temps car seul l’état « Installation » s’affichait à l'écran, parfois pendant des heures. Grâce à l’ajout de ces nouveaux états, au lieu d'appeler le support technique, les utilisateurs peuvent désormais appuyer sur le lien « En attente de la synchronisation de l’appareil » et suivre les instructions pour forcer la reprise du processus de synchronisation.


## Mars 2016
### Nouveautés au 29 mars 2016
À l’exception de la mise à jour de la stratégie de configuration générale Windows 10, toutes les fonctionnalités publiées le 29 mars 2016, sont également prises en charge pour les clients hybrides (Configuration Manager intégré à Intune). La prise en charge d’un environnement hybride pour la mise à jour de la stratégie de configuration générale Windows 10 sera bientôt disponible. Veuillez noter que certaines de ces fonctionnalités peuvent nécessiter la dernière version du Configuration Manager.

### Gestion d'applications
- **Contrôles MAM pour empêcher la synchronisation des contacts Outlook (iOS).** Un nouveau paramètre est disponible pour la gestion des applications mobiles sans inscription de l'appareil. Ce paramètre vous permet d’empêcher une application de synchroniser les contacts avec le carnet d'adresses natif sur les appareils iOS. Si ce paramètre est activé, l'application ne pourra plus enregistrer les contacts dans le carnet d'adresses natif. Si ce paramètre est désactivé, l'application pourra enregistrer les contacts dans le carnet d'adresses natif. Lorsque vous réinitialisez de façon sélective un appareil ou une application, tous les contacts déjà enregistrés dans le carnet d'adresses natif seront supprimés. Ce nouveau paramètre est pris en charge par l'application Outlook sur les appareils iOS. Pour plus d’informations à ce sujet et sur d’autres paramètres, consultez [Créer et déployer des stratégies de gestion des appareils mobiles](https://technet.microsoft.com/en-us/library/dn292747.aspx).

### Contrôle d'accès
- **Skype Entreprise Online prend en charge l'accès conditionnel.** Vous pouvez définir une stratégie d'accès conditionnel pour Skype Entreprise Online afin que cette application soit uniquement accessible aux appareils iOS et Android gérés et compatibles. Les utilisateurs finaux qui essaient de se connecter à l’application mobile Skype Entreprise sur un appareil iOS et Android seront invités à s'inscrire auprès d’Intune et à résoudre les éventuels problèmes d'incompatibilité avant de finaliser la connexion. Pour plus d’informations, consultez [Manage access to Skype for Business Online](https://technet.microsoft.com/en-us/library/mt695297.aspx) (Gestion de l’accès à Skype Entreprise Online).

### Gestion des appareils
- **Prise en charge d’Intune pour iOS 9.3.** Le Lundi 21 mars, Apple a annoncé la mise sur le marché d’iOS 9.3. Nous avons travaillé à assurer la compatibilité de Microsoft Intune avec la dernière version du système d’exploitation mobile Apple et [nous avons le plaisir d’annoncer qu’Intune prend en charge la gestion des appareils iOS 9.3](https://blogs.technet.microsoft.com/microsoftintune/2016/03/23/microsoft-intune-provides-support-for-ios-9-3/).

  Toutes les fonctionnalités Intune existantes actuellement disponibles pour la gestion des appareils iOS continue de fonctionner en toute transparence lorsque les utilisateurs migrent leurs appareils vers iOS 9.3. iOS 9.3 est également pris en charge aujourd’hui pour les clients hybrides (Configuration Manager intégré à Intune).

- **La stratégie de configuration générale Windows 10 contient maintenant des paramètres pour gérer Windows Defender sur des PC Windows 10 inscrits.** Pour plus d’informations, consultez [Paramètres de la stratégie de configuration Windows 10 dans Microsoft Intune](https://technet.microsoft.com/en-us/library/mt404697.aspx).


### Portail d'entreprise

- **Packages d’applications Windows disponibles directement accessibles depuis le portail d’entreprise.** Les utilisateurs de PC sous Windows 8, Windows 8.1 et Windows RT peuvent désormais installer des packages d'applications Windows (avec l'extension .aspx) directement depuis le site Web du portail d'entreprise. Auparavant, vous deviez effectuer le déploiement, ou les utilisateurs devaient installer l'application Portail d'entreprise sur leurs appareils pour installer des applications.

- **Les utilisateurs peuvent verrouiller à distance leurs appareils depuis le portail d’entreprise** Une nouvelle option de verrouillage à distance a été ajoutée au site Web du portail d'entreprise pour permettre aux utilisateurs de verrouiller à distance leurs appareils depuis le portail si leur appareil est égaré ou volé. Consultez les [instructions pour l’utilisateur final](https://technet.microsoft.com/library/mt590895.aspx/?wt.mc_id=ui#BKMK_iwp_remote_lock). Le tableau suivant répertorie les plates-formes prises en charge pour le verrouillage à distance avec Intune en mode autonome et Intune avec Configuration Manager.

|Plate-forme | Détails de la prise en charge|
|---------|----------------|
|Android |Pris en charge|
|iOS |Pris en charge|
|Windows 10 Mobile |Pris en charge uniquement si le téléphone dispose d’un code secret|
|Windows 10 Desktop |Non prise en charge|
|Windows Phone 8.1 |Pris en charge uniquement si le téléphone dispose d’un code secret|
|Windows Phone 8.0 |Non prise en charge|
|PC (Windows 8.0 et versions antérieures) |Non prise en charge|
|PC (Windows 8.1) |Non pris en charge|

### Nouveautés au 10 mars 2016

### Gestion d'applications

- **Tirer parti de la gestion « Open-in » d’iOS pour les appareils qui sont inscrits dans une solution tierce de gestion des appareils mobiles** Vous pouvez utiliser votre fournisseur tiers de gestion des appareils mobiles pour tirer parti de la gestion « Open-In » d’iOS. Vous pouvez définir des restrictions dans les paramètres de profil de configuration et déployer l’application à l’aide des informations contenues dans [Gérer les transferts de données entre applications iOS](manage-data-transfer-between-ios-apps-with-microsoft-intune.md).

     Cette approche présente deux avantages principaux :

     1. Les utilisateurs doivent se connecter avec leur compte professionnel avant de pouvoir accéder à des données d’entreprise à partir des services cloud ou d’autres applications. Cela permet de s’assurer que les stratégies de gestion des applications mobiles sont en place lors de l’accès aux données.

     2. Les profils de messagerie gérés et d’autres applications gérées déployées par le biais d’une solution de gestion des appareils mobiles tierce peuvent partager des fichiers et des données avec les applications qui ont des stratégies MAM Intune.

- **Gérer l’application Microsoft Outlook avec des stratégies GAM pour les appareils non inscrits dans Intune** Vous pouvez désormais gérer l’application Microsoft Outlook sur les appareils qui ne sont pas inscrits dans Intune avec la stratégie de gestion des applications mobiles Intune. L’application Microsoft Outlook mise à jour avec les fonctionnalités MAM est disponible pour les appareils [iOS](https://itunes.apple.com/us/app/microsoft-outlook-email-calendar/id951937596?mt=8) et [Android](https://play.google.com/store/apps/details?id=com.microsoft.office.outlook). Suivez les instructions de la rubrique [Créer et déployer des stratégies de gestion des applications mobiles](https://technet.microsoft.com/library/mt627829.aspx) pour créer une stratégie MAM.  


- **Les stratégies de configuration des applications mobiles offrent plus de souplesse pour spécifier les détails de l’utilisateur pour les applications iOS** Vous pouvez fournir des paramètres utilisateur dont une application iOS peut avoir besoin quand elle est ouverte. Par exemple, vous pouvez fournir un port réseau ou un nom d’utilisateur. Pour plus d’informations, consultez [Configurer des applications iOS avec des stratégies de configuration des applications mobiles dans Microsoft Intune](configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune.md).


- **Déployer Adobe Reader pour Microsoft Intune sur des appareils iOS gérés par Intune dans votre entreprise** L’application Adobe Reader pour iOS peut maintenant être gérée sur les appareils inscrits avec la stratégie de gestion des applications mobiles Intune.

- **Vérifiez que les clips web déployés sont ouverts dans Managed Browser** Vous pouvez déployer des clips web ciblés qui peuvent uniquement être ouverts à l’aide de Managed Browser sur des appareils iOS et Android. Par exemple, vous déployez des liens vers des ressources d’entreprise par le biais du portail d’entreprise et, quand les utilisateurs accèdent aux liens, ils s’ouvrent directement dans Managed Browser où ils peuvent être protégés par une stratégie de gestion des applications mobiles. Pour plus d’informations, consultez [Déployer des applications](deploy-apps.md).


- **Rechercher, gérer et distribuer des applications Windows Store pour Entreprises pour les appareils Windows 10 à partir de la console d’administration Intune** La prise en charge du Windows Store pour Entreprises est disponible dans Intune pour vous aider à rechercher, gérer et distribuer des applications sur les appareils Windows 10 que vous gérez. Le Windows Store pour Entreprises vous permet de gérer le processus de déploiement et de surveillance de ces applications à partir de la console Administrateur Intune, la même console que vous utilisez pour gérer vos autres applications. Plus précisément, le Windows Store pour Entreprises gère le contenu et les licences des « applications sous licence en ligne ». Pour plus d’informations, consultez [Gérer les applications que vous avez achetées dans Windows Store pour Entreprises](manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune.md).


### Gestion des appareils
- **Distribution de certificats PFX pour les appareils iOS** Les administrateurs Intune peuvent créer et déployer des certificats PFX iOS pour l’authentification Wi-Fi, e-mail et VPN sur les appareils iOS. Cette fonctionnalité est déjà disponible pour les appareils Android et Windows 10. Pour plus d’informations, consultez [Activer l’accès aux ressources d’entreprise à l’aide de profils de certificat](secure-resource-access-with-certificate-profiles.md).


- **Appliquer des applications et des stratégies à différents groupes d’appareils en fonction de la sélection de catégorie de l’utilisateur** Les administrateurs Intune peuvent maintenant définir des catégories d’appareils personnalisées que les utilisateurs peuvent sélectionner pendant l’inscription. Par exemple, les administrateurs peuvent souhaiter que les utilisateurs spécifient s’ils inscrivent un appareil utilisé pour « Caisse enregistreuse », « Camion de livraison » ou « Salle des inventaires ». La catégorie sélectionnée fait que l’appareil devient membre d’un groupe d’appareils Intune, qui peut être utilisé pour le déploiement de différentes stratégies et applications sur l’appareil inscrit. Pour plus d’informations, consultez [Catégoriser les appareils avec le mappage de groupe d’appareils](categorize-devices-with-device-group-mapping-in-microsoft-intune.md).

### Modifications et mises à jour du portail d’entreprise Microsoft
Les modifications suivantes ont été apportées au portail d’entreprise dans cette version.

**Application Portail d’entreprise Android**

* Quand vos utilisateurs lancent une application gérée par la gestion des applications mobiles (MAM), un message les avertit que l’application est gérée par leur société. Les utilisateurs peuvent désormais appuyer sur un lien « En savoir plus » pour obtenir des [informations supplémentaires](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_use_mgd_apps) sur ce que signifie le terme « applications gérées ». Ils peuvent aussi appuyer sur « Ne plus afficher » pour que le message n’apparaisse plus lors du lancement de l’application.
* De nouveaux écrans ont été ajoutés pour guider les utilisateurs lors du processus d’inscription, et pour fournir des informations supplémentaires sur la raison pour laquelle ils doivent s’inscrire et sur ce que les administrateurs informatiques peuvent et ne peuvent pas voir sur leurs appareils inscrits. Pour plus d’informations, consultez les [instructions d’inscription](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_enroll_devc).
* Les messages d’erreur d’inscription sont maintenant affichés dans l’application Portail d’entreprise. Auparavant, ces messages étaient affichés sur le site web du portail d’entreprise. Cette modification signifie que tous les messages d’erreur apparaissent maintenant à un seul endroit, plutôt qu’à deux emplacements différents.


**Application Portail d’entreprise iOS**
* Quand vos utilisateurs lancent une application gérée par la gestion des applications mobiles (MAM), un message les avertit que l’application est gérée par leur société. Les utilisateurs peuvent désormais appuyer sur un lien « En savoir plus » pour obtenir des [informations supplémentaires](https://technet.microsoft.com/library/mt598622.aspx#BKMK_ios_use_mgd_apps) sur ce que signifie le terme « applications gérées ». Ils peuvent aussi appuyer sur « Ne plus afficher » pour que le message n’apparaisse plus lors du lancement de l’application.
* De nouveaux écrans ont été ajoutés pour guider les utilisateurs lors du processus d’inscription, et pour fournir des informations supplémentaires sur la raison pour laquelle ils doivent s’inscrire et sur ce que les administrateurs informatiques peuvent et ne peuvent pas voir sur leurs appareils inscrits. Pour plus d’informations, consultez les [instructions d’inscription](https://technet.microsoft.com/library/mt598622.aspx#BKMK_enroll_ios_device).
* Les messages d’erreur d’inscription sont maintenant affichés dans l’application Portail d’entreprise. Auparavant, ces messages étaient affichés sur le site web du portail d’entreprise. Cette modification signifie que tous les messages d’erreur apparaissent maintenant à un seul endroit, plutôt qu’à deux emplacements différents.




## Février 2016
### Modifications et mises à jour du portail d’entreprise Microsoft

Les modifications suivantes ont été apportées au portail d’entreprise dans cette version.

#### Application Portail d’entreprise Android
- De nouveaux écrans ont été ajoutés pour guider les utilisateurs lors du processus d’inscription, et pour fournir des informations supplémentaires sur la raison pour laquelle ils doivent s’inscrire et sur ce que les administrateurs informatiques peuvent et ne peuvent pas voir sur leurs appareils inscrits. Pour plus d’informations, consultez les [instructions d’inscription](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_enroll_devc).
- Les messages d’erreur d’inscription sont maintenant affichés dans l’application Portail d’entreprise. Auparavant, ces messages étaient affichés sur le site web du portail d’entreprise. Cette modification signifie que tous les messages d’erreur apparaissent maintenant à un seul endroit, plutôt qu’à deux emplacements différents.

#### Application Portail d’entreprise iOS
 - De nouveaux écrans ont été ajoutés pour guider les utilisateurs lors du processus d’inscription, et pour fournir des informations supplémentaires sur la raison pour laquelle ils doivent s’inscrire et sur ce que les administrateurs informatiques peuvent et ne peuvent pas voir sur leurs appareils inscrits. Pour plus d’informations, consultez les [instructions d’inscription](https://technet.microsoft.com/library/mt598622.aspx#BKMK_enroll_ios_device).

 - Les messages d’erreur d’inscription sont maintenant affichés dans l’application Portail d’entreprise. Auparavant, ces messages étaient affichés sur le site web du portail d’entreprise. Cette modification signifie que tous les messages d’erreur apparaissent maintenant à un seul endroit, plutôt qu’à deux emplacements différents.


## Janvier 2016

### Tirer parti des fonctionnalités de Windows 10
* **Accès conditionnel avec le service d’attestation de l’intégrité** Les administrateurs Intune peuvent désormais afficher l’état de l’attestation de l’intégrité des appareils Windows 10 dans la console d’administration Intune. L’attestation de l’intégrité des appareils permet à l’administrateur de s’assurer que les ordinateurs clients ont des configurations de BIOS, de Module de plateforme sécurisée (TPM) et de logiciel de démarrage dignes de confiance. Pour prendre en charge l’attestation de l’intégrité des appareils, les appareils clients doivent exécuter Windows 10 avec le Module de plateforme sécurisée (TPM) 2 activé. L’attestation de l’intégrité des appareils affiche le nombre d’appareils activés pour chacun des éléments suivants :
    * Logiciel anti-programme malveillant à lancement anticipé
    * BitLocker
    * Démarrage sécurisé
    * Intégrité du code

    Pour plus d’informations sur le paramètre d’intégrité des appareils, sur les points de données recueillis et sur le rapport d’attestation d’intégrité, consultez [Introduction aux stratégies de conformité des appareils pour Microsoft Intune](introduction-to-device-compliance-policies-in-microsoft-intune.md). Pour en savoir plus, référez-vous aux [détails du service HAS](https://msdn.microsoft.com/en-us/library/dn934876.aspx).

* [Stratégie Windows 10 Passport for Work et gestion des certificats](control-microsoft-passport-settings-on-devices-with-microsoft-intune.md) Avec Intune, vous pouvez **intégrer Microsoft Passport for Work** et disposer ainsi d’une méthode de connexion alternative pour Windows 10 qui utilise Active Directory ou un compte Azure Active Directory pour remplacer un mot de passe, une carte à puce ou une carte à puce virtuelle. Passport vous permet d’utiliser un mouvement utilisateur pour vous connecter, au lieu d’un mot de passe. Un mouvement utilisateur peut être un simple code confidentiel, une authentification biométrique telle que Windows Hello ou un appareil externe tel qu’un lecteur d’empreintes digitales.

* **VPN pour des applications spécifiques** Vous pouvez sélectionner les applications qui se connectent automatiquement à votre réseau d’entreprise par le biais du VPN. Créez la liste des applications quand vous configurez le profil VPN, comme décrit dans Aider les utilisateurs à se connecter à leur travail à l’aide de profils VPN avec Microsoft Intune.

* **Prise en charge de la réinitialisation complète de Windows 10** Vous pouvez maintenant effectuer une réinitialisation complète à distance d’appareils Windows 10 Desktop inscrits dans Intune par le biais de la console d’administration Intune. La réinitialisation complète de Windows 10 effectue une réinitialisation aux paramètres d’usine de l’appareil.


### Mise à jour du programme VPP (Volume Purchase Program) d’Apple
Intune peut maintenant vous aider à [gérer les applications que vous avez achetées par le biais du programme VPP (Volume Purchase Program) d’Apple pour les entreprises](manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune.md). Cela comprend la synchronisation des informations de licence entre Apple et Intune, et le suivi du nombre de copies de chaque application que vous avez déployées.

### Utiliser des numéros IMEI pour identifier les appareils appartenant à l’entreprise
Vous pouvez désormais [importer des numéros IMEI (international mobile equipment identity)](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md) pour les plates-formes d’appareils mobiles ayant ce type de numéro, afin de faciliter l’identification des appareils mobiles appartenant à l’entreprise. Une fois inscrit dans Intune, les appareils avec des numéros IMEI importés sont marqués comme appareils d’entreprise, ce qui peut être utilisé pour appliquer des stratégies différentes de celles appliquées aux appareils personnels.

### Davantage d’applications sont désormais compatibles avec les stratégies MAM Intune
Des applications supplémentaires de partenaires de Microsoft sont désormais compatibles avec les stratégies de gestion des applications mobiles (MAM) Intune (pour les appareils gérés par Intune) :
* Box for EMM (de Box Inc) : iOS uniquement
* Adobe Reader (d’Adobe) : Android uniquement
* Foxit PDF Reader (de Foxit Corporation) : iOS et Android


### La prise en charge d’IE9 cesse en janvier
Le support d’Internet Explorer 9 prend fin dès le mois de février 2016. Dès lors, ce ne sera plus le navigateur officiel pour accéder au site web Portail d’entreprise Microsoft Intune, au portail de compte Intune et à la console d’administration Intune. Vous devrez migrer vers Internet Explorer 10 ou version ultérieure.

## Décembre 2015
### Modifications et mises à jour du portail d’entreprise Microsoft
Les modifications suivantes ont été apportées au portail d’entreprise dans cette version.

**Application Portail d’entreprise Android**

Les modifications suivantes ont été apportées pour se conformer aux nouvelles exigences de Google. Sur les appareils Android 6.0 et versions ultérieures, deux nouveaux messages sont présentés aux utilisateurs :
* Autoriser l’application Portail d’entreprise à passer et gérer des appels téléphoniques ?
* Autoriser l’application Portail d’entreprise à accéder aux photos, aux fichiers multimédias et aux fichiers de votre appareil ?

Pour plus d’informations sur ces deux messages, consultez les tableaux suivants.



Texte du message  |Autoriser l’application Portail d’entreprise à passer et gérer des appels téléphoniques ?  
---------|---------
Signification du message     |  Permet d’envoyer le numéro IMEI et le numéro de téléphone de l’appareil de l’utilisateur au service Intune et de les afficher dans la console d’administration sur la page Matériel.   </br></br>**REMARQUE : L’application Portail d’entreprise ne passe et ne gère jamais d’appels téléphoniques !** Le texte du message est contrôlé par Google et ne peut pas être modifié. </br></br>Pour afficher la page **Matériel**, accédez à **Groupes** > **Tous les appareils mobiles** > **Appareils**. Sélectionnez l’appareil de l’utilisateur et accédez à **Afficher les propriétés** > **Matériel**.    
Où et quand le message s’affiche  | Le message s’affiche quand les utilisateurs se connectent à l’application Portail d’entreprise pour la première fois pour inscrire leur appareil.|         
Ce qui se passe si les utilisateurs autorisent l’accès  |  Le numéro IMEI et le numéro de téléphone de l’appareil s’affichent dans la console d’administration de la page Matériel. |         
Ce qui se passe si les utilisateurs refusent l’accès     | Ils peuvent continuer à utiliser l’application Portail d’entreprise et inscrire leur appareil, mais le numéro IMEI et le numéro de téléphone de l’appareil de l’utilisateur sont vides dans la console d’administration de la page Matériel.       </br></br> La deuxième fois que les utilisateurs se connectent à l’application Portail d’entreprise après le refus de l’accès, le message affiche une case **Ne plus me demander** que les utilisateurs peuvent cocher pour que le message ne s’affiche plus.</br></br>Si les utilisateurs autorisent, puis refusent par la suite l’accès, le message s’affiche la prochaine fois qu’ils se connectent à l’application Portail d’entreprise après l’inscription.</br></br>Si les utilisateurs décident par la suite d’autoriser l’accès, ils peuvent accéder à **Paramètres** > **Applications** > **Portail d’entreprise** > **Autorisations** > **Téléphone**, puis activer l’autorisation.
Plus d'informations     |  Pour vos utilisateurs : [Se connecter à l’application Portail d’entreprise](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_signin_cp)  </br></br>Pour les professionnels de l’informatique : Les informations présentes dans ce tableau figurent également dans [Description des messages de l’application Portail d’entreprise pour vos utilisateurs](https://technet.microsoft.com/library/dn948527.aspx#BKMK_help_users_understd_msgs)   

Texte du message  |Autoriser l’application Portail d’entreprise à accéder aux photos, aux fichiers multimédias et aux fichiers de votre appareil ?  
---------|---------
Signification du message     |  Permet à l’appareil d’écrire des journaux de données sur la carte SD, et donc de déplacer les journaux à l’aide d’un câble USB.   </br></br>**REMARQUE : L’application Portail d’entreprise n’accède jamais aux photos, aux fichiers multimédias ou aux fichiers des utilisateurs.** Le texte du message est contrôlé par Google et ne peut pas être modifié.     
Où et quand le message s’affiche  | Le message s’affiche quand les utilisateurs appuient sur **Envoyer les données** pour envoyer les journaux de données à leur administrateur informatique.|         
Ce qui se passe si les utilisateurs autorisent l’accès  |  Les journaux sont copiés sur la carte SD. |         
Ce qui se passe si les utilisateurs refusent l’accès     | Ils peuvent toujours envoyer les journaux de données, mais les journaux ne sont pas copiés sur la carte SD de l’appareil.       </br></br> La deuxième fois que les utilisateurs se connectent à l’application Portail d’entreprise après le refus de l’accès, le message affiche une case **Ne plus me demander** que les utilisateurs peuvent cocher pour que le message ne s’affiche plus.</br></br>Si les utilisateurs autorisent, puis refusent par la suite l’accès, le message s’affiche la prochaine fois qu’ils essaient d’envoyer les journaux.</br></br>Si les utilisateurs décident par la suite d’autoriser l’accès, ils peuvent accéder à **Paramètres** > **Applications** > **Portail d’entreprise** > **Autorisations** > **Stockage**, puis activer l’autorisation.
Plus d'informations     |  Pour vos utilisateurs : [Envoyer des journaux de données de diagnostic à votre administrateur informatique par e-mail](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_send_diag_logs)  </br></br>Pour les professionnels de l’informatique : Les informations présentes dans ce tableau figurent également dans [Description des messages de l’application Portail d’entreprise pour vos utilisateurs](https://technet.microsoft.com/library/dn948527.aspx#BKMK_help_users_understd_msgs)   


**Application Portail d’entreprise iOS**
* Les utilisateurs peuvent désormais utiliser Microsoft Outlook ou d’autres applications de messagerie pour envoyer les journaux de diagnostic à l’administrateur informatique. Avant, seule l’application native pouvait être utilisée.
* La prise en charge a été améliorée pour le programme d’inscription d’appareil (DEP) d’Apple et les appareils inscrits de l’entreprise. Pour plus d’informations, consultez [Vous êtes invité à identifier votre appareil quand vous essayez de l’inscrire](https://technet.microsoft.com/library/mt598622.aspx#BKMK_ios_id_your_device).
* Dans la liste des appareils inscrits de l’utilisateur, une coche verte s’affiche désormais en regard de l’appareil que l’utilisateur est en train d’utiliser. Avant l’ajout de cette coche, les utilisateurs ne pouvaient pas savoir quel appareil inscrit ils utilisaient.

**Application Portail d’entreprise Windows**

Microsoft recueille automatiquement des données anonymes sur les performances et l'utilisation du portail d'entreprise pour améliorer les produits et services Microsoft. Les utilisateurs finaux peuvent désactiver la collecte de données à l'aide du paramètre Données d'utilisation sur leur appareil, mais les administrateurs n'ont aucun contrôle sur la collecte de données et ne peuvent pas changer la sélection de l'utilisateur final pour ce paramètre.



## Novembre 2015
### Gestion d'applications
Intune prend en charge les stratégies de gestion des applications mobiles (MAM) qui aident à empêcher la divulgation des données d’entreprise aux applications ou services consommateurs. Auparavant, ces stratégies s’appliquaient uniquement aux applications mobiles exécutées sur des appareils qui étaient également inscrits pour la gestion des appareils mobiles dans Intune.

Avec la mise à jour de ce mois-ci, Intune étend ses fonctionnalités MAM à de nouvelles classes d’appareils. En plus des appareils inscrits dans Intune, vous pouvez appliquer les stratégies MAM :
* Aux appareils gérés par toute autre solution de gestion des appareils mobiles.
* Aux appareils qui ne sont inscrits dans aucun système de gestion des appareils mobiles (généralement des appareils BYOD).

Vous trouverez plus d’informations sur ces nouvelles fonctionnalités MAM dans les billets de blog suivants :
* [Enhancing managed mobile productivity](http://blogs.technet.com/b/microsoftintune/archive/2015/11/17/enhancing-managed-mobile-productivity.aspx)
* [Announcing new Microsoft Enterprise Mobility capabilities](http://blogs.technet.com/b/microsoftintune/archive/2015/11/17/enhancing-managed-mobile-productivity.aspx)

Voici quelques points importants et informations supplémentaires sur les fonctionnalités MAM d’Intune :
* Les données d’entreprise sont isolées des données des clients dans les applications compatibles avec Intune, notamment les applications Office Mobile, les applications tierces qui ont adopté le SDK Intune ou les applications métier encapsulées par Intune.
* Les données d’entreprise peuvent être partagées (**Couper/Copier/Coller**) entre les applications d’entreprise, tout en empêchant leur partage dans des applications personnelles. Pour plus d’informations, consultez [Comment les stratégies de gestion des applications mobiles protègent les données d’application](https://technet.microsoft.com/library/mt627825.aspx) . Cet exemple de scénario, [Utiliser l’application Microsoft Word pour des tâches personnelles et professionnelles](https://technet.microsoft.com/library/mt627827.aspx), montre comment empêcher le partage des données d’entreprise dans des applications personnelles.
* Stratégies de prévention de perte des données clés, telles que les codes confidentiels propres aux applications, les contrôles Enregistrer sous et le partage des données managées entre les applications. Pour obtenir une liste de toutes les stratégies, consultez [Créer et déployer des stratégies de gestion des applications mobiles à l’aide de Microsoft Intune](https://technet.microsoft.com/library/mt627829.aspx).
* Les applications Word, Excel, PowerPoint, Outlook, OneNote et OneDrive Entreprise offrent toutes ces nouvelles fonctionnalités et peuvent être gérées avec ou sans l’inscription d’appareils. Les fonctionnalités de protection contre la perte de données sont intégrées de manière native aux applications Office standard dans l’Apple Store ou le Google Play Store, et ne nécessitent pas de création de package de restrictions d’application ni de chargement indépendant.
* Pour plus d’informations, consultez [Prise en main des stratégies de gestion des applications mobiles dans le portail Azure](https://technet.microsoft.com/library/mt627830.aspx). Pour découvrir comment configurer et déployer des stratégies de gestion des applications mobiles, consultez [Créer et déployer des stratégies de gestion des applications mobiles à l’aide de Microsoft Intune](https://technet.microsoft.com/library/mt627829.aspx).
* Quand les utilisateurs s’authentifient auprès de l’application avec leurs informations d’identification d’entreprise, les fonctionnalités de protection contre la perte de données sont configurées automatiquement. La rubrique [Expérience utilisateur pour les applications associées aux stratégies de gestion des applications mobiles Microsoft Intune](https://technet.microsoft.com/library/mt627827.aspx) contient des exemples de scénarios pour l’accès à OneDrive sur des appareils iOS et Android.
* Fonctionne sur les appareils iOS et Android.

La liste des [Applications Microsoft utilisables avec les stratégies de gestion des applications mobiles de Microsoft Intune](https://technet.microsoft.com/library/dn708489.aspx) a été mise à jour et contient les dernières applications.

### Gestion des appareils
 **Gestion des appareils Mac OS X** Vous pouvez maintenant inscrire et gérer des appareils Mac OS X avec Intune. Vous pouvez effectuer les opérations suivantes avec vos appareils Mac OS X :
* Inscrire des appareils pour qu’ils soient gérés par Intune. Consultez [Configurer la gestion iOS et MAC avec Microsoft Intune](https://technet.microsoft.com/library/dn408185.aspx).
* Contrôler les paramètres des appareils avec une stratégie de configuration générale. Consultez [Paramètres de la stratégie de configuration Mac OS X dans Microsoft Intune](https://technet.microsoft.com/library/mt627823.aspx).
* Déployer des paramètres Mac OS X que vous avez créés avec l’outil Apple Configurator. Consultez [Paramètres de la stratégie personnalisée Mac OS X dans Microsoft Intune](https://technet.microsoft.com/library/mt627820.aspx).
* Recueillir l’inventaire matériel et logiciel à partir d’appareils Mac OS X. Consultez [Comprendre vos appareils grâce à l’inventaire de Microsoft Intune](https://technet.microsoft.com/library/jj733634.aspx).
* Exécuter de nouveaux rapports qui affichent des détails sur les appareils Mac OS X que vous gérez. Consultez [Présentation des opérations Microsoft Intune à l’aide de rapports](https://technet.microsoft.com/library/dn646977.aspx).

**Nouveaux paramètres de navigateur Edge pour les appareils Windows 10** De nouveaux paramètres ont été ajoutés à la stratégie de configuration générale de Windows 10 pour vous permettre de gérer les paramètres et les fonctionnalités du navigateur Microsoft Edge. Consultez [Paramètres de la stratégie de configuration Windows 10 dans Microsoft Intune](https://technet.microsoft.com/library/mt404697.aspx).

**Profils de messagerie** Une nouvelle stratégie de profils de messagerie a été ajoutée pour les appareils Windows 10 Desktop et Windows 10 Mobile. Consultez [Gérer des paramètres et des fonctionnalités sur vos appareils avec des stratégies Microsoft Intune](https://technet.microsoft.com/library/dn646984.aspx).

**Nouveaux paramètres de stratégie de conformité** Les nouveaux paramètres de stratégie système et de sécurité suivants ont été ajoutés à la liste des stratégies de conformité :
* Pour être sûr que les dernières mises à jour sont installées sur les appareils Windows 8.1 ou version ultérieure qui accèdent aux ressources de votre entreprise, vous devez utiliser le paramètre **Exiger les mises à jour automatiques**. Vous pouvez également spécifier le type de mise à jour à installer automatiquement : soit toutes les mises à jour marquées comme importantes, soit toutes les mises à jour marquées comme importantes ou recommandées. Pour obtenir la liste complète des paramètres de stratégie de conformité, consultez [Gérer les stratégies de conformité d’appareils pour Microsoft Intune](https://technet.microsoft.com/library/dn705843.aspx).
* Le nouveau paramètre **Exiger un mot de passe quand l’appareil quitte un état inactif**, combiné avec le paramètre existant **Minutes d’inactivité avant demande du mot de passe**, vous permet de créer un paramètre de conformité qui oblige l’utilisateur final à entrer un mot de passe pour utiliser un appareil qui est inactif depuis un certain temps.

**Nouvelles options de stratégie d’accès conditionnel** Vous pouvez appliquer des stratégies d’accès conditionnel à **tous les utilisateurs** dans des stratégies d’accès conditionnel nouvelles ou existantes. Tous les utilisateurs disposant d’une licence pour Intune et Office 365 devront inscrire leurs appareils, et si la plateforme de l’appareil n’est pas prise en charge par Intune, l’accès est bloqué pour les applications clientes à l’aide de la [connexion basée sur l’authentification Active Directory (authentification moderne)](https://blogs.office.com/2014/11/12/office-2013-updated-authentication-enabling-multi-factor-authentication-saml-identity-providers/).

Vous pouvez également spécifier que la stratégie d’accès conditionnel s’applique à **toutes les plateformes**.  Toute application cliente utilisant la [connexion basée sur l’authentification Active Directory (authentification moderne)](https://blogs.office.com/2014/11/12/office-2013-updated-authentication-enabling-multi-factor-authentication-saml-identity-providers/) est soumise à la stratégie d’accès conditionnel, et si la plateforme n’est pas prise en charge par Intune, elle est bloquée.

### Modifications et mises à jour du portail d’entreprise Microsoft
Les modifications suivantes ont été apportées aux applications de portail d'entreprise dans cette version :

* **Android**: un écran d’accueil a été ajouté à l’application Portail d’entreprise Android pour aider les utilisateurs à comprendre la fonction de cette application. Cet écran vise à réduire les téléchargements de l’application par les utilisateurs dont les entreprises ne sont pas abonnées à Intune.

* **iOS** : Intune prend désormais en charge l’inscription des appareils Mac OS X à l’aide du [site web Portail d’entreprise](https://portal.manage.microsoft.com). Pour obtenir des instructions, consultez [Inscrire votre appareil Mac OS X dans Intune](https://technet.microsoft.com/library/mt598622.aspx).

* **Site web Portail d’entreprise**: les utilisateurs qui ont inscrit leur appareil dans Intune peuvent désormais réinitialiser leur code d’accès à l’aide de l’option **Réinitialiser le code d’accès** sur le site web du portail d’entreprise. Auparavant, seuls les administrateurs informatiques pouvaient réinitialiser les codes d’accès des utilisateurs. L’option Réinitialiser le code d’accès n’est pas prise en charge sur les appareils Windows 8.1 ni Windows RT. Elle s’affiche uniquement quand les appareils sont inscrits dans la gestion des appareils mobiles (MDM) ou MDM avec Exchange ActiveSync. Pour obtenir des instructions utilisateur, consultez [Réinitialiser votre code d’accès](https://technet.microsoft.com/library/mt590895.aspx).

### Modifications apportées à la gestion des licences par les administrateurs généraux
En octobre, nous avons indiqué que les administrateurs généraux (également appelés Administrateurs de clients) pouvaient continuer à effectuer des tâches d’administration quotidiennes sans licence distincte Intune ou Enterprise Mobility Suite (EMS). Toutefois, si les administrateurs généraux souhaitent utiliser le service, par exemple pour inscrire leur propre appareil ou un appareil d’entreprise, ou pour utiliser le portail d’entreprise Intune, ils doivent avoir une licence Intune ou EMS comme tout autre utilisateur. Voici quelques détails supplémentaires.
* Le portail d’entreprise Intune permet aux utilisateurs finaux :
    * D’inscrire leur appareil.
    * D’afficher l’état de leur appareil.
    * De télécharger des logiciels qu’un administrateur général a déployés dans l’organisation.
    * D’accéder à des liens publiés par l’administrateur général pour savoir comment contacter le service informatique.

    [En savoir plus sur le portail d’entreprise](https://technet.microsoft.com/library/dn646966.aspx#BKMK_CompanyPortal) et sur les différentes [façons de personnaliser le portail d’entreprise](https://technet.microsoft.com/library/dn646983.aspx#BKMK_ConfigureCompanyPortal).
* La personne qui s’inscrit pour acheter Intune ou EMS pour le compte d’une société devient automatiquement le premier administrateur général dans son locataire. Cet automne, Intune a commencé à affecter automatiquement une licence Intune ou EMS à ce premier administrateur général dans le cadre de la transition vers le [portail Office 365](http://portal.office.com/) et de la suppression du [portail des comptes Intune](http://account.manage.microsoft.com/). Les administrateurs généraux supplémentaires ajoutés peuvent continuer à effectuer des tâches d’administration quotidienne sans licence Intune ou EMS distincte. Si l’administrateur général agit comme un utilisateur final et veut inscrire son propre appareil (ou un appareil d’entreprise) ou télécharger des logiciels à partir du portail d’entreprise, il doit avoir une licence, comme tout autre utilisateur.
* Cette modification va prendre effet en janvier 2016.
* Cette modification ne doit pas affecter la capacité des partenaires Microsoft à administrer le service pour le compte de leurs clients. En revanche, les utilisateurs finaux devront avoir une licence Intune ou EMS pour pouvoir inscrire un appareil et accéder au portail d’entreprise ou télécharger un logiciel à partir du portail.

Si vous avez des questions sur cette modification, n’hésitez pas à contacter votre équipe de support technique Intune :
* [Canaux de support Microsoft Intune](https://technet.microsoft.com/library/jj839713.aspx)
* [Support de la communauté](https://social.technet.microsoft.com/Forums/en-US/home?forum=microsoftintuneprod)

Si vous avez des commentaires d’ordre général sur Microsoft Intune, notamment si vous voulez soumettre une demande de modification de conception (DCR, Design Change Request) ou un bogue, accédez à [Intune User Voice](https://microsoftintune.uservoice.com/).


### Nouveautés de la documentation d’Intune -- Novembre 2015
**Nouveau contenu**
* [Paramètres de la stratégie de configuration Mac OS X dans Microsoft Intune](https://technet.microsoft.com/library/mt627823.aspx) : explique comment contrôler les paramètres et les fonctionnalités des appareils Mac OS X.
* [Paramètres de la stratégie personnalisée Mac OS X dans Microsoft Intune](https://technet.microsoft.com/library/mt627820.aspx) : explique comment déployer les paramètres des appareils Mac OS X que vous avez créés à l’aide de l’outil Apple Configurator.
* [Configurer des stratégies d’application de prévention contre les pertes de données avec Microsoft Intune](https://technet.microsoft.com/library/mt627825.aspx) : contient des informations sur les scénarios pris en charge par les stratégies de gestion des applications mobiles et sur la façon dont les stratégies protègent les données.
* [Prise en main des stratégies de gestion des applications mobiles dans le portail Azure](https://technet.microsoft.com/library/mt627830.aspx) : explique ce que vous devez connaître pour commencer à utiliser le portail Azure en version préliminaire pour les stratégies de gestion des applications mobiles.
* [Créer et déployer des stratégies de gestion des applications mobiles à l’aide de Microsoft Intune](https://technet.microsoft.com/library/mt627829.aspx) : contient une procédure pas à pas illustrant comment créer des stratégies de gestion des applications mobiles dans le portail Azure en version préliminaire.
* [Analyser les stratégies de gestion des applications mobiles à l’aide de Microsoft Intune](https://technet.microsoft.com/library/mt627824.aspx): explique comment surveiller vos stratégies de gestion des applications mobiles à l’aide du portail Azure en version préliminaire.
* [Stratégies de gestion des applications mobiles Microsoft Intune et iOS Open In](https://technet.microsoft.com/library/mt627821.aspx): explique le fonctionnement des stratégies de gestion des applications mobiles avec la fonctionnalité iOS Open In.
* [Expérience utilisateur pour les applications associées aux stratégies de gestion des applications mobiles Microsoft Intune](https://technet.microsoft.com/library/mt627827.aspx) : décrit l’expérience utilisateur en cas d’utilisation d’applications associées à une stratégie de gestion des applications mobiles.
* [Réinitialiser les données d’applications d’entreprise managées avec Microsoft Intune](https://technet.microsoft.com/library/mt627826.aspx) : explique comment supprimer des données d’application d’entreprise.

**Contenu mis à jour**
* [Paramètres de la stratégie de configuration Windows 10 dans Microsoft Intune](https://technet.microsoft.com/library/mt404697.aspx) : ajout de nouveaux paramètres de navigateur Edge.
* [Configurer la gestion iOS et MAC avec Microsoft Intune](http://technet.microsoft.com/library/dn408185.aspx) : ajout d’informations expliquant comment inscrire des appareils Mac OS X.
* [Comprendre vos appareils grâce à l’inventaire de Microsoft Intune](https://technet.microsoft.com/library/jj733634.aspx) : ajout d’informations sur l’inventaire collecté à partir d’appareils Mac OS X. La rubrique a aussi été mise à jour avec les dernières informations pour toutes les plateformes.
* [Présentation des opérations Microsoft Intune à l’aide de rapports](https://technet.microsoft.com/library/dn646977.aspx) : ajout d’informations sur les deux nouveaux rapports qui permettent d’afficher des informations sur vos appareils Mac OS X gérés.
* [Gérer les stratégies de conformité d’appareils pour Microsoft Intune](https://technet.microsoft.com/library/dn705843.aspx): ajout d’informations sur les nouvelles stratégies de conformité relatives aux exigences en matière de mises à jour automatiques et de mots de passe quand un appareil sort d’un état d’inactivité.
* [Gérer l’accès à la messagerie avec Microsoft Intune](https://technet.microsoft.com/library/dn705841.aspx) : ajout d’informations sur la possibilité d’appliquer une stratégie d’accès conditionnel à toutes les plateformes et tous les utilisateurs.
* [Gérer l’accès à SharePoint Online avec Microsoft Intune](https://technet.microsoft.com/library/dn705844.aspx) : ajout d’informations sur la possibilité d’appliquer une stratégie d’accès conditionnel à toutes les plateformes et tous les utilisateurs.

## Octobre 2015

### Mises à jour de l’accès conditionnel pour Exchange sur site
**Vous pouvez désormais accorder l’accès à la messagerie Exchange Active Sync aux appareils conformes inscrits dans Intune quand la règle Exchange globale est définie sur « Bloquer » ou « Quarantaine ».** Jusqu’à présent, pour autoriser l’accès à la messagerie sur les appareils inscrits et conformes, vous deviez définir la règle Exchange globale par défaut sur **Autoriser**.

Avec cette mise à jour du service, ce paramètre n’est plus obligatoire pour l’accès conditionnel. Si votre environnement Exchange exige que votre règle globale par défaut soit définie sur **Bloquer/Quarantaine**, cochez simplement la case **Remplacement de la règle par défaut** dans la page de stratégie d’accès conditionnel d’Exchange sur site. La rubrique [Gérer l’accès à la messagerie avec Microsoft Intune](https://technet.microsoft.com/library/dn705841.aspx) contient davantage de détails sur les règles et les notifications qui en résultent pour les utilisateurs finaux.

**Nouvelle expérience de mise en quarantaine en un seul clic** : nous avons simplifié l’expérience de messagerie de mise en quarantaine pour permettre une inscription en un seul clic. Grâce à la mise à jour de ce service, il suffit aux utilisateurs finaux de cliquer sur un lien dans le message électronique de mise en quarantaine pour finaliser l’inscription dans l’application Portail d’entreprise.
### Mises à jour relatives à la gestion des applications et des appareils mobiles
**Android** Toutes les fonctionnalités de gestion d’Intune prennent désormais en charge Android 6.0 (Marshmallow), comme l’explique ce billet de blog : [Microsoft Intune Provides Day 0 Support for Android Marshmallow](http://blogs.technet.com/b/microsoftintune/archive/2015/10/09/microsoft-intune-to-provide-day-0-support-for-android-marshmallow.aspx)

**iOS** Vous ne pouvez plus créer de déploiements d’applications à destination d’appareils iOS exécutant une version antérieure à iOS 7.1. Les déploiements d’applications existants à destination d’appareils exécutant une version antérieure à iOS 7.1 continueront de fonctionner et d’être gérés par Intune.

**Windows 10** Intune prend désormais en charge le déploiement d’applications Windows 10 universelles à l’aide du type de programmation d’installation de logiciel **Package d’application Windows**. Pour plus d’informations et pour connaître les conditions requises, consultez [Get Started with app deployment in Microsoft Intune](http://technet.microsoft.com/en-US/library/dn646955.aspx) (Prise en main du déploiement d’applications dans Microsoft Intune).


### Modifications et mises à jour des applications Portail d'entreprise de Microsoft
Les modifications suivantes ont été apportées aux applications Portail d’entreprise dans cette version : **iOS** De nouveaux boutons ont été ajoutés à l’application Portail d’entreprise pour permettre aux utilisateurs d’envoyer plus facilement les journaux de diagnostic à leurs administrateurs informatiques :

|Nom du bouton|Emplacement|
|------------|---------------|
|Rapport|Messages d’alerte d’erreur|
|Envoyer un rapport de diagnostic|Écran « À propos de » de l’application Portail d’entreprise|


>[!div class="step-by-step"]

>[&larr; **Nouveautés d'Intune**](whats-new-in-microsoft-intune.md)    


<!--HONumber=Jun16_HO1-->


