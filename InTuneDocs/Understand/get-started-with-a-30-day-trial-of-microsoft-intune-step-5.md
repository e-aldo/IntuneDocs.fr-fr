---
title: "Inscrire des appareils mobiles pour évaluation | Microsoft Intune"
description: "Comment inscrire des appareils mobiles et installer une application lorsque vous vous inscrivez à un essai gratuit d’Intune de 30 jours"
keywords: 
author: Staciebarker
manager: angrobe
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 47806f69-303d-41d9-9b0e-9b9445ea24ac
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 60ee39a7eeeb9068a7350ec87f60e7148ccb7826
ms.openlocfilehash: d441bb68a28a18cf45c616271cb33556df9f67f3


---

# Inscrire des appareils mobiles pour évaluation et installer une application
Pour configurer la gestion des appareils mobiles avec Intune, vous devez d’abord définir l’autorité de gestion des appareils mobiles, activer la gestion des plateformes d’appareils, puis inscrire vos appareils à l’aide de l’application de portail d’entreprise. Vous pouvez ensuite déployer l'application Microsoft Skype que vous avez publiée.

## Préparer le service pour la gestion des appareils

1.  **Utiliser Intune comme autorité de gestion des appareils mobiles**

    Dans la [console d’administration Intune](https://manage.microsoft.com/), cliquez sur **Admin** &gt; **Gestion des appareils mobiles**. Choisissez **Tâches** > **Définir l’autorité MDM**, puis **Oui** dans la boîte de dialogue **Autorité MDM**.

2.  **Activer la gestion des appareils mobiles pour votre plateforme d'appareils**

    Activez la gestion des appareils mobiles pour la plateforme d'appareils que vous souhaitez gérer. La configuration requise varie en fonction de la plateforme :

    -   **iOS et Mac OS X** : consultez [Configurer la gestion iOS et Mac avec Microsoft Intune](/Intune/Deploy-Use/set-up-ios-and-mac-management-with-microsoft-intune).

    -   **Android** : les appareils mobiles Android permettent aux utilisateurs de s’inscrire à l’aide de l’application de portail d’entreprise disponible sur Google Play. Aucune configuration supplémentaire n'est nécessaire dans Intune.

    -   **Windows Phone** : consultez [Configurer la gestion Windows Phone avec Microsoft Intune](/Intune/Deploy-Use/set-up-windows-phone-management-with-microsoft-intune).

## Inscrire des appareils de test

### iOS et Mac OS X
Installez l’application **Portail d’entreprise Microsoft Intune** de Microsoft Corporation disponible dans l’App Store et connectez-vous avec les informations d’identification d’utilisateur Intune ajoutées ci-dessus. Affichez **Appareils inscrits** pour ajouter votre appareil.

### Android
Installez l’application **Portail d’entreprise Intune** de Microsoft Corporation disponible sur [Google Play](http://go.microsoft.com/fwlink/p/?LinkId=386612) et connectez-vous avec les informations d’identification d’utilisateur Intune ajoutées ci-dessus.

### Windows Phone 8.1
Les utilisateurs installent l’application **Portail d’entreprise** de Microsoft Corporation disponible dans le Windows Phone Store et se connectent avec les informations d’identification d’utilisateur Intune ajoutées ci-dessus.  Affichez **Appareils inscrits** pour ajouter votre appareil.

 ### Windows Phone 8.0
 Les utilisateurs cliquent sur **paramètres système** &gt; **applications de l’entreprise**, puis se connectent avec les informations d’identification d’utilisateur Intune ajoutées ci-dessus. L'application Portail d'entreprise est déployée sur votre téléphone.

Si vous êtes invité à entrer une **Adresse du serveur**, tapez « manage.microsoft.com ».


## Installer l’application précédemment déployée
Ouvrez le portail d’entreprise sur l’appareil mobile, choisissez **Applications**, puis installez **Microsoft Skype**.

Pour en savoir plus sur la gestion des appareils mobiles à l’aide d’Intune, consultez [Se préparer à inscrire des appareils dans Microsoft Intune](/Intune/deploy-use/get-ready-to-enroll-devices-in-microsoft-intune).

### Étapes suivantes
Félicitations ! Vous venez d’effectuer l’étape 5 de la procédure pas à pas de la *version d’évaluation de Microsoft Intune*.

>[!div class="step-by-step"]

>[&larr; **Créer des stratégies**](.\get-started-with-a-30-day-trial-of-microsoft-intune-step-4.md)     [**Options et fonctionnalités supplémentaires** &rarr;](.\get-started-with-a-30-day-trial-of-microsoft-intune-step-6.md)  



<!--HONumber=Jul16_HO4-->


