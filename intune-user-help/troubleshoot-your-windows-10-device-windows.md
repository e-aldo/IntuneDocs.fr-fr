---
title: Résolution de problèmes liés à l’inscription de votre appareil Windows 10 | Microsoft Docs
description: ''
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 07/13/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 4ab630b6-47ff-443b-a2a5-be23388bcea7
searchScope:
- User help
ROBOTS: ''
ms.reviewer: priyar
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 97f23594a5c7b047caf37dbaa39c481585a96d76
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2018
---
# <a name="troubleshoot-your-windows-10-device-enrollment"></a>Résolution de problèmes liés à l’inscription de votre appareil Windows 10
Si vous avez suivi les étapes présentées dans la rubrique [Inscrire un appareil Windows 10 Mobile ou Windows 10 Desktop dans Intune](enroll-your-w10-phone-or-w10-pc-windows.md), mais que vous ne pouvez pas toujours accéder à vos e-mails et fichiers professionnels ou scolaires, essayez les étapes de dépannage suivantes.

1.  Examinez les deux écrans suivants et déterminez celui qui ressemble à ce que vous voyez sur votre appareil. Suivez les étapes associées à l’écran que vous voyez sur votre appareil.

    Si vous voyez cet écran, consultez les étapes de [dépannage à suivre si vous voyez Accès scolaire ou professionnel](#troubleshooting-steps-to-follow-if-you-see-access-work-or-school).

    ![settings-accounts-access-work-or-school](./media/w10-enroll-rs1-connect-to-work-or-school.png)

    Si vous voyez cet écran, consultez les étapes de [dépannage à suivre si vous voyez Votre compte](#troubleshooting-steps-to-follow-if-you-see-your-account).

    ![settings-accounts-your-account](./media/W10-enroll-2-accounts-your-account.png)

## <a name="troubleshooting-steps-to-follow-if-you-see-access-work-or-school"></a>Étapes de dépannage à suivre si vous voyez « Accès Professionnel ou Scolaire »

1. Si vous avez suivi les étapes ci-dessus, mais que vous ne pouvez toujours pas accéder à vos e-mails ou fichiers professionnels ou scolaires, retournez dans **Accès scolaire ou professionnel**.

2. Effectuez l'une des opérations suivantes :

   - Si vous voyez une connexion qui ressemble à l’image ci-dessous, appuyez dessus, puis vérifiez que vous voyez les options Gérer, Informations et Déconnexion. Si vous voyez ces options, vous êtes désormais inscrit et connecté.

     ![validate-successful-enrollment](./media/w10-enroll-rs1-validate-successful-enrollment.png)

   - Si vous ne voyez pas les informations de connexion indiquées ci-dessus, ou si certaines de ces options manquent, appuyez sur **Connexion**, puis connectez-vous avec vos informations d’identification professionnelles ou scolaires. Vous devez à présent être connecté.

## <a name="troubleshooting-steps-to-follow-if-you-see-your-account"></a>Étapes de dépannage à suivre si vous voyez « Votre compte »

Si vous avez suivi les étapes ci-dessus mais que vous ne pouvez toujours pas accéder à vos e-mails, vos fichiers ou d’autres données professionnelles ou scolaires, retournez dans **Comptes** et appuyez sur **Accès professionnel**.

- Vous voyez votre compte professionnel ou scolaire ? Félicitations, vous êtes connecté.

- Si vous ne voyez pas votre compte professionnel ou scolaire, appuyez sur **Connexion**, puis connectez-vous avec vos informations d’identification professionnelles ou scolaires.

## <a name="troubleshooting-steps-to-follow-if-you-see-set-up-a-work-or-school-account"></a>Étapes de dépannage à suivre si vous voyez « Configurer un compte professionnel ou scolaire »

Si vous voyez un message qui indique <strong>Nous n’avons pas pu découvrir automatiquement un point de terminaison de gestion correspondant au nom d’utilisateur entré. Vérifiez votre nom d’utilisateur et réessayez. Si vous connaissez l’URL de votre point de terminaison de gestion, entrez-la.</strong>, vous devez essayer d’entrer à nouveau vos nom d’utilisateur et mot de passe. Si cela ne fonctionne toujours pas, vous devez vérifier auprès du support technique de votre entreprise le site web que vous devez indiquer dans la zone de texte <strong>Point de terminaison de gestion</strong>. Il s’agit d’un site web qui ressemble probablement à <strong>www.votreentreprise.onmicrosoft.com</strong>.

Encore besoin d’aide ? Contactez le support technique de votre entreprise. Pour obtenir ses coordonnées, consultez le [site web du Portail d’entreprise](https://portal.manage.microsoft.com#HelpDeskDialog).
