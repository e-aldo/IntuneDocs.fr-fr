---
# required metadata

title: Connexions VPN | Microsoft Intune
description:
keywords:
author: Nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: abc57093-7351-408f-9f41-a30877f96f73

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Connexions VPN dans Microsoft Intune
 Les réseaux privés virtuels (VPN, Virtual Private Networks) vous permettent de donner à vos utilisateurs un accès distant sécurisé à votre réseau d'entreprise. Les utilisateurs distants peuvent travailler comme si leur appareil était physiquement connecté au réseau. Les appareils utilisent un profil de connexion VPN pour établir une connexion avec le serveur VPN. Utilisez les **profils VPN** dans Microsoft Intune pour déployer des paramètres VPN pour les utilisateurs et appareils de votre organisation. En déployant ces paramètres, vous réduisez l'effort que doit fournir l'utilisateur final pour se connecter aux ressources du réseau d'entreprise.

Par exemple, vous souhaitez approvisionner tous les appareils iOS en fonction des paramètres nécessaires pour se connecter à un partage de fichiers sur le réseau d'entreprise. Vous créez un profil VPN contenant les paramètres nécessaires pour se connecter au réseau d'entreprise, puis vous déployez ce profil pour tous les utilisateurs ayant des appareils iOS. Les utilisateurs voient la connexion VPN dans la liste des réseaux disponibles et peuvent se connecter avec un minimum d'effort.

Vous pouvez configurer les types d'appareil suivants avec des profils VPN :

* Appareils qui exécutent Android 4 et versions ultérieures
* Appareils qui exécutent iOS 7.1 et versions ultérieures
* Appareils qui exécutent Mac OS X 10.9 et versions ultérieures
* Appareils inscrits qui exécutent Windows 8.1 et versions ultérieures
* appareils qui exécutent Windows Phone 8.1 et versions ultérieures.
* Appareils qui exécutent Windows 10 Desktop et Mobile.

Les options de configuration de profil VPN varient selon le type d'appareil sélectionné.

## Types de connexions VPN

Intune prend en charge la création de profils VPN qui utilisent les types de connexions suivants :




Type de connexion |iOS et Mac OS X  |Android  |Windows 8.1|Windows RT|Windows RT 8.1|Windows Phone 8.1  |Windows 10 Desktop et Mobile |
---------|---------|---------|---------|---------|---------
Cisco AnyConnect |Oui |Oui   |Non    |     Non    |Non  |Non    | Oui, (OMA-URI, mobile uniquement)|     
Pulse Secure |Oui  |Oui |Oui   |Non  |Oui  |Oui| Oui|        
Client F5 Edge |Oui |Oui |Oui |Non  |Oui  |   Oui |  Oui|   
Dell SonicWALL Mobile Connect |Oui |Oui |Oui |Non  |Oui |Oui |Oui|         
CheckPoint Mobile VPN |Oui |Oui |Oui |Oui |Oui|Oui|Oui|




> [!IMPORTANT] Avant de pouvoir utiliser les profils VPN déployés sur un appareil, vous devez installer l'application VPN applicable pour le profil. Vous pouvez utiliser les informations fournies dans la rubrique [Déployer des applications dans Microsoft Intune](deploy-apps-in-microsoft-intune.md) pour vous aider à déployer l’application applicable à l'aide d’Intune.  

 Apprenez à créer des profils VPN personnalisés à l’aide des paramètres de l’URI dans [Configurations personnalisées pour les profils VPN](custom-configurations-for-vpn-profiles.md).     

## Mode de sécurisation des profils VPN

Les profils VPN peuvent utiliser différents types de connexion et protocole de fabricants différents. Ces connexions sont généralement sécurisées à l'aide de l'une des deux méthodes suivantes :

### Certificats

Quand vous créez le profil VPN, vous choisissez un profil de certificat SCEP ou .PFX que vous avez créé précédemment dans Intune.

Il s'agit du certificat d'identité, qui est utilisé pour l'authentification par rapport à un profil de certificat approuvé (ou un certificat racine) que vous avez créée pour établir le fait que l'utilisateur est autorisé à se connecter. Le certificat approuvé est déployé sur l'ordinateur qui authentifie la connexion VPN, en règle générale le serveur VPN.

Pour plus d’informations sur la façon de créer et d’utiliser des profils de certificat dans Intune, consultez [Sécuriser l’accès aux ressources avec des profils de certificat](secure-resource-access-with-certificate-profiles.md).

### Nom d'utilisateur et mot de passe

L'utilisateur s'authentifie auprès du serveur VPN en fournissant son nom d'utilisateur et son mot de passe.

## Créer un profil VPN

1. Dans la [console d’administration Microsoft Intune](https://manage.microsoft.com), cliquez sur **Stratégie > Ajouter une stratégie**.
2. Sélectionnez un modèle pour la nouvelle stratégie en développant le type d’appareil approprié, puis choisissez le profil VPN pour cet appareil :
    * **Profil VPN (Android 4 et versions ultérieures)**
    * **Profil VPN (iOS 7.1 et versions ultérieures)**
    * **Profil VPN (Mac OS X 10.9 et versions ultérieures)**
    * **Profil VPN (Windows 8.1 et versions ultérieures)**
    * **Profil VPN (Windows Phone 8.1 et versions ultérieures)**
    * **Profil VPN (Windows 10 Desktop et Mobile, et versions ultérieures)**

    Vous pouvez uniquement créer et déployer une stratégie de profil VPN personnalisée. Les paramètres recommandés ne sont pas disponibles.

3. Utilisez le tableau suivant pour vous aider à configurer les paramètres de profil VPN :

Nom du paramètre  |Plus d'informations  
---------|---------
**Nom**     |Entrez un nom unique pour le profil VPN pour vous aider à l’identifier dans la console Intune.         
**Description**     |Fournissez une description qui donne un aperçu du profil VPN et d'autres informations pertinentes pour mieux le localiser.         
**Nom de la connexion VPN (visible par les utilisateurs)**     |Spécifiez un nom pour le profil VPN. Il s'agit du nom que voient les utilisateurs dans la liste des connexions VPN disponibles sur leurs appareils.         
**Type de connexion**     |  Sélectionnez l’un des types de connexions suivants à utiliser dans le profil VPN : **Cisco AnyConnect** (non disponible pour Windows 8.1 ou Windows Phone 8.1), **Pulse Secure**, **Client F5 Edge**, **Dell SonicWALL Mobile Connect**, **CheckPoint Mobile VPN**
**Description du serveur VPN**     | Spécifiez une description pour le serveur VPN auquel les appareils se connecteront. **Exemple :** serveur VPN Contoso. Quand le type de connexion est **Client F5 Edge**, utilisez le champ **Liste de serveurs** pour spécifier une liste de descriptions et d'adresses IP de serveur.
**Adresse IP du serveur ou nom de domaine complet**    |Fournissez l'adresse IP ou le nom de domaine complet du serveur VPN auquel les appareils se connectent. **Exemples :** 192.168.1.1, vpn.contoso.com.  Quand le type de connexion est **Client F5 Edge**, utilisez le champ **Liste de serveurs** pour spécifier une liste de descriptions et d'adresses IP de serveur.         |         
**Liste de serveurs**     |Cliquez sur **Ajouter** pour ajouter un nouveau serveur VPN à utiliser pour la connexion VPN. Vous pouvez aussi spécifier le serveur par défaut pour la connexion. Cette option est visible uniquement quand le type de connexion est **Client F5 Edge**.         
**Envoyer tout le trafic réseau via la connexion VPN**     |Si vous sélectionnez cette option, tout le trafic réseau est envoyé via la connexion VPN. Si vous ne sélectionnez pas cette option, le client négocie dynamiquement les itinéraires pour le tunneling fractionné durant la connexion au serveur VPN tiers. Seules les connexions au réseau d'entreprise sont envoyées via un tunnel VPN. La tunnelisation VPN n'est pas utilisée quand vous vous connectez à des ressources sur Internet.
**Méthodes d'authentification**| Sélectionnez la méthode d'authentification utilisée par la connexion VPN : **Certificats** ou **Nom d’utilisateur et mot de passe**. (Nom d'utilisateur et mot de passe n'est pas disponible quand le type de connexion est Cisco AnyConnect.) L'option **Méthode d'authentification** n'est pas disponible pour Windows 8.1.
**Conserver les informations d'identification de l'utilisateur à chaque ouverture de session**|Sélectionnez cette option pour vous assurer que les informations d'identification sont mémorisées, pour que l'utilisateur n'ait pas à les entrer chaque fois qu'une connexion est établie.
**Sélectionner un certificat client pour l'authentification client (certificat d'identité)**|Sélectionnez le certificat SCEP client que vous avez créé précédemment et qui sera utilisé pour authentifier la connexion VPN. Pour plus d’informations sur la façon de créer des profils de certificat dans Intune, consultez [Sécuriser l’accès aux ressources avec des profils de certificat](secure-resource-access-with-certificate-profiles.md). Cette option est visible uniquement quand la méthode d’authentification est **Certificats**.
**Rôle**| Spécifiez le nom du rôle d'utilisateur qui a accès à cette connexion. Un rôle d'utilisateur définit des paramètres personnels, des options et active ou désactive certaines fonctionnalités d'accès. Cette option est visible uniquement quand le type de connexion est **Pulse Secure**.
**Domaine**|Spécifiez le nom du domaine d'authentification que vous souhaitez utiliser. Un domaine d'authentification est un regroupement de ressources d'authentification utilisé par le type de connexion Pulse Secure. Cette option est visible uniquement quand le type de connexion est **Pulse Secure**.
**Groupe de connexion ou domaine**|Spécifiez le nom du groupe de connexion ou domaine auquel vous souhaitez vous connecter. Cette option est visible uniquement quand le type de connexion est **Dell SonicWALL Mobile Connect**.
**Empreinte digitale**|Spécifiez une chaîne, par exemple « Code d'empreinte digitale Contoso », qui sera utilisée pour vérifier que le serveur VPN est digne de confiance. Une empreinte digitale peut être envoyée au client pour qu'il sache qu'il peut approuver n'importe quel serveur présentant cette même empreinte lors de la connexion. Si l'appareil n'a pas encore l'empreinte digitale, il invite l'utilisateur à approuver le serveur VPN auquel il se connecte en affichant l'empreinte digitale (l'utilisateur vérifie l'empreinte manuellement et clique sur **Approuver** pour se connecter). Cette option est visible uniquement quand le type de connexion est **CheckPoint Mobile VPN**.
**Par VPN d'application**|Sélectionnez cette option si vous souhaitez associer cette connexion VPN à une application iOS ou Mac OS X pour que la connexion s’ouvre quand l’application est exécutée. Vous pouvez associer le profil VPN à une application lors du déploiement du logiciel. Pour plus d’informations, consultez [Déployer des applications dans Microsoft Intune](deploy-apps-in-microsoft-intune.md)
**Détecter automatiquement les paramètres du proxy** (iOS, Mac OS X, Windows 8.1 et Windows Phone 8.1 uniquement)|Si votre serveur VPN nécessite un serveur proxy pour la connexion, spécifiez si vous souhaitez que les appareils détectent automatiquement les paramètres de connexion. Pour plus d'informations, consultez la documentation de Windows Server.
**Utiliser un script de configuration automatique** (iOS, Mac OS X, Windows 8.1 et Windows Phone 8.1 uniquement)|Si votre serveur VPN nécessite un serveur proxy pour la connexion, spécifiez si vous souhaitez utiliser un script de configuration automatique pour définir les paramètres, puis spécifiez une URL vers le fichier contenant les paramètres. Pour plus d'informations, consultez la documentation de Windows Server.
**Utiliser un serveur proxy** (iOS, Mac OS X, Windows 8.1 et Windows Phone 8.1 uniquement)|Si votre serveur VPN nécessite un serveur proxy pour la connexion, sélectionnez cette option, puis spécifiez l'adresse et le numéro de port du serveur proxy. Pour plus d'informations, consultez la documentation de Windows Server.
**Ignorer les paramètres du proxy pour les adresses locales** (iOS, Mac OS X, Windows 8.1 et Windows Phone 8.1 uniquement)|Si votre serveur VPN nécessite un serveur proxy pour la connexion, sélectionnez cette option si vous ne souhaitez pas utiliser le serveur proxy pour les adresses locales que vous spécifiez. Pour plus d'informations, consultez la documentation de Windows Server.
**XML personnalisé** (Windows 8.1 et versions ultérieures, et Windows Phone 8.1 et versions ultérieures)|Vous permet de spécifier des commandes XML personnalisées qui configurent la connexion VPN. Exemples. Pour **Pulse Secure** : &lt;pulse-schema&gt;&lt;isSingleSignOnCredential&gt;true&lt;/isSingleSignOnCredential&gt;&lt;/pulse-schema&gt;. Pour **CheckPoint Mobile VPN** : &lt;CheckPointVPN port="443" name="CheckPointSelfhost" sso="true"  debug="3" /&gt;. Pour **Dell SonicWALL Mobile Connect** : &lt;MobileConnect&gt;&lt;Compression&gt;false&lt;/Compression&gt;&lt;debugLogging&gt;True&lt;/debugLogging&gt;&lt;packetCapture&gt;False&lt;/packetCapture&gt;&lt;/MobileConnect&gt;. Pour **F5 Edge Client** : &lt;f5-vpn-conf&gt;&lt;single-sign-on-credential /&gt;&lt;/f5-vpn-conf&gt;. Pour plus d'informations sur la façon d'écrire des commandes XML personnalisées, reportez-vous à la documentation du VPN de chaque fabricant.
**Liste de recherche de suffixes DNS** (Windows Phone 8.1 uniquement)|Spécifiez un suffixe DNS sur chaque ligne. Chaque suffixe DNS que vous spécifiez sera recherché lors de la connexion à un site web à l'aide d'un nom court. Par exemple, spécifiez les suffixes DNS **domain1.contoso.com** et **domain2.contoso.com**, accédez à l'URL **http://mywebsite**, et les URL **http://mywebsite.domain1.contoso.com** et **http://mywebsite.domain2.contoso.com** seront recherchées.
**Ignorer VPN lors d'une connexion à un réseau Wi-Fi de l'entreprise** (Windows Phone 8.1 uniquement)|Indique que la connexion VPN n'est pas utilisée quand l'appareil est connecté au réseau Wi-Fi d'entreprise.
**Ignorer le VPN en cas de connexion à un réseau Wi-Fi domestique** (Windows Phone 8.1 uniquement)|Indique que la connexion VPN n'est pas utilisée quand l'appareil est connecté à un réseau Wi-Fi domestique.

Les paramètres supplémentaires suivants sont disponibles pour les appareils Windows 10 Desktop et Mobile

Nom du paramètre  |Plus d'informations  
---------|---------
**Règles de trafic réseau**| Définissez les protocoles, les ports locaux et distants et les plages d’adresses à activer pour la connexion VPN. Si vous ne créez pas de règle de trafic réseau, tous les protocoles, les ports et les plages d’adresses sont activés. Dès lors que vous créez une règle, seuls les protocoles, les ports et les plages d’adresses que vous spécifiez dans cette règle ou dans des règles supplémentaires sont utilisés par la connexion VPN.
**Itinéraires**|Itinéraires qui utilisent la connexion VPN.
**Serveurs DNS**| Serveurs DNS qui sont utilisés par la connexion VPN une fois la connexion établie.         
**Applications associées**     | Vous pouvez fournir une liste d'applications qui utiliseront automatiquement la connexion VPN. Le type d'application détermine l'identificateur de l'application. Pour les applications universelles, vous devez fournir le nom de la famille de packages. Pour les applications de bureau, vous devez fournir le chemin de l'application.          


Voici un exemple d’utilisation des paramètres de limites réseau de l’entreprise. Si vous souhaitez activer le VPN uniquement pour les services Bureau à distance, vous devez créer une règle de trafic réseau qui autorise le trafic pour le numéro de protocole 27 sur le port externe 3996. Aucun autre trafic n’utilisera le VPN.

Vous pouvez définir des itinéraires dans les limites réseau de l’entreprise quand votre type de connexion VPN ne vous permet pas de définir la façon dont le trafic est traité dans une tunnelisation fractionnée. Dans ce cas, utilisez **Itinéraires** pour répertorier les itinéraires qui utiliseront le VPN.

Vous pouvez limiter l’utilisation du VPN des appareils Windows 10 à des applications spécifiques en créant un paramètre OMA-URI personnalisé.

La nouvelle stratégie s'affiche sous le nœud **Stratégies de configuration** de l'espace de travail **Stratégie** .

## Déploiement de la stratégie

1.  Dans l’espace de travail **Stratégie**, sélectionnez la stratégie à déployer, puis cliquez sur **Gérer le déploiement**.

2.  Dans la boîte de dialogue **Gérer le déploiement** :

    -   **Pour déployer la stratégie** : sélectionnez un ou plusieurs groupes sur lesquels déployer la stratégie, puis cliquez sur **Ajouter** &gt; **OK**.

    -   **Pour fermer la boîte de dialogue sans la déployer**, cliquez sur **Annuler**.


Une fois le déploiement réussi, les utilisateurs verront le nom de la connexion VPN que vous avez spécifié dans la liste des connexions VPN sur leur appareil.

Un récapitulatif de l'état et des alertes identifient, dans la page **Vue d'ensemble** de l'espace de travail **Stratégie** , les problèmes liés à la stratégie qui nécessitent votre attention. En outre, le Tableau de bord contient un récapitulatif de l'état.



<!--HONumber=May16_HO1-->


