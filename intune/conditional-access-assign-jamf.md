---
title: "Appliquer des stratégies de conformité aux appareils gérés par Jamf"
titlesuffix: Azure portal
description: "Utilisez la conformité pour sécuriser les appareils gérés par Jamf."
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 11/14/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c87fd2bd-7f53-4f1b-b985-c34f2d85a7bc
ms.reviewer: elocholi
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6184552ce901ffc062f0453f169ec992049ae69b
ms.sourcegitcommit: 82088d297eef629e3da6011681ead442ae7e25f7
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/15/2017
---
# <a name="enforce-compliance-on-macs-managed-with-jamf-pro"></a>Appliquer la conformité sur les Mac gérés par Jamf Pro

|S’applique à : Intune dans le portail Azure |
|--|
|Vous recherchez de la documentation sur Intune dans le portail Classic ? [Cliquez ici](/intune/introduction-intune?toc=/intune-classic/toc.json).|
| |

|Actuellement en préversion privée|
|--|
|Les fonctionnalités décrites dans cette rubrique ne sont accessibles qu’aux clients qui utilisent la préversion privée. Ce message sera supprimé une fois qu’elle sera commercialisée pour tous les clients.|
| |

Vous pouvez utiliser Azure Active Directory et les stratégies d’accès conditionnel de Microsoft Intune. Assurez-vous que vos utilisateurs finaux respectent les exigences de l’organisation. Vous pouvez appliquer ces stratégies à des Mac [gérés par Jamf Pro](conditional-access-integrate-jamf.md). Cela nécessite à la fois un accès aux consoles Intune et Jamf Pro.

## <a name="set-up-device-compliance-policies-in-intune"></a>Configuration des stratégies de conformité d’appareils dans Intune

1. Ouvrez Microsoft Azure, puis accédez à **Intune** > **Conformité de l’appareil** > **Stratégies**. Vous pouvez créer des stratégies pour macOS, y compris sélectionner une série d’actions (par exemple, l’envoi d’avertissements par e-mail) aux utilisateurs et groupes non conformes.
2. Recherchez les groupes désirés et appliquez-leur les stratégies.

## <a name="require-the-company-portal-app-for-macos"></a>Déployer l'application Portail d'entreprise pour macOS

1. Sur un appareil macOS, accédez à https://aka.ms/macoscompanyportal pour télécharger la version actuelle de l’application Portail d’entreprise pour macOS.
2. Ouvrez Jamf Pro, puis accédez à **Gestion de l’ordinateur** > **Packages**.
3. Créez un package avec l’application Portail d’entreprise pour macOS, puis cliquez sur **Enregistrer**.
4. Ouvrez **Ordinateurs** > **Stratégies**, puis sélectionnez **Nouveau**.
5. Utilisez la charge utile **Général** pour configurer les paramètres de la stratégie, notamment la fréquence de déclenchement et d’exécution.
6. Sélectionnez la charge utile **Packages** et cliquez sur **Configurer**.
7. Cliquez sur **Ajouter** pour sélectionner le package avec l’application Portail d’entreprise.
8. Choisissez l’option **Installer** dans le menu contextuel **Action**.
9. Configurez les paramètres pour le package.
10. Cliquez sur l’onglet **Étendue** pour spécifier les ordinateurs sur lesquels l’application Portail d’entreprise doit être installée. Cliquez sur **Enregistrer**. La stratégie sera appliquée aux appareils inclus dans l’étendue la prochaine fois que le déclencheur sélectionné sera exécuté sur l’ordinateur et qu’il répondra aux critères définis dans la charge utile **Général**.

## <a name="direct-your-users-to-register-jamf-pro-managed-devices-with-azure-active-directory"></a>Aider vos utilisateurs à inscrire leurs appareils gérés par Jamf Pro auprès d’Azure Active Directory

> [!NOTE]
> Vous devez [déployer le portail d’entreprise](conditional-access-assign-jamf.md#require-the-company-portal-app-for-macos) pour macOS avant de passer aux étapes suivantes.  

Les utilisateurs finaux doivent lancer l’application Portail d’entreprise via le libre-service Jamf pour inscrire l’appareil auprès d’Azure AD en tant qu’appareil géré par Jamf Pro.

1. Dans Jamf Pro, accédez à **Ordinateurs** > **Stratégies** et créez une stratégie pour l’inscription d’appareils.
2. Configurez la charge utile **Accès conditionnel**, notamment la fréquence de déclenchement et d’exécution. Définissez la priorité sur **Après**.
3. Cliquez sur l’onglet **Étendue** et incluez tous les appareils ciblés dans l’étendue de la stratégie.
4. Cliquez sur l’onglet **Libre-service** pour rendre la stratégie disponible dans le libre-service Jamf. Incluez la stratégie dans la catégorie **Conformité de l'appareil**. Cliquez sur **Enregistrer**.
