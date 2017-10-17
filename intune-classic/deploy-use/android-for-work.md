---
title: "À propos d’Android for Work"
description: "Intune gère Android for Work pour renforcer la confidentialité et les fonctionnalités de gestion dans le cadre de l’utilisation professionnelle des appareils Android."
keywords: 
author: nathbarn
manager: angrobe
ms.date: 03/22/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: aa0002d9-f5a0-466e-98ac-3970cb77e3a2
ROBOTS: NOINDEX,NOFOLLOW
ms.custom: intune-classic
ms.openlocfilehash: 17c066ee7208790a591272ae5e1edc99cf2141a4
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/10/2017
---
# <a name="manage-android-for-work-devices-with-intune"></a>Gérer les appareils Android for Work avec Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Android for Work est un ensemble de fonctionnalités et de services pour les appareils Android, qui séparent les applications et les données personnelles d’un profil de travail contenant des applications et des données professionnelles. Android for Work offre des fonctionnalités de gestion et une confidentialité supplémentaires dans le cadre de l’utilisation professionnelle des appareils Android. Intune vous permet de déployer les applications et les ressources d’entreprise sur les appareils Android for Work de manière à ce que les informations professionnelles soient séparées des informations personnelles. Déployées correctement, les applications et les données auxquelles elles accèdent demeurent exclusivement dans l’environnement Android for Work sur l’appareil.

## <a name="supported-devices"></a>Appareils pris en charge

Les fonctionnalités de gestion d’Android for Work s’appuient sur des fonctionnalités qui font partie du nouveau système d’exploitation Android. Android for Work est pris en charge sur les appareils exécutant Android 5.0 Lollipop et ultérieur qui prennent en charge les profils professionnels. Pour les appareils qui ne prennent pas en charge Android for Work, la gestion Android conventionnelle reste disponible. En savoir plus sur les [conditions requises par Android for Work](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012).

## <a name="onboarding"></a>Intégration

Avant d’inscrire des appareils Android for Work, vous devez effectuer certaines étapes d’intégration. Ces étapes établissent une connexion entre votre client Intune et le service Play for Work de Google, qui fait partie intégrante du processus de distribution et de gestion des applications Android for Work. En savoir plus sur l’[activation de l’inscription des appareils Android for Work](/intune-classic/deploy-use/set-up-android-for-work).

## <a name="work-profile-management"></a>Gestion des profils professionnels

Quand vous gérez un appareil Android for Work avec Intune, vous ne gérez pas l’ensemble de l’appareil. Les fonctionnalités de gestion affectent seulement le profil professionnel créé sur l’appareil lors de l’inscription. Toutes les applications déployées sur l’appareil avec Intune sont installées dans le profil professionnel. Les icônes des applications du profil professionnel affichent un porte-documents orange pour différencier les applications professionnelles des applications personnelles sur l’appareil. Toutes les applications Android et les données en dehors de la partie Android for Work de l’appareil demeurent personnelles et sous le contrôle de l’utilisateur final. Les utilisateurs peuvent installer n’importe quelle application de leur choix dans la partie personnelle de l’appareil, tandis que les administrateurs peuvent gérer et surveiller les applications et les actions dont l’étendue est limitée au profil professionnel.

Intune fournit un éventail de paramètres généraux intégrés que vous pouvez configurer sur les appareils Android for Work. En savoir plus sur les [paramètres de stratégie d’Android for Work](android-for-work-policy-settings-in-microsoft-intune.md)

## <a name="app-publishing-and-distribution"></a>Distribution et publication des applications

Le service Google Play for Work fait partie intégrante de la gestion et de la distribution des applications Android for Work. Toutes les applications déployées sur les appareils Android for Work dans le profil professionnel proviennent du service Play for Work. Pour gérer et déployer des applications dans le Play Store, vous vous connectez au site web de Google Play en tant qu’administrateur de votre entreprise pour la gestion de Google. Vous pouvez approuver des applications pour le un déploiement Android for Work afin qu’elles apparaissent dans les profils de travail des appareils. Ces applications peuvent alors se synchroniser à la console Intune où elles peuvent ensuite être déployées et gérées à l’aide d’Intune. Les applications métier développées par votre organisation doivent être publiées sur Play for Work à l’aide de la console de publication d’applications Android de Google. Les applications métier doivent être configurées dans la console de publication d’applications Android pour restreindre l’accès à votre organisation.

Les applications peuvent être installées sans que l’utilisateur n’intervienne ni n’autorise une **installation provenant de sources inconnues**. Pour rechercher et installer des applications facultatives ou disponibles, l’utilisateur peut parcourir le magasin Play for Work sur son appareil. En savoir plus sur le [déploiement d’applications pour Android for Work](/intune-classic/deploy-use/android-for-work-apps).

## <a name="app-configuration"></a>Configuration de l’application

Android for Work fournit une infrastructure pour le déploiement de valeurs de configuration d’application sur les applications qui les prennent en charge. En spécifiant des valeurs de configuration pour les applications professionnelles, ces valeurs sont correctement définies quand les utilisateurs lancent l’application pour la première fois. Pour que la configuration des applications soit prise en charge, les développeurs d’applications doivent créer leurs applications Android afin que celles-ci prennent en charge les valeurs de configuration gérées. Si tel est le cas, vous pouvez utiliser Intune pour spécifier et appliquer ces paramètres de configuration. En savoir plus sur les [paramètres de configuration d’application Android for Work](afw-app-configuration-policy.md).

## <a name="email-configuration"></a>Configuration de la messagerie

Android for Work ne fournit pas d’application de messagerie par défaut ou d’objet de profil de messagerie natif comme celui fourni par iOS. Par contre, vous pouvez définir les configurations de messagerie en appliquant les paramètres de configuration d’application aux applications de messagerie qui les prennent en charge. Gmail et Nine Work sont deux applications clientes Exchange ActiveSync (EAS) dans le Play Store qui prennent en charge la configuration avec la configuration d’applications Android for Work.

Intune fournit des modèles de configuration pour les applications Gmail et Nine Work gérées en tant qu’applications de travail. Les autres applications de messagerie qui prennent en charge les profils de configuration d’application peuvent être configurées avec des stratégies de configuration d’application mobile.

Si vous utilisez un accès conditionnel Exchange ActiveSync pour des appareils Android for Work, vous devez utiliser l’application de messagerie Gmail ou Nine Work. L’application Microsoft Outlook pour Android, ou toute autre application de messagerie qui utilise l’authentification moderne par le biais d’ADAL, est également prise en charge. En savoir plus sur les [profils de messagerie pour l’e-mail d’entreprise](configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune.md).

## <a name="app-protection-policies"></a>Stratégies de protection des applications

Les stratégies de protection des applications sont entièrement prises en charge dans le profil de travail du profil personnel. Vous pouvez publier des applications métier dans la console de publication d’applications Android à l’adresse https://play.google.com/apps/publish. Cette console inclut une option permettant de réserver les applications à votre organisation. Explorez les [paramètres de stratégie de conformité d’Android for Work](afw-compliance-policy-settings-in-microsoft-intune.md). Pour obtenir des informations générales sur les stratégies de protection des applications, consultez [Stratégies d’application](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md).

## <a name="vpn-profiles"></a>Profils VPN

La prise en charge VPN est similaire à celle des profils VPN Android. Les mêmes fournisseurs de VPN et les mêmes options de configuration de base sont disponibles pour la gestion Android for Work à deux différences près :

-  **VPN limité au profil professionnel** : les connexions VPN sont limitées aux applications déployées sur le profil professionnel. Seules les applications gérées par Android for Work peuvent utiliser la connexion VPN. Les applications personnelles sur l’appareil ne peuvent pas utiliser de connexion VPN gérée.

-  **VPN propre à l’application** : si un fournisseur VPN prend en charge la configuration d’une connexion VPN propre à l’application et permet de configurer une connexion VPN par application via le profil de configuration d’application Android for Work, la connexion VPN propre à l’application peut être configurée dans Intune. Vérifiez auprès du fournisseur VPN s’il prend en charge cette fonctionnalité. En savoir plus sur les [profils de connexion VPN](vpn-connections-in-microsoft-intune.md).

## <a name="certificate-profiles"></a>Profils de certificat

Les options de configuration de profil de certificat qui sont disponibles pour la gestion Android sont également disponibles sur les appareils Android for Work. Android for Work fournit des API de gestion de certificats avancée. La gestion de certificats avancée offre les fonctionnalités suivantes :

- Elle garantit que le déploiement des certificats s’effectue sans assistance et de façon transparente vis-à-vis de l’utilisateur.
-  Elle garantit que les certificats déployés sont entièrement supprimés quand un appareil est mis hors service dans Intune et que le profil professionnel est supprimé.
-  Elle fournit une messagerie améliorée qui informe les utilisateurs que le certificat a été déployé et configuré par leur service informatique par le biais de leur service de gestion.

En savoir plus sur les [profils de certificats](secure-resource-access-with-certificate-profiles.md).

## <a name="wi-fi-profiles"></a>Profils Wi-Fi

Les profils Wi-Fi gérés par Android for Work sont supprimés quand l’appareil est mis hors service dans Intune et que le profil professionnel est supprimé. En savoir plus sur les [profils Wi-Fi](wi-fi-connections-in-microsoft-intune.md).

## <a name="next-steps"></a>Étapes suivantes
[Activation de l’inscription des appareils Android for Work](/intune-classic/deploy-use/set-up-android-for-work)

[Déploiement d’applications pour Android for Work](/intune-classic/deploy-use/android-for-work-apps)
