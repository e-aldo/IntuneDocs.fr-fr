---
title: "Intégration d’Intune avec les services cloud Microsoft | Microsoft Intune"
description: "Intégration d’Intune avec les produits et services cloud Microsoft et d’autres produits Microsoft"
keywords: 
author: barlanmsft
manager: angrobe
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 49675811-08a3-408f-810b-89552ff404bd
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 6d1c7c670341692d4ea0c823e4a9a96746b83067
ms.openlocfilehash: 83020d347a4bc036778d830f5189e68e7f8d85da


---

# Intégration d’Intune avec les produits et services cloud Microsoft

Avant de configurer [!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)], consultez cette rubrique et les autres conditions requises répertoriées dans [Informations à connaître avant de commencer à utiliser Microsoft Intune](what-to-know-before-you-start-microsoft-intune.md).
##Intégration dans d'autres services cloud Microsoft


[!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] partage une base commune avec d'autres services cloud Microsoft. Lorsque vous utilisez le même compte pour vous abonner à plusieurs services cloud, ces services utilisent la même infrastructure Microsoft Azure AD et sont clients d'Azure AD. Azure AD fournit les principales capacités d'annuaires et de gestion des identités pour les services cloud Microsoft.

En savoir plus sur l’[administration d’Azure AD](http://technet.microsoft.com/library/hh967611.aspx) dans la bibliothèque TechNet.

## Intégration dans d'autres produits Microsoft
Vous pouvez utiliser [!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)] en tant que service cloud autonome ou en tant que service cloud intégré à d'autres produits. Actuellement, seul [!INCLUDE[cmshort](../includes/cmshort_md.md)] peut s'intégrer directement dans [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].

La décision d'intégrer [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] avec [!INCLUDE[cmshort](../includes/cmshort_md.md)] est un choix définitif qui vous oblige à définir l'autorité de gestion des appareils mobiles à partir de la console [!INCLUDE[cmshort](../includes/cmshort_md.md)] et non depuis le [!INCLUDE[wit_icp_1](../includes/wit_icp_1_md.md)]. Une fois que l'autorité de gestion des appareils mobiles est définie, vous ne pouvez pas modifier ni inverser cette configuration.

Quand vous utilisez [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] avec [!INCLUDE[cmshort](../includes/cmshort_md.md)], vous n’utilisez pas la [!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)] pour gérer [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)], mais plutôt la console [!INCLUDE[cmshort](../includes/cmshort_md.md)]. [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] utilise quand même son stockage cloud dans Azure pour héberger les logiciels que vous déployez sur les appareils que vous gérez avec [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].

Pour plus d’informations, consultez [Gérer les appareils mobiles avec Configuration Manager et Microsoft Intune](http://msdn.microsoft.com/library/2c6bd0e5-d436-41c8-bf38-30152d76be10) dans la documentation de [!INCLUDE[cm5short](../includes/cm5short_md.md)] SP1.

### Voir aussi
[Informations à connaître avant de commencer à utiliser Microsoft Intune](what-to-know-before-you-start-microsoft-intune.md)



<!--HONumber=Aug16_HO4-->


