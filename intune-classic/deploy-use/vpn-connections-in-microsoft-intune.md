---
title: Connexions VPN
description: "Utilisez les profils VPN afin de déployer des paramètres VPN pour les utilisateurs et appareils de votre organisation."
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 05/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: abc57093-7351-408f-9f41-a30877f96f73
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 5b1140d990ac5d1c4364b1f48107a355c43c6cdb
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/10/2017
---
# <a name="vpn-connections-in-microsoft-intune"></a>Connexions VPN dans Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Les réseaux privés virtuels (ou VPN) donnent à vos utilisateurs un accès distant sécurisé à votre réseau d’entreprise. Les appareils utilisent un *profil de connexion VPN* pour établir une connexion avec le serveur VPN. Utilisez les *profils VPN* dans Microsoft Intune pour déployer des paramètres VPN sur les utilisateurs et appareils de votre organisation, afin qu’ils puissent se connecter au réseau facilement et en toute sécurité.

Par exemple, supposons que vous voulez approvisionner tous les appareils iOS en fonction des paramètres nécessaires pour se connecter à un partage de fichiers sur le réseau d’entreprise. Vous créez un profil VPN contenant les paramètres nécessaires pour se connecter au réseau d’entreprise, puis vous déployez ce profil pour tous les utilisateurs qui ont des appareils iOS. Les utilisateurs voient la connexion VPN dans la liste des réseaux disponibles et peuvent se connecter avec un minimum d’effort.

Vous pouvez configurer les types d’appareil suivants avec des profils VPN :

* Appareils qui exécutent Android 4 et versions ultérieures
* Appareils Android for Work
* Appareils qui exécutent iOS 8.0 et versions ultérieures
* Appareils qui exécutent Mac OS X 10.9 et versions ultérieures
* Appareils inscrits qui exécutent Windows 8.1 et versions ultérieures
* Appareils qui exécutent Windows Phone 8.1 et versions ultérieures
* Appareils qui exécutent Windows 10 Desktop et Mobile

Les options de configuration de profil VPN varient selon le type d’appareil sélectionné.

## <a name="vpn-connection-types"></a>Types de connexions VPN

Intune prend en charge la création de profils VPN qui utilisent les types de connexions suivants :


Type de connexion |iOS et Mac OS X  |Android et Android for Work|Windows 8.1|Windows RT 8.1|Windows Phone 8.1|Windows 10 Desktop et Mobile |
----------------|------------------|-------|-----------|----------|--------------|-----------------|----------------------|
Cisco AnyConnect|Oui |Oui   |Non    |Non  |Non    | Oui (OMA-URI, mobile uniquement)|     
Cisco (IPsec)|Oui |Oui   |Non  |Non  |Non | Non|
Citrix|Oui |Oui (Android uniquement)   |Non  |Non  |Non | Non|
Pulse Secure|Oui  |Oui |Oui   |Oui  |Oui| Oui|        
Client F5 Microsoft Edge|Oui |Oui |Oui |Oui  |   Oui |  Oui|   
Dell SonicWALL Mobile Connect|Oui |Oui |Oui |Oui |Oui |Oui|         
CheckPoint Mobile VPN|Oui |Oui |Oui |Oui|Oui|Oui|
Microsoft SSL (SSTP)|Non |Non |Non |Non|Non|VPNv1 OMA-URI*|
Microsoft Automatic|Non |Non |Non |Non|Oui (OMA-URI)|Oui|
IKEv2|Profil personnalisé iOS|Non |Non |Non|Oui (OMA-URI)|Oui|
PPTP|Profil personnalisé iOS|Non |Non |Non|Non|Oui|
L2TP|Profil personnalisé iOS|Non |Non |Non|Oui (OMA-URI)|Oui|

\* Sans les paramètres supplémentaires qui sont disponibles pour Windows 10.

> [!IMPORTANT]
> Avant de pouvoir utiliser les profils VPN déployés sur un appareil, vous devez installer l'application VPN applicable pour le profil. Vous pouvez utiliser les informations fournies dans la rubrique [Déployer des applications dans Microsoft Intune](deploy-apps-in-microsoft-intune.md) pour vous aider à déployer l’application applicable avec Intune.  

 Apprenez à créer des profils VPN personnalisés à l’aide des paramètres de l’URI dans [Configurations personnalisées pour les profils VPN](create-custom-vpn-profiles.md).     

## <a name="methods-of-securing-vpn-profiles"></a>Méthodes de sécurisation des profils VPN

Les profils VPN peuvent utiliser différents types de connexion et protocole de fabricants différents. Ces connexions sont généralement sécurisées à l’aide de l’une des deux méthodes suivantes.

### <a name="certificates"></a>Certificats

Quand vous créez le profil VPN, vous choisissez un profil de certificat SCEP ou PFX que vous avez créé précédemment dans Intune. Il s’agit du certificat d’identité. Il est utilisé pour effectuer une authentification auprès d’un profil de certificat approuvé (ou *certificat racine*) que vous avez créé pour établir que l’utilisateur est autorisé à se connecter. Le certificat approuvé est déployé sur l'ordinateur qui authentifie la connexion VPN, en règle générale le serveur VPN.

Pour plus d’informations sur la création et l’utilisation des profils de certificat dans Intune, consultez [Sécuriser l’accès aux ressources avec des profils de certificat](secure-resource-access-with-certificate-profiles.md).

### <a name="user-name-and-password"></a>Nom d'utilisateur et mot de passe

L’utilisateur s’authentifie auprès du serveur VPN en fournissant un nom d’utilisateur et un mot de passe.

## <a name="create-a-vpn-profile"></a>Créer un profil VPN

1. Dans la [console d’administration Microsoft Intune](https://manage.microsoft.com), choisissez **Stratégie** > **Ajouter une stratégie**.
2. Sélectionnez un modèle pour la nouvelle stratégie en développant le type d’appareil approprié, puis choisissez le profil VPN pour cet appareil :
    * **Profil VPN (Android 4 et versions ultérieures)**
    * **Profil VPN (Android for Work)**
    * **Profil VPN (iOS 8.0 et versions ultérieures)**
    * **Profil VPN (Mac OS X 10.9 et versions ultérieures)**
    * **Profil VPN (Windows 8.1 et versions ultérieures)**
    * **Profil VPN (Windows Phone 8.1 et versions ultérieures)**
    * **Profil VPN (Windows 10 Desktop et Mobile, et versions ultérieures)**

 Vous pouvez créer et déployer une stratégie de profil VPN personnalisée uniquement. Les paramètres recommandés ne sont pas disponibles.

> [!Note]
> Un profil VPN pour les appareils Android for Work ne permet une connexion VPN que pour les applications qui sont installées sur le profil professionnel de l’appareil.
>
> Certains types de connexions VPN prennent en charge le mode VPN par application pour les appareils Android for Work et pour l’activation du mode VPN par application sur les applications distribuées via Intune.  

3. Utilisez le tableau suivant pour vous aider à configurer les paramètres de profil VPN :

Nom du paramètre  |Plus d'informations  
---------|---------
**Nom**     |Entrez un nom unique pour le profil VPN pour vous aider à l’identifier dans la console Intune.         
**Description**     |Fournissez une description qui donne un aperçu du profil VPN et d'autres informations pertinentes pour mieux le localiser.         
**Nom de la connexion VPN (affiché aux utilisateurs)**     |Spécifiez un nom pour le profil VPN. Il s'agit du nom que voient les utilisateurs dans la liste des connexions VPN disponibles sur leurs appareils.         
**Type de connexion**     |  Sélectionnez l’un des types de connexions suivants à utiliser dans le profil VPN : **Cisco AnyConnect** (non disponible pour Windows 8.1 ou Windows Phone 8.1), **Pulse Secure**, **Citrix**, **F5 Edge Client**, **Dell SonicWALL Mobile Connect**, **CheckPoint Mobile VPN**.
**Description du serveur VPN**     | Spécifiez une description pour le serveur VPN auquel les appareils se connecteront. Exemple : **serveur VPN Contoso**. Quand le type de connexion est **Client F5 Microsoft Edge**, utilisez le champ **Liste de serveurs** pour spécifier une liste de descriptions et d'adresses IP de serveur.
**Adresse IP du serveur ou nom de domaine complet**    |Fournissez l'adresse IP ou le nom de domaine complet du serveur VPN auquel les appareils se connectent. Exemples : **192.168.1.1**, **vpn.contoso.com**.  Quand le type de connexion est **Client F5 Microsoft Edge**, utilisez le champ **Liste de serveurs** pour spécifier une liste de descriptions et d'adresses IP de serveur.         |         
**Liste de serveurs**     |Choisissez **Ajouter** pour ajouter un nouveau serveur VPN à utiliser pour la connexion VPN. Vous pouvez aussi spécifier le serveur par défaut pour la connexion. Cette option est visible uniquement quand le type de connexion est **Client F5 Microsoft Edge**.         
**Envoyer tout le trafic réseau via la connexion VPN**     |Si vous sélectionnez cette option, tout le trafic réseau est envoyé via la connexion VPN. Si vous ne sélectionnez pas cette option, le client négocie dynamiquement les itinéraires pour le tunneling fractionné durant la connexion au serveur VPN tiers. Seules les connexions au réseau d'entreprise sont envoyées via un tunnel VPN. La tunnelisation VPN n'est pas utilisée quand vous vous connectez à des ressources sur Internet.
**Méthodes d’authentification**| Sélectionnez la méthode d’authentification que la connexion VPN utilise : **Certificats** ou **Nom d’utilisateur et mot de passe**. (**Nom d’utilisateur et mot de passe** n’est pas disponible quand le type de connexion est Cisco AnyConnect.) L'option **Méthode d’authentification** n’est pas disponible pour Windows 8.1.
**Conserver les informations d’identification de l’utilisateur à chaque ouverture de session**|Sélectionnez cette option pour vous assurer que les informations d'identification sont mémorisées, pour que l'utilisateur n'ait pas à les entrer chaque fois qu'une connexion est établie.
**Sélectionner un certificat client pour l’authentification client (certificat d’identité)**|Sélectionnez le certificat SCEP client que vous avez créé précédemment et qui sera utilisé pour authentifier la connexion VPN. Pour plus d’informations sur la façon de créer des profils de certificat dans Intune, consultez [Sécuriser l’accès aux ressources avec des profils de certificat](secure-resource-access-with-certificate-profiles.md). Cette option est visible uniquement quand la méthode d'authentification est **Certificats**.
**Rôle**| Spécifiez le nom du rôle d'utilisateur qui a accès à cette connexion. Un rôle d’utilisateur définit des options et des paramètres personnels, et active ou désactive certaines fonctionnalités d’accès. Cette option est visible uniquement quand le type de connexion est **Pulse Secure** ou **Citrix**.
**Domaine**|Spécifiez le nom du domaine d'authentification que vous souhaitez utiliser. Un domaine d’authentification est un regroupement de ressources d’authentification qu’utilise le type de connexion Pulse Secure ou Citrix. Cette option est visible uniquement quand le type de connexion est **Pulse Secure** ou **Citrix**.
**Groupe de connexion ou domaine**|Spécifiez le nom du groupe de connexion ou domaine auquel vous souhaitez vous connecter. Cette option est visible uniquement quand le type de connexion est **Dell SonicWALL Mobile Connect**.
**Empreinte digitale**|Spécifiez une chaîne (par exemple « Code d’empreinte digitale Contoso ») qui sera utilisée pour vérifier que le serveur VPN est digne de confiance. Une empreinte digitale peut être envoyée au client pour que celui-ci sache qu’il peut approuver n’importe quel serveur présentant cette même empreinte lors de la connexion. Si l’appareil n’a pas encore l’empreinte digitale, il invite l’utilisateur à approuver le serveur VPN auquel il se connecte en affichant l’empreinte digitale. (L’utilisateur vérifie manuellement l’empreinte digitale et choisit **confiance** pour se connecter.) Cette option est visible uniquement quand le type de connexion est **CheckPoint Mobile VPN**.
**Par VPN d’application**|Sélectionnez cette option si vous souhaitez associer cette connexion VPN à une application iOS ou Mac OS X pour que la connexion s’ouvre quand l’application est exécutée. Vous pouvez associer le profil VPN à une application lors du déploiement du logiciel. Pour plus d’informations, consultez [Déployer des applications dans Microsoft Intune](deploy-apps-in-microsoft-intune.md).
**VPN à la demande**|Vous pouvez configurer un VPN à la demande pour les appareils iOS 8.0 et versions ultérieures. Pour savoir comment procéder, consultez [VPN à la demande pour les appareils iOS](#on-demand-vpn-for-ios-devices).
**Détecter automatiquement les paramètres du proxy** (iOS, Mac OS X, Windows 8.1 et Windows Phone 8.1 uniquement)|Si votre serveur VPN nécessite un serveur proxy pour la connexion, spécifiez si vous souhaitez que les appareils détectent automatiquement les paramètres de connexion. Pour plus d'informations, consultez la documentation de Windows Server.
**Utiliser un script de configuration automatique** (iOS, Mac OS X, Windows 8.1 et Windows Phone 8.1 uniquement)|Si votre serveur VPN nécessite un serveur proxy pour la connexion, spécifiez si vous souhaitez utiliser un script de configuration automatique pour définir les paramètres, puis spécifiez une URL vers le fichier qui contient les paramètres. Pour plus d'informations, consultez la documentation de Windows Server.
**Utiliser un serveur proxy** (iOS, Mac OS X, Windows 8.1 et Windows Phone 8.1 uniquement)|Si votre serveur VPN nécessite un serveur proxy pour la connexion, sélectionnez cette option, puis spécifiez l'adresse et le numéro de port du serveur proxy. Pour plus d'informations, consultez la documentation de Windows Server.
**Ignorer les paramètres du proxy pour les adresses locales** (iOS, Mac OS X, Windows 8.1 et Windows Phone 8.1 uniquement)|Si votre serveur VPN nécessite un serveur proxy pour la connexion, sélectionnez cette option si vous ne souhaitez pas utiliser le serveur proxy pour les adresses locales que vous spécifiez. Pour plus d'informations, consultez la documentation de Windows Server.
**XML personnalisé** (Windows 8.1 et versions ultérieures, et Windows Phone 8.1 et versions ultérieures)|Spécifiez des commandes XML personnalisées qui configurent la connexion VPN. Exemple pour **Pulse Secure** : &lt;pulse-schema&gt;&lt;isSingleSignOnCredential&gt;true&lt;/isSingleSignOnCredential&gt;&lt;/pulse-schema&gt;. Exemple pour **CheckPoint Mobile VPN** : &lt;CheckPointVPN port="443" name="CheckPointSelfhost" sso="true"  debug="3" /&gt;. Exemple pour **Dell SonicWALL Mobile Connect** : &lt;MobileConnect&gt;&lt;Compression&gt;false&lt;/Compression&gt;&lt;debugLogging&gt;True&lt;/debugLogging&gt;&lt;packetCapture&gt;False&lt;/packetCapture&gt;&lt;/MobileConnect&gt;. Exemple pour **F5 Edge Client** : &lt;f5-vpn-conf&gt;&lt;single-sign-on-credential /&gt;&lt;/f5-vpn-conf&gt;. Pour plus d’informations sur l’écriture des commandes XML personnalisées, reportez-vous à la documentation du VPN de chaque fabricant.
**Liste de recherche de suffixes DNS** (Windows Phone 8.1 uniquement)|Spécifiez un suffixe DNS sur chaque ligne. Chaque suffixe DNS que vous spécifiez sera recherché lors de la connexion à un site web en utilisant un nom court. Par exemple, spécifiez les suffixes DNS **domain1.contoso.com** et **domain2.contoso.com**, accédez à l'URL **http://mywebsite**, et les URL **http://mywebsite.domain1.contoso.com** et **http://mywebsite.domain2.contoso.com** seront recherchées.
**Ignorer VPN lors d'une connexion à un réseau Wi-Fi de l'entreprise** (Windows Phone 8.1 uniquement)|Sélectionnez cette option pour indiquer que la connexion VPN n’est pas utilisée quand l’appareil est connecté au réseau Wi-Fi d’entreprise.
**Ignorer le VPN en cas de connexion à un réseau Wi-Fi domestique** (Windows Phone 8.1 uniquement)|Sélectionnez cette option pour indiquer que la connexion VPN n’est pas utilisée quand l’appareil est connecté à un réseau Wi-Fi domestique.

Les paramètres supplémentaires suivants sont disponibles pour les appareils Windows 10 Desktop et Mobile.

Nom du paramètre  |Plus d'informations  
---------|---------
**Règles de trafic réseau**|Sélectionnez les protocoles, les ports locaux/distants et les plages d’adresses à activer pour la connexion VPN. Si vous ne créez pas de règle de trafic réseau, tous les protocoles, les ports et les plages d’adresses sont activés. Une fois qu’une règle est créée, la connexion VPN utilise uniquement les protocoles, les ports et les plages d’adresses que vous spécifiez dans cette règle.
**Itinéraires**|Sélectionnez les itinéraires qui utiliseront la connexion VPN.
**Serveurs DNS**| Sélectionnez les serveurs DNS qu’utilisera la connexion VPN quand celle-ci sera établie.         
**Applications associées**|Fournissez une liste d’applications qui utiliseront automatiquement la connexion VPN. Le type d'application détermine l'identificateur de l'application. Pour une application universelle, indiquez le nom de famille du package. Pour une application de bureau, indiquez le chemin de l’application.          


> [!IMPORTANT]
> Nous vous recommandons de sécuriser toutes les listes d’applications que vous compilez pour les utiliser dans la configuration d’un VPN par application. Si un utilisateur non autorisé modifie votre liste et que vous l’importez dans la liste des applications du VPN par application, vous autorisez potentiellement un accès VPN à des applications qui ne doivent pas y avoir accès. Pour sécuriser les listes d’applications, vous avez la possibilité d’utiliser une liste de contrôle d’accès (liste ACL).

Voici un exemple d’utilisation des paramètres pour les limites réseau de l’entreprise. Si vous souhaitez activer le VPN uniquement pour les services Bureau à distance, créez une règle de trafic réseau qui autorise le trafic pour le protocole 27 sur le port externe 3996. Aucun autre trafic n’utilisera le VPN.

Vous pouvez définir des itinéraires dans les limites réseau de l’entreprise quand votre type de connexion VPN ne vous permet pas de définir la façon dont le trafic est traité dans une tunnelisation fractionnée. Dans ce cas, utilisez **Itinéraires** pour répertorier les itinéraires qui utiliseront le VPN.

Vous pouvez limiter l’utilisation du VPN pour les appareils Windows 10 à des applications spécifiques en créant un paramètre OMA-URI personnalisé.

La nouvelle stratégie apparaît sous le nœud **Stratégies de configuration** de l’espace de travail **Stratégie**.

### <a name="on-demand-vpn-for-ios-devices"></a>VPN à la demande pour les appareils iOS
Vous pouvez configurer un VPN à la demande pour les appareils iOS 8.0 et versions ultérieures.

> [!NOTE]
>  
> Par contre, vous ne pouvez pas utiliser un VPN par application et un VPN à la demande dans la même stratégie.

1. Dans la page de configuration de la stratégie, recherchez **Règles à la demande pour cette connexion VPN**. Les colonnes sont intitulées **Correspondance** (condition vérifiée par les règles) et **Action** (action déclenchée par la stratégie quand la condition est remplie).
2. Choisissez **Ajouter** pour créer une règle. Vous pouvez configurer deux types de correspondances dans la règle. Vous ne pouvez configurer qu’un de ces types par règle.
  - **SSID** - font référence aux réseaux sans fil.
  - **Domaines de recherche DNS** - Vous pouvez utiliser des noms de domaine complets, tels que *team. corp.contoso.com*, ou des domaines tels que *contoso.com*, ce qui revient à utiliser * *.contoso.com*.
3. Facultatif : fournissez une sonde de chaîne d’URL, qui est une URL que la règle utilise comme test. Si l’appareil sur lequel ce profil est installé peut accéder à cette URL sans redirection, la connexion VPN est établie et l’appareil se connecte à l’URL cible. L’utilisateur ne voit pas le site de la sonde de chaîne d’URL. Par exemple, une sonde de chaîne d’URL peut être l’adresse d’un serveur web d’audit qui vérifie la compatibilité de l’appareil avant la connexion du VPN. Autre exemple, l’URL teste la capacité du VPN à se connecter à un site avant de connecter l’appareil à l’URL cible via le VPN.
4. Choisissez une des actions suivantes :
  - **Se connecter**
  - **Évaluer la connexion**, qui a trois paramètres. a. **Action de domaine** : Choisissez **Se connecter si nécessaire** ou **Ne jamais se connecter** b. **Liste des domaines séparés par une virgule** : Ne configurez cette option que si vous choisissez **Se connecter si nécessaire** comme **Action de domaine** c. **Sonde de chaîne d’URL obligatoire** : URL HTTP ou HTTPS (recommandé) telle que *https://vpntestprobe.contoso.com*. La règle vérifie s’il existe une réponse en provenance de cette adresse. Si ce n’est pas le cas et que l’option **Action de domaine** est définie sur **Se connecter si nécessaire**, le VPN est déclenché.
      
     > [!TIP]
     >
     >Par exemple, vous pouvez utiliser cette action si une partie des sites de votre réseau d’entreprise nécessite une connexion de réseau d’entreprise directe ou VPN. Si vous répertoriez *corp.contoso.com* dans **Liste des domaines de recherche DNS séparés par une virgule**, vous pouvez choisir **Se connecter si nécessaire**, puis répertorier des sites spécifiques au sein de ce réseau qui peuvent nécessiter un VPN, tels que *sharepoint.corp.contoso.com*. La règle vérifie si *vpntestprobe.contoso.com* est accessible. Si ce n’est pas le cas, le VPN est déclenché pour le site sharepoint.
  - **Ignorer** : La connectivité VPN ne subit aucune modification. Si le VPN est connecté, laissez-le ainsi. S’il ne l’est pas, ne le connectez pas. Par exemple, vous avez peut-être une règle qui connecte le VPN pour tous vos sites web d’entreprise internes, mais vous souhaitez qu’un de ces sites internes ne soit accessible que quand l’appareil est effectivement connecté au réseau d’entreprise. Dans ce cas, vous devez créer une règle Ignorer pour ce site.
  - **Déconnecter** : Les appareils sont déconnectés du VPN quand les conditions sont remplies. Par exemple, vous pouvez répertorier vos réseaux sans fil d’entreprise dans le champ **SSID** et créer une règle qui déconnecte les appareils du VPN quand ils se connectent à l’un de ces réseaux.

Les règles propres à un domaine sont évaluées avant les règles relatives à tous les domaines.


## <a name="deploy-the-policy"></a>Déploiement de la stratégie

1.  Dans l’espace de travail **Stratégie**, sélectionnez la stratégie à déployer, puis choisissez **Gérer le déploiement**.

2.  Dans la boîte de dialogue **Gérer le déploiement** :

    -   Pour déployer la stratégie : sélectionnez un ou plusieurs groupes sur lesquels déployer la stratégie, puis choisissez **Ajouter** &gt; **OK**.

    -   Pour fermer la boîte de dialogue sans la déployer, choisissez **Annuler**.


Une fois le déploiement réussi, les utilisateurs voient le nom de la connexion VPN que vous avez spécifié dans la liste des connexions VPN sur leur appareil.

Un récapitulatif de l'état et des alertes identifient, dans la page **Vue d'ensemble** de l'espace de travail **Stratégie** , les problèmes liés à la stratégie qui nécessitent votre attention. En outre, le Tableau de bord contient un récapitulatif de l'état.
