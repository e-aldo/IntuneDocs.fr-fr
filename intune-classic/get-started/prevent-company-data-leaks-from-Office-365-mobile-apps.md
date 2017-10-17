---
title: "Éviter les fuites de données d’entreprise à partir d’applications mobiles Office 365"
description: "Utilisez Intune pour sécuriser les données de votre organisation avec des stratégies de gestion des applications mobiles (GAM) qui permettent d’éviter les fuites de données d’entreprise à partir d’applications mobiles Office 365 ou autres applications métier."
keywords: 
author: jeffgilb
ms.author: jeffgilb
manager: angrobe
ms.date: 11/22/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 19be3de7-539c-49f5-8c46-5363b987fef9
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: pchacon
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 40356d01be1d436e2a7fc0598ebac0d25749a49a
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/10/2017
---
# <a name="quick-start-guide-prevent-company-data-leaks-from-office-365-mobile-apps"></a>Guide de démarrage rapide : Éviter les fuites de données d’entreprise à partir d’applications mobiles Office 365

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Microsoft Intune peut vous aider à sécuriser les données de votre organisation à l’aide de stratégies de gestion des applications mobiles (GAM) qui permettent d’éviter les fuites de données d’entreprise à partir d’applications mobiles Office 365 ou autres applications métier. Les stratégies GAM Intune peuvent être utilisées sans que les utilisateurs n’aient à inscrire leurs appareils auprès de la gestion des appareils mobiles (MDM) Intune. Ainsi, si vous avez des utilisateurs qui ne souhaitent pas inscrire leurs appareils mobiles BYOD ou Android auprès d’une solution MDM Microsoft (Intune, Configuration Manager ou EAS), si vous souhaitez protéger les données de l’entreprise sans gérer les appareils des utilisateurs finaux ou si vous utilisez déjà une solution MDM non-Microsoft, Intune peut vous aider à optimiser la sécurité des données de votre société.   

## <a name="is-this-quick-start-guide-right-for-me"></a>Ce Guide de démarrage rapide est-il fait pour moi ?
Vous voulez autoriser les utilisateurs finaux à accéder à vos données Office 365 et à vos applications métier depuis leurs appareils iOS et Android sans exiger l’inscription de ces appareils auprès d’une solution de gestion des appareils mobiles (MDM) tout en continuant de contrôler ce qu’ils peuvent ou ne peuvent pas faire avec les données, notamment les copier et les coller dans des applications personnelles ?

Si c’est le cas, Microsoft Intune vous permet de définir des stratégies GAM pour les applications mobiles Office 365 sur iOS et Android, notamment des restrictions des fonctions couper/copier/coller, la désactivation de la fonction Enregistrer sous, la définition de l’obligation d’un code PIN et la possibilité de réinitialiser des données protégées par GAM à distance.  Cela protège les données d’entreprise sans obliger les utilisateurs à inscrire leurs appareils auprès d’une solution MDM, tout en conservant une expérience utilisateur de pointe avec les applications mobiles Office.

## <a name="how-do-i-do-it"></a>Comment procéder ?
1.  Apprenez le [fonctionnement de base de la Gestion des applications mobiles (GAM) Intune](/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune).
2.  Découvrez [ce que vous devez faire avant de pouvoir créer des stratégies de gestion des applications mobiles](/intune-classic/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune) dans le portail Azure.
3.  [Créez et déployez des stratégies de gestion des applications mobiles](/intune-classic/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune) avec Intune.

### <a name="additional-information"></a>Informations supplémentaires :
- [Expérience de l’utilisateur final](/intune-classic/deploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune) pour des applications avec la GAM activée.
- [Préparer des applications métier GAM avec Intune](/intune/apps-prepare-mobile-application-management)
- <a href="https://www.microsoft.com/cloud-platform/microsoft-intune-partners" target="_blank">Liste des partenaires Microsoft Intune&rarr;</a> fournissant des applications prenant en charge la gestion des applications mobiles (GAM).

## <a name="what-should-i-do-next"></a>Que dois-je faire ensuite ?
[Migrer d’une solution MDM non-Microsoft vers Microsoft Intune](/intune-classic/deploy-use/migrate-to-intune)

[Inscrire des appareils auprès de MDM Intune](/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)
