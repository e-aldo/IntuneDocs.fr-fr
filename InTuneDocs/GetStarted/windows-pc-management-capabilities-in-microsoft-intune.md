---
title: "Fonctionnalités du client logiciel PC Intune | Microsoft Intune"
description: "En savoir plus sur les fonctionnalités Intune lorsque vous gérez des PC Windows avec le client logiciel Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 09/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 77fa5c66-a87c-47df-964c-800eea509b33
ms.reviewer: owenyen
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: a4f7a503417938eabb4334757dcf12a63f082fd3
ms.openlocfilehash: e786cd33b5c963fa373d281e93721d0dd0f5456c


---

# Fonctionnalités de gestion des PC Windows quand vous utilisez le client logiciel Intune
Dans la plupart des scénarios, vous inscrirez vos appareils avec Microsoft Intune, car cette approche offre davantage de fonctionnalités. Toutefois, vous pouvez également gérer des PC en utilisant le client logiciel Intune, qui fournit les fonctionnalités suivantes :

-   **[Gestion des mises à jour logicielles](/intune/deploy-use/keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune)** : vous pouvez maintenir les PC à jour et gérer les périodes d’application des mises à jour.

-   **[Stratégie de Pare-feu Windows](/intune/deploy-use/help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune)** : elle permet de garantir que tous les PC utilisés dans votre entreprise ont un Pare-feu Windows actif et correctement configuré.

-   **[Protection contre les programmes malveillants](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)** : Intune inclut la fonctionnalité Endpoint Protection, qui vous aide à protéger les PC contre les programmes malveillants.

-   **[Assistance à distance](/intune/deploy-use/common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client#request-and-provide-remote-assistance-to-windows-pcs-that-use-the-intune-client-software )** : Intune permet aux utilisateurs de contacter l’équipe du support informatique, qui peut ensuite les aider via une fonctionnalité de Bureau à distance intégrée à Intune (nécessite le logiciel TeamViewer).

-   **[Gestion des licences logicielles](/intune/deploy-use/manage-license-agreements-for-windows-pc-software-in-microsoft-intune)** : suivez le nombre de licences logicielles disponibles et le nombre de ces licences utilisé.
-   **[Déploiement d’applications](/intune/deploy-use/add-apps-for-windows-pcs-in-microsoft-intune)** : déployez des logiciels sur les PC que vous gérez. Certaines fonctionnalités de gestion d'applications ne sont pas disponibles lorsque vous gérez des PC avec le client logiciel.


Intune prend en charge l’installation du client logiciel sur un maximum de 7 000 appareils Windows.

## Conditions du système d'exploitation
Intune peut gérer des PC exécutant les versions suivantes de Windows (32 bits et 64 bits) :


-   **Windows Vista** : versions Professionnel, Entreprise et Édition Intégrale

-   **Windows 7** : versions Professionnel, Entreprise et Édition Intégrale (sans Service Pack ou avec SP1)

-   **Windows 8** : versions Professionnel et Entreprise

-   **Windows 8.1** : versions Professionnel et Entreprise

- **Windows 10** : versions Professionnel, Éducation et Entreprise


## Configuration matérielle minimale requise
Voici la configuration matérielle minimale requise pour l’installation du client logiciel Intune :

|Condition requise|Détails|
|---------------|--------------------|
|Réseau|Le PC sur lequel est installé le client doit disposer d’une connexion à Internet.|
|Processeur et mémoire|Reportez-vous à la configuration requise du processeur et de la RAM pour le système d’exploitation du PC.|
|Espace disque|200 Mo d'espace disponible sur le disque avant l'installation du logiciel client.|

## Autres conditions requises
Voici la configuration logicielle requise pour l’installation du client logiciel Intune :

|Condition requise|Détails|
|---------------|--------------------|
|Autorisations administratives|Le compte qui installe le logiciel client doit disposer des autorisations d’administrateur local sur ce PC.|
|Windows Installer 3.1|Le PC doit disposer de Windows Installer 3.1 au minimum.|
|Supprimer les logiciels clients incompatibles|Avant d’installer le logiciel client PC Intune, vous devez désinstaller le logiciel client suivant de ce PC :<br /><br />- Toute version de Configuration Manager<br />- Toute version de Microsoft Systems Management Server (SMS)|

### Voir aussi
[Fonctionnalités de gestion des appareils inscrits de Microsoft Intune](./mobile-device-management-capabilities-in-microsoft-intune.md)



<!--HONumber=Oct16_HO4-->


