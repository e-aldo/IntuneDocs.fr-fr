---
title: Supprimer votre appareil Windows d’Intune
description: Explique comment supprimer un appareil Windows d’Intune
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 05/08/2018
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
ms.openlocfilehash: a3cad6a73b3455790441c594933d599b2c6e89f9
ms.sourcegitcommit: 34e96e57af6b861ecdfea085acf3c44cff1f3d43
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/17/2018
---
# <a name="remove-your-windows-device-from-intune-management"></a>Supprimer votre appareil Windows de la gestion Intune

Supprimez un appareil Windows inscrit auprès d’Intune quand vous ne devez ou ne voulez plus :  
* Utiliser votre appareil dans un cadre professionnel ou scolaire. 
* Accéder à vos e-mails, applications ou autres ressources professionnelles ou scolaires.

Une fois que vous l’aurez supprimé, vous ne pourrez plus accéder aux ressources professionnelles ou scolaires à partir de l’appareil. Les appareils Windows pouvant être supprimés d’Intune sont les suivants :  
* Appareils Windows 10 
* Ordinateurs Windows 8.1
* Appareils mobiles WIndows 8.1
 
Pour plus d’informations sur ce qui se passe quand vous supprimez votre appareil de la gestion Intune, consultez [Que se passe-t-il quand vous supprimez votre appareil d’Intune ?](what-happens-if-you-unenroll-your-device-from-intune-windows.md).

## <a name="remove-your-windows-10-device"></a>Supprimer votre appareil Windows 10
Pour supprimer un appareil Windows 10 d’Intune, effectuez les étapes suivantes.

### <a name="via-the-company-portal-app"></a>Par le biais de l’application Portail d’entreprise

1. Ouvrez l'application Portail d'entreprise.
2. Connectez-vous en utilisant vos informations d'identification professionnelles ou scolaires.
3. Dans **Mes appareils**, sélectionnez l’appareil que vous voulez supprimer.
4. En haut à droite de la page d’application, sélectionnez l’icône **Voir plus**.
5. Sélectionnez **Supprimer**. 
6. Pour confirmer la suppression de l’appareil, sélectionnez **Supprimer l’appareil**.

### <a name="via-device-settings-app"></a>Par le biais de l’application Paramètres de l’appareil
1. Ouvrez l’application Paramètres. 
2. Accédez à **Comptes** > **Accès scolaire ou professionnel**.
3. Sélectionnez le compte connecté que vous souhaitez supprimer > **Déconnecter**.
4. Pour confirmer la suppression de l’appareil, sélectionnez **Oui**.

## <a name="remove-your-windows-81-computer"></a>Supprimer votre ordinateur Windows 8.1
Pour supprimer un ordinateur Windows 8.1 d’Intune, effectuez les étapes suivantes.

1.  Accédez à **Paramètres du PC** > **Réseau** > **Espace de travail**.
2.  Sous **Jonction d’espace de travail**, sélectionnez **Quitter**.
3.  Sous **Activer la gestion des appareils**, sélectionnez **Désactiver**.
4.  Dans la fenêtre contextuelle qui s’ouvre, sélectionnez **Désactiver**.

## <a name="remove-your-windows-81-mobile-device"></a>Supprimer votre appareil mobile Windows 8.1
Pour supprimer un appareil mobile Windows 8.1 d’Intune, effectuez les étapes suivantes.

1.  Accédez à **Paramètres** > **Espace de travail**.
2.  Appuyez sur le compte Espace de travail que vous voulez désinscrire.
3.  Appuyez sur **Supprimer** dans le bas de l’écran.
4.  Dans la boîte de dialogue **Supprimer le compte**, appuyez sur **Supprimer**.  
## <a name="removing-your-personal-information-after-removing-the-company-portal"></a>Suppression de vos informations personnelles après la suppression du portail d’entreprise
Il existe deux types de données que stocke les le portail d’entreprise sur votre appareil Windows :

-   **Journaux de diagnostic** : données d’activité d’application standard collectées par Microsoft. Elles sont automatiquement effacées quand vous désinstallez l’application Portail d’entreprise. Les données d’activité de l’application portent par exemple sur la durée pendant laquelle l’application a été ouverte, ou sur d’éventuels plantages.
-   **Cache d’application** : fichiers de prise en charge nécessaires au fonctionnement de l’application, comme les icônes et les paramètres.

Pour supprimer les journaux et le cache stockés, effectuez une des actions suivantes :

* [Désinstallez l’application Portail d’entreprise](https://support.microsoft.com/help/4028003/windows-10-uninstall-apps-and-programs). 

* Réinitialisez l’application Portail d’entreprise. Ouvrez l’application **Paramètres** et sélectionnez > **Applications** > **Portail d’entreprise** > **Options avancées** > **Réinitialiser**. 

Encore besoin d’aide ? Contactez le support technique de votre entreprise. Pour obtenir ses coordonnées, consultez le [site web du Portail d’entreprise](https://portal.manage.microsoft.com#HelpDeskDialog).
