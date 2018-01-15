---
title: "Inscription avec le Gestionnaire d’inscription d’appareil"
description: "Le compte de gestionnaire d’inscription d’appareil peut gérer un grand nombre d’appareils mobiles d’entreprise partagés avec un seul compte d’utilisateur."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 01/03/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a23abc61-69ed-44f1-9b71-b86aefc6ba03
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: b55c5d588eb366487a9e1594a46f88551e0b6ee2
ms.sourcegitcommit: 5fd17a57989c6da3d325ed2e0018ce16fe20bb79
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/04/2018
---
# <a name="enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune"></a>Inscrire des appareils d’entreprise avec le gestionnaire d’inscription d’appareil dans Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Les organisations peuvent utiliser Intune pour gérer un grand nombre d'appareils mobiles avec un seul compte d’utilisateur. Le compte du *gestionnaire d’inscription d’appareil* est un compte d’utilisateur spécial qui peut inscrire jusqu’à 1 000 appareils. Vous ajoutez des utilisateurs existants au compte de gestionnaire d’inscription d’appareil afin qu’ils puissent bénéficier des fonctionnalités associées. Chaque appareil inscrit utilise une seule licence. Nous vous recommandons d’utiliser les appareils inscrits avec ce compte comme appareils partagés (c’est-à-dire, sans affinité utilisateur) plutôt que comme appareils personnels (« BYOD »).  

Les utilisateurs doivent figurer dans le portail Azure pour être ajoutés comme gestionnaires d’inscription d’appareil. Pour une sécurité optimale, l’utilisateur du gestionnaire d’inscription d’appareil ne doit pas être également un administrateur Intune.

>[!NOTE]
>La méthode d’inscription via le gestionnaire d’inscription d’appareil ne peut pas être utilisée avec l’[Assistant de configuration Apple Configurator](ios-setup-assistant-enrollment-in-microsoft-intune.md) ou l[’inscription directe](ios-direct-enrollment-in-microsoft-intune.md), l’inscription macOS, ni avec la [méthode d’inscription DEP](ios-device-enrollment-program-in-microsoft-intune.md).

## <a name="example-of-a-device-enrollment-manager-scenario"></a>Exemple d’un scénario faisant intervenir un gestionnaire d’inscription d’appareil

Un restaurant souhaite fournir 50 tablettes à son personnel de service et des moniteurs de commande à son personnel de cuisine. Les employés n’ont jamais besoin d’accéder aux données de l’entreprise ou de se connecter comme utilisateurs. L’administrateur Intune crée un compte de gestionnaire d’inscription d’appareil et lui ajoute un superviseur de restaurant, ce qui a pour effet d’attribuer à ce superviseur les fonctionnalités associées. Le superviseur peut désormais inscrire les 50 tablettes en utilisant les informations d’identification du gestionnaire d’inscription d’appareil.

Seuls les utilisateurs existants dans la console Intune peuvent être gestionnaires d'inscription d'appareil. Le gestionnaire d’inscription d’appareil ne peut pas être administrateur Intune.

L’utilisateur du gestionnaire d’inscription d’appareil peut :

-   Inscrire jusqu’à 1 000 appareils dans Intune
-   Accéder au portail d’entreprise pour obtenir des applications d’entreprise
-   Configurer l’accès aux données de l’entreprise en déployant des applications spécifiques aux rôles sur les tablettes

## <a name="limitations-of-devices-that-are-enrolled-with-a-dem-account"></a>Limitations des appareils qui sont inscrits avec un compte de gestionnaire d’inscription d’appareil

Les appareils inscrits avec un compte de gestionnaire d’inscription d’appareil ont les limitations suivantes :

  - Il n’existe aucun « utilisateur » propre à l’appareil. Par conséquent, aucun accès aux données d’entreprise ou à la messagerie n’est possible. Toutefois, le VPN, par exemple, peut toujours être utilisé pour fournir aux applications d’appareil un accès aux données.

  - Il n’y a pas d’accès conditionnel, car il s’agit de scénarios par utilisateur.

  - L’utilisateur du gestionnaire d’inscription d’appareil ne peut pas annuler l’inscription des appareils inscrits auprès du gestionnaire d’inscription d’appareil sur l’appareil lui-même à l’aide du portail d’entreprise. L’administrateur Intune a cette capacité, mais pas l’utilisateur du gestionnaire d’inscription d’appareil.

  - Seul l’appareil local s’affiche dans l’application Portail d’entreprise ou le site web.

  - Les utilisateurs ne peuvent pas utiliser les applications du programme d’achat en volume (VPP) Apple en raison des critères des identifiants Apple par utilisateur pour la gestion des applications.

  - (iOS uniquement) Si vous utilisez le gestionnaire d’inscription d’appareil pour inscrire des appareils iOS, vous ne pouvez pas utiliser Apple Configurator ni le programme d’inscription des appareils Apple pour inscrire des appareils.

> [!NOTE]
> Pour déployer des applications d’entreprise sur des appareils gérés par le gestionnaire d’inscription d’appareil, déployez l’application Portail d’entreprise comme **Installation requise** sur le compte d’utilisateur du gestionnaire d’inscription d’appareil.
> Pour améliorer les performances, l’affichage de l’application Portail d’entreprise sur un appareil de gestionnaire d’inscription d’appareil affiche uniquement les appareils locaux. La gestion à distance d’autres appareils DEM est possible uniquement à partir de la console d’administration Intune.


## <a name="add-a-device-enrollment-manager"></a>Ajouter un gestionnaire d’inscription d’appareil

1.  Assurez-vous que l’utilisateur que vous souhaitez ajouter au compte de gestionnaire d’inscription d’appareil existe déjà. Si vous devez ajouter l’utilisateur, connectez-vous au [portail Office 365](https://go.microsoft.com/fwlink/p/?LinkId=698854) et suivez les étapes dans [Ajouter des utilisateurs individuellement ou en bloc à Office 365](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).

2.  Connectez-vous à la [console d’administration Microsoft Intune](https://manage.microsoft.com) avec vos informations d’identification d’administrateur.

3.  Dans le volet de navigation, choisissez **Admin**, puis accédez à **Gestion des administrateurs** et sélectionnez **Gestionnaires d’inscription d’appareil**. La page **Gestionnaires d’inscription d’appareil** s’ouvre.

4.  Choisissez **Ajouter...** La boîte de dialogue **Ajouter un gestionnaire d'inscription d'appareil** s'ouvre.

5.  Entrez l’**ID d’utilisateur** du compte Intune, puis choisissez **OK**.

    À présent, l’utilisateur du gestionnaire d’inscription d’appareil peut inscrire des appareils mobiles en suivant la même procédure qu’un utilisateur final pour un scénario BYOD dans le portail d’entreprise. L’utilisateur final du gestionnaire peut installer l’application Portail d’entreprise et inscrire l’appareil à l’aide de ses informations d’identification DEM sur 1 000 appareils au maximum. Pour connaître les étapes d’inscription de l’utilisateur final pour chaque plateforme, consultez :

  - [Inscrire un appareil iOS dans Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios)
  - [Inscrire votre appareil macOS dans Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-macos)
  - [Inscrire un appareil Android dans Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android)
  - [Inscrire un appareil Windows dans Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-windows)

## <a name="delete-a-device-enrollment-manager-from-intune"></a>Supprimer un gestionnaire d'inscription d'appareil d'Intune

1.  Connectez-vous au [portail de compte Microsoft Intune](https://manage.microsoft.com) avec vos informations d’identification d’administrateur.

2.  Dans le volet de navigation, choisissez **Admin**, puis accédez à **Gestion des administrateurs** et sélectionnez **Gestionnaires d’inscription d’appareil**. La page **Gestionnaires d’inscription d’appareil** s’ouvre.

3.  Sélectionnez l’**Utilisateur** du gestionnaire d’inscription d’appareil à supprimer, puis choisissez **Supprimer**. Cet utilisateur ne sera pas supprimé d’Intune, et les appareils qu’il gère resteront inscrits dans Intune. La suppression d'un gestionnaire d'inscription d'appareil empêche l'utilisateur correspondant d'inscrire plusieurs appareils dans Intune.

4.  Choisissez **Oui** pour confirmer la suppression du gestionnaire d’inscription d’appareil.

La suppression d'un gestionnaire d'inscription d'appareil n'affecte pas les appareils inscrits. Quand un gestionnaire d'inscription d'appareil est supprimé :

-   Aucun appareil inscrit n’est affecté.

-   Les appareils inscrits continuent à être entièrement gérés.

-   Les informations d’identification de compte du gestionnaire d’inscription d’appareil supprimé restent valides et vous permettent de vous connecter au Portail d’entreprise pour accéder aux applications.

-   La suppression du gestionnaire d’inscription d’appareil n’entraîne pas la réinitialisation ou la mise hors service des appareils.

-   Il existe toujours une relation entre le compte du gestionnaire d’inscription d’appareil supprimé et les appareils inscrits, mais aucun appareil supplémentaire ne peut être inscrit.
