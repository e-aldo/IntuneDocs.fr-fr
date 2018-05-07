---
title: Gérer les appareils Windows Holographic avec Microsoft Intune - Azure | Microsoft Docs
description: Avec Microsoft Intune, vous pouvez effectuer différentes tâches sur des appareils exécutant Windows Holographic for Business, notamment configurer le Portail d’entreprise, créer une stratégie de conformité, personnaliser les paramètres OMA-URI, déployer des applications, catégoriser les appareils en groupes, créer des profils, imposer des restrictions aux appareils, activer les mises à jour logicielles, définir des conditions générales, configurer les paramètres VPN et Wi-Fi, et utiliser Hello Entreprise.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 4/5/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 45d8f5051d9663273c6515717b7930145ff8a964
ms.sourcegitcommit: 2773f388f50654366197a95a6838306f70fc18b8
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/18/2018
---
# <a name="customize-devices-running-windows-holographic-with-intune"></a>Personnaliser les appareils exécutant Windows Holographic avec Intune

Microsoft Intune prend en charge les appareils exécutant Windows Holographic for Business, comme [Microsoft HoloLens](https://docs.microsoft.com/en-us/hololens/).

Pour gérer les appareils qui exécutent Windows Holographic avec Microsoft Intune, vous devez créer un profil Mise à niveau d’édition. Ce profil de mise à niveau permet de mettre à niveau les appareils de Windows Holographic vers Windows Holographic for Business. Pour Microsoft HoloLens, vous pouvez acheter Commercial Suite afin d’obtenir la licence nécessaire pour la mise à niveau. Pour plus d’informations, consultez [Mettre à niveau les appareils exécutant Windows Holographique vers Windows Holographic for Business](holographic-upgrade.md).

Pour gérer et personnaliser plus facilement vos appareils Windows Holographic for Business, utilisez les tâches décrites dans cet article. Par exemple, vous pouvez gérer les mises à jour logicielles, configurer les paramètres VPN, etc.

## <a name="company-portal"></a>Portail d'entreprise
**[Configurer l’application Portail d’entreprise](company-portal-app.md)**

Intune inclut le Portail d’entreprise, qui permet aux utilisateurs d’accéder aux données de l’entreprise, d’inscrire des appareils, d’installer des applications, de contacter votre service informatique, etc. Vous pouvez personnaliser l’application Portail d’entreprise pour les appareils exécutant Windows Holographic for Business.

## <a name="compliance-policy"></a>Stratégie de conformité
**[Créer une stratégie de conformité des appareils](compliance-policy-create-windows.md)**

Les stratégies de conformité sont des règles et des paramètres que les appareils doivent respecter pour être conformes. Vous pouvez utiliser ces stratégies avec un accès conditionnel pour empêcher les appareils non conformes d’accéder aux ressources de l’entreprise. Dans Intune, vous pouvez créer des stratégies de conformité pour autoriser ou bloquer l’accès des appareils exécutant Windows Holographic for Business. Par exemple, vous pouvez créer une stratégie qui impose l’activation de BitLocker.

Voir aussi **[Bien démarrer avec les stratégies de conformité](device-compliance-get-started.md)**.

## <a name="deploy-and-manage-apps"></a>Déployer et gérer des applications
**[Ajouter des applications à Intune](apps-add.md)**

À l’aide d’Intune, vous pouvez ajouter des applications aux appareils exécutant Windows Holographic for Business. Il existe plusieurs façons de déployer des applications. Par exemple, vous pouvez :

- [Ajouter des applications Microsoft Store](store-apps-windows.md)
- [Ajouter des applications que vous créez](lob-apps-windows.md)
- [Affecter des applications à des groupes](apps-deploy.md)

Microsoft Intune peut déployer des applications Windows universelles sur les appareils Microsoft HoloLens exécutant Windows Holographic for Business. Vous pouvez charger directement vos packages d’applications sur le portail Azure Intune, ou les déployer à partir du Microsoft Store pour Entreprises. Pour plus d’informations sur les domaines connexes, consultez ce qui suit :
- Pour déployer des applications métier à l’aide du portail Azure Intune, consultez [Guide pratique pour ajouter des applications métier Windows à Microsoft Intune](lob-apps-windows.md).
- Pour déployer des applications à l’aide du Microsoft Store pour Entreprises, consultez [Guide pratique pour gérer les applications que vous avez achetées dans le Microsoft Store pour Entreprises avec Microsoft Intune](windows-store-for-business.md). 
- Pour en savoir plus sur la gestion des applications avec Microsoft Intune, consultez [Qu’est-ce que la gestion des applications Microsoft Intune ?](app-management.md).
- Pour en savoir plus sur le développement d’applications pour Microsoft HoloLens, consultez [Applications de réalité mixte pour Microsoft HoloLens](https://www.microsoft.com/hololens/apps). 

> [!NOTE]
> Les appareils HoloLens exécutant Windows 10 Holographic for Business 1607 ne prennent pas en charge les applications sous licence en ligne du Microsoft Store pour Entreprises. Pour en savoir plus, consultez [Installer des applications sur HoloLens](https://docs.microsoft.com/en-us/hololens/hololens-install-apps).


## <a name="device-categories-and-groups"></a>Catégories et groupes d’appareils
**[Catégoriser les appareils en groupes](device-group-mapping.md)**

À l’aide d’Intune, vous pouvez créer des catégories d’appareils pour ajouter automatiquement des appareils à des groupes en fonction des catégories créées, par exemple Ventes, Comptabilité, Ressources humaines, etc. L’idée est de faciliter la gestion de vos appareils exécutant Windows Holographic for Business.

## <a name="device-configuration-profiles"></a>Profils de configuration d’appareil 
**[Bien démarrer avec les profils de configuration](device-profiles.md) et [créer votre propre profil](device-profile-create.md)**

Intune inclut des paramètres et des fonctionnalités que vous pouvez activer ou désactiver sur différents appareils de votre organisation. Ces paramètres et fonctionnalités sont gérés à l’aide de profils. Par exemple, vous pouvez créer un profil qui active Cortana ou Windows Defender SmartScreen sur vos appareils exécutant Windows Holographic for Business.

Dans vos profils, vous pouvez utiliser OMA-URI pour personnaliser certains paramètres, imposer des restrictions aux appareils et configurer un réseau VPN (réseau privé virtuel) ou Wi-Fi.

#### <a name="custom-device-settingscustom-settings-windows-holographicmd"></a>[Paramètres d’appareil personnalisés](custom-settings-windows-holographic.md)

Pour configurer les paramètres OMA-URI (Open Mobile Alliance Uniform Resource Identifier), vous pouvez créer un profil personnalisé dans Intune. Utilisez les paramètres OMA-URI pour contrôler différentes fonctionnalités sur vos appareils Windows Holographic for Business, par exemple l’activation d’un VPN ou la recherche de mises à jour sur Microsoft Update.

#### <a name="device-restrictionsdevice-restrictions-windows-holographicmd"></a>[Restrictions relatives aux appareils](device-restrictions-windows-holographic.md)

Les restrictions imposées aux appareils vous permettent de contrôler différents paramètres et fonctionnalités sur vos appareils, notamment la saisie d’un mot de passe obligatoire, l’installation d’applications à partir du [Microsoft Store](https://www.microsoft.com/store/apps/windows?icid=CNavAppsWindowsApps), l’activation de Bluetooth, etc. Vous créez ces restrictions dans un profil Intune. Vous pouvez appliquer ce profil à plusieurs appareils exécutant Windows Holographic for Business.

#### <a name="configure-vpnvpn-settings-configuremd"></a>[Configurer un VPN](vpn-settings-configure.md)

Les réseaux privés virtuels (ou VPN) donnent à vos utilisateurs un accès distant sécurisé à votre réseau d’entreprise. Dans Intune, vous pouvez créer un profil VPN comprenant des paramètres spécifiques pour vos appareils Windows Holographic for Business. Par exemple, vous pouvez créer un profil VPN pour que tous les appareils Windows Holographic for Business utilisent une connexion de type VPN Citrix.

#### <a name="configure-wi-fiwi-fi-settings-configuremd"></a>[Configurer le Wi-Fi](wi-fi-settings-configure.md)

Vous pouvez également créer un profil Wi-Fi dans Intune pour affecter des paramètres de réseau sans fil à vos appareils Windows Holographic for Business. Quand vous affectez un profil Wi-Fi, vos utilisateurs finaux bénéficient d’un accès au réseau d’entreprise, sans aucune configuration réseau. Par exemple, vous pouvez créer un réseau Wi-Fi dédié uniquement aux appareils Windows Holographic for Business.

## <a name="software-updates"></a>Mises à jour logicielles
**[Gérer les mises à jour logicielles](windows-update-for-business-configure.md)**

Intune inclut une fonctionnalité appelée anneaux de mise à jour pour les appareils Windows 10. Ces anneaux de mise à jour comportent un groupe de paramètres qui déterminent l’installation des mises à jour. Par exemple, vous pouvez créer une fenêtre de maintenance pour installer les mises à jour, ou choisir de redémarrer l’appareil après l’installation des mises à jour. Vous pouvez appliquer un anneau de mise à jour à plusieurs appareils exécutant Windows Holographic for Business.

## <a name="terms-and-conditions"></a>Conditions générales
**[Définir les conditions générales de votre entreprise pour l’accès utilisateur](terms-and-conditions-create.md)**

Pour que les utilisateurs puissent inscrire des appareils et accéder aux applications de votre entreprise, notamment les e-mails, vous pouvez leur demander d’accepter d’abord les conditions générales de l’entreprise. Dans Intune, vous pouvez définir la manière dont les conditions générales s’affichent dans le Portail d’entreprise, et affecter également ces conditions générales aux appareils exécutant Windows Holographic for Business.

## <a name="windows-hello-for-business"></a>Windows Hello Entreprise
**[Utiliser Windows Hello Entreprise](windows-hello.md)**

Hello Entreprise est une méthode de connexion alternative qui utilise un compte Azure Active Directory à la place d’un mot de passe, d’une carte à puce ou d’une carte à puce virtuelle. Avec Hello Entreprise, vos appareils Windows Holographic for Business peuvent se connecter à l’aide d’un code PIN de longueur minimale défini par vos soins.
