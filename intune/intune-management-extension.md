---
title: "Gérer des scripts PowerShell dans Intune pour des appareils Windows 10"
titlesuffix: Azure portal
description: "Découvrez comment charger des scripts PowerShell dans Intune pour les exécuter sur des appareils Windows 10."
keywords: 
author: dougeby
manager: angrobe
ms.date: 10/17/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 768b6f08-3eff-4551-b139-095b3cfd1f89
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b621edad5523f3c77191fb2ef8ca2ea67318dec0
ms.sourcegitcommit: e9f9fccccef691333143b7523d1b325ee7d1915a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/02/2017
---
# <a name="manage-powershell-scripts-in-intune-for-windows-10-devices"></a>Gérer des scripts PowerShell dans Intune pour des appareils Windows 10
L’extension de gestion Intune vous permet de charger des scripts PowerShell dans Intune pour les exécuter sur des appareils Windows 10. L’extension de gestion vient en complément des fonctionnalités de gestion des appareils mobiles (MDM) Windows 10 et facilite l’adoption d’une gestion moderne.

## <a name="moving-to-modern-management"></a>Vers une gestion moderne
Actuellement, l’informatique de l’utilisateur final connaît une transformation numérique. L’informatique classique et traditionnelle se caractérise par une plateforme d’appareils unique, des appareils d’entreprise, des utilisateurs travaillant depuis leur bureau et de nombreux processus informatiques manuels et réactifs. En revanche, un lieu de travail moderne compte plusieurs plateformes d’appareils à la fois personnelles et professionnelles, permet aux utilisateurs de travailler où qu’ils se trouvent et offre des processus informatiques automatisés et proactifs. 

Les services MDM, tels que Microsoft Intune, peuvent gérer les appareils Windows 10 en utilisant le protocole MDM. Le client de gestion Windows 10 intégré peut communiquer avec Intune pour effectuer des tâches de gestion d’entreprise. Il facilite la gestion moderne sur les appareils Windows 10. Il existe toutefois certaines fonctionnalités susceptibles de vous être nécessaires, telles que la configuration avancée des appareils, le dépannage et la gestion des applications Win32 héritée, qui ne sont pas disponibles dans la gestion des appareils mobiles Windows 10. Pour ces fonctionnalités, vous pouvez exécuter le logiciel client Intune sur vos appareils Windows 10. Par voie de conséquence, vous ne pouvez pas utiliser les nouvelles fonctionnalités fournies par la gestion des appareils mobiles Windows 10. [Comparez le logiciel client Intune et la gestion des appareils mobiles Windows 10](https://docs.microsoft.com/intune-classic/deploy-use/pc-management-comparison).

L’extension de gestion Intune vient en complément des fonctionnalités MDM de Windows 10 intégrées. Vous pouvez créer des scripts PowerShell à exécuter sur les appareils Windows 10 qui fournissent les fonctionnalités dont vous avez besoin. Par exemple, vous pouvez créer un script PowerShell qui installe une application Win32 héritée sur vos appareils Windows 10, charger le script sur Intune, affecter le script à un groupe Azure Active Directory (AD) et exécuter le script sur les appareils Windows 10. Vous pouvez ensuite surveiller l’état de l’exécution du script sur les appareils Windows 10 du début à la fin.

## <a name="prerequisites"></a>Prérequis
L’extension de gestion Intune est soumise aux prérequis suivants :
- Les appareils doivent être joints à Azure AD.
- Les appareils doivent exécuter Windows 10, version 1607 ou ultérieure.

## <a name="create-a-powershell-script-policy"></a>Créer une stratégie de script PowerShell 
1. Connectez-vous au [portail Azure](https://portal.azure.com).
2. Choisissez **Autres services** > **Surveillance + Gestion** > **Intune**.
3. Dans le panneau **Intune**, choisissez **Configuration de l’appareil**.
4. Dans le panneau **Configuration de l’appareil**, choisissez **Gérer** > **Scripts PowerShell**.
5. Dans le panneau **Scripts PowerShell**, choisissez **Ajouter un script**.
6. Dans le panneau **Ajouter un script PowerShell**, entrez un **Nom** et une **Description** pour le script PowerShell.
7. Pour **Emplacement du script**, recherchez le script PowerShell. La taille du script doit être inférieure à 10 Ko (ASCII) ou 5 Ko (Unicode).
8. Choisissez **Configurer**, puis indiquez si vous souhaitez exécuter le script avec les informations d’identification de l’utilisateur sur l’appareil (**Oui**) ou dans le contexte du système (**Non**). Par défaut, le script s’exécute dans le contexte du système. Sélectionnez **Oui**, sauf si le script doit s’exécuter dans le contexte du système. 
  ![Panneau Ajouter un script PowerShell](./media/mgmt-extension-add-script.png)
9. Indiquez si le script doit être signé par un éditeur approuvé (**Oui**). Par défaut, il n’est pas nécessaire que le script soit signé. 
10. Cliquez sur **OK**, puis cliquez sur **Créer** pour enregistrer le script.

## <a name="assign-a-powershell-script-policy"></a>Assigner une stratégie de script PowerShell
1. Connectez-vous au [portail Azure](https://portal.azure.com).
2. Choisissez **Autres services** > **Surveillance + Gestion** > **Intune**.
3. Dans le panneau **Intune**, choisissez **Configuration de l’appareil**.
4. Dans le panneau **Configuration de l’appareil**, choisissez **Gérer** > **Scripts PowerShell**.
5. Dans le panneau **Scripts PowerShell**, sélectionnez le script à assigner, puis choisissez **Gérer** > **Affectations**.
  ![Panneau Ajouter un script PowerShell](./media/mgmt-extension-assignments.png)
 
6. Choisissez **Sélectionner des groupes** pour répertorier les groupes Azure AD disponibles. 
7. Sélectionnez les groupes, puis cliquez sur **Sélectionner** pour attribuer la stratégie aux groupes sélectionnés.

L’extension de gestion Intune se synchronise avec Intune une fois par heure. Une fois la stratégie attribuée aux groupes Azure AD, le script PowerShell est exécuté, puis les résultats de l’exécution sont consignés dans un rapport. 
 
## <a name="monitor-run-status-for-powershell-scripts"></a>Surveiller l’état de l’exécution des scripts PowerShell
Vous pouvez surveiller l’état de l’exécution des scripts PowerShell pour les utilisateurs et les appareils dans le portail Azure.
1. Connectez-vous au [portail Azure](https://portal.azure.com).
2. Choisissez **Autres services** > **Surveillance + Gestion** > **Intune**.
3. Dans le panneau **Intune**, choisissez **Configuration de l’appareil**.
4. Dans le panneau **Configuration de l’appareil**, choisissez **Gérer** > **Scripts PowerShell**.
5. Dans le panneau **Scripts PowerShell**, sélectionnez le script à surveiller, choisissez **Surveiller**, puis un des rapports suivants :
   - **État de l’appareil**
   - **État de l’utilisateur**
