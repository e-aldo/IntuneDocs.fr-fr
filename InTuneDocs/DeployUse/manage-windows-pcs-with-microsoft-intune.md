---
title: Gestion de PC avec logiciel client | Microsoft Intune
description: "Gérer des PC Windows en installant le logiciel du client Intune."
keywords: 
author: nathbarn
manager: angrobe
ms.date: 07/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3b8d22fe-c318-4796-b760-44f1ccf34312
ms.reviewer: owenyen
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: cf471320f122eea7804ff6cd6cad208f8cd5a692
ms.openlocfilehash: f264dc3740ce9b117fcc01c39792904a2dc6e7ab


---

# Gestion des ordinateurs Windows avec le logiciel client Intune PC
Au lieu [d’inscrire des PC Windows en tant qu’appareils mobiles](set-up-windows-device-management-with-microsoft-intune.md), vous pouvez inscrire et gérer des PC Windows en installant le logiciel client Intune.

Intune gère les PC Windows avec des stratégies semblables aux objets de stratégie de groupe (GPO) des services de domaine Active Directory de Windows Server. Si vous gérez des ordinateurs joints à un domaine Active Directory avec Intune, vous devez [vérifier que les stratégies Intune ne sont pas en conflit avec les objets de stratégie de groupe](resolve-gpo-and-microsoft-intune-policy-conflicts.md) en place dans votre organisation.

Bien que le client logiciel Intune prenne en charge des [fonctionnalités de gestion qui protègent vos PC](policies-to-protect-windows-pcs-in-microsoft-intune.md) en gérant des mises à jour logicielles, le Pare-feu Windows et Endpoint Protection, les PC gérés avec le client Intune ne peuvent pas être ciblés par d’autres stratégies Intune, notamment les paramètres de stratégie **Windows** spécifiques à la gestion des appareils mobiles.

> [!NOTE]
> Les appareils qui exécutent Windows 8.1 ou versions ultérieures peuvent être gérés à l’aide du client Intune ou inscrits en tant qu’appareils mobiles. Les informations ci-dessous s’appliquent aux ordinateurs qui exécutent le client Intune. Les opérations simultanées d’installation du client Intune PC et d’inscription de l’appareil Windows pour la gestion d’appareils mobiles ne sont pas prises en charge.

## Configuration requise pour la gestion du client Intune PC

**Matériel** : voici la configuration matérielle minimale requise pour l’installation du client Intune :

|Condition requise|Plus d'informations|
|---------------|--------------------|
|Réseau|Le PC sur lequel est installé le client doit disposer d’une connexion à Internet.|
|Processeur et mémoire|Reportez-vous à la configuration requise du processeur et de la RAM pour le système d’exploitation du PC.|
|Espace disque|200 Mo d'espace disponible sur le disque avant l'installation du logiciel client.|

**Logiciel** : voici la configuration logicielle requise pour l’installation du client :

|Condition requise|Plus d'informations|
|---------------|--------------------|
|Système d'exploitation | Appareil Windows exécutant Windows 7 ou une version ultérieure. |
|Autorisations administratives|Le compte qui installe le logiciel client doit disposer des autorisations d’administrateur local sur cet ordinateur.|
|Windows Installer 3.1|Le PC doit disposer de Windows Installer 3.1 au minimum.<br /><br />Pour afficher la version de Windows Installer sur un PC :<br /><br />-   Sur le PC, cliquez avec le bouton droit sur **%windir%\System32\msiexec.exe**, puis cliquez sur **Propriétés**.<br /><br />Vous pouvez télécharger la dernière version de Windows Installer à partir de [Windows Installer Redistributables](http://go.microsoft.com/fwlink/?LinkID=234258) sur le site web Microsoft Developer Network.|
|Supprimer les logiciels clients incompatibles|Avant d’installer le logiciel client Intune, vous devez désinstaller le gestionnaire de configuration ou le client du serveur de gestion du système du PC, s’ils sont présents.|

## Installer le client d’ordinateur Intune
Le logiciel client Intune peut être installé en suivant l’une de ces méthodes :

-  [Déployez manuellement le logiciel client Microsoft Intune](install-the-windows-pc-client-with-microsoft-intune.md#to-manually-deploy-the-client-software). Dans ce type de déploiement, un administrateur télécharge le logiciel client Intune et l’installe manuellement sur chaque PC.

  Pour télécharger le logiciel client Intune, ouvrez la [console d’administration Intune](https://manage.microsoft.com), puis sélectionnez **Administrateur** > **Téléchargement du logiciel client** et cliquez sur **Télécharger le logiciel client**.

-  Utilisez les fichiers que vous avez téléchargés pour l’installation manuelle du client logiciel Intune pour [déployer le client sur des ordinateurs joints à un domaine à l’aide d’objets de stratégie de groupe Active Directory](install-the-windows-pc-client-with-microsoft-intune.md#to-automatically-deploy-the-client-software-by-using-group-policy).

-  Déployez le logiciel client Intune sur des ordinateurs dans le cadre d'un [déploiement de système d'exploitation](install-the-windows-pc-client-with-microsoft-intune.md#install-the-microsoft-intune-client-software-as-part-of-an-image).

-  Envoyez des instructions aux utilisateurs avec l’URL du Portail d’entreprise Intune, [https://portal.manage.microsoft.com](http://go.microsoft.com/fwlink/?LinkId=825632). Lorsqu’ils ouvrent le Portail d’entreprise, les utilisateurs sont invités à inscrire leur PC en téléchargeant et exécutant le logiciel client Intune.

## Gestion des ordinateurs avec le client d’ordinateur Intune
Une fois le logiciel client Intune installé, il active plusieurs fonctionnalités de gestion des ordinateurs, notamment : la [gestion des applications](deploy-apps-in-microsoft-intune.md), Endpoint Protection, l’inventaire matériel et logiciel, le contrôle à distance (par le biais des demandes d’assistance à distance), les mises à jour logicielles et les rapports sur les paramètres de compatibilité.

Plusieurs tâches de gestion des ordinateurs activées par le client d’ordinateur sont gérées à l’aide de stratégies Intune telles que les suivantes :

-   Configuration des [paramètres du Pare-feu Windows](help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune.md) sur les ordinateurs gérés.

-   Configuration des [paramètres de mise à jour logicielle](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md) pour les ordinateurs gérés afin de rechercher et télécharger les mises à jour logicielles obligatoires.

-   Contribuer à la sécurisation des ordinateurs gérés contre les menaces potentielles et les logiciels malveillants par le biais de la [surveillance en temps réel et de la gestion Endpoint Protection](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md) .

![Modèle de stratégies pour les PC Windows](../media/pc_policy_template.png)

Outre les actions de l’agent client Intune exécutées localement sur des ordinateurs individuels, vous pouvez également utiliser la console d’administration Intune pour effectuer d’autres [tâches courantes de gestion des ordinateurs](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md) sur les PC Windows sur lesquels le client est installé, notamment :

-   Afficher les informations sur l’inventaire matériel et logiciel des ordinateurs gérés

-   Redémarrer à distance un ordinateur

-   Mettre un ordinateur hors service pour désinstaller le logiciel client et le supprimer de la gestion avec Intune

-   Lier des utilisateurs à des ordinateurs gérés spécifiques

-   Répondre à des demandes d’assistance à distance

L’agent client Intune s’exécute généralement en mode silencieux en arrière-plan sans avoir besoin de l’interaction de l’utilisateur ou de résoudre des problèmes. Toutefois, si vous avez besoin d’aide pour résoudre des problèmes liés à la gestion des ordinateurs, plusieurs [ressources sont disponibles](/intune/troubleshoot/troubleshoot-client-setup-in-microsoft-intune).



<!--HONumber=Aug16_HO4-->


