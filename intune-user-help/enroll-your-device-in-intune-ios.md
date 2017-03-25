---
title: Inscrire un appareil iOS dans Intune | Microsoft Docs
description: Cette rubrique explique comment inscrire un appareil iOS dans Intune
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 03/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6eeec7aa-1b07-4ce3-894c-13e09b89bdd4
searchScope:
- User help
ROBOTS: 
ms.reviewer: esmich
ms.suite: ems
ms.custom: intune-enduser
translationtype: Human Translation
ms.sourcegitcommit: 1ba0dab35e0da6cfe744314a4935221a206fcea7
ms.openlocfilehash: af3313e6ba5cbf9184aaaa9b197f7a3b2b9d4c3e
ms.lasthandoff: 03/13/2017


---


# <a name="enroll-your-ios-device-in-intune"></a>Inscrire un appareil iOS dans Intune

Si votre société ou votre école utilise Microsoft Intune, vous pouvez inscrire votre appareil iOS pour accéder à la messagerie, aux fichiers et d’autres ressources d’entreprise. Quand vous inscrivez vos appareils, le service Informatique peut gérer ces ressources professionnelles ou pédagogiques, les sécuriser et vous donner la liberté d’utiliser l’appareil de votre choix pour effectuer votre travail. Pour en savoir plus sur l’inscription, consultez [Que se passe-t-il si vous installez l’application Portail d’entreprise et que vous inscrivez votre appareil dans Intune ?](what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-ios.md)

<iframe src="https://channel9.msdn.com/Series/IntuneEnrollment/iOS-Enrollment/player" width="960" height="540" allowFullScreen frameBorder="0"></iframe>

> [!NOTE]
> Si vous essayez d’inscrire un appareil macOS, tel qu’un MacBook Pro ou un iMac, [suivez plutôt ces instructions](enroll-your-device-in-intune-macos.md).

**Avant de commencer :**

- Veillez à terminer l’inscription après avoir démarré la procédure. Une interruption de plus de quelques minutes arrête généralement le processus et vous oblige à effectuer un redémarrage.
- Si votre inscription échoue pour une raison quelconque, vous devez revenir à l’application du portail d'entreprise et réessayer.
- Vérifiez que votre connexion Wi-Fi fonctionne. Si ce n’est pas le cas, l’inscription échoue.
- Si vous avez bloqué Safari sur votre appareil, débloquez-le. Vous devez utiliser Safari pour effectuer l’inscription.


**Pour inscrire un appareil iOS :**

1.  Appliquez la procédure décrite dans [Installer l’application Portail d’entreprise Intune et s’y connecter](install-and-sign-in-to-the-intune-company-portal-app-ios.md).

2. Dans la page **Configuration de l’accès à l’entreprise**, appuyez sur **Commencer**.

    ![ios-enroll-comp-access-setup-begin](./media/ios-enroll-1a-comp-access-setup.png)

3. Dans l’écran **Pourquoi inscrire votre appareil ?**, découvrez ce que vous pouvez faire une fois votre appareil inscrit, puis appuyez sur **Continuer**.

    ![ios-enroll-why-enroll](./media/ios-enroll-1b-why-enroll.png)

> [!NOTE]
> Les triangles jaunes ne signifient pas que vous avez déjà rencontré une erreur. Ces icônes indiquent qu’il existe toujours des étapes à effectuer dans le processus d’inscription.

4. Consultez la liste de ce que votre administrateur informatique peut voir et ne pas voir sur votre appareil inscrit, puis appuyez sur **Continuer**.

    ![ios-enroll-what-it-can-see](./media/ios-enroll-1c-we-care-privacy.png)

5.  Dans l’écran **Et ensuite ?**, découvrez ce qui se passe lors de l’inscription, puis appuyez sur **Inscrire**.

     ![ios-enroll-what-comes-next](./media/ios-enroll-1d-what-comes-next.png)

6.  Dans l’écran **Installer un profil**, appuyez sur **Installer** et entrez votre code secret si vous y êtes invité.

    ![ios-enroll-install-profile](./media/ios-enroll-2-mgt-profile-install.png)

7.  Appuyez sur **Installer**.

    ![ios-enroll-tap-install](./media/ios-enroll-3-mgt-profile-install-2.png)    

8.  Appuyez sur **Installer** pour indiquer que vous avez lu l’avertissement.

       ![ios-enroll-tap-install-after-warning](./media/ios-enroll-4-warning.png)

9.  Appuyez sur **Confiance**.

       ![ios-enroll-tap-trust](./media/ios-enroll-5-trust.png)

10.  Quand l’écran change et indique que l’installation du profil est terminée, appuyez sur **Terminé**.

     ![ios-enroll-tap-done](./media/ios-enroll-6-done.png)

    Un message « Inscription de l’appareil » s’affiche à l’écran.

11.  Quand un message vous invite à ouvrir la page sur le portail d’entreprise, appuyez sur **Ouvrir**.

    ![ios-enroll-open-comp-portal](./media/ios-enroll-7-open-cp.png)

12. Dans l’écran **Configuration de l’accès à l’entreprise**, appuyez sur **Continuer**. Si votre administrateur informatique a configuré des exigences de sécurité supplémentaires, telles que l’obligation de définir un mot de passe, suivez les instructions à l’écran jusqu’à ce que toutes les exigences de conformité soient satisfaites et que l’écran Configuration de l’accès à l’entreprise réapparaisse, puis appuyez sur **Continuer**.

    ![ios-enroll-comp-access-tap-continue](./media/ios-enroll-8-comp-access-setup-compliance.png)

13. Appuyez sur **Terminé**.

    ![ios-enroll-tap-done](./media/ios-enroll-9-comp-access-setup-complete.png)

Votre appareil est maintenant inscrit dans Intune, et l’application Portail d’entreprise réapparaît.

> [!Note]
> Si votre organisation utilise un logiciel de gestion des dépenses de télécommunications, vous devrez exécuter une procédure supplémentaire pour finaliser l’inscription de votre appareil. Découvrez-en plus [ici](enroll-your-device-with-telecom-expense-management-ios.md).

Encore besoin d’aide ? Contactez votre administrateur informatique. Pour obtenir ses coordonnées, consultez le [site web du Portail d’entreprise](http://portal.manage.microsoft.com).

