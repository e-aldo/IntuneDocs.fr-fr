---
# required metadata

title: Inscrire des appareils mobiles et installer une application | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 5d3215e7-0a5c-44bd-afb0-aeafce98c43f

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# inscrire des appareils mobiles et installer une application
Pour configurer la gestion des appareils mobiles avec Intune, vous devez d’abord définir l’autorité de gestion des appareils mobiles, activer la gestion des plateformes d’appareils, puis inscrire vos appareils à l’aide de l’application Portail d’entreprise. Vous pouvez ensuite déployer l’application Microsoft Skype que vous avez publiée à l’étape 6.

## Activer la gestion des appareils et inscrire des appareils

1.  **Utiliser Intune comme autorité de gestion des appareils mobiles**
    Dans la [console d’administration Intune](https://manage.microsoft.com/), cliquez sur **Admin** > **Gestion des appareils mobiles**, puis sélectionnez **Définir l’autorité de gestion des appareils mobiles** sous **Tâches**.  Dans la boîte de dialogue Autorité de gestion des appareils mobiles, cliquez sur **Oui**.
    ![Console d’administration. Définir l’autorité de gestion des appareils mobiles sur Intune](./media/mdmAuthority.png)

2.  **Activer la gestion des appareils mobiles pour votre plateforme d'appareils**
    Activez la gestion des appareils mobiles pour la plateforme d'appareils que vous souhaitez gérer. La configuration requise varie en fonction de la plateforme :

    -   **iOS et Mac OS X** : consultez [Configurer la gestion iOS et Mac avec Microsoft Intune](/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune).

    -   **Windows Phone** : consultez [Configurer la gestion de Windows Phone avec Microsoft Intune](/intune/deploy-use/set-up-windows-phone-management-with-microsoft-intune).

    -   **Android** : les appareils mobiles Android permettent aux utilisateurs de s’inscrire à l’aide de l’application Portail d’entreprise disponible sur [Google Play](https://play.google.com/store/apps/details?id=com.skype.raider). Aucune configuration supplémentaire n'est nécessaire dans Intune.

3.  **Inscrire des appareils** :

    -   **Android** : installez l’application **Portail d’entreprise Intune** de Microsoft Corporation disponible sur [Google Play](http://go.microsoft.com/fwlink/p/?LinkId=386612) et connectez-vous avec les informations d’identification de l’utilisateur Intune ajoutées ci-dessus.

    -   **iOS et Mac OS X** : installez l’application **Portail d’entreprise Microsoft Intune** de Microsoft Corporation disponible dans l’App Store et connectez-vous avec les informations d’identification d’utilisateur Intune ajoutées ci-dessus. Affichez **Appareils inscrits** pour ajouter votre appareil.

    -   **Windows Phone 8.1** : les utilisateurs installent l’application **Portail d’entreprise** de Microsoft Corporation disponible dans le Windows Phone Store et se connectent avec les informations d’identification d’utilisateur Intune ajoutées ci-dessus.  Affichez **Appareils inscrits** pour ajouter votre appareil.

    -   **Windows Phone 8.0** : les utilisateurs cliquent sur **paramètres système** &gt; **applications de l’entreprise**, puis se connectent avec les informations d’identification d’utilisateur Intune ajoutées ci-dessus. L'application de portail d'entreprise est déployée sur votre téléphone.

    Si vous êtes invité à entrer une **Adresse du serveur**, tapez « manage.microsoft.com ».

## Installer une application sur un appareil inscrit
Dans l’[étape 6](start-with-a-paid-subscription-to-microsoft-intune-step-6.md) de ce guide de démarrage rapide, vous avez publié l’application Skype pour votre groupe d’utilisateurs Intune personnalisé. Maintenant, vous allez installer cette application sur un appareil nouvellement inscrit.

Ouvrez le Portail d’entreprise sur l’appareil mobile inscrit, choisissez **Applications**, puis installez **Microsoft Skype**.

Pour en savoir plus sur la gestion des appareils mobiles à l’aide de [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)], consultez [Se préparer à inscrire des appareils dans Microsoft Intune](/intune/deploy-use/get-ready-to-enroll-devices-in-microsoft-intune).


### Étapes suivantes
Félicitations ! Vous venez d’effectuer la dernière étape du *guide de démarrage rapide Intune*. Maintenant que votre configuration initiale est terminée, vous pouvez envisager d’activer des fonctionnalités supplémentaires de gestion des appareils mobiles.

>[!div class="step-by-step"]

>[&larr; **Inscrire des appareils**](.\start-with-a-paid-subscription-to-microsoft-intune-step-8.md)     [**Tâches de post-configuration** &rarr;](.\post-configuration-tasks.md)  


<!--HONumber=May16_HO1-->


