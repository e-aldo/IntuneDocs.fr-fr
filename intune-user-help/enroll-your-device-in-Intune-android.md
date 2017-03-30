---
title: Inscrire un appareil Android dans Intune | Microsoft Docs
description: Cette rubrique explique comment inscrire un appareil Android dans Intune
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 03/17/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0ed3a002-7533-4001-ae24-e10b64b66620
searchScope:
- User help
ROBOTS: 
ms.reviewer: arnab
ms.suite: ems
ms.custom: intune-enduser
translationtype: Human Translation
ms.sourcegitcommit: 07a1f63d02e2517e4ab64305304127a40922263c
ms.openlocfilehash: a4886c9fb780f2748aa767e426f404e03671f42e
ms.lasthandoff: 03/20/2017


---


# <a name="enroll-your-android-device-in-intune"></a>Inscrire un appareil Android dans Intune

Si votre société ou votre école utilise Microsoft Intune, vous pouvez inscrire votre appareil Android pour accéder à la messagerie, aux fichiers et d’autres ressources d’entreprise. Quand vous inscrivez vos appareils, le service Informatique peut gérer ces ressources professionnelles ou pédagogiques, les sécuriser et vous donner la liberté d’utiliser l’appareil de votre choix pour effectuer votre travail. Pour en savoir plus sur l’inscription, consultez [Que se passe-t-il quand j’installe l’application Portail d’entreprise et que j’inscris mon appareil ?](what-happens-if-you-install-the-Company-Portal-app-and-enroll-your-device-in-intune-android.md)

<iframe src="https://channel9.msdn.com/Series/IntuneEnrollment/Android-Enrollment/player" width="960" height="540" allowFullScreen frameBorder="0"></iframe>

Ces instructions d’inscription concernent les appareils natifs et Samsung KNOX Android. Samsung KNOX est un type de sécurité que certains appareils Samsung utilisent pour fournir une protection supplémentaire par rapport aux appareils Android natifs. Pour vérifier si vous avez un appareil Samsung KNOX, accédez à **Paramètres** > **About device** (À propos de l’appareil). Si « Version Knox » n’apparaît pas dans la liste, c’est que vous avez un appareil Android natif.

Avant ou après l’inscription, vous pouvez être invité à choisir une catégorie qui décrit le mieux votre utilisation de l’appareil. Votre administrateur informatique utilise cette catégorie pour vérifier les applications auxquelles vous avez accès.

Si vous recevez une erreur pendant que vous inscrivez votre appareil dans Intune, vous pouvez [envoyer les erreurs d’inscription à votre administrateur informatique](send-enrollment-errors-to-your-it-admin-android.md).

**Pour inscrire un appareil Android :**

1.  Installez l’application Portail d’entreprise Intune gratuite à partir de [Google Play](http://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal).

2.  Ouvrez l’application Portail d’entreprise Microsoft Intune.

3.  Dans l’écran de **bienvenue** du portail d’entreprise, appuyez sur **Se connecter**, puis connectez-vous avec votre compte professionnel ou scolaire.

    ![L’écran d’accueil de l’application Portail d’entreprise pour Android demande à l’utilisateur de se connecter avec son compte professionnel ou scolaire. Il affiche également un avertissement sur le fait que les comptes Microsoft et les autres comptes personnels ne sont pas acceptés.](./media/and-enroll-0-welcome-screen.png)   

4.  Si votre administrateur informatique a établi des conditions générales, appuyez sur **ACCEPTER** pour en accepter les termes.

    ![android-company-portal-sign-in](./media/and-enroll-3-accept-terms.png)

5.  Connectez-vous à l’application Portail d’entreprise à l’aide de votre compte professionnel ou scolaire et de votre mot de passe, puis appuyez sur **Se connecter**.

    ![android-company-portal-sign-in](./media/and-enroll-2-cp-sign-in.png)

6.  Dans l’écran **Configuration de l’accès à l’entreprise**, appuyez sur **COMMENCER**.

    ![Écran de configuration de l’accès à l’entreprise](./media/and-enroll-4a-comp-access-setup.png)

    > [!NOTE]
    > Les triangles jaunes ne signifient pas que vous avez déjà rencontré une erreur. Ces icônes indiquent qu’il existe toujours des étapes à effectuer dans le processus d’inscription.

7. Dans l’écran **Pourquoi inscrire votre appareil ?**, découvrez ce que vous pouvez faire une fois votre appareil inscrit, puis appuyez sur **Continuer**.

    ![Pourquoi inscrire votre appareil ?](./media/and-enroll-4b-why-enroll.png)

8.  Consultez la liste de ce que votre administrateur informatique peut voir et ne pas voir sur votre appareil, puis appuyez sur **CONTINUER**.

    ![Paramètres de confidentialité](./media/and-enroll-4c-we-care-privacy.png)

9.  Dans l’écran **Et ensuite ?**, découvrez ce qui se passe lors de l’inscription, puis appuyez sur **INSCRIRE**.

    ![Écran Et ensuite](./media/and-enroll-4d-what-comes-next.png)

10.  Si vous utilisez Android 6.0 ou version ultérieure, effectuez cette étape. Sinon, passez à l'étape suivante.

    Si votre administrateur informatique a configuré certaines stratégies, les messages suivants peuvent s’afficher :
    -    **Autoriser l’application Portail d’entreprise à passer et gérer des appels téléphoniques ?**

        ![android-company-portal-sign-in](./media/and-enroll-3a-allow-phone-access.png)

    Si ce message s’affiche, appuyez sur **Autoriser** Vous pouvez appuyer sur AUTORISER sans risques car **Microsoft ne passe jamais ni ne gère vos appels téléphoniques**. Google contrôle le texte du message et Microsoft ne peut pas le modifier. Quand vous autorisez l’accès, vous permettez simplement à votre appareil d’envoyer son numéro d’identité internationale d’équipement mobile (IMEI) à Intune. Le numéro IMEI est comparable à un numéro de série qui identifie un appareil mobile de façon unique.

    Si vous refusez l’accès, le message apparaît la prochaine fois que vous vous connectez à l’application Portail d’entreprise, mais vous pouvez désactiver les futurs messages en cochant la case **Ne plus poser la question**. Si vous décidez ensuite d’autoriser l’accès, accédez à **Paramètres** &gt; **Applications** &gt; **Portail d’entreprise** &gt; **Autorisations** &gt; **Téléphone**, puis activer l’autorisation.

    -    **Autoriser le portail d’entreprise à accéder à vos contacts ?**

        ![android-company-portal-sign-in](./media/and-enroll-3b-allow-contacts-access.png)

        Si ce message s’affiche, appuyez sur **Autoriser** Vous pouvez appuyer sur AUTORISER sans risques car **Microsoft n’accède jamais à vos contacts**. Google contrôle le texte du message et Microsoft ne peut pas le modifier. Quand vous autorisez l’accès, l’application Portail d’entreprise est uniquement autorisée à créer, utiliser et gérer votre compte professionnel.

        Si vous refusez l’accès, le message apparaît la prochaine fois que vous vous connectez à l’application Portail d’entreprise, mais vous pouvez désactiver les futurs messages en cochant la case **Ne plus poser la question**. Si vous décidez ensuite d’autoriser l’accès, accédez à **Paramètres** &gt; **Applications** &gt; **Portail d’entreprise** &gt; **Autorisations** &gt; **Téléphone**, puis activer l’autorisation.

11.  Dans l’écran **Activer l’administrateur d’appareils**, cliquez sur **Activer**.

    ![Écran Activer l’administrateur d’appareils](./media/and-enroll-5-activate.png)

    Le rôle d’administrateur d’appareils est un rôle dont le portail d’entreprise a besoin pour gérer votre appareil. Il permet à votre administrateur d’afficher certaines informations, notamment le nombre de fois que vous avez essayé de déverrouiller l’écran, et d’effectuer certaines actions.

    Il est important de noter que ces actions sont effectuées au nom de la sécurité. Votre administrateur informatique n’essaie pas de violer votre vie privée ou d’effacer vos informations sans raison, mais il veut s’assurer que les données d’entreprise sont conservées en toute sécurité.

    Microsoft ne contrôle pas ce message, et nous sommes conscients que sa formulation peut sembler quelque peu radicale. Il n’existe pas de moyen pour le portail d’entreprise d’afficher uniquement les restrictions et les informations d’accès pertinentes pour votre organisation. Toutes ces autorisations sont accordées simultanément dans cet écran. Contactez votre administrateur informatique pour plus d’informations sur l’utilisation des informations de contact sur le [site web du portail d’entreprise](http://portal.manage.microsoft.com) si vous avez des questions spécifiques concernant votre propre utilisation.

12.  Suivez les invites pour entrer un code confidentiel ou un mot de passe. Si vous avez déjà configuré un code confidentiel ou un mot de passe sur cet appareil, cet écran ne s’affiche pas ou vous n’êtes pas invité à entrer un nouveau code confidentiel ou mot de passe.

    ![Entrer le code confidentiel ou le mot de passe](./media/and-enroll-6-PIN-native.png)

13.  Si vous utilisez un appareil Samsung KNOX, appuyez sur **Confirmer**. Vous verrez alors un message vous informant que votre appareil est en cours d’inscription. Si vous utilisez un appareil Android natif, l’écran ci-dessous apparaît indiquant que votre appareil est en cours d’inscription.

    ![Politique de confidentialité Samsung KNOX](./media/and-enroll-7-knox-privacy-policy.png)

    Cet écran montre que votre appareil est en cours d’inscription.

    ![Écran Inscription de l’appareil](./media/and-enroll-8-device-enrolling.png)

14. Quand l’écran **Configuration de l’accès à l’entreprise** s’affiche, appuyez sur **CONTINUER**. Si un message indique que votre appareil n’est pas conforme, suivez les instructions pour résoudre le problème, puis appuyez sur **CONTINUER**.

    ![L’appareil n’est pas conforme mais il est inscrit](./media/and-enroll-9a-noncompliant-enrolled-device.png)

    ![Les problèmes de conformité de l’appareil devant être corrigés s’affichent](./media/and-enroll-9b-resolve-compliance-issues.png)

    Vous trouverez plus d’informations sur les problèmes en appuyant dessus.

    ![Problèmes de conformité des appareils développés](./media/and-enroll-9c-resolve-compliance-issues-expanded.png)

    ![Écran de configuration de l’accès à l’entreprise](./media/and-enroll-9d-comp-access-setup.png)  

15. Dans l’écran **Fin de la configuration de l’accès à l’entreprise**, appuyez sur **TERMINÉ**. Votre appareil est maintenant inscrit.

    ![Écran Configuration de l’accès à l’entreprise terminée](./media/and-enroll-10-comp-access-setup-complete.png)

Avant d’installer des applications d’entreprise, accédez à **Paramètres** &gt; **Sécurité** et activez **Sources inconnues**. Si vous n’activez pas cette option avant d’installer des applications, apparaît le message : « Installation bloquée. Pour des raisons de sécurité, votre appareil est configuré pour bloquer les installations d’applications provenant de sources inconnues. Vous pouvez appuyer sur **Paramètres** dans la boîte de dialogue d’erreur pour accéder à l’option **Sources inconnues**.

> [!Note]
> Si votre organisation utilise un logiciel de gestion des dépenses de télécommunications, vous devrez exécuter une procédure supplémentaire pour finaliser l’inscription de votre appareil. Découvrez-en plus [ici](enroll-your-device-with-telecom-expense-management-android.md).

Encore besoin d’aide ? Contactez votre administrateur (consultez le [site web Portail d’entreprise](http://portal.manage.microsoft.com) pour plus d’informations) ou écrivez à l’<a href="mailto:wintunedroidfbk@microsoft.com?subject=I'm having trouble with enrolling my Android device&body=Describe the issue you're experiencing here.">équipe Microsoft Android</a>.

