---
title: Paramètres VPN pour les appareils iOS dans Microsoft Intune - Azure | Microsoft Docs
description: Voir les paramètres de configuration de réseau privé virtuel (VPN) disponibles, notamment les détails de la connexion, les méthodes d’authentification et la tunnelisation fractionnée, dans les paramètres de base ; les paramètres VPN personnalisés avec l’identificateur et les paires clé-valeur ; les paramètres VPN par application qui incluent des URL Safari et des réseaux VPN à la demande avec SSID ou domaines de recherche DNS ; et les paramètres de proxy pour inclure un script de configuration, une adresse IP ou de nom de domaine complet et le port TCP dans Microsoft Intune sur les appareils exécutant iOS.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 5/16/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 05d93f1518427201d9d96dbc22c772967fe4fa0f
ms.sourcegitcommit: 97b9f966f23895495b4c8a685f1397b78cc01d57
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34744565"
---
# <a name="configure-vpn-settings-in-microsoft-intune-for-devices-running-ios"></a>Configurer les paramètres VPN dans Microsoft Intune pour les appareils exécutant iOS

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Cet article présente les paramètres Intune permettant de configurer des connexions VPN sur les appareils exécutant iOS.

Selon les paramètres que vous choisissez, toutes les valeurs de la liste suivante ne sont pas nécessairement configurables.

## <a name="base-vpn-settings"></a>Paramètres VPN de base

- **Nom de connexion** : entrez un nom pour cette connexion. Les utilisateurs finaux voient ce nom quand ils recherchent dans leur appareil une liste de connexions VPN disponibles.
- **Adresse IP ou nom de domaine complet** : entrez l’adresse IP ou le nom de domaine complet (FQDN) du serveur VPN auquel les appareils se connectent. Par exemple, entrez **192.168.1.1** ou **vpn.contoso.com**.
- **Méthode d’authentification** : choisissez la façon dont les appareils s’authentifient auprès du serveur VPN à partir de :
  - **Certificats** : sous **Certificat d’authentification**, sélectionnez un profil de certificat SCEP ou PKCS existant pour authentifier la connexion. [Configurer les certificats](certificates-configure.md) fournit quelques conseils sur les profils de certificat.
  - **Nom d’utilisateur et mot de passe** : les utilisateurs finaux doivent entrer un nom d’utilisateur et un mot de passe pour se connecter au serveur VPN.

    > [!NOTE]
    > Si le nom d’utilisateur et le mot de passe sont utilisés comme méthode d’authentification pour les VPN IPsec Cisco, ils doivent fournir le SharedSecret par le biais d’un profil Apple Configurator personnalisé.
  
- **Type de connexion** : sélectionnez le type de connexion VPN dans la liste de fournisseurs suivante :
  - **Check Point Capsule VPN**
  - **Cisco AnyConnect**
  - **Cisco Legacy AnyConnect**
  - **SonicWall Mobile Connect**
  - **Client F5 Edge**
  - **Palo Alto Networks GlobalProtect**
  - **Pulse Secure**
  - **Cisco (IPSec)**
  - **Citrix**
  - **VPN personnalisé**

    > [!NOTE]
    > - Les profils VPN **Cisco Legacy AnyConnect** sont destinés à l’application [Cisco Legacy AnyConnect](https://itunes.apple.com/app/cisco-legacy-anyconnect/id392790924) version 4.0.5x et versions antérieures
    > - Les profils VPN **Cisco AnyConnect** sont destinés à l’application [Cisco AnyConnect](https://itunes.apple.com/app/cisco-anyconnect/id1135064690) version 4.0.7x et versions ultérieures

- **Tunneling fractionné** : **activez**ou **désactivez** cette option pour laisser les appareils décider quelle connexion utiliser en fonction du trafic. Par exemple, un utilisateur dans un hôtel utilise la connexion VPN pour accéder à ses fichiers de travail, mais utilise le réseau standard de l’hôtel pour surfer sur Internet.

## <a name="custom-vpn-settings"></a>Paramètres VPN personnalisés

Si vous avez sélectionné **VPN personnalisé** comme type de connexion, configurez également les paramètres suivants :

- **Identificateur VPN** : identificateur pour l’application VPN que vous utilisez, qui est fourni par votre fournisseur VPN.
- **Entrez les paires clé-valeur pour les attributs du VPN personnalisé** : ajoutez ou importez des **Clés** et **Valeurs** pour personnaliser votre connexion VPN. Là encore, ces valeurs sont généralement fournies par votre fournisseur de VPN.

## <a name="apps-per-app-vpn-settings"></a>Paramètres des applications (VPN par application)

- **VPN par application** : activez cette option pour utiliser des URL qui activent la connexion VPN quand elles sont consultées à partir du navigateur Safari. Pour configurer un VPN par application, vous devez sélectionner **Certificats** comme méthode d’authentification dans les paramètres VPN de base.
  - **URL Safari qui déclenchent ce VPN** : sélectionnez cette option pour ajouter une ou plusieurs URL de site web. Quand ces URL sont consultées, la connexion VPN est activée.

- **VPN à la demande** : configurez des règles conditionnelles qui contrôlent l’activation de la connexion VPN. Par exemple, créez une condition dans laquelle la connexion VPN est utilisée uniquement quand un appareil n’est pas connecté au réseau Wi-Fi d’une société. Ou bien créez une condition dans laquelle la connexion VPN n’est pas lancée si un appareil ne peut pas accéder à un domaine de recherche DNS que vous spécifiez.

  - **Domaines de recherche DNS ou SSID** : indiquez si cette condition utilise les **SSID** de réseau sans fil ou les **domaines de recherche DNS**. Cliquez sur **Ajouter** pour configurer un ou plusieurs SSID ou domaines de recherche.
  - **Sonde de chaîne d’URL** : facultatif. Entrez une URL que la règle utilise comme test. Si l’appareil sur lequel ce profil est installé peut accéder à cette URL sans redirection, la connexion VPN est lancée et l’appareil se connecte à l’URL cible. L’utilisateur ne voit pas le site de la sonde de chaîne d’URL. Par exemple, une sonde de chaîne d’URL peut être l’adresse d’un serveur web d’audit qui vérifie la compatibilité de l’appareil avant la connexion du VPN. Autre exemple, l’URL teste la capacité du VPN à se connecter à un site avant de connecter l’appareil à l’URL cible via le VPN.
  - **Action du domaine** : choisissez l’un des éléments suivants :
    - Se connecter si nécessaire
    - Ne jamais se connecter
  - **Action** : choisissez l’un des éléments suivants :
    - Se connecter
    - Évaluer la connexion
    - Ignorer
    - Se déconnecter

## <a name="proxy-settings"></a>Paramètres du proxy

- **Script de configuration automatique** : utilisez un fichier de configuration pour configurer le serveur proxy. Entrez **l’URL du serveur proxy** (par exemple **http://proxy.contoso.com**) qui contient le fichier de configuration.
- **Adresse** : entrez l’adresse IP du nom d’hôte complet du serveur proxy.
- **Numéro de port** : entrez le numéro de port associé au serveur proxy.

## <a name="next-step"></a>Étape suivante
[Créer des profils VPN dans Intune](vpn-settings-configure.md)
