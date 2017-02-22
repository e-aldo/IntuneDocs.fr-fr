---
title: "Gérer les applications à partir du Windows Store pour Entreprises | Version préliminaire d’Intune Azure | Microsoft Docs"
description: "Version préliminaire d&quot;Intune Azure : découvrez comment synchroniser les applications dans Intune depuis Windows Store pour Entreprises, puis les affecter et assurer leur suivi."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/02/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2ed5d3f0-2749-45cd-b6bf-fd8c7c08bc1b
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: a57ac0e6cb29dbfc87bb09c04bb372228a1d72be
ms.openlocfilehash: 2acb58a8fc71ae7f2e0bce127e709a678faa27cb

---

# <a name="how-to-manage-apps-you-purchased-from-the-windows-store-for-business"></a>Guide pratique de gestion des applications que vous avez achetées dans Windows Store pour Entreprises

[!INCLUDE[azure_preview](../includes/azure_preview.md)]


[Windows Store pour Entreprises](https://www.microsoft.com/business-store) propose un lieu dans lequel vous pouvez trouver et acheter des applications pour votre organisation, individuellement ou par lots. En connectant le Windows Store à Microsoft Intune, vous pouvez gérer les applications achetées en volume depuis le portail Intune. Exemple :
* Vous pouvez synchroniser la liste des applications que vous avez achetées dans le magasin avec Intune.
* Les applications qui sont synchronisées apparaissent dans la console d’administration Intune et vous pouvez les affecter comme toute autre application.
* Vous pouvez effectuer un suivi du nombre de licences disponibles et de la quantité de licences utilisée dans la console d’administration Intune.
* Intune bloque le déploiement et l’installation des applications s’il n’y a pas suffisamment de licences disponibles.

## <a name="before-you-start"></a>Avant de commencer
Passez en revue les informations suivantes avant de commencer la synchronisation et le déploiement des applications depuis Windows Store pour Entreprises :
* Vous devez configurer Intune comme autorité de gestion des appareils mobiles pour votre organisation.
* Vous devez avoir créé un compte sur Windows Store pour Entreprises.
* Une fois que vous avez associé un compte Windows Business Store avec Intune, vous ne pouvez pas basculer sur un autre compte ultérieurement.
* Les applications achetées depuis le magasin ne peuvent pas être manuellement ajoutées ou supprimées d’Intune. Elles peuvent uniquement être synchronisées avec Windows Store pour Entreprises.
* Intune synchronise uniquement les applications sous licence en ligne que vous avez achetées auprès de Windows Store pour Entreprises.
* Les appareils doivent être joints à des services de domaine Active Directory ou à un espace de travail pour pouvoir utiliser cette fonctionnalité.
* Les appareils inscrits doivent utiliser la version 1511 de Windows 10 ou version ultérieure.

## <a name="associate-your-windows-store-for-business-account-with-intune"></a>Associer votre compte Windows Store pour Entreprises à Intune
Avant d’activer la synchronisation dans la console Intune, vous devez configurer votre compte de magasin pour utiliser Intune comme outil de gestion :
1. Veillez à vous connecter à Business Store avec le compte de locataire que vous utilisez pour accéder à Intune.
2. Dans Business Store, choisissez **Paramètres** > **Outils de gestion**.
3. Sur la page Outils de gestion, choisissez **Ajouter un outil de gestion**, puis sélectionnez **Microsoft Intune**.

> [!NOTE]
> Si vous utilisez plusieurs outils de gestion pour déployer des applications Windows Store pour Entreprises, vous ne pouviez associer qu’un seul outil au Windows Store pour Entreprises. Désormais, vous pouvez associer plusieurs outils de gestion au Windows Store, par exemple, Intune et Configuration Manager.

Vous pouvez maintenant continuer et configurer la synchronisation dans la console Intune.

## <a name="configure-synchronization"></a>Configuration de la synchronisation

1. Connectez-vous au portail Azure.
2. Choisissez **Plus de services** > **Autres** > **Intune**.
3. Dans le panneau **Intune**, choisissez **Gérer les applications**.
1. Dans le panneau **Mobile Apps**, choisissez **Installation** > **Windows Store pour Entreprises**.
2. Cliquez sur **Activer**.
3. Si vous ne l’avez pas déjà fait, cliquez sur le lien pour vous inscrire à Windows Store pour Entreprises, et associer votre compte comme détaillé précédemment.
5. Dans la liste déroulante **Langue**, choisissez la langue dans laquelle les applications de Windows Store pour Entreprises s’afficheront dans le portail Intune. Quelle que soit la langue dans laquelle elles sont affichées, elles seront installées dans la langue de l’utilisateur final lorsqu’elles sont disponibles.
6. Cliquez sur **Synchroniser** pour récupérer les applications que vous avez achetées dans le Windows Store dans Intune.

## <a name="synchronize-apps"></a>Synchroniser les applications

1. Dans la charge de travail **Gérer les applications**, choisissez **Installation** > **Windows Store pour Entreprises**.
2. Cliquez sur **Synchroniser** pour récupérer les applications que vous avez achetées dans le Windows Store dans Intune.

## <a name="assign-apps"></a>Attribuer des applications

Vous affectez des applications à partir du magasin de la même façon que vous déploieriez toute autre application Intune. Pour plus d’informations, consultez [Guide pratique d’affectation d’applications à des groupes avec Microsoft Intune](deploy-apps.md). Toutefois, au lieu d’affecter les applications à partir de la page **Toutes les applications**, affectez-les à partir de la page **Applications sous licence**.

Lorsque vous affectez une application Windows Store pour Entreprises, une licence est utilisée par chaque utilisateur qui installe l’application. Si vous utilisez toutes les licences disponibles pour une application déployée, vous ne pourrez plus déployer d’autres copies. Vous devrez prendre l’une des actions suivantes :
* Désinstallez l’application de certains appareils.
* Réduisez la portée du déploiement actuel pour cibler uniquement les utilisateurs pour lesquels vous avez suffisamment de licences.
* Achetez plus de copies de l’application dans Windows Store pour Entreprises.

> [!Important]
> Les applications déployées sont uniquement disponibles pour l’utilisateur qui a inscrit l’appareil à l’origine. Aucun autre utilisateur ne peut accéder à l’application.



<!--HONumber=Feb17_HO1-->


