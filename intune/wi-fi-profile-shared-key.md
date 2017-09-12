---
title: "Création d’un profil Wi-Fi avec une clé prépartagée"
titleSuffix: Azure portal
description: "Utiliser un profil personnalisé Intune pour créer un profil Wi-Fi avec une clé prépartagée."
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 05/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c6fd72a6-7dc8-48fc-9df1-db5627a51597
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: c524acc403d6a1c041aa0dcea0948c2707202e03
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/09/2017
---
# <a name="use-a-microsoft-intune-custom-device-profile-to-create-a-wi-fi-profile-with-a-pre-shared-key"></a>Utiliser un profil d’appareil personnalisé Microsoft Intune pour créer un profil Wi-Fi avec une clé prépartagée
[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Voici comment utiliser les **Profils d’appareil personnalisés** d’Intune pour créer un profil Wi-Fi avec une clé prépartagée. Cette rubrique comprend également un exemple de création d’un profil Wi-Fi basé sur EAP.

> [!NOTE]
-   Il peut s’avérer plus facile de copier le code à partir d’un ordinateur qui se connecte à ce réseau, comme décrit ci-dessous.
- Pour Android, vous avez également la possibilité d’utiliser ce [générateur de clés prépartagées Android](http://johnathonb.com/2015/05/intune-android-pre-shared-key-generator/) fourni par Johnathon Biersack.
-   Vous pouvez ajouter plusieurs réseaux et plusieurs clés en ajoutant davantage de paramètres OMA-URI.
-  Pour iOS, utilisez l’outil Apple Configurator sur une station Mac pour installer le profil. Vous pouvez également utiliser le [générateur de configuration mobile de clés prépartagées pour iOS](http://johnathonb.com/2015/05/intune-ios-psk-mobile-config-generator/) fourni par Johnathon Biersack.


1.  Pour créer un profil Wi-Fi avec une clé préalablement partagée pour Android ou Windows ou un profil Wi-Fi basé sur EAP, choisissez **Personnalisé** pour cette plateforme d’appareil au lieu d’un profil Wi-Fi quand vous créez un profil d’appareil.

2.  Fournissez un nom et une description.
3.  Ajoutez un paramètre OMA-URI :

   a.   Entrez un nom pour ce paramètre de réseau Wi-Fi.

   b.   Entrez une description du paramètre OMA-URI ou laissez-la vide.

   c.   **Type de données** : définissez sur **String**.

   d.   **OMA-URI** :

    - **Pour Android** : ./Vendor/MSFT/WiFi/Profile/<SSID>/Settings
    - **Pour Windows** : ./Vendor/MSFT/WiFi/Profile/MyNetwork/WlanXml

    > [!NOTE]
Veillez à inclure le point au début.

    Le SSID est l’identificateur SSID pour lequel vous créez la stratégie. Par exemple, `./Vendor/MSFT/WiFi/Profile/Hotspot-1/Settings`.

  e. **Champ de valeur** correspond à l’endroit où vous collez le code XML. Voici un exemple. Chaque valeur doit être adaptée à vos paramètres réseau. Consultez la section Commentaires du code pour certains pointeurs.
4. Choisissez **OK**, enregistrez et affectez la stratégie.

    > [!NOTE]
    > Cette stratégie peut être attribuée uniquement à des groupes d’utilisateurs.

La prochaine fois que chaque appareil s’enregistrera, la stratégie sera appliquée et un profil Wi-Fi sera créé sur l’appareil. L’appareil sera en mesure de se connecter automatiquement au réseau.

## <a name="android-or-windows-wi-fi-profile"></a>Profil Wi-Fi Android ou Windows

Voici un exemple de code XML pour un profil Wi-Fi Android ou Windows :

> [!IMPORTANT]
>
> `<protected>false</protected>`doit être défini sur **false**, car la valeur **true** peut amener l’appareil à attendre un mot de passe chiffré et à tenter de le déchiffrer, ce qui risque d’entraîner un échec de connexion.
>
>  `<hex>53534944</hex>` doit être défini sur la valeur hexadécimale de `<name><SSID of wifi profile></name>`.
>  Les appareils Windows 10 peuvent retourner une fausse erreur *0x87D1FDE8 Échec de la correction* et être néanmoins configurés avec le profil.

```
<!--
<Name of wifi profile> = Name of profile
<SSID of wifi profile> = Plain text of SSID. Does not need to be escaped, could be <name>Your Company's Network</name>
<nonBroadcast><true/false></nonBroadcast>
<Type of authentication> = Type of authentication used by the network, such as WPA2PSK.
<Type of encryption> = Type of encryption used by the network
<protected>false</protected> do not change this value, as true could cause device to expect an encrypted password and then try to decrypt it, which may result in a failed connection.
<password> = Password to connect to the network
x>53534944</hex> should be set to the hexadecimal value of <name><SSID of wifi profile></name>
-->
<WLANProfile
xmlns="http://www.microsoft.com/networking/WLAN/profile/v1">
  <name><Name of wifi profile></name>
  <SSIDConfig>
    <SSID>
      <hex>53534944</hex>
 <name><SSID of wifi profile></name>
    </SSID>
    <nonBroadcast>false</nonBroadcast>
  </SSIDConfig>
  <connectionType>ESS</connectionType>
  <connectionMode>auto</connectionMode>
  <autoSwitch>false</autoSwitch>
  <MSM>
    <security>
      <authEncryption>
        <authentication><Type of authentication></authentication>
        <encryption><Type of encryption></encryption>
        <useOneX>false</useOneX>
      </authEncryption>
      <sharedKey>
        <keyType>networkKey</keyType>
        <protected>false</protected>
        <keyMaterial>MyPassword</keyMaterial>
      </sharedKey>
      <keyIndex>0</keyIndex>
    </security>
  </MSM>
</WLANProfile>
```

## <a name="eap-based-wi-fi-profile"></a>Profil Wi-Fi basé sur EAP
Voici un exemple du code XML pour un profil Wi-Fi basé sur EAP :

```
    <WLANProfile xmlns="http://www.microsoft.com/networking/WLAN/profile/v1">
      <name>testcert</name>
      <SSIDConfig>
        <SSID>
          <hex>7465737463657274</hex>
          <name>testcert</name>
        </SSID>
        <nonBroadcast>true</nonBroadcast>
      </SSIDConfig>
      <connectionType>ESS</connectionType>
      <connectionMode>auto</connectionMode>
      <autoSwitch>false</autoSwitch>
      <MSM>
        <security>
          <authEncryption>
            <authentication>WPA2</authentication>
            <encryption>AES</encryption>
            <useOneX>true</useOneX>
            <FIPSMode     xmlns="http://www.microsoft.com/networking/WLAN/profile/v2">false</FIPSMode>
          </authEncryption>
          <PMKCacheMode>disabled</PMKCacheMode>
          <OneX xmlns="http://www.microsoft.com/networking/OneX/v1">
            <cacheUserData>false</cacheUserData>
            <authMode>user</authMode>
            <EAPConfig>
              <EapHostConfig     xmlns="http://www.microsoft.com/provisioning/EapHostConfig">
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
                      <PerformServerValidation xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">false</PerformServerValidation>
                      <AcceptServerName xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">false</AcceptServerName>
                      <TLSExtensions xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">
                        <FilteringInfo xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV3">
                          <AllPurposeEnabled>true</AllPurposeEnabled>
                          <CAHashList Enabled="true">
                            <IssuerHash>75 f5 06 9c a4 12 0e 9b db bc a1 d9 9d d0 f0 75 fa 3b b8 78 </IssuerHash>
                          </CAHashList>
                          <EKUMapping>
                            <EKUMap>
                              <EKUName>Client Authentication</EKUName>
                              <EKUOID>1.3.6.1.5.5.7.3.2</EKUOID>
                            </EKUMap>
                          </EKUMapping>
                          <ClientAuthEKUList Enabled="true"/>
                          <AnyPurposeEKUList Enabled="false">
                            <EKUMapInList>
                              <EKUName>Client Authentication</EKUName>
                            </EKUMapInList>
                          </AnyPurposeEKUList>
                        </FilteringInfo>
                      </TLSExtensions>
                    </EapType>
                  </Eap>
                </Config>
              </EapHostConfig>
            </EAPConfig>
          </OneX>
        </security>
      </MSM>
    </WLANProfile>
```

## <a name="create-the-xml-file-from-an-existing-wi-fi-connection"></a>Création du fichier XML à partir d’une connexion Wi-Fi existante
Vous pouvez également créer un du fichier XML à partir d’une connexion Wi-Fi existante :
1. Sur un ordinateur connecté au réseau sans fil ou qui s’y est connecté récemment, ouvrez le dossier suivant : C:\ProgramData\Microsoft\Wlansvc\Profiles\Interfaces\{guid}.

    Il est préférable d’utiliser un ordinateur qui n’est pas connecté à plusieurs réseaux sans fil, car vous devrez effectuer des recherches dans chaque profil pour trouver celui qui convient.
3.     Recherchez dans les fichiers XML pour trouver celui dont le nom est correct.
4.     Une fois que vous avez localisé le fichier XML approprié, copiez et collez le code XML dans le champ de données de la page de paramètres OMA-URI.
