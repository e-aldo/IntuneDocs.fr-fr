---
title: "Introduction à Intune dans la préversion du portail Azure"
titleSuffix: Intune Azure preview
description: "Préversion Intune Azure : Découvrez les bases d’Intune dans la préversion du portail Azure et comment celui-ci peut vous aider à gérer vos appareils."
keywords: 
author: robstackmsft
ms.author: robstack
nmanager: angrobe
ms.date: 03/15/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4a085264-232a-4af0-97f1-747496c44517
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: deea78dcea9ade031441bf12b388a862235a8e9c
ms.openlocfilehash: 13d20cd985dbc22cd6d833fa333f31be809ffae5
ms.lasthandoff: 03/15/2017


---


# <a name="introduction-to-microsoft-intune-in-the-azure-portal-preview"></a>Introduction à Microsoft Intune dans la préversion du portail Azure


[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Microsoft Intune migre vers le portail Azure, et cela signifie que les flux de travail et fonctionnalités que vous utilisiez vont changer.
Le nouveau portail vous offre un aperçu des fonctionnalités nouvelles et mises à jour dans le portail Azure, où vous pouvez gérer les appareils mobiles, PC et applications de votre entreprise.
Toutes les fonctionnalités Intune finiront par être migrées vers Azure, mais vous pouvez effectuer de nombreuses tâches Intune dans le portail Azure dès aujourd’hui. Étant donné que cette nouvelle expérience est disponible en préversion, certaines fonctionnalités ne sont peut-être pas encore présentes dans le portail. Consultez la section [Nouveautés](#what's-new) pour plus d’informations.

> [!IMPORTANT]
> **Vous ne voyez pas encore le nouveau portail ?**<br>
> Nous avons déjà commencé à déployer la préversion pour certains clients. Les clients existants seront migrés vers la nouvelle expérience à compter du début de l’année civile 2017. Vous recevrez une notification dans le centre de messages Office avant la migration de votre client.


Vous trouverez la documentation du nouveau produit dans cette bibliothèque, et elle sera continuellement mise à jour pendant le développement de la préversion. Si vous avez des suggestions, n’hésitez pas à laisser des commentaires dans la section dédiée de la rubrique. Nous sommes à votre écoute.

<!--- You can view the new Intune technical preview console in Azure at [portal.azure.com]. --->

Points clés de la nouvelle expérience :

- Une console intégrée pour tous vos composants Enterprise Mobility + Security (EMS)
- Une console HTML basée sur les normes web
- Prise en charge de l’API Microsoft Graph pour automatiser de nombreuses actions
- Groupes Azure AD (Active Directory) pour assurer la compatibilité dans toutes vos applications Azure
- Prise en charge des navigateurs web les plus récents

Si vous recherchez une documentation pour la console Intune classique, consultez la [bibliothèque de documentation pour Intune](https://docs.microsoft.com/en-us/intune/).

## <a name="before-you-start"></a>Avant de commencer

Pour utiliser Intune dans le portail Azure, vous devez disposer d’un compte d’administration et d’un compte client Intune. [Inscrivez-vous pour obtenir un compte](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0%20) si vous n’en avez pas déjà un.

## <a name="supported-web-browsers-for-the-azure-portal"></a>Navigateurs web pris en charge pour le portail Azure

Le portail Azure s’exécute sur la plupart des PC, Mac et tablettes. Les téléphones mobiles ne sont pas pris en charge.
Actuellement, les navigateurs suivants sont pris en charge :

- Microsoft Edge (dernière version)
- Microsoft Internet Explorer 11
- Safari (dernière version, Mac uniquement)
- Chrome (dernière version)
- Firefox (dernière version)

Pour obtenir les informations les plus récentes sur les navigateurs pris en charge, consultez le [portail Azure](https://docs.microsoft.com/azure/azure-preview-portal-supported-browsers-devices).

## <a name="whats-in-this-library"></a>Que contient cette bibliothèque ?

La documentation reflète la disposition du portail Intune faciliter la recherche des informations dont vous avez besoin.

![Charges de travail sur le portail Azure](./media/azure-portal-workloads.png)

### <a name="introduction-and-get-started"></a>Introduction et prise en main
Cette section contient des informations sur les [nouveautés](/intune-azure/introduction/whats-new), les [problèmes connus](/intune-azure/introduction/known-issues-in-the-intune-preview), [la façon de bénéficier du support](/intune-azure/introduction/how-to-get-support-for-microsoft-intune) et comment [bien démarrer avec un essai gratuit](/intune-azure/introduction/sign-up-free-trial-microsoft-intune) d’Intune.
### <a name="plan-and-design"></a>Planifier et concevoir
Informations pour vous aider à [planifier et concevoir](/intune-azure/plan-and-design/get-started) votre environnement Intune.
### <a name="device-enrollment"></a>Inscription de périphériques
[Apprenez à configurer la gestion de vos appareils par Intune](/intune-azure/enroll-devices/what-is).
### <a name="devices"></a>Périphériques
[Découvrez les appareils que vous gérez avec un inventaire et des rapports](/intune-azure/manage-devices/what-is).
### <a name="manage-users-and-groups"></a>Gérer les utilisateurs et les groupes
[Découvrez-en davantage sur les utilisateurs des appareils que vous gérez et triez les ressources en les regroupant en groupes](/intune-azure/manage-users/what-is).
### <a name="manage-apps"></a>Gérer des applications
[Apprenez à publier, gérer, configurer et protéger les applications](/intune-azure/manage-apps/what-is-app-management).
### <a name="device-configuration"></a>Configuration des appareils
[Apprenez-en davantage sur les profils que vous pouvez utiliser pour configurer les paramètres et fonctionnalités sur les appareils que vous gérez](/intune-azure/configure-devices/what-are-device-profiles).
### <a name="device-compliance"></a>Conformité de l’appareil
[Définissez un niveau de conformité pour vos appareils, puis créez un rapport sur tous les appareils qui ne sont pas conformes](/intune-azure/set-device-compliance/what-is-device-compliance).
### <a name="conditional-access"></a>Accès conditionnel
[Restreignez l’accès aux services Exchange en fonction des conditions que vous spécifiez](/intune-azure/conditional-access/what-is-conditional-access).
### <a name="intune-roles"></a>Rôles Intune
[Contrôlez les utilisateurs pouvant effectuer diverses actions Intune, et à qui ces actions s’appliquent](/intune-azure/access-control/role-based-access-control). Vous pouvez utiliser les rôles intégrés, qui couvrent des scénarios courants dans Intune, ou vous pouvez créer vos propres rôles.



## <a name="whats-new"></a>Nouveautés

[Découvrez les nouveautés de la préversion](/intune-azure/introduction/whats-new).

