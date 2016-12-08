---
title: Gestion de PC avec logiciel client | Microsoft Intune
description: "Gérer des PC Windows en installant le logiciel du client Intune."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 08/30/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3b8d22fe-c318-4796-b760-44f1ccf34312
ms.reviewer: owenyen
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: eeb85a28ea6f99a0123ec5df3b0d476a678b85cb
ms.openlocfilehash: fb862178e0791936243ebb21c6b70ea808d07d16


---

# <a name="manage-windows-pcs-with-intune-pc-client-software"></a>Gestion des ordinateurs Windows avec le logiciel client Intune PC
Au lieu [d’inscrire des PC Windows en tant qu’appareils mobiles](set-up-windows-device-management-with-microsoft-intune.md), vous pouvez inscrire et gérer des PC Windows en installant le logiciel client Intune.

Intune gère les PC Windows avec des stratégies semblables aux objets de stratégie de groupe (GPO) des services de domaine Active Directory de Windows Server. Si vous gérez des ordinateurs joints à un domaine Active Directory avec Intune, vous devez [vérifier que les stratégies Intune ne sont pas en conflit avec les objets de stratégie de groupe](resolve-gpo-and-microsoft-intune-policy-conflicts.md) en place dans votre organisation.

Bien que le logiciel client Intune prenne en charge des [fonctionnalités de gestion qui protègent vos PC](policies-to-protect-windows-pcs-in-microsoft-intune.md) en gérant les mises à jour logicielles, le Pare-feu Windows et Endpoint Protection, les PC gérés avec le logiciel client Intune ne peuvent pas être ciblés par d’autres stratégies Intune, notamment les paramètres de stratégie **Windows** spécifiques de la gestion des appareils mobiles.

> [!NOTE]
> Les appareils exécutant Windows 8.1 ou ultérieur peuvent être gérés avec le client Intune ou comme des appareils mobiles. Cette rubrique s’applique aux ordinateurs exécutant le logiciel client Intune. Les opérations simultanées d’installation du client Intune et d’inscription à la gestion d’appareils mobiles ne sont pas prises en charge.

## <a name="requirements-for-intune-pc-client-management"></a>Configuration requise pour la gestion du client Intune PC

**Matériel** : voici la configuration matérielle minimale requise pour l’installation du client Intune :

|Condition requise|Plus d'informations|
|---------------|--------------------|
|Réseau|Le PC sur lequel est installé le client doit disposer d’une connexion à Internet.|
|Processeur et mémoire|Reportez-vous à la configuration requise du processeur et de la RAM pour le système d’exploitation du PC.|
|Espace disque|200 Mo d'espace disponible sur le disque avant l'installation du logiciel client.|

**Logiciel** : voici la configuration logicielle requise pour l’installation du client :

|Condition requise|Plus d'informations|
|---------------|--------------------|
|Système d'exploitation | Appareil Windows exécutant Windows Vista ou ultérieur. Les versions des éditions familiales ne sont pas prises en charge.|
|Autorisations administratives|Le compte qui installe le logiciel client doit disposer des autorisations d’administrateur local sur cet ordinateur.|
|Windows Installer 3.1|Le PC doit disposer de Windows Installer 3.1 au minimum.<br /><br />Pour afficher la version de Windows Installer sur un PC :<br /><br />-   Sur le PC, cliquez avec le bouton droit sur **%windir%\System32\msiexec.exe**, puis cliquez sur **Propriétés**.<br /><br />Vous pouvez télécharger la dernière version de Windows Installer à partir de [Windows Installer Redistributables](http://go.microsoft.com/fwlink/?LinkID=234258) sur le site web Microsoft Developer Network.|
|Supprimer les logiciels clients incompatibles|Avant d’installer le logiciel client Intune, désinstallez tout logiciel client Configuration Manager, Operations Manager, Operations Management Suite et Service Manager du PC.|

## <a name="computer-management-with-the-intune-computer-client"></a>Gestion des ordinateurs avec le client d’ordinateur Intune
Une fois le logiciel client Intune installé, les fonctionnalités de gestion disponibles sont notamment : la [gestion des applications](deploy-apps-in-microsoft-intune.md), la [surveillance en temps réel et Endpoint Protection](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md), la [gestion des paramètres du Pare-feu Windows](help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune.md), l’inventaire matériel et logiciel, le contrôle à distance (par le biais des demandes d’assistance à distance), les [paramètres de mises à jour logicielles](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md) et les rapports sur les paramètres de compatibilité.

Certaines options de gestion disponibles pour les PC gérés comme des appareils mobiles ne sont pas disponibles pour les PC gérés par le logiciel client, notamment :

-   Réinitialisation complète (la réinitialisation sélective est disponible)
-   Accès conditionnel
-   Stratégies Windows autres que les stratégies de **gestion de l’ordinateur**

![Modèle de stratégies pour les PC Windows](../media/pc_policy_template.png)

Outre les actions de l’agent client Intune exécutées localement sur des ordinateurs individuels, vous pouvez également utiliser la console d’administration Intune pour effectuer d’autres [tâches courantes de gestion des ordinateurs](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md) sur les PC Windows sur lesquels le client est installé, notamment :

-   Afficher les informations sur l’inventaire matériel et logiciel des ordinateurs gérés

-   Redémarrer à distance un ordinateur

-   Mettre un ordinateur hors service pour désinstaller le logiciel client et le supprimer de la gestion avec Intune

-   Lier des utilisateurs à des ordinateurs gérés spécifiques

-   Répondre à des demandes d’assistance à distance

L’agent client Intune s’exécute généralement en mode silencieux en arrière-plan sans avoir besoin de l’interaction de l’utilisateur ou de résoudre des problèmes. Toutefois, si vous avez besoin d’aide pour résoudre des problèmes liés à la gestion des ordinateurs, plusieurs [ressources sont disponibles](/intune/troubleshoot/troubleshoot-client-setup-in-microsoft-intune).



<!--HONumber=Nov16_HO1-->


