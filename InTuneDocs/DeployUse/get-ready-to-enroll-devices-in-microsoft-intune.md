---
# required metadata

title: Se préparer à inscrire des appareils dans Microsoft Intune | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 44fd4af0-f9b0-493a-b590-7825139d9d40

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Se préparer à inscrire des appareils dans Microsoft Intune
Pour permettre aux employés d’inscrire des appareils mobiles (dont Android, iOS et Windows Phone, ainsi que des PC Windows) auprès d’Intune, vous devez activer l’inscription d’appareils. Pour autoriser l’inscription, vous devez définir une autorité de gestion des appareils mobiles, configurer le portail d’entreprise Intune, attribuer des licences et activer l’inscription pour la plateforme d’appareils.

## <a name="BKMK_Set_MDM_Authority"></a>Définir l'autorité de gestion des appareils mobiles
L’autorité de gestion d’appareils mobiles définit le service de gestion habilité à gérer un ensemble d’appareils. Les options en matière d’autorité de gestion des appareils mobiles incluent Intune en version autonome et Configuration Manager avec Intune. Si vous définissez Configuration Manager en tant qu’autorité de gestion, aucun autre service ne peut être utilisé pour la gestion des appareils mobiles.

>[!IMPORTANT]
> Réfléchissez bien avant de décider de gérer les appareils mobiles à l’aide d’Intune uniquement (service en ligne) ou à l’aide de System Center Configuration Manager avec Intune (solution logicielle locale avec service en ligne). Une fois qu’elle est définie, l’autorité de gestion des appareils mobiles n’est pas modifiable.



1.  Dans la [console d’administration Microsoft Intune](http://manage.microsoft.com), cliquez sur **Admin** &gt; **Gestion des appareils mobiles**.

2.  Dans la liste **Tâches** , cliquez sur **Définir l'autorité de gestion des appareils mobiles**. La boîte de dialogue **Définir l'autorité MDM** s'ouvre.

    ![Boîte de dialogue Définir l’autorité MDM](../media/intune-mdm-authority.png)

3.  Intune vous invite à confirmer que vous souhaitez définir Intune comme autorité MDM. Cochez la case, puis cliquez sur **Oui** pour utiliser Microsoft Intune pour gérer les appareils mobiles.

## Configurer le portail d’entreprise Intune et attribuer des licences
Le portail d’entreprise Intune aide les utilisateurs à accéder aux ressources d’entreprise, telles que les applications, à trouver des informations de support technique ainsi qu’à inscrire et désinscrire des appareils. Avant l’inscription d’appareils, vous devez [configurer le portail d’entreprise](/intune/get-started/get-started-with-a-paid-subscription-to-microsoft-intune-step-7). Vous devez également [attribuer des licences utilisateur](/intune/get-started/get-started-with-a-paid-subscription-to-microsoft-intune-step-4) pour autoriser l’accès à Intune.

## Configurer la gestion des appareils
Après avoir configuré l’autorité de gestion des appareils mobiles, vous devez configurer la gestion des appareils pour les systèmes d’exploitation que votre organisation souhaite prendre en charge. Les étapes requises pour configurer la gestion des appareils varient selon le système d’exploitation. Par exemple, le système d’exploitation Android ne vous demande d’effectuer aucune opération dans la console d’administration Intune. En revanche, iOS et Windows nécessitent une relation d’approbation entre les appareils et Intune pour autoriser la gestion.

> [!div class="op_single_selector"]
- [Configuration de la gestion Android avec Microsoft Intune](set-up-android-management-with-microsoft-intune.md)
- [Configurer la gestion iOS et MAC avec Microsoft Intune](set-up-ios-and-mac-management-with-microsoft-intune.md)
- [Configurer la gestion de Windows Phone avec Microsoft Intune](set-up-windows-phone-management-with-microsoft-intune.md)
- [Configurer la gestion des périphériques Windows avec Microsoft Intune](set-up-windows-device-management-with-microsoft-intune.md)

Vous pouvez également effectuer les opérations suivantes :
 - Utiliser le [compte de gestionnaire d’inscription d’appareil](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md) pour inscrire de nombreux appareils
 - [Indiquer les appareils d’entreprise avec des numéros IMEI](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md) pour mieux inscrire les appareils et cibler la stratégie


<!--HONumber=May16_HO1-->


