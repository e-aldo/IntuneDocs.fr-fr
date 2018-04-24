---
title: Gérer les applications du Microsoft Store pour Entreprises
description: Connecter Microsoft Intune au Microsoft Store pour Entreprises pour gérer et déployer des applications achetées en volume à partir de la console Intune
keywords: ''
author: mattbriggs
ms.author: mabrigg
manager: dougeby
ms.date: 02/02/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 8e38d47d-0c5e-40ce-b379-29d3657f5c28
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: coryfe
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: b32f9c6be910156c26b446b7bf70a7975b4afaff
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2018
---
# <a name="manage-apps-you-purchased-from-the-microsoft-store-for-business-with-microsoft-intune"></a>Gérer les applications que vous avez achetées dans le Microsoft Store pour Entreprises avec Microsoft Intune

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Le [Microsoft Store pour Entreprises](https://www.microsoft.com/business-store) propose un emplacement dans lequel vous pouvez trouver et acheter des applications pour votre organisation, individuellement ou en volume. En connectant le Store à Microsoft Intune, vous pouvez gérer les applications achetées en volume depuis la console Intune. Par exemple :
* Vous pouvez synchroniser la liste des applications que vous avez achetées dans le Store avec Intune.
* Les applications qui sont synchronisées apparaissent dans la console d’administration Intune et vous pouvez les déployer comme toute autre application.
* Vous pouvez effectuer un suivi du nombre de licences disponibles et de la quantité de licences utilisée dans la console d’administration Intune.
* Intune bloque le déploiement et l’installation des applications s’il n’y a pas suffisamment de licences disponibles.

## <a name="before-you-start"></a>Avant de commencer
Passez en revue les informations suivantes avant de commencer la synchronisation et le déploiement des applications à partir du Microsoft Store pour Entreprises :
* Vous devez configurer Intune comme autorité de gestion des appareils mobiles pour votre organisation. Pour plus d’informations, consultez [Prérequis pour l’inscription d’appareils dans Microsoft Intune](prerequisites-for-enrollment.md).
* Vous devez disposer d’un compte Microsoft Store pour Entreprises.
* Une fois que vous avez associé un compte Windows Business Store avec Intune, vous ne pouvez pas basculer sur un autre compte ultérieurement.
* Les applications achetées depuis le Store ne peuvent pas être manuellement ajoutées ou supprimées d’Intune. Elles peuvent uniquement être synchronisées avec le Microsoft Store pour Entreprises.
* Intune synchronise uniquement les applications sous licence en ligne que vous avez achetées dans le Microsoft Store pour Entreprises.
* Les appareils doivent être joints à des services de domaine Active Directory ou à un espace de travail pour pouvoir utiliser cette fonctionnalité.
* Les appareils inscrits doivent utiliser la version 1511 de Windows 10.

## <a name="associate-your-microsoft-store-for-business-account-with-intune"></a>Associer votre compte Microsoft Store pour Entreprises à Intune
Avant d’activer la synchronisation dans la console Intune, vous devez configurer votre compte de Store pour utiliser Intune comme outil de gestion :
1. Veillez à vous connecter à Business Store avec le compte de locataire que vous utilisez pour accéder à Intune.
2. Dans Business Store, choisissez **Paramètres** > **Outils de gestion**.
3. Sur la page Outils de gestion, choisissez **Ajouter un outil de gestion**, puis sélectionnez **Microsoft Intune**.

> [!NOTE]
> Si vous utilisez plusieurs outils de gestion pour déployer des applications Microsoft Store pour Entreprises, vous ne pouviez auparavant en associer qu’un au Microsoft Store pour Entreprises. Désormais, vous pouvez associer plusieurs outils de gestion au Windows Store, par exemple, Intune et Configuration Manager.

Vous pouvez maintenant continuer et configurer la synchronisation dans la console Intune.

## <a name="configure-synchronization"></a>Configuration de la synchronisation

1. Dans la [console d’administration Microsoft Intune](https://manage.microsoft.com), choisissez **Administration**
2. Dans l’espace de travail **Administration**, développez l’option **Gestion des appareils mobiles** > **Windows**, puis cliquez sur **Store Pro**.
3. Dans la page **Microsoft Store pour Entreprises**,effectuez les étapes suivantes :
   * Si vous ne l’avez pas déjà fait, cliquez sur le lien pour vous inscrire au Microsoft Store pour Entreprises.
   * Une fois l’inscription effectuée, cliquez sur **Configurer la synchronisation**.
4. Dans la boîte de dialogue **Configurer la synchronisation des applications du Microsoft Store pour Entreprises**, sélectionnez **Activer la synchronisation du Microsoft Store pour Entreprises**.
5. Dans la liste déroulante **Langue**, choisissez la langue dans laquelle les applications du Microsoft Store pour Entreprises s’affichent dans la console Intune. Quelle que soit la langue dans laquelle elles sont affichées, elles seront installées dans la langue de l’utilisateur final lorsqu’elles sont disponibles.
6. Cliquez sur **OK**.

## <a name="synchronize-apps"></a>Synchroniser les applications

1. Dans la page **Microsoft Store pour Entreprises**, cliquez sur **Synchroniser maintenant** pour synchroniser les applications que vous avez achetées sur le Microsoft Store avec Intune.
2. Dans l’espace de travail **Applications**, sélectionnez **Applications** > **Applications achetées en volume** pour afficher les applications que vous pouvez déployer et vérifier que vos applications achetées ont bien été importées. Les applications de ce nœud s’affichent avec le nombre total de licences que vous possédez, ainsi que le nombre de licences disponibles.
Par exemple, vous pouvez acheter l’application Portail d’entreprise (sous licence en ligne) dans le Microsoft Store pour Entreprises, la synchroniser dans la console Intune, puis la déployer comme une application obligatoire sur les appareils Windows 10 nécessaires. 


## <a name="deploy-apps"></a>Déployer des applications

Vous déployez des applications à partir du Store de la même façon que vous déploieriez toute autre application Intune. Pour plus d’informations, consultez [Déployer des applications dans Microsoft Intune](deploy-apps-in-microsoft-intune.md).
Quand vous déployez une application Microsoft Store pour Entreprises, une licence est utilisée par chaque utilisateur qui installe l’application. Si vous utilisez toutes les licences disponibles pour une application déployée, vous ne pourrez plus déployer d’autres copies. Vous devrez prendre l’une des actions suivantes :
* Désinstallez l’application de certains appareils.
* Réduisez la portée du déploiement actuel pour cibler uniquement les utilisateurs pour lesquels vous avez suffisamment de licences.
* Achetez plus de copies de l’application dans le Microsoft Store pour Entreprises.

> [!Important]
> Les applications déployées sont uniquement disponibles pour l’utilisateur qui a inscrit l’appareil à l’origine. Aucun autre utilisateur ne peut accéder à l’application.


### <a name="see-also"></a>Voir aussi
[Ajouter des applications pour des appareils mobiles dans Microsoft Intune](add-apps-for-mobile-devices-in-microsoft-intune.md)
