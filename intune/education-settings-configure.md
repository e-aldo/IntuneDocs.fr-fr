---
title: Configurer les paramètres d’éducation Intune pour Windows 10
titleSuffix: Microsoft Intune
description: Découvrez comment utiliser Intune pour configurer des paramètres d’éducation sur les appareils Windows 10 que vous gérez.
keywords: ''
author: barlanmsft
ms.author: barlan
manager: dougeby
ms.date: 02/23/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 6f4de4bd-3dde-4a8d-8e22-46c5d06c3eea
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6fa631cfb799fe02aee935f524a4012f381973d8
ms.sourcegitcommit: e30fb2375fb79f67e5c1e4ed7b2c21fb9ca80c59
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/17/2018
---
# <a name="how-to-configure-windows-10-education-settings-in-microsoft-intune"></a>Guide pratique pour configurer des paramètres d’éducation Windows 10 dans Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Les profils d’éducation vous permettent de spécifier les détails qui configurent l’application Windows Take a Test, y compris les détails du compte et l’URL de test. Lorsque vous configurez cette option, l’application Take a Test s’ouvre avec le test que vous spécifiez, et aucune autre application ne peut être exécutée sur l’appareil jusqu'à ce que le test soit terminé.

Pour plus d’informations sur l’application Examen, consultez [Effectuer des tests dans Windows 10](https://docs.microsoft.com/education/windows/take-tests-in-windows-10).

## <a name="create-a-device-profile-containing-education-profile-settings"></a>Créer un profil d’appareil contenant les paramètres du profil d’éducation

1. Connectez-vous au [portail Azure](https://portal.azure.com).
2. Choisissez **Tous les services** > **Intune**. Intune se trouve dans la section **Surveillance + Gestion**.
3. Dans le volet **Intune**, choisissez **Configuration de l’appareil**.
2. Dans le volet **Configuration de l’appareil**, sous la section **Gérer**, choisissez **Profils**.
3. Dans le volet de profils, choisissez **Créer un profil**.
4. Dans le volet **Créer un profil**, entrez un **Nom** et une **Description** pour le profil de restriction d’appareil.
5. Dans la liste déroulante **Plateforme**, sélectionnez **Windows 10 et versions ultérieures**.
6. Dans la liste déroulante **Type de profil**, choisissez **Profil d’éducation**. 
7. Choisissez **Paramètres > Configurer** puis, dans le volet **Test**, configurez les éléments suivants :
    - **Type de compte** - Sélectionnez un type de compte dans la liste déroulante.
    - **Nom d’utilisateur du compte** - Entrez le nom d’utilisateur du compte utilisé avec Take a Test. Cela peut être un compte de domaine, un compte Azure Active Directory (AAD) ou un compte d’ordinateur local.
    - **URL de l’évaluation** - Fournissez l’URL du test que les utilisateurs doivent effectuer. Pour plus d’informations, consultez la documentation Take a Test.
    - **Capture d’écran** - Spécifiez si vous souhaitez pouvoir surveiller l’activité de l’écran pendant que les utilisateurs effectuent un test.
    - **Suggestion de texte** - Autorisez ou bloquez les suggestions de texte pendant que les utilisateurs effectuent un test.
8. Quand vous avez terminé, revenez au volet **Créer un profil** et appuyez sur **Créer**.

Le profil est créé et s’affiche dans le volet de la liste des profils.

## <a name="next-steps"></a>Étapes suivantes

Si vous souhaitez continuer et attribuer ce profil à des groupes, consultez [Guide pratique pour l’attribution de profils d’appareils](device-profile-assign.md).



