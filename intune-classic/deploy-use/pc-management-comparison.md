---
title: Comparer les options de gestion des PC Windows
description: "Inscrire des appareils iOS d’entreprise à l’aide du programme d’inscription des appareils Apple ou d’Apple Configurator"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 05/11/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 068a73bb-e6b3-44a6-8f6e-4cf7d455bbf3
ms.reviewer: owenyen
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 560ce922fa58e759157358c6b7348fe0388ce408
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/01/2017
---
# <a name="compare-managing-windows-pcs-as-computers-or-mobile-devices"></a>Comparer la gestion des PC Windows en tant qu’ordinateurs ou appareils mobiles

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Les organisations peuvent utiliser Microsoft Intune pour gérer les PC Windows en tant qu’appareils mobiles avec la gestion des appareils mobiles (MDM) ou en tant qu’ordinateurs avec le logiciel client Intune.  Microsoft recommande l’utilisation de la solution MDM dans la mesure du possible. Toutefois, pour vous aider à mieux comprendre les différences entre ces options, le tableau suivant compare les deux options de gestion.

|**Fonctionnalité/Scénario** |**Windows en tant qu’ordinateur**<br>Client logiciel Intune | **Windows en tant qu’appareil mobile**<br>GESTION DES APPAREILS MOBILES |
|--------------|-------------------------------|-------------------------------|
|**Systèmes d’exploitation** |Windows 10, Windows 8+, Windows 7, Windows Vista | Windows 10+ |
|**Prise en charge du portail Intune** |[Console Silverlight](https://manage.microsoft.com)|[Portail Azure](https://portal.azure.com) |
|**Accès conditionnel**|Non disponible|Disponible <br>[Qu’est-ce que l’accès conditionnel ?](https://docs.microsoft.com/intune-azure/conditional-access/what-is-conditional-access)|
|**Inscription en bloc**|Non disponible|Disponible <br>[Inscription en bloc des appareils Windows](https://docs.microsoft.com/intune-azure/enroll-devices/bulk-enroll-windows)|
|**Profils d’appareils**|Non disponible|Disponible <br>[Que sont les profils d’appareil Microsoft Intune ?](https://docs.microsoft.com/intune-azure/configure-devices/what-are-device-profiles)|
|**Inscription sans agent**|Non disponible |Disponible<br>[Inscrire des appareils Windows](https://docs.microsoft.com/intune-azure/enroll-devices/enroll-windows-devices)|
|**Gestion des mises à jour logicielles**| Mises à jour Windows et mises à jour des applications Microsoft<br>[Maintenir des PC Windows à jour avec les mises à jour logicielles](https://docs.microsoft.com/intune/deploy-use/keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune)|Microsoft Store pour Entreprises pour les mises à jour des applications Windows 10 et Microsoft<br> [Configurer les paramètres Windows Update Entreprise](https://docs.microsoft.com/intune-azure/configure-devices/how-to-configure-windows-update-for-business) |
|**Gestion des licences logicielles**|Disponible <br>[Gérer les contrats de licence des logiciels de PC Windows](https://docs.microsoft.com/intune/deploy-use/manage-license-agreements-for-windows-pc-software-in-microsoft-intune)|Microsoft Store pour Entreprises (applications .appx uniquement)<br>[Gestion des applications achetées dans Windows Store pour Entreprises](https://docs.microsoft.com/intune-azure/manage-apps/wsfb-apps)|
|**Inventaire**|Disponible <br>[Afficher l’inventaire logiciel et matériel pour les PC Windows](https://docs.microsoft.com/intune/deploy-use/view-hardware-and-software-inventory-for-windows-pcs-in-microsoft-intune)|Disponible <br>[Comment surveiller les informations d’applications](https://docs.microsoft.com/intune/apps-monitor)<br>[Qu’est-ce que la gestion des appareils](https://docs.microsoft.com/intune/device-management)|
|**Stratégie de Pare-feu Windows**|Disponible <br>[Protéger les PC Windows à l’aide de stratégies de Pare-feu Windows](https://docs.microsoft.com/intune/deploy-use/help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune) |Non disponible|
|**Protection contre les programmes malveillants**|Endpoint Protection<br>[Contribuer à la sécurisation des PC Windows avec Endpoint Protection](https://docs.microsoft.com/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)|Windows Defender<br>[Paramètres de Windows Defender](https://docs.microsoft.com/intune-azure/configure-devices/custom-for-windows-10#windows-defender-settings)|
|**Assistance à distance** |TeamViewer<br>[Demander et fournir une assistance à distance pour les PC Windows](https://docs.microsoft.com/intune/deploy-use/request-and-provide-remote-assistance-for-windows-pcs-in-microsoft-intune)|Non disponible |
|**Déploiement d'applications** | Non disponible pour Microsoft Store pour Entreprises,<br>.exe, .appx, et .msi incluant plusieurs fichiers uniquement<br>[Ajouter des applications pour les PC Windows exécutant le logiciel client Intune](https://docs.microsoft.com/intune/deploy-use/add-apps-for-windows-pcs-in-microsoft-intune)|Disponible pour les applications du Microsoft Store et les applications métier<br>[Guide pratique d’ajout d’applications du Windows Store](https://docs.microsoft.com/intune-azure/manage-apps/windows-store-app)<br>Déploiement d’applications Microsoft et Win32 disponible prochainement |
|**Protection d’applications**|Non disponible|Disponible <br>[Que sont les stratégies de protection des applications ?](https://docs.microsoft.com/intune-azure/manage-apps/what-is-app-protection-policy)|


### <a name="advantages-of-mdm-windows-pc-management"></a>Avantages de la gestion des PC Windows avec gestion des appareils mobiles (MDM)
La gestion des PC Windows avec la gestion des appareils mobiles moderne présente les avantages suivants :
- **Scalabilité** : la gestion MDM évolue avec la gestion cloud Intune. Le logiciel client Intune est limité à 7 000 PC.
- **Simplicité** : utilise les fonctionnalités de gestion modernes incluses dans le système d’exploitation sans se baser sur un client logiciel téléchargé
- **Cohérence** : vos PC Windows sont gérés comme tous les autres appareils mobiles de votre organisation
<!-- - **Cloud optimization** - -->
