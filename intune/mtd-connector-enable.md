---
title: Activer le connecteur Mobile Threat Defense dans Microsoft Intune
titlesuffix: Azure portal
description: Activez le connecteur entre votre partenaire Mobile Threat Defense (MTD) et Microsoft Intune.
keywords: 
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 02/27/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dbb6a37e-ba47-4b69-922c-d25e66c279f6
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 28233965fb68ef1b83b07d14d39568b5bd997c89
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/08/2018
---
# <a name="enable-the-mobile-threat-defense-connector-in-intune"></a>Activer le connecteur Mobile Threat Defense dans Intune

> [!NOTE] 
> Cette rubrique s’applique à tous les partenaires Mobile Threat Defense.

Pendant l’installation de Mobile Threat Defense (MTD), vous avez configuré une stratégie de classification des menaces dans votre console de partenaire MTD et avez créé la stratégie de conformité des appareils dans Intune. Si vous avez déjà activé le connecteur Intune dans la console de partenaire MTD, vous pouvez maintenant activer la connexion MTD dans Intune.

## <a name="to-enable-the-mtd-connector"></a>Pour activer le connecteur MTD

1. Accédez au [portail Azure](https://portal.azure.com) et connectez-vous avec vos informations d’identification Intune. Une fois correctement connecté, le **tableau de bord Azure** apparaît.

2. Dans le **tableau de bord Azure**, choisissez **Tous les services** dans le menu de gauche, puis tapez **Intune** dans le filtre de zone de texte.

3. Choisissez **Intune**. Le **tableau de bord Intune** s’ouvre.

4. Dans le **Tableau de bord Intune**, choisissez **Conformité des appareils**, puis **Protection contre les menaces mobiles** sous la section **Configuration**.

5. Dans le volet **Mobile Threat Defense**, choisissez **Ajouter**.

6. Choisissez votre solution MTD comme **connecteur Mobile Threat Defense à configurer** dans la liste déroulante.

    ![Configuration de MTD dans le portail Intune Azure](./media/enable-mtd-connector-1.png)

7. Modifiez les options en fonction des besoins de votre organisation.

## <a name="mtd-toggle-options"></a>Options MTD

Vous pouvez décider des options de MTD à activer en fonction des besoins de votre organisation. Voici plus de détails :

- **Connecter les appareils Android 4.1+ à [nom du partenaire MTD]** : quand vous activez cette option, les appareils Android 4.1 + peuvent signaler des risques de sécurité à Intune.
    - **Marquer comme non conforme si aucune donnée n’est reçue** : Si Intune ne reçoit pas de données du partenaire MTD concernant un appareil sur cette plateforme, l’appareil est considéré comme non conforme.
<br></br>
- **Connecter les appareils iOS 8.0+ à [nom du partenaire MTD]** : quand vous activez cette option, les appareils iOS 8.0+ peuvent signaler des risques de sécurité à Intune.
    - **Marquer comme non conforme si aucune donnée n’est reçue** : Si Intune ne reçoit pas de données du partenaire MTD concernant un appareil sur cette plateforme, l’appareil est considéré comme non conforme.
<br></br>
- **Bloquer les versions de système d’exploitation non prises en charge** : bloquez si l’appareil exécute un système d’exploitation inférieur à la valeur de version minimale prise en charge.

- **Nombre de jours avant de considérer le partenaire non réactif** : le nombre de jours d’inactivité avant qu’Intune considère le partenaire non réactif car la connexion est perdue. Intune ignore l’état de conformité pour les partenaires MTD non réactifs.

> [!IMPORTANT] 
> Vous devez ajouter et affecter les applications MTD avant de créer les règles de conformité des appareils et de stratégie d’accès conditionnel. Cela garantit que l’application MTD est prête et mise à la disposition des utilisateurs finaux qui souhaitent l’installer pour pouvoir accéder à leur e-mail ou à d’autres ressources de l’entreprise.

> [!TIP]
> Vous pouvez voir l’**état de la connexion** et l’heure de la **dernière synchronisation** entre Intune et le partenaire MTD dans le volet Mobile Threat Defense.
