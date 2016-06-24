---
# required metadata

title: Configurations personnalisées pour les profils VPN | Microsoft Intune
description:
keywords:
author: Nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 4c0bd439-3b58-420b-9a9a-282886986786

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Configurations personnalisées pour les profils VPN

## Créer une configuration personnalisée
Vous pouvez utiliser des configurations personnalisées pour créer des profils VPN dans Intune. Pour créer une configuration personnalisée

   1. Dans la console d’administration Intune **Stratégie** -> **Ajouter une stratégie** -> *<Expand platform>* -> **Configuration personnalisée** -> **Créer une stratégie**.
   2. Spécifiez un nom pour la stratégie.
   3. Pour chaque paramètre d’URI, cliquez sur **Ajouter** et fournissez les informations demandées. Voici un exemple :

   ![Boîte de dialogue de configuration personnalisée de profil VPN](./media/Intune_Add_VPN_URI.png)

   4.  Une fois que vous avez entré tous les paramètres d’URI, cliquez sur **Enregistrer la stratégie**, puis déployez la stratégie.

## Déployer une stratégie de configuration

1.  Dans l’espace de travail **Stratégie** , sélectionnez la stratégie à déployer, puis cliquez sur **Gérer le déploiement**.

2.  Dans la boîte de dialogue **Gérer le déploiement** :

    -   **Pour déployer la stratégie** : sélectionnez un ou plusieurs groupes sur lesquels déployer la stratégie, puis cliquez sur **Ajouter** &gt; **OK**.

    -   **Pour fermer la boîte de dialogue sans la déployer**, cliquez sur **Annuler**.

Quand vous sélectionnez une stratégie déployée, vous pouvez afficher d’autres informations sur le déploiement dans la partie inférieure de la liste de stratégies.

##Exemple de paramètres d’URI pour une configuration de profil VPN personnalisée
Voici des exemples d’entrées de valeurs d’URI pour créer une configuration personnalisée d’un VPN dans une société fictive nommée Contoso. Pour plus d’informations, telles que le type de données pour chaque entrée, consultez [VPNv2 CSP](https://msdn.microsoft.com/en-us/library/windows/hardware/dn914776.aspx)

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

Pour toute question sur la façon dont ces paramètres doivent être utilisés, ou pour plus d’informations sur ce qu’ils font, consultez la documentation du fournisseur de services de configuration (CSP) : https://msdn.microsoft.com/en-us/library/windows/hardware/dn914776(v=vs.85).aspx

## Paramètres d’URI pour les VPN Android par application sur PulseSecure
### URI PERSONNALISÉ POUR LA LISTE DES PACKAGES 
-  Type de données = Chaîne
-  OMA-URI = ./Vendor/MSFT/VPN/Profile/<Name>/PackageList 
-  Valeur = liste des packages séparés par des délimiteurs.
   - Délimiteurs : point-virgule (;), deux-points (:), virgule (,), barre verticale (|)

Exemples : 
- com.android.chrome
- com.android.chrome;com.android.browser

### URI PERSONNALISÉ POUR LE MODE (FACULTATIF)
- Type de données = Chaîne
- OMA-URI = ./Vendor/MSFT/VPN/Profile/NAME/Mode 

> Remarques
> - Utilisez le même *nom* que celui que vous avez affecté au profil personnalisé
> - Valeurs possibles : *GLOBAL*, *WHITELIST*, *BLACKLIST*
> - La valeur par défaut est *GLOBAL* si aucun PackageList n’est fourni (compatibilité descendante avec les profils à l’échelle du système)
> - La valeur par défaut est *WHITELIST* si un PackageList est fourni.


### Voir aussi
(Connexions VPN dans Microsoft Intune)[vpn-connections-in-microsoft-intune.md]


<!--HONumber=Jun16_HO1-->


