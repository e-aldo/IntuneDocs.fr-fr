---
title: Inscrire des appareils Android dans Intune | Microsoft Docs
titlesuffix: Azure portal
description: "Apprenez à inscrire des appareils Android dans Intune."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f276d98c-b077-452a-8835-41919d674db5
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: be998ba3282665d4aff7873b16bb1187edce7693
ms.sourcegitcommit: 94d3d86f8ae9f82a9872384bbaae53580036a4ff
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/01/2017
---
# <a name="enroll-android-devices"></a>Inscrire des appareils Android

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

En votre qualité d’administrateur Intune, Intune vous permet de gérer des appareils Android, notamment des appareils Samsung Knox Standard. Vous pouvez également gérer le profil professionnel sur les appareils [Android for Work](#enable-enrollment-of-android-for-work-devices).

Les appareils qui exécutent Samsung KNOX Standard sont pris en charge pour la gestion des utilisateurs multiples par Intune. Cela signifie que les utilisateurs finaux peuvent se connecter et se déconnecter de l’appareil avec leurs informations d’identification AD, et que l’appareil est géré de façon centralisée qu’il soit en cours d’utilisation ou non. Quand les utilisateurs finaux se connectent, ils ont accès aux applications et les éventuelles stratégies sont appliquées à ces applications. Quand les utilisateurs se déconnectent, toutes les données d’application sont effacées.

## <a name="prerequisite"></a>Prérequis

Vous devez définir l’autorité MDM sur **Microsoft Intune** pour préparer la gestion des appareils mobiles. Consultez la page [Configurer l’autorité MDM](mdm-authority-set.md) pour obtenir des instructions. Cet élément ne se définit qu’une seule fois, quand vous configurez pour la première fois Intune pour la gestion des appareils mobiles.

## <a name="set-up-android-enrollment"></a>Configurer l’inscription Android

Par défaut, Intune autorise l’inscription des appareils Android et Samsung Knox Standard.

Pour empêcher l’inscription des appareils Android, ou uniquement des appareils personnels Android, consultez [Définir des restrictions de type d’appareil](enrollment-restrictions-set.md).

Pour activer la gestion des appareils, vos utilisateurs doivent inscrire leurs appareils en téléchargeant l’application Portail d’entreprise Intune, qui est disponible à partir de Google Play, puis en ouvrant l’application et en suivant les invites d’inscription. Une fois que les appareils Android sont gérés, vous pouvez [affecter des stratégies de conformité](compliance-policy-create-android.md), [gérer les applications](app-management.md), et bien plus encore.

## <a name="enable-enrollment-of-android-for-work-devices"></a>Activer l’inscription des appareils Android for Work

Pour activer la gestion du profil professionnel sur les appareils qui [prennent en charge Android for Work](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012), vous devez ajouter une liaison Android for Work à Intune. Pour inscrire des appareils qui prennent en charge Android for Work, mais qui étaient inscrits en tant qu’appareils Android ordinaires, vous devez désinscrire les appareils, puis les réinscrire.

## <a name="add-android-for-work-binding-for-intune"></a>Ajouter une liaison Android for Work à Intune

1. **Configurer la gestion des appareils mobiles Intune**<br>
Si vous ne l’avez pas déjà fait, préparez la gestion des appareils mobiles en définissant **Microsoft Intune** comme [autorité de gestion des appareils mobiles](mdm-authority-set.md).
2. **Configurer une liaison Android for Work**<br>
    En tant qu’administrateur Intune, dans le portail Azure, choisissez **Plus de services** > **Surveillance + gestion** > **Intune**.

    1. Dans le panneau **Intune**, choisissez **Inscription de l’appareil**, > **Inscription d’Android for Work**, puis cliquez sur **Configurer** pour ouvrir le site web Android for Work de Google Play. Ce dernier s’ouvre dans un nouvel onglet de votre navigateur.
  ![Capture d’écran montrant le lien vers Configurer la liaison Android for Work](./media/android-work-bind.png)

    2. **Se connecter à Google**<br>
   Dans la page de connexion de Google, entrez le compte Google à associer à toutes les tâches de gestion Android for Work pour ce client. Il s’agit du compte Google partagé par les administrateurs informatiques de votre organisation pour gérer et publier des applications dans la console Play for Work.

    3. **Fournir les détails de l’organisation**<br>
   Fournissez le nom de votre société en guise de **nom d’organisation**. Pour **Enterprise mobility management (EMM) provider** (Fournisseur de gestion de la mobilité d’entreprise), *Microsoft Intune* doit être affiché. Acceptez le contrat Android for Work, puis cliquez sur **Confirmer**. Votre demande va être traitée.

## <a name="specify-android-for-work-enrollment-settings"></a>Spécifier les paramètres d’inscription Android for Work
   Android for Work n’est pris en charge que sur certains appareils Android. Consultez la rubrique de Google [Conditions requises par Android for Work](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012 style="target=new_window"). Tout appareil qui prend en charge Android for Work prend également en charge la gestion Android conventionnelle.  Intune vous permet de spécifier comment les appareils prenant en charge Android for Work doivent être gérés :

   - **Gérer tous les appareils comme des appareils Android** : tous les appareils Android, notamment ceux qui prennent en charge Android for Work, sont inscrits comme appareils Android conventionnels.
   - **Gérer les appareils pris en charge comme des appareils Android for Work** : tous les appareils qui prennent en charge Android for Work sont inscrits comme appareils Android for Work. Tout appareil Android qui ne prend pas en charge Android for Work est inscrit comme appareil Android conventionnel.
   - **Gérer les appareils pris en charge des utilisateurs de ces groupes d’utilisateurs uniquement comme des appareils Android for Work** : vous permet de cibler la gestion Android for Work sur un ensemble limité d’utilisateurs. Seuls les membres des groupes sélectionnés qui inscrivent un appareil prenant en charge Android for Work sont inscrits comme appareils Android for Work. Tous les autres sont inscrits comme appareils Android. Cette option est utile lors des phases pilotes Android for Work.

<!--  ## Next steps for Android for Work
After configuring the Android for Work binding and settings, you can do the following:
- [Deploy Android for Work apps](android-for-work-apps.md)
- [Add Android for Work configuration policies](android-for-work-policy-settings-in-microsoft-intune.md)  -->

## <a name="tell-your-users-how-to-enroll-their-devices-to-access-company-resources"></a>Indiquez à vos utilisateurs comment inscrire leurs appareils de manière à ce qu’ils puissent accéder aux ressources de l’entreprise

Vous devez indiquer à vos utilisateurs finaux d’accéder à Google Play pour télécharger l’application Portail d’entreprise Intune, puis d’ouvrir l’application et de suivre les invites pour inscrire leur appareil. L’application guide les utilisateurs tout au long du processus d’inscription en leur expliquant ce qu’ils peuvent attendre, et ce que les administrateurs informatiques peuvent et ne peuvent pas voir sur leurs appareils.

Vous pouvez également leur envoyer un lien vers les étapes d’inscription en ligne : [Inscrire un appareil Android dans Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android).

Pour plus d’informations sur les autres tâches de l’utilisateur final, consultez les articles suivants :

- [Ressources concernant l’expérience utilisateur final avec Microsoft Intune](end-user-educate.md)
- [Utilisation de votre appareil Android avec Intune](https://docs.microsoft.com/intune-user-help/using-your-android-device-with-intune)

## <a name="unbinding-your-android-for-work-administrative-account"></a>Séparation de votre compte administratif Android for Work

Vous pouvez désactiver l’inscription et la gestion Android for Work. En cliquant sur **Séparer** dans la console d’administration Intune, vous supprimez tous les appareils Android for Work inscrits, ainsi que la relation entre le compte Android for Work et Intune.

### <a name="how-to-unbind-an-android-for-work-account"></a>Comment séparer un compte Android for Work

1. **Séparer la liaison Android for Work**<br>
    En tant qu’administrateur Intune, dans le portail Azure, choisissez **Plus de services** > **Surveillance + gestion** > **Intune**.  Dans le panneau **Intune**, choisissez **Inscription de l’appareil**, > **Inscription d’Android for Work**, puis cliquez sur **Annuler la liaison**.

2. **Confirmer la suppression de la liaison Android for Work**<br>
  Cliquez sur **Oui** pour supprimer la liaison et désinscrire tous les appareils Android for Work d’Intune.
