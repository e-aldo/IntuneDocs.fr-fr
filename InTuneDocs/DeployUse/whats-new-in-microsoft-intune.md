---
title: "Nouveautés | Microsoft Intune"
description: "Découvrir les nouveautés de la version de Microsoft Intune de ce mois-ci et des versions précédentes"
keywords: 
author: Lindavr
manager: angrobe
ms.date: 07/18/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
ms.reviewer: mamoriss
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 68af4d7f0b082f14e6f9c06f8739805f9590384e
ms.openlocfilehash: 64bd2e3c8e8da3949634a544eb2c582e889c8209


---

# Nouveautés de Microsoft Intune
Découvrez les nouveautés de la version de Microsoft Intune de ce mois-ci. Vous pouvez également découvrir les modifications à venir que vous devez planifier, ainsi que des informations sur les versions précédentes.

Toutes ces fonctionnalités seront finalement prises en charge pour les déploiements de clients hybrides (Configuration Manager avec Intune). Pour plus d’informations sur les nouvelles fonctionnalités hybrides, consultez notre page [Nouveautés hybrides](https://technet.microsoft.com/en-US/library/mt718155(TechNet.10).aspx).

## Août 2016
## Mises à jour du Portail d’entreprise

### Android
- **Application Portail d’entreprise Android**<br/>
L’application Portail d’entreprise Intune pour Android assure la prise en charge dès le premier jour du système d’exploitation Android 7.0 pour les appareils mobiles, bientôt disponible.  

- **Suppression par Google de la fonctionnalité de réinitialisation à distance du code secret sur les appareils Android 7.0**<br/>
Sur les appareils Android 7.0, les administrateurs informatiques Intune et les utilisateurs finaux ne pourront pas réinitialiser à distance le code secret de leur appareil, car Google a supprimé cette fonction pour ces appareils. Cependant, pour les versions antérieures à 7.0, les administrateurs informatiques pourront continuer à réinitialiser à distance le code secret d’un utilisateur, et les utilisateurs finaux, à réinitialiser leur code secret à partir du site web du Portail d’entreprise.

## Juillet 2016
## Gestion d'applications
### Améliorer l’expérience de mise à jour de profil d’approvisionnement d’application
Les applications mobiles métier Apple iOS intègrent un profil d’approvisionnement et du code signé avec un certificat. Lorsque l’application s’exécute sur un appareil iOS, iOS confirme l’intégrité de l’application iOS et applique les stratégies définies par le profil de configuration.

Le certificat de signature d’entreprise que vous utilisez pour signer des applications dure généralement 3 ans. Toutefois, le profil de configuration expire au bout d’1 an. Grâce à cette mise à jour, Intune vous offre les outils pour déployer de façon proactive une nouvelle stratégie de profil de configuration pour les appareils qui disposent d’applications arrivant prochainement à expiration alors que le certificat est toujours valide. Pour plus d’informations, consultez [Utilisation de stratégies de profil de configuration d’applications mobiles iOS pour maintenir vos applications métier à jour](/intune/deploy-use/ios-mobile-app-provisioning-profiles).
<!--- TFS 1280247--->
### Disponibilité du Xamarin SDK pour applications Intune
Le composant Xamarin SDK pour applications Intune vous permet d’activer les fonctionnalités de gestion des applications mobiles Intune dans vos applications Android et iOS mobiles développées avec Xamarin. Le composant est disponible dans le [Xamarin Store](https://components.xamarin.com/view/Microsoft.Intune.MAM) ou sur la [page Github de Microsoft Intune](https://github.com/msintuneappsdk).
<!--- TFS 1061478 --->

## Gestion des appareils
### Augmentation du nombre d’inscriptions d’appareils
Intune augmente le nombre maximal d’inscriptions d’appareils configurables en repoussant leur limite de 5 appareils par utilisateur à 15.
<!---TFS 1289896 --->

### Intégration de TeamViewer sur les PC Windows exécutant le logiciel client Intune
L’intégration de [TeamViewer](https://www.teamviewer.com) sur les PC Windows exécutant le client Intune vous permet d’établir des sessions d’assistance à distance avec des PC Windows, afin d’aider les départements de support technique des utilisateurs finaux. Cela inclut Windows 7, 8, 8.1 et Windows 10. Pour en savoir plus, voir [Tâches courantes de gestion des PC Windows avec le client Microsoft Intune](intune/deploy-use/common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client).
<!---TFS 1284856--->

## Mises à jour du Portail d’entreprise
### Site web Portail d’entreprise
- **Amélioration de l’interface d’inscription d’appareils Windows**<br/>
Lorsque vous utilisez l’accès conditionnel, les étapes d’inscription pour Windows 8.1, Windows 10 Desktop et Windows 10 Mobile ont été précisées dans le site web du portail d’entreprise. Les utilisateurs peuvent à présent voir deux étapes distinctes, « Inscription de l’appareil » et « Jonction au lieu de travail », ce qui leur permet de consulter plus facilement l’état de leur appareil et de terminer le processus en cas d’échec de l’outil Workplace Join (WPJ). Ces différentes étapes sont également censées simplifier le processus de résolution des problèmes pour les administrateurs. Auparavant, lorsque les utilisateurs finaux inscrivaient un appareil et que toutes les étapes de l’inscription réussissaient à l’exception de la jonction au lieu de travail, l’appareil inscrit n’apparaissait pas dans la liste des appareils identifiables par les utilisateurs, ce qui pouvait s’avérer déroutant.

### Android
- **Application Portail d’entreprise Android**<br/>
Si un message d’erreur s’affiche pour les utilisateurs finaux Android en leur indiquant qu’il manque un certificat requis pour leur appareil, ils peuvent appuyer sur un bouton « Comment résoudre ce problème » pour consulter les [étapes](/intune/enduser/your-device-is-missing-a-required-certificate-android#your-device-is-missing-a-certificate-required-by-your-it-administrator) à suivre afin d’installer le certificat manquant. Si les utilisateurs suivent ces étapes, mais qu’un autre message d’erreur indique « Certificat manquant », ils sont invités à contacter leur administrateur et à fournir ce [lien](/intune/troubleshoot/troubleshoot-device-enrollment-in-intune#android-certificate-issues), qui mène vers les étapes à suivre pour résoudre ce problème de certificat.

- **Limiter les installations d’applications à chargement indépendant sur les appareils inscrits**<br/>
Les appareils Android ne peuvent plus installer d’applications par le biais du site web du portail d’entreprise, sauf s’ils ont été inscrits dans Intune à l’aide de l’application portail d’entreprise Intune pour Android.
<!---TFS 1299082--->

### iOS
- **Modifications apportées aux comptes des gestionnaires d’inscription d’appareil dans l’application Portail d’entreprise iOS**<br/>
Pour améliorer les performances et la mise à l’échelle, Intune n’affiche plus tous les appareils Gestionnaires d’inscription d’appareil (DEM) dans le volet **Mes appareils** de l’application Portail d’entreprise pour iOS. Seul l’appareil local qui exécute l'application est affiché et uniquement s'il est inscrit via l'application Portail d'entreprise.

    L'utilisateur DEM peut effectuer des actions sur l’appareil local, mais la gestion à distance d’autres appareils inscrits ne peut être effectuée à partir de la console d'administration Intune. En outre, Intune désapprouve l’utilisation de comptes DEM avec le Programme d’inscription d’appareils Apple ou l’outil Apple Configurator. Ces deux méthodes d'inscription prennent déjà en charge l'inscription sans utilisateur pour les appareils iOS partagés.

    Utilisez uniquement les comptes DEM lors l'inscription sans utilisateur d’appareils partagés n'est pas disponible. Pour plus d’informations, consultez [Inscrire des appareils d’entreprise avec le Gestionnaire d’inscription d’appareil dans Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune).
<!---TFS 1233681--->

## Modification des noms de fonctionnalités Windows
- [Microsoft Passport pour Windows](/intune/deploy-use/control-microsoft-passport-settings-on-devices-with-microsoft-intune) est maintenant appelé **Windows Hello Entreprise**.
- [Protection des données d’entreprise](https://technet.microsoft.com/itpro/windows/keep-secure/create-edp-policy-using-intune) est maintenant appelé **Protection des informations Windows**.

## Nouveautés à venir
### Début de la transition des groupes Intune vers les groupes Azure Active Directory en août 2016
Intune crée une nouvelle expérience de gestion des groupes qui utilise les groupes de sécurité Azure Active Directory (AAD). Ces groupes de sécurité basés sur Azure AD peuvent contenir des utilisateurs et des appareils. Ils seront utilisés pour la gestion, le déploiement de stratégie et de profil de tous les groupes quand nous introduirons le nouveau portail d’administration Intune basé sur Azure.

Cette nouvelle expérience apporte les avantages suivants :
- Vous n’aurez plus besoin de dupliquer des groupes entre des services.
- Vous pourrez accéder à de nouvelles fonctionnalités de groupe Azure Active Directory Premium (AADP).
- Vous pourrez bénéficier d’une l’extensibilité lors de l’utilisation de PowerShell et Graph.
- La gestion des groupes est unifiée lors de la gestion de la mobilité d’entreprise.

Pour activer la transition vers les groupes de sécurité, nous allons modifier la console d’administration. Ces modifications et l’utilisation des groupes de sécurité Azure AD seront consignées dans la documentation Intune.

Les clients qui ne connaissent pas Intune constateront certaines modifications du groupe de sécurité avant les clients actuels.

Outre les modifications dans la gestion de groupe, les fonctionnalités suivantes deviendront obsolètes :
- Exclusion de membres ou de groupes lors de la création d’un groupe
- Groupes **Utilisateurs non groupés** et **Appareils non groupés**
- **Gérer des groupes** dans le rôle d’administrateur de service
- Alertes personnalisées basées sur le groupe pour les règles de notification
- Glissement des groupes dans les rapports

Nous publierons en août des informations supplémentaires sur la réduction de l’impact de ces obsolescences.

### Ajout de « Notifications » sur le portail d’entreprise pour Android
En septembre, nous publierons une mise à jour du Portail d’entreprise pour Android, qui présentera la nouvelle icône **Notifications** de la page d’accueil. En appuyant sur cette icône, vous pourrez accéder à la page **Notifications** qui indiquera à votre utilisateur final tous les éléments qui nécessitent son attention particulière dans l’application de portail d’entreprise, tels que la non-conformité d’un appareil, ainsi que les mises à jour ou les activations d’inscriptions. Si vous utilisez également l’application de portail d’entreprise iOS, vous pouvez déjà utiliser ces notifications. Une fois la page **Notifications** en place, si votre appareil est déjà inscrit, vous ne verrez plus la page **Configuration de l’accès à l’entreprise** à chaque fois que vous accédez au portail d’entreprise pour Android ou que vous y revenez. Nous savons que beaucoup d’entre vous ont créé des conseils pour l’utilisateur final et que vous appréciez de recevoir des notifications avancées lorsque vos conseils/captures d’écrans doivent être mis à jour. Mettez à jour votre documentation pour refléter les modifications de l’expérience à venir. Vous trouverez des captures d’écran mises à jour ici : https://aka.ms/androidcpupdate.  



### Feuille de route du cloud
Restez informé des développements à venir pour Intune avec la [Feuille de route de la plateforme cloud](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune).

### Désapprobation du service
- **Modifications apportées à la prise en charge de l’application Portail d’entreprise iOS**<br/>
En septembre, tous les utilisateurs de l’application Portail d’entreprise Microsoft Intune pour iOS devront utiliser la dernière version. Les nouveaux utilisateurs pourront uniquement télécharger la dernière version et les utilisateurs actuels devront effectuer une mise à jour vers cette version. La dernière version nécessite iOS 8.0 ou version ultérieure. Les appareils qui exécutent d’anciennes versions d’iOS ne pourront pas utiliser le portail d’entreprise ni être inscrits tant qu’ils n’auront pas été mis à jour vers iOS 8.0 ou version ultérieure, et que l’application Portail d’entreprise n’aura pas été mise à jour vers la dernière version. Les appareils inscrits qui exécutent les versions antérieures à iOS 8.0 continueront d’être gérés et répertoriés dans la Console d’administration Intune.  

- **Mise à jour de la version minimale de Managed Browser pour iOS 8.0**<br/>
En août, Intune publiera une mise à jour de l’application Microsoft Intune Managed Browser pour iOS qui prendra uniquement en charge les appareils exécutant iOS version 8.0 ou ultérieure. Même si les appareils iOS 7.1 pourront toujours utiliser l’application Managed Browser, nous vous recommandons d’inciter vos utilisateurs à procéder à la mise à jour pour iOS 8.0 ou ultérieure. Ils pourront ainsi accéder aux nouvelles fonctionnalités de Managed Browser et en tirer pleinement parti.  
<!---TFS 1313253--->

- **Les applications du portail d’entreprise pour Windows 8 et Windows Phone 8 seront obsolètes à partir de septembre 2016** <br/>
À compter de septembre 2016, les utilisateurs de l’application Portail d’entreprise Microsoft Intune pour plateformes Windows Phone 8 et Windows 8 ne pourront plus bénéficier du support Microsoft Intune. Mettez à jour vos appareils vers Windows 8.1 et Windows Phone 8.1, et utilisez les applications Portail d’entreprise Windows 8.1 et Windows Phone 8.1 correspondantes pour continuer la distribution des applications sur ces appareils.
<!---TFS 1255391--->

- **Applications de visionneuse Intune** <br/>
Avec la publication de la nouvelle application de partage RMS, nous allons supprimer les applications de visionneuse Intune suivantes à compter du mois d’août 2016 :
    - Intune AV Viewer
    - Intune PDF Viewer
    - Intune Image Viewer pour Android depuis Google Play

  Au lieu d’utiliser les applications de visionneuse Intune, nous vous recommandons d’utiliser la nouvelle [application Rights Management (partage RMS) pour Android](https://docs.microsoft.com/en-us/intune/deploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune#viewing-media-files-with-the-rights-management-sharing-app), qui vous permet de déployer une application unique à la place de trois applications distinctes pour afficher en toute sécurité les fichiers d’entreprise sur les appareils Android. Quand l’application de visionneuse Intune ne sera plus prise en charge, elle sera supprimée du Google Store et ne sera plus disponible pour une utilisation ultérieure.

<!--- - **Custom Group Targeting of Notification Rules Removal.**<br/>
Intune notification rules define who an email alert will be sent to from Intune. Currently, you can configure notification rules to send emails to all users of devices in an Intune device group that you created. From around June 1st 2016 moving forward, targeting user-created groups will no longer be supported.

    Today, to target a notification rule to a group you created from the Microsoft Intune administration console, you would take the following steps:

    In the **Admin** workspace, click **Notification Rules** > **Create New Rule**

    In step two of the Create Notification Rule Wizard, select the device groups which the rule will target. This step, “select device groups”, is being removed from the Intune Console.

    The preliminary timeline for this change is as follows:
    - In August, 2016, new tenants will not see step two of the Create Notification Rule Wizard. Exiting tenants are unaffected.
    - Around September, 2016, some existing tenants will not see the “select device groups” in the wizard.
    - Around November, 2016, we expect that all tenants will not see the “select device groups” in the wizard.

--->



## Versions précédentes d’Intune
Les dernières améliorations apportées à Intune au cours des six derniers mois sont répertoriées dans l’article [Versions précédentes d’Intune](previous-intune-releases.md).

### Voir aussi
* [Blog Microsoft Intune](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Feuille de route de la plateforme cloud](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)



<!--HONumber=Aug16_HO2-->


