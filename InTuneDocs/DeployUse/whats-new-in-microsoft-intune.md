---
title: "Nouveautés | Microsoft Intune"
description: "Découvrir les nouveautés de la version de Microsoft Intune de ce mois-ci et des versions précédentes"
keywords: 
author: Lindavr
manager: angrobe
ms.date: 08/10/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
ms.reviewer: mamoriss
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: d51ab5d486e7e23d2527f9cb95f105e7916cdb27
ms.openlocfilehash: 138d362618c9859a55988b7a2ada85e44b0e95c5


---

# Nouveautés de Microsoft Intune
Découvrez les nouveautés de la version de Microsoft Intune de ce mois-ci. Vous pouvez également découvrir les modifications à venir que vous devez planifier, ainsi que des informations sur les versions précédentes.

Toutes ces fonctionnalités seront finalement prises en charge pour les déploiements de clients hybrides (Configuration Manager avec Intune). Pour plus d’informations sur les nouvelles fonctionnalités hybrides, consultez notre page [Nouveautés hybrides](https://technet.microsoft.com/en-US/library/mt718155(TechNet.10).aspx).
<!---@Barry, the above blurb stays in each version, but make sure Tyler signs off each time. Also, remember to set the ms.date in the metadata to the sprint release. --->

## Août 2016
## Gestion d'applications
<!---@Barry, I created the buckets of App management, Device management, etc but am not tied to them. Just wanted to break up and organize the feature list. If you're going to take over the Company Portal section, please talk to Stacie about how she's been organizing it. --->

### Applications affichées et masquées dans iOS 9.3
Pour les appareils exécutant iOS 9.3 ou version ultérieure, vous pouvez utiliser la liste des applications affichées et masquées dans la stratégie de configuration générale d’iOS pour :
- Spécifier une liste d’applications à masquer aux utilisateurs. Les utilisateurs ne peuvent pas afficher ou lancer ces applications.
- Spécifier une liste d’applications que les utilisateurs peuvent afficher et lancer. Aucune autre application ne peut être affichée ou lancée.

Les applications que vous pouvez spécifier incluent celles que vous avez déployées, ainsi que les applications iOS intégrées telles que Messages et Notes. Pour plus d’informations, consultez [Paramètres de la stratégie iOS dans Microsoft Intune]( https://docs.microsoft.com/intune/deploy-use/ios-policy-settings-in-microsoft-intune).
<!---TFS 1279009 checked--->
### Stratégie des applications autorisées et bloquées pour les appareils dotés de Samsung KNOX
Vous pouvez désormais configurer une stratégie personnalisée pour les appareils dotés de Samsung KNOX, qui vous permet de créer l’un des éléments suivants :
- Une liste d’applications qui sont bloquées sur l’appareil. Même si elle est installée, une application incluse dans la liste d’applications bloquées ne peut pas être activée sur l’appareil.
- Une liste d’applications que les utilisateurs de l’appareil sont autorisés à installer à partir du magasin Google Play. Aucune autre application ne peut être installée à partir de ce magasin.

Ces paramètres peuvent uniquement être utilisés par les appareils qui exécutent Samsung KNOX.
Pour plus d’informations, consultez [Utiliser des stratégies personnalisées pour autoriser et bloquer des applications pour les appareils Samsung KNOX]( custom-policy-to-allow-and-block-samsung-knox-apps.md).
<!---TFS 1311629 checked --->
### Nouvelles applications compatibles avec les stratégies de gestion des applications mobiles (MAM)
L’application Yammer pour [iOS](https://itunes.apple.com/app/yammer/id289559439?mt=8) et [Android](https://play.google.com/store/apps/details?id=com.yammer.v1) est désormais compatible avec les [stratégies de gestion des applications mobiles (MAM) Intune](/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune), que l’appareil soit inscrit ou non.

Pour obtenir la liste complète des applications MAM compatibles, consultez le site des [partenaires des applications Microsoft Intune](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-partners).
<!--- TFS 1252335 & 1252336 checked--->


<!--- I started putting TFS numbers in the What's Coming topic and found it helpful when updating the What's New. Up to you if you want to continue. --->

### Applications de visionneuse Intune
Avec la publication de la nouvelle application de partage RMS, nous allons supprimer les applications de visionneuse Intune suivantes à compter du mois d’août 2016 :
- Intune AV Viewer
- Intune PDF Viewer
- Intune Image Viewer pour Android depuis Google Play

Au lieu d’utiliser les applications de visionneuse Intune, nous vous recommandons d’utiliser la nouvelle [application Rights Management (partage RMS) pour Android](https://docs.microsoft.com/en-us/intune/deploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune#viewing-media-files-with-the-rights-management-sharing-app), qui vous permet de déployer une application unique à la place de trois applications distinctes pour afficher en toute sécurité les fichiers d’entreprise sur les appareils Android. Quand l’application de visionneuse Intune ne sera plus prise en charge, elle sera supprimée du Google Store et ne sera plus disponible pour une utilisation ultérieure.

## Gestion des appareils
### Prise en charge d’Android 7.0
Intune assure la prise en charge dès le premier jour du système d’exploitation Android 7.0 pour les appareils mobiles, bientôt disponible.
<!---TFS 1262053--->
### Suppression par Google de la fonctionnalité de réinitialisation à distance du code secret sur les appareils Android 7.0
Google supprime la fonctionnalité permettant aux utilisateurs finaux et aux administrateurs informatiques de réinitialiser à distance le code secret de leurs appareils Android 7.0. Auparavant, les administrateurs informatiques pouvaient réinitialiser à distance le code secret d’un utilisateur, et les utilisateurs finaux pouvaient réinitialiser leur code secret depuis le site web du Portail d’entreprise.



## Mises à jour du Portail d’entreprise
### Site web Portail d’entreprise
- **Lien des commentaires sur le Portail d’entreprise à l’attention de Microsoft** <br/>
Le site web du Portail d’entreprise permet aux utilisateurs finaux de sélectionner un nouveau lien « Commentaires », en bas de la page, pour envoyer des commentaires à Microsoft concernant leur expérience d’utilisation du site. Les commentaires regroupés sont anonymes et permettent à Microsoft d’améliorer le site web du Portail d’entreprise, afin d’optimiser cette expérience.
<!--- TFS 1313657 checked--->

### iOS
- **Mise à jour de la version minimale de Managed Browser pour iOS 8.0**<br/>
L’application Microsoft Intune Managed Browser pour iOS a été mise à jour pour prendre en charge les appareils exécutant iOS 8.0 ou version ultérieure. Même si les appareils iOS 7.1 peuvent toujours utiliser l’application Managed Browser existante, nous vous recommandons d’inciter vos utilisateurs à procéder à la mise à jour pour iOS 8.0 ou version ultérieure. Ils pourront ainsi accéder aux nouvelles fonctionnalités de Managed Browser et en tirer pleinement parti.  
<!---TFS 1313253 checked--->

## Nouveautés à venir
### Début de la transition des groupes Intune vers les groupes Azure Active Directory dès septembre 2016
Intune crée une nouvelle expérience de gestion de groupe qui utilise les groupes de sécurité Azure Active Directory (AAD) en tant que groupes d’utilisateurs et d’appareils dans Intune. Ces groupes seront utilisés pour la gestion, le déploiement de stratégies et de profils de tous les groupes **lorsque nous introduirons le nouveau portail d’administration Intune basé sur Azure**.

Grâce à cette nouvelle expérience, vous n’aurez plus besoin de dupliquer des groupes entre des services, **ce qui vous permet d’accéder à certaines fonctionnalités de groupes Azure Active Directory Premium (AADP)**, tout en bénéficiant d’une extensibilité lors de l’utilisation de PowerShell et Graph. La gestion des groupes sera également unifiée lors de la gestion de la mobilité d’entreprise.

Pour activer la transition vers les groupes de sécurité, nous allons devoir modifier la **console d’administration actuelle**. **Ces modifications et l’utilisation des groupes de sécurité Azure AD seront consignées dans la documentation d’Intune**.

Les clients qui ne connaissent pas Intune constateront **certaines modifications du groupe de sécurité avant les clients actuels**.

Outre les modifications dans la gestion de groupe, **les fonctionnalités suivantes deviendront obsolètes** :
- Exclusion de membres ou de groupes lors de la création d’un groupe
- Groupes **Utilisateurs non groupés** et **Appareils non groupés**
- **Gérer des groupes** dans le rôle d’administrateur de service
- Alertes personnalisées basées sur le groupe pour les règles de notification
- Glissement des groupes dans les rapports
<!--- TFS 1295329--->

### Ajout de « Notifications » sur le portail d’entreprise pour Android
En septembre, nous publierons une mise à jour du Portail d’entreprise pour Android, qui présentera la nouvelle icône **Notifications** de la page d’accueil. En appuyant sur cette icône, vous pourrez accéder à la page **Notifications** qui indiquera à votre utilisateur final tous les éléments qui nécessitent son attention particulière dans l’application de portail d’entreprise, tels que la non-conformité d’un appareil, ainsi que les mises à jour ou les activations d’inscriptions. Si vous utilisez également l’application de portail d’entreprise iOS, vous pouvez déjà utiliser ces notifications. Une fois la page **Notifications** en place, si votre appareil est déjà inscrit, vous ne verrez plus la page **Configuration de l’accès à l’entreprise** à chaque fois que vous accédez au portail d’entreprise pour Android ou que vous y revenez. Nous savons que beaucoup d’entre vous ont créé des conseils pour l’utilisateur final et que vous appréciez de recevoir des notifications avancées lorsque vos conseils/captures d’écrans doivent être mis à jour. Mettez à jour votre documentation pour refléter les modifications de l’expérience à venir. Vous trouverez des captures d’écran mises à jour ici : https://aka.ms/androidcpupdate.  


### Feuille de route du cloud
Restez informé des développements à venir pour Intune avec la [Feuille de route de la plateforme cloud](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune).

### Désapprobation du service
<!---@Barry, we started listing service deprecations earlier this summer. --->
- **Modifications apportées à la prise en charge de l’application Portail d’entreprise iOS**<br/>
En septembre, tous les utilisateurs de l’application Portail d’entreprise Microsoft Intune pour iOS devront utiliser la dernière version. Les nouveaux utilisateurs pourront uniquement télécharger la dernière version et les utilisateurs actuels devront effectuer une mise à jour vers cette version. La dernière version nécessite iOS 8.0 ou version ultérieure. Les appareils qui exécutent d’anciennes versions d’iOS ne pourront pas utiliser le portail d’entreprise ni être inscrits tant qu’ils n’auront pas été mis à jour vers iOS 8.0 ou version ultérieure, et que l’application Portail d’entreprise n’aura pas été mise à jour vers la dernière version. Les appareils inscrits qui exécutent les versions antérieures à iOS 8.0 continueront d’être gérés et répertoriés dans la Console d’administration Intune.  

- **Mise à jour de la version minimale de Managed Browser pour iOS 8.0**<br/>
En août, Intune publiera une mise à jour de l’application Microsoft Intune Managed Browser pour iOS qui prendra uniquement en charge les appareils exécutant iOS version 8.0 ou ultérieure. Même si les appareils iOS 7.1 pourront toujours utiliser l’application Managed Browser, nous vous recommandons d’inciter vos utilisateurs à procéder à la mise à jour pour iOS 8.0 ou ultérieure. Ils pourront ainsi accéder aux nouvelles fonctionnalités de Managed Browser et en tirer pleinement parti.  
<!---TFS 1313253--->

- **Les applications du portail d’entreprise pour Windows 8 et Windows Phone 8 seront obsolètes à partir de septembre 2016** <br/>
À compter de septembre 2016, les utilisateurs de l’application Portail d’entreprise Microsoft Intune pour plateformes Windows Phone 8 et Windows 8 ne pourront plus bénéficier du support Microsoft Intune. Mettez à jour vos appareils vers Windows 8.1 et Windows Phone 8.1, et utilisez les applications Portail d’entreprise Windows 8.1 et Windows Phone 8.1 correspondantes pour continuer la distribution des applications sur ces appareils.
<!---TFS 1255391--->

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



<!--HONumber=Aug16_HO3-->


