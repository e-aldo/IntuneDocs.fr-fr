---
title: "Applications autorisées et bloquées pour KNOX"
description: "Profil personnalisé pour créer une liste d’applications autorisées et bloquées pour KNOX."
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 11/02/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bbc8e0df-7bf3-494e-8bc4-dac59a98ab41
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: ee5279c91eeaa2d75044a156ebe9c4b100bd8047
ms.sourcegitcommit: 3b397b1dcb780e2f82a3d8fba693773f1a9fcde1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/12/2017
---
# <a name="use-custom-policies-to-allow-and-block-apps-for-samsung-knox-standard-devices"></a>Utiliser des stratégies personnalisées pour autoriser et bloquer des applications pour les appareils Samsung KNOX Standard

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Appliquez les procédures de cette rubrique pour créer une stratégie personnalisée Microsoft Intune qui crée l’un des éléments suivants :

- Une liste d’applications qui sont bloquées sur l’appareil. Les applications figurant dans cette liste ne peuvent pas s’exécuter, même si elles étaient déjà installées quand la stratégie a été appliquée.
- Une liste d’applications que les utilisateurs de l’appareil sont autorisés à installer à partir du magasin Google Play. Seules les applications figurant dans la liste peuvent être installées. Aucune autre application ne peut être installée à partir de ce magasin.

Ces paramètres peuvent uniquement être utilisés par les appareils qui exécutent Samsung KNOX Standard.

## <a name="to-create-an-allowed-or-blocked-app-list"></a>Pour créer une liste d’applications autorisées ou bloquées

1. Dans la [console d’administration Microsoft Intune](https://manage.microsoft.com/), sélectionnez **Stratégie** &gt; **Stratégies de configuration** &gt; **Ajouter**.
2. Dans la boîte de dialogue **Créer une nouvelle stratégie**, développez **Android**, choisissez **Configuration personnalisée**, puis **Créer une stratégie**.
3. Fournissez un nom et éventuellement une description pour la stratégie puis, dans la section **Paramètres OMA-URI**, choisissez **Ajouter**.
4. Dans la boîte de dialogue **Ajouter ou modifier un paramètre OMA-URI**, spécifiez ce qui suit. Pour obtenir la liste des applications dont l’exécution est bloquée sur l’appareil :
    
    - **Nom du paramètre**. Entrez **PreventStartPackages**.
    - **Description du paramètre**. Entrez une description facultative, comme « Liste des applications dont l’exécution est bloquée ».
    -   **Type de données**. Dans la liste déroulante, choisissez **Chaîne**.
    -   **OMA-URI**. Entrez **./Vendor/MSFT/PolicyManager/My/ApplicationManagement/PreventStartPackages**.
    -   **Valeur**. Entrez une liste de noms de packages d’applications que vous souhaitez bloquer. Vous pouvez utiliser **; : ,** ou **|** comme délimiteur. (Exemple : package1;package2;)

    Pour obtenir la liste des applications que les utilisateurs sont autorisés à installer à partir du Google Play Store tout en excluant toutes les autres applications :

    - **Nom du paramètre**. Entrez **AllowInstallPackages**.
    - **Description du paramètre**. Entrez une description facultative, comme « Liste des applications que les utilisateurs peuvent installer à partir de Google Play ».
    - **Type de données**. Dans la liste déroulante, choisissez **Chaîne**.
    - **OMA-URI**. Entrez **./Vendor/MSFT/PolicyManager/My/ApplicationManagement/AllowInstallPackages**.
    - **Valeur**. Entrez une liste de noms de packages d’applications que vous souhaitez autoriser. Vous pouvez utiliser **; : ,** ou **|** comme délimiteur. (Exemple : package1;package2;)

4. Cliquez sur **OK**, puis sur **Enregistrer la stratégie**. 

>[!TIP]
> Vous pouvez connaître l’ID de package d’une application en accédant à l’application dans le Google Play Store. L’ID de package est contenu dans l’URL de la page d’application. Par exemple, l’ID de package de l’application Microsoft Word est **com.microsoft.office.word**.

La prochaine fois que chaque appareil ciblé se connectera, les paramètres d’application seront appliqués.


## <a name="deploy-the-policy"></a>Déploiement de la stratégie

1.  Dans l’espace de travail **Stratégie** , sélectionnez la stratégie à déployer, puis cliquez sur **Gérer le déploiement**.

2.  Dans la boîte de dialogue **Gérer le déploiement**, sélectionnez un ou plusieurs groupes sur lesquels vous voulez déployer la stratégie, puis cliquez sur **Ajouter** &gt; **OK**.

 
Quand vous sélectionnez une stratégie déployée, vous pouvez afficher d’autres informations sur le déploiement dans la partie inférieure de la liste de stratégies.

### <a name="see-also"></a>Voir aussi
[Paramètres de la stratégie de configuration Android et Samsung KNOX dans Microsoft Intune](android-policy-settings-in-microsoft-intune.md)
