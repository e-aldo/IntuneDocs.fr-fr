---
title: Inscrire des appareils avec Windows AutoPilot
titleSuffix: Microsoft Intune
description: Découvrez comment inscrire des appareils Windows 10 avec Windows AutoPilot.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/25/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: a2dc5594-a373-48dc-ba3d-27aff0c3f944
ms.openlocfilehash: c96f211f18168c8ae55f0ca2391c6c140caef649
ms.sourcegitcommit: dc8b6f802cca7895a19ec38bec283d4b3150d213
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/19/2018
ms.locfileid: "39138714"
---
# <a name="enroll-windows-devices-by-using-the-windows-autopilot"></a>Inscrire des appareils Windows avec Windows AutoPilot
Windows AutoPilot simplifie le provisionnement des appareils. La création et la maintenance des images de système d’exploitation personnalisées demandent beaucoup de temps. L’application de ces images de système d’exploitation personnalisées à de nouveaux appareils en vue de les préparer pour vos utilisateurs finaux peut être tout aussi longue. Avec Microsoft Intune et AutoPilot, vous pouvez donner de nouveaux appareils à vos utilisateurs finaux sans devoir créer, gérer et appliquer des images de système d’exploitation personnalisées sur les appareils. Quand vous utilisez Intune pour gérer des appareils AutoPilot, vous pouvez gérer des stratégies, des profils, des applications, etc. une fois ceux-ci inscrits. Pour une vue d’ensemble des avantages, des scénarios et des prérequis, consultez [Vue d’ensemble de Windows AutoPilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-10-autopilot).

## <a name="prerequisites"></a>Prérequis
- [Inscription automatique Windows activée](https://docs.microsoft.com/intune-classic/deploy-use/set-up-windows-device-management-with-microsoft-intune#enable-windows-10-automatic-enrollment)
- [Abonnement à Azure Active Directory Premium](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium) <!--&#40;[trial subscription](http://go.microsoft.com/fwlink/?LinkID=816845)&#41;-->

## <a name="add-devices"></a>Ajouter des appareils

Vous pouvez ajouter des appareils Windows AutoPilot en important un fichier CSV contenant leurs informations.

1. Accédez à [Intune dans le portail Azure](https://aka.ms/intuneportal), puis choisissez **Inscription des appareils** > **Inscription Windows** > **Appareils** > **Importer**.

    ![Capture d’écran des appareils Windows AutoPilot](media/enrollment-autopilot/autopilot-import-device.png)

2. Sous **Ajouter des appareils Windows AutoPilot**, accédez au fichier CSV répertoriant les appareils que vous souhaitez ajouter. Le fichier doit contenir les numéros de série, les ID de produit Windows, les codes de hachage du matériel et les ID de commande facultatifs des appareils.

    ![Capture d’écran Ajouter des appareils Windows AutoPilot](media/enrollment-autopilot/autopilot-import-device2.png)

3. Choisissez **Importer** pour démarrer l’importation des informations sur les appareils. L’importation peut prendre plusieurs minutes.

4. Une fois l’importation terminée, choisissez **Inscription de l’appareil** > **Inscription Windows** > **Windows AutoPilot** > **Appareils** > **Synchroniser**. Un message indique que la synchronisation est en cours. Le processus peut durer quelques minutes, en fonction du nombre d’appareils à synchroniser.

5. Actualisez la vue pour voir les nouveaux appareils.

## <a name="create-an-autopilot-device-group"></a>Créer un groupe d’appareils AutoPilot

1. Accédez à [Intune dans le portail Azure](https://aka.ms/intuneportal), puis choisissez **Groupes**.
2. Dans le panneau **Groupe** :
    1. Pour **Type de groupe**, choisissez **Sécurité**.
    2. Renseignez les champs **Nom du groupe** et **Description du groupe**.
    3. Pour **Type d’appartenance**, choisissez **Affecté** ou **Appareil dynamique**.
3. Si vous avez choisi **Affecté** pour **Type d’appartenance** à l’étape précédente, dans le panneau **Groupe**, choisissez **Membres**, puis ajoutez les appareils AutoPilot au groupe.
    Les appareils AutoPilot qui ne sont pas encore inscrits sont ceux dont le nom correspond au numéro de série de l’appareil.
4. Si vous avez choisi **Appareils dynamiques** pour **Type d’appartenance** ci-dessus, dans le panneau **Groupe**, choisissez **Membres de dispositif dynamique**, puis tapez le code suivant dans la zone **Règle avancée**.
    - Si vous souhaitez créer un groupe qui inclut tous vos appareils AutoPilot, tapez `(device.devicePhysicalIDs -any _ -contains "[ZTDId]")`.
    - Si vous souhaitez créer un groupe qui inclut tous les appareils AutoPilot associés à un certain ID de commande, tapez `(device.devicePhysicalIds -any _ -eq "[OrderID]:179887111881") `.
    - Si vous souhaitez créer un groupe qui inclut tous les appareils AutoPilot associés à un certain ID de bon de commande, tapez `(device.devicePhysicalIds -any _ -eq "[PurchaseOrderId]:76222342342")`.
    
    Après avoir ajouté le code dans la zone **Règle avancée**, choisissez **Enregistrer**.
5. Choisissez **Créer**.



## <a name="create-an-autopilot-deployment-profile"></a>Créer un profil de déploiement AutoPilot
Les profils de déploiement AutoPilot sont utilisés pour configurer les appareils AutoPilot.
1. Accédez à [Intune dans le portail Azure](https://aka.ms/intuneportal), puis choisissez **Inscription des appareils** > **Inscription Windows** > **Profils de déploiement** > **Créer un profil**.
2. Tapez un **Nom** et une **Description** facultative.
3. Pour **Mode de déploiement**, choisissez l’une de ces deux options :
    - **Géré par l’utilisateur** : les appareils avec ce profil sont associés à l’utilisateur qui inscrit l’appareil. Vous devez fournir des informations d’identification d’utilisateur pour provisionner l’appareil.
    - **Auto-déploiement (préversion)** : les appareils (Windows 10 Insider Preview build 17672 ou ultérieure) avec ce profil ne sont pas associés à l’utilisateur qui inscrit l’appareil. Vous n’avez pas à fournir des informations d’identification d’utilisateur pour provisionner l’appareil.
4. Dans la zone **Joindre à Azure AD en tant que**, sélectionnez **Joint à Azure AD**.
5. Choisissez **OOBE (Out-Of-Box Experience)**, configurez les options suivantes, puis choisissez **Enregistrer** :
    - **Langue (région)*** : choisissez la langue à utiliser pour l’appareil. Cette option est disponible uniquement si vous avez choisi **Auto-déploiement**  comme **Mode de déploiement**.
    - **Configurer le clavier automatiquement*** : si **Langue (région)** est sélectionné, vous pouvez ignorer la page de sélection du clavier. Cette option est disponible uniquement si vous avez choisi **Auto-déploiement**  comme **Mode de déploiement**.
    - **Contrat de licence utilisateur final (CLUF)** : (Windows 10, version 1709 ou ultérieure) choisissez s’il faut montrer le CLUF aux utilisateurs.
    - **Paramètres de confidentialité** : choisissez si vous voulez montrer les paramètres de confidentialité aux utilisateurs.
    - **Type de compte d’utilisateur** : choisissez si le type de compte d’utilisateur est **Administrateur** ou **Standard**. 

6. Choisissez **Créer** pour créer le profil. Le profil de déploiement AutoPilot est maintenant disponible pour être attribué à des appareils.

* Les options **Langue (région)** et **Configurer le clavier automatiquement** ne sont disponibles que si vous avez choisi **Auto-déploiement (préversion)** comme **Mode de déploiement**  (Windows 10 Insider Preview Build 17672 ou version ultérieure).


## <a name="assign-an-autopilot-deployment-profile-to-a-device-group"></a>Attribuer un profil de déploiement AutoPilot à un groupe d’appareils

1. Accédez à [Intune dans le portail Azure](https://aka.ms/intuneportal), puis choisissez **Inscription des appareils** > **Inscription Windows** > **Profils de déploiement** > Choisir un profil.
2. Dans le panneau du profil, choisissez **Affectations**. 
3. Choisissez **Sélectionner des groupes** puis, dans le panneau **Sélectionner des groupes**, sélectionnez les groupes auxquels vous souhaitez affecter le profil, puis choisissez **Sélectionner**.

## <a name="edit-an-autopilot-deployment-profile"></a>Modifier un profil de déploiement AutoPilot
Une fois que vous avez créé un profil de déploiement AutoPilot, vous pouvez modifier certaines parties du profil de déploiement.   

1. Dans [Intune du portail Azure](https://aka.ms/intuneportal), choisissez **Inscription des appareils**.
2. Sous **Inscription Windows**, dans la section **Windows AutoPilot**, choisissez **Profils de déploiement**.
3. Sélectionnez le profil que vous voulez modifier.
4. Cliquez sur **Propriétés** sur la gauche pour changer le nom ou la description du profil de déploiement. Cliquez sur **Enregistrer** après avoir apporté les modifications.
5. Cliquez sur **Paramètres** pour apporter des modifications aux paramètres OOBE. Cliquez sur **Enregistrer** après avoir apporté les modifications.

> [!NOTE]
> Les modifications apportées au profil sont appliquées aux appareils qui ont été affectés à ce profil. Cependant, il n’est pas appliqué aux appareils qui sont déjà inscrits à Intune tant que ceux-ci ne sont pas réinitialisés et réinscrits.

## <a name="alerts-for-windows-autopilot-unassigned-devices-----163236---"></a>Alertes pour les appareils non affectés Windows AutoPilot  <!-- 163236 -->
Vous pouvez afficher une alerte pour voir combien d’appareils du programme AutoPilot ne sont pas affectés à des profils de déploiement AutoPilot. Utilisez les informations de l’alerte pour créer des profils et les affecter aux appareils non affectés. Quand vous cliquez sur l’alerte, une liste complète des appareils Windows AutoPilot et des informations détaillées les concernant s’affichent.

Pour afficher les alertes concernant les appareils non affectés, accédez à [Intune dans le portail Azure](https://aka.ms/intuneportal), puis choisissez **Inscription d’appareil** > **Vue d’ensemble** > **Appareils non affectés**.  

## <a name="delete-autopilot-devices"></a>Supprimer des appareils AutoPilot

Vous pouvez supprimer les appareils Windows AutoPilot qui ne sont pas inscrits.

1. Si les appareils sont inscrits dans Intune, vous devez d’abord [les supprimer dans le portail Azure Active Directory](devices-wipe.md#delete-devices-from-the-azure-active-directory-portal).

2. Dans [Intune dans le portail Azure](https://aka.ms/intuneportal), choisissez **Inscription des appareils** > **Inscription Windows** > **Appareils**.

3. Sous **Appareils Windows AutoPilot**, choisissez les appareils à supprimer, puis choisissez **Supprimer**.

4. Confirmez la suppression en choisissant **Oui**. La suppression peut prendre quelques minutes.

## <a name="using-autopilot-in-other-portals"></a>Utilisation d’AutoPilot dans d’autres portails
Si vous n’êtes pas intéressé par la gestion des appareils mobiles, vous pouvez utiliser AutoPilot dans Microsoft Store pour Entreprises, par exemple. Si l’utilisation d’autres portails est une possibilité, nous vous recommandons d’utiliser seulement Intune pour gérer vos déploiements AutoPilot. Si vous utilisez Intune et un autre portail, Intune ne peut pas :
- Afficher les modifications apportées aux profils créés dans Intune, mais modifiés dans un autre portail
- Synchroniser les profils créés dans un autre portail
- Afficher les modifications apportées aux attributions de profils effectuées dans un autre portail
- Synchroniser les attributions de profils effectuées dans un autre portail
- Afficher les modifications apportées à la liste des appareils effectuées dans un autre portail

## <a name="next-steps"></a>Étapes suivantes
Après avoir configuré Windows AutoPilot pour les appareils Windows 10 inscrits, découvrez comment gérer ces appareils. Pour plus d’informations, consultez [Qu’est-ce que la gestion des appareils Microsoft Intune ?](https://docs.microsoft.com/intune/device-management)
