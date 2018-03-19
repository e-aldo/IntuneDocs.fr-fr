---
title: "Bien démarrer avec les stratégies dans Microsoft Intune"
titlesuffix: 
description: "Créez des stratégies pour protéger les données d’entreprise et gérer l’accès aux ressources de l’entreprise par les utilisateurs finaux des appareils."
keywords: 
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 02/26/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1ac74ba5-7441-44ac-98b5-9d8bb8899747
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8af61eb207a8f9b2dc74650627fcab0e4d858904
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/08/2018
---
# <a name="get-started-with-creating-policies"></a>Bien démarrer avec la création de stratégies

L’un des principaux objectifs lors de la prise en main d’Intune est l’inscription des appareils afin de s’assurer qu’ils sont conformes aux stratégies d’entreprise. Les stratégies de conformité vous aident non seulement à gérer des types d’appareils spécifiques, tels que les bornes d’entreprise, mais également les appareils personnels (Bring Your Own Device), les tablettes et les appareils sans utilisateur.

![Tableau de bord de conformité avec peu de données](/intune/media/generic-compliance-dashboard.png)

Gérez les appareils mobiles dans les domaines suivants à l’aide de stratégies de conformité :

* Régulation du nombre d’appareils inscrits par chaque utilisateur
* Gestion des paramètres des appareils (par exemple inscription au niveau de l’appareil, longueur du mot de passe, utilisation de l’appareil photo)
* Fourniture d’applications, de profils de messagerie et VPN, etc.
* Évaluation des critères au niveau de l’appareil dans le cadre des stratégies de conformité de la sécurité

Vous créez des stratégies de conformité pour chaque plateforme séparément. Pour cet exercice, nous allons nous limiter à iOS. Les stratégies suivantes sont disponibles pour les appareils iOS :

* Configuration d'un code confidentiel ou mot de passe
* Chiffrement de l'appareil
* Appareil jailbreaké
* Profil de messagerie
* Version minimale du système d’exploitation
* Version maximale du système d’exploitation

__Comment créer une stratégie ?__

1. Connectez-vous au [portail Azure](https://portal.azure.com).
2. Choisissez **Tous les services** > **Intune**. Intune se trouve dans la section **Surveillance + Gestion**.
3. Sélectionnez **Conformité de l’appareil**.
4. Dans le volet **Conformité de l’appareil**, sélectionnez **Stratégies**.
5. Sélectionnez **Créer une stratégie**, puis renseignez les détails tels que le **Nom** et la **Description**. 
6. Choisissez **iOS** comme **Plateforme**.
6. Dans **Paramètres**, sélectionnez **Sécurité du système**, puis affectez la valeur **Exiger** à **Exiger un mot de passe pour déverrouiller des appareils mobiles**. Vous pouvez également définir d’autres règles, telles que **Longueur minimale du mot de passe**, **Type de mot de passe obligatoire** et **Nombre de caractères non alphanumériques dans le mot de passe**. Une fois que vous avez fini de configurer votre stratégie, sélectionnez **OK**.
7. Revenez au volet **Créer une stratégie**, puis sélectionnez **Créer**.
8. Une fois la stratégie créée, sélectionnez **Affectations** pour l’affecter à votre groupe de test. Sélectionnez votre groupe de test, qui doit contenir votre utilisateur test, puis affectez la stratégie à ce groupe en cliquant sur **Enregistrer**.
9. Patientez quelques minutes. Votre appareil inscrit devrait vous inviter à entrer un mot de passe mis à jour afin de rester conforme à la stratégie d’entreprise. Vous pouvez également effectuer cette vérification manuellement dans **l’application Portail d’entreprise pour iOS** en appuyant sur le nom de l’appareil, puis sur le bouton **Synchroniser**.

## <a name="next-steps"></a>Étapes suivantes

[Bien démarrer avec l’inscription d’appareils](get-started-enroll.md) - Découvrez l’expérience d’inscription en effectuant le processus d’inscription complet d’un appareil iOS.

## <a name="learn-more"></a>En savoir plus

* [Surveiller les stratégies de conformité d’appareils Intune](compliance-policy-monitor.md)
* [Utilisations courantes des stratégies d’accès conditionnel avec Intune](conditional-access-intune-common-ways-use.md)
