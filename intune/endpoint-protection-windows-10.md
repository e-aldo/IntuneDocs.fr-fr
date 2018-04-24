---
title: Ajouter Endpoint Protection sur Windows 10 dans Microsoft Intune - Azure | Microsoft Docs
description: Sur les appareils Windows 10, utilisez ou configurez les paramètres Endpoint Protection pour activer les fonctionnalités de Windows Defender, notamment Application Guard, Pare-feu, SmartScreen, le chiffrement et BitLocker, Exploit Guard, Contrôle d’application, Centre de sécurité, ainsi que la sécurité sur les appareils locaux dans Microsoft Intune.
keywords: ''
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 03/28/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 3af7c91b-8292-4c7e-8d25-8834fcf3517a
ms.reviewer: ilwu
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: afe1e737bb5214af76395db91b8aea72cb5d42a0
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2018
---
# <a name="endpoint-protection-settings-for-windows-10-and-later-in-intune"></a>Paramètres Endpoint Protection pour Windows 10 (et versions ultérieures) dans Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Le profil Endpoint Protection vous permet de contrôler les fonctionnalités de sécurité sur les appareils Windows 10, telles que BitLocker et Windows Defender.

Utilisez les informations de cet article pour découvrir comment créer des profils Endpoint Protection.

> [!Note]
> Ces paramètres ne sont pas pris en charge dans les éditions Famille et Professionnel de Windows 10.

## <a name="windows-defender-application-guard"></a>Windows Defender Application Guard

Application Guard est uniquement disponible pour les appareils Windows 10 (64 bits). L’utilisation de ce profil permet d’installer un composant Win32 pour activer Application Guard.

- **Application Guard** : ouvrez des sites non approuvés dans un conteneur de navigation virtualisé Hyper-V.
- **Comportement du Presse-papiers** : choisissez les actions de copier-coller autorisées entre le PC local et le navigateur virtuel Application Guard.
- **Contenu externe sur les sites de l’entreprise** : bloquez le chargement du contenu des sites web non approuvés.
- **Imprimer à partir du navigateur virtuel** : autorisez l’impression en PDF et en XPS ainsi que les imprimantes locales et/ou réseau à imprimer du contenu à partir du navigateur virtuel.
- **Collecter les journaux** : collectez les journaux des événements qui se produisent dans une session de navigation Application Guard.
- **Conserver les données du navigateur générées par l’utilisateur** : enregistrez les données utilisateur (par exemple les mots de passe, les favoris et les cookies) qui sont créées au cours d’une session de navigation virtuelle Application Guard.
- **Accélération graphique** : accélérez le chargement des graphiques des sites web quand vous travaillez dans la session de navigation virtuelle Application Guard. Les sites web se chargent plus vite si vous activez l’accès à une unité de traitement graphique virtuelle.
- **Télécharger les fichiers sur le système de fichiers hôte** : autorisez les utilisateurs à télécharger des fichiers à partir du navigateur virtualisé sur le système d’exploitation hôte.

## <a name="windows-defender-firewall"></a>Pare-feu Windows Defender

### <a name="global-settings"></a>Paramètres globaux

Ces paramètres s’appliquent à tous les types de réseaux.

- **Protocole FTP** : bloquez le protocole FTP avec état.
- **Durée d’inactivité des associations de sécurité avant suppression** : les associations de sécurité sont supprimées si aucun trafic réseau n’est visible pendant *n* secondes.
- **Codage des clés prépartagées** : codez les clés prépartagées avec UTF-8.
- **Exemptions IPsec** : configurez un trafic spécifique pour qu’il soit exempté d’IPsec, notamment **Codes type ICMP IPv6 de découverte de voisin**, **ICMP**, **Codes type ICMP IPv6 de découverte de routeur** et **Trafic DHCP IPv4 et IPv6**.
- **Vérification de la liste de révocation de certificats** : définissez une valeur pour le mode d’application de la vérification de la liste de révocation de certificats, notamment **Désactiver la vérification de la liste de révocation de certificats**, **Échec de vérification de la liste de révocation de certificats sur le certificat révoqué uniquement** et **Échec de vérification de la liste de révocation de certificats pour toute erreur rencontrée**.
- **Associer le jeu d’authentification de façon opportuniste par module de génération de clés** : définissez des modules de génération de clés pour ignorer l’intégralité du jeu d’authentification si les suites d’authentification ne sont pas toutes prises en charge dans ce jeu.
- **Mise en file d’attente des paquets** : spécifiez comment la mise à l’échelle des logiciels côté réception est activée pour la réception chiffrée et efface le texte pour le scénario de passerelle du tunnel IPsec. Ce paramètre garantit la préservation de l’ordre des paquets.

### <a name="network-settings"></a>Paramètres du réseau

Ces paramètres s’appliquent à des types de réseaux spécifiques, notamment **Réseau (espace de travail) avec domaine**, **Réseau privé (détectable)** et **Réseau public (non détectable)**.

#### <a name="general-settings"></a>Paramètres généraux :

- **Pare-feu Windows Defender** : activez ce paramètre pour bloquer le trafic réseau.
- **Mode furtif** : empêchez le Pare-feu de fonctionner en mode furtif. Le blocage du mode furtif vous permet de bloquer également **Exemption de paquets sécurisés IPsec**.
- **Protégé** : l’activation de ce paramètre et du paramètre de pare-feu bloque tout le trafic entrant.
- **Réponses en monodiffusion au trafic en multidiffusion** : bloquez les réponses en monodiffusion au trafic en multidiffusion. En règle générale, vous ne souhaitez pas recevoir des réponses en monodiffusion à des messages de multidiffusion ou de diffusion, car ces réponses peuvent indiquer une attaque par déni de service ou un attaquant qui tente de sonder un ordinateur actif connu.
- **Notifications entrantes** : empêchez l’affichage des notifications pour les utilisateurs lors du blocage d’une application pour écouter sur un port.
- **Action par défaut pour les connexions entrantes** : configurez l’action par défaut que le pare-feu effectue sur les connexions entrantes.

#### <a name="rule-merging"></a>Fusion des règles

- **Règles de Pare-feu Windows Defender d’application autorisées du magasin local** : appliquez des règles de pare-feu autorisées dans le magasin local à reconnaître et à appliquer.
- **Règles de Pare-feu Windows Defender de port globales du magasin local** : appliquez des règles de pare-feu de port globales dans le magasin local à reconnaître et à appliquer.
- **Règles de Pare-feu Windows Defender du magasin local** : appliquez des règles de pare-feu globales dans le magasin local à reconnaître et à appliquer.
- **Règles IPsec du magasin local** : appliquez les règles de sécurité de connexion du magasin local, quelles que soient les versions des règles de sécurité de schéma ou de connexion.

## <a name="windows-defender-smartscreen-settings"></a>Paramètres Windows Defender SmartScreen

- **SmartScreen pour les applications et fichiers** : activez Windows SmartScreen pour l’exécution de fichiers et d’applications.
- **Exécution des fichiers non vérifiée** : empêche l’utilisateur final d’exécuter des fichiers qui n’ont pas été vérifiés par Windows SmartScreen.

## <a name="windows-encryption"></a>Chiffrement Windows

### <a name="windows-settings"></a>Paramètres Windows

Ces paramètres s’appliquent à toutes les versions de Windows 10.

- **Chiffrer les appareils** : si ce paramètre est activé, les utilisateurs sont invités à activer le chiffrement de l’appareil. Ils sont aussi invités à confirmer que le chiffrement d’un autre fournisseur n’a pas été activé. Si le chiffrement Windows est activé alors qu’une autre méthode de chiffrement est active, l’appareil peut devenir instable.
- **Chiffrer la carte de stockage** : activez ce paramètre pour chiffrer toutes les cartes de stockage amovibles utilisées par l’appareil.


### <a name="bitlocker-base-settings"></a>Paramètres de base BitLocker

Les paramètres de base correspondent aux paramètres BitLocker universels pour tous les types de lecteurs de données. Les paramètres de stratégie de groupe BitLocker permettent de gérer les options de configuration ou les tâches de chiffrement de lecteur modifiables par l’utilisateur final pour tous les types de lecteurs de données.

- **Avertissement pour tout autre chiffrement de disque** : désactivez l’invite d’avertissement pour tout autre chiffrement de disque sur les ordinateurs des utilisateurs finaux.
- **Configurer les méthodes de chiffrement** : activez ce paramètre pour configurer des algorithmes de chiffrement pour le système d’exploitation, les données et les lecteurs amovibles.
  - **Chiffrement pour les lecteurs du système d’exploitation** : choisissez la méthode de chiffrement pour les lecteurs de système d’exploitation. Nous vous recommandons d’utiliser l’algorithme AES-XTS.
  - **Chiffrement pour les lecteurs de données fixes** : choisissez la méthode de chiffrement pour les lecteurs de données fixes (intégrés). Nous vous recommandons d’utiliser l’algorithme AES-XTS.
  - **Chiffrement pour les lecteurs de données amovibles** : choisissez la méthode de chiffrement pour les lecteurs de données amovibles. Si le lecteur amovible est utilisé avec des appareils qui n’exécutent pas Windows 10, nous vous recommandons d’utiliser l’algorithme AES-CBC.

### <a name="bitlocker-os-drive-settings"></a>Paramètres de lecteur du système d’exploitation BitLocker

Ces paramètres s’appliquent spécifiquement aux lecteurs de données de système d’exploitation.

- **Authentification supplémentaire au démarrage** : indiquez les conditions d’authentification pour le démarrage de l’ordinateur, notamment l’utilisation du Module de plateforme sécurisée (TPM).
  - **BitLocker avec puce TPM non compatible**
  - **Démarrage du module TPM compatible** : configurez si la puce TPM est autorisée, non autorisée ou obligatoire.
  - **Code PIN de démarrage du module TPM compatible** : configurez si l’utilisation d’un code PIN de démarrage avec la puce TPM est autorisée, non autorisée ou obligatoire.
  - **Clé de démarrage du module TPM compatible** : configurez si l’utilisation d’une clé de démarrage avec la puce TPM est autorisée, non autorisée ou obligatoire.
  - **Code PIN et clé de démarrage du module TPM compatible** : configurez si l’utilisation d’une clé de démarrage et d’un code PIN avec la puce TPM est autorisée, non autorisée ou obligatoire.
- **Longueur minimale du code PIN** : activez ce paramètre pour configurer une longueur minimale pour le code PIN de démarrage de TPM.
  - **Nombre minimal de caractères** : entrez le nombre de caractères obligatoires pour le code PIN de démarrage (**4**-**20**).
- **Récupération du lecteur du système d’exploitation** : activez ce paramètre pour contrôler comment les lecteurs du système d’exploitation protégés par BitLocker sont récupérés quand les informations de démarrage nécessaires ne sont pas disponibles.
  - **Agent de récupération de données basé sur les certificats** : activez ce paramètre si vous souhaitez que les agents de récupération de données puissent être utilisés avec les lecteurs du système d’exploitation protégés par BitLocker.
  - **Création d’un mot de passe de récupération par l’utilisateur** : configurez si les utilisateurs sont autorisés, non autorisés ou contraints à générer un mot de passe de récupération de 48 chiffres.
  - **Création d’une clé de récupération par l’utilisateur** : configurez si les utilisateurs sont autorisés, non autorisés ou contraints à générer une clé de récupération de 256 bits.
  - **Options de récupération dans l’Assistant Installation de BitLocker** : activez ce paramètre pour empêcher les utilisateurs de voir ou de changer les options de récupération quand ils activent BitLocker.
  - **Enregistrer les informations de récupération BitLocker dans AD DS** : active le stockage des informations de récupération BitLocker dans Active Directory.
  - **Informations de récupération BitLocker stockées dans AD DS** : configurez les parties des informations de récupération BitLocker qui sont stockées dans Active Directory. Choisissez parmi :
    - **Sauvegarder les mots de passe et les jeux de clés de récupération**
    - **Sauvegarder les mots de passe de récupération uniquement**
  - **Stocker les informations de récupération dans AD DS avant l’activation de BitLocker** : activez ce paramètre pour empêcher les utilisateurs d’activer BitLocker, sauf si l’appareil est joint au domaine et que les informations de récupération BitLocker sont correctement stockées dans Active Directory.
- **Message et URL de récupération préalables au démarrage** : activez ce paramètre pour configurer le message et l’URL qui s’affichent sur l’écran de récupération de clé préalable au démarrage.
  - **Message de récupération préalable au démarrage** : configurez la façon dont le message de récupération préalable au démarrage est présenté aux utilisateurs. Choisissez parmi :
    - **Utiliser le message et l’URL de récupération par défaut**
    - **Utiliser un message et une URL de récupération vides**
    - **Utiliser le message de récupération personnalisé**
    - **Utiliser l’URL de récupération personnalisée**

### <a name="bitlocker-fixed-data-drive-settings"></a>Paramètres BitLocker des lecteurs de données fixes

- **Accès en écriture à un lecteur de données fixe non protégé par BitLocker** : si ce paramètre est activé, la protection BitLocker doit être activée sur tous les lecteurs de données fixes, ou intégrés, pour qu’ils soient accessibles en écriture.
- **Récupération d’un lecteur fixe** : activez ce paramètre pour contrôler comment les lecteurs fixes protégés par BitLocker sont récupérés quand les informations de démarrage nécessaires ne sont pas disponibles.
  - **Agent de récupération de données** : activez ce paramètre si vous souhaitez que les agents de récupération de données soient utilisés avec les lecteurs fixes protégés par BitLocker.
  - **Création d’un mot de passe de récupération par l’utilisateur** : configurez si les utilisateurs sont autorisés, non autorisés ou contraints à générer un mot de passe de récupération de 48 chiffres.  
  - **Création d’une clé de récupération par l’utilisateur** : configurez si les utilisateurs sont autorisés, non autorisés ou contraints à générer une clé de récupération de 256 bits.
  - **Options de récupération dans l’Assistant Installation de BitLocker** : activez ce paramètre pour empêcher les utilisateurs de voir ou de changer les options de récupération quand ils activent BitLocker.
  - **Enregistrer les informations de récupération BitLocker dans AD DS** : active le stockage des informations de récupération BitLocker dans Active Directory.
  - **Informations de récupération BitLocker dans AD DS** : configurez les parties des informations de récupération BitLocker qui sont stockées dans Active Directory. Choisissez parmi :
    - **Sauvegarder les mots de passe et les jeux de clés de récupération**
    - **Sauvegarder les mots de passe de récupération uniquement**
  - **Stocker les informations de récupération dans AD DS avant l’activation de BitLocker** : activez ce paramètre pour empêcher les utilisateurs d’activer BitLocker, sauf si l’appareil est joint au domaine et que les informations de récupération BitLocker ont été correctement stockées dans Active Directory.

### <a name="bitlocker-removable-data-drive-settings"></a>Paramètres BitLocker des lecteurs de données amovibles

- **Accès en écriture à un lecteur de données amovible non protégé par BitLocker** : spécifiez si le chiffrement BitLocker est obligatoire pour les lecteurs de stockage amovibles.
  - **Accès en écriture aux appareils configurés dans une autre organisation** : spécifiez si les lecteurs de données amovibles qui appartiennent à une autre organisation sont accessibles en écriture.

## <a name="windows-defender-exploit-guard"></a>Windows Defender Exploit Guard

Utilisez [Windows Defender Exploit Guard](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/windows-defender-exploit-guard) pour gérer et réduire la surface d’attaque des applications utilisées par vos employés.

### <a name="attack-surface-reduction"></a>Règles de réduction de la surface d’attaque

- **Marquer le vol des informations d’identification du sous-système de l’autorité de sécurité locale Windows**

Cette fonctionnalité contribue à [empêcher les actions et les applications](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard) généralement utilisées par les programmes malveillants pour infecter les ordinateurs.

#### <a name="rules-to-prevent-office-macro-threats"></a>Règles pour empêcher les menaces sur les macros Office

Empêchez les applications Office d’effectuer les actions suivantes :

- **Applications Office effectuant des injections dans d’autres processus (aucune exception)**
- **Applications/macros Office créant du contenu exécutable**
- **Applications Office lançant des processus enfants**
- **Importations Win32 de code macro Office**

#### <a name="rules-to-prevent-script-threats"></a>Règles pour empêcher les menaces sur les scripts

Bloquez les éléments suivants pour empêcher les menaces sur les scripts :

- **Code js/vbs/ps/macro brouillé**
- **js/vbs, exécution de la charge utile téléchargée à partir d’Internet (aucune exception)**
- **Création de processus à partir des commandes PSExec et WMI**
- **Processus non approuvés et non signés exécutés à partir d’USB**
- **Fichiers exécutables qui ne répondent pas à des critères de prédominance, d’âge ou de liste approuvée**

#### <a name="rules-to-prevent-email-threats"></a>Règles pour empêcher les menaces sur les e-mails

Bloquez ce qui suit pour empêcher les menaces sur les e-mails :

- **Exécution du contenu exécutable (exe, dll, ps, js, vbs, etc.) supprimé de la messagerie (messagerie web/client de messagerie) (aucune exception)**

#### <a name="rules-to-protect-against-ransomware"></a>Règles de protection contre les ransomware
- **Protection avancée contre les ransomware**

> [!TIP]
> Pour plus d’informations sur ces règles, consultez [Reduce attack surfaces with Windows Defender Exploit Guard](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard) (Réduire les surfaces d’attaque avec Windows Defender Exploit Guard).

#### <a name="attack-surface-reduction-exceptions"></a>Exceptions de la réduction de surface d’attaque

- **Fichiers et dossiers à exclure des règles de réduction de la surface d’attaque** : importez/ajoutez une liste d’emplacements à exclure des règles configurées.

### <a name="controlled-folder-access"></a>Accès contrôlé aux dossiers

Protégez vos données importantes contre des applications malveillantes et des menaces, telles que les ransomware.

- **Protection des dossiers** : protégez les fichiers et dossiers contre des modifications indésirables apportées par des applications malveillantes. Vous pouvez importer une **liste des applications qui ont accès aux dossiers protégés** ou les ajouter manuellement. Vous pouvez également ajouter une **liste de dossiers supplémentaires qui doivent être protégés** par un chargement ou les ajouter manuellement.

### <a name="network-filtering"></a>Filtrage du réseau

Bloquez les connexions sortantes de toutes les applications aux adresses IP/domaines de faible réputation.

### <a name="exploit-protection"></a>Exploit Protection

Bloquez les **modifications par l’utilisateur de l’interface d’Exploit Protection** en chargeant un fichier XML qui vous permet de configurer des restrictions au niveau de la mémoire, du flux de contrôle et des stratégies pour protéger une application contre des attaques.

Pour activer Exploit Protection, créez un fichier XML représentant les paramètres d’atténuation du système et des applications de votre choix. Pour cela, utilisez l’une des deux méthodes suivantes :

 1. PowerShell : utilisez une ou plusieurs des applets de commande PowerShell (Get-ProcessMitigation, Set-ProcessMitigation et ConvertTo-ProcessMitigationPolicy) pour configurer les paramètres d’atténuation et les exporter sous forme d’une représentation XML.

 2. Interface utilisateur du Centre de sécurité Windows Defender : dans le Centre de sécurité Windows Defender, cliquez sur Contrôle des applications et du navigateur, puis faites défiler l’écran vers le bas jusqu’à Exploit Protection. Utilisez d’abord les onglets Paramètres système et Paramètres du programme pour configurer les paramètres d’atténuation. Recherchez ensuite le lien Exporter les paramètres en bas de l’écran pour les exporter sous forme d’une représentation XML.

## <a name="windows-defender-application-control"></a>Contrôle d’application Windows Defender

Utilisez **Stratégies d’intégrité du code de contrôle des applications** pour choisir d’autres applications devant être auditées ou dont l’exécution peut être approuvée par le contrôle d’application Windows Defender. L’exécution des composants Windows et de toutes les applications du Windows Store est automatiquement approuvée.

Les applications ne sont pas bloquées quand elles s’exécutent en mode **Auditer uniquement**. Le mode **Auditer uniquement** enregistre tous les événements dans les journaux du client local.

Une fois activé, le contrôle d’application peut être désactivé uniquement en changeant le mode **Appliquer** en **Auditer uniquement**. Quand vous changez le mode **Appliquer** en **Non configuré**, le contrôle d’application continue à s’appliquer sur les appareils attribués.

## <a name="windows-defender-security-center"></a>Centre de sécurité Windows Defender

L’application Centre de sécurité Windows Defender fonctionne comme une application ou un processus distinct de chacune des fonctionnalités individuelles et affiche des notifications dans le centre de notifications. Elle agit comme un collecteur de données ou emplacement unique pour afficher l’état et configurer chacune des fonctionnalités. Vous trouverez plus d’informations dans la documentation [Windows Defender](https://docs.microsoft.com/windows/threat-protection/windows-defender-security-center/windows-defender-security-center).

#### <a name="windows-defender-security-center-app-and-notifications"></a>Application Centre de sécurité Windows Defender et notifications

Empêchez l’utilisateur final d’accéder aux différentes zones de l’application Centre de sécurité Windows Defender. Masquez une section pour bloquer également les notifications associées.

- **Protection contre les virus et menaces**
- **Performances des appareils et intégrité**
- **Pare-feu et protection du réseau**
- **Contrôle des applications et du navigateur**
- **Options de contrôle parental**
- **Notifications des zones affichées de l’application** : choisissez les notifications à afficher aux utilisateurs finaux. Les notifications non critiques sont notamment les récapitulatifs d’activité de l’antivirus Windows Defender, dont les notifications indiquant qu’une analyse est terminée. Toutes les autres notifications sont considérées comme critiques.

#### <a name="it-contact-information"></a>Informations de contact du service informatique

Indiquez les informations de contact du service informatique à afficher dans l’application Centre de sécurité Windows Defender et ses notifications. Vous avez le choix entre **Afficher dans l’application et dans les notifications**, **Afficher uniquement dans l’application**, **Afficher uniquement dans les notifications** ou **Ne pas afficher**. Vous devez définir le **nom de l’organisation du service informatique** et au moins l’une des options de contact suivantes :

- **Numéro de téléphone ou ID Skype du service informatique**
- **Adresse e-mail du service informatique**
- **URL du site web de support informatique**

## <a name="next-steps"></a>Étapes suivantes

Pour attribuer ce profil à des groupes, consultez [Guide pratique pour attribuer des profils d’appareil](device-profile-assign.md).