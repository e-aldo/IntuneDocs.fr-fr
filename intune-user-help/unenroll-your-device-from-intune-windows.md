---
title: Supprimer votre appareil Windows d’Intune | Microsoft Docs
description: Explique comment supprimer un appareil Windows d’Intune
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 03/28/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 018bda65-7238-41f5-b92a-e5f67b7fe085
searchScope:
- User help
ROBOTS: ''
ms.reviewer: jieyang
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 9f9051fb393c82031d581f7fec731a3b148cbf2e
ms.sourcegitcommit: 7f46e9990797bdfa669ccba2077721f1bc70c07e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/04/2018
---
# <a name="remove-your-windows-device-from-intune"></a>Supprimer votre appareil Windows d’Intune

Si votre appareil Windows est inscrit à Intune, mais que vous ne voulez plus l’utiliser pour accéder à l’e-mail, aux applications ou à d’autres ressources professionnelles ou scolaires, vous devez le supprimer de la gestion. Une fois que vous aurez supprimé votre appareil d'Intune, vous ne pourrez plus accéder à ces ressources. Pour plus d’informations sur ce qui se passe lors de la suppression de votre appareil de la gestion, consultez [Que se passe-t-il quand vous désinscrivez votre appareil d’Intune ?](what-happens-if-you-unenroll-your-device-from-intune-windows.md).

## <a name="remove-your-windows-10-device"></a>Supprimer votre appareil Windows 10

1.  Dans votre liste d'applications, appuyez sur l'application **Portail d'entreprise** .

2.  Connectez-vous en utilisant vos informations d'identification professionnelles ou scolaires.

3.  Dans **Mes appareils**, sélectionnez l'appareil que vous voulez désinscrire.

4.  Appuyez sur **Supprimer** &gt; **Supprimer**.

## <a name="remove-your-windows-81-computer"></a>Supprimer votre ordinateur Windows 8.1

1.  Accédez à **Paramètres du PC** &gt; **Réseau** &gt; **Espace de travail**.

2.  Sous **Jonction d’espace de travail**, sélectionnez **Quitter**.

3.  Sous **Activer la gestion des appareils**, sélectionnez **Désactiver**.

4.  Dans la fenêtre contextuelle qui s’ouvre, sélectionnez **Désactiver**.

## <a name="remove-your-windows-phone-81-mobile-device"></a>Supprimer votre appareil mobile Windows Phone 8.1

1.  Accédez à **Paramètres** &gt; **Espace de travail**.

2.  Appuyez sur le compte Espace de travail que vous voulez désinscrire.

3.  Appuyez sur **Supprimer** dans le bas de l’écran.

4.  Dans la boîte de dialogue **Supprimer le compte**, appuyez sur **Supprimer**.

## <a name="removing-your-personal-information-after-removing-the-company-portal"></a>Suppression de vos informations personnelles après la suppression du portail d’entreprise

Il existe deux types de données que stocke les le portail d’entreprise sur votre appareil Windows :

-   **Journaux de diagnostic** : les données standard de l’activité de l’application que Microsoft collecte, comme la durée pendant laquelle l’application reste ouverte ou si elle a planté, sont automatiquement effacées quand vous supprimez l’appareil du portail d’entreprise.
-   **Cache d’application** : stockage de certains fichiers de prise en charge nécessaires au fonctionnement de l’application, comme les icônes et les paramètres.

Vous devez effectuer quelques étapes pour supprimer totalement ces informations.

### <a name="uninstall-the-company-portal"></a>Désinstaller le portail d’entreprise  

La [Désinstallation de l’application Portail d’entreprise](https://support.microsoft.com/help/4028003/windows-10-uninstall-apps-and-programs) supprime certaines des données de l’application stockées sur votre appareil.  

### <a name="reset-the-company-portal"></a>Réinitialiser le portail d’entreprise

Vous pouvez réinitialiser le reste des données d’application du portail d’entreprise en réinitialisant l’application dans Paramètres. Ouvrez **Paramètres** > **Applications et fonctionnalités** > **Portail d’entreprise** > **Options avancées**  >  **Réinitialiser**.

Encore besoin d’aide ? Contactez le support technique de votre entreprise. Pour obtenir ses coordonnées, consultez le [site web du Portail d’entreprise](https://portal.manage.microsoft.com#HelpDeskDialog).