---
title: Guide pratique pour supprimer un appareil Android d’Intune | Microsoft Docs
description: Cette rubrique explique comment désinscrire un appareil Android d’Intune
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 03/23/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f40aab26-7613-48cc-a74e-de83df9465a4
searchScope:
- User help
ROBOTS: ''
ms.reviewer: arnab
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 683b5ec7b07d7c270ea30ac438e7fc839b13d5fc
ms.sourcegitcommit: 490365fb8b5405f323b4358fb1ec9dfdd9ff2d58
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43150342"
---
# <a name="how-to-remove-your-android-device-from-intune"></a>Guide pratique pour supprimer un appareil Android d’Intune

Quand vous supprimez votre appareil Android d’Intune, celui-ci ne peut plus accéder aux ressources de l’entreprise.  Pour plus d’informations sur ce qui se passe lors de la suppression de votre appareil de la gestion, consultez [Que se passe-t-il quand vous désinscrivez votre appareil d’Intune ?](what-happens-if-you-unenroll-your-device-from-intune-android.md)

## <a name="removing-the-device-from-the-company-portal-app"></a>Suppression de l’appareil de l’application Portail d’entreprise

Pour supprimer votre appareil d’Intune et de l’application Portail d’entreprise, suivez ces étapes :

1. Ouvrez le **menu d’action** en appuyant sur les trois points verticaux dans l’angle supérieur droit de l’application Portail d’entreprise.

   ![Image de l’application Portail d’entreprise Android, avec le menu d’action ouvert dans l’angle supérieur droit. La nouvelle option « Supprimer le portail d’entreprise » est disponible en tant que troisième option, sous « Mon profil » et « Paramètres », et au-dessus de « Conditions générales », « Aide et commentaires » et « À propos ».](./media/android_remove_cp_menu_action_after_1705.png)

2. Appuyez sur **Supprimer le portail d’entreprise**.

3. Une confirmation s’affiche, vous demandant si vous êtes sûr de vouloir supprimer le portail d’entreprise. Cette fenêtre fournit des informations sur ce qui se passe lorsque vous désinscrivez votre appareil. Après avoir lu ce message, appuyez sur **OK** pour supprimer l’application.

   ![Une image de la boîte de dialogue de confirmation, qui est disponible après avoir sélectionné la nouvelle option « Supprimer le portail d’entreprise » dans le menu Action. La boîte de dialogue informe l’utilisateur que « en supprimant le portail d’entreprise, votre appareil ne sera plus géré par le support technique de votre entreprise et pourrait perdre l’accès à la messagerie, aux applications et aux données de l’entreprise ». L’utilisateur doit ensuite confirmer qu’il souhaite supprimer l’application Portail d’entreprise en sélectionnant « Oui ».](./media/android_remove_cp_menu_confirmation_after_1705.png)

## <a name="removing-data-collected-by-the-company-portal-app"></a>Suppression des données collectées par l’application Portail d’entreprise

Pour supprimer toutes les données que stocke l’application Portail d’entreprise pour Android sur votre appareil :

-   Effacer les données d’application dans Applications -> Cliquer sur l’application -> bouton « Effacer les données »
-   Supprimer le dossier '\storage\internal storage\Android\data\com.microsoft.windowsintune.companyportal'

Encore besoin d’aide ? Contactez le support technique de votre entreprise. Pour obtenir ses coordonnées, consultez le [site web du Portail d’entreprise](https://go.microsoft.com/fwlink/?linkid=2010980).
