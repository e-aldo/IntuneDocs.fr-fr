---
title: Inscrire votre appareil iOS pour la gestion des dépenses de télécommunications avec Intune
description: Découvrez comment inscrire un appareil iOS dans un logiciel de gestion des dépenses de télécommunications.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 04/19/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 6d8c6372-f2ce-4558-8886-1d7c1966699c
searchScope:
- User help
ROBOTS: ''
ms.reviewer: sumitp
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: ff51405ee48851b5a48c4d6142c33bc16ed6218e
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2018
---
# <a name="enroll-your-ios-device-in-telecom-expense-management"></a>Inscrire votre appareil iOS pour la gestion des dépenses de télécommunications

Votre organisation peut utiliser un logiciel de gestion des dépenses de télécommunications pour garantir l’utilisation de ses forfaits de données et d’appels vocaux dans des limites acceptables. Une fois que vous aurez fini d’inscrire votre appareil, vous serez invité à sélectionner la catégorie qui lui convient le mieux.

  ![Capture de l’écran de sélection de la catégorie adaptée à un appareil iOS permettant de choisir entre une inscription d’entreprise et une inscription personnelle](./media/ios-enroll-10-tem-select-best-category.png)

Sélectionnez l’option appropriée. Vous recevrez alors une notification vous invitant à installer l’application [__Datalert__](https://itunes.apple.com/app/datalert/id771029268?mt=8) à partir de l’App Store. L’application Datalert permet à votre organisation de mesurer sa consommation des données. Si votre organisation a configuré l’option d’inscription professionnelle ou scolaire Microsoft, vous devrez ouvrir une session avec votre compte professionnel ou scolaire. Si cette option n’a pas été activée, vous devrez fournir certaines informations, telles que votre numéro de téléphone, et vérifier votre appareil à l’aide d’un code pour vous inscrire au service Datalert à partir de l’application.

  ![Capture de l’écran d’accueil de l’application Datalert vous invitant à passer à l’écran suivant après vous avoir brièvement expliqué que Datalert vous aidera à tirer le meilleur parti de votre forfait de données](./media/ios-enroll-11-tem-datalert-setup.png)

## <a name="enroll-into-datalert-using-your-microsoft-work-or-school-account"></a>S’inscrire à Datalert à l’aide de votre compte Microsoft professionnel ou scolaire

> [!NOTE]
> Vous devez avoir installé et activé l’application [Microsoft Authenticator](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) sur votre téléphone pour procéder à l’inscription.

1. Sélectionnez __Enroll with Microsoft account__ (S’inscrire avec un compte Microsoft).

   ![Une image de l’écran Paramètres de l’application Datalert, qui contient un champ de numéro de téléphone permettant d’inscrire un appareil, apparaît sur la moitié supérieure de l’écran ; un champ « Enroll with Microsoft account » (S’inscrire avec un compte Microsoft ») s’affiche dans la partie inférieure, à condition que vous disposiez d’un compte Microsoft Office 365 et d’un abonnement Intune.](./media/ios-enroll-11a-tem-datalert-enroll-msft-account.png)

2. Vous recevrez une notification indiquant que __« Datalert » souhaite ouvrir « Authenticator »__. Sélectionnez __Ouvrir__.

   ![Image de la fenêtre contextuelle invitant l’utilisateur à ouvrir l’application Authenticator à la demande de l’application Datalert.](./media/ios-enroll-11b-tem-datalert-open-authenticator.png)

3. Connectez-vous avec votre __compte scolaire ou professionnel Microsoft__. Le programme d’installation de Datalert s’exécute quelques instants, avant de se terminer. Cliquez sur __Terminer__ à la fin de l’installation.

## <a name="enroll-into-datalert-using-your-phone-number"></a>S’inscrire dans Datalert à l’aide de votre numéro de téléphone

1. Indiquez le numéro de téléphone de votre appareil.

   ![Capture d’écran de l’application Datalert demandant un numéro de téléphone](./media/ios-enroll-12-tem-datalert-phone-number.png)

2. Vous recevrez alors un code de vérification par SMS. Fournissez ce code, puis appuyez sur __OK__.

   ![Capture d’écran de l’application Datalert demandant le code de vérification envoyé par SMS](./media/ios-enroll-13-tem-datalert-sms.png)

3. La procédure d’installation de Datalert s’achève dès que vous fournissez le code de vérification. Appuyez sur __Terminer__. Vous serez alors en mesure d’analyser vos données à l’aide de l’application Datalert.

   ![Capture d’écran de l’application Datalert analysant la consommation des données du jour](./media/ios-enroll-14-tem-datalert-monitoring-active.png)

Une fois inscrit, vous commencerez à visualiser votre consommation des données dans l’application Datalert.

Encore besoin d’aide ? Contactez le support technique de votre entreprise. Pour obtenir ses coordonnées, consultez le [site web du Portail d’entreprise](https://portal.manage.microsoft.com#HelpDeskDialog).
