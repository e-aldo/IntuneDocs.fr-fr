---
title: Inscrire des appareils Android dans Intune
titlesuffix: Microsoft Intune
description: "Découvrez comment inscrire des appareils Android dans Intune."
keywords: 
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 01/31/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f276d98c-b077-452a-8835-41919d674db5
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0a72199c9e38f4f4d9d7317469eea2e6254efee7
ms.sourcegitcommit: aafed032492c1b5861d7097a335f9bbb29ce3221
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/02/2018
---
# <a name="enroll-android-devices"></a>Inscrire des appareils Android

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

En votre qualité d’administrateur Intune, vous pouvez gérer des appareils Android, notamment des appareils Samsung Knox Standard. Vous pouvez également gérer le profil professionnel [Appareils Android for Work](#enable-enrollment-of-android-for-work-devices).

Les appareils qui exécutent Samsung Knox Standard sont pris en charge pour la gestion des utilisateurs multiples par Intune. Cela signifie que les utilisateurs finaux peuvent se connecter et se déconnecter d’un appareil avec leurs informations d’identification Azure AD. L’appareil est géré de manière centralisée, qu’il soit en cours d’utilisation ou non. Quand les utilisateurs se connectent, ils ont accès aux applications et les éventuelles stratégies sont appliquées à ces applications. Quand les utilisateurs se déconnectent, toutes les données d’application sont effacées.

## <a name="prerequisite"></a>Prérequis

Pour préparer la gestion des appareils mobiles, vous devez définir l’autorité de gestion des appareils mobiles (MDM) sur **Microsoft Intune**. Consultez la page [Configurer l’autorité MDM](mdm-authority-set.md) pour obtenir des instructions. Cet élément ne se définit qu’une seule fois, quand vous configurez pour la première fois Intune pour la gestion des appareils mobiles.

## <a name="set-up-android-enrollment"></a>Configurer l’inscription Android

Par défaut, Intune autorise l’inscription des appareils Android et Samsung Knox Standard.

Pour empêcher l’inscription des appareils Android, ou uniquement des appareils personnels Android, consultez [Définir des restrictions de type d’appareil](enrollment-restrictions-set.md).

Pour activer la gestion des appareils, vos utilisateurs doivent inscrire leurs appareils en téléchargeant l’application Portail d’entreprise Intune (disponible à partir de Google Play), puis en ouvrant l’application et en suivant les invites. Une fois que les appareils Android sont gérés, vous pouvez [affecter des stratégies de conformité](compliance-policy-create-android.md), [gérer les applications](app-management.md), et bien plus encore.

## <a name="enable-enrollment-of-android-for-work-devices"></a>Activer l’inscription des appareils Android for Work

Pour activer la gestion du profil professionnel sur les appareils qui [prennent en charge Android for Work](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012), vous devez ajouter une liaison Android for Work à Intune. Si vous voulez inscrire des appareils dans Android for Work, mais que ces appareils étaient auparavant inscrits comme appareils Android ordinaires, vous devez désinscrire les appareils, puis les réinscrire.

Si vous inscrivez des appareils Android for Work à l’aide d’un compte de [Gestionnaire d’inscription d’appareil](device-enrollment-manager-enroll.md), il existe une limite de 10 appareils pouvant être inscrits par compte.

## <a name="add-android-for-work-binding-for-intune"></a>Ajouter une liaison Android for Work pour Intune

> [!NOTE]
> En raison de l’interaction entre les domaines Google et Microsoft, cette étape peut nécessiter un réglage des paramètres de votre navigateur.  Vérifiez que « portal.azure.com » et « play.google.com » sont dans la même zone de sécurité de votre navigateur.

1. **Configurer la gestion des appareils mobiles Intune**<br>
Si vous ne l’avez pas déjà fait, préparez la gestion des appareils mobiles en définissant **Microsoft Intune** comme [autorité de gestion des appareils mobiles](mdm-authority-set.md).
2. **Configurer une liaison Android for Work**<br>
    En tant qu’administrateur Intune, dans le portail Azure, choisissez **Plus de services** > **Surveillance + gestion** > **Intune**.

   a. Dans le panneau **Intune**, choisissez **Inscription de l’appareil** > **Inscription d’Android for Work**, puis choisissez **Configurer** pour ouvrir le site web Android for Work de Google Play. Le site web s’ouvre dans un nouvel onglet dans votre navigateur.
   ![Écran d’inscription d’Android for Work](./media/android-work-bind.png)

   b. **Se connecter à Google**<br>
   Dans la page de connexion de Google, entrez le compte Google à associer à toutes les tâches de gestion Android for Work pour ce client. Il s’agit du compte Google partagé par les administrateurs informatiques de votre organisation pour gérer et publier des applications dans la console Play for Work. Vous pouvez utiliser un compte Google existant ou en créer un.  Le compte que vous choisissez ne doit pas être associé à un domaine G Suite.

   c. **Fournir les détails de l’organisation**<br>
   Fournissez le nom de votre société comme **Nom d’organisation**. Pour **Enterprise mobility management (EMM) provider** (Fournisseur de gestion de la mobilité d’entreprise), **Microsoft Intune** doit être affiché. Acceptez le contrat Android for Work, puis choisissez **Confirmer**. Votre demande va être traitée.

## <a name="specify-android-for-work-enrollment-settings"></a>Spécifier les paramètres d’inscription Android for Work
Android for Work n’est pris en charge que sur certains appareils Android. Consultez la rubrique de Google [Conditions requises par Android for Work](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012%20style=%22target=new_window%22). Tout appareil qui prend en charge Android for Work prend également en charge la gestion Android conventionnelle. Intune vous permet de spécifier la façon dont les appareils qui prennent en charge Android for Work doivent être gérés dans [Restrictions d’inscription](enrollment-restrictions-set.md).

- **Bloquer (défini par défaut)** : Tous les appareils Android, notamment ceux qui prennent en charge Android for Work, sont inscrits comme des appareils Android conventionnels.
- **Autoriser** : Tous les appareils qui prennent en charge Android for Work sont inscrits comme des appareils Android for Work. Tout appareil Android qui ne prend pas en charge Android for Work est inscrit comme appareil Android conventionnel.

## <a name="approve-the-company-portal-app-in-the-managed-google-play-store"></a>Approuver l’application Portail d’entreprise dans le Google Play Store géré
Vous devez approuver l’application Portail d’entreprise pour Android sur le Google Play Store géré pour garantir qu’elle reçoit les mises à jour automatiques d’applications. Si vous ne l’approuvez pas, le portail d’entreprise finit par devenir obsolète et risque de ne pas recevoir les correctifs de bogues importants ou les nouvelles fonctionnalités publiés par Microsoft.

Pour approuver le portail d’entreprise Intune, effectuez les étapes suivantes :

1.  Accédez à l’application Portail d’entreprise sur le [Google Play Store géré](https://play.google.com/work/apps/details?id=com.microsoft.windowsintune.companyportal).
2.  Connectez-vous au Google Play Store géré avec le même compte Google que celui utilisé pour configurer la liaison pour Android for Work.
3.  Cliquez sur **Approuver** ; une nouvelle boîte de dialogue s’ouvre.
4.  Vérifiez les autorisations dans cette boîte de dialogue, puis cliquez sur **Approuver**. Vous devez affecter ces autorisations afin de permettre à l’application Portail d’entreprise de gérer le profil professionnel sur l’appareil.
5.  Sélectionnez **Keep approved when app requests new permissions** (Laisser approuvé quand l’application demande de nouvelles autorisations), puis cliquez sur **Enregistrer.**

<!--  ## Next steps for Android for Work
After configuring the Android for Work binding and settings, you can do the following:
- [Deploy Android for Work apps](android-for-work-apps.md)
- [Add Android for Work configuration policies](android-for-work-policy-settings-in-microsoft-intune.md)  -->

## <a name="tell-your-users-how-to-enroll-their-devices-to-access-company-resources"></a>Indiquez à vos utilisateurs comment inscrire leurs appareils de manière à ce qu’ils puissent accéder aux ressources de l’entreprise

Demandez à vos utilisateurs d’accéder à Google Play pour télécharger l’application Portail d’entreprise Intune, puis d’ouvrir l’application et de suivre les invites pour inscrire leur appareil. L’application guide les utilisateurs tout au long du processus d’inscription en leur expliquant ce qu’ils peuvent attendre, et ce que les administrateurs informatiques peuvent et ne peuvent pas voir sur leurs appareils.

Vous pouvez également leur envoyer un lien vers les étapes d’inscription en ligne : [Inscrire un appareil Android dans Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android).

Pour plus d’informations sur les autres tâches de l’utilisateur, consultez les articles suivants :

- [Ressources concernant l’expérience utilisateur final avec Microsoft Intune](end-user-educate.md)
- [Utilisation de votre appareil Android avec Intune](https://docs.microsoft.com/intune-user-help/using-your-android-device-with-intune)

## <a name="unbind-your-android-for-work-administrative-account"></a>Séparer votre compte administratif Android for Work

Vous pouvez désactiver l’inscription et la gestion Android for Work. Un clic sur **Séparer** dans la console d’administration Intune annule l’inscription de tous les appareils Android for Work inscrits. Cela supprime également la relation entre le compte Android for Work et Intune.

### <a name="to-unbind-an-android-for-work-account"></a>Pour séparer un compte Android for Work

1. **Séparer la liaison Android for Work**<br>
    En tant qu’administrateur Intune, dans le portail Azure, choisissez **Plus de services** > **Surveillance + gestion** > **Intune**.  Dans le panneau **Intune**, choisissez **Inscription de l’appareil****Inscription d’Android for Work**, puis **Séparer**.

2. **Confirmer la suppression de la liaison Android for Work**<br>
  Choisissez **Oui** pour supprimer la liaison et désinscrire tous les appareils Android for Work d’Intune.
