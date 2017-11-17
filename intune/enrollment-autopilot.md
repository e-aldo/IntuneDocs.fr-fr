---
title: "Inscrire des appareils Windows à l’aide du programme Windows AutoPilot Deployment"
description: "Découvrez comment inscrire de nouveaux appareils Windows 10 à l’aide du programme Windows AutoPilot Deployment."
keywords: 
author: dougeby
ms.author: dougeby
manager: angrobe
ms.date: 11/08/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a2dc5594-a373-48dc-ba3d-27aff0c3f944
ms.openlocfilehash: 736eda24e355024e2abadd57206c0f0423e6d4b4
ms.sourcegitcommit: af958afce3070a3044aafea490c8afc55301d9df
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/09/2017
---
# <a name="enroll-windows-devices-using-windows-autopilot-deployment-program"></a>Inscrire des appareils Windows à l’aide du programme Windows AutoPilot Deployment
Le programme Windows AutoPilot Deployment simplifie la configuration des appareils. De nos jours, la création et la maintenance des images de système d’exploitation personnalisées demandent beaucoup de temps. L’application de ces images de système d’exploitation personnalisées à de nouveaux appareils en vue de les préparer pour vos utilisateurs finaux peut être tout aussi longue. Avec Microsoft Intune et AutoPilot, vous pouvez donner de nouveaux appareils à vos utilisateurs finaux sans devoir créer, gérer et appliquer des images de système d’exploitation personnalisées sur les appareils. Quand vous utilisez Intune pour gérer des appareils AutoPilot, vous pouvez gérer des stratégies, des profils, des applications, etc. sur les appareils une fois qu’ils sont inscrits. Pour une vue d’ensemble des avantages, des scénarios et des prérequis, consultez [Vue d’ensemble de Windows AutoPilot](https://docs.microsoft.com/windows/deployment/windows-10-auto-pilot).

## <a name="prerequisites"></a>Prérequis
- [Les appareils doivent être inscrits dans votre organisation](https://docs.microsoft.com/windows/deployment/windows-10-auto-pilot#registering-devices-to-your-organization)
- [Inscription automatique Windows activée](https://docs.microsoft.com/intune-classic/deploy-use/set-up-windows-device-management-with-microsoft-intune#enable-windows-10-automatic-enrollment)
- [Abonnement à Azure Active Directory Premium](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium).<!--&#40;[trial subscription](http://go.microsoft.com/fwlink/?LinkID=816845)&#41;-->

## <a name="synchronize-devices"></a>Synchroniser des appareils
Synchronisez vos appareils inscrits à Intune pour pouvoir les configurer.

1. Connectez-vous à [Azure](https://portal.azure.com/).
2. Choisissez **Autres services** > **Surveillance + Gestion** > **Intune**.
3. Dans le panneau **Intune**, choisissez **Inscription de l’appareil**.
4. Dans le panneau **Inscription Windows**, dans la section **Programme Windows AutoPilot Deployment**, choisissez **Appareils**.
5. Cliquez sur **Synchroniser** pour importer vos appareils inscrits. Un message indique que la synchronisation est en cours.
6. Actualisez la vue pour voir les nouveaux appareils. Le processus peut durer quelques minutes, en fonction du nombre d’appareils à synchroniser.  

## <a name="create-an-autopilot-deployment-profile"></a>Créer un profil de déploiement AutoPilot
Les profils de déploiement AutoPilot sont utilisés pour configurer les appareils AutoPilot.
1. Connectez-vous à [Azure](https://portal.azure.com/). 
2. Choisissez **Autres services** > **Surveillance + Gestion** > **Intune**.
3. Dans le panneau **Intune**, choisissez **Inscription de l’appareil**.
4. Dans le panneau **Inscription Windows**, dans la section **Programme Windows AutoPilot Deployment**, choisissez **Profils de déploiement**.
5. Cliquez sur **Créer un profil**, puis choisissez un nom et une description facultative. 
6. Pour **Type de jonction**, sélectionnez **Joint à Azure AD**.
7. Pour **OOBE (Out-Of-Box Experience)**, configurez les options suivantes et cliquez sur **OK** : 
   - **Paramètres de confidentialité** : choisissez si vous voulez montrer les paramètres de confidentialité aux utilisateurs. 
   - **Contrat de licence utilisateur final (CLUF)** : choisissez s’il faut montrer le CLUF aux utilisateurs.
   - **Type de compte d’utilisateur** : choisissez si le type de compte d’utilisateur est **Administrateur** ou **Standard**.

     > [!Note]    
     > Ce paramètre ne s’applique pas aux comptes d’administrateur général ou d’administrateur d’entreprise. Ces comptes ne peuvent pas correspondre à des utilisateurs standard, car ils donnent accès à toutes les fonctionnalités d’administration dans Azure AD.
8. Cliquez sur **Créer** pour créer le profil. Le profil de déploiement AutoPilot est maintenant disponible pour être attribué à des appareils.
     
> [!Note]    
> Les paramètres suivants sont configurés avec tous les profils de déploiement AutoPilot :
> - Ignorer les pages de configuration de Cortana, OneDrive et de l’inscription OEM
> - Configurer automatiquement pour une entreprise ou un établissement scolaire
> - Expérience de connexion avec une personnalisation d’entreprise ou d’établissement scolaire    

## <a name="alerts-for-windows-autopilot-unassigned-devices-----163236---"></a>Alertes pour les appareils non affectés Windows AutoPilot  <!-- 163236 -->
Vous pouvez afficher une alerte pour les appareils non affectés Windows AutoPilot afin de voir combien d’appareils du programme AutoPilot n’ont pas de profils de déploiement AutoPilot attribués. Utilisez les informations de l’alerte pour créer des profils et les affecter aux appareils non affectés. Quand vous cliquez sur l’alerte, une liste complète des appareils Windows AutoPilot et des informations détaillées les concernant s’affichent. 
1. Connectez-vous à [Azure](https://portal.azure.com/). 
2. Choisissez **Autres services** > **Surveillance + Gestion** > **Intune**.
3. Dans le panneau **Intune**, choisissez **Inscription de l’appareil**.
4. Choisissez **Vue d’ensemble** pour voir l’alerte. Cliquez sur l’alerte pour afficher la liste des appareils AutoPilot.  

## <a name="assign-an-autopilot-deployment-profile"></a>Attribuer un profil de déploiement AutoPilot
Une fois que vous avez créé des profils de déploiement AutoPilot, vous pouvez les attribuer à des appareils sélectionnés.

1. Connectez-vous à [Azure](https://portal.azure.com/). 
2. Choisissez **Autres services** > **Surveillance + Gestion** > **Intune**.
3. Dans le panneau **Intune**, choisissez **Inscription de l’appareil**.
4. Dans le panneau **Inscription Windows**, dans la section **Programme Windows AutoPilot Deployment**, choisissez **Appareils**.
5. Sélectionnez les appareils auxquels vous voulez attribuer le profil de déploiement. Vous pouvez filtrer sur la colonne **État** pour trouver facilement les appareils auxquels aucun profil n’a été attribué. 
6. Cliquez sur **Attribuer un profil**, sélectionnez le profil de déploiement AutoPilot, puis cliquez sur **Attribuer**. Un message indique que l’attribution est en cours.
7. Actualisez la vue pour voir que le profil a été attribué aux appareils. Le processus peut durer quelques minutes, en fonction du nombre d’appareils sélectionnés. 

> [!Note]
> Le nouveau profil est attribué à l’appareil. Cependant, le profil n’est pas appliqué aux appareils déjà inscrits à Intune tant qu’ils ne sont pas réinitialisés et réinscrits.

### <a name="assign-a-different-autopilot-deployment-profile"></a>Attribuer un autre profil de déploiement AutoPilot
Une fois que vous avez attribué un profil de déploiement AutoPilot à un appareil, si vous décidez d’attribuer un autre profil, attribuez le nouveau profil à l’appareil.  

## <a name="edit-an-autopilot-deployment-profile"></a>Modifier un profil de déploiement AutoPilot 
Une fois que vous avez créé un profil de déploiement AutoPilot, vous pouvez modifier certaines parties du profil de déploiement.   
1. Connectez-vous à [Azure](https://portal.azure.com/). 
2. Choisissez **Autres services** > **Surveillance + Gestion** > **Intune**.
3. Dans le panneau **Intune**, choisissez **Inscription de l’appareil**.
4. Dans le panneau **Inscription Windows**, dans la section **Programme Windows AutoPilot Deployment**, choisissez **Profils de déploiement**. 
5. Sélectionnez le profil que vous voulez modifier. 
6. Cliquez sur **Propriétés** sur la gauche pour changer le nom ou la description du profil de déploiement. Cliquez sur **Enregistrer** après avoir apporté les modifications. 
7. Cliquez sur **Paramètres** pour apporter des modifications aux paramètres OOBE. Cliquez sur **Enregistrer** après avoir apporté les modifications. 

> [!NOTE]
> Le profil mis à jour est attribué aux appareils. Cependant, il n’est pas appliqué aux appareils qui sont déjà inscrits à Intune tant que ceux-ci ne sont pas réinitialisés et réinscrits. 

## <a name="using-autopilot-in-other-portals"></a>Utilisation d’AutoPilot dans d’autres portails
Si vous n’êtes pas intéressé par la gestion des appareils mobiles, vous avez la possibilité d’utiliser AutoPilot par exemple dans Microsoft Store pour Entreprises. Si l’utilisation d’autres portails est une possibilité, nous vous recommandons d’utiliser seulement Intune pour gérer vos déploiements AutoPilot. Si vous utilisez Intune et un autre portail, Intune ne peut pas :
- Afficher les modifications apportées aux profils créés dans Intune, mais modifiés dans un autre portail
- Synchroniser les profils créés dans un autre portail
- Afficher les modifications apportées aux attributions de profils effectuées dans un autre portail
- Synchroniser les attributions de profils effectuées dans un autre portail

## <a name="next-steps"></a>Étapes suivantes
Après avoir configuré Windows AutoPilot pour les appareils Windows 10 inscrits, découvrez comment gérer ces appareils. Pour plus d’informations, consultez [Qu’est-ce que la gestion des appareils Microsoft Intune ?](https://docs.microsoft.com/intune/device-management)