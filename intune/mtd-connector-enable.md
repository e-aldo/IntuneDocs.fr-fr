---
title: Activer le connecteur Mobile Threat Defense avec Intune
titlesuffix: Azure portal
description: Activez le connecteur Mobile Threat Defense dans Intune.
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dbb6a37e-ba47-4b69-922c-d25e66c279f6
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d818581ca74e64bf27c968b39969afd889b6fbda
ms.sourcegitcommit: d434dfab7ef7a6c4082d675717fa22d5581b4f51
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/19/2017
---
# <a name="enable-mobile-threat-defense-in-intune"></a>Activer Mobile Threat Defense dans Intune

> [!NOTE] 
> Cette rubrique s’applique à tous les partenaires Mobile Threat Defense.

Pour activer la connexion de protection contre les menaces mobiles (MTD, Mobile Threat Defense) dans Intune, vous devez avoir déjà configuré le connecteur Intune dans la console de partenaire MTD.

## <a name="to-enable-the-mtd-connector"></a>Pour activer le connecteur MTD

1. Accédez au [portail Azure](https://portal.azure.com) et connectez-vous avec vos informations d’identification Intune. Une fois correctement connecté, le **tableau de bord Azure** apparaît.

2. Dans le **tableau de bord Azure**, choisissez **Autres services** dans le menu de gauche, puis tapez **Intune** dans le filtre de zone de texte.

3. Choisissez **Intune**. Le **Tableau de bord Intune** s’ouvre.

4. Dans le **Tableau de bord Intune**, choisissez **Conformité des appareils**, puis **Protection contre les menaces mobiles** sous la section **Configuration**.

5. Dans le panneau **Protection contre les menaces mobiles**, choisissez **Ajouter**.

6. Choisissez votre solution MTD comme **connecteur Mobile Threat Defense à configurer** dans la liste déroulante.

    ![Configuration de MTD dans le portail Intune Azure](./media/enable-mtd-connector-1.png)

7. Modifiez les options en fonction des besoins de votre organisation.

## <a name="mtd-toggle-options"></a>Options MTD

Vous pouvez décider des options de MTD à activer en fonction des besoins de votre organisation. Voici plus de détails :

- **Connecter les appareils Android 4.1+ à [nom du partenaire MTD]** : quand vous activez cette option, les appareils Android 4.1 + peuvent signaler des risques de sécurité à Intune.
    - **Marquer comme non conforme si aucune donnée n’est reçue** : si Intune ne reçoit pas de données sur un appareil sur cette plateforme venant du partenaire MTD, considère l’appareil non conforme.
<br></br>
- **Connecter les appareils iOS 8.0+ à [nom du partenaire MTD]** : quand vous activez cette option, les appareils iOS 8.0+ peuvent signaler des risques de sécurité à Intune.
    - **Marquer comme non conforme si aucune donnée n’est reçue** : si Intune ne reçoit pas de données sur un appareil sur cette plateforme venant du partenaire MTD, considère l’appareil non conforme.
<br></br>
- **Bloquer les versions de système d’exploitation non prises en charge** : bloquez si l’appareil exécute un système d’exploitation inférieur à la valeur de version minimale prise en charge.

- **Nombre de jours avant de considérer le partenaire non réactif** : le nombre de jours d’inactivité avant qu’Intune considère le partenaire non réactif car la connexion est perdue. Intune ignore l’état de conformité pour les partenaires MTD non réactifs.

> [!IMPORTANT] 
> Vous devez ajouter et affecter les applications MTD avant de créer les règles de conformité des appareils et de stratégie d’accès conditionnel. Cela garantit que l’application MTD est prête et mise à la disposition des utilisateurs finaux qui souhaitent l’installer pour pouvoir accéder à leur e-mail ou à d’autres ressources de l’entreprise.

> [!TIP]
> Vous pouvez voir **l’état de la connexion** et l’heure de **dernière synchronisation** entre Intune et le partenaire MTD à partir du panneau Protection contre les menaces mobiles.
