---
# required metadata

title: Déployer des applications | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: ad5ea85c-aa2e-4110-a184-172cd0b8f270

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Déployer des applications avec Microsoft Intune

Cette rubrique décrit certains des concepts que vous devez comprendre avant de commencer à déployer des applications avec Microsoft Intune.

## Éditeur de logiciel Intune
L’**Éditeur de logiciel Microsoft Intune** démarre quand vous ajoutez ou modifiez des applications à partir de la console d’administration Microsoft Intune. Dans l’éditeur, vous sélectionnez et configurez un type de programme d’installation de logiciel qui permet de charger des applications (programmes pour des ordinateurs ou applications pour des appareils mobiles) à stocker dans l’espace de stockage cloud Intune ou d’établir un lien vers une boutique en ligne ou une application web.

### Configuration requise
Avant de commencer à utiliser l’Éditeur de logiciel Microsoft Intune, vous devez installer la version complète du [Microsoft .NET Framework 4.0](https://www.microsoft.com/download/details.aspx?id=17851). Après l’installation, il peut-être nécessaire de redémarrer votre ordinateur pour que l’éditeur de logiciel s’ouvre correctement.

## Espace de stockage cloud
Toutes les applications que vous déployez en utilisant le type d’installation de programme d’installation de logiciel doivent être mises en package et chargées dans le stockage de cloud Microsoft Intune. Un abonnement d’essai à Intune inclut 2 Go de stockage cloud, utilisé pour stocker les applications gérées et les mises à jour. Un abonnement payant inclut 20 Go, avec la possibilité d’acheter du stockage supplémentaire.

Vous pouvez voir combien d’espace vous utilisez et acheter du stockage supplémentaire dans le nœud **Utilisation du stockage** de l’espace de travail **Administration**.

Les règles suivantes s’appliquent à l’achat de stockage cloud supplémentaire pour Intune :

-   Vous devez disposer d'un abonnement payant actif pour acheter du stockage supplémentaire.

-   Seuls les administrateurs de facturation ou généraux de Microsoft Online Services peuvent acheter du stockage supplémentaire via le portail des comptes Intune. Pour ajouter, supprimer ou gérer ces administrateurs, vous devez être administrateur général et vous connecter au portail des comptes Intune.

-   Si vous êtes un client de licences en volume qui a acheté Intune ou le composant additionnel de Microsoft Intune via le contrat d’entreprise, contactez votre responsable de compte Microsoft ou votre partenaire Microsoft afin d’obtenir des informations tarifaires et acheter du stockage supplémentaire.

#### Configuration requise pour l’espace de stockage cloud

-   Tous les fichiers associés à une application doivent se trouver au même emplacement et être accessibles par Intune.

-   La taille maximale des fichiers que vous chargez est de 2 Go.

-   Pour charger des fichiers, vous devez disposer d’une connexion Internet ayant un débit minimal de 768 Kbits/s.

## Actions de déploiement d’applications
Quand vous déployez des applications, vous pouvez choisir parmi les actions de déploiement suivantes :

-   **Installation requise** : l’application est installée sur l’appareil, sans intervention de l’utilisateur final.

    > [!TIP]
    > Pour les appareils iOS qui ne sont pas en mode supervisé et pour tous les appareils Android, l’utilisateur doit accepter l’offre de l’application avant son installation.
    >
    > Vous ne pouvez plus créer de déploiements d’applications à destination d’appareils iOS exécutant un système d’exploitation antérieur à iOS 7.1. Les déploiements d’applications existants à destination d’appareils exécutant un système d’exploitation antérieur à iOS 7.1 continuent de fonctionner et d’être gérés par Intune.

-   **Installation disponible** : l’application s’affiche sur le portail d’entreprise et les utilisateurs finaux peuvent l’installer à la demande.

-   **Désinstaller** : l'application est désinstallée de l'appareil.

-   **Non applicable** : l'application n'est pas affichée dans le portail d'entreprise et n'est pas installée sur les appareils.

#### Comprendre quelles actions de déploiement sont disponibles pour chaque type de programme d’installation

|Type de programme d’installation|Installation requise|Installation disponible|Désinstaller|Non applicable|
|------------------|--------------------|---------------------|-------------|------------------|
|Package d'application Windows (déployé sur un groupe d'utilisateurs)|Oui|Oui|Oui|Oui|
|Package d’application Windows (déployé sur un groupe d’appareils)|Oui|Non|Oui|Oui|
|Package d'application pour les appareils mobiles (déployé sur un groupe d'utilisateurs)|Oui|Oui|Oui|Oui|
|Package d'application pour les appareils mobiles (déployé sur un groupe d'appareils)|Oui|Non|Oui|Oui|
|Windows Installer (déployé sur un groupe d'utilisateurs)|Non|Oui|Non|Oui|
|Windows Installer (déployé sur un groupe d'appareils)|Oui|Non|Oui|Oui|
|Lien externe (déployé sur un groupe d'utilisateurs)|Non|Oui|Non|Oui|
|Lien externe (déployé sur un groupe d'appareils)|Non|Non|Non|Non|
|Application iOS gérée à partir de l'App Store (déployée sur un groupe d'utilisateurs)|Oui|Oui|Oui|Oui|
|Application iOS gérée à partir de l'App Store (déployée sur un groupe d'appareils)|Oui|Non|Oui|Oui|
> [!TIP]
> Quand vous déployez des applications, si vous sélectionnez à la fois des groupes d’utilisateurs et des groupes d’appareils, vous pouvez déployer l’application seulement comme **Installation disponible**.

## Conflits de déploiement
Quand deux déploiements avec la même action de déploiement sont reçus par un appareil, les règles suivantes s'appliquent :

-   Les déploiements sur un groupe d'appareils ont la priorité sur les déploiements sur un groupe d'utilisateurs. Toutefois, si une application est déployée sur un groupe d'utilisateurs avec une action de déploiement **Disponible** et que la même application est également déployée sur un groupe d'appareils avec une action de déploiement **Non applicable**, l'application est disponible sur le portail d'entreprise pour que les utilisateurs puissent l'installer.

-   L’intention de l’administrateur informatique est prioritaire sur l’utilisateur final.

-   Une action d’installation est prioritaire sur une action de désinstallation.

-   Si une installation requise et une installation disponible sont reçues par un appareil, les actions sont combinées (l’application est à la fois requise et disponible).


## Étapes suivantes

Découvrez comment [déployer des applications dans Microsoft Intune](deploy-apps-in-microsoft-intune.md).

<!--HONumber=May16_HO1-->


