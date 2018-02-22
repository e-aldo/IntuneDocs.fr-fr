---
title: "Paramètres personnalisés Intune pour les appareils Windows Holographic for Business"
titlesuffix: Azure portal
description: "Découvrez les paramètres que vous pouvez utiliser dans un profil personnalisé Windows Holographic for Business."
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 1/24/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ae46aef10ca294637a4d433ce273d3c53e695d64
ms.sourcegitcommit: 93622d740cbd12043eedc25a9699cc4256e23e7e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/01/2018
---
# <a name="custom-device-settings-for-windows-holographic-for-business-devices-in-microsoft-intune"></a>Paramètres personnalisés pour les appareils Windows Holographic for Business dans Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

 Utilisez le profil Microsoft Intune **personnalisé** pour Windows Holographic for Business pour déployer des paramètres OMA-URI (Open Mobile Alliance Uniform Resource Identifier) pouvant servir à contrôler les fonctionnalités sur des appareils. Windows Holographic for Business rend disponibles de nombreux paramètres de fournisseurs de services de configuration. Pour avoir une vue d’ensemble des fournisseur de services de configuration, consultez [Présentation des fournisseurs de services de configuration pour les professionnels de l’informatique](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers). Pour connaître les fournisseurs de services de configuration pris en charge par Windows Holographique, consultez [Fournisseurs de services de configuration pris en charge dans Windows Holographique](https://docs.microsoft.com/en-us/windows/client-management/mdm/configuration-service-provider-reference#hololens).

Si vous recherchez un paramètre particulier, n’oubliez pas que le [profil de restriction d’appareil Windows Holographic for Business](device-restrictions-windows-holographic.md) contient de nombreux paramètres intégrés et ne nécessite pas de spécifier des valeurs personnalisées.

1. Suivez les instructions figurant dans [Configuration de paramètres d'appareil personnalisés dans Microsoft Intune](custom-settings-configure.md) pour commencer.
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
5. Lorsque vous avez terminé, revenez au panneau **Créer un profil** et cliquez sur **Créer**.
Le profil est créé et s’affiche dans le panneau de la liste des profils.

## <a name="supported-custom-settings"></a>Paramètres personnalisés pris en charge

Windows Holographic for Business prend en charge les paramètres personnalisés suivants :


|Nom du paramètre|OMA-URI|Type de données  |
|---------|---------|---------|
|AllowFastReconnect     |./Vendor/MSFT/Policy/Config/Authentication/AllowFastReconnect|Entier (0 - non autorisé, 1 - autorisé)|
|AllowVPN     |./Vendor/MSFT/Policy/Config/Settings/AllowVPN|Entier (0 - non autorisé, 1 - autorisé)|



## <a name="how-to-find-the-policies-you-can-configure"></a>Comment trouver les stratégies que vous pouvez configurer

La liste complète de tous les fournisseurs de services de configuration pris en charge par Windows Holographique est disponible dans [Fournisseurs de services de configuration pris en charge dans Windows Holographique](https://docs.microsoft.com/en-us/windows/client-management/mdm/configuration-service-provider-reference#hololens). Les paramètres ne sont pas tous compatibles avec toutes les versions de Windows Holographique. Le tableau de la rubrique Windows indique quelles versions sont prises en charge pour chaque fournisseur de services de configuration.

De plus, Intune ne prend pas en charge tous les paramètres mentionnés dans la rubrique. Pour savoir si Intune prend en charge le paramètre de votre choix, ouvrez la rubrique relative à ce paramètre. Chaque page de paramètre indique ses opérations prises en charge. Pour fonctionner avec Intune, le paramètre doit prendre en charge les opérations **Ajouter** ou **Remplacer**.


