---
title: "Configurer les paramètres d’Intune Education pour iOS"
titleSuffix: Intune Azure preview
description: "Préversion Intune Azure : Découvrez les paramètres que vous pouvez utiliser pour contrôler les paramètres Education sur les appareils iOS."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 01/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 44c427f8-0f22-43c2-8c29-e0f9fa533b1f
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: 8d801c0b264e95348f55b1d4046c00e43ead5d10
ms.lasthandoff: 02/18/2017


---

# <a name="how-to-configure-intune-education-settings-for-ios-devices-in-intune-azure-preview"></a>Guide pratique pour configurer des paramètres d’Intune Education pour les appareils iOS dans la préversion d’Intune Azure

[!INCLUDE[azure_preview](../includes/azure_preview.md)]


## <a name="create-a-device-profile-containing-ios-education-settings"></a>Créer un profil d’appareil contenant les paramètres d’iOS Education

1. Connectez-vous au portail Azure.
2. Choisissez **Plus de services** > **Autres** > **Intune**.
3. Dans le panneau **Intune**, choisissez **Configurer des appareils**.
2. Dans le panneau **Configuration de l’appareil**, sélectionnez **Gérer** > **Profils**.
3. Dans le panneau des profils, sélectionnez **Créer un profil**.
4. Dans le panneau **Créer un profil**, entrez un **Nom** et une **Description** pour le profil de mise à niveau de l’édition.
5. Dans la liste déroulante **Plateforme**, choisissez **iOS**.
6. Dans la liste déroulante **Type de profil**, choisissez **Education**.
7. Dans le panneau **Education**, sélectionnez les éléments suivants :
    - **Fichier de certificat racine Professeur**
    - **Profil PKCS12 / PFX Professeur**
    - **Fichier de certificat racine Étudiant**
    - **Profil PKCS12 / PFX Étudiant**
8. Lorsque vous avez terminé, revenez au panneau **Créer un profil** et appuyez sur **Créer**.

Le profil est créé et s’affiche dans le panneau de la liste des profils.

