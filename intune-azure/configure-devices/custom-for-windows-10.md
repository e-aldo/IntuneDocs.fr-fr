---
title: "Paramètres personnalisés Intune pour les appareils Windows 10"
titleSuffix: Intune Azure preview
description: "Préversion Intune Azure : Découvrez les paramètres que vous pouvez utiliser dans un profil personnalisé Windows 10."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7bcea136-7260-4042-b21b-c7dab86b380d
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: 647415914fb0f44807eff7baf7a56ea3a382f027
ms.contentlocale: fr-fr
ms.lasthandoff: 02/18/2017


---

# <a name="custom-device-settings-for-windows-10-devices-in-microsoft-intune"></a>Paramètres des appareils personnalisés pour les appareils Windows 10 dans Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

 Utilisez le profil Microsoft Intune **personnalisé** pour Windows 10 et Windows 10 Mobile pour déployer des paramètres OMA-URI (Open Mobile Alliance Uniform Resource Identifier) qui peuvent être utilisés pour contrôler les fonctionnalités sur des appareils. Dans Windows 10, de nombreux paramètres sont disponibles par le biais du [fournisseur de services de configuration de stratégie](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers).

1. Suivez les instructions figurant dans le [Guide pratique pour la configuration des paramètres d’appareils personnalisés](how-to-configure-custom-settings.md) pour commencer.
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


## <a name="policy-settings"></a>Paramètres de stratégie

|Nom de la stratégie et URI|Détails|
|---------------|------------|-----------|
|**Autoriser la mise à jour automatique**<br>./Vendor/MSFT/Policy/Config/Update/AllowAutoUpdate|Desktop uniquement<br>**Type de données :** Entier<br />**Valeurs :** **0** - **5** (valeur par défaut : **1**)|
|**Planifier le jour de l’installation**<br>./Vendor/MSFT/Policy/Config/Update/ScheduledInstallDay|Mobile uniquement<br>**Type de données :** Entier<br />**Valeurs :**<br>**0** - Tous les jours (par défaut)<br>**1** - Dimanche<br>**2** - Lundi<br>**3** - Mardi<br>**4** - Mercredi<br>**5** - Jeudi<br>**6** - Vendredi<br>**7** - Samedi|
|**Planifier l’heure de l’installation**<br>./Vendor/MSFT/Policy/Config/Update/ScheduledInstallTime|Desktop et mobile<br />**Type de données :** Entier<br />**Valeurs :** **0** – **23** heures (**0** correspond à minuit) (par défaut : **3**)|
|**DeviceLock/AllowIdleReturnWithoutPassword**<br>./Vendor/MSFT/Policy/Config/DeviceLock/AllowIdleReturnWithoutPassword|Mobile uniquement<br />**Type de données :** Entier<br />**Valeurs :**<br>**0** : L’utilisateur ne peut pas définir le minuteur de la période de grâce du mot de passe ; la valeur est « à chaque fois ».<br>**1** : L’utilisateur peut définir le minuteur de la période de grâce du mot de passe (valeur par défaut).|
|**WiFi/AllowWiFi**<br>./Vendor/MSFT/Policy/Config/WiFi/AllowWiFi|Mobile uniquement<br />**Type de données :** Entier<br />**Valeurs :**<br>**0** – Ne pas autoriser **Utiliser la connexion Wi-Fi**.<br>**1** –**Autoriser l’utilisation de la connexion Wi-Fi** (par défaut).|
|**WiFi/AllowInternetSharing**<br>./Vendor/MSFT/Policy/Config/WiFi/AllowInternetSharing|Desktop et mobile<br>**Type de données :** Entier<br />**Valeurs :** **0** – Ne pas autoriser le partage Internet **1** – Autoriser le partage Internet (valeur par défaut)|
|**WiFi/AllowAutoConnectToWiFiSenseHotspots**<br>./Vendor/MSFT/Policy/Config/WiFi/AllowAutoConnectToWiFiSenseHotspots|Desktop et mobile<br />**Type de données :** Entier<br />**Valeurs :** **0** – non autorisé, **1** – autorisé (valeur par défaut)|
|**WiFi/AllowManualWiFiConfiguration**<br>./Vendor/MSFT/Policy/Config/WiFi/AllowManualWiFiConfiguration|Mobile uniquement<br />**Type de données :** Entier<br />**Valeurs :**<br>**0** – Aucune connexion non-Wi-Fi en dehors de celles approvisionnées par la Gestion des appareils mobiles n’est autorisée.<br>**1** – L’ajout de nouveaux SSID réseau au-delà de ceux approvisionnés par MDM est autorisé (par défaut).|
|**System/AllowLocation**<br>./Vendor/MSFT/Policy/Config/System/AllowLocation|Desktop et mobile<br />**Type de données :** Entier<br />**Valeurs :** **0** – non autorisé, **1** – autorisé (valeur par défaut)|
|**System/AllowTelemetry**<br>./Vendor/MSFT/Policy/Config/System/AllowTelemetry|Desktop et mobile<br>**Type de données :** Entier<br />**Valeurs :**<br>**0** – Non autorisé (paramètre Entreprise uniquement)<br>**1** – Limité<br>**2** – Complet (par défaut)<br>**3** – Complet et informations de diagnostic|
|**System/AllowExperimentation**<br>./Vendor/MSFT/Policy/Config/System/AllowExperimentation|Desktop et mobile<br />**Type de données :** Entier<br />**Valeurs :**<br>**0** – Non autorisé<br>**1** – Paramètres uniquement (par défaut)<br>**2** – Paramètres et expérimentation|
|**Security/AntiTheftMode**<br>./Vendor/MSFT/Policy/Config/Security/AntiTheftMode|Mobile uniquement<br />**Type de données :** Entier<br />**Valeurs :**<br>**0** – Ne pas autoriser le mode antivol<br>**1** – Préférence utilisateur (par défaut)|
|**Connectivity/AllowUSBConnection**<br>./Vendor/MSFT/Policy/Config/Connectivity/AllowUSBConnection|Mobile uniquement<br />**Type de données :** Entier<br />**Valeurs :** **0** – non autorisé, **1** – autorisé (valeur par défaut)|
|**System/AllowUserToResetPhone**<br>./Vendor/MSFT/Policy/Config/System/AllowUserToResetPhone|Mobile uniquement<br />**Type de données :** Entier<br />**Valeurs :** **0** – non autorisé, **1** – autorisé (valeur par défaut)|
|**Connectivity/AllowCellularDataRoaming**<br>./Vendor/MSFT/Policy/Config/Connectivity/AllowCellularDataRoaming|Desktop et mobile<br />**Type de données :** Entier<br />**Valeurs :** **0** – non autorisé, **1** – autorisé (valeur par défaut)|
|**Connectivity/AllowVPNOverCellular**<br>./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNOverCellular|Desktop et mobile<br />**Type de données :** Entier<br />**Valeurs :**<br>**0** – Un VPN n’est pas autorisé sur une connexion cellulaire.<br>**1** – Un VPN peut utiliser n’importe quelle connexion, y compris une connexion cellulaire (par défaut).|
|**Connectivity/AllowVPNRoamingOverCellular**<br>./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNRoamingOverCellular|Mobile uniquement<br />**Type de données :** Entier<br />**Valeurs :** **0** – non autorisé, **1** – autorisé (valeur par défaut)|
|**Connectivity/AllowVPNRoamingOverCellular**<br>./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNRoamingOverCellular|Mobile uniquement<br />**Type de données :** Entier<br />**Valeurs :** **0** – non autorisé, **1** – autorisé (valeur par défaut)|
|**Connectivity/AllowBluetooth**<br>./Vendor/MSFT/Policy/Config/Connectivity/AllowBluetooth|Desktop et mobile<br />**Type de données :** Entier<br />**Valeurs :**<br>**0** – Ne pas autoriser l'utilisateur à activer le Bluetooth.<br>**1** – Réservé. L'utilisateur peut activer et configurer le Bluetooth (non pris en charge dans Windows Phone 8.1 pour MDM, EAS, Windows 10 Desktop ou Windows 10 Mobile)<br>**2** - Autorisé. L’utilisateur peut activer et configurer le Bluetooth (par défaut).|
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
|**TextInput/AllowIMENetworkAccess**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowIMENetworkAccess|Desktop uniquement<br />**Type de données :** Entier<br />**Valeurs :**<br>**0** – Ne pas autoriser<br>L'ouverture du dictionnaire étendu est désactivée.<br>Un utilisateur ne peut pas :<br>- Ajouter un nouveau dictionnaire étendu ouvert<br />- Ajouter un nouveau fichier de configuration d’intégration de la recherche<br>- Utiliser la fonctionnalité de candidat de cloud<br>- Envoyer un mot inscrit par l’utilisateur<br>**1** - Autoriser<br>Un dictionnaire étendu ouvert peut être ajouté et utilisé par défaut. Par ailleurs, la fonction d'intégration de la recherche peut être utilisée par défaut.<br>Un utilisateur peut :<br>Utiliser la fonctionnalité de candidat de cloud.|
|**TextInput/AllowIMELogging**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowIMELogging|Desktop uniquement<br />**Type de données :** Entier<br />**Valeurs :**<br>**0** - La journalisation des erreurs de conversion est désactivée.<br>**1** - La journalisation des erreurs de conversion est activée (valeur par défaut).|
|**TextInput/AllowJapaneseNonPublishingStandardGlyph**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseNonPublishingStandardGlyph|Desktop uniquement<br />**Type de données :** Entier<br />**Valeurs :** **0** – non autorisé, **1** – autorisé (valeur par défaut)|
|**TextInput/AllowJapaneseIVSCharacters**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseIVSCharacters|Desktop uniquement<br />**Type de données :** Entier<br />**Valeurs :** **0** – non autorisé, **1** – autorisé (valeur par défaut)|
|**TextInput/AllowJapaneseUserDictionary**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseUserDictionary|Desktop uniquement<br />**Type de données :** Entier<br />**Valeurs :** **0** – non autorisé, **1** – autorisé (valeur par défaut)|
|**TextInput/AllowJapaneseIMESurrogatePairCharacters**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseIMESurrogatePairCharacters|Desktop uniquement<br />**Type de données :** Entier<br />**Valeurs :** **0** – non autorisé, **1** – autorisé (valeur par défaut)|
|**TextInput/ExcludeJapaneseIMEExceptShiftJIS**<br>./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptShiftJIS|Desktop uniquement<br />**Type de données :** Entier<br />**Valeurs :**<br>**0** – Aucun caractère n’est filtré (par défaut).<br>**1** – Tous les caractères sont filtrés, sauf les caractères Shift-JIS.|
|**TextInput/ExcludeJapaneseIMEExceptJIS0208**<br>./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptJIS0208|Desktop uniquement<br />**Type de données :** Entier<br />**Valeurs :**<br />**0** – Aucun caractère n’est filtré (par défaut).<br>**1** – Tous les caractères sont filtrés, sauf les caractères JIS0208.|
|**TextInput/ExcludeJapaneseIMEExceptJIS0208andEUDC**<br>./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptJIS0208andEUDC|Desktop uniquement<br />**Type de données :** Entier<br />**Valeurs :**<br>**0** – Aucun caractère n’est filtré (par défaut).<br>**1** – Tous les caractères sont filtrés, sauf les caractères JIS0208 ou EUDC.|
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
|**Search/SafeSearchPermissions**<br>./Vendor/MSFT/Policy/Config/Search/SafeSearchPermissions|Mobile uniquement<br />**Type de données :** Entier<br />**Valeurs :**<br>**0** – Strict, niveau de filtrage le plus élevé en matière de contenu pour adultes.<br>**1** – Modéré, niveau de filtrage modéré en matière de contenu pour adultes (les résultats de recherche valides ne sont pas filtrés – par défaut).|
|**Experience/AllowCopyPaste**<br>./Vendor/MSFT/Policy/Config/Experience/AllowCopyPaste|Desktop uniquement<br />**Type de données :** Entier<br />**Valeurs :** **0** – non autorisé, **1** – autorisé (valeur par défaut)|
|**ForceStartSize**<br>./Vendor/MSFT/Policy/Config/Start/ForceStartSize|Mobile uniquement<br />**Type de données :** Entier<br />**Valeurs :**<br>**0** – Autoriser l’utilisateur à modifier la taille (par défaut).<br>**1** - Forcer un affichage n’utilisant pas le plein écran.<br>**1** - Forcer le plein écran.|
|**Update/RequireDeferUpgrade**<br>./Vendor/MSFT/Policy/Config/Update/RequireDeferUpgrade|Desktop et mobile<br />**Type de données :** Entier<br />**Valeurs :**<br>**0** : ne pas reporter la mise à niveau (rester dans la branche active, CB – par défaut)<br>**1** : activer le report des mises à jour et des mises à niveau (l’appareil suit les règles de la branche actuelle d’entreprise, CBB)<br />Pour plus d'informations, consultez :<br>[Présentation de la maintenance de Windows 10](https://technet.microsoft.com/library/mt598226.aspx)<br>[Planifier le déploiement de Windows 10](https://technet.microsoft.com/library/mt574241.aspx)|
|**Update/DeferUpdatePeriod**<br>./Vendor/MSFT/Policy/Config/Update/DeferUpdatePeriod|Desktop et mobile<br>**Description :** stratégie de report des mises à jour logicielles pendant quatre semaines<br />**Type de données :** Entier<br />**Valeurs :**<br> **0** : appliquer immédiatement les mises à jour (par défaut)<br>**1**-**4** : nombre de semaines de report des mises à jour logicielles.<br />Pour plus d'informations, consultez :<br>[Présentation de la maintenance de Windows 10](https://technet.microsoft.com/library/mt598226.aspx)<br>[Planifier le déploiement de Windows 10](https://technet.microsoft.com/library/mt574241.aspx)|
|**Update/DeferUpgradePeriod**<br>./Vendor/MSFT/Policy/Config/Update/DeferUpgradePeriod|Desktop et mobile<br>**Description :** stratégie de report des mises à niveau des fonctionnalités jusqu’à huit mois<br />**Type de données :** Entier<br />**Valeurs :**<br>**0** : appliquer immédiatement les mises à jour (par défaut)<br>**1**-**8** : nombre de mois de report des mises à niveau des fonctionnalités.<br />Pour plus d'informations, consultez :<br>[Présentation de la maintenance de Windows 10](https://technet.microsoft.com/library/mt598226.aspx)<br>[Planifier le déploiement de Windows 10](https://technet.microsoft.com/library/mt574241.aspx)|
|**Update/PauseDeferrals**<br>./Vendor/MSFT/Policy/Config/Update/PauseDeferrals|Desktop et mobile<br>**Description :** Autorise un appareil à cesser de recevoir des mises à jour et des mises à niveau pendant cinq semaines.<br />**Type de données :** Entier<br />**Valeurs :**<br>**0** : appliquer immédiatement les mises à jour (par défaut)<br>**1** : suspendre les mises à jour et les mises à niveau (expire au bout de cinq semaines)|

## <a name="windows-defender-settings"></a>Paramètres de Windows Defender

|Nom de la stratégie et URI|Détails|
|---------------|-----------|
|**AllowRealtimeMonitoring**<br>./Vendor/MSFT/Policy/Config/Defender/AllowRealtimeMonitoring|Desktop uniquement<br />**Type de données :** Entier<br />**Valeurs :** **0** – non autorisé, **1** – autorisé (valeur par défaut)|
|**AllowBehaviorMonitoring**<br>./Vendor/MSFT/Policy/Config/Defender/AllowBehaviorMonitoring|Desktop uniquement<br />**Type de données :** Entier<br />**Valeurs :** **0** – non autorisé, **1** – autorisé (valeur par défaut)|
|**AllowIntrusionPreventionSystem**<br>./Vendor/MSFT/Policy/Config/Defender/AllowIntrusionPreventionSystem|Desktop uniquement<br />**Type de données :** Entier<br />**Valeurs :** **0** – non autorisé, **1** – autorisé (valeur par défaut)|
|**AllowIOAVProtection**<br>./Vendor/MSFT/Policy/Config/Defender/AllowIOAVProtection|Desktop uniquement<br />**Type de données :** Entier<br />**Valeurs :** **0** – non autorisé, **1** – autorisé (valeur par défaut)|
|**AllowScriptScanning**<br>./Vendor/MSFT/Policy/Config/Defender/AllowScriptScanning|Desktop uniquement<br />**Type de données :** Entier<br />**Valeurs :** **0** – non autorisé, **1** – autorisé (valeur par défaut)|
|**AllowOnAccessProtection**<br>./Vendor/MSFT/Policy/Config/Defender/AllowOnAccessProtection|Desktop uniquement<br />**Type de données :** Entier<br />**Valeurs :** **0** – non autorisé, **1** – autorisé (valeur par défaut)|
|**RealTimeScanDirection**<br>./Vendor/MSFT/Policy/Config/Defender/RealTimeScanDirection|Desktop uniquement<br />**Type de données :** Entier<br />**Valeurs :**<br>**0** – Surveiller tous les fichiers (valeur par défaut)<br>**1** – Surveiller les fichiers entrants<br>**2** – Surveiller les fichiers sortants|
|**DaysToRetainCleanedMalware**<br>./Vendor/MSFT/Policy/Config/Defender/DaysToRetainCleanedMalware|Desktop uniquement<br />**Type de données :** Entier<br />**Valeurs :**<br>**0** - **90** – Représente la durée pendant laquelle les logiciels malveillants sont conservés.<br>**Valeur par défaut :** **0** – Les logiciels malveillants sont conservés indéfiniment dans le dossier de quarantaine et ne sont pas supprimés automatiquement.|
|**AllowUserUIAccess**<br>./Vendor/MSFT/Policy/Config/Defender/AllowUserUIAccess|Desktop uniquement<br />**Type de données :** Entier<br />**Valeurs :** **0** – non autorisé, **1** – autorisé (valeur par défaut)|
|**ScanParameter**<br>./Vendor/MSFT/Policy/Config/Defender/ScanParameter|Desktop uniquement<br />**Type de données :** Entier<br />**Valeurs :**<br>**1** – Analyse rapide (par défaut)<br>**2** – Analyse complète|
|**ScheduleScanDay**<br>./Vendor/MSFT/Policy/Config/Defender/ScheduleScanDay|Desktop uniquement<br />**Type de données :** Entier<br />**Valeurs :**<br>**0** – Tous les jours (par défaut)<br>**1** - Lundi<br>**2** - Mardi<br>**3** - Mercredi<br>**4** - Jeudi<br>**5** - Vendredi<br>**6** - Samedi<br>**7** - Dimanche<br>**8** - Aucune analyse planifiée|
|**ScheduleScanTime**<br>./Vendor/MSFT/Policy/Config/Defender/ScheduleScanTime|Desktop uniquement<br />**Type de données :** Entier<br />**Valeurs :**<br>**0** – 00:00<br>**60** – 1:00<br>**120** – 2:00 (par défaut)<br>**180** – 3:00<br>**240** – 4:00<br>**300** – 5:00<br>**360** – 6:00<br>**420** – 7:00<br>**480** – 8:00<br>**540** – 9:00<br>**600** – 10:00<br>**660** – 11:00<br>**720** – 12:00<br>**780** – 13:00<br>**840** – 14:00<br>**900** – 15:00<br>**960** – 16:00<br>**1020** – 17:00<br>**1080** – 18:00<br>**1140** – 19:00<br>**1200** – 20:00<br>**1260** – 21:00<br>**1320** – 22:00<br>**1381** – Fenêtre de maintenance|
|**ScheduleQuickScanTime**<br>./Vendor/MSFT/Policy/Config/Defender/ScheduleQuickScanTime|Desktop uniquement<br>**Type de données :** Entier<br />**Valeurs :**<br>**0** – 00:00<br>**60** – 1:00<br>**120** – 2:00 (par défaut)<br>**180** – 3:00<br>**240** – 4:00<br>**300** – 5:00<br>**360** – 6:00<br>**420** – 7:00<br>**480** – 8:00<br>**540** – 9:00<br>**600** – 10:00<br>**660** – 11:00<br>**720** – 12:00<br>**780** – 13:00<br>**840** – 14:00<br>**900** – 15:00<br>**960** – 16:00<br>**1020** – 17:00<br>**1080** – 18:00<br>**1140** – 19:00<br>**1200** – 20:00<br>**1260** – 21:00<br>**1320** – 22:00<br>**1380** – 23:00|
|**AVGCPULoadFactor**<br>./Vendor/MSFT/Policy/Config/Defender/AVGCPULoadFactor|Desktop uniquement<br />**Type de données :** Entier<br />**Valeurs :** **0** - **100** (valeur par défaut : **50**)|
|**AllowArchiveScanning**<br>./Vendor/MSFT/Policy/Config/Defender/AllowArchiveScanning|Desktop uniquement<br />**Type de données :** Entier<br />**Valeurs :** **0** – non autorisé, **1** – autorisé (valeur par défaut)|
|**AllowEmailScanning**<br>./Vendor/MSFT/Policy/Config/Defender/AllowEmailScanning|Desktop uniquement<br />**Type de données :** Entier<br>**Valeurs :** **0** – non autorisé (valeur par défaut), **1** – autorisé|
|**AllowFullScanRemovableDriveScanning**<br>./Vendor/MSFT/Policy/Config/Defender/AllowFullScanRemovableDriveScanning|Desktop uniquement<br />**Type de données :** Entier<br />**Valeurs :** **0** – non autorisé (valeur par défaut), **1** – autorisé|
|**AllowFullScanOnMappedNetworkDrives**<br>./Vendor/MSFT/Policy/Config/Defender/AllowFullScanOnMappedNetworkDrives|Desktop uniquement<br />**Type de données :** Entier<br />**Valeurs :** **0** – non autorisé, **1** – autorisé (valeur par défaut)|
|**AllowScanningNetworkFiles**<br>./Vendor/MSFT/Policy/Config/Defender/AllowScanningNetworkFiles|Desktop uniquement<br />**Type de données :** Entier<br />**Valeurs :** **0** – non autorisé, **1** – autorisé (valeur par défaut) – s’exécute également quand le protocole RTP est activé, si défini sur autorisé|
|**SignatureUpdateInterval**<br>./Vendor/MSFT/Policy/Config/Defender/SignatureUpdateInterval|Desktop uniquement<br />**Type de données :** Entier<br />**Valeurs :**<br>**0** – Ne pas vérifier les signatures par intervalle<br>**1** – Vérifier les signatures toutes les heures<br>**2** – Vérifier toutes les 2 heures, etc.<br>**24** – Vérifier tous les jours<br>**Valeur par défaut :** 8 – vérifier toutes les 8 heures|
|**AllowCloudProtection**<br>./Vendor/MSFT/Policy/Config/Defender/AllowCloudProtection|Desktop uniquement<br />**Type de données :** Entier<br />**Valeurs :** **0** – non autorisé, **1** – autorisé (valeur par défaut)|
|**SubmitSamplesConsent**<br>./Vendor/MSFT/Policy/Config/Defender/SubmitSamplesConsent|Desktop uniquement<br />**Type de données :** Entier<br />**Valeurs :**<br>**0** – Toujours demander (par défaut)<br>**1** – Envoyer automatiquement des échantillons sécurisés<br>**2** – Ne jamais envoyer<br>**3** – Envoyer automatiquement tous les échantillons|
|**ExcludedExtensions**<br>./Vendor/MSFT/Policy/Config/Defender/ExcludedExtensions|Desktop uniquement<br />**Type de données:** Chaîne<br />**Valeurs :**<br>*&lt;liste d’extensions séparées par des points-virgules&gt;* Par exemple : **obj;lib**<br>**Par défaut :** Aucune extension n’est exclue.|
|**ExcludedPaths**<br>./Vendor/MSFT/Policy/Config/Defender/ExcludedPaths|Desktop uniquement<br />**Type de données:** Chaîne<br />**Valeurs :**<br />*&lt;liste de chemins d'accès séparés par des points-virgules&gt;*<br />Exemple : **c:\test;c:\test1.exe**<br />**Valeur par défaut :** Aucun chemin n’est exclu.|
|**ExcludedProcesses**<br>./Vendor/MSFT/Policy/Config/Defender/ExcludedProcesses|Desktop uniquement<br />**Type de données:** Chaîne<br />**Valeurs :**<br>*&lt;liste de chemins d'accès séparés par des points-virgules&gt;*<br>Exemple : **c:\test.exe;c:\test1.exe**<br>**Valeur par défaut :** Aucun processus n’est exclu.|

## <a name="edge-browser-settings"></a>Paramètres du navigateur Edge

|Nom de la stratégie et URI|Détails|
|---------------|------------|-----------|
|**Autoriser le navigateur**<br>./Vendor/MSFT/Policy/Config/Browser/AllowBrowser|Mobile uniquement<br />**Type de données :** Entier<br />**Valeurs :** **0** : navigation désactivée, **1** : navigation activée (valeur par défaut)|
|**AllowSearchSuggestionsinAddressBar**<br>./Vendor/MSFT/Policy/Config/Browser/AllowSearchSuggestionsinAddressBar|Desktop et mobile<br />**Type de données :** Entier<br />**Valeurs :** **0** : Ne pas afficher les suggestions, **1** : Afficher les suggestions (valeur par défaut)|
|**SendIntranetTraffictoInternetExplorer**<br>./Vendor/MSFT/Policy/Config/Browser/SendIntranetTraffictoInternetExplorer|Desktop uniquement<br />**Type de données :** Entier<br />**Valeurs :**<br>**0** – Désactivé (ouvre les sites intranet dans le navigateur Microsoft Edge – par défaut)<br>**1** – Activé (ouvre les sites intranet dans Internet Explorer)|
|**Autoriser Do Not Track**<br>./Vendor/MSFT/Policy/Config/Browser/AllowDoNotTrack|Desktop et Mobile<br />**Type de données :** Entier<br />**Valeurs :** **0** – Désactivé (DNT non envoyé, valeur par défaut), **1** : Activé (envoyer DNT)|
|**Configurer SmartScreen**<br>./Vendor/MSFT/Policy/Config/Browser/AllowSmartScreen|Desktop et mobile<br />**Type de données :** Entier<br />**Valeurs :** **0** – Ne pas autoriser, **1** – Autoriser (valeur par défaut)|
|**Autoriser les fenêtres indépendantes**<br>./Vendor/MSFT/Policy/Config/Browser/AllowPopups|Desktop uniquement<br />**Type de données :** Entier<br />**Valeurs :** **0** – Bloquer les fenêtres publicitaires (valeur par défaut), **1** – Autoriser les fenêtres publicitaires|
|**Autoriser les cookies**<br>./Vendor/MSFT/Policy/Config/Browser/AllowCookies|Desktop et mobile<br />**Type de données :** Entier<br />**Valeurs :**<br>**0** – Autoriser les cookies de tous les sites web (valeur par défaut)<br>**1** – Bloquer uniquement les cookies tiers<br>**2** – Bloquer tous les cookies|
|**Autoriser l’enregistrement du mot de passe**<br>./Vendor/MSFT/Policy/Config/Browser/AllowPasswordManager|Desktop et mobile<br />**Type de données :** Entier<br />**Valeurs :**<br>**0** – Le gestionnaire de mots de passe est désactivé <br>**1** – Le gestionnaire de mots de passe est activé (par défaut)|
|**Autoriser le remplissage automatique**<br>./Vendor/MSFT/Policy/Config/Browser/AllowAutofill|Desktop uniquement<br />**Type de données :** Entier<br />**Valeurs :** **0** – Désactivé (valeur par défaut), **1** – Activé|
|**Configurer la liste des sites d’entreprise**<br>./Vendor/MSFT/Policy/Config/Browser/EnterpriseModeSiteList|Desktop uniquement<br />**Type de données:** Chaîne<br />**Valeurs :<br>** 0 **– Non configuré<br>**1** – Utiliser la liste des sites d’entreprise d’Internet Explorer si elle est configurée (valeur par défaut)<br>**2** – Spécifier l’emplacement de la liste des sites d’entreprise|

