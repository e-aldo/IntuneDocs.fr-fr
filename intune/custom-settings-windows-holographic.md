---
title: "Paramètres personnalisés Microsoft Intune pour les appareils Windows Holographic for Business"
titlesuffix: 
description: "Découvrez les paramètres que vous pouvez utiliser dans un profil personnalisé Windows Holographic for Business."
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 3/6/2018
ms.article: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b95d891d1dfaecbce182fde4a2221255a7e1eb06
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/08/2018
---
# <a name="microsoft-intune-custom-device-settings-for-devices-running-windows-holographic-for-business"></a>Paramètres personnalisés pour les appareils Microsoft Intune pour les appareils exécutant Windows Holographic for Business

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

 Utilisez le profil Microsoft Intune **personnalisé** pour Windows Holographic for Business pour déployer des paramètres OMA-URI (Open Mobile Alliance Uniform Resource Identifier) pouvant servir à contrôler les fonctionnalités sur des appareils. Windows Holographic for Business rend disponibles de nombreux paramètres de fournisseurs de services de configuration. Pour avoir une vue d’ensemble des fournisseur de services de configuration, consultez [Présentation des fournisseurs de services de configuration pour les professionnels de l’informatique](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers). Pour connaître les fournisseurs de services de configuration pris en charge par Windows Holographique, consultez [Fournisseurs de services de configuration pris en charge dans Windows Holographique](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens).

Si vous recherchez un paramètre particulier, n’oubliez pas que le [profil de restriction d’appareil Windows Holographic for Business](device-restrictions-windows-holographic.md) contient de nombreux paramètres intégrés et ne nécessite pas de spécifier des valeurs personnalisées.

1. Suivez les instructions figurant dans [Configuration de paramètres d'appareil personnalisés dans Microsoft Intune](custom-settings-configure.md) pour commencer.
2. Dans **Créer un profil**, choisissez **Paramètres** pour ajouter un ou plusieurs paramètres OMA-URI.
3. Dans **Paramètres OMA-URI personnalisés**, cliquez sur **Ajouter** pour ajouter une nouvelle valeur. Vous pouvez également cliquer sur **Exporter** pour créer une liste de toutes les valeurs que vous avez configurées dans un fichier de valeurs séparées par des virgules (.csv).
4. Pour chaque paramètre OMA-URI à ajouter, entrez les informations suivantes :
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
1. Quand vous avez terminé, revenez à **Créer un profil** et cliquez sur **Créer**.
Le profil est créé et apparaît dans la liste des profils.

## <a name="recommended-custom-settings"></a>Paramètres personnalisés recommandés

Les paramètres suivants sont utiles pour les appareils exécutant Windows Holographic for Business :


|Nom du paramètre|OMA-URI|Type de données  |
|---------|---------|---------|
|[AllowFastReconnect](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-authentication#authentication-allowfastreconnect)|./Vendor/MSFT/Policy/Config/Authentication/AllowFastReconnect|Entier<br>0 : Non autorisé<br>1 : Autorisé (par défaut)|
|[AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn)|./Vendor/MSFT/Policy/Config/Settings/AllowVPN|Entier<br>0 : Non autorisé<br>1 : Autorisé (par défaut)|
|[AllowUpdateService](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowupdateservice)|./Vendor/MSFT/Policy/Config/Update/AllowUpdateService|Entier<br>0 : Le service de mise à jour n’est pas autorisé <br>1 – Le service de mise à jour est autorisé (par défaut)|
|[UpdateServiceURL](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-updateserviceurl)|./Vendor/MSFT/Policy/Config/Update/UpdateServiceUrl|Chaîne<br>URL : L’appareil vérifie l’existence de mises à jour auprès du serveur WSUS à l’URL spécifiée.<br>Non configuré : L’appareil vérifie l’existence de mises à jour auprès de Microsoft Update.|
|[RequireUpdatesApproval](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-requireupdateapproval)|./Vendor/MSFT/Policy/Config/Update/RequireUpdateApproval|Entier<br>0 : Non configuré L’appareil installe toutes les mises à jour applicables.<br>1 – L’appareil installe seulement les mises à jour applicables qui figurent dans la liste des mises à jour approuvées. Définissez cette stratégie sur 1 si le département informatique veut contrôler le déploiement des mises à jour sur les appareils, par exemple quand des tests sont nécessaires avant un déploiement.|
|[ApprovedUpdates](https://docs.microsoft.com/windows/client-management/mdm/update-csp)|./Vendor/MSFT/Update/ApprovedUpdates<br><br>**Important**<br>Vous devez lire et accepter le CLUF de la mise à jour pour le compte de vos utilisateurs finaux. Ne pas le faire constitue une violation des obligations légales ou contractuelles.|Nœud pour les approbations des mises à jour et l’acceptation du CLUF pour le compte de l’utilisateur final.|
[ApplicationLaunchRestrictions](https://docs.microsoft.com/windows/client-management/mdm/applocker-csp)|./Vendor/MSFT/AppLocker/ApplicationLaunchRestrictions/*Grouping*/*ApplicationType*/Policy<br><br>**Important**<br>L’article Fournisseur de services de configuration AppLocker utilise des exemples XML avec une séquence d’échappement. Pour configurer les paramètres avec des profils personnalisés Intune, vous devez utiliser du XML brut.|Chaîne<br>Pour plus d’informations, consultez l’article [Fournisseur de services de configuration AppLocker](https://docs.microsoft.com/windows/client-management/mdm/applocker-csp). 

## <a name="how-to-find-the-policies-you-can-configure"></a>Comment trouver les stratégies que vous pouvez configurer

La liste complète de tous les fournisseurs de services de configuration pris en charge par Windows Holographique est disponible dans [Fournisseurs de services de configuration pris en charge dans Windows Holographique](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens). Les paramètres ne sont pas tous compatibles avec toutes les versions de Windows Holographique. Le tableau de l’article Windows indique quelles versions sont prises en charge pour chaque fournisseur de services de configuration.

En outre, Intune ne prend pas en charge tous les paramètres mentionnés dans l’article. Pour savoir si Intune prend en charge le paramètre de votre choix, ouvrez l’article relatif à ce paramètre. Chaque page de paramètre indique ses opérations prises en charge. Pour fonctionner avec Intune, le paramètre doit prendre en charge les opérations **Ajouter** ou **Remplacer**.
