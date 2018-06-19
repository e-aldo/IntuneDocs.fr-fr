---
title: Paramètres personnalisés dans Microsoft Intune pour les appareils exécutant Windows 10
titlesuffix: ''
description: Découvrez les paramètres personnalisés que vous pouvez configurer dans un profil personnalisé Windows 10.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 3/1/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 36705c49a55c88c41470feaad14520e900dcb3dd
ms.sourcegitcommit: dbea918d2c0c335b2251fea18d7341340eafd673
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31837011"
---
# <a name="microsoft-intune-custom-device-settings-for-devices-running-windows-10"></a>Paramètres d’appareil personnalisés dans Microsoft Intune pour les appareils exécutant Windows 10

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

 Utilisez le profil Microsoft Intune **personnalisé** pour Windows 10 et Windows 10 Mobile pour déployer des paramètres OMA-URI (Open Mobile Alliance Uniform Resource Identifier) qui peuvent être utilisés pour contrôler les fonctionnalités sur des appareils. De nombreux paramètres de fournisseur de services de configuration (CSP) sont disponibles dans Windows 10, notamment le [fournisseur CSP de stratégie](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers).
Si vous recherchez un paramètre particulier, n’oubliez pas que le [profil de restriction d’appareil Windows 10](device-restrictions-windows-10.md) contient de nombreux paramètres intégrés à Intune et ne nécessitant pas de spécifier des valeurs personnalisées.

## <a name="configure-custom-settings"></a>Configurer des paramètres personnalisés

1. Suivez les instructions figurant dans [Configuration de paramètres d'appareil personnalisés dans Microsoft Intune](custom-settings-configure.md) pour commencer.
1. Dans le volet **Paramètres OMA-URI personnalisés**, cliquez sur **Ajouter** pour ajouter une nouvelle valeur. Vous pouvez également cliquer sur **Exporter** pour créer une liste de toutes les valeurs que vous avez configurées dans un fichier de valeurs séparées par des virgules (.csv).
1. Pour chaque paramètre OMA-URI à ajouter, entrez les informations suivantes. Utilisez la liste figurant dans cet article pour connaître les paramètres que vous pouvez utiliser :
    - **Nom** : affectez un nom unique au paramètre OMA-URI pour vous aider à l'identifier dans la liste des paramètres.
    - **Description** : en option, entrez une description du paramètre.
    - **OMA-URI (sensible à la casse)**  : Spécifiez l’identificateur OMA-URI pour lequel vous voulez fournir un paramètre.
    - **Type de données** : Choisissez parmi :
        - **Chaîne**
        - **Chaîne (XML)**
        - **Date et heure**
        - **Entier**
        - **Virgule flottante**
        - **Booléen**
        - **Base64**
    - **Valeur** : spécifiez la valeur ou le fichier à associer au paramètre OMA-URI que vous avez entré.
1. Lorsque vous avez terminé, sélectionnez **OK**, revenez au volet **Créer un profil** et sélectionnez **Créer**.
Le profil est créé et apparaît dans le volet de la liste des profils.

## <a name="example"></a>Exemple
Dans la capture d’écran ci-après, le paramètre **Connectivity/AllowVPNOverCellular** a été activé. Il permet à un appareil Windows 10 d’ouvrir une connexion VPN sur un réseau de téléphonie mobile.

> ![Exemple de stratégie personnalisée contenant des paramètres VPN](./media/custom-policy-example.png)


## <a name="how-to-find-the-policies-you-can-configure"></a>Comment trouver les stratégies que vous pouvez configurer

Vous trouverez une liste complète de tous les fournisseurs de services de configuration pris en charge par Windows 10 dans la [référence de fournisseur de services de configuration](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference) dans la bibliothèque de documentation de Windows.

Les paramètres ne sont pas tous compatibles avec toutes les versions de Windows 10. Le tableau de l’article Windows indique quelles versions sont prises en charge pour chaque fournisseur de services de configuration.

De plus, Intune ne prend pas en charge tous les paramètres mentionnés dans l’article. Pour savoir si Intune prend en charge le paramètre de votre choix, ouvrez l’article relatif à ce paramètre. Chaque page de paramètre indique ses opérations prises en charge. Pour fonctionner avec Intune, le paramètre doit prendre en charge les opérations **Ajouter** ou **Remplacer**.
