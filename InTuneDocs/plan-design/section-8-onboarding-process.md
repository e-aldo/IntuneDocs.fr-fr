---
title: "Processus d&quot;intégration Intune | Microsoft Docs"
description: "Cet article vous fournit tous les détails à prendre en considération lors de l&quot;intégration d&quot;une solution Intune sur cloud uniquement dans votre environnement."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ac7bd764-5365-4920-8fd0-ea57d5ebe039
ms.reviewer: jeffbu, cgerth
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: ab6d9b6b296fb4e1fb0aaa9496fede28976728dc
ms.openlocfilehash: 23d40a31c43a061e0f3b1fbb05827697ca7380ac
ms.lasthandoff: 04/14/2017


---

# <a name="intune-implementation"></a>Implémentation d'Intune

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

Pendant la phase d’intégration, vous allez implémenter Intune dans votre environnement de production. Le processus d’implémentation se compose du paramétrage et de la configuration d'Intune et des dépendances externes (si nécessaire), selon vos [exigences de cas d'utilisation](section-3-determine-use-case-requirements.md) qui ont été passées en revue dans les sections précédentes de ce guide.

La section suivante fournit une vue d’ensemble du processus d'implémentation Intune incluant des exigences et des tâches de haut niveau.

>[!TIP]
> Consultez la section [Ressources supplémentaires](additional-resources.md) pour plus d’informations sur le processus d’implémentation Intune.

## <a name="intune-requirements"></a>Configuration requise d'Intune

Les principales exigences d'Intune autonome sont fournies ci-dessous :

-   Abonnement EMS/Intune

-   Abonnement Office 365 (pour les applications Office et les applications gérées par la stratégie MAM)

-   Certificat d'APN Apple (pour permettre la gestion de la plate-forme d'appareils iOS)

-   Azure AD Connect (pour la synchronisation d'annuaires)

-   Connecteur Intune sur site pour Exchange (pour l'autorité de certificat pour Exchange sur site, si nécessaire)

-   Intune Certificate Connector (pour le déploiement dy certificat SCEP, si nécessaire)

>[!TIP]
> Vous trouverez [ici](https://docs.microsoft.com/intune/get-started/what-to-know-before-you-start-microsoft-intune) plus d’informations sur la configuration Intune autonome requise.

## <a name="intune-implementation-process"></a>Processus d'implémentation d'Intune

### <a name="overview-of-implementation-tasks"></a>Vue d’ensemble des tâches d’implémentation

Voici une vue d’ensemble de chaque tâche de l’implémentation Intune.

#### <a name="task-1-add-intune-subscription"></a>Tâche 1 : Ajouter un abonnement Intune

Comme indiqué dans la section de configuration précédente, un abonnement EMS ou Intune est requis. Si votre organisation ne dispose pas d’un abonnement EMS ou Intune, veuillez contacter votre équipe des comptes Microsoft pour lui signifier votre souhait d’acheter Enterprise Mobility + Security (EMS) ou Intune.

-   En savoir plus sur [comment acheter Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune-pricing).

#### <a name="task-2-add-office-365-subscription"></a>Tâche 2 : Ajouter un abonnement Office 365

Cette étape est facultative. Comme indiqué dans la section de configuration précédente, un abonnement Office 365 est requis si vous envisagez d’utiliser Exchange Online et de gérer des applications mobiles Office avec la stratégie MAM. Si votre organisation ne dispose pas d’un abonnement Office 365, veuillez contacter Microsoft ou votre équipe des comptes Microsoft pour lui signifier votre souhait d’acheter Office 365.

-   En savoir plus sur [comment acheter Office 365](https://products.office.com/business/compare-office-365-for-business-plans).

#### <a name="task-3-add-users-groups-in-azure-ad"></a>Tâche 3 : Ajouter des groupes d’utilisateurs dans Azure AD

Vous devrez peut-être ajouter des utilisateurs ou des groupes de sécurité à AD ou AAD selon les scénarios de cas d'utilisation et les exigences de votre déploiement Intune. Vous devez vérifier vos utilisateurs et groupes de sécurité actuels dans Active Directory ou Azure Active Directory et déterminer s'ils répondent totalement à vos besoins. De nouveaux utilisateurs et groupes de sécurité sont généralement ajoutées dans Active Directory puis synchronisés dans Azure Active Directory via Azure AD Directory Connect.

-   En savoir plus sur [comment ajouter des utilisateurs/groupes dans Intune](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-3).

#### <a name="task-4-assign-intune-and-office-365-user-licenses"></a>Tâche 4 : Attribuer des licences utilisateur Intune et Office 365

Tous les utilisateurs ciblés pour un déploiement EMS/Intune et Office 365 devront disposer d’une licence. L’attribution d'une licence EMS/Intune et Office 365 peut être effectuée dans le portail du Centre d'administration Office 365.

-   En savoir plus sur [comment attribuer des licences Intune](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-4).

#### <a name="task-5-set-mobile-device-management-authority-to-intune"></a>Tâche 5 : Définir Intune comme autorité de gestion des appareils mobiles

Avant de commencer l'installation, la configuration, la gestion et l'inscription des appareils avec Intune, vous devez définir Intune comme autorité de gestion des appareils. La tâche Définition de l’autorité de gestion des appareils est effectuée dans l'espace de travail Admin du portail d'administration Intune.

-   En savoir plus sur la [définition de l'autorité de gestion des appareils](https://docs.microsoft.com/intune/deploy-use/prerequisites-for-enrollment#step-2-set-mdm-authority).

#### <a name="task-6-enable-device-platforms"></a>Tâche 6 : Activer les plateformes d'appareils mobiles

Par défaut, dans la console d’administration Intune, la plupart des plateformes d’appareils sont activées, à l’exception des appareils Apple (iOS et Mac). Avant de pouvoir inscrire et gérer les appareils iOS dans Intune, la plate-forme d'appareils doit être activée. L’activation de la plate-forme d'appareils iOS se déroule selon un processus en trois étapes : créer et télécharger le certificat des APN puis charger le certificat des APN dans Intune.

-   En savoir plus sur le [fonctionnement de la gestion des appareils iOS et Mac.](https://docs.microsoft.com/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune)

#### <a name="task-7-add-and-deploy-terms-and-conditions-policies"></a>Tâche 7 : Ajouter et déployer des stratégies de conditions générales

Microsoft Intune prend en charge l’ajout et le déploiement de stratégies de conditions générales. L'ajout et le déploiement de stratégies de conditions générales s'effectuent dans l'espace de travail Stratégie du portail d'administration Intune. Ajoutez les stratégies de conditions générales adéquates et déployez-les sur des groupes ciblés en fonction des cas d'utilisation et exigences de votre déploiement Intune.

-   En savoir plus sur l'[ajout et le déploiement des stratégies de conditions générales](https://docs.microsoft.com/intune/deploy-use/terms-and-condition-policy-settings-in-microsoft-intune).

#### <a name="task-8-add-and-deploy-configuration-policies"></a>Tâche 8 : Ajouter et déployer des stratégies de configuration

Microsoft Intune prend en charge l’ajout et le déploiement de deux types de stratégies de configuration, Général et Personnalisé. L'ajout et le déploiement de stratégies de configuration s'effectuent dans l'espace de travail Stratégie du portail d'administration Intune. Ajoutez les stratégies de configuration adéquates et déployez-les sur des groupes ciblés en fonction des cas d'utilisation et exigences de votre déploiement Intune.

-   En savoir plus sur l'[ajout et le déploiement des stratégies de configuration](https://docs.microsoft.com/intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies).

#### <a name="task-9-add-and-deploy-resource-profiles"></a>Tâche 9 : Ajouter et déployer des profils de ressources

Microsoft Intune prend en charge les profils de messagerie, Wi-Fi et VPN. L'ajout et le déploiement de profils s'effectuent dans l'espace de travail Stratégie du portail d'administration Intune. Ajoutez les profils de messagerie/Wi-Fi/VPN adéquats et déployez-les sur des groupes ciblés en fonction des cas d'utilisation et exigences de votre déploiement Intune.

-   En savoir plus sur [comment activer l’accès aux ressources d’entreprise avec Intune](https://docs.microsoft.com/intune/deploy-use/enable-access-to-company-resources-with-microsoft-intune).

#### <a name="task-10-add-and-deploy-apps"></a>Tâche 10 : Ajouter et déployer des applications

Microsoft Intune prend en charge le déploiement d'applications Web, métier et de banque publique. En outre, la gestion d’applications que vous avez intégrées au SDK Intune en les associant à des stratégies MAM est prise en charge. L'ajout et le déploiement d'applications s'effectuent dans l'espace de travail Application du portail d'administration Intune. L'ajout de stratégies MAM s'effectue dans l'espace de travail Stratégie du portail d'administration Intune. Ajoutez les applications adéquates et déployez-les sur des groupes ciblés en fonction des cas d'utilisation et exigences de votre déploiement Intune.

-   En savoir plus sur l'[ajout et le déploiement des applications](https://docs.microsoft.com/intune/deploy-use/deploy-apps).

#### <a name="task-11-add-and-deploy-compliance-policies"></a>Tâche 11 : Ajouter et déployer des stratégies de conformité

Microsoft Intune prend en charge les stratégies de conformité. L'ajout et le déploiement de stratégies de conformité s'effectuent dans l'espace de travail Stratégie du portail d'administration Intune. Ajoutez les stratégies de conformité adéquates et déployez-les sur des groupes ciblés en fonction des cas d'utilisation et exigences de votre déploiement Intune.

-   En savoir plus sur les [stratégies de conformité](https://docs.microsoft.com/intune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune).

#### <a name="task-12-enable-conditional-access-policies"></a>Tâche 12 : Activer les stratégie d’accès conditionnel

Microsoft Intune prend en charge l’accès conditionnel pour Exchange Online et sur site, SharePoint Online, Skype Entreprise Online et Dynamics CRM Online. Vous devez activer les stratégies d’accès conditionnel dans l'espace de travail Stratégie du portail d’administration Intune. Activez et configurez l'accès conditionnel adéquat en fonction des [cas d'utilisation et exigences de votre déploiement Intune](section-3-determine-use-case-requirements.md).

-   En savoir plus sur l'[accès conditionnel](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune).

#### <a name="task-13-enroll-devices"></a>Tâche 13 : Inscrire des appareils

Intune prend en charge les plateformes d'appareils iOS, macOS, Android, Windows Desktop et Windows Mobile. Inscrivez les plateformes d'appareils mobiles adéquates en fonction des cas d'utilisation et exigences de votre déploiement Intune.

-   En savoir plus sur [comment inscrire des appareils](https://docs.microsoft.com/intune/deploy-use/enroll-devices-in-microsoft-intune).

>[!TIP]
> Consultez ce [module de session Microsoft Virtual Academy Intune](https://mva.microsoft.com/training-courses/deploying-microsoft-enterprise-mobility-suite-16408?l=PPWNoZxvD_1404778676) pour plus d’informations sur le processus d’implémentation Intune.

## <a name="next-section"></a>Section suivante

La section suivante fournit des conseils sur le [test et la validation de votre déploiement Intune](section-9-test-and-validation.md).

