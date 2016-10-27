---
title: "Inscrire un appareil Windows 10 dans Intune | Microsoft Intune"
description: "Cette rubrique explique comment inscrire un appareil Windows 10 Mobile ou Desktop dans Intune"
keywords: 
author: barlan
ms.author: barlan
manager: angrobe
ms.date: 10/18/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 36250832-c6fd-4e8d-b681-de735023ebc3
ms.reviewer: priyar
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 9e0321b23bbbaaa16c28c23e56b5fbcaee0d3c24
ms.openlocfilehash: 75f19a1c613b2d018e0cb89862f15aa4be2bc138


---


# Inscrire un appareil Windows 10 Mobile ou Windows 10 Desktop dans Intune

Si votre société ou votre école utilise Microsoft Intune, vous pouvez inscrire vos appareils pour accéder à la messagerie, aux fichiers et d’autres ressources d’entreprise. L’inscription de vos appareils permet à votre organisation de sécuriser les données d’entreprise. Pour en savoir plus sur l’inscription, consultez [Que se passe-t-il quand j’installe l’application Portail d’entreprise et que j’inscris mon appareil dans Intune ?](what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-windows.md) et [Liste de ce que votre administrateur peut voir et ne pas voir sur votre appareil](what-can-your-it-administrator-see-when-you-enroll-your-device-in-intune-windows.md).


Pour inscrire un appareil Windows 10 Mobile ou Windows 10 Desktop

1.  Accédez aux **Paramètres** Windows, puis appuyez sur **Comptes**.

    ![Paramètres Windows](./media/w10-enroll-rs1-settings-accounts.png)

2.  Examinez les deux écrans suivants et déterminez celui qui ressemble à celui qui s’affiche sur votre appareil. Suivez les étapes correspondant à l’écran qui s’affiche sur votre appareil.

    Si cet écran s’affiche, suivez les instructions indiquées dans la section [Étapes à suivre si vous voyez Accès scolaire ou professionnel](#steps-to-follow-if-you-see-access-work-or-school).

    ![Se connecter à un compte professionnel ou scolaire](./media/w10-enroll-rs1-connect-to-work-or-school.png)

    Si vous voyez cet écran, consultez les [étapes à suivre si vous voyez Votre compte](#steps-to-follow-if-you-see-your-account).

    ![Votre compte](./media/w10-enroll-2-accounts-your-account.png)

## Étapes à suivre si vous voyez Accès scolaire ou professionnel

1.  Cliquez sur **Accès scolaire ou professionnel**, puis cliquez sur **Connecter**.

    ![Appuyer sur Accès au compte professionnel ou scolaire](./media/w10-enroll-rs1-connect-to-work-or-school.png)

2.  Entrez votre adresse e-mail professionnelle ou scolaire, puis appuyez sur **Suivant**.

    ![Entrer votre compte professionnel ou scolaire](./media/w10-enroll-rs1-set-up-work-or-school-account.png)

3. Connectez-vous à Intune avec votre compte professionnel ou scolaire.

    ![Ajouter un compte professionnel ou scolaire](./media/w10-enroll-rs1-enter-your-credentials.png)

    Vous verrez un message indiquant que votre société ou votre école procède à l’inscription de votre appareil.

4. Lorsque l’écran **Vous voilà prêt !** s’affiche, appuyez sur **Fermer**. Vous avez terminé.

  ![Appuyer sur Fermer dans l’écran « Vous voilà prêt !  »](./media/w10-enroll-rs1-youre-all-set.png)

5. Si vous voulez vérifier que votre connexion est correcte, revenez aux **Paramètres**, où votre compte professionnel ou scolaire doit maintenant s’afficher.

    ![Valider que la connexion a été correctement configurée](./media/w10-enroll-rs1-validate-successful-enrollment.png)

Si vous avez suivi les étapes précédentes, mais que vous ne pouvez toujours pas accéder à votre compte e-mail ou vos fichiers professionnels ou scolaires, consultez les [Étapes de dépannage à suivre si vous voyez Accès scolaire ou professionnel](troubleshoot-your-windows-10-device-windows.md#troubleshooting-steps-to-follow-if-you-see-access-work-or-school).


## Étapes à suivre si vous voyez Votre compte

1.  Accédez aux **Paramètres** Windows, puis appuyez sur **Comptes**.

    ![Accéder à Paramètres et Comptes](./media/W10-enroll-1-settings-accounts.png)

2.  Appuyez sur **Votre compte**.

    ![Appuyer sur Votre compte](./media/W10-enroll-2-accounts-your-account.png)

3.  Appuyez sur **Ajouter un compte professionnel ou scolaire**.

    ![Appuyer sur Ajouter un compte professionnel ou scolaire](./media/w10-enroll-3-add-work-school-acct.png)

4.  Connectez-vous avec vos informations d'identification professionnelles ou scolaires.

    ![sign-in](./media/W10-enroll-4-sign-in.png)

Si vous avez suivi les étapes précédentes, mais que vous ne pouvez toujours pas accéder à votre adresse e-mail, vos fichiers ou d’autres données professionnelles ou scolaires, suivez les instructions indiquées dans la section [Étapes de dépannage à suivre si vous voyez Votre compte](troubleshoot-your-windows-10-device-windows.md#troubleshooting-steps-to-follow-if-you-see-your-account).

Nous vous recommandons aussi d'installer l'application Portail d'entreprise. Elle vous permet d'identifier et d'obtenir facilement les applications d'entreprise qui présentent un intérêt pour vous et votre rôle. En fonction de la façon dont votre entreprise a configuré Intune, l'application Portail d'entreprise a peut-être été installée dans le cadre de votre processus d'inscription.

Pour vérifier si vous disposez de l’application, recherchez **Portail d’entreprise** dans votre liste d’applications. Si l'application Portail d'entreprise ne figure pas dans votre liste d'applications, procédez comme suit pour l'installer.

1.  Appuyez sur **Démarrer** &gt; **Store**.

2.  Appuyez sur **Rechercher**, puis tapez **portail d’entreprise**.

3.  Dans la liste des résultats, appuyez sur **Portail d’entreprise** &gt; **Installer**.

4.  Appuyez sur **Installer** ou **Gratuit**. L'option affichée dépend de la façon dont votre entreprise a configuré l'application.

Encore besoin d’aide ? Contactez votre administrateur informatique. Pour obtenir ses informations de contact, consultez le [site web du Portail d’entreprise](http://portal.manage.microsoft.com).





<!--HONumber=Oct16_HO1-->


