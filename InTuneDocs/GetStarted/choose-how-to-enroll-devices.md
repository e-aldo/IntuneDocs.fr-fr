---
# required metadata

title: Choisir comment inscrire des appareils mobiles | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 06/06/2016
ms.topic: article
ms.prod:
ms.service:
ms.technology:
ms.assetid: cac62b64-3f8b-47ae-aa66-970c7ba15466

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
#ms.reviewer: damionw
#ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Choisir comment inscrire des appareils mobiles

L’inscription des appareils mobiles est le processus qui permet de gérer les smartphones, les tablettes et les ordinateurs portables dans Microsoft Intune. En tant qu’administrateur, vous devez déterminer la meilleure façon d’inscrire les appareils en fonction des éléments suivants :

 -  Propriété (appareil personnel ou d’entreprise)
 -  Utilisation (partagée ou personnelle)
 -  Plateforme (iOS, Android, Windows Phone, PC, Mac)

Vos réponses aux questions suivantes vous permettront de déterminer la méthode d’inscription qui convient le mieux pour les appareils que vous gérez.

## **Les employés apportent-ils leurs propres appareils ou sont-ils fournis par l’entreprise ?**

  L’inscription des **appareils personnels**, ou inscription « Apportez votre propre appareil » (BYOD), permet aux utilisateurs d’inscrire leurs appareils pour accéder aux ressources de l’entreprise telles que la messagerie, les applications d’entreprise, les données d’entreprise et le support. Les **appareils d’entreprise** sont fournis par l’entreprise pour répondre aux besoins professionnels des employés.
  > [!div class="button"]   [Inscription BYOD >](#byod-device-enrollment)   [Inscription d’un appareil d’entreprise >](cod-device-enrollment)

### Inscription d’un appareil BYOD

L’inscription de type BYOD nécessite que les utilisateurs installent l’application Portail d’entreprise Intune sur leurs appareils. Ils peuvent ensuite lancer l’application et s’inscrire en fournissant les identifiants de leur compte professionnel ou scolaire. Si Intune trouve une licence correspondant à ces identifiants, l’appareil est ajouté à la console d’administration Intune et reçoit la stratégie Intune qui lui permet d’accéder aux ressources de l’entreprise.

**Sélectionnez le type d’appareil :**

> [!div class="op_single_selector"]
- [Configuration de la gestion Android avec Microsoft Intune](..deploy-use/set-up-android-management-with-microsoft-intune.md)
- [Configurer la gestion iOS et MAC avec Microsoft Intune](..deploy-use/set-up-ios-and-mac-management-with-microsoft-intune.md)
- [Configurer la gestion de Windows Phone avec Microsoft Intune](..deploy-use/set-up-windows-phone-management-with-microsoft-intune.md)
- [Configurer la gestion des périphériques Windows avec Microsoft Intune](..deploy-use/set-up-windows-device-management-with-microsoft-intune.md)


### Inscription d’un appareil d’entreprise

Les appareils d’entreprise peuvent être inscrits pour un usage unique ou partagé.  Les **appareils partagés** n’ont pas d’utilisateur attitré et ne sont généralement pas configurés pour accéder à la messagerie. Il peut s’agir d’appareils de type bornes ou autres appareils à visée utilitaire que les utilisateurs empruntent, puis rendent quand ils ont terminé. Les méthodes d’inscription recommandées dépendent de la plateforme de l’appareil. Les **appareils dédiés** sont attribués à des utilisateurs individuels et doivent être suivis comme des ressources d’entreprise tout en permettant aux utilisateurs d’accéder à leur messagerie et à leurs données comme sur leurs appareils personnels. Les méthodes d’inscription recommandées dépendent de la plateforme de l’appareil.

## **Vos appareils d’entreprise sont-ils partagés ou dédiés ?**

> [!div class="button"] [Partagés >](#Shared-company-owned-devices)   [Dédiés >](..deploy-use/get-ready-to-enroll-devices-in-microsoft-intune)


### Appareils d’entreprise partagés

Ces appareils n’ont pas d’utilisateur attitré et ne sont généralement pas configurés pour accéder à la messagerie. Il peut s’agir d’appareils de type bornes ou autres appareils à visée utilitaire que les utilisateurs empruntent, puis rendent quand ils ont terminé. Les méthodes d’inscription recommandées dépendent de la plateforme de l’appareil.

  - **Appareils Windows et Android** : un *gestionnaire d’inscription d’appareil* est un compte Intune qui peut être utilisé pour inscrire plusieurs appareils partagés à l’aide de l’application Portail d’entreprise.
  > [!div class="button"]   [Windows >](../deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune) [Android >](../deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune) [iOS >](#shared-ios-device-enrollment)

### Inscription d’appareils iOS partagés

La méthode recommandée pour l’inscription des appareils iOS partagés appartenant à l’entreprise dépend de la manière dont vous avez acheté ces appareils, ainsi que de la manière dont vous les gérez :

  - **Programme d’inscription des appareils (DEP) d’Apple** : les appareils iOS achetés ou gérés à l’aide du programme d’inscription des appareils peuvent être ciblés avec un profil d’inscription. Quand les utilisateurs allument leur appareil pour la première fois, celui-ci télécharge le profil DEP et s’inscrit avec ce profil.
  - **Apple Configurator sur Mac** : Apple Configurator est une application Apple qui s’exécute sur un ordinateur Mac. Pour installer un profil d’inscription sur un appareil iOS, connectez ce dernier au Mac à l’aide d’un câble USB. Si vous pouvez réinitialiser les appareils aux paramètres d’usine pour les inscrire, utilisez l’inscription à l’aide de l’Assistant Configuration. Si vous ne souhaitez pas réinitialiser les appareils, utilisez l’inscription directe.
  - **Aucune des méthodes ci-dessus** : si vous ne pouvez pas ou ne souhaitez pas utiliser les méthodes d’inscription DEP Apple ou Apple Configurator, utilisez le gestionnaire d’inscription d’appareil d’Intune.

  **Choisissez :**
    > [!div class="button"]      [Inscription DEP >](../deploy-use/ios-device-enrollment-program-in-microsoft-intune) [Mac >](../deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune) [Inscription directe >](../deploy-use/ios-direct-enrollment-in-microsoft-intune)  

  > [!div class="button"]     [Inscription à l’aide du gestionnaire d’inscription d’appareil >](../deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune)

**Utilisateurs individuels** : les appareils d’entreprise qui sont attribués à des utilisateurs individuels doivent être suivis comme des ressources d’entreprise tout en permettant aux utilisateurs d’accéder à leur messagerie et à leurs données comme sur leurs appareils personnels. Les méthodes d’inscription recommandées dépendent de la plateforme de l’appareil.

  - **Appareils Windows et Android** : en important les numéros IMEI des appareils d’entreprise, vous pouvez les marquer comme des appareils d’entreprise dans Intune. Les utilisateurs peuvent ensuite inscrire leurs appareils en tant qu’appareils personnels en installant l’application Portail d’entreprise. Ils pourront ainsi accéder aux ressources d’entreprise telles que la messagerie, les applications et les données.
  > [!div class="button"]   [Marquer à l’aide de l’IMEI >](../deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers)

  - **Appareils iOS** : les appareils iOS partagés peuvent être gérés de trois façons.  **Comment allez-vous inscrire vos appareils iOS partagés ?**

    - **Programme d’inscription des appareils (DEP) d’Apple** : les appareils iOS achetés ou gérés à l’aide du programme d’inscription des appareils peuvent être ciblés avec un profil d’inscription. Quand les utilisateurs allument leur appareil pour la première fois, celui-ci télécharge le profil DEP et s’inscrit avec ce profil.
    > [!div class="button"]     [Inscription DEP](../deploy-use/ios-device-enrollment-program-in-microsoft-intune).

    - **Apple Configurator sur un Mac** : Apple Configurator est une application Apple qui s’exécute sur un ordinateur Mac. Pour installer un profil d’inscription sur un appareil iOS, connectez ce dernier au Mac à l’aide d’un câble USB. Si vous pouvez réinitialiser les appareils aux paramètres d’usine pour les inscrire, utilisez l’inscription à l’aide de l’Assistant Configuration.

    Si vous ne souhaitez pas réinitialiser les appareils, utilisez l’inscription directe.
    Si vous pouvez réinitialiser les appareils aux paramètres d’usine pour les inscrire, utilisez l’inscription à l’aide de l’Assistant Configuration.
    > [!div class="button"] [Inscription Assistant d’installation iOS](../deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune) [!div class="button"] [Inscription directe iOS](../deploy-use/ios-direct-enrollment-in-microsoft-intune).

    - **Aucune des méthodes ci-dessus** : si vous ne pouvez pas ou ne souhaitez pas utiliser les méthodes d’inscription DEP Apple ou Apple Configurator, vous pouvez marquer les appareils comme des appareils d’entreprise en important leur numéro IMEI dans Intune. Les utilisateurs peuvent ensuite inscrire leurs appareils en tant qu’appareils personnels en installant l’application Portail d’entreprise. Ils pourront ainsi accéder aux ressources d’entreprise telles que la messagerie, les applications et les données. > [!div class="button"][Marquer les appareils à l’aide de leur numéro IMEI](../deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers)


<!--HONumber=Jun16_HO2-->


