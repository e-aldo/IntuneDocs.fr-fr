---
title: "Introduction à Intune dans la version préliminaire du portail Azure | Version préliminaire d’Intune Azure | Microsoft Docs"
description: "Version préliminaire d&quot;Intune Azure : apprendre les bases sur Intune dans la version préliminaire du portail Azure et la façon dont il peut vous aider à gérer vos appareils."
keywords: 
author: robstackmsft
ms.author: robstack
nmanager: angrobe
ms.date: 01/08/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4a085264-232a-4af0-97f1-747496c44517
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 1024d2a33d843c628ffbb68f7b01a5d511191e7e
ms.openlocfilehash: f7f6dd79531d8d69eda3ed80bbb1cddf2692ab81


---


# <a name="introduction-to-microsoft-intune-in-the-azure-portal-preview"></a>Introduction à Microsoft Intune dans la version préliminaire du portail Azure


[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Microsoft Intune migre vers le portail Azure, et cela signifie que les flux de travail et fonctionnalités que vous utilisiez vont changer.
Le nouveau portail vous offre un aperçu des fonctionnalités nouvelles et mises à jour dans le portail Azure, où vous pouvez gérer les appareils mobiles, PC et applications de votre entreprise.
Toutes les fonctionnalités Intune finiront par être migrées vers Azure, mais vous pouvez effectuer certaines tâches Intune dans le portail Azure dès aujourd'hui. Étant donné que cette nouvelle expérience est disponible en version préliminaire, certaines fonctionnalités ne sont peut-être pas encore présentes dans le portail. Consultez la section [Nouveautés de la version préliminaire](#what's-new-in-the-preview) pour plus d’informations.

> [!IMPORTANT]
> **Vous ne voyez pas encore le nouveau portail ?**<br>
> Nous avons déjà commencé à déployer la version préliminaire pour certains clients. Les clients existants seront migrés vers la nouvelle expérience à compter du début de l’année civile 2017. Vous recevrez une notification dans le centre de messages Office avant la migration de votre client. Si vous avez des questions concernant la chronologie de la migration de votre client, contactez notre équipe de migration à l’adresse suivante : [intunegrps@microsoft.com](mailto:intunegrps@microsoft.com).


Vous trouverez la documentation du nouveau produit dans cette bibliothèque, et elle sera continuellement mise à jour pendant le développement de la version préliminaire. Si vous avez des suggestions, n’hésitez pas à laisser des commentaires dans la section dédiée de la rubrique. Nous sommes à votre écoute.

<!--- You can view the new Intune technical preview console in Azure at [portal.azure.com]. --->

Points clés de la nouvelle expérience :

- Une console intégrée pour tous vos composants Enterprise Mobility + Security (EMS)
- Une console HTML basée sur les normes web
- Prise en charge de l’API Microsoft Graph pour automatiser de nombreuses actions
- Groupes Azure AD pour assurer la compatibilité dans toutes vos applications Azure
- Prise en charge des navigateurs web les plus récents

Si vous recherchez une documentation pour la console Intune classique, consultez la [Bibliothèque de documentation pour Intune](https://docs.microsoft.com/en-us/intune/).

## <a name="before-you-start"></a>Avant de commencer

Pour utiliser Intune dans le portail Azure, vous devez disposer d’un compte d’administration et d’un compte client Intune. Vous pouvez créer un compte [ici](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0%20).

## <a name="supported-web-browsers-for-the-azure-portal"></a>Navigateurs web pris en charge pour le portail Azure

Le portail Azure s’exécute sur la plupart des PC, Mac et tablettes. Les téléphones mobiles ne sont pas pris en charge.
Actuellement, les navigateurs suivants sont pris en charge :

- Microsoft Edge (dernière version)
- Microsoft Internet Explorer 11
- Safari (dernière version, Mac uniquement)
- Chrome (dernière version)
- Firefox (dernière version)

Pour obtenir les informations les plus récentes sur les navigateurs pris en charge, consultez [cette page](https://docs.microsoft.com/azure/azure-preview-portal-supported-browsers-devices).

## <a name="whats-in-this-library"></a>Que contient cette bibliothèque ?

La documentation reflète la disposition du portail Intune faciliter la recherche des informations dont vous avez besoin.

![Charges de travail sur le portail Azure](./media/azure-portal-workloads.png)

<!--- ### Plan and design
Information to help you plan and design your Intune environment.
[Read more](/intune-azure/plan-and-design/get-started) --->
### <a name="enroll-devices"></a>Inscrire des appareils
Guide pratique d’affectation de la gestion de vos appareils à Intune.
[En savoir plus](/intune-azure/enroll-devices/what-is)
### <a name="devices--groups"></a>Appareils et groupes
Découvrez les appareils que vous gérez avec un inventaire et des rapports.
[En savoir plus](/intune-azure/manage-devices/what-is)
### <a name="manage-users"></a>Gérer des utilisateurs
Découvrez-en davantage sur les utilisateurs des appareils que vous gérez.
[En savoir plus](/intune-azure/manage-users/what-is)
### <a name="manage-apps"></a>Gérer des applications
Contient des informations sur la façon de publier, gérer, configurer et protéger les applications.
[En savoir plus](/intune-azure/manage-apps/what-is-app-management)
### <a name="configure-devices"></a>Configurer des appareils
Contient des informations sur les profils que vous pouvez utiliser pour configurer les paramètres et fonctionnalités sur les appareils que vous gérez.
[En savoir plus](/intune-azure/configure-devices/what-are-device-profiles)
### <a name="set-device-compliance"></a>Définir la conformité des appareils
Définissez un niveau de conformité pour vos appareils, puis créez un rapport sur tous les appareils qui ne sont pas conformes. [En savoir plus](/intune-azure/set-device-compliance/what-is-device-compliance)
### <a name="conditional-access"></a>Accès conditionnel
Restreignez l’accès aux services Exchange en fonction des conditions que vous spécifiez.
[En savoir plus](/intune-azure/conditional-access/what-is-conditional-access)
### <a name="access-control"></a>Contrôle d'accès
Contrôlez les utilisateurs pouvant effectuer diverses actions Intune, et à qui ces actions s’appliquent. Vous pouvez utiliser les rôles intégrés, qui couvrent des scénarios courants dans Intune, ou vous pouvez créer vos propres rôles.
[En savoir plus](/intune-azure/access-control/role-based-access-control)


## <a name="whats-new"></a>Nouveautés

[Découvrez les nouveautés de la version préliminaire](/intune-azure/introduction/whats-new).


<!--HONumber=Feb17_HO1-->


