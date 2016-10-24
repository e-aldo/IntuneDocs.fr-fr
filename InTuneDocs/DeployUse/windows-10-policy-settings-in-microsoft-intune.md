---
title: "Paramètres de la stratégie dans Windows 10 | Microsoft Intune"
description: "Utilisez les paramètres de stratégie de cette rubrique pour configurer les paramètres intégrés et personnalisés des appareils Windows 10 Mobile et Windows 10 Desktop inscrits."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 10/03/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 00a602d9-b339-4fd8-ab70-defbf6686855
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b8522406a3c73746b09616c3ec917464cf751312
ms.openlocfilehash: 6e482beb5e2edce648ecb6f1821baa6214fa0f2f


---

# Paramètres de stratégie Intune pour les appareils Windows 10 dans Microsoft Intune

Cette rubrique contient des informations qui vous aideront à comprendre les paramètres de stratégie Intune que vous pouvez utiliser pour gérer des appareils Windows 10. Lisez cette rubrique parallèlement aux procédures indiquées dans [Gérer des paramètres et des fonctionnalités sur vos appareils avec des stratégies Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies) pour configurer des paramètres intégrés et personnalisés sur les appareils Windows 10 Desktop et Windows 10 Mobile inscrits. Vous ne pouvez pas utiliser ces stratégies avec des ordinateurs qui exécutent le [logiciel client des PC Intune](/intune/get-started/windows-pc-management-capabilities-in-microsoft-intune).

Vous pouvez choisir parmi deux types de stratégie :

- **Stratégie personnalisée** : Utilisez la **stratégie personnalisée** Microsoft Intune pour Windows 10 et Windows 10 Mobile pour déployer des paramètres OMA-URI (Open Mobile Alliance Uniform Resource Identifier) qui peuvent être utilisés pour contrôler les fonctionnalités sur les appareils. Dans Windows 10, de nombreux paramètres sont disponibles par le biais du [fournisseur de services de configuration de stratégie](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers).
- **Stratégie de configuration générale** : Utilisez ce type de stratégie quand vous voulez sélectionner des paramètres à partir d’une liste prédéfinie fournie dans Microsoft Intune.

## Paramètres de la stratégie personnalisée

Fournissez les paramètres suivants dans une stratégie personnalisée :

## &nbsp;&nbsp;&nbsp;Général

Entrez un nom et éventuellement une description pour cette stratégie afin de vous permettre de l’identifier dans la console Intune.

## &nbsp;&nbsp;&nbsp;Paramètres OMA-URI

Pour chaque paramètre OMA-URI à ajouter, entrez les informations suivantes. Utilisez les [informations de référence sur les paramètres d’URI Windows 10](/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune#Windows-10-URI-settings) données dans cette rubrique pour connaître les paramètres que vous pouvez utiliser : 

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

### Exemple
Dans la capture d’écran ci-dessous, le paramètre **Connectivity/AllowVPNOverCellular** a été activé. Il permet à un appareil Windows 10 d’ouvrir une connexion VPN sur un réseau de téléphonie mobile.

> ![Exemple de stratégie personnalisée contenant des paramètres VPN](./media/custom-policy-example.png)

## Paramètres d’URI Windows 10
Utilisez cette section pour en savoir plus sur les paramètres OMA-URI que vous pouvez configurer avec une **stratégie personnalisée Windows 10**.

## &nbsp;&nbsp;&nbsp;Stratégie

|Nom de la stratégie et URI|Détails|
|---------------|------------|-----------|
|**AllowAutoUpdate**<br>./Vendor/MSFT/Policy/Config/Update/AllowAutoUpdate|Desktop uniquement<br>**Type de données :** Entier<br />**Valeurs :** **0** - **5** (valeur par défaut : **1**)|
|**ScheduledInstallDay**<br>./Vendor/MSFT/Policy/Config/Update/ScheduledInstallDay|Mobile uniquement<br>**Type de données :** Entier<br />**Valeurs :**<br>**0** - Tous les jours (par défaut)<br>**1** - Dimanche<br>**2** - Lundi<br>**3** - Mardi<br>**4** - Mercredi<br>**5** - Jeudi<br>**6** - Vendredi<br>**7** - Samedi|
|**ScheduledInstallTime**<br>./Vendor/MSFT/Policy/Config/Update/ScheduledInstallTime|Desktop et mobile<br />**Type de données :** Entier<br />**Valeurs :** **0** – **23** heures (**0** correspond à minuit) (par défaut : **3**)|
|**DeviceLock/AllowIdleReturnWithoutPassword**<br>./Vendor/MSFT/Policy/Config/DeviceLock/AllowIdleReturnWithoutPassword|Mobile uniquement<br />**Type de données :** Entier<br />**Valeurs :**<br>**0** : L’utilisateur ne peut pas définir le minuteur de la période de grâce du mot de passe ; la valeur est « à chaque fois ».<br>**1** : L’utilisateur peut définir le minuteur de la période de grâce du mot de passe (valeur par défaut).|
|**WiFi/AllowWiFi**<br>./Vendor/MSFT/Policy/Config/WiFi/AllowWiFi|Mobile uniquement<br />**Type de données :** Entier<br />**Valeurs :**<br>**0** – Ne pas autoriser **Utiliser la connexion Wi-Fi**.<br>**1** –**Autoriser l’utilisation de la connexion Wi-Fi** (par défaut).|
|**WiFi/AllowInternetSharing**<br>./Vendor/MSFT/Policy/Config/WiFi/AllowInternetSharing|Desktop et mobile<br>**Type de données :** Entier<br />**Valeurs :** **0** – Ne pas autoriser le partage Internet **1** – Autoriser le partage Internet (valeur par défaut)|
|**WiFi/AllowAutoConnectToWiFiSenseHotspots**<br>./Vendor/MSFT/Policy/Config/WiFi/AllowAutoConnectToWiFiSenseHotspots|Desktop et mobile<br />**Type de données :** Entier<br />**Valeurs :** **0** – non autorisé, **1** – autorisé (valeur par défaut)|
|**WiFi/AllowManualWiFiConfiguration**<br>./Vendor/MSFT/Policy/Config/WiFi/AllowManualWiFiConfiguration|Mobile uniquement<br />**Type de données :** Entier<br />**Valeurs :**<br>**0** – Aucune connexion non-Wi-Fi en dehors de celles approvisionnées par la Gestion des appareils mobiles n’est autorisée.<br>**1** – L’ajout de nouveaux SSID réseau au-delà de ceux approvisionnés par MDM est autorisé (par défaut).|
|**System/AllowLocation**<br>./Vendor/MSFT/Policy/Config/System/AllowLocation|Desktop et mobile<br />**Type de données :** Entier<br />**Valeurs :** **0** – non autorisé, **1** – autorisé (valeur par défaut)|
|**System/AllowTelemetry**<br>./Vendor/MSFT/Policy/Config/System/AllowTelemetry|Desktop et mobile<br>**Type de données :** Entier<br />**Valeurs :**<br>**0** – Non autorisé (paramètre Entreprise uniquement)<br>**1** – Limité<br>**2** – Complet (par défaut)<br>**3** – Complet et informations de diagnostic|
|**System/AllowExperimentation**<br>./Vendor/MSFT/Policy/Config/System/AllowExperimentation|Desktop et mobile<br />**Type de données :** Entier<br />**Valeurs :**<br>**0** – Non autorisé<br>**1** – Paramètres uniquement (par défaut)<br>**2** – Paramètres et expérimentation|
|**Security/AntiTheftMode**<br>./Vendor/MSFT/Policy/Config/Security/AntiTheftMode|Mobile uniquement<br />**Type de données :** Entier<br />**Valeurs :**<br>**0** – Ne pas autoriser le mode antivol<br>**1** – Préférence utilisateur (par défaut)|
|**Connectivity/AllowUSBConnection**<br>./Vendor/MSFT/Policy/Config/Connectivity/AllowUSBConnection|Mobile uniquement<br />**Type de données :** Entier<br />**Valeurs :** **0** – non autorisé, **1** – autorisé (valeur par défaut)|
|**System/AllowUserToResetPhone**<br>./Vendor/MSFT/Policy/Config/System/AllowUserToResetPhone|Mobile uniquement<br />**Type de données :** Entier<br />**Valeurs :** **0** – non autorisé, **1** – autorisé (valeur par défaut)|
|**Connectivity/AllowCellularDataRoaming**<br>./Vendor/MSFT/Policy/Config/Connectivity/AllowCellularDataRoaming|Desktop et mobile<br />**Type de données :** Entier<br />**Valeurs :** **0** – non autorisé, **1** – autorisé (valeur par défaut)|
|**Connectivity/AllowVPNOverCellular**<br>./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNOverCellular|Desktop et mobile<br />**Type de données :** Entier<br />**Valeurs :**<br>**0** – Un VPN n’est pas autorisé sur une connexion cellulaire.<br>**1** – Un VPN peut utiliser n’importe quelle connexion, y compris une connexion cellulaire (par défaut).|
|**Connectivity/AllowVPNRoamingOverCellular**<br>./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNRoamingOverCellular|Mobile uniquement<br />**Type de données :** Entier<br />**Valeurs :** **0** – non autorisé, **1** – autorisé (valeur par défaut)|
|**Connectivity/AllowVPNRoamingOverCellular**<br>./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNRoamingOverCellular|Mobile uniquement<br />**Type de données :** Entier<br />**Valeurs :** **0** – non autorisé, **1** – autorisé (valeur par défaut)|
|**Connectivity/AllowBluetooth**<br>./Vendor/MSFT/Policy/Config/Connectivity/AllowBluetooth|Desktop et mobile<br />**Type de données :** Entier<br />**Valeurs :**<br>**0** – Ne pas autoriser l'utilisateur à activer le Bluetooth.<br>**1** – Réservé. L'utilisateur peut activer et configurer le Bluetooth (non pris en charge dans Windows Phone 8.1 pour MDM, EAS, Windows 10 Desktop ou Windows 10 Mobile)<br>**2** - Autorisé. L’utilisateur peut activer et configurer le Bluetooth (par défaut).|
|**Experience/AllowScreenCapture**<br>./Vendor/MSFT/Policy/Config/Experience/AllowScreenCapture|Mobile uniquement<br />**Type de données :** Entier<br />**Valeurs :** **0** – non autorisé, **1** – autorisé (valeur par défaut)|
|**Experience/AllowTaskSwitcher**<br>./Vendor/MSFT/Policy/Config/Experience/AllowTaskSwitcher|Mobile uniquement<br />**Type de données :** Entier<br />**Valeurs :** **0** – non autorisé, **1** – autorisé (valeur par défaut)|
|**Experience/AllowVoiceRecording**<br>./Vendor/MSFT/Policy/Config/Experience/AllowVoiceRecording|Mobile uniquement<br />**Type de données :** Entier<br />**Valeurs :** **0** – non autorisé, **1** – autorisé (valeur par défaut)|
|**Experience/AllowSyncMySettings**<br>./Vendor/MSFT/Policy/Config/Experience/AllowSyncMySettings|Mobile uniquement<br />**Type de données :** Entier<br />**Valeurs :** **0** – Ne pas autoriser l’itinérance, **1** – Autoriser l’itinérance (valeur par défaut)|
|**Experience/AllowManualMDMUnenrollment**<br>./Vendor/MSFT/Policy/Config/Experience/AllowManualMDMUnenrollment|Desktop et mobile<br />**Type de données :** Entier<br />**Valeurs :** **0** – non autorisé, **1** – autorisé (valeur par défaut)|
|**Accounts/AllowMicrosoftAccountConnection**<br>./Vendor/MSFT/Policy/Config/Accounts/AllowMicrosoftAccountConnection|Desktop et mobile<br />**Type de données :** Entier<br />**Valeurs :** **0** – non autorisé, **1** – autorisé (valeur par défaut)|
|**Accounts/AllowAddingNonMicrosoftAccountsManually**<br>./Vendor/MSFT/Policy/Config/Accounts/AllowAddingNonMicrosoftAccountsManually|Desktop et mobile<br />**Type de données :** Entier<br />**Valeurs :** **0** – non autorisé, **1** – autorisé (valeur par défaut)|
|**Security/AllowManualRootCertificateInstallation**<br>./Vendor/MSFT/Policy/Config/Security/AllowManualRootCertificateInstallation|Mobile uniquement<br />**Type de données :** Entier<br />**Valeurs :** **0** – non autorisé, **1** – autorisé (valeur par défaut)|
|**Security/AllowAddProvisioningPackages**<br>./Vendor/MSFT/Policy/Config/Security/AllowAddProvisioningPackages|Desktop et mobile<br />**Type de données :** Entier<br />**Valeurs :** **0** – non autorisé, **1** – autorisé (valeur par défaut)|
|**Search/DisableBackoff**<br>./Vendor/MSFT/Policy/Config/Search/DisableBackoff|Desktop et mobile<br />**Type de données :** Entier<br />**Valeurs :** **0** (valeur par défaut), **1**|
|**Search/PreventRemoteQueries**<br>./Vendor/MSFT/Policy/Config/Search/PreventRemoteQueries|Desktop et mobile<br />**Type de données :** Entier<br />**Valeurs :** **0**, **1** (valeur par défaut)|
|**Search/AllowUsingDiacritics**<br>./Vendor/MSFT/Policy/Config/Search/AllowUsingDiacritics|Desktop et mobile<br />**Type de données :** Entier<br />**Valeurs :** **0** (valeur par défaut), **1**|
|**Search/AlwaysUseAutoLangDetection**<br>./Vendor/MSFT/Policy/Config/Search/AlwaysUseAutoLangDetection|Desktop et mobile<br />**Type de données :** Entier<br />**Valeurs :** **0** (valeur par défaut), **1**|
|**Search/DisableRemovableDriveIndexing**<br>./Vendor/MSFT/Policy/Config/Search/DisableRemovableDriveIndexing|Desktop et mobile<br />**Type de données :** Entier<br />**Valeurs :** **0** (valeur par défaut), **1**|
|**Search/PreventIndexingLowDiskSpaceMB**<br>./Vendor/MSFT/Policy/Config/Search/PreventIndexingLowDiskSpaceMB|Desktop et mobile<br />**Type de données :** Entier<br />**Valeurs :** **0**, **1** (valeur par défaut)|
|**Search/AllowIndexingEncryptedStoresOrItems**<br>./Vendor/MSFT/Policy/Config/Search/AllowIndexingEncryptedStoresOrItems|Desktop et mobile<br />**Type de données :** Entier<br />**Valeurs :** **0** (valeur par défaut), **1**|
|**Security/AllowRemoveProvisioningPackage**<br>./Vendor/MSFT/Policy/Config/Security/AllowRemoveProvisioningPackage|Desktop et mobile<br />**Type de données :** Entier<br />**Valeurs :** **0** – non autorisé, **1** – autorisé (valeur par défaut)|
|**Security/RequireProvisioningPackageSignature**<br>./Vendor/MSFT/Policy/Config/Security/RequireProvisioningPackageSignature|Desktop et mobile<br />**Type de données :** Entier<br />**Valeurs :** **0** (valeur par défaut), **1**|
|**AboveLock/AllowActionCenterNotifications**<br>./Vendor/MSFT/Policy/Config/AboveLock/AllowActionCenterNotifications|Desktop et mobile<br />**Type de données :** Entier<br />**Valeurs :** **0** – non autorisé, **1** – autorisé (valeur par défaut)|
|**TextInput/AllowIMENetworkAccess**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowIMENetworkAccess|Desktop uniquement<br />**Type de données :** Entier<br />**Valeurs :**<br>**0** – Ne pas autoriser<br>L'ouverture du dictionnaire étendu est désactivée.<br>Un utilisateur ne peut pas :<br>- Ajouter un nouveau dictionnaire étendu ouvert<br />- Ajouter un nouveau fichier de configuration d’intégration de la recherche<br>- Utiliser la fonctionnalité de candidat de cloud<br>- Envoyer un mot inscrit par l’utilisateur<br>**1** - Autoriser<br>Un dictionnaire étendu ouvert peut être ajouté et utilisé par défaut. Par ailleurs, la fonction d'intégration de la recherche peut être utilisée par défaut.<br>Un utilisateur peut :<br>Utiliser la fonctionnalité de candidat de cloud.|
|**TextInput/AllowIMELogging**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowIMELogging|Desktop uniquement<br />**Type de données :** Entier<br />**Valeurs :**<br>**0** - La journalisation des erreurs de conversion est désactivée.<br>**1** - La journalisation des erreurs de conversion est activée (valeur par défaut).|
|**TextInput/AllowJapaneseNonPublishingStandardGlyph**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseNonPublishingStandardGlyph|Desktop uniquement<br />**Type de données :** Entier<br />**Valeurs :** **0** – non autorisé, **1** – autorisé (valeur par défaut)|
|**TextInput/AllowJapaneseIVSCharacters**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseIVSCharacters|Desktop uniquement<br />**Type de données :** Entier<br />**Valeurs :** **0** – non autorisé, **1** – autorisé (valeur par défaut)|
|**TextInput/AllowJapaneseUserDictionary**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseUserDictionary|Desktop uniquement<br />**Type de données :** Entier<br />**Valeurs :** **0** – non autorisé, **1** – autorisé (valeur par défaut)|
|**TextInput/AllowJapaneseIMESurrogatePairCharacters**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseIMESurrogatePairCharacters|Desktop uniquement<br />**Type de données :** Entier<br />**Valeurs :** **0** – non autorisé, **1** – autorisé (valeur par défaut)|
|**TextInput/ExcludeJapaneseIMEExceptShiftJIS**<br>./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptShiftJIS|Desktop uniquement<br />**Type de données :** Entier<br />**Valeurs :**<br>**0** – Aucun caractère n’est filtré (par défaut).<br>**1** – Tous les caractères sont filtrés, sauf les caractères Shift-JIS.|
|**TextInput/ExcludeJapaneseIMEExceptJIS0208**<br>./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptJIS0208|Desktop uniquement<br />**Type de données :** Entier<br />**Valeurs :**<br />**0** – Aucun caractère n’est filtré (par défaut).<br>**1** – Tous les caractères sont filtrés, sauf les caractères JIS0208.|
|**TextInput/ExcludeJapaneseIMEExceptJIS0208andEUDC**<br>./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptJIS0208andEUDC|Desktop uniquement<br />**Type de données :** Entier<br />**Valeurs :**<br>**0** – Aucun caractère n’est filtré (par défaut).<br>**1** – Tous les caractères sont filtrés, sauf les caractères JIS0208 ou EUDC.|
|**TextInput/AllowInputPanel**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowInputPanel|Desktop uniquement<br />**Type de données :** Entier<br />**Valeurs :** **0** – non autorisé, **1** – autorisé (valeur par défaut)|
|**Bluetooth/AllowDiscoverableMode**<br>./Vendor/MSFT/Policy/Config/Bluetooth/AllowDiscoverableMode|Desktop et mobile<br />**Type de données :** Entier<br />**Valeurs :** **0** – non autorisé, **1** – autorisé (valeur par défaut)|
|**Bluetooth/AllowAdvertising**<br>./Vendor/MSFT/Policy/Config/Bluetooth/AllowAdvertising|Desktop et mobile<br />**Type de données :** Entier<br />**Valeurs :** **0** – non autorisé, **1** – autorisé (valeur par défaut)|
|**Settings/AllowDataSense**<br>./Vendor/MSFT/Policy/Config/Settings/AllowDataSense|Desktop et mobile<br />**Type de données :** Entier<br />**Valeurs :** **0** – non autorisé, **1** – autorisé (valeur par défaut)|
|**Settings/AllowVPN**<br>./Vendor/MSFT/Policy/Config/Settings/AllowVPN|Desktop et mobile<br />**Type de données :** Entier<br />**Valeurs :** **0** – non autorisé, **1** – autorisé (valeur par défaut)|
|**Settings/AllowWorkplace**<br>./Vendor/MSFT/Policy/Config/Settings/AllowWorkplace|Desktop uniquement<br />**Type de données :** Entier<br />**Valeurs :** **0** – non autorisé, **1** – autorisé (valeur par défaut)|
|**Settings/AllowDateTime**<br>./Vendor/MSFT/Policy/Config/Settings/AllowDateTime|Desktop et mobile<br />**Type de données :** Entier<br />**Valeurs :** **0** – non autorisé, **1** – autorisé (valeur par défaut)|
|**Settings/AllowLanguage**<br>./Vendor/MSFT/Policy/Config/Settings/AllowLanguage|Desktop uniquement<br />**Type de données :** Entier<br />**Valeurs :** **0** – non autorisé, **1** – autorisé (valeur par défaut)|
|**Settings/AllowRegion**<br>./Vendor/MSFT/Policy/Config/Settings/AllowRegion|Desktop uniquement<br />**Type de données :** Entier<br />**Valeurs :** **0** – non autorisé, **1** – autorisé (valeur par défaut)|
|**Settings/AllowSignInOptions**<br>./Vendor/MSFT/Policy/Config/Settings/AllowSignInOptions|Desktop uniquement<br />**Type de données :** Entier<br />**Valeurs :** **0** – non autorisé, **1** – autorisé (valeur par défaut)|
|**Settings/AllowYourAccount**<br>./Vendor/MSFT/Policy/Config/Settings/AllowYourAccount|Desktop et mobile<br />**Type de données :** Entier<br />**Valeurs :** **0** – non autorisé, **1** – autorisé (valeur par défaut)|
|**Settings/AllowPowerSleep**<br>./Vendor/MSFT/Policy/Config/Settings/AllowPowerSleep|Desktop uniquement<br />**Type de données :** Entier<br />**Valeurs :** **0** – non autorisé, **1** – autorisé (valeur par défaut)|
|**Settings/AllowAutoPlay**<br>./Vendor/MSFT/Policy/Config/Settings/AllowAutoPlay|Desktop uniquement<br />**Type de données :** Entier<br />**Valeurs :** **0** – non autorisé, **1** – autorisé (valeur par défaut)|
|**Experience/AllowCortana**<br>./Vendor/MSFT/Policy/Config/Experience/AllowCortana|Desktop et mobile<br />**Type de données :** Entier<br />**Valeurs :** **0** – non autorisé, **1** – autorisé (valeur par défaut)|
|**Search/SafeSearchPermissions**<br>./Vendor/MSFT/Policy/Config/Search/SafeSearchPermissions|Mobile uniquement<br />**Type de données :** Entier<br />**Valeurs :**<br>**0** – Strict, niveau de filtrage le plus élevé en matière de contenu pour adultes.<br>**1** – Modéré, niveau de filtrage modéré en matière de contenu pour adultes (les résultats de recherche valides ne sont pas filtrés – par défaut).|
|**Experience/AllowCopyPaste**<br>./Vendor/MSFT/Policy/Config/Experience/AllowCopyPaste|Desktop uniquement<br />**Type de données :** Entier<br />**Valeurs :** **0** – non autorisé, **1** – autorisé (valeur par défaut)|
|**ForceStartSize**<br>./Vendor/MSFT/Policy/Config/Start/ForceStartSize|Mobile uniquement<br />**Type de données :** Entier<br />**Valeurs :**<br>**0** – Autoriser l’utilisateur à modifier la taille (par défaut).<br>**1** - Forcer un affichage n’utilisant pas le plein écran.<br>**1** - Forcer le plein écran.|
|**Update/RequireDeferUpgrade**<br>./Vendor/MSFT/Policy/Config/Update/RequireDeferUpgrade|Desktop et mobile<br />**Type de données :** Entier<br />**Valeurs :**<br>**0** : ne pas reporter la mise à niveau (rester dans la branche active, CB – par défaut)<br>**1** : activer le report des mises à jour et des mises à niveau (l’appareil suit les règles de la branche actuelle d’entreprise, CBB)<br />Pour plus d'informations, consultez :<br>[Introduction à la maintenance de Windows 10](https://technet.microsoft.com/library/mt598226.aspx)<br>[Plan de déploiement de Windows 10](https://technet.microsoft.com/library/mt574241.aspx)|
|**Update/DeferUpdatePeriod**<br>./Vendor/MSFT/Policy/Config/Update/DeferUpdatePeriod|Desktop et mobile<br>**Description :** stratégie de report des mises à jour logicielles pendant quatre semaines<br />**Type de données :** Entier<br />**Valeurs :**<br> **0** : appliquer immédiatement les mises à jour (par défaut)<br>**1**-**4** : nombre de semaines de report des mises à jour logicielles.<br />Pour plus d'informations, consultez :<br>[Introduction à la maintenance de Windows 10](https://technet.microsoft.com/library/mt598226.aspx)<br>[Plan de déploiement de Windows 10](https://technet.microsoft.com/library/mt574241.aspx)|
|**Update/DeferUpgradePeriod**<br>./Vendor/MSFT/Policy/Config/Update/DeferUpgradePeriod|Desktop et mobile<br>**Description :** stratégie de report des mises à niveau des fonctionnalités jusqu’à huit mois<br />**Type de données :** Entier<br />**Valeurs :**<br>**0** : appliquer immédiatement les mises à jour (par défaut)<br>**1**-**8** : nombre de mois de report des mises à niveau des fonctionnalités.<br />Pour plus d'informations, consultez :<br>[Introduction à la maintenance de Windows 10](https://technet.microsoft.com/library/mt598226.aspx)<br>[Plan de déploiement de Windows 10](https://technet.microsoft.com/library/mt574241.aspx)|
|**Update/PauseDeferrals**<br>./Vendor/MSFT/Policy/Config/Update/PauseDeferrals|Desktop et mobile<br>**Description :** Autorise un appareil à cesser de recevoir des mises à jour et des mises à niveau pendant cinq semaines.<br />**Type de données :** Entier<br />**Valeurs :**<br>**0** : appliquer immédiatement les mises à jour (par défaut)<br>**1** : suspendre les mises à jour et les mises à niveau (expire au bout de cinq semaines)|

## &nbsp;&nbsp;&nbsp;Windows Defender

|Nom de la stratégie et URI|Détails|
|---------------|-----------|
|**AllowRealtimeMonitoring**<br>./Vendor/MSFT/Policy/Config/Defender/AllowRealtimeMonitoring|Desktop uniquement<br />**Type de données :** Entier<br />**Valeurs :** **0** – non autorisé, **1** – autorisé (valeur par défaut)|
|**AllowBehaviorMonitoring**<br>./Vendor/MSFT/Policy/Config/Defender/AllowBehaviorMonitoring|Desktop uniquement<br />**Type de données :** Entier<br />**Valeurs :** **0** – non autorisé, **1** – autorisé (valeur par défaut)|
|**AllowIntrusionPreventionSystem**<br>./Vendor/MSFT/Policy/Config/Defender/AllowIntrusionPreventionSystem|Desktop uniquement<br />**Type de données :** Entier<br />**Valeurs :** **0** – non autorisé, **1** – autorisé (valeur par défaut)|
|**AllowIOAVProtection**<br>./Vendor/MSFT/Policy/Config/Defender/AllowIOAVProtection|Desktop uniquement<br />**Type de données :** Entier<br />**Valeurs :** **0** – non autorisé, **1** – autorisé (valeur par défaut)|
|**AllowScriptScanning**<br>./Vendor/MSFT/Policy/Config/Defender/AllowScriptScanning|Desktop uniquement<br />**Type de données :** Entier<br />**Valeurs :** **0** – non autorisé, **1** – autorisé (valeur par défaut)|
|**AllowOnAccessProtection**<br>./Vendor/MSFT/Policy/Config/Defender/AllowOnAccessProtection|Desktop uniquement<br />**Type de données :** Entier<br />**Valeurs :** **0** – non autorisé, **1** – autorisé (valeur par défaut)|
|**RealTimeScanDirection**<br>./Vendor/MSFT/Policy/Config/Defender/RealTimeScanDirection|Desktop uniquement<br />**Type de données :** Entier<br />**Valeurs :**<br>**0** – Analyser tous les fichiers (valeur par défaut)<br>**1** – Analyser les fichiers entrants<br>**2** – Analyser les fichiers sortants|
|**DaysToRetainCleanedMalware**<br>./Vendor/MSFT/Policy/Config/Defender/DaysToRetainCleanedMalware|Desktop uniquement<br />**Type de données :** Entier<br />**Valeurs :**<br>**0** - **90** – Représente la durée pendant laquelle les logiciels malveillants sont conservés.<br>**Valeur par défaut :** **0** – Les logiciels malveillants sont conservés indéfiniment dans le dossier de quarantaine et ne sont pas supprimés automatiquement.|
|**AllowUserUIAccess**<br>./Vendor/MSFT/Policy/Config/Defender/AllowUserUIAccess|Desktop uniquement<br />**Type de données :** Entier<br />**Valeurs :** **0** – non autorisé, **1** – autorisé (valeur par défaut)|
|**ScanParameter**<br>./Vendor/MSFT/Policy/Config/Defender/ScanParameter|Desktop uniquement<br />**Type de données :** Entier<br />**Valeurs :**<br>**1** – Analyse rapide (par défaut)<br>**2** – Analyse complète|
|**ScheduleScanDay**<br>./Vendor/MSFT/Policy/Config/Defender/ScheduleScanDay|Desktop uniquement<br />**Type de données :** Entier<br />**Valeurs :**<br>**0** – Tous les jours (par défaut)<br>**1** - Lundi<br>**2** - Mardi<br>**3** - Mercredi<br>**4** - Jeudi<br>**5** - Vendredi<br>**6** - Samedi<br>**7** - Dimanche<br>**8** - Aucune analyse planifiée|
|**ScheduleScanTime**<br>./Vendor/MSFT/Policy/Config/Defender/ScheduleScanTime|Desktop uniquement<br />**Type de données :** Entier<br />**Valeurs :**<br>**0** – 00:00<br>**60** – 1:00<br>**120** – 2:00 (par défaut)<br>**180** – 3:00<br>**240** – 4:00<br>**300** – 5:00<br>**360** – 6:00<br>**420** – 7:00<br>**480** – 8:00<br>**540** – 9:00<br>**600** – 10:00<br>**660** – 11:00<br>**720** – 12:00<br>**780** – 13:00<br>**840** – 14:00<br>**900** – 15:00<br>**960** – 16:00<br>**1020** – 17:00<br>**1080** – 18:00<br>**1140** – 19:00<br>**1200** – 20:00<br>**1260** – 21:00<br>**1320** – 22:00<br>**1381** – Fenêtre de maintenance|
|**ScheduleQuickScanTime**<br>./Vendor/MSFT/Policy/Config/Defender/ScheduleQuickScanTime|Desktop uniquement<br>**Type de données :** Entier<br />**Valeurs :**<br>**0** – 00:00<br>**60** – 1:00<br>**120** – 2:00 (par défaut)<br>**180** – 3:00<br>**240** – 4:00<br>**300** – 5:00<br>**360** – 6:00<br>**420** – 7:00<br>**480** – 8:00<br>**540** – 9:00<br>**600** – 10:00<br>**660** – 11:00<br>**720** – 12:00<br>**780** – 13:00<br>**840** – 14:00<br>**900** – 15:00<br>**960** – 16:00<br>**1020** – 17:00<br>**1080** – 18:00<br>**1140** – 19:00<br>**1200** – 20:00<br>**1260** – 21:00<br>**1320** – 22:00<br>**1380** – 23:00|
|**AVGCPULoadFactor**<br>./Vendor/MSFT/Policy/Config/Defender/AVGCPULoadFactor|Desktop uniquement<br />**Type de données :** Entier<br />**Valeurs :** **0** - **100** (valeur par défaut : **50**)|
|**AllowArchiveScanning**<br>./Vendor/MSFT/Policy/Config/Defender/AllowArchiveScanning|Desktop uniquement<br />**Type de données :** Entier<br />**Valeurs :** **0** – non autorisé, **1** – autorisé (valeur par défaut)|
|**AllowEmailScanning**<br>./Vendor/MSFT/Policy/Config/Defender/AllowEmailScanning|Desktop uniquement<br />**Type de données :** Entier<br>**Valeurs :** **0** – non autorisé (valeur par défaut), **1** – autorisé|
|**AllowFullScanRemovableDriveScanning**<br>./Vendor/MSFT/Policy/Config/Defender/AllowFullScanRemovableDriveScanning|Desktop uniquement<br />**Type de données :** Entier<br />**Valeurs :** **0** – non autorisé (valeur par défaut), **1** – autorisé|
|**AllowFullScanOnMappedNetworkDrives**<br>./Vendor/MSFT/Policy/Config/Defender/AllowFullScanOnMappedNetworkDrives|Desktop uniquement<br />**Type de données :** Entier<br />**Valeurs :** **0** – non autorisé, **1** – autorisé (valeur par défaut)|
|**AllowScanningNetworkFiles**<br>./Vendor/MSFT/Policy/Config/Defender/AllowScanningNetworkFiles|Desktop uniquement<br />**Type de données :** Entier<br />**Valeurs :** **0** – non autorisé, **1** – autorisé (valeur par défaut) – s’exécute également quand le protocole RTP est activé, si défini sur autorisé|
|**SignatureUpdateInterval**<br>./Vendor/MSFT/Policy/Config/Defender/SignatureUpdateInterval|Desktop uniquement<br />**Type de données :** Entier<br />**Valeurs :**<br>**0** – Ne pas vérifier les signatures par intervalle<br>**1** – Vérifier les signatures toutes les heures<br>**2** – Vérifier toutes les 2 heures, etc.<br>**24** – Vérifier tous les jours<br>**Valeur par défaut :** 8 – vérifier toutes les 8 heures|
|**AllowCloudProtection**<br>./Vendor/MSFT/Policy/Config/Defender/AllowCloudProtection|Desktop uniquement<br />**Type de données :** Entier<br />**Valeurs :** **0** – non autorisé, **1** – autorisé (valeur par défaut)|
|**SubmitSamplesConsent**<br>./Vendor/MSFT/Policy/Config/Defender/SubmitSamplesConsent|Desktop uniquement<br />**Type de données :** Entier<br />**Valeurs :**<br>**0** – Toujours demander (par défaut)<br>**1** – Envoyer automatiquement des échantillons sécurisés<br>**2** – Ne jamais envoyer<br>**3** – Envoyer automatiquement tous les échantillons|
|**ExcludedExtensions**<br>./Vendor/MSFT/Policy/Config/Defender/ExcludedExtensions|Desktop uniquement<br />**Type de données : ** Chaîne<br />**Valeurs :**<br>*&lt;liste d’extensions séparées par des points-virgules&gt;* Par exemple : **obj;lib**<br>**Par défaut :** Aucune extension n’est exclue.|
|**ExcludedPaths**<br>./Vendor/MSFT/Policy/Config/Defender/ExcludedPaths|Desktop uniquement<br />**Type de données : ** Chaîne<br />**Valeurs :**<br />*&lt;liste de chemins d'accès séparés par des points-virgules&gt;*<br />Exemple : **c:\test;c:\test1.exe**<br />**Valeur par défaut :** Aucun chemin n’est exclu.|
|**ExcludedProcesses**<br>./Vendor/MSFT/Policy/Config/Defender/ExcludedProcesses|Desktop uniquement<br />**Type de données : ** Chaîne<br />**Valeurs :**<br>*&lt;liste de chemins d'accès séparés par des points-virgules&gt;*<br>Exemple : **c:\test.exe;c:\test1.exe**<br>**Valeur par défaut :** Aucun processus n’est exclu.|

## &nbsp;&nbsp;&nbsp;Navigateur Edge

|Nom de la stratégie et URI|Détails|
|---------------|------------|-----------|
|**Autoriser ce navigateur**<br>./Vendor/MSFT/Policy/Config/Browser/AllowBrowser|Mobile uniquement<br />**Type de données :** Entier<br />**Valeurs :** **0** : navigation désactivée, **1** : navigation activée (valeur par défaut)|
|**AllowSearchSuggestionsinAddressBar**<br>./Vendor/MSFT/Policy/Config/Browser/AllowSearchSuggestionsinAddressBar|Desktop et mobile<br />**Type de données :** Entier<br />**Valeurs :** **0** : Ne pas afficher les suggestions, **1** : Afficher les suggestions (valeur par défaut)|
|**SendIntranetTraffictoInternetExplorer**<br>./Vendor/MSFT/Policy/Config/Browser/SendIntranetTraffictoInternetExplorer|Desktop uniquement<br />**Type de données :** Entier<br />**Valeurs :**<br>**0** – Désactivé (ouvre les sites intranet dans le navigateur Microsoft Edge – par défaut)<br>**1** – Activé (ouvre les sites intranet dans Internet Explorer)|
|**Autoriser Do Not Track**<br>./Vendor/MSFT/Policy/Config/Browser/AllowDoNotTrack|Desktop et Mobile<br />**Type de données :** Entier<br />**Valeurs :** **0** – Désactivé (DNT non envoyé, valeur par défaut), **1** : Activé (envoyer DNT)|
|**Configurer SmartScreen**<br>./Vendor/MSFT/Policy/Config/Browser/AllowSmartScreen|Desktop et mobile<br />**Type de données :** Entier<br />**Valeurs :** **0** – Ne pas autoriser, **1** – Autoriser (valeur par défaut)|
|**Autoriser les fenêtres contextuelles**<br>./Vendor/MSFT/Policy/Config/Browser/AllowPopups|Desktop uniquement<br />**Type de données :** Entier<br />**Valeurs :** **0** – Bloquer les fenêtres publicitaires (valeur par défaut), **1** – Autoriser les fenêtres publicitaires|
|**Autoriser les cookies**<br>./Vendor/MSFT/Policy/Config/Browser/AllowCookies|Desktop et mobile<br />**Type de données :** Entier<br />**Valeurs :**<br>**0** – Autoriser les cookies de tous les sites web (valeur par défaut)<br>**1** – Bloquer uniquement les cookies tiers<br>**2** – Bloquer tous les cookies|
|**Autoriser l'enregistrement du mot de passe**<br>./Vendor/MSFT/Policy/Config/Browser/AllowPasswordManager|Desktop et mobile<br />**Type de données :** Entier<br />**Valeurs :**<br>**0** – Le gestionnaire de mots de passe est désactivé <br>**1** – Le gestionnaire de mots de passe est activé (par défaut)|
|**Autoriser le remplissage automatique**<br>./Vendor/MSFT/Policy/Config/Browser/AllowAutofill|Desktop uniquement<br />**Type de données :** Entier<br />**Valeurs :** **0** – Désactivé (valeur par défaut), **1** – Activé|
|**Configurer la liste des sites d’entreprise**<br>./Vendor/MSFT/Policy/Config/Browser/EnterpriseModeSiteList|Desktop uniquement<br />**Type de données : ** Chaîne<br />**Valeurs :<br> **0** – Non configuré<br>**1** – Utiliser la liste des sites d’entreprise d’Internet Explorer si elle est configurée (valeur par défaut)<br>**2** – Spécifier l’emplacement de la liste des sites d’entreprise|

## Paramètres de la stratégie de configuration générale

Utilisez la **stratégie de configuration générale** Microsoft Intune pour Windows 10 afin de configurer les paramètres intégrés des appareils Windows 10 Desktop et Windows 10 Mobile inscrits. 

## &nbsp;&nbsp;&nbsp;Mot de passe

|Nom du paramètre|Informations supplémentaires (si requises)|
|----------------|----------------------|
|**Exiger un mot de passe pour déverrouiller des appareils**|-|
|**Type de mot de passe requis**|Spécifie si le mot de passe doit être numérique uniquement ou alphanumérique|
|**Type de mot de passe requis** - **Nombre minimum de jeux de caractères**|Il existe quatre jeux de caractères : lettres minuscules, lettres majuscules, symboles et chiffres. Ce paramètre spécifie le nombre de jeux à inclure dans le mot de passe.|
|**Longueur minimale du mot de passe**|S’applique à Windows 10 Mobile uniquement|
|**Nombre d'échecs de connexion répétée autorisé avant réinitialisation de l'appareil**|Pour les appareils exécutant Windows 10 : Si BitLocker est activé sur l’appareil, ce dernier passe en mode de récupération BitLocker après le nombre d’échecs de connexion que vous spécifiez. Si BitLocker n’est pas activé sur l’appareil, alors ce paramètre ne s’applique pas.<br>Pour les appareils exécutant Windows 10 Mobile : Après le nombre d’échecs de connexion que vous spécifiez, l’appareil est réinitialisé.|
|**Minutes d'inactivité avant arrêt de l'écran**|Spécifie la durée pendant laquelle l’appareil doit être inactif avant que l’écran de veille se verrouille.|
|**Expiration du mot de passe (jours)**|Spécifie la durée après laquelle le mot de passe d'un appareil doit être modifié.|
|**Mémoriser l'historique des mots de passe**|Spécifie si vous souhaitez empêcher l'utilisateur final de créer des mots de passe utilisés précédemment.|
|**Mémoriser l'historique des mots de passe** - **Empêcher la réutilisation des mots de passe précédents**|Spécifie le nombre de mots de passe déjà utilisés et conservés par l’appareil.|
|**Exiger un mot de passe quand l'appareil quitte un état inactif**|Si cette option est activée, l’utilisateur doit entrer un mot de passe pour déverrouiller l’appareil. (Windows 10 Mobile uniquement)|

## &nbsp;&nbsp;&nbsp;Chiffrement

|Nom du paramètre|Informations supplémentaires (si requises)|
|----------------|----------------------|
|**Exiger le chiffrement sur l'appareil mobile**|Active le chiffrement sur les appareils ciblés.<br>(Windows 10 Mobile uniquement)|

## &nbsp;&nbsp;&nbsp;Système

|Nom du paramètre|Informations supplémentaires (si requises)|
|----------------|----------------------|
|**Autoriser la capture d'écran**|Autorise l’utilisateur à capturer le contenu de l’écran d’appareil en tant qu’image. (Windows 10 Mobile uniquement)|
|**Autoriser la désinscription manuelle**|Permet à l'utilisateur de supprimer manuellement le compte d'espace de travail de l'appareil|
|**Autoriser l'installation manuelle de certificats racines**|S’applique à Windows 10 Mobile|
|**Autoriser l'envoi des données de diagnostic et d'utilisation à Microsoft**|Les valeurs possibles sont les suivantes :<br><br>**Non** - Aucune donnée n’est envoyée à Microsoft<br>**Basique** - Une quantité limitée d’informations est envoyée à Microsoft<br>**Amélioré** - Des données de diagnostic avancées sont envoyées à Microsoft<br>**Complète (recommandée)** - envoie les mêmes données que **Amélioré**, ainsi que des données supplémentaires sur l'état de l’appareil|


## &nbsp;&nbsp;&nbsp;Compte et synchronisation

|Nom du paramètre|Informations supplémentaires (si requises)|
|----------------|----------------------|---------------------|
|**Autoriser le compte Microsoft**|Permet à l'utilisateur d'associer un compte Microsoft à l’appareil.|
|**Autoriser l'ajout manuel de comptes non-Microsoft**|Permet à l'utilisateur d'ajouter des comptes de messagerie à l'appareil qui ne sont pas associés à un compte Microsoft.|
|**Autoriser la synchronisation des paramètres pour les comptes Microsoft**|Permet aux paramètres d’appareil et d'application associés à un compte Microsoft de se synchroniser entre les appareils.|

## &nbsp;&nbsp;&nbsp;Microsoft Edge

|Nom du paramètre|Informations supplémentaires (si requises)|
|----------------|----------------------|
|**Autoriser le navigateur web**|Permet d’utiliser le navigateur web Microsoft Edge sur l’appareil.<br>(Windows 10 Mobile uniquement)|
|**Autoriser les suggestions de recherche dans la barre d'adresse**|Permet à votre moteur de recherche de suggérer des sites à mesure que vous saisissez des expressions de recherche.|
|**Autoriser l'envoi du trafic intranet vers Internet Explorer**|Permet aux utilisateurs d’ouvrir des sites web intranet dans Internet Explorer.<br>(Windows 10 Desktop uniquement)|
|**Autoriser Do Not Track**|Configure le navigateur Microsoft Edge pour envoyer des en-êtes Do Not Track aux sites web que les utilisateurs visitent.|
|**Activer SmartScreen**|-|
|**Autoriser les scripts actifs**|Autoriser l’exécution de scripts, tels que JavaScript, dans le navigateur Microsoft Edge.|
|**Autoriser les fenêtres contextuelles**|S’applique à Windows 10 Desktop uniquement|
|**Autoriser les cookies**|-|
|**Autoriser le remplissage automatique**|Autoriser les utilisateurs à modifier les paramètres de saisie semi-automatique dans le navigateur.<br>(Windows 10 Desktop uniquement)|
|**Autoriser le gestionnaire de mots de passe**|Activer ou désactiver la fonctionnalité Gestionnaire de mots de passe Microsoft Edge.|
|**Emplacement de la liste des sites en mode entreprise**|Indique où trouver la liste des sites web qui s'ouvrent en Mode entreprise. Les utilisateurs ne peuvent pas modifier cette liste.<br>(Windows 10 Desktop uniquement)|

## &nbsp;&nbsp;&nbsp;Applications

|Nom du paramètre|Informations supplémentaires (si requises)|
|----------------|----------------------|---------------------|
|**Autoriser la boutique d'applications**|S’applique à Windows 10 Mobile uniquement|



## &nbsp;&nbsp;&nbsp;Cellulaire

|Nom du paramètre|Informations supplémentaires (si requises)|
|----------------|----------------------|---------------------|
|**Autoriser l'itinérance des données**|Autorisez l'itinérance entre réseaux lors de l'accès aux données.|
|**Autoriser une connexion VPN sur un réseau cellulaire**|Contrôle si l’appareil peut accéder aux connexions VPN lorsqu'il est connecté à un réseau cellulaire.|
|**Autoriser l'itinérance VPN sur un réseau cellulaire**|Contrôle si l’appareil peut accéder aux connexions VPN lorsqu'il est en itinérance sur un réseau cellulaire.|

## &nbsp;&nbsp;&nbsp;Matériel

|Nom du paramètre|Informations supplémentaires (si requises)|
|----------------|----------------------|
|**Autoriser l'appareil photo**|-|
|**Autoriser le stockage amovible**|Spécifie si des périphériques de stockage externe telle une carte SD peuvent être utilisés avec l'appareil.|
|**Autoriser le Wi-Fi**|S’applique à Windows 10 Mobile uniquement|
|**Autoriser le partage Internet**|Autorise l'utilisation du partage de connexion Internet sur l'appareil.|
|**Autoriser la configuration manuelle du Wi-Fi**|Détermine si les utilisateurs peuvent configurer leurs propres connexions Wi-Fi ou s'ils peuvent uniquement utiliser les connexions configurées par un profil Wi-Fi.<br>(Windows 10 Mobile uniquement)|
|**Autoriser la connexion automatique aux points d'accès Wi-Fi gratuits**|Permet à l’appareil de se connecter automatiquement aux points d'accès Wi-Fi gratuits et d’accepter automatiquement les termes et conditions de la connexion.|
|**Autoriser la géolocalisation**|Spécifie si l'appareil peut utiliser les informations des services d'emplacement.|
|**Autoriser NFC**|Permet à l’appareil d’utiliser ses fonctionnalités NFC (Near Field Communications).|
|**Autoriser Bluetooth**|-|
|**Autoriser le mode découvrable Bluetooth**|Permet à cet appareil d’être découvert par d'autres appareils Bluetooth.|
|**Autoriser la publicité Bluetooth**|Permet aux appareils de recevoir des publicités par Bluetooth.|
|**Autoriser la réinitialisation du téléphone**|Détermine si l'utilisateur peut rétablir les paramètres d'usine de son appareil.|
|**Autoriser la connexion USB**|Contrôle si les appareils peuvent accéder à des périphériques de stockage externe via une connexion USB.|
|**Autoriser le mode antivol**|Configurer si le mode antivol Windows est activé.|

## &nbsp;&nbsp;&nbsp;Fonctionnalités

|Nom du paramètre|Informations supplémentaires (si requises)|
|----------------|----------------------|---------------------|
|**Autoriser la fonction copier-coller**|S’applique à Windows 10 Mobile uniquement|
|**Autoriser l'enregistrement vocal**|S’applique à Windows 10 Mobile uniquement|
|**Autoriser Cortana**|Active ou désactive l'assistant vocal Cortana.|
|**Autoriser les notifications du centre de notifications**|Active ou désactive les notifications du centre de notifications sur l'écran de verrouillage de l'appareil.<br>(Windows 10 Mobile uniquement)|

## &nbsp;&nbsp;&nbsp;Windows Defender

Tous les paramètres sont pour Windows 10 Desktop uniquement.

|Nom du paramètre|Informations supplémentaires (si requises)|
|-|-|
|**Autoriser la surveillance en temps réel**|Active la recherche en temps réel des logiciels malveillants, logiciels espions et autres logiciels indésirables.|
|**Autoriser l'analyse du comportement**|Permet à Defender de rechercher certains modèles connus d'activité suspecte sur les appareils.|
|**Activer le système NIS (Network Inspection System)**|Le système NIS (Network Inspection System) vous aide à protéger les appareils contre les attaques transmises via le réseau à l'aide de signatures de vulnérabilités connues fournies par le Microsoft Endpoint Protection Center afin de détecter et de bloquer tout trafic malveillant.|
|**Analyser tous les téléchargements**|Contrôle si Defender analyse tous les fichiers téléchargés depuis Internet.|
|**Autoriser l'analyse de scripts**|Configure Defender pour analyser les scripts utilisés dans Internet Explorer Defender.|
|**Surveiller l'activité des fichiers et des programmes**|Activez ce paramètre pour autoriser Defender à surveiller l'activité des fichiers et des programmes sur les appareils.|
|**Durée du suivi des logiciels malveillants dont le cas a été résolu (en jours)**|Permet à Defender de continuer à suivre les logiciels malveillants résolus pendant un certain nombre de jours que vous spécifiez, pour vous permettre de vérifier manuellement les appareils affectés. Si vous définissez le nombre de jours du suivi sur **0**, les logiciels malveillants restent dans le dossier de quarantaine et ne sont pas automatiquement supprimés. |
|**Autoriser l'accès à l'interface utilisateur cliente**|Détermine si l'interface utilisateur de Windows Defender est masquée aux utilisateurs finaux.<br>Lorsque ce paramètre est modifié, le changement est appliqué au prochain redémarrage de l'ordinateur de l'utilisateur final.|
|**Planifier une analyse quotidienne rapide**|Permet de planifier une analyse rapide exécutée tous les jours à l’heure de votre choix.|
|**Planifier une analyse système**|Vous permet de planifier une analyse système complète ou rapide exécutée régulièrement le jour et à l’heure de votre choix.|
|**Limiter l'utilisation du processeur lors d'une analyse à**|Vous permet de limiter la quantité de ressources du processeur que les analyses sont autorisées à utiliser (de **1** à **100**)|
|**Analyser les fichiers d'archives**|Permet à Defender d'analyser les fichiers archivés tels que les archives Zip ou Cab.|
|**Analyser les messages électroniques**|Permet à Defender d’analyser les messages électroniques lorsqu'ils arrivent sur l’appareil.|
|**Analyser les lecteurs amovibles**|Permet à Defender d'analyser les lecteurs amovibles tels que les clés USB.|
|**Analyser les lecteurs réseau mappés**|Permet à Defender d'analyser les fichiers sur un lecteur réseau mappé.<br>Si les fichiers sur le lecteur sont en lecture seule, Defender ne pourra pas supprimer les logiciels malveillants détectés dans ces fichiers.|
|**Analyser les fichiers ouverts à partir de dossiers partagés sur le réseau**|Permet à Defender d'analyser les fichiers sur des lecteurs réseau partagés (par exemple, les lecteurs accessibles à partir d'un chemin d'accès UNC).<br>Si les fichiers sur le lecteur sont en lecture seule, Defender ne pourra pas supprimer les logiciels malveillants détectés dans ces fichiers.|
|**Intervalle de mise à jour des signatures**|Spécifiez l'intervalle auquel Defender vérifie les nouveaux fichiers de signatures.|
|**Autoriser la protection de cloud**|Autorisez ou empêchez Microsoft Active Protection Service de recevoir des informations sur l'activité des logiciels malveillants à partir des appareils que vous gérez. Ces informations serviront à améliorer le service.|
|**Demander aux utilisateurs d'envoyer des exemples**|Contrôle si les fichiers susceptibles de nécessiter une analyse plus approfondie de la part de Microsoft pour déterminer s’il s’agit de logiciels malveillants sont automatiquement envoyés à Microsoft.|
|**Détection des applications potentiellement indésirables**|Ce paramètre permet d’empêcher les appareils de bureau Windows inscrits d’exécuter des logiciels considérés par Windows Defender comme potentiellement indésirables. Vous pouvez empêcher ces applications d’être exécutées ou utiliser le mode Audit pour être informé lorsqu’une application potentiellement indésirable est installée.|
|**Fichiers et dossiers à exclure lors de l'exécution d'une analyse ou de l'utilisation de la protection en temps réel**|Ajoutez un ou plusieurs fichiers et dossiers comme **C:\Path** ou **%ProgramFiles%\Path\filename.exe** à la liste des exclusions. Ces fichiers et dossiers ne seront pas inclus dans les analyses en temps réel ou planifiées.|
|**Extensions de fichier à exclure lors d'une analyse ou de la protection en temps réel**|Ajoutez une ou plusieurs extensions de fichier comme **jpg** ou **txt** à la liste des exclusions. Tous les fichiers avec ces extensions ne seront pas inclus dans les analyses en temps réel ou planifiées.|
|**Processus à exclure lors d'une analyse ou de la protection en temps réel**|Ajoutez un ou plusieurs processus du type **.exe**, **.com**, ou **.scr** à la liste des exclusions. Ces processus ne seront pas inclus dans les analyses en temps réel ou planifiées.| 


## &nbsp;&nbsp;&nbsp;Updates

|Nom du paramètre|Informations supplémentaires (si requises)|
|----------------|---------------|
|**Autoriser les mises à jour automatiques**|Activez ce paramètre pour autoriser les mises à jour automatiques. Ensuite, configurez l'un des paramètres suivants pour contrôler le comportement de mise à jour :<br />**Notification de téléchargement**<br />**Installer automatiquement au moment de la maintenance**<br />**Installer et redémarrer automatiquement au moment de la maintenance**<br />**Installer et redémarrer automatiquement au moment planifié** **Remarque :** Quand cette option est sélectionnée, vous pouvez aussi configurer les paramètres suivants : **Supprimer la notification à l’utilisateur final** et **Définir un jour d’installation pour les mises à jour planifiées**<br>(Windows 10 Desktop uniquement)|
|**Autoriser les fonctionnalités préliminaires**|Permet à Microsoft de déployer des versions préliminaires de paramètres et de fonctionnalités sur des appareils dotés de Windows 10. Vous pouvez décider d’autoriser l’installation des paramètres uniquement, ou de toutes les versions préliminaires de paramètres et de fonctionnalités.|

### Voir aussi
[Gérer des paramètres et des fonctionnalités sur vos appareils avec des stratégies Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)





<!--HONumber=Oct16_HO1-->


