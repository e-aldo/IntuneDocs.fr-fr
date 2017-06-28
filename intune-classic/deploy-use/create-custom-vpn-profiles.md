---
title: "Configurations personnalisées pour les profils VPN Microsoft Intune"
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
ms.translationtype: Human Translation
ms.sourcegitcommit: df3c42d8b52d1a01ddab82727e707639d5f77c16
ms.openlocfilehash: 2ee20ce0b9f7794132c3a56046b1680f940b3424
ms.contentlocale: fr-fr
ms.lasthandoff: 06/08/2017


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

Ensuite, [déployez la stratégie](/intune-classic/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies#deploy-a-configuration-policy) comme d’habitude.

## <a name="example-uri-settings"></a>Exemples de paramètres URI

Ces paramètres peuvent être utilisés pour créer une configuration personnalisée d’un VPN dans une société fictive nommée Contoso.
Pour obtenir tous les détails sur l'ensemble des paramètres configurables, consultez [VPNv2 CSP](https://msdn.microsoft.com/library/windows/hardware/dn914776.aspx).

**VPN Contoso natif (IKEv2) :**<br />
./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/Servers

**vpn.contoso.com**<br />
./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/NativeProtocolType

**Ikev2<br />** ./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/RoutingPolicyType

**SplitTunnel**<br />
./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/Authentication/UserMethod

**Eap**<br />
./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/Authentication/Eap/Configuration
``` xml
<EapHostConfig xmlns="http://www.microsoft.com/provisioning/EapHostConfig">
   <EapMethod>
      <Type xmlns="http://www.microsoft.com/provisioning/EapCommon">13</Type>
      <VendorId xmlns="http://www.microsoft.com/provisioning/EapCommon">0</VendorId>
      <VendorType xmlns="http://www.microsoft.com/provisioning/EapCommon">0</VendorType>
      <AuthorId xmlns="http://www.microsoft.com/provisioning/EapCommon">0</AuthorId>
   </EapMethod>
   <Config xmlns="http://www.microsoft.com/provisioning/EapHostConfig">
      <Eap xmlns="http://www.microsoft.com/provisioning/BaseEapConnectionPropertiesV1">
         <Type>13</Type>
         <EapType xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV1">
            <CredentialsSource>
               <CertificateStore>
                  <SimpleCertSelection>true</SimpleCertSelection>
               </CertificateStore>
            </CredentialsSource>
            <ServerValidation>
               <DisableUserPromptForServerValidation>false</DisableUserPromptForServerValidation>
               <ServerNames></ServerNames>
            </ServerValidation>
            <DifferentUsername>false</DifferentUsername>
            <PerformServerValidation xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">
               false
            </PerformServerValidation>
            <AcceptServerName xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">
               false
            </AcceptServerName>
         </EapType>
      </Eap>
   </Config>
</EapHostConfig>
```
**./Vendor/MSFT/VPNv2/ContosoVPN/ByPassForLocal**<br />
True

**./Vendor/MSFT/VPNv2/ContosoVPN/RememberCredentials**<br />
1

**./Vendor/MSFT/VPNv2/ContosoVPN/DomainNameInformationList/1/DomainName**<br />
Corp.Contoso.com

**./Vendor/MSFT/VPNv2/ContosoVPN/DnsSuffix**<br />
Corp.Contoso.com

**./Vendor/MSFT/VPNv2/ContosoVPN/TrustedNetworkDetection**<br />
Corp.Contoso.com

**./Vendor/MSFT/VPNv2/ContosoVPN/RouteList/1/Address**<br />
10.0.0.0

**./Vendor/MSFT/VPNv2/ContosoVPN/RouteList/1/PrefixSize**<br />
8

**./Vendor/MSFT/VPNv2/ContosoVPN/AlwaysOn**<br />
true

**./Vendor/MSFT/VPNv2/ContosoVPN/AppTriggerList/0/App/Id**<br />
%PROGRAMFILES%\Internet Explorer\iexplore.exe

**./Vendor/MSFT/VPNv2/ContosoVPN/AppTriggerList/1/App/Id**<br />
%PROGRAMFILES% (x86)\Internet Explorer\iexplore.exe

**./Vendor/MSFT/VPNv2/ContosoVPN/AppTriggerList/2/App/Id**<br />
Microsoft.MicrosoftEdge_8wekyb3d8bbwe

**./Vendor/MSFT/VPNv2/ContosoVPN/TrafficFilterList/0/App/Id**<br />
%PROGRAMFILES% (x86)\Internet Explorer\iexplore.exe

**./Vendor/MSFT/VPNv2/ContosoVPN/TrafficFilterList/1/App/Id**<br />
Microsoft.MicrosoftEdge_8wekyb3d8bbwe

Pour toute question sur la façon dont ces paramètres doivent être utilisés, ou pour plus d’informations sur ce qu’ils font, consultez la [documentation du fournisseur de services de configuration (CSP)](https://msdn.microsoft.com/library/windows/hardware/dn914776(v=vs.85).aspx).

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

