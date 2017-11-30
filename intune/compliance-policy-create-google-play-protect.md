---
title: "Activer la conformité de Google Play Protect avec Intune"
titleSuffix: Azure portal
description: "Apprenez à créer une stratégie de conformité pour les appareils Android afin d’activer Google Play Protect."
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 11/20/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: E9810BEB-000A-4DFB-B5C7-A22A92082B22
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d610bc338c1bcf81ed3bc71f1357e001914c5877
ms.sourcegitcommit: 71e6e80b7370024624ce2e5fad1ca5b372975748
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-device-compliance-policy-to-enable-google-play-protect"></a>Création d’une stratégie de conformité pour activer Google Play Protect

Vous pouvez créer une stratégie de conformité pour la plateforme Android afin de vérifier la conformité de Google Play Protect (GPP).

La stratégie de conformité nécessitant ces paramètres peut ensuite être ciblée sur un groupe d’utilisateurs ou d’appareils Android. Si ces paramètres ne sont pas activés sur un appareil, celui-ci n’est pas conforme.

## <a name="create-a-compliance-policy"></a>créer une stratégie de conformité

1. Connectez-vous au portail Azure. Choisissez **Autres services** > **Surveillance + Gestion** + **Intune**.
2. Choisissez **Conformité de l’appareil** dans le groupe **Gérer**. 
3. Choisissez **Stratégies**, puis **Créer une stratégie**.
4. Tapez le **Nom** et la **Description** de la stratégie.
5. Sélectionnez **Android** pour la plateforme.
6. Choisissez **Paramètres** > **Intégrité de l’appareil**.
7. Configurez les paramètres **Google Play Protect**.
8. Lorsque vous avez défini les paramètres Google Play Protect, spécifiez les paramètres **Sécurité** et **Propriété de l’appareil**. Une fois que vous avez terminé, choisissez **Enregistrer**.

## <a name="configure-the-google-play-protect-settings"></a>Configurer les paramètres Google Play Protect

 - **Google Play Services est configuré**  
   L’application Google Play Services doit être installée et activée. Google Play Services autorise les mises à jour de sécurité et constitue une dépendance de niveau de base pour de nombreuses fonctionnalités de sécurité sur les appareils Google certifiés.
 - **Fournisseur de sécurité à jour**  
   Un fournisseur de sécurité à jour doit être en mesure de protéger un appareil contre les vulnérabilités connues.
 - **Analyse des menaces sur les applications**  
   La fonctionnalité **Vérifier les applications** Android doit être activée.
    > [!Note]  
    > Sur la plateforme Android héritée, cette fonctionnalité constitue un paramètre de conformité. Intune ne peut que vérifier si ce paramètre est activé au niveau de l’appareil. Sur les appareils avec des profils professionnels, précédemment désignés sous l’appellation Android for Work, ce paramètre correspond à un paramètre de la stratégie de configuration. Ceci permet aux administrateurs d’activer le paramètre pour un appareil.

    Si votre entreprise utilise des profils professionnels Android, vous pouvez activer **Analyse des menaces sur les applications** pour vos appareils inscrits. Établissez un profil d’appareil et demandez le paramètre de sécurité système. Pour plus d’informations, consultez [Paramètres de restriction des appareils Android for Work dans Microsoft Intune](device-restrictions-android-for-work.md).

 - **Attestation d’appareil SafetyNet**  
   Définissez le niveau d’intégrité d’attestation d’appareil SafetyNet qui doit être respecté. Les niveaux incluent **Non configuré**, **Vérifier l’intégrité de base** et **Vérifier l’intégrité de base et les appareils certifiés**.




## <a name="next-steps"></a>Étapes suivantes

Pour en savoir plus sur l’utilisation des stratégies de conformité des appareils Intune, consultez [Bien démarrer avec les stratégies de conformité des appareils Intune](device-compliance-get-started.md).