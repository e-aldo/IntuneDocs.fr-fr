---
# required metadata

title: Fonctionnalités de gestion des PC Windows dans Microsoft Intune | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 77fa5c66-a87c-47df-964c-800eea509b33

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Fonctionnalités de gestion des PC Windows (avec le client PC Intune)
Dans la plupart des scénarios, vous inscrirez vos appareils avec Microsoft Intune car cette approche offre davantage de fonctionnalités que le recours au client PC Intune. Toutefois, vous pouvez également gérer des ordinateurs en utilisant le client Intune PC qui fournit les fonctionnalités suivantes :

-   **Gérer les mises à jour logicielles** : vous pouvez maintenir les PC à jour et gérer les périodes d’application des mises à jour.

-   **Stratégie de Pare-feu Windows** : elle garantit qu’aucun PC utilisé par votre entreprise n’a de Pare-feu Windows inactif ou mal configuré.

-   La **protection contre les programmes malveillants** Intune inclut Endpoint Protection qui veille à la protection de vos PC contre les logiciels malveillants.

-   **Assistance à distance** : Intune permet aux utilisateurs de contacter l'équipe du support informatique, qui peut vous aider via une fonctionnalité de Bureau à distance intégrée à Intune.

-   **Gestion des licences logicielles** : suivez le nombre de licences logicielles disponibles et le nombre de licences disponibles utilisé.
-   **Déploiement d'applications** : déployez des logiciels sur les ordinateurs que vous gérez. Certaines fonctionnalités de gestion d'applications ne sont pas disponibles lorsque vous gérez des ordinateurs avec le logiciel client.


## Conditions du système d'exploitation
Intune peut gérer des ordinateurs exécutant les versions de Windows suivantes (x86 et x64) :


-   **Windows Vista** : Professionnel, Entreprise et Édition Intégrale.

-   **Windows 7** : Professionnel, Entreprise et Édition Intégrale (sans Service Pack ou avec SP1).

-   **Windows 8** : Professionnel et Entreprise.

-   **Windows 8.1** : Professionnel et Entreprise.


## Configuration matérielle minimale requise
Voici la configuration matérielle minimale requise pour l’installation du client PC Intune :

|Condition requise|Détails|
|---------------|--------------------|
|Réseau|Le PC sur lequel est installé le client doit disposer d’une connexion à Internet.|
|Processeur et mémoire|Reportez-vous à la configuration requise du processeur et de la RAM pour le système d’exploitation du PC.|
|Espace disque|200 Mo d'espace disponible sur le disque avant l'installation du logiciel client.|

## Autres conditions requises
Voici la configuration logicielle requise pour l’installation du client PC Intune :

|Condition requise|Détails|
|---------------|--------------------|
|Autorisations administratives|Le compte qui installe le logiciel client doit disposer des autorisations d’administrateur local sur ce PC.|
|Windows Installer 3.1|Windows Installer 3.1 au minimum doit être installé sur le PC.|
|Supprimer les logiciels clients incompatibles|Avant d’installer le logiciel client PC Intune , vous devez désinstaller le logiciel client suivant de ce PC :<br /><br />- Toute version de Configuration Manager<br />- Toute version de Microsoft Systems Management Server (SMS)|

### Voir aussi
[Fonctionnalités de gestion des appareils mobiles dans Microsoft Intune](/intune/understand/mobile-device-management-capabilties-in-microsoft-intune.md)


<!--HONumber=May16_HO1-->


