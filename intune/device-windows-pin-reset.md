---
title: "Réinitialiser le code secret sur les appareils Windows avec Intune"
titlesuffix: Azure portal
description: "Apprenez à utiliser Intune pour réinitialiser le code secret sur les appareils Windows intégrés au service de réinitialisation de code PIN Microsoft."
keywords: 
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 08/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5027d012-d6c2-4971-a9ac-217f91d67d87
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b6149eeb3da2da3be3a137845eee5a0a515a4e39
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/25/2018
---
# <a name="reset-the-passcode-on-windows-devices-integrated-with-the-microsoft-pin-reset-service-using-intune"></a>Réinitialiser le code secret sur les appareils Windows intégrés au service de réinitialisation de code PIN Microsoft avec Intune

La fonctionnalité de réinitialisation du code secret pour les appareils Windows s’intègre au service de réinitialisation de code PIN Microsoft pour vous permettre de générer un nouveau code secret pour les appareils qui exécutent Windows 10 Mobile. Les appareils doivent exécuter Windows 10 Creators Update ou une version ultérieure.

## <a name="supported-platforms"></a>Plateformes prises en charge

- Windows - Prise en charge de Windows 10 Creators Update et ultérieur (joint à Azure AD)
- Windows Phone - Non prise en charge
- iOS - Non prise en charge
- macOS - Non prise en charge
- Android - Non prise en charge


## <a name="before-you-start"></a>Avant de commencer

Avant de pouvoir réinitialiser à distance le code secret sur les appareils Windows que vous pouvez gérer, vous devez intégrer le service de réinitialisation de code PIN à votre client Intune et configurer les appareils que vous gérez. Pour ce faire, suivez les instructions ci-dessous :

### <a name="connect-intune-with-the-pin-reset-service"></a>Connecter Intune au service de réinitialisation de code PIN

1. Visitez le [site web d’intégration du service de réinitialisation de code PIN Microsoft](https://login.windows.net/common/oauth2/authorize?response_type=code&client_id=b8456c59-1230-44c7-a4a2-99b085333e84&resource=https%3A%2F%2Fgraph.windows.net&redirect_uri=https%3A%2F%2Fcred.microsoft.com&state=e9191523-6c2f-4f1d-a4f9-c36f26f89df0&prompt=admin_consent) et connectez-vous en utilisant le compte d’administrateur client qui vous permet de gérer votre client Intune.
2. Une fois connecté, cliquez sur **Accepter** pour autoriser le service de réinitialisation de code PIN à accéder à votre compte.<br>
![Page des autorisations du service de réinitialisation de code PIN](./media/pin-reset-service-application.png)
3. Dans le portail Azure, vous pouvez vérifier qu’Intune et le service de réinitialisation de code PIN ont été intégrés dans le panneau Applications d’entreprise - Toutes les applications comme indiqué dans la capture d’écran suivante :<br>
![Application du service de réinitialisation de code PIN dans Azure](./media/pin-reset-service-home-screen.png)
4. Connectez-vous à [ce site web](https://login.windows.net/common/oauth2/authorize?response_type=code&client_id=9115dd05-fad5-4f9c-acc7-305d08b1b04e&resource=https%3A%2F%2Fcred.microsoft.com%2F&redirect_uri=ms-appx-web%3A%2F%2FMicrosoft.AAD.BrokerPlugin%2F9115dd05-fad5-4f9c-acc7-305d08b1b04e&state=6765f8c5-f4a7-4029-b667-46a6776ad611&prompt=admin_consent) avec vos informations d’identification d’administrateur de client Intune et choisissez à nouveau **Accepter** pour autoriser le service à accéder à votre compte.

### <a name="configure-windows-devices-to-use-pin-reset"></a>Configurer les appareils Windows pour utiliser la réinitialisation de code PIN

Pour configurer la réinitialisation de code PIN sur les appareils Windows que vous gérez, utilisez une [stratégie d’appareil personnalisée Windows 10 Intune](custom-settings-windows-10.md) pour activer la fonctionnalité. Configurez la stratégie à l’aide du fournisseur de services de configuration de stratégie Windows suivant :


- **Pour les appareils** - **./Device/Vendor/MSFT/PassportForWork/*ID_locataire*/Policies/EnablePinRecovery**

*ID_locataire* fait référence à l’ID de votre annuaire Azure Active Directory que vous pouvez obtenir dans la page **Propriétés** d’Azure Active Directory.

Affectez à ce fournisseur de services de configuration la valeur **True**.

## <a name="steps-to-reset-the-passcode"></a>Étapes pour réinitialiser le code secret

1. Connectez-vous au portail Azure.
2. Choisissez **Autres services** > **Surveillance + Gestion** > **Intune**.
3. Dans le panneau **Intune**, choisissez **Appareils**.
4. Dans le panneau **Appareils**, choisissez **Gérer** > **Tous les appareils**.
5. Sélectionnez l’appareil pour lequel vous souhaitez réinitialiser le code secret puis, dans le panneau Propriétés de l’appareil, choisissez **Nouveau code secret**.
6. Dans la zone de confirmation qui s’affiche, choisissez **Oui**. Le code secret est généré et affiché dans le portail pendant les sept prochains jours.

## <a name="next-steps"></a>Étapes suivantes

Si la réinitialisation du code secret échoue, un lien est fourni dans le portail pour obtenir plus d’informations.


