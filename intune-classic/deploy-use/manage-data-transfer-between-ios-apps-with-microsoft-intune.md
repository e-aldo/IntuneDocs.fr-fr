---
title: "Gérer les transferts de données entre applications iOS"
description: "Cette rubrique explique comment utiliser la fonctionnalité iOS Open In et les stratégies de gestion des applications mobiles pour gérer les transferts de données entre applications."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3a4515c1-b325-4ac1-9f0a-45ac27e00681
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 05975303bd45764d56f00986aea5aa30399893f9
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/01/2017
---
# <a name="manage-data-transfer-between-ios-apps-with-microsoft-intune"></a>Gérer les transferts de données entre applications iOS avec Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

## <a name="manage-ios-apps"></a>Gérer les applications iOS
La protection des données de votre entreprise nécessite notamment de vérifier que les transferts de fichiers sont limités aux applications que vous gérez.  Vous pouvez gérer les applications iOS comme suit :

-   Empêchez la perte de données d’entreprise en configurant une stratégie de protection des applications pour les applications. Ces dernières sont appelées des applications **gérées par une stratégie**.

-   Vous pouvez également déployer et gérer des applications via le **canal MDM**.  Ceci nécessite que les appareils soient inscrits dans la solution MDM. Il peut s’agir d’applications **gérées par une stratégie** ou d’autres applications gérées.

La fonctionnalité **Ouvrir dans la gestion** des appareils iOS peut limiter les transferts de fichiers entre des applications déployées sur le **canal MDM**. Les restrictions de gestion de l’ouverture sont définies dans les paramètres de configuration et déployées à l’aide de votre solution de gestion des périphériques mobiles (GPM).  Quand l’utilisateur installe l’application déployée, les restrictions que vous avez définies sont appliquées.

##  <a name="manage-data-transfer-between-ios-apps"></a>Gérer les transferts de données entre applications iOS
Vous pouvez utiliser les stratégies de protection des applications avec la fonctionnalité **Open in management** d’iOS pour protéger les données d’entreprise des façons suivantes :

-   **Appareils appartenant à l’employé non gérés par une solution de gestion des appareils mobiles :** vous pouvez définir le [paramètre de la stratégie de protection des applications](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) pour **autoriser l’application à transférer des données uniquement vers des applications gérées**. Quand l’utilisateur final ouvre un fichier protégé dans une application non gérée, le fichier n’est pas lisible.

-   **Appareils gérés par Intune :** pour les appareils inscrits dans Intune, le transfert de données entre les applications avec les stratégies de protection des applications et les autres applications iOS gérées qui sont déployées par le biais de Microsoft Intune est automatiquement autorisé. Pour permettre le transfert de données entre les applications avec les stratégies protection des applications, activez le paramètre **Autoriser l’application à transférer des données uniquement vers des applications gérées**. Vous pouvez utiliser la fonctionnalité **Ouvrir dans la gestion** pour contrôler le transfert de données entre les applications qui sont déployées via Intune.   

-   **Appareils gérés par une solution MDM tierce** : vous pouvez limiter le transfert de données uniquement à des applications gérées en utilisant la fonctionnalité **Ouvrir d’iOS dans la gestion**.
Pour vous assurer que les applications que vous déployez à l’aide de votre solution MDM tierce sont également associées aux stratégies de protection des applications que vous avez configurées dans Intune, vous devez configurer le paramètre de nom UPN d’utilisateur comme décrit dans la procédure [Configurer le paramètre UPN d’utilisateur](#configure-user-upn-setting-for-third-party-emm).  Quand les applications sont déployées avec le paramètre UPN de l’utilisateur, les stratégies de protection des applications sont appliquées à l’application quand l’utilisateur final se connecte en utilisant son compte professionnel.

> [!IMPORTANT]
> Le paramètre Nom UPN d’utilisateur est obligatoire seulement pour les applications déployées sur des appareils gérés par une gestion MDM tierce.  Pour les appareils gérés par Intune, ce paramètre n’est pas obligatoire.

## <a name="configure-user-upn-setting-for-third-party-emm"></a>Configurer le paramètre UPN d’utilisateur pour une solution de gestion de la mobilité d’entreprise tierce
Le paramètre UPN d’utilisateur **doit être configuré** pour les appareils gérés par une solution de gestion de la mobilité d’entreprise tierce. La procédure décrite ci-dessous est un flux général indiquant comment configurer le paramètre UPN et l’expérience résultante pour l’utilisateur final :


1.  Dans le portail Azure, [configurez une stratégie de protection des applications](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) pour la plateforme iOS. Configurez les paramètres de stratégie selon les besoins de votre entreprise et sélectionnez les applications qui doivent disposer de cette stratégie.

2.  Déployez les applications et le profil de messagerie que vous souhaitez gérer **par le biais de votre solution de gestion des appareils mobiles tierce** en suivant les étapes généralisées ci-dessous. Cette expérience est également abordée dans l’Exemple 1.

  1.  Déployez l’application avec les paramètres de configuration d’application suivants :

      **clé** = IntuneMAMUPN,  **valeur** = <username@company.com>

      Exemple : [‘IntuneMAMUPN’, ‘jondoe@microsoft.com’]

  2.  Déployez la stratégie Open in management à l’aide de votre fournisseur de gestion des appareils mobiles tiers sur les appareils inscrits.


### <a name="example-1-admin-experience-in-third-party-mdm-console"></a>Exemple 1 : Expérience de l’administrateur dans la console de gestion des appareils mobiles tierce

1. Accédez à la console d’administration du fournisseur de gestion des appareils mobiles tiers. Accédez à la section de la console dans laquelle vous déployez les paramètres de configuration d’application sur les appareils iOS inscrits.

2. Dans la section Configuration de l’application, entrez le paramètre suivant :

  **clé** = IntuneMAMUPN,  **valeur** = <username@company.com>

  La syntaxe exacte de la paire clé/valeur peut varier en fonction du fournisseur de gestion des appareils mobiles tiers. Le tableau ci-dessous présente des exemples de fournisseurs de gestion des appareils mobiles tiers et les valeurs exactes à entrer dans la paire clé/valeur.

|Fournisseur de gestion des appareils mobiles tiers| Clé Configuration | Type de valeur | Valeur Configuration|
| ------- | ---- | ---- | ---- |
| VMware AirWatch | IntuneMAMUPN | Chaîne | {UserPrincipalName}|
| MobileIron Core | IntuneMAMUPN | Chaîne | $EMAIL$ **ou** $USER_UPN$ |
| MobileIron Cloud | IntuneMAMUPN | Chaîne | ${userUPN} **ou** ${userEmailAddress} |

### <a name="example-2-end-user-experience"></a>Exemple 2 : Expérience de l’utilisateur final

1.  L’utilisateur installe l’application Microsoft Word sur l’appareil.

2.  L’utilisateur final lance l’application de messagerie native gérée pour accéder à sa messagerie.

3.  L’utilisateur final tente d’ouvrir un document provenant de la messagerie native dans Microsoft Word.

4.  Quand l’application Word démarre, l’utilisateur final est invité à se connecter en utilisant son compte professionnel.  Ce compte de travail que l’utilisateur final saisit lors de l’invite doit correspondre à celui que vous avez spécifié dans les paramètres de configuration de l’application pour Microsoft Word.

    > [!NOTE]
    > L’utilisateur final peut ajouter d’autres comptes personnels dans Word pour effectuer son travail personnel sans être affecté par les stratégies de protection des applications lors de l’utilisation de l’application Word dans un contexte personnel.

5.  Quand la connexion est établie, les paramètres de la stratégie de protection des applications sont appliqués à l’application Word.

6.  Le transfert de données s’exécute maintenant avec succès et le document est marqué avec l’identité de l’entreprise dans l’application. En outre, le fichier est traité dans un contexte de travail ; les paramètres de stratégie sont appliqués en conséquence.

### <a name="validate-user-upn-setting-for-third-party-emm"></a>Valider le paramètre UPN d’utilisateur pour une solution de gestion de la mobilité d’entreprise tierce

Après avoir configuré le paramètre UPN d’utilisateur, vous devez vérifier que l’application iOS peut recevoir la stratégie de protection des applications Intune et s’y conformer.

Par exemple, le paramètre de stratégie **Exiger le code confidentiel de l’application** est facile à tester visuellement sur un appareil. Si le paramètre de stratégie a la valeur **Oui**, l’utilisateur final est invité à définir ou à entrer un code PIN quand il tente d’accéder aux données de l’entreprise.

Tout d’abord, [créez et déployez une stratégie de protection des applications](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) sur l’application iOS. Pour plus d’informations sur la façon de tester la stratégie de protection des applications, consultez [Valider les stratégies de protection des applications](validate-mobile-application-management.md).



### <a name="see-also"></a>Voir aussi
[Protéger les données d’application à l’aide de stratégies de protection des applications avec Microsoft Intune](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)
