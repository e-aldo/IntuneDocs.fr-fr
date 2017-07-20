---
title: Connecteur Check Point SandBlast Mobile avec Intune
titleSuffix: Intune on Azure
description: "Intégration de Check Point SandBlast à Intune"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 07/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 706a4228-9bdf-41e0-b8d1-64c923dd2d2b
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e722411e7eea11a604cdd2c6f7f818053d0ffbb0
ms.sourcegitcommit: 3b21f20108e2bf1cf47c141b36a7bdae609c4ec3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/10/2017
---
# <a name="check-point-sandblast-mobile-threat-defense-connector-with-intune"></a>Connecteur de protection contre les menaces mobiles Check Point SandBlast Mobile avec Intune

Vous pouvez contrôler l’accès des appareils mobiles aux ressources de l’entreprise à l’aide d’un accès conditionnel basé sur une évaluation des risques effectuée par Check Point SandBlast Mobile, solution de protection contre les menaces mobiles qui s’intègre à Microsoft Intune. Le risque est évalué en fonction des données de télémétrie recueillies par les appareils exécutant l’application Check Point SandBlast Mobile.

Vous pouvez configurer des stratégies d’accès conditionnel basées sur l’évaluation des risques Check Point SandBlast Mobile par le biais des stratégies de conformité d’appareil Intune, que vous pouvez utiliser pour autoriser ou empêcher les appareils non conformes d’accéder aux ressources de l’entreprise en fonction des menaces détectées.

## <a name="how-do-intune-and-check-point-sandblast-mobile-help-protect-your-company-resources"></a>Comment Intune et Check Point SandBlast Mobile vous aident-ils à protéger les ressources de votre entreprise ?

L’application Check Point SandBlast Mobile pour Android et iOS capture le système de fichiers, la pile réseau, les données de télémétrie de l’appareil et des applications quand elles sont disponibles, puis les envoie au service cloud Check Point SandBlast pour évaluer les risques de l’appareil face aux menaces mobiles.

La stratégie de conformité des appareils Intune comprend une règle de protection contre les menaces mobiles Check Point SandBlast Mobile, qui est basée sur l’évaluation des risques Check Point SandBlast. Quand cette règle est activée, Intune évalue si l’appareil est conforme à la stratégie activée. Si l’appareil est détecté non conforme, les utilisateurs sont interdits d’accès aux ressources de l’entreprise comme Exchange Online et SharePoint Online. Les utilisateurs reçoivent aussi des conseils de l’application mobile Check Point SandBlast installée sur leurs appareils pour résoudre le problème et rétablir l’accès aux ressources de l’entreprise.

<!-- ## Sample scenarios

Here are some common scenarios:

### Control access based on threats from malicious apps

When malicious apps such as malware are detected on devices, you can block devices until the threat is resolved:

-   Connecting to corporate e-mail

-   Syncing corporate files with the OneDrive for Work app

-   Accessing company apps

**Block when malicious apps are detected:**

![Check Point MTD block when malicious apps are detected](./media/checkpoint-MTD-2.PNG)

**Access granted on remediation:**

![Check Point MTD access granted](./media/checkpoint-MTD-3.PNG)

### Control access based on threat to network

Detect threats like **Man-in-the-middle** in network, and protect access to Wi-Fi networks based on the device risk.

**Block network access through Wi-Fi:**

![Check Point MTD block network access through Wi-Fi](./media/checkpoint-MTD-4.PNG)

**Access granted on remediation:**

![Check Point MTD Wi-Fi access granted](./media/checkpoint-MTD-5.PNG)

### Control access to SharePoint Online based on threat to network

Detect threats like **Man-in-the-middle** in network, and prevent synchronization of corporate files based on the device risk.

**Block SharePoint Online when network threats are detected:**

![Check Point MTD block SharePoint Online access](./media/checkpoint-MTD-6.PNG)

**Access granted on remediation:**

![Check Point MTD SharePoint Online access granted](./media/checkpoint-MTD-7.PNG)

## Supported platforms

-   **Android 4.1 and later**

-   **iOS 8 and later**

## Pre-requisites

-   Azure Active Directory Premium

-   Microsoft Intune subscription

-   Check Point SandBlast Mobile Threat Defense subscription
    -   See [CheckPoint SandBlast website](https://www.checkpoint.com/) for more information.

## Next steps

[Set up CheckPoint SandBlast Mobile app](mtd-apps-ios-app-configuration-policy-add-assign.md)

[Integrate CheckPoint SandBlast with Intune](checkpoint-sandblast-mobile-mtd-connector-integration.md)

[Enable CheckPoint SandBlast Mobile MTD connector](mtd-connector-enable.md)

[Create CheckPoint SandBlast Mobile device compliance policy](mtd-device-compliance-policy-create.md)
