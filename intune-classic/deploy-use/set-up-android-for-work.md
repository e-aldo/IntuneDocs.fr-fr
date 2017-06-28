---
title: Configurer Android for Work
description: Activez la gestion des appareils mobiles pour les appareils Android for Work avec Microsoft Intune.
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/29/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b2fdcea9-9ad7-4d73-88e2-854b7a774bb2
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: df3c42d8b52d1a01ddab82727e707639d5f77c16
ms.openlocfilehash: 852997044cef22901e8133d76f327e98b2a1ee72
ms.contentlocale: fr-fr
ms.lasthandoff: 06/08/2017


---

# <a name="enable-enrollment-of-android-for-work-devices"></a>Activer l’inscription des appareils Android for Work

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Pour activer la gestion des appareils Android for Work, vous devez ajouter une liaison Android for Work à Intune. Pour inscrire des appareils qui prennent en charge Android for Work, mais qui étaient inscrits en tant qu’appareils Android ordinaires, vous devez désinscrire les appareils, puis les réinscrire.

## <a name="add-android-for-work-binding-for-intune"></a>Ajouter une liaison Android for Work à Intune

1. **Configurer Intune**<br>
Si vous ne l’avez pas déjà fait, préparez la gestion des appareils mobiles en [définissant l’autorité de gestion des appareils mobiles](/intune-classic/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-8#enable-device-enrollment) sur **Microsoft Intune** et en configurant la gestion des appareils mobiles.

2. **Configurer une liaison Android for Work**<br>
    En tant qu’administrateur d’Intune, ouvrez la [Console d’administration Microsoft Intune](https://manage.microsoft.com), accédez à **Administration** &gt; **Gestion des appareils mobiles** &gt; **Android for Work**, puis cliquez sur **Configurer** pour ouvrir le site web Android for Work de Google Play. Ce dernier s’ouvre dans un nouvel onglet de votre navigateur.

3. **Se connecter à Google**<br>
   Dans la page de connexion de Google, entrez le compte Google à associer à toutes les tâches de gestion Android for Work pour ce client. Il s’agit du compte Google partagé par les administrateurs informatiques de votre organisation pour gérer et publier des applications dans la console Play for Work.

4. **Fournir les détails de l’organisation**<br>
   Fournissez le nom de votre société en guise de **nom d’organisation**. Pour **Enterprise mobility management (EMM) provider** (Fournisseur de gestion de la mobilité d’entreprise), *Microsoft Intune* doit être affiché. Acceptez le contrat Android for Work, puis cliquez sur **Confirmer**. Votre demande va être traitée.

## <a name="specify-android-for-work-enrollment-settings"></a>Spécifier les paramètres d’inscription Android for Work
   Android for Work n’est pris en charge que sur certains appareils Android. Consultez la rubrique de Google [Conditions requises par Android for Work](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012 style="target=new_window").  Tout appareil qui prend en charge Android for Work prend également en charge la gestion Android conventionnelle.  Intune vous permet de spécifier comment les appareils prenant en charge Android for Work doivent être gérés :

   - **Gérer tous les appareils comme des appareils Android** : tous les appareils Android, notamment ceux qui prennent en charge Android for Work, sont inscrits comme appareils Android conventionnels.
   - **Gérer les appareils pris en charge comme des appareils Android for Work** : tous les appareils qui prennent en charge Android for Work sont inscrits comme appareils Android for Work. Tout appareil Android qui ne prend pas en charge Android for Work est inscrit comme appareil Android conventionnel.
   - **Gérer les appareils pris en charge des utilisateurs de ces groupes d’utilisateurs uniquement comme des appareils Android for Work** : vous permet de cibler la gestion Android for Work sur un ensemble limité d’utilisateurs. Seuls les membres des groupes sélectionnés qui inscrivent un appareil prenant en charge Android for Work sont inscrits comme appareils Android for Work. Tous les autres sont inscrits comme appareils Android. Cette option est utile lors des phases pilotes Android for Work.

## <a name="next-steps-for-android-for-work"></a>Prochaines étapes pour Android for Work
Après avoir configuré la liaison et les paramètres Android for Work, vous pouvez effectuer les opérations suivantes :
- [Déployer des applications Android for Work](android-for-work-apps.md)
- [Ajouter des stratégies de configuration Android for Work](android-for-work-policy-settings-in-microsoft-intune.md)

## <a name="unbinding-your-android-for-work-administrative-account"></a>Séparation de votre compte administratif Android for Work

Vous pouvez désactiver l’inscription et la gestion Android for Work. En cliquant sur **Séparer** dans la console d’administration Intune, vous supprimez tous les appareils Android for Work inscrits, ainsi que la relation entre le compte Android for Work et Intune.

### <a name="how-to-unbind-an-android-for-work-account"></a>Comment séparer un compte Android for Work

1. **Séparer la liaison Android for Work**<br>
    En tant qu’utilisateur administratif, ouvrez la [console d’administration Microsoft Intune](https://manage.microsoft.com), accédez à **Administration** &gt; **Gestion des appareils mobiles** &gt; **Android for Work**, puis cliquez sur **Séparer**.

2. **Confirmer la suppression de la liaison Android for Work**<br>
  Cliquez sur **Oui** pour supprimer la liaison et désinscrire tous les appareils Android for Work d’Intune.

