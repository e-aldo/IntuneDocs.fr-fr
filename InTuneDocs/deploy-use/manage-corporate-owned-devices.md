---
title: "Gérer les appareils d’entreprise | Microsoft Docs"
description: "Inscrivez les appareils d’entreprise de différentes façons, selon le type d’appareil, la méthode utilisée pour son achat et les besoins de l’organisation."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 01/29/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2b60bbff-25e6-489b-9621-c71b4275fa06
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 521a37044d6721fe905db7740329688ba2c24b35
ms.openlocfilehash: ae077d80e05b33d625285d796917f4f6c153ca3f


---

# <a name="enroll-corporate-owned-devices-by-using-intune"></a>Inscrire des appareils d’entreprise à l’aide d’Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Vous pouvez inscrire des appareils d’entreprise ou d’organisation en vue de les gérer avec Intune de diverses façons en fonction du type d’appareil, de la méthode utilisée pour son achat et des besoins de l’organisation. Vous pouvez également installer l’application Portail d’entreprise pour inscrire et gérer les appareils d’entreprise, comme dans un scénario BYOD (« Apportez votre propre appareil »).

Par défaut, les appareils de toutes les plateformes peuvent être inscrits dans Intune. Pour bloquer l’inscription des appareils, connectez-vous au [portail d’administration Microsoft Intune](http://manage.microsoft.com) avec vos informations d’identification d’administrateur. Choisissez **Admin** > **Gestion des appareils mobiles** > **Règles d’inscription**, puis décochez les cases appropriées pour les plateformes que vous souhaitez bloquer.

## <a name="enroll-corporate-owned-ios-devices"></a>Inscrire des appareils iOS d'entreprise

Les méthodes d’inscription d’appareil d’entreprise constituent un bon choix dans le cadre des scénarios CYOD (« Choisissez votre propre appareil »). Dans un environnement CYOD, l’organisation paie pour un appareil que l’utilisateur sélectionne et elle gère l’appareil.

Si vous proposez aux utilisateurs de choisir parmi des appareils iOS, vous pouvez préconfigurer l’inscription afin que l’appareil soit géré avec Intune dès que l’utilisateur l’allume pour la première fois. Intune prend en charge l’inscription à l’aide du service [Apple DEP (Device Enrollment Program)](ios-device-enrollment-program-in-microsoft-intune.md) ou de l’outil Apple Configurator sur un ordinateur Mac pour l’inscription [directe](ios-direct-enrollment-in-microsoft-intune.md) ou avec l’[Assistant de configuration](ios-setup-assistant-enrollment-in-microsoft-intune.md).

Découvrez comment [inscrire des appareils iOS d’entreprise](enroll-corporate-owned-ios-devices-in-microsoft-intune.md).

## <a name="create-a-device-enrollment-manager-account"></a>Créer un compte de gestionnaire d’inscription d’appareil

Vous pouvez créer un compte de gestionnaire d’inscription d’appareil pour utilisateur unique dans Intune pour gérer un grand nombre d’appareils mobiles pour votre organisation. Après avoir créé un compte de gestionnaire d’inscription d’appareil, un gestionnaire de compte désigné peut inscrire plus d’appareils que les 15 pouvant être inscrits par un utilisateur standard.

Vous pouvez utiliser un compte de gestionnaire d’inscription d’appareil pour inscrire uniquement des appareils qui ne sont pas utilisés par un utilisateur spécifique. Ces types d’appareils sont adaptés aux applications utilitaires ou de point de vente, par exemple, mais ne le sont pas pour les utilisateurs qui doivent accéder à des e-mails ou ressources de l’entreprise.

Découvrez comment [inscrire des appareils d’entreprise en utilisant un compte de gestionnaire d’inscription d’appareil](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md).

## <a name="enroll-corporate-owned-windows-10-enterprise-devices"></a>Inscrire des appareils d’entreprise Windows 10 Entreprise

Si vous utilisez Azure Active Directory Premium ou Microsoft Enterprise Mobility Suite dans votre organisation, vous pouvez [inscrire des appareils Windows 10 Entreprise](https://docs.microsoft.com/active-directory/active-directory-azureadjoin-windows10-devices-overview). Quand un utilisateur ajoute un compte professionnel ou scolaire sur un appareil, celui-ci est automatiquement marqué comme « appartenant à l’entreprise ».

## <a name="import-imei-numbers"></a>Importer des numéros IMEI

De nombreux fabricants d’appareils mobiles utilisent un numéro unique appelé IMEI sur leurs appareils. Vous pouvez importer les numéros IMEI des appareils appartenant à votre organisation. Quand l’appareil est géré par Intune, il est marqué comme appareil appartenant à l’entreprise.

Découvrez comment [marquer des appareils d’entreprise en utilisant des numéros IMEI](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md).

## <a name="identify-a-device-as-corporate-owned"></a>Identifier un appareil comme appartenant à l’entreprise

Intune reconnaît un appareil comme « appartenant à l’entreprise » quand l’une des conditions suivantes est remplie :

 - Il a été [inscrit à l’aide d’un compte de gestionnaire d’inscription d’appareil](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md) (toutes plateformes confondues).
 - Il a été inscrit à l’aide du service [Apple DEP](ios-device-enrollment-program-in-microsoft-intune.md) ou de l’outil [Apple Configurator](ios-setup-assistant-enrollment-in-microsoft-intune.md) (iOS uniquement).
 - Son fabricant l’a [prédéclaré à l’aide de numéros IMEI](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md) (toutes les plateformes avec des numéros IMEI).
 - Il est inscrit dans [Azure Active Directory ou Enterprise Mobility Suite comme appareil Windows 10 Entreprise](https://docs.microsoft.com/active-directory/active-directory-azureadjoin-windows10-devices-overview) (Windows 10 uniquement).

Quand un appareil est marqué comme appartenant à l’entreprise, la colonne **Propriété** de cet enregistrement d’appareil indique **Entreprise** dans la Console Administrateur. 



<!--HONumber=Jan17_HO5-->


