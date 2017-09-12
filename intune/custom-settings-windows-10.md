---
title: "Paramètres personnalisés Intune pour les appareils Windows 10"
titlesuffix: Azure portal
description: "Découvrez les paramètres que vous pouvez utiliser dans un profil personnalisé Windows 10."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7bcea136-7260-4042-b21b-c7dab86b380d
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 03dd17d1ef6cde7514720c063cef7da4c3c7db3d
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/09/2017
---
# <a name="custom-device-settings-for-windows-10-devices-in-microsoft-intune"></a>Paramètres des appareils personnalisés pour les appareils Windows 10 dans Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

 Utilisez le profil Microsoft Intune **personnalisé** pour Windows 10 et Windows 10 Mobile pour déployer des paramètres OMA-URI (Open Mobile Alliance Uniform Resource Identifier) qui peuvent être utilisés pour contrôler les fonctionnalités sur des appareils. Dans Windows 10, de nombreux paramètres CSP sont disponibles, par exemple le [fournisseur de services de configuration de stratégie](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers).
Si vous recherchez un paramètre particulier, n’oubliez pas que le [profil de restriction d’appareil Windows 10](device-restrictions-windows-10.md) contient de nombreux paramètres intégrés à Intune et ne nécessitant pas de spécifier des valeurs personnalisées.

1. Suivez les instructions figurant dans le [Guide pratique pour la configuration des paramètres d’appareils personnalisés](custom-settings-configure.md) pour commencer.
2. Dans le panneau **Créer un profil**, choisissez **Paramètres** pour ajouter un ou plusieurs paramètres OMA-URI.
3. Dans le panneau **Paramètres OMA-URI personnalisés**, cliquez sur **Ajouter** pour ajouter une nouvelle valeur. Vous pouvez également cliquer sur **Exporter** pour créer une liste de toutes les valeurs que vous avez configurées dans un fichier de valeurs séparées par des virgules (.csv).
4. Pour chaque paramètre OMA-URI à ajouter, entrez les informations suivantes. Utilisez la liste figurant dans cette rubrique pour connaître les paramètres que vous pouvez utiliser :
    - **Nom du paramètre** : Affectez un nom unique au paramètre OMA-URI pour mieux l’identifier dans la liste des paramètres.
    - **Description du paramètre** : Si vous le souhaitez, entrez une description du paramètre.
    - **Type de données** : Choisissez parmi :
        - **Chaîne**
        - **Chaîne (XML)**
        - **Date et heure**
        - **Entier**
        - **Virgule flottante**
        - **Booléen**
    - **OMA-URI (sensible à la casse)** : Spécifiez l’identificateur OMA-URI pour lequel vous voulez fournir un paramètre.
    - **Valeur** : Spécifiez la valeur à associer à l’identificateur OMA-URI que vous avez entré.
5. Lorsque vous avez terminé, revenez au panneau **Créer un profil** et appuyez sur **Créer**.
Le profil est créé et s’affiche dans le panneau de la liste des profils.

## <a name="example"></a>Exemple
Dans la capture d’écran ci-dessous, le paramètre **Connectivity/AllowVPNOverCellular** a été activé. Il permet à un appareil Windows 10 d’ouvrir une connexion VPN sur un réseau de téléphonie mobile.

> ![Exemple de stratégie personnalisée contenant des paramètres VPN](./media/custom-policy-example.png)


## <a name="how-to-find-the-policies-you-can-configure"></a>Comment trouver les stratégies que vous pouvez configurer

Vous trouverez une liste complète de tous les fournisseurs de services de configuration pris en charge par Windows 10 dans la [référence de fournisseur de services de configuration](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference) dans la bibliothèque de documentation de Windows.

Les paramètres ne sont pas tous compatibles avec toutes les versions de Windows 10. Le tableau de la rubrique Windows indique quelles versions sont prises en charge pour chaque fournisseur de services de configuration.

De plus, Intune ne prend pas en charge tous les paramètres mentionnés dans la rubrique. Pour savoir si Intune prend en charge le paramètre de votre choix, ouvrez la rubrique relative à ce paramètre. Chaque page de paramètre indique ses opérations prises en charge. Pour fonctionner avec Intune, le paramètre doit prendre en charge les opérations **Ajouter** ou **Remplacer**.


