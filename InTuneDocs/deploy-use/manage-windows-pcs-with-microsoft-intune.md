---
title: Gestion de PC avec logiciel client | Microsoft Docs
description: "Gérer des PC Windows en installant le logiciel du client Intune."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3b8d22fe-c318-4796-b760-44f1ccf34312
ms.reviewer: owenyen
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: c66226b7fc31f91669c4f4f0693ccbd7c679189f
ms.openlocfilehash: 74f2848dcd2863022dac44cf302b330a99cf1a55
ms.lasthandoff: 03/29/2017


---

# <a name="manage-windows-pcs-with-intune-pc-client-software"></a>Gestion des ordinateurs Windows avec le logiciel client Intune PC
L’[inscription de PC Windows en tant qu’appareils mobiles](set-up-windows-device-management-with-microsoft-intune.md) est la méthode préférée d’inscription de PC Windows dans Intune. Cependant, en tant qu’administrateur informatique, vous pouvez aussi choisir d’inscrire et de gérer des PC Windows en installant le logiciel client Intune, comme décrit dans cette rubrique. Le client logiciel Intune n’est pas pris en charge dans le cadre de l’inscription en tant qu’appareil mobile.

Intune gère les PC Windows avec des stratégies semblables aux objets de stratégie de groupe (GPO) des services de domaine Active Directory de Windows Server. Si vous gérez des ordinateurs joints à un domaine Active Directory avec Intune, [vérifiez que les stratégies Intune ne sont pas en conflit avec les objets de stratégie de groupe](resolve-gpo-and-microsoft-intune-policy-conflicts.md) en place dans votre organisation. Vous pouvez en savoir plus sur les [GPO](https://technet.microsoft.com/library/hh147307.aspx).

## <a name="policies-and-app-deployments-for-the-intune-software-client"></a>Stratégies et déploiements d’applications pour le logiciel client Intune

Bien que le logiciel client Intune prenne en charge des [fonctionnalités de gestion qui protègent vos PC](policies-to-protect-windows-pcs-in-microsoft-intune.md) en gérant les mises à jour logicielles, le Pare-feu Windows et Endpoint Protection, les PC gérés avec le logiciel client Intune ne peuvent pas être ciblés par d’autres stratégies Intune, notamment les paramètres de stratégie **Windows** spécifiques à la gestion des appareils mobiles.

Quand vous utilisez le logiciel client Intune pour gérer des PC Windows, vous pouvez utiliser uniquement les stratégies figurant dans la section **Gestion de l’ordinateur**.

  ![Sélection d'un modèle pour la nouvelle stratégie de PC Windows](../media/select-template-for-pc-policy.png)

Pour une description détaillée des stratégies que vous pouvez définir, consultez les rubriques suivantes :

- [Utilisation de stratégies pour vous aider à protéger les PC Windows qui exécutent le logiciel client Intune](https://docs.microsoft.com/intune/deploy-use/policies-to-protect-windows-pcs-in-microsoft-intune)
- [Maintenir des PC Windows à jour avec les mises à jour logicielles dans Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune)
- [Protéger les PC Windows à l'aide de stratégies de Pare-feu Windows dans Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune)
- [Contribuer à la sécurisation des PC Windows avec Endpoint Protection pour Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)

En outre, lors du déploiement d’applications, vous pouvez utiliser uniquement le programme Windows Installer (.exe, .msi).

  ![Sélection de la plateforme et de l’emplacement des fichiers logiciels du client PC](../media/select-platform-of-software-files-for-pc-agent.png)

> [!NOTE]
> Vous pouvez gérer des appareils Windows 8.1 ou version ultérieure en tant que PC, en utilisant le logiciel client Intune ou comme des appareils mobiles à l’aide de la fonctionnalité de gestion des appareils mobiles (MDM). Vous ne pouvez pas utiliser les deux méthodes ensemble. Réfléchissez donc bien avant de prendre votre décision de gérer des PC à l’aide du logiciel client Intune. Cette rubrique concerne uniquement la gestion d’appareils comme PC en exécutant le logiciel client Intune.

## <a name="requirements-for-intune-pc-client-management"></a>Configuration requise pour la gestion du client Intune PC

**Matériel** : voici la configuration matérielle minimale requise pour l’installation du logiciel client Intune :

|Situation|Plus d'informations|
|---------------|--------------------|
|Réseau|Le PC sur lequel est installé le client doit disposer d’une connexion à Internet.|
|Processeur et mémoire|Reportez-vous à la configuration requise du processeur et de la RAM pour le système d’exploitation du PC.|
|Espace disque|200 Mo d'espace disponible sur le disque avant l'installation du logiciel client.|

**Logiciel** : voici la configuration logicielle requise pour l’installation du logiciel client :

|Situation|Plus d'informations|
|---------------|--------------------|
|Système d'exploitation | Appareil Windows exécutant Windows Vista ou ultérieur. </br></br>**Les éditions familiales ne sont pas prises en charge.**|
|Autorisations administratives|Le compte qui installe le logiciel client doit disposer des autorisations d’administrateur local sur cet ordinateur.|
|Windows Installer 3.1|Le PC doit disposer de Windows Installer 3.1 au minimum.<br /><br />Pour afficher la version de Windows Installer sur un PC :<br /><br />  Sur le PC, cliquez avec le bouton droit sur **%windir%\System32\msiexec.exe**, puis cliquez sur **Propriétés**.<br /><br />Vous pouvez télécharger la dernière version de Windows Installer à partir de [Windows Installer Redistributables](http://go.microsoft.com/fwlink/?LinkID=234258) sur le site web Microsoft Developer Network.|
|Supprimer les logiciels clients incompatibles|Avant d’installer le logiciel client Intune, désinstallez tout logiciel client Configuration Manager, Operations Manager, Operations Management Suite et Service Manager du PC.|

## <a name="computer-management-capabilities-with-the-intune-client-software"></a>Fonctionnalités de gestion des ordinateurs avec le logiciel client Intune

Une fois le logiciel client Intune installé, les fonctionnalités de gestion sont les suivantes :

- [Gestion des applications](deploy-apps-in-microsoft-intune.md)

- [Surveillance en temps réel et Endpoint Protection](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md) : Endpoint Protection est similaire à Windows Defender. Endpoint Protection s’applique à Windows 7 et Windows 8. Pour Windows 10 et versions ultérieures, le nom du produit est devenu Windows Defender.

- [Gestion des paramètres du Pare-feu Windows](help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune.md), inventaire matériel et logiciel, contrôle à distance (via des demandes d’assistance à distance)

- [Paramètres de mise à jour logicielle](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md)

- Création de rapports sur les paramètres de conformité

Dans la console d’administration Intune, certaines sections, telles que « Mises à jour », « Protection » et « Licences » apparaissent uniquement si vous avez inscrit des appareils à l’aide du logiciel client Intune.

  ![Éléments de la console administrateur qui s’affichent uniquement pour le client PC](../media/admin-console-settings-only-for-pc-agent.png)

Vous pouvez également utiliser la console d’administration Intune pour effectuer d’autres tâches courantes de gestion des ordinateurs sur les PC Windows sur lesquels le client est installé :

-   Afficher les informations sur l’inventaire matériel et logiciel des ordinateurs gérés
-   Redémarrer à distance un ordinateur
-   Mettre un ordinateur hors service pour désinstaller le logiciel client et le supprimer de la gestion avec Intune
-   Lier des utilisateurs à des ordinateurs gérés spécifiques
-   Répondre à des demandes d’assistance à distance

Pour plus d’informations sur les tâches ci-dessus, consultez les [tâches courantes de gestion des ordinateurs](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md).

## <a name="management-limitations-of-the-intune-client-software"></a>Limitations de la gestion du logiciel client Intune

Certaines options de gestion, qui peuvent être utilisées pour gérer des PC comme des appareils mobiles, ne peuvent pas être utilisées pour les PC qui sont gérés par le logiciel client Intune :

-   Réinitialisation complète (la réinitialisation sélective est disponible)

-   Accès conditionnel

## <a name="help-with-troubleshooting"></a>Aide à la résolution des problèmes

Le logiciel client Intune s’exécute généralement en mode silencieux en arrière-plan sans avoir besoin de l’intervention de l’utilisateur ni de dépannage. Si vous avez besoin de résoudre des problèmes de gestion de PC, vous pouvez vérifier les journaux. Le logiciel client Intune et les journaux correspondants sont installés dans le répertoire %Program Files%\Microsoft\OnlineManagement.

Vous pouvez également consulter la rubrique [Résolution des problèmes d’installation du client dans Microsoft Intune](/intune/troubleshoot/troubleshoot-client-setup-in-microsoft-intune) pour vérifier les problèmes qui peuvent se produire et les solutions proposées.

