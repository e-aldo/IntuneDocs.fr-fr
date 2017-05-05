---
title: "Configurations personnalisées pour les profils VPN Microsoft Intune | Microsoft Docs"
description: "Utilisez des configurations personnalisées pour créer des profils VPN dans Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4c0bd439-3b58-420b-9a9a-282886986786
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 8b2bd3ecba0b597bc742ea08872ffe8fc58155cf
ms.openlocfilehash: a8e44fced435193031d17860b13a03d084b5c6aa
ms.lasthandoff: 04/24/2017


---

# <a name="custom-configurations-for-microsoft-intune-vpn-profiles"></a>Configurations personnalisées pour les profils VPN Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

## <a name="create-a-custom-configuration"></a>Créer une configuration personnalisée
Vous pouvez utiliser des stratégies de configuration personnalisées Intune afin de créer des profils VPN pour :

* Appareils qui exécutent Android 4 et versions ultérieures
* Appareils Android for Work
* Appareils inscrits qui exécutent Windows 8.1 et versions ultérieures
* Appareils qui exécutent Windows Phone 8.1 et versions ultérieures
* Appareils inscrits qui exécutent Windows 10 Desktop
* Appareil qui exécutent Windows 10 Mobile

Ce type de stratégie peut être utile lorsque les stratégies VPN Intune standard n'incluent pas les paramètres que vous souhaitez utiliser.

## <a name="to-create-a-custom-configuration-policy"></a>Pour créer une stratégie de configuration personnalisée :

   1. Dans la [console d’administration Intune](https://manage.microsoft.com), choisissez **Stratégie** > **Ajouter une stratégie** > *Expand platform (Développer la plateforme)* > **Configuration personnalisée** > **Créer une stratégie**.
   2. Entrez un nom pour la stratégie.
   3. Pour chaque paramètre d’URI que vous souhaitez spécifier, choisissez **Ajouter** et fournissez les informations demandées. Voici un exemple :

   ![Boîte de dialogue de configuration personnalisée de profil VPN](./media/Intune_Add_VPN_URI.png)

   4.  Une fois que vous avez entré tous les paramètres d’URI, choisissez **Enregistrer la stratégie**, puis déployez la stratégie.

Ensuite, [déployez la stratégie](/intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies#deploy-a-configuration-policy) comme d’habitude.

## <a name="example-uri-settings"></a>Exemples de paramètres URI

Ces paramètres peuvent être utilisés pour créer une configuration personnalisée d’un VPN dans une société fictive nommée Contoso.
Pour obtenir tous les détails sur l'ensemble des paramètres configurables, consultez [VPNv2 CSP](https://msdn.microsoft.com/library/windows/hardware/dn914776.aspx).

VPN Contoso natif (IKEv2) : ./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/Servers

vpn.contoso.com ./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/NativeProtocolType

Ikev2 ./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/RoutingPolicyType

SplitTunnel ./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/Authentication/UserMethod

Eap ./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/Authentication/Eap/Configuration &lt;EapHostConfig xmlns="https://www.microsoft.com/provisioning/EapHostConfig"&gt;&lt;EapMethod&gt;&lt;Type xmlns="https://www.microsoft.com/provisioning/EapCommon"&gt;13&lt;/Type&gt;&lt;VendorId xmlns="https://www.microsoft.com/provisioning/EapCommon"&gt;0&lt;/VendorId&gt;&lt;VendorType xmlns="https://www.microsoft.com/provisioning/EapCommon"&gt;0&lt;/VendorType&gt;&lt;AuthorId xmlns="https://www.microsoft.com/provisioning/EapCommon"&gt;0&lt;/AuthorId&gt;&lt;/EapMethod&gt;&lt;Config xmlns="https://www.microsoft.com/provisioning/EapHostConfig"&gt;&lt;Eap xmlns="https://www.microsoft.com/provisioning/BaseEapConnectionPropertiesV1"&gt;&lt;Type&gt;13&lt;/Type&gt;&lt;EapType xmlns="https://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV1"&gt;&lt;CredentialsSource&gt;&lt;CertificateStore&gt;&lt;SimpleCertSelection&gt;true&lt;/SimpleCertSelection&gt;&lt;/CertificateStore&gt;&lt;/CredentialsSource&gt;&lt;ServerValidation&gt;&lt;DisableUserPromptForServerValidation&gt;false&lt;/DisableUserPromptForServerValidation&gt;&lt;ServerNames&gt;&lt;/ServerNames&gt;&lt;/ServerValidation&gt;&lt;DifferentUsername&gt;false&lt;/DifferentUsername&gt;&lt;PerformServerValidation xmlns="https://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2"&gt;false&lt;/PerformServerValidation&gt;&lt;AcceptServerName xmlns="https://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2"&gt;false&lt;/AcceptServerName&gt;&lt;/EapType&gt;&lt;/Eap&gt;&lt;/Config&gt;&lt;/EapHostConfig&gt;

**./Vendor/MSFT/VPNv2/ContosoVPN/ByPassForLocal** True

**./Vendor/MSFT/VPNv2/ContosoVPN/RememberCredentials** 1

**./Vendor/MSFT/VPNv2/ContosoVPN/DomainNameInformationList/1/DomainName** Corp.Contoso.com

**./Vendor/MSFT/VPNv2/ContosoVPN/DnsSuffix** Corp.Contoso.com

**./Vendor/MSFT/VPNv2/ContosoVPN/TrustedNetworkDetection** Corp.Contoso.com

**./Vendor/MSFT/VPNv2/ContosoVPN/RouteList/1/Address** 10.0.0.0

**./Vendor/MSFT/VPNv2/ContosoVPN/RouteList/1/PrefixSize** 8

**./Vendor/MSFT/VPNv2/ContosoVPN/AlwaysOn** true

**./Vendor/MSFT/VPNv2/ContosoVPN/AppTriggerList/0/App/Id** %PROGRAMFILES%\Internet Explorer\iexplore.exe

**./Vendor/MSFT/VPNv2/ContosoVPN/AppTriggerList/1/App/Id** %PROGRAMFILES% (x86)\Internet Explorer\iexplore.exe

**./Vendor/MSFT/VPNv2/ContosoVPN/AppTriggerList/2/App/Id** Microsoft.MicrosoftEdge_8wekyb3d8bbwe

**./Vendor/MSFT/VPNv2/ContosoVPN/TrafficFilterList/0/App/Id** %PROGRAMFILES% (x86)\Internet Explorer\iexplore.exe

**./Vendor/MSFT/VPNv2/ContosoVPN/TrafficFilterList/1/App/Id** Microsoft.MicrosoftEdge_8wekyb3d8bbwe

Pour toute question sur la façon dont ces paramètres doivent être utilisés, ou pour plus d’informations sur ce qu’ils font, consultez la documentation du fournisseur de services de configuration (CSP) : https://msdn.microsoft.com/library/windows/hardware/dn914776(v=vs.85).aspx.

## <a name="uri-settings-for-android-per-app-vpn-on-pulsesecure"></a>Paramètres d’URI pour les VPN Android par application sur PulseSecure
### <a name="custom-uri-for-package-list"></a>URI PERSONNALISÉ POUR LA LISTE DES PACKAGES
-  Type de données = Chaîne
-  OMA-URI = ./Vendor/MSFT/VPN/Profile/Name/PackageList
-  Valeur = liste des packages séparés par des délimiteurs.
   - Délimiteurs : point-virgule (;), deux-points (:), virgule (,), barre verticale (|)

Exemples :
- com.android.chrome
- com.android.chrome;com.android.browser

### <a name="custom-uri-for-mode-optional"></a>URI PERSONNALISÉ POUR LE MODE (FACULTATIF)
- Type de données = Chaîne
- OMA-URI = ./Vendor/MSFT/VPN/Profile/NAME/Mode

> Remarques
> - Utilisez le même *nom* que celui que vous avez affecté au profil personnalisé
> - Valeurs possibles : *GLOBAL*, *WHITELIST*, *BLACKLIST*
> - La valeur par défaut est *GLOBAL* si aucun PackageList n’est fourni (compatibilité descendante avec les profils à l’échelle du système)
> - La valeur par défaut est *WHITELIST* si un PackageList est fourni.


### <a name="see-also"></a>Voir aussi
[Connexions VPN dans Microsoft Intune](vpn-connections-in-microsoft-intune.md)

