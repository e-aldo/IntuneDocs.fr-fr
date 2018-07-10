---
title: Bien démarrer avec les stratégies dans Microsoft Intune - Azure | Microsoft Docs
description: Créez des stratégies pour protéger les données d’entreprise et gérer l’accès aux ressources de l’entreprise par les utilisateurs finaux des appareils. Ensuite, affectez les stratégies à des groupes.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 06/04/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 1ac74ba5-7441-44ac-98b5-9d8bb8899747
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d7fa1b596a1800971919cfc0ab3e94d2d16ec328
ms.sourcegitcommit: afda8a0fc0f615e976b18ddddf81d56d7ae3566e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/20/2018
ms.locfileid: "36271522"
---
# <a name="get-started-with-creating-policies"></a>Bien démarrer avec la création de stratégies

Les stratégies Intune sont un excellent moyen d’inscrire des appareils et de garantir qu’ils sont conformes à vos stratégies d’entreprise. Les stratégies de conformité vous aident à gérer des types d’appareils spécifiques, comme les bornes d’entreprise, des appareils personnels (Bring Your Own Device), des tablettes et des appareils sans utilisateur.

![Tableau de bord de conformité avec peu de données](/intune/media/generic-compliance-dashboard.png)

Les appareils mobiles peuvent être gérés avec des stratégies de conformité, notamment :

* Régulation du nombre d’appareils qu’un utilisateur inscrit dans Intune
* Gestion des paramètres des appareils, comme l’inscription au niveau de l’appareil, la longueur du mot de passe et l’utilisation de l’appareil photo
* Fourniture d’applications, de profils de messagerie, de profils VPN, etc.
* Évaluation des critères au niveau de l’appareil dans le cadre des stratégies de conformité de la sécurité

Les stratégies de conformité sont créées pour chaque plateforme, comme iOS, Android, Windows, etc. Pour cet exercice, utilisez iOS. Les stratégies suivantes sont disponibles pour les appareils iOS :

* Configuration d'un code confidentiel ou mot de passe
* Chiffrement de l'appareil
* Appareil jailbreaké
* Profil de messagerie
* Version minimale du système d’exploitation
* Version maximale du système d’exploitation

## <a name="create-a-policy"></a>Créer une stratégie

1. Connectez-vous au [portail Azure](https://portal.azure.com).
2. Sélectionnez **Tous les services**, filtrez sur **Intune**, puis sélectionnez **Microsoft Intune**.
3. Sélectionnez **Conformité de l’appareil** > **Stratégies** > **Créer une stratégie**.
4. Entrez un **Nom** et une **Description** pour la stratégie. 
5. Pour la **Plateforme**, sélectionnez **iOS**.
6. Dans **Paramètres**, sélectionnez **Sécurité du système**, puis définissez **Exiger un mot de passe pour déverrouiller des appareils mobiles** sur **Exiger**. 

    Vous pouvez également définir d’autres règles, par exemple : 
    - **Longueur minimale du mot de passe**
    - **Type de mot de passe requis**
    - **Nombre de caractères non alphanumériques dans le mot de passe**
    
    Une fois que vous avez fini de configurer votre stratégie, sélectionnez **OK**.
  
7. Revenez à **Créer une stratégie**, puis sélectionnez **Créer**. Cette étape crée la stratégie et la fait apparaître dans **Conformité de l’appareil** > **Stratégies**.
8. Sélectionnez votre nouvelle stratégie, puis choisissez **Affectations**. Vous pouvez inclure ou exclure des groupes de sécurité Azure AD (Azure Active Directory).
Choisissez Groupes sélectionnés pour voir vos groupes de sécurité Azure AD existants. Sélectionnez les groupes d’utilisateurs auxquels vous souhaitez appliquer cette stratégie, puis choisissez **Enregistrer** pour déployer la stratégie auprès des utilisateurs.

Pour être conforme à la nouvelle stratégie d’entreprise, après quelques minutes, votre appareil inscrit vous demande un mot de passe mis à jour. Vous pouvez rechercher manuellement la mise à jour dans **l’application Portail d’entreprise pour iOS**. Ouvrez l’application Portail d’entreprise, sélectionnez le nom de l’appareil, puis **Synchroniser**.

> [!NOTE]
> Les nouvelles stratégies appliquées à un groupe d’appareils dynamique peuvent nécessiter jusqu’à huit heures pour être appliquées à tous les appareils du groupe.

## <a name="next-steps"></a>Étapes suivantes

[Bien démarrer avec l’inscription d’appareils](get-started-enroll.md) - Découvrez l’expérience d’inscription en effectuant le processus d’inscription complet d’un appareil iOS.

## <a name="learn-more"></a>En savoir plus

* [Surveiller les stratégies de conformité d’appareils Intune](compliance-policy-monitor.md)
* [Utilisations courantes des stratégies d’accès conditionnel avec Intune](conditional-access-intune-common-ways-use.md)
