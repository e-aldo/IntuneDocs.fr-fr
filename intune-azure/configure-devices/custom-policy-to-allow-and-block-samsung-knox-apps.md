---
title: "Stratégie Intune Autoriser ou bloquer des applications pour Samsung KNOX"
titleSuffix: Intune Azure preview
description: "Préversion Intune Azure : Créez un profil personnalisé pour autoriser et bloquer des applications pour les appareils Samsung KNOX Standard."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d035ebf5-85f4-4001-a249-75d24325061a
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: f7680666ca466bd37711eeb363fe2c1f9d52e371
ms.lasthandoff: 02/18/2017



---
# <a name="use-custom-policies-to-allow-and-block-apps-for-samsung-knox-standard-devices-in-microsoft-intune"></a>Utiliser des stratégies personnalisées pour autoriser et bloquer des applications pour les appareils Samsung KNOX Standard dans Microsoft Intune
[!INCLUDE[azure_preview](../includes/azure_preview.md)] Appliquez les procédures de cette rubrique pour créer une stratégie personnalisée Microsoft Intune qui crée l’un des éléments suivants Intune Azure en préversion :

- Une liste d’applications qui sont bloquées sur l’appareil. Les applications figurant dans cette liste ne peuvent pas s’exécuter, même si elles étaient déjà installées quand la stratégie a été appliquée.
- Une liste d’applications que les utilisateurs de l’appareil sont autorisés à installer à partir du magasin Google Play. Seules les applications figurant dans la liste peuvent être installées. Aucune autre application ne peut être installée à partir de ce magasin.

Ces paramètres peuvent uniquement être utilisés par les appareils qui exécutent Samsung KNOX Standard.

## <a name="create-an-allowed-or-blocked-app-list"></a>Créer une liste d’applications autorisées ou bloquées

1. Connectez-vous au portail Azure.
2. Choisissez **Plus de services** > **Autres** > **Intune**.
3. Dans le panneau **Intune**, choisissez **Configurer des appareils**.
2. Dans le panneau **Configuration de l’appareil**, choisissez **Gérer** > **Profils**.
2. Dans le panneau de la liste des profils, sélectionnez **Créer un profil**.
3. Dans le panneau **Créer un profil**, entrez un **nom** et éventuellement une **description** pour ce profil d'appareil.
2. Choisissez le **type de plate-forme** **Android**et le type de profil **Personnalisé**.
3. Cliquez sur **Paramètres**.
3. Dans le panneau **Paramètres OMA-URI personnalisés**, choisissez **Ajouter**.
4. Dans la boîte de dialogue **Ajouter ou modifier un paramètre OMA-URI**, spécifiez les informations suivantes :

### <a name="for-a-list-of-apps-that-are-blocked-from-running-on-the-device"></a>Pour afficher une liste d’applications qui sont bloquées sur l’appareil :

- **Nom** - Entrez **PreventStartPackages**.
- **Description** - Entrez une description facultative, comme « Liste des applications dont l’exécution est bloquée ».
-     **Type de données** - Dans la liste déroulante, choisissez **Chaîne**.
-     **OMA-URI** - Entrez **./Vendor/MSFT/PolicyManager/My/ApplicationManagement/PreventStartPackages**
-     **Valeur** - Entrez une liste de noms de packages d’applications que vous souhaitez autoriser. Vous pouvez utiliser **; : ,** ou **|** comme délimiteur. (Exemple : package1;package2;)

### <a name="for-a-list-of-apps-that-users-are-allowed-to-install-from-the-google-play-store-while-excluding-all-other-apps"></a>Pour obtenir la liste des applications que les utilisateurs sont autorisés à installer à partir du Google Play Store tout en excluant toutes les autres applications :
- **Nom** - Entrez **AllowInstallPackages**.
- **Description** - Entrez une description facultative, comme « Liste des applications que les utilisateurs peuvent installer à partir de Google Play ».
- **Type de données** - Dans la liste déroulante, choisissez **Chaîne**.
- **OMA-URI** - Entrez **./Vendor/MSFT/PolicyManager/My/ApplicationManagement/AllowInstallPackages**
- **Valeur** - Entrez une liste de noms de packages d’applications que vous souhaitez autoriser. Vous pouvez utiliser **; : ,** ou **|** comme délimiteur. (Exemple : package1;package2;)

4. Cliquez sur **OK**, puis, dans le panneau **Créer un profil**, choisissez **Créer**.

>[!TIP]
> Vous pouvez connaître l’ID de package d’une application en accédant à l’application dans le Google Play Store. L’ID de package est contenu dans l’URL de la page d’application. Par exemple, l’ID de package de l’application Microsoft Word est **com.microsoft.office.word**.

La prochaine fois que chaque appareil ciblé se connectera, les paramètres d’application seront appliqués.


<!---## Assign the custom profile--->

