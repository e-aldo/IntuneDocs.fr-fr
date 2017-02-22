---
title: "Guide de création de profils VPN personnalisés avec Microsoft Intune | Microsoft Docs"
description: "Utilisez des configurations personnalisées pour créer des profils VPN dans Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4c0bd439-3b58-420b-9a9a-282886986786
ms.reviewer: karanda
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: f2b364b2c57adab33df2a8e6b34c1f30c02988d3
ms.openlocfilehash: e92593062ad2ed7a4098922715106f47f4e78d4f


---

# <a name="how-to-create-custom-vpn-profiles-with-microsoft-intune"></a>Guide de création de profils VPN personnalisés avec Microsoft Intune

## <a name="create-a-custom-configuration"></a>Créer une configuration personnalisée
Vous pouvez utiliser des stratégies de configuration personnalisées Intune afin de créer des profils VPN pour :

* Appareils qui exécutent Android 4 et versions ultérieures
* Appareils inscrits qui exécutent Windows 8.1 et versions ultérieures
* Appareils qui exécutent Windows Phone 8.1 et versions ultérieures
* Appareils inscrits qui exécutent Windows 10 Desktop 
* Appareils exécutant Windows 10 Mobile

Ce type de stratégie peut être utile lorsque les stratégies VPN Intune standard n'incluent pas les paramètres que vous souhaitez utiliser.

## <a name="to-create-a-custom-configuration-policy"></a>Pour créer une stratégie de configuration personnalisée :

1. Connectez-vous au portail Azure.
2. Choisissez **Plus de services** > **Autres** > **Intune**.
3. Dans le panneau **Intune**, choisissez **Configurer des appareils**.
4. Dans le panneau **Configuration de l’appareil**, choisissez **Gérer** > **Profils**.
5. Dans le panneau des profils, sélectionnez **Créer un profil**.
6. Dans le panneau **Créer un profil**, entrez un **Nom** et une **Description** pour votre profil VPN.
7. À partir de la liste déroulante **Plateforme**, sélectionnez la plateforme d’appareil à laquelle vous souhaitez appliquer les paramètres VPN. Actuellement, vous pouvez choisir l’une des plateformes suivantes pour les paramètres personnalisés :
    - **Android**
    - **iOS** (configuré à l’aide d’un fichier que vous avez exporté à partir d’Apple Configurator).
    - **macOS** (configuré à l’aide d’un fichier que vous avez exporté à partir d’Apple Configurator).
    - **Windows Phone 8.1**
    - **Windows 10 et versions ultérieures**
6. Dans la liste déroulante **Type de profil**, choisissez **Personnalisé**.
7. Dans le panneau **Paramètres OMA-URI personnalisés**, choisissez **Ajouter** pour chaque paramètre d’URI que vous souhaitez spécifier, fournissez les informations demandées, puis choisissez **OK**. Voici un exemple :

   ![Boîte de dialogue de configuration personnalisée de profil VPN](./media/Intune_Add_VPN_URI.png)

4.  Une fois que vous avez entré tous les paramètres des URI dont vous avez besoin, choisissez **OK**, puis, dans le panneau **Créer un profil**, choisissez **Créer**.

Le profil est créé et s’affiche dans le panneau de la liste des profils.
Si vous souhaitez continuer et affecter ce profil à des groupes, consultez le [Guide pratique d’attribution des profils d’appareils](how-to-assign-device-profiles.md).

## <a name="example-uri-settings"></a>Exemples de paramètres URI

Ces paramètres peuvent être utilisés pour créer une configuration personnalisée d’un VPN dans une société fictive nommée Contoso.
Pour obtenir tous les détails sur l'ensemble des paramètres configurables, consultez [VPNv2 CSP](https://msdn.microsoft.com/en-us/library/windows/hardware/dn914776.aspx).

VPN Contoso natif (IKEv2) : ./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/Servers

vpn.contoso.com ./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/NativeProtocolType

Ikev2 ./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/RoutingPolicyType

SplitTunnel ./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/Authentication/UserMethod

Eap ./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/Authentication/Eap/Configuration &lt;EapHostConfig xmlns="http://www.microsoft.com/provisioning/EapHostConfig"&gt;&lt;EapMethod&gt;&lt;Type xmlns="http://www.microsoft.com/provisioning/EapCommon"&gt;13&lt;/Type&gt;&lt;VendorId xmlns="http://www.microsoft.com/provisioning/EapCommon"&gt;0&lt;/VendorId&gt;&lt;VendorType xmlns="http://www.microsoft.com/provisioning/EapCommon"&gt;0&lt;/VendorType&gt;&lt;AuthorId xmlns="http://www.microsoft.com/provisioning/EapCommon"&gt;0&lt;/AuthorId&gt;&lt;/EapMethod&gt;&lt;Config xmlns="http://www.microsoft.com/provisioning/EapHostConfig"&gt;&lt;Eap xmlns="http://www.microsoft.com/provisioning/BaseEapConnectionPropertiesV1"&gt;&lt;Type&gt;13&lt;/Type&gt;&lt;EapType xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV1"&gt;&lt;CredentialsSource&gt;&lt;CertificateStore&gt;&lt;SimpleCertSelection&gt;true&lt;/SimpleCertSelection&gt;&lt;/CertificateStore&gt;&lt;/CredentialsSource&gt;&lt;ServerValidation&gt;&lt;DisableUserPromptForServerValidation&gt;false&lt;/DisableUserPromptForServerValidation&gt;&lt;ServerNames&gt;&lt;/ServerNames&gt;&lt;/ServerValidation&gt;&lt;DifferentUsername&gt;false&lt;/DifferentUsername&gt;&lt;PerformServerValidation xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2"&gt;false&lt;/PerformServerValidation&gt;&lt;AcceptServerName xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2"&gt;false&lt;/AcceptServerName&gt;&lt;/EapType&gt;&lt;/Eap&gt;&lt;/Config&gt;&lt;/EapHostConfig&gt;

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

Pour toute question sur la façon dont ces paramètres doivent être utilisés, ou pour plus d’informations sur ce qu’ils font, consultez la documentation du fournisseur de services de configuration (CSP) : https://msdn.microsoft.com/en-us/library/windows/hardware/dn914776(v=vs.85).aspx.

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






<!--HONumber=Feb17_HO1-->


