---
title: "Déployer l’application Lookout for Work | Microsoft Docs"
description: "Configurer et déployer l’application Lookout for Work pour Android."
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/21/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 524c4209-ad57-4d35-955e-a00d796bf858
ms.reviewer: sandera
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: ab6d9b6b296fb4e1fb0aaa9496fede28976728dc
ms.openlocfilehash: eaf30c8a59013af6359743227edc8aa6709577c5
ms.lasthandoff: 04/14/2017


---

# <a name="configure-and-deploy-lookout-for-work-app"></a>Configurer et déployer l’application Lookout for Work

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Cet article explique comment configurer et déployer l’application Lookout for Work pour les appareils Android et iOS.

## <a name="android-google-play-store-app"></a>Android (application Google Play Store)

1.    Dans la [console Administrateur Microsoft Intune](https://manage.microsoft.com), accédez à **Applications** et choisissez **Ajouter des applications**.
2.    Dans la page **Installation du logiciel** du serveur de publication, choisissez **Lien externe**, puis indiquez l’URL suivante : https://play.google.com/store/apps/details?id=com.lookout.enterprise
  >[!NOTE]
  >Ne cliquez pas sur l’option pour obtenir Managed Browser.

3.    Dans la page **Description du logiciel**, renseignez les informations suivantes :
  * **Serveur de publication :** Lookout Mobile Security
  * **Nom :** Lookout for Work
  * **Description :** Lookout offre la meilleure protection contre les menaces mobiles pour sécuriser votre appareil. Quand l’application Lookout est installée sur l’appareil, elle protège votre appareil contre les menaces et elle vous avertit (ainsi que l’administrateur de votre entreprise) des menaces détectées.
  * **Catégorie :** Gestion de l’ordinateur

4. En cas de réussite de l’opération, le message **Le téléchargement des données s’est terminé correctement dans Microsoft Intune s’affiche**.

  Dans la console Intune, quand vous cliquez sur **Applications**, vous voyez maintenant l’application **Lookout for Work** dans la liste. ![Capture d’écran de la page Applications dans la console Administrateur Intune montrant l’application Lookout for Work dans la liste](../media/mtp/lookout-app-listed-intune-console.png)

5. Déployez l’application pour les utilisateurs en sélectionnant l’application Lookout for Work et en choisissant **Gérer le déploiement**.

  Vous devez sélectionner les mêmes utilisateurs que ceux qui ont été ajoutés à l’option Gestion des inscriptions dans la console Lookout MTP.  Pour plus d’informations sur l’ajout de groupes d’utilisateurs dans Lookout MTP, consultez l’étape 3 dans la section [Configurer votre abonnement à Lookout MTP](configure-and-deploy-lookout-for-work-apps.md).

  >[!IMPORTANT]
  > L’Assistant Déploiement d’application Intune n’a pas connaissance des groupes d’utilisateurs Azure AD et utilise les groupes d’utilisateurs Intune à la place. Vous devez donc créer un groupe d’utilisateurs Intune basé sur le groupe d’utilisateurs Azure AD qui est inscrit dans la console Lookout MTP, comme cela est décrit dans [cette](plan-your-user-and-device-groups.md) rubrique.

6. Choisissez l’option **Installation requise** pour exiger que l’application Lookout soit installée sur l’appareil de l’utilisateur.

## <a name="ios-enterprise-signed-version-of-lookout-app"></a>iOS (version Enterprise signée de l’application Lookout)

1. Vérifiez que la **gestion iOS** est configurée sur votre appareil. Pour obtenir des instructions sur la configuration de votre appareil relative à la gestion iOS, consultez [Configurer la gestion des appareils iOS et Mac](set-up-ios-and-mac-management-with-microsoft-intune.md).

2. **Resignez** l’application iOS Lookout for Work. Lookout distribue son application iOS Lookout for Work en dehors de l’App Store iOS. **Avant de distribuer l’application**, vous devez resigner l’application avec votre certificat de développeur d’entreprise iOS. Pour obtenir des instructions détaillées pour resigner des applications iOS Lookout for Work, consultez [Lookout for Work iOS app re-signing process](https://personal.support.lookout.com/hc/articles/114094038714) (Processus pour resigner des applications iOS Lookout for Work) sur le site Lookout.

3. Activez l’authentification Azure Active Directory pour les utilisateurs iOS de la manière suivante :
  1.  Connectez-vous au [portail de gestion Azure Active Directory](https://manage.windowsazure.com) et accédez à la page d’application.
  2.  Ajoutez l’**application iOS Lookout for Work** comme **application cliente native**.
  ![Capture d’écran de la boîte de dialogue Ajouter des applications présentant l’option Application cliente native](../media/mtp/aad-add-app.png)
  3. Remplacez **com.lookout.enterprise.nom_de_votre_entreprise** par l’ID d’ensemble client que vous avez sélectionné quand vous avez signé le package IPA.
  4.  Ajouter l’URI de redirection : **&lt;companyportal://code/ >** suivi d’une version codée URL de votre URI de redirection d’origine.
  5.  Ajoutez **Autorisations déléguées** à votre application.

  Pour plus d’informations, consultez [Configurer une application cliente native](https://azure.microsoft.com/documentation/articles/app-service-mobile-how-to-configure-active-directory-authentication/#optional-configure-a-native-client-application).

4. Chargez le fichier .ipa resigné comme décrit dans la rubrique [Ajouter des applications pour les appareils mobiles dans Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/add-apps-for-mobile-devices-in-microsoft-intune). Définissez la version de système d’exploitation minimale sur iOS version 8.0 ou ultérieure.

  ![Capture d’écran de la page Applications dans la console Administrateur Intune répertoriant l’application Lookout for work dans la liste des applications](../media/mtp/ios-app-uploaded-intune.png)

5. Créez la stratégie de configuration d’application gérée comme décrit dans la rubrique [Configurer des applications iOS avec des stratégies de configuration des applications mobiles dans Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune).

  ![Capture d’écran de l’Assistant de création d’une stratégie, avec mise en surbrillance de la stratégie de configuration d’application stipulant iOS version 8.0 ou ultérieure](../media/mtp/ios-app-config.png)

6. **Déployez l’application pour les utilisateurs** en sélectionnant l’application Lookout for Work, puis choisissez **Gérer le déploiement**.

  Vous devez sélectionner les mêmes utilisateurs que ceux qui ont été ajoutés à l’option Gestion des inscriptions dans la console Lookout.  Pour plus d’informations sur l’ajout de groupes d’utilisateurs dans Lookout MTP, consultez l’étape 3 dans la section [Configurer votre abonnement à Lookout](https://docs.microsoft.com/sccm/protect/deploy-use/configure-and-deploy-lookout-for-work-apps).

  >[!IMPORTANT]
  > L’Assistant Déploiement d’application Intune n’a pas connaissance des groupes d’utilisateurs Azure AD et utilise les groupes d’utilisateurs Intune à la place. Vous devez donc créer un groupe d’utilisateurs Intune basé sur le groupe d’utilisateurs Azure AD qui est inscrit dans la console Lookout, comme cela est décrit dans [cette](plan-your-user-and-device-groups.md) rubrique.

  Choisissez l’option **Installation requise** pour exiger que l’application Lookout soit installée sur l’appareil de l’utilisateur.

## <a name="what-happens-when-the-deployed-app-is-opened-on-the-device"></a>Que se passe-t-il quand l’application déployée est ouverte sur l’appareil ?

Quand l’utilisateur ouvre l’application Lookout for Work sur l’appareil, il est invité à activer l’application et à choisir l’option Se connecter avec Azure Active Directory. Une procédure pas à pas pour l’utilisateur final est décrite dans les rubriques suivantes :

* [Vous êtes invité à installer Lookout for Work sur votre appareil Android](http://docs.microsoft.com/intune/enduser/you-are-prompted-to-install-lookout-for-work-android)

* [Vous devez résoudre une menace que Lookout for Work a détectée sur votre appareil Android](http://docs.microsoft.com/intune/enduser/you-need-to-resolve-a-threat-found-by-lookout-for-work-android)

## <a name="next-steps"></a>Étapes suivantes
* [Créer une stratégie de conformité des appareils Lookout dans Intune](https://docs.microsoft.com/sccm/protect/deploy-use/enable-device-threat-protection-rule-compliance-policy)

