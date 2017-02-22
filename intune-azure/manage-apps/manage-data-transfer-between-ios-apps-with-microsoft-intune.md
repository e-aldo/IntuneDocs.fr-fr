---
title: "Gestion du transfert de données entre des applications iOS | Version préliminaire d’Intune Azure | Microsoft Docs"
description: "Version préliminaire d’Intune Azure : cette rubrique explique comment utiliser la fonctionnalité iOS Open In et les stratégies de gestion des applications mobiles pour gérer les transferts de données entre applications."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d10b2d64-8c72-4e9b-bd06-ab9d9486ba5e
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 424fae862592c1ab5b4221fb5ad40a52c39f6760
ms.openlocfilehash: 8846417efd34db32d5a5c872ef438f5a0bc57e36


---

# <a name="how-to-manage-data-transfer-between-ios-apps"></a>Guide pratique de gestion des transferts de données entre applications iOS 
## <a name="manage-ios-apps"></a>Gérer les applications iOS
La protection des données de votre entreprise nécessite notamment de vérifier que les transferts de fichiers sont limités aux applications que vous gérez.  Vous pouvez gérer les applications iOS comme suit :

-   Empêchez la perte de données d’entreprise en configurant une stratégie de protection des applications pour les applications. Nous appellerons cela les applications **gérées par une stratégie**.

-   Vous pouvez également déployer et gérer des applications via le **canal MDM**.  Ceci nécessite que les appareils soient inscrits dans la solution MDM. Il peut s’agir d’applications **gérées par une stratégie** ou d’autres applications gérées.

La fonctionnalité **Ouvrir dans la gestion** pour les appareils iOS peut limiter les transferts de fichiers entre des applications déployées sur le **canal MDM**. Les restrictions de gestion de l’ouverture sont définies dans les paramètres de configuration et déployées à l’aide de votre solution de gestion des appareils mobiles (MDM).  Quand l’utilisateur installe l’application déployée, les restrictions que vous avez définies sont appliquées.
##  <a name="using-app-protection-with-ios-apps"></a>Utilisation de la protection des applications avec des applications iOS
Les stratégies de protection des applications peuvent être utilisées avec la fonctionnalité **d'ouverture dans la gestion** d’iOS pour protéger les données d’entreprise des façons suivantes :

-   **Appareils appartenant à l’entreprise non gérés par une solution MDM :** vous pouvez définir les paramètres de la stratégie de protection des applications pour **autoriser l’application à transférer des données uniquement vers des applications gérées**. Quand l’utilisateur final ouvre un fichier protégé dans une application non gérée, le fichier n’est pas lisible.

-   **Appareils gérés par Intune :** pour les appareils inscrits dans Intune, le transfert de données entre les applications avec les stratégies de protection des applications et les autres applications iOS gérées déployées par le biais d'Intune est autorisé automatiquement. Pour permettre le transfert de données entre les applications avec les stratégies protection des applications, activez le paramètre **Autoriser l’application à transférer des données uniquement vers des applications gérées**. Vous pouvez utiliser la fonctionnalité **Ouvrir dans la gestion** pour contrôler le transfert de données entre les applications qui sont déployées via Intune.   

-   **Appareils gérés par une solution MDM tierce** : vous pouvez limiter le transfert de données uniquement à des applications gérées en utilisant la fonctionnalité **Ouvrir d’iOS dans la gestion**.
Pour vous assurer que les applications que vous déployez à l’aide de votre solution MDM tierce sont également associées aux stratégies de protection des applications que vous avez configurées dans Intune, vous devez configurer le paramètre de nom UPN d’utilisateur comme décrit dans la procédure [Configurer le paramètre UPN d’utilisateur](#configure-user-upn-setting).  Quand les applications sont déployées avec le paramètre UPN de l’utilisateur, les stratégies de protection des applications sont appliquées à l’application quand l’utilisateur final se connecte en utilisant son compte professionnel.

> [!IMPORTANT]
> Le paramètre Nom UPN d’utilisateur est obligatoire seulement pour les applications déployées sur des appareils gérés par une gestion MDM tierce.  Pour les appareils gérés par Intune, ce paramètre n’est pas obligatoire.

## <a name="configure-user-upn-setting"></a>Configurer le paramètre UPN d’utilisateur
Cette configuration est requise pour les appareils qui sont gérés par une solution MDM tierce. La procédure décrite ci-dessous est un flux général indiquant comment implémenter le paramètre UPN et l’expérience utilisateur final obtenue :


1.  Dans le portail Azure, [configurez une stratégie de gestion des applications mobiles](app-protection-policies.md) pour la plateforme iOS. Configurez les paramètres de stratégie selon les besoins de votre entreprise et sélectionnez les applications qui doivent disposer de cette stratégie.

2.  Déployez les applications et le profil de messagerie que vous souhaitez gérer **avec votre solution MDM tierce** à l’aide du paramètre décrit dans les étapes 3 et 4.

3.  Déployez l’application avec les paramètres de configuration d’application suivants : clé=IntuneMAMUPN, valeur=<username@company.com> [exemple: 'IntuneMAMUPN', ‘jondoe@microsoft.com’]

4.  Déployez la stratégie Ouvrir dans la gestion sur les appareils inscrits.

### <a name="example-end-user-experience"></a>Exemple d’expérience utilisateur final

1.  L’utilisateur installe l’application Microsoft Word sur l’appareil.

2.  L’utilisateur final lance l’application de messagerie native gérée pour accéder à sa messagerie.

3.  L’utilisateur final tente d’ouvrir un document provenant de la messagerie native dans Microsoft Word.

4.  Quand l’application Word démarre, l’utilisateur final est invité à se connecter en utilisant son compte professionnel.  Ce compte de travail que l’utilisateur final saisit lors de l’invite doit correspondre à celui que vous avez spécifié dans les paramètres de configuration de l’application pour Microsoft Word.

    > [!NOTE]
    > L’utilisateur final peut ajouter d’autres comptes personnels dans Word pour effectuer son travail personnel sans être affecté par les stratégies de protection des applications lors de l’utilisation de l’application Word dans un contexte personnel.

5.  Quand la connexion est établie, les paramètres de stratégie d’application sont appliqués à l’application Word.

6.  Le transfert de données se fait maintenant avec succès et le document est marqué avec l’identité de l’entreprise dans l’application. En outre, les données sont traitées dans un contexte de travail et les paramètres de stratégie sont donc appliqués.

### <a name="see-also"></a>Voir aussi
[Qu’est ce qu’une stratégie de protection d’application Intune ?](what-is-app-protection-policy.md)



<!--HONumber=Feb17_HO1-->


