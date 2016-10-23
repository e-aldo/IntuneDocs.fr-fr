---
title: Configuration de la gestion Android for Work | Microsoft Intune
description: Activez la gestion des appareils mobiles pour les appareils Android for Work avec Microsoft Intune.
keywords: 
author: NathBarn
manager: angrobe
ms.date: 10/12/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b2fdcea9-9ad7-4d73-88e2-854b7a774bb2
translationtype: Human Translation
ms.sourcegitcommit: 519b66c94f3d056e060ed11e1a3d7d6d118a94fb
ms.openlocfilehash: 5f48303dd28627f961f8c2cfd38f8977354e2724


---

# Activer l’inscription des appareils Android for Work

Pour activer la gestion des appareils Android for Work, vous devez ajouter une liaison Android for Work à Intune. Pour inscrire des appareils qui prennent en charge Android for Work, mais qui étaient inscrits comme des appareils Android ordinaires, les appareils doivent être désinscrits, puis réinscrits.

## Ajouter une liaison Android for Work à Intune

1. **Configurer Intune**<br>
Si vous ne l’avez pas déjà fait, préparez la gestion des appareils mobiles en [définissant l’autorité de gestion des appareils mobiles](prerequisites-for-enrollment.md#set-mobile-device-management-authority) sur **Microsoft Intune** et en configurant la gestion des appareils mobiles.

2. **Configurer une liaison Android for Work**<br>
    En tant qu’utilisateur administratif, ouvrez la [console d’administration Microsoft Intune](http://manage.microsoft.com), accédez à **Administration** &gt; **Gestion des appareils mobiles** &gt; **Android for Work**, puis cliquez sur **Configurer** pour ouvrir le site web Android for Work de Google Play. Ce dernier s’ouvre dans un nouvel onglet de votre navigateur.

3. **Se connecter à Google**<br>
   Dans la page de connexion de Google, entrez le compte Google à associer à toutes les tâches de gestion Android for Work pour ce client. Il peut s’agir d’un compte Google partagé entre les administrateurs qui gèrent Intune. Il s’agit du compte Google utilisé par votre organisation pour gérer et publier des applications dans la console Play for Work.

4. **Fournir les détails de l’organisation**<br>
   Fournissez le nom de votre société en guise de **nom d’organisation**. Pour **Enterprise mobility management (EMM) provider** (Fournisseur de gestion de la mobilité d’entreprise), *Microsoft Intune* doit être affiché. Acceptez le contrat Android for Work, puis cliquez sur **Confirmer**. Votre demande va être traitée.

## Spécifier les paramètres d’inscription Android for Work
   Android for Work n’est pris en charge que sur certains appareils Android. Consultez la rubrique de Google [Conditions requises par Android for Work](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012 style="target=new_window").  Tout appareil qui prend en charge Android for Work prend également en charge la gestion Android conventionnelle.  Intune vous permet de spécifier comment les appareils prenant en charge Android for Work doivent être gérés :

   - **Gérer tous les appareils comme des appareils Android** : (désactivé) tous les appareils Android, notamment ceux qui prennent en charge Android for Work, sont inscrits comme appareils Android conventionnels.
   - **Gérer les appareils pris en charge comme des appareils Android for Work** : (activé) tous les appareils qui prennent en charge Android for Work sont inscrits comme appareils Android for Work. Tout appareil Android qui ne prend pas en charge Android for Work est inscrit comme appareil Android conventionnel.
   - **Gérer les appareils pris en charge des utilisateurs de ces groupes d’utilisateurs uniquement comme des appareils Android for Work** : (test) vous permet de cibler la gestion Android for Work sur un ensemble limité d’utilisateurs. Seuls les membres des groupes sélectionnés qui inscrivent un appareil prenant en charge Android for Work sont inscrits comme appareils Android for Work. Tous les autres sont inscrits comme appareils Android.

## Prochaines étapes pour Android for Work
Après avoir configuré la liaison et les paramètres Android for Work, vous pouvez effectuer les opérations suivantes :
- [Déployer des applications Android for Work](android-for-work-apps.md)
- [Ajouter des stratégies de configuration Android for Work](android-for-work-policy-settings-in-microsoft-intune.md)

## Séparation de votre compte administratif Android for Work

Vous pouvez désactiver l’inscription et la gestion Android for Work. Cliquer sur **Séparer** supprime tout appareil Android for Work de l’inscription, ainsi que la relation entre le compte Android for Work et Intune.

### Comment séparer un compte Android for Work

1. **Séparer la liaison Android for Work**<br>
    En tant qu’utilisateur administratif, ouvrez la [console d’administration Microsoft Intune](http://manage.microsoft.com), accédez à **Administration** &gt; **Gestion des appareils mobiles** &gt; **Android for Work**, puis cliquez sur **Séparer**.

2. **Confirmer la suppression de la liaison Android for Work**<br>
  Cliquez sur **Oui** pour supprimer la liaison et désinscrire tous les appareils Android for Work d’Intune.



<!--HONumber=Oct16_HO2-->


