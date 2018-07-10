---
title: Paramètres personnalisés pour les appareils Windows 10 dans Microsoft Intune - Azure | Microsoft Docs
description: Configurez des paramètres personnalisés OMA-URI sur des appareils exécutant Windows 10 avec un profil personnalisé dans Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 6/18/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: bdbb6643a4ee8aace0db22cd7f9189f7ac6445f0
ms.sourcegitcommit: ada99fefe9a612ed753420116f8c801ac4bf0934
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/19/2018
ms.locfileid: "36232824"
---
# <a name="custom-oma-uri-settings-for-windows-10-devices---intune"></a>Paramètres OMA-URI personnalisés pour les appareils Windows 10 - Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Utilisez le profil Microsoft Intune **personnalisé** pour Windows 10 et Windows 10 Mobile pour déployer des paramètres OMA-URI (Open Mobile Alliance Uniform Resource Identifier). Ces paramètres sont utilisés pour contrôler les fonctionnalités sur les appareils. De nombreux paramètres de fournisseur de services de configuration (CSP) sont disponibles dans Windows 10, comme [Fournisseur CSP de stratégie](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers).

Si vous recherchez un paramètre spécifique, n’oubliez pas que le [profil de restriction d’appareil Windows 10](device-restrictions-windows-10.md) contient de nombreux paramètres intégrés à Intune et ne nécessitent pas de valeurs personnalisées.

## <a name="configure-custom-settings"></a>Configurer des paramètres personnalisés

1. Créez un profil de configuration avec le type de profil **Personnalisé**. [Guide pratique pour configurer des paramètres d’appareils personnalisés](custom-settings-configure.md) répertorie les étapes.
2. Dans **Paramètres OMA-URI personnalisés**, sélectionnez **Ajouter** pour créer un paramètre. Vous pouvez également cliquer sur **Exporter** pour créer une liste de toutes les valeurs que vous avez configurées dans un fichier de valeurs séparées par des virgules (.csv).
3. Pour chaque paramètre OMA-URI à ajouter, entrez les informations suivantes :

- **Nom** : entrez un nom unique pour paramètre OMA-URI, qui vous permette de l’identifier dans la liste des paramètres.
- **Description** : (facultatif) entrez une description du paramètre.
- **OMA-URI (sensible à la casse)**  : Entrez l’identificateur OMA-URI pour lequel vous voulez fournir un paramètre.
- **Type de données** : Choisissez parmi :
  - **Chaîne**
  - **Chaîne (XML)**
  - **Date et heure**
  - **Entier**
  - **Virgule flottante**
  - **Booléen**
  - **Base64**
- **Valeur** : entrez la valeur ou le fichier à associer à l’identificateur OMA-URI que vous avez entré.

4. Quand vous avez terminé, sélectionnez **OK**. Dans **Créer un profil**, sélectionnez **Créer**. Le profil est créé et apparaît dans la liste des profils.

## <a name="example"></a>Exemple
Dans l’exemple suivant, le paramètre **Connectivity/AllowVPNOverCellular** est activé. Il permet à un appareil Windows 10 d’ouvrir une connexion VPN sur un réseau de téléphonie mobile.

![Exemple de stratégie personnalisée contenant des paramètres VPN](./media/custom-policy-example.png)

## <a name="find-the-policies-you-can-configure"></a>Trouver les stratégies que vous pouvez configurer

Vous pouvez trouver une liste complète de tous les fournisseurs de services de configuration pris en charge par Windows 10 dans les [Informations de référence sur les fournisseurs de services de configuration](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference).

Les paramètres ne sont pas tous compatibles avec toutes les versions de Windows 10. [Informations de référence sur les fournisseurs de services de configuration](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference) vous indique quelles versions sont prises en charge pour chaque fournisseur de services de configuration.

En outre, Intune ne prend pas en charge tous les paramètres répertoriés. Pour savoir si Intune prend en charge le paramètre de votre choix, ouvrez l’article relatif à ce paramètre. Chaque page de paramètre indique ses opérations prises en charge. Pour fonctionner avec Intune, le paramètre doit prendre en charge les opérations **Ajouter** ou **Remplacer**.
