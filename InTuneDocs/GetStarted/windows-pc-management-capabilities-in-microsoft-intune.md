---
title: "Fonctionnalités de gestion des PC Windows | Microsoft Intune"
description: "En savoir plus sur les fonctionnalités Intune lorsque vous gérez des ordinateurs Windows avec le logiciel client Intune."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 08/04/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 77fa5c66-a87c-47df-964c-800eea509b33
ms.reviewer: owenyen
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: a6caef9e0f4d6235ecf1a89c1765d6c8e6ce1a7b
ms.openlocfilehash: e5e3833a38434d4fe55cae554fc49f567b606ad8


---

# Fonctionnalités de gestion des PC Windows (avec le client PC Intune)
Dans la plupart des scénarios, vous inscrirez vos appareils avec Microsoft Intune car cette approche offre davantage de fonctionnalités que le recours au client PC Intune. Toutefois, vous pouvez également gérer des ordinateurs en utilisant le client Intune PC, qui fournit les fonctionnalités suivantes :

-   **Gestion des mises à jour logicielles** : Vous pouvez maintenir les PC à jour et gérer les périodes d’application des mises à jour.

-   **Stratégie de Pare-feu Windows** : Elle garantit qu’aucun PC utilisé dans votre entreprise n’a de Pare-feu Windows inactif ou mal configuré.

-   La **protection contre les programmes malveillants** Intune inclut Endpoint Protection qui veille à la protection de vos PC contre les logiciels malveillants.

-   **Assistance à distance** : Intune permet aux utilisateurs de contacter l’équipe du support informatique qui peut vous aider via une fonctionnalité de Bureau à distance intégrée à Intune (nécessite le logiciel TeamViewer).

-   **Gestion des licences logicielles** : suivez le nombre de licences logicielles disponibles et le nombre de licences disponibles utilisé.
-   **Déploiement d'applications** : déployez des logiciels sur les ordinateurs que vous gérez. Certaines fonctionnalités de gestion d'applications ne sont pas disponibles lorsque vous gérez des ordinateurs avec le logiciel client.


Intune prend en charge l’installation du logiciel client PC sur un maximum de 7 000 appareils Windows.

## Conditions du système d'exploitation
Intune peut gérer des PC exécutant les versions suivantes de Windows (32 bits et 64 bits) :


-   **Windows Vista** : versions Professionnel, Entreprise et Édition Intégrale

-   **Windows 7** : versions Professionnel, Entreprise et Édition Intégrale (sans Service Pack ou avec SP1)

-   **Windows 8** : versions Professionnel et Entreprise

-   **Windows 8.1** : versions Professionnel et Entreprise

- **Windows 10** : versions Professionnel, Éducation et Entreprise


## Configuration matérielle minimale requise
Voici la configuration matérielle minimale requise pour l’installation du client PC Intune :

|Condition requise|Détails|
|---------------|--------------------|
|Réseau|Le PC sur lequel est installé le client doit disposer d’une connexion à Internet.|
|Processeur et mémoire|Reportez-vous à la configuration requise du processeur et de la RAM pour le système d’exploitation du PC.|
|Espace disque|200 Mo d'espace disponible sur le disque avant l'installation du logiciel client.|

## Autres conditions requises
Voici la configuration logicielle requise pour l’installation du client PC Intune :

|Condition requise|Détails|
|---------------|--------------------|
|Autorisations administratives|Le compte qui installe le logiciel client doit disposer des autorisations d’administrateur local sur ce PC.|
|Windows Installer 3.1|Le PC doit disposer de Windows Installer 3.1 au minimum.|
|Supprimer les logiciels clients incompatibles|Avant d’installer le logiciel client PC Intune, vous devez désinstaller le logiciel client suivant de ce PC :<br /><br />- Toute version de Configuration Manager<br />- Toute version de Microsoft Systems Management Server (SMS)|

### Voir aussi
[Fonctionnalités de gestion des appareils mobiles dans Microsoft Intune](./mobile-device-management-capabilities-in-microsoft-intune.md)



<!--HONumber=Aug16_HO3-->


