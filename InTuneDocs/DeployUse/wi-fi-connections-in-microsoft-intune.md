---
# required metadata

title: Connexions Wi-Fi | Microsoft Intune
description:
keywords:
author: Nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 0b1b86ed-2e80-474d-8437-17dd4bc07b55

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Connexions Wi-Fi dans Microsoft Intune
Utilisez les profils Wi-Fi de Microsoft Intune pour déployer les paramètres de réseau sans fil des utilisateurs et des appareils de votre organisation. Ces paramètres simplifient les connexions des utilisateurs aux réseaux sans fil.

Par exemple, vous installez un nouveau réseau Wi-Fi nommé **Contoso Wi-Fi** et souhaitez configurer tous les appareils iOS pour se connecter à ce réseau. Voici le processus :

1.   Créez un profil Wi-Fi contenant les paramètres nécessaires à la connexion au réseau sans fil **Wi-Fi Contoso**.

2. Déployez le profil sur le groupe d'utilisateurs avec des appareils iOS.

3.   Les utilisateurs recherchent le nouveau réseau **Wi-Fi Contoso** dans la liste des réseaux sans fil et peuvent facilement s’y connecter.

Vous pouvez déployer les profils Wi-Fi sur les plateformes suivantes :

-   Android 4.0 et versions ultérieures

-   iOS 7.1 et versions ultérieures

-   Mac OS X 10.9 et versions ultérieures

Pour les appareils qui exécutent Windows 8.1 ou version ultérieure, vous pouvez importer un profil de configuration Wi-Fi précédemment exporté vers un fichier. Pour plus d'informations, consultez Importer un profil Wi-Fi plus loin dans cette rubrique.

## Comment créer un profil Wi-Fi

1.  Dans la [console d’administration Microsoft Intune](https://manage.microsoft.com), cliquez sur **Stratégie** &gt; **Ajouter une stratégie**.

2.  Sélectionnez l'un des types de stratégie suivants, puis cliquez sur **Créer une stratégie**:

    -   **Profil Wi-Fi (Android 4 et versions ultérieures)**

    -   **Profil Wi-Fi (iOS 7.1 et versions ultérieures)**

    -   **Profil VPN (Mac OS X 10.9 et versions ultérieures)**

    Il n'existe aucun paramètre recommandé pour ce type de stratégie. Vous devez créer une stratégie personnalisée.

3.  Fournissez un nom et une description pour le profil.

4. Spécifiez les valeurs **Connexions réseau** :

  |Paramètre|Plus d’informations| |-----------|--------------------|
|**Nom réseau**|Spécifiez un nom descriptif pour le réseau sans fil. Il s’agit du nom qui s’affiche sur l’appareil de l’utilisateur quand il choisit un réseau sans fil.| |**SSID (Service Set Identifier)**|Spécifiez le (SSID) du réseau sans fil auquel les appareils doivent se connecter. Le SSID respecte la casse et n’est pas visible aux utilisateurs.| |**Me connecter automatiquement lorsque ce réseau est à portée**|Sélectionnez cette option pour connecter automatiquement les appareils au réseau sans fil lorsqu’il est à portée.| |**Se connecter quand le réseau ne diffuse pas son nom (SSID)**|Sélectionnez cette option pour permettre aux appareils de se connecter au réseau lorsque celui-ci n’est pas visible dans la liste des réseaux (il est masqué et ne diffuse pas son nom).|

5. Configurez les **Paramètres de sécurité** de la plateforme sélectionnée. Les paramètres disponibles varient selon le type de sécurité que vous sélectionnez.

  #### Pour les appareils Android

  |Nom du paramètre|Plus d’informations|Contexte d’utilisation :| |----------------|--------------------|-------------|
|**Type de sécurité**|Sélectionnez le protocole de sécurité du réseau sans fil :<br /><br />-   **WPA-Entreprise/WPA2-Entreprise**<br />-   **Aucune authentification (ouvert)** si le réseau n’est pas sécurisé.|Toujours| |**Type EAP**|Choisissez le type de protocole EAP (Extensible Authentication Protocol) utilisé pour authentifier les connexions sans fil sécurisées :<br /><br />-   **EAP-TLS**<br />-   **PEAP**<br />-   **EAP-TTLS**|Vous avez sélectionné le type de sécurité **WPA-Enterprise/WPA2-Enterprise**.| |**Sélectionner les certificats racines pour la validation du serveur**|Cliquez sur **Sélectionner**, puis choisissez le profil de certificat racine approuvé utilisé pour authentifier la connexion. **Important :** Pour créer le profil de certificat racine de confiance, consultez [Secure resource access with certificate profiles](secure-resource-access-with-certificate-profiles.md) (Sécuriser l’accès aux ressources avec des profils de certificat).|N’importe quel **type EAP** est sélectionné.| |**Méthode d’authentification**|Sélectionnez la méthode d’authentification de la connexion :<br /><br />-   **Certificats** pour spécifier le certificat client<br />-   **Nom d’utilisateur et mot de passe** pour spécifier une autre méthode d’authentication| Le **type EAP** est **PEAP** ou **EAP-TTLS**.| |**Sélectionner une méthode non-EAP pour l’authentification (identité interne)**|Sélectionnez la façon dont vous allez authentifier la connexion :<br /><br />-   **aucune.**<br />-   **Mot de passe non chiffré (PAP)**<br />-   **Protocole CHAP (Challenge Handshake Authentication Protocol)**<br />-   **Microsoft CHAP (MS-CHAP)**<br />-   **Microsoft CHAP Version 2 (MS-CHAP v2)**<br /><br />Les options disponibles dépendent du type EAP sélectionné.|La **méthode d’authentification** est **Nom d’utilisateur et mot de passe**.| |**Autoriser la confidentialité de l’identité (identité externe)**|Spécifiez le texte envoyé en réponse à une demande d’identité EAP. Ce texte peut être n'importe quelle valeur. Lors de l’authentification, cette identité anonyme est envoyée en premier, suivie de l’identification réelle adressée dans un tunnel sécurisé.|Le **type EAP** est **PEAP** ou **EAP-TTLS**.| |**Sélectionner un certificat client pour l’authentification client (certificat d’identité)**|Cliquez sur **Sélectionner**, puis choisissez le profil de certificat SCEP utilisé pour authentifier la connexion. **Important :** pour créer un profil de certificat SCEP, consultez [Sécuriser l’accès aux ressources avec des profils de certificat](secure-resource-access-with-certificate-profiles.md).|Le type de sécurité est **WPA-Enterprise/WPA2-Enterprise**, et n’importe quel **type EAP** est sélectionné.|

  #### Pour les appareils iOS et Mac OS X

  |Nom du paramètre|Plus d’informations|Contexte d’utilisation :| |----------------|--------------------|-------------|
|**Type de sécurité**|Sélectionnez le protocole de sécurité du réseau sans fil :<br /><br />-   **WPA-Personnel/WPA2-Personnel**<br />-   **WPA-Entreprise/WPA2-Entreprise**<br />-   **WEP**<br />-   **Aucune authentification (ouvert)** si le réseau n’est pas sécurisé.|Toujours| |**Type EAP**|Choisissez le type de protocole EAP (Extensible Authentication Protocol) utilisé pour authentifier les connexions sans fil sécurisées :<br /><br />-   **EAP-TLS**<br />-   **PEAP**<br />-   **EAP-TLS**<br />-   **EAP-AST**<br />-   **LEAP**<br />-   **EAP-SIM**|Vous avez sélectionné un type de sécurité **WPA-Enterprise/WPA2-Enterprise**.| |**Noms de certificat de serveur approuvé**|Sélectionnez le profil de certificat racine approuvé utilisé pour authentifier la connexion. **Important :** pour créer le profil de certificat racine de confiance, consultez [Secure resource access with certificate profiles](secure-resource-access-with-certificate-profiles.md) (Sécuriser l’accès aux ressources avec des profils de certificat).|Vous avez sélectionné un type EAP **EAP-TLS**, **PEAP**, **EAP-TTLS** ou **EAP-FAST**.| |**Utiliser le PAC (Protected Access Credential (informations d’identification d’accès protégé))**|Sélectionnez cette option si vous voulez utiliser les informations d’identification d’accès protégé pour établir un tunnel authentifié entre le client et le serveur d’authentification. Un fichier PAC existant est utilisé s’il est présent.|Le **type EAP** est **EAP-FAST**.| |**Configurer les informations d’identification de l’accès protégé**|Configure le fichier PAC sur vos appareils.<br /><br />Quand cette option est utilisée, vous pouvez également sélectionner **Configurer anonymement le fichier PAC** pour vous assurer que le fichier PAC est configuré sans authentifier le serveur.|L’option **Utiliser le PAC (Protected Access Credential (informations d’identification d’accès protégé))** est sélectionnée.| |**Méthode d’authentification**|Sélectionnez la méthode d’authentification utilisée pour la connexion :<br /><br /><ul><li>**Certificats** pour spécifier le certificat client</li><li>**Nom d’utilisateur et mot de passe** pour spécifier une des méthodes non-EAP suivantes pour l’authentification (également appelée Identité interne) :<br /><br /><ul><li>**aucune.**</li><li>**Mot de passe non chiffré (PAP)**</li><li>**Protocole CHAP (Challenge Handshake Authentication Protocol)**</li><li>**Microsoft CHAP (MS-CHAP)**</li><li>**Microsoft CHAP Version 2 (MS-CHAP v2)**</li><li>**EAP-TLS**</li></ul></li></ul>|Le **type EAP** est **PEAP** ou **EAP-TTLS**.| |**Sélectionner un certificat client pour l’authentification client (certificat d’identité)**|Sélectionnez le profil de certificat SCEP utilisé pour authentifier la connexion. **Important :** Pour créer un profil de certificat SCEP, consultez [Secure resource access with certificate profiles](secure-resource-access-with-certificate-profiles.md) (Sécuriser l’accès aux ressources avec des profils de certificat).|Quand le type de sécurité est **WPA-Enterprise/WPA2-Enterprise** et que le **type EAP** est **EAP-TLS**, **PEAP** ou **EAP-TTLS**.| |**Autoriser la confidentialité de l’identité (identité externe)**|Spécifiez le texte envoyé en réponse à une demande d’identité EAP. Ce texte peut être n'importe quelle valeur.<br /><br />Lors de l’authentification, cette identité anonyme est envoyée en premier, suivie de l’identification réelle adressée dans un tunnel sécurisé.|Quand le **type EAP** est défini sur **PEAP**, **EAP-TTLS** ou **EAP-FAST**.|

6. (iOS et MAC OS X uniquement) Configurer les **paramètres du proxy**

    |Nom du paramètre|Plus d'informations|Contexte d'utilisation :|
    |----------------|-------------------|-------------|
    |**Paramètres proxy pour cette connexion Wi-Fi**|Choisissez le type de paramètres du proxy :<br /><br />-   **Aucun** (par défaut)<br />-   **Manuel** : spécifiez manuellement l’URL et le numéro de port du serveur proxy.<br />-   **Automatique** : utilisez un fichier de configuration pour configurer le serveur proxy.|Toujours|
    |**Adresse du serveur proxy** et **Numéro du Port**|Spécifiez l'URL et le numéro de port du serveur proxy.|**Paramètres proxy pour cette connexion Wi-Fi** est défini sur **Manuel**|
    |**URL du serveur proxy**|Spécifiez l'URL du fichier contenant les paramètres du serveur proxy.|**Paramètres proxy pour cette connexion Wi-Fi** est défini sur **Automatique**|

7.  Enregistrer le profil Wi-Fi

La nouvelle stratégie s'affiche sous le nœud **Stratégies de configuration** de l'espace de travail **Stratégie** . Pour plus d'informations sur le déploiement du profil, voir **Étapes suivantes**.

## Exporter ou importer un profil de configuration Wi-Fi (Windows 8.1 et versions ultérieures uniquement)

### Exporter un profil Wi-Fi
Dans Windows, vous pouvez recourir à l’utilitaire **netsh wlan** pour exporter un profil Wi-Fi existant dans un fichier XML lisible par Intune. Sur un ordinateur Windows où le profil Wi-Fi requis est déjà installé, utilisez la procédure suivante.

1.  Créez un dossier local pour les profils Wi-Fi exportés, comme c:\WiFi

2.  Ouvrez une invite de commandes en tant qu’administrateur.

3.  Exécutez la commande `netsh wlan show profiles` et notez le nom du profil que vous voulez exporter.  Dans cet exemple, le nom du profil est *WiFiName*.

4.  Exécutez la commande suivante : `netsh wlan export profile name="ProfileName" folder=c:\Wifi`. Celle-ci crée un fichier de profil Wi-Fi nommé « Wi-Fi-WiFiName.xml » dans le dossier de destination.

## Importer un profil Wi-Fi
Utilisez l’option **Stratégie d’importation Wi-Fi Windows** pour importer un ensemble de paramètres Wi-Fi que vous pouvez ensuite déployer sur les groupes d’utilisateurs ou d’appareils requis. La procédure d’exportation d’un profil Wi-Fi est décrite dans

1.  Dans la [console d’administration Microsoft Intune](https://manage.microsoft.com), cliquez sur **Stratégie** &gt; **Ajouter une stratégie**.

2.  Configurez une stratégie du type **Windows** &gt; **Stratégie d’importation Wi-Fi Windows**.

    Vous pouvez uniquement créer et déployer une stratégie d'importation Wi-Fi Windows personnalisée. Les paramètres recommandés ne sont pas disponibles.

3.  Spécifiez les valeurs générales suivantes pour la stratégie d'importation Wi-Fi Windows :

    |Nom du paramètre|Plus d'informations|
    |----------------|--------------------|
    |**Nom**|Entrez un nom unique pour le profil Wi-Fi afin de l'identifier facilement dans la console Intune.|
    |**Description**|Fournissez une description du profil Wi-Fi et d'autres informations pertinentes pour mieux le localiser.|

4.  Spécifiez les valeurs suivantes sous l’en-tête **Profil Wi-Fi personnalisé** :

    |Nom du paramètre|Plus d'informations|
    |----------------|--------------------|
    |**Fichier de configuration de profil**|Cliquez sur **Importer** pour sélectionner le fichier XML contenant les paramètres de profil Wi-Fi que vous voulez importer dans Intune.|
    |**Nom du profil de configuration personnalisé (montré aux utilisateurs)**|Affiche le nom du profil de configuration Wi-Fi tel qu'il apparaîtra aux utilisateurs sur leurs appareils.|
    |**Détails du profil de configuration**|Affiche le code XML du profil de configuration que vous avez sélectionné.|

5.  Quand vous avez terminé, cliquez sur **Enregistrer la stratégie**.

6.  La nouvelle stratégie s'affiche sous le nœud **Stratégies de configuration** de l'espace de travail **Stratégie** .

## Déploiement de la stratégie

1.  Dans l’espace de travail **Stratégie** , sélectionnez la stratégie à déployer, puis cliquez sur **Gérer le déploiement**.

2.  Dans la boîte de dialogue **Gérer le déploiement** :

    -   **Pour déployer la stratégie** : sélectionnez un ou plusieurs groupes sur lesquels déployer la stratégie, puis cliquez sur **Ajouter** &gt; **OK**.

    -   **Pour fermer la boîte de dialogue sans la déployer**, cliquez sur **Annuler**.


Un récapitulatif de l'état et des alertes identifient, dans la page **Vue d'ensemble** de l'espace de travail **Stratégie** , les problèmes liés à la stratégie qui nécessitent votre attention. En outre, le Tableau de bord contient un récapitulatif de l'état.

### Voir aussi
Découvrez comment créer un profil Wi-Fi avec une clé prépartagée dans [Profil Wi-Fi à clé prépartagée](pre-shared-key-wi-fi-profile.md)


<!--HONumber=Jun16_HO1-->


