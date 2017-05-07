---
title: "Configurer les paramètres d’éducation Intune pour Windows 10"
titleSuffix: Intune Azure preview
description: "Intune Azure en version préliminaire : découvrez comment utiliser Intune pour configurer des paramètres d’éducation sur les appareils Windows 10 que vous gérez."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6f4de4bd-3dde-4a8d-8e22-46c5d06c3eea
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: e5dd7cb5b320df7f443b52a1b502027fa3c4acaf
ms.openlocfilehash: d3fdf8884a0b7c035cde89da930ef74172b76873
ms.lasthandoff: 04/19/2017


---

# <a name="how-to-configure-windows-10-education-settings-in-microsoft-intune"></a>Guide pratique pour configurer des paramètres d’éducation Windows 10 dans Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Les profils d’éducation vous permettent de spécifier les détails qui configurent l’application Windows Take a Test, y compris les détails du compte et l’URL de test. Lorsque vous configurez cette option, l’application Take a Test s’ouvre avec le test que vous spécifiez, et aucune autre application ne peut être exécutée sur l’appareil jusqu'à ce que le test soit terminé.

Utilisez les informations de cette rubrique pour apprendre les notions de base sur la configuration de profils de restriction de l’appareil, puis lisez les autres rubriques pour chaque plateforme pour en savoir plus sur les caractéristiques des appareils.

## <a name="create-a-device-profile-containing-education-profile-settings"></a>Créer un profil d’appareil contenant les paramètres du profil d’éducation

1. Connectez-vous au portail Azure.
2. Choisissez **Plus de services** > **Autres** > **Intune**.
3. Dans le panneau **Intune**, choisissez **Configuration de l’appareil**.
2. Dans le panneau **Configuration de l’appareil**, choisissez **Gérer** > **Profils**.
3. Dans le panneau des profils, sélectionnez **Créer un profil**.
4. Dans le panneau **Créer un profil**, entrez un **Nom** et une **Description** pour le profil de restriction d'appareil.
5. Dans la liste déroulante **Plateforme**, sélectionnez **Windows 10 et versions ultérieures**.
6. Dans la liste déroulante **Type de profil**, choisissez **Profil d’éducation**. 
7. Choisissez Paramètres > Configurer, puis, dans le panneau **Test**, configurez les éléments suivants :
    - **Nom d’utilisateur du compte** - Entrez le nom d’utilisateur du compte utilisé avec Take a Test. Cela peut être un compte de domaine, un compte Azure Active Directory (AAD) ou un compte d’ordinateur local.
    - **URL de l’évaluation** - Fournissez l’URL du test que les utilisateurs doivent effectuer. Pour plus d’informations, consultez la documentation Take a Test.
    - **Capture d’écran** - Spécifiez si vous souhaitez pouvoir surveiller l’activité de l’écran pendant que les utilisateurs effectuent un test.
    - **Suggestion de texte** - Autorisez ou bloquez les suggestions de texte pendant que les utilisateurs effectuent un test.
8. Lorsque vous avez terminé, revenez au panneau **Créer un profil** et appuyez sur **Créer**.

Le profil est créé et s’affiche dans le panneau de la liste des profils.
Si vous souhaitez continuer et attribuer ce profil à des groupes, consultez [Guide pratique pour l’attribution de profils d’appareils](how-to-assign-device-profiles.md).




