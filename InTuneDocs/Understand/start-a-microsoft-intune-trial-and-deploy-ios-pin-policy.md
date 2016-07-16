---
title: "Commencer une évaluation de Microsoft Intune et déployer une stratégie de code confidentiel iOS | Microsoft Intune"
description: 
keywords: 
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 06cb9a73-0f17-44b3-b334-86c98020316e
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 7f3985b10ac9612c8c1efc4756eb25cdcf29b023
ms.openlocfilehash: 6787d0c35621b2bc94bfe376dfd1669e9dfe46db


---

# Commencer une évaluation de Microsoft Intune et déployer une stratégie de code confidentiel iOS
Ces instructions pas à pas vous permettent de configurer une évaluation d’Intune et de configurer une stratégie de code confidentiel pour des appareils iOS. Pour obtenir une liste d’autres tâches d’évaluation d’Intune courantes, consultez [Tâches courantes pour l’évaluation d’Intune](common-microsoft-intune-evaluation-tasks.md).



## Passer en revue les conditions requises pour cette tâche

-   PC Windows avec Internet Explorer : pour effectuer les tâches d’administration

-   Appareil iOS 7.1 ou version ultérieure pour tester la validation de la stratégie utilisateur

-   Téléphone pour vous authentifier pendant l’inscription de la version d’évaluation

## Créer un compte d’évaluation Intune gratuit
> [!NOTE]
> Si vous avez déjà un abonnement à Intune, ignorez cette section et passez à la suivante.

1.  Sur un PC Windows, cliquez avec le bouton droit sur **Internet Explorer** (IE), puis sélectionnez **Navigation InPrivate**.

    ![Démarrer la navigation InPrivate](../media/30-day-trial-walkthrus/30day-start-trial-1-InPrivate.png)

2.  Accédez au [portail d’inscription Intune](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1), fournissez les informations demandées, puis cliquez sur **Suivant**.

    ![S’inscrire pour obtenir un compte](../media/30-day-trial-walkthrus/30day-start-trial-2-abt-you.png)

3.  Entrez un ID utilisateur et un mot de passe pour votre compte d’administrateur, puis cliquez sur **Suivant**. Vous utiliserez cet ID pour vous connecter au portail et effectuer vos tâches d’administration Intune.

    ![Créer un ID](../media/30-day-trial-walkthrus/30day-start-trial-3-createID.png)

4.  Entrez votre numéro de téléphone portable et cliquez sur **M’envoyer un SMS** pour valider votre numéro.

    ![Valider vos informations](../media/30-day-trial-walkthrus/30day-start-trial-4-textme.png)

5.  Enregistrez les informations affichées à l’écran, puis cliquez sur **Vous êtes prêt !**.

    ![Vous êtes prêt](../media/30-day-trial-walkthrus/30day-start-trial-5-ReadyToGo.png)

## Créer un utilisateur de test

1.  Sur un PC Windows, cliquez sur **Démarrer** pour accéder à la page de gestion des utilisateurs.

    ![Accéder à la page de gestion des utilisateurs](../media/30-day-trial-walkthrus/30day-crt-user-6-click-start.png)

2.  Cliquez sur le bouton **+** pour ajouter un utilisateur.

    ![Ajouter un utilisateur](../media/30-day-trial-walkthrus/30day-crt-user-7-click-plus.png)

3.  Dans la page **Créer un compte d’utilisateur** :

    1.  Fournissez les informations relatives à l’utilisateur de test.

    2.  Sélectionnez l’option **Entrez le mot de passe**.

    3.  Décochez la case **Exiger que cette personne modifie son mot de passe la prochaine fois qu’il se connecte**.

    4.  Cliquez sur **Créer**.

    ![Créer un nouveau compte d’utilisateur](../media/30-day-trial-walkthrus/30day-crt-user-8-add-user-info.png)

4.  Dans la page de confirmation de création de l’utilisateur, cliquez sur **Fermer**.

    ![Page de confirmation de création de l’utilisateur](../media/30-day-trial-walkthrus/30day-crt-user-9-close-confirm.png)

5.  Cliquez sur le bouton **Actualiser** pour voir l’utilisateur de test que vous avez créé.

    ![Confirmation du compte](../media/30-day-trial-walkthrus/30day-crt-user-10-refresh-user.png)

## Configurer une stratégie de code confidentiel iOS pour l’utilisateur de test

1.  Sur un PC Windows, définissez Intune comme autorité de gestion des appareils mobiles :

    1.  Accédez à la [console de gestion Intune](http://manage.microsoft.com/), connectez-vous avec votre compte d’administrateur, puis cliquez sur **Démarrer la gestion des appareils mobiles**. La page Autorité de gestion des appareils mobiles s’ouvre.

        ![Prise en main de la console Intune](../media/30-day-trial-walkthrus/30day-cfg-pol-11-start-mg-mobl-dev.png)

    2.  Cliquez sur le lien **Définir l’autorité de gestion des appareils mobiles**.

        ![Définir l’autorité de gestion des appareils mobiles](../media/30-day-trial-walkthrus/30day-cfg-pol-12-link-set-mdm.png)

2.  Activez les appareils iOS pour l’inscription. Ce processus configure un certificat approuvé entre Apple Push Notification Service (APNs) et votre abonnement Intune.

    1.  Cliquez sur **Activer la plateforme iOS et Mac OS X**.

        ![Activer l’inscription iOS et Mac OS X](../media/30-day-trial-walkthrus/30day-cfg-pol-13-enbl-ios-plat.png)

    2.  Cliquez sur **Télécharger la demande de certificat APNs**.

        ![Télécharger le certificat APNs](../media/30-day-trial-walkthrus/30day-cfg-pol-14-dwnld-cert-reqst.png)

    3.  Spécifiez un nom de fichier et un emplacement pour votre demande de signature de certificat, puis cliquez sur **Enregistrer**. Ce fichier contient la clé publique qui correspond à une clé privée détenue par votre abonnement Intune.

        ![Spécifier la demande de signature de certificat](../media/30-day-trial-walkthrus/30day-cfg-pol-15-cert-name-loc.png)

    4.  Cliquez sur **Portail Apple Push Certificates** pour ouvrir un nouvel onglet.

        ![Accéder à la page des certificats APNs](../media/30-day-trial-walkthrus/30day-cfg-pol-16-cert-portl-link.png)

    5.  Entrez votre ID Apple et votre mot de passe, puis cliquez sur **Se connecter**. Cet ID peut être celui que vous utilisez sur votre appareil iOS pour obtenir des applications à partir de l’App Store iOS.

        ![Connectez-vous à Apple Push Certificates portal (Portail des certificats Push Apple)](../media/30-day-trial-walkthrus/30day-cfg-pol-17-id-passw-signin.png)

    6.  Cliquez sur **Créer un certificat**.

        ![Créez un certificat APNs](../media/30-day-trial-walkthrus/30day-cfg-pol-18-create-cert.png)

    7.  Lisez les conditions d’utilisation d’Apple, cochez la case, puis cliquez sur **Accepter**.

        ![Acceptez les conditions d’utilisation](../media/30-day-trial-walkthrus/30day-cfg-pol-19-TOU.png)

    8.  Cliquez sur **Parcourir**.

        ![Accédez à l’emplacement où vous avez enregistré le certificat](../media/30-day-trial-walkthrus/30day-cfg-pol-20-browse.png)

    9. Sélectionnez le fichier de demande de signature de certificat (CSR) que vous avez enregistré précédemment, puis cliquez sur **Ouvrir**.

        ![Ouvrez le certificat](../media/30-day-trial-walkthrus/30day-cfg-pol-21-CSRfile-open.png)

    10. Cliquez sur le bouton **Télécharger**.

        ![Téléchargez le certificat](../media/30-day-trial-walkthrus/30day-cfg-pol-22-upld-reqst.png)

    11. Quand vous êtes invité à télécharger un fichier JSON, cliquez sur **Enregistrer sous**.

        ![Enregistrez le fichier JSON](../media/30-day-trial-walkthrus/30day-cfg-pol-23-json-saveas.png)

    12. Spécifiez un emplacement pour votre fichier JSON, puis cliquez sur **Enregistrer**.

        ![Spécifiez l’emplacement où enregistrer le fichier JSON](../media/30-day-trial-walkthrus/30day-cfg-pol-24-json-save-loc.png)

        Si votre page n’est pas automatiquement redirigée après quelques secondes, cliquez sur **Annuler**.

        ![Annulez si la page ne vous redirige pas](../media/30-day-trial-walkthrus/30day-cfg-pol-25-json-pg-cancel.png)

    13. Pour récupérer votre nouveau fichier de certificat, cliquez sur **Télécharger**.

        ![Téléchargez le certificat](../media/30-day-trial-walkthrus/30day-cfg-pol-26-dwnld-retrv-cert.png)

    14. Quand vous êtes invité à télécharger un fichier PEM, cliquez sur **Enregistrer sous**.

        ![Téléchargez le fichier PEM](../media/30-day-trial-walkthrus/30day-cfg-pol-27-pem-saveas.png)

    15. Spécifiez un emplacement pour le fichier PEM et cliquez sur **Enregistrer**.

        ![Enregistrez le fichier PEM](../media/30-day-trial-walkthrus/30day-cfg-pol-28-pem-save-loc.png)

    16. Revenez à l’onglet de la console de gestion Intune, puis cliquez sur **Télécharger le certificat APNs**.

        ![Téléchargez le certificat APNs](../media/30-day-trial-walkthrus/30day-cfg-pol-29-upld-cert.png)

    17. Entrez votre ID Apple et cliquez sur **Parcourir**.

        ![Entrez votre ID Apple](../media/30-day-trial-walkthrus/30day-cfg-pol-30-app-id-browse.png)

    18. Sélectionnez le fichier PEM que vous venez d’enregistrer, puis cliquez sur **Ouvrir**.

        ![Ouvrez le fichier PEM](../media/30-day-trial-walkthrus/30day-cfg-pol-31-sel-pem-open.png)

    19. Cliquez sur **Télécharger**.

        ![Téléchargez le fichier PEM](../media/30-day-trial-walkthrus/30day-cfg-pol-32-pem-upload.png)

        Votre certificat APNs est maintenant configuré.

        ![Configuration de certificat APNs terminée](../media/30-day-trial-walkthrus/30day-cfg-pol-33-apns-confgd.png)

3.  Créez un groupe d’utilisateurs de test pour le ciblage de stratégie :

    1.  Dans le volet gauche, cliquez sur **Groupes**.

        ![Ouvrez les groupes](../media/30-day-trial-walkthrus/30day-cfg-pol-34-clk-groups.png)

    2.  Tout à droite, cliquez sur **Créer un groupe**.

        ![Créer un groupe](../media/30-day-trial-walkthrus/30day-cfg-pol-35-crt-group.png)

    3.  Spécifiez un nom de groupe, sélectionnez **Tous les utilisateurs** comme groupe parent, puis cliquez sur **Suivant**.

        ![Sélectionnez Tous les utilisateurs comme groupe parent](../media/30-day-trial-walkthrus/30day-cfg-pol-36-name-group.png)

    4.  Dans le champ **Commencer l’appartenance au groupe par**, sélectionnez **Tous les utilisateurs du groupe parent**, puis cliquez sur **Terminer**.

        ![Commencez l’appartenance au groupe parent](../media/30-day-trial-walkthrus/30day-cfg-pol-37-all-users-group.png)

4.  Créez une stratégie de code confidentiel iOS et ciblez-la sur le groupe d’utilisateurs de test :

    1.  Dans le volet gauche, cliquez sur **Stratégie**.

        ![Ouvrez l’espace de travail Stratégie](../media/30-day-trial-walkthrus/30day-cfg-pol-38-clk-policy.png)

    2.  Tout à droite, cliquez sur **Ajouter une stratégie**.

        ![Ajoutez une stratégie](../media/30-day-trial-walkthrus/30day-cfg-pol-39-add-policy.png)

    3.  Développez le nœud iOS, sélectionnez la ligne **Configuration générale**, puis cliquez sur **Créer une stratégie**.

        ![Créer une stratégie de configuration générale iOS](../media/30-day-trial-walkthrus/30day-cfg-pol-40-gen_cfg_pol.png)

    4.  Tapez un nom pour la stratégie, activez l’option **Exiger un mot de passe pour déverrouiller les appareils mobiles**, puis affectez la valeur **4** comme **Longueur minimale du mot de passe**.

        ![Configurez les paramètres du mot de passe](../media/30-day-trial-walkthrus/30day-cfg-pol-41-name-policy.png)

    5.  Cliquez sur **Oui** pour déployer la stratégie.

        ![Déployez la stratégie](../media/30-day-trial-walkthrus/30day-cfg-pol-42-yes-deploy-pol.png)

    6.  Cliquez sur le groupe d’utilisateurs créé précédemment, sur **Ajouter**, puis sur **OK**.

        ![Sélectionnez le groupe pour la stratégie](../media/30-day-trial-walkthrus/30day-cfg-pol-43-add-pol-to-grp.png)

        Vous avez maintenant une stratégie de code confidentiel iOS qui cible votre groupe d’utilisateurs de test.

        ![Configuration de la stratégie terminée](../media/30-day-trial-walkthrus/30day-cfg-pol-44-policy-applied.png)

## Vérifier que la stratégie est appliquée sur un appareil iOS

1.  Sur un iPad, lancez l’App Store iOS, installez l’application gratuite **Portail d’entreprise Microsoft Intune**, puis ouvrez-la.

    ![Installation du portail d’entreprise](../media/30-day-trial-walkthrus/30day-cfg-pol-45-cportal-installed.png)

2.  Entrez le nom de compte et le mot de passe de votre utilisateur de test, puis appuyez sur **Se connecter**.

    ![Entrez vos informations d’identification](../media/30-day-trial-walkthrus/30day-cfg-pol-46-cportal-signin.png)

3.  Appuyez sur **Inscription** pour commencer l’inscription de l’appareil dans Intune.

    ![Démarrez l’inscription](../media/30-day-trial-walkthrus/30day-cfg-pol-47-tap-enroll.jpg)

4.  Dans l’écran **Installer un profil**, appuyez sur **Installer**.

    ![Installez un profil](../media/30-day-trial-walkthrus/30day-cfg-pol-48-profile-install-1.jpg)

5.  Dans la boîte de dialogue **Installer un profil**, appuyez sur **Installer**.

    ![Continuez l’installation du profil](../media/30-day-trial-walkthrus/30day-cfg-pol-49-profile-install-2.jpg)

6.  Dans l’écran **Avertissement**, appuyez sur **Installer**.

    ![Acceptez le message d’avertissement](../media/30-day-trial-walkthrus/30day-cfg-pol-50-warning-install-3.png)

7.  Dans la boîte de dialogue **Gestion à distance**, appuyez sur **Approuver**.

    ![Gestion à distance de la confiance](../media/30-day-trial-walkthrus/30day-cfg-pol-51-remt-mgmt-trust.jpg)

8.  Une fois l’installation du profil de gestion terminée, appuyez sur **Terminé**. L’inscription est terminée.

    ![Inscription terminée](../media/30-day-trial-walkthrus/30day-cfg-pol-52-profile-done.jpg)

9. Une fois l’inscription terminée, appuyez sur **OK** et fermez l’application Portail d’entreprise.

    ![Appuyez sur OK pour fermer l’application Portail d’entreprise](../media/30-day-trial-walkthrus/30day-cfg-pol-53-devc-enrolled-ok.png)

10. Quand vous êtes invité à configurer un code d’accès, appuyez sur **Continuer**.

    ![Acceptez l’invite pour configurer le code d’accès](../media/30-day-trial-walkthrus/30day-cfg-pol-54-passcode-req-cont.png)

11. Tapez votre code d’accès, appuyez sur **Continuer**, retapez votre code d’accès, puis appuyez sur **Enregistrer**.

    ![Entrez un code d’accès](../media/30-day-trial-walkthrus/30day-cfg-pol-55-passcode-enter.jpg)

12. Appuyez sur le bouton d’alimentation pour verrouiller votre iPad, puis faites glisser pour le déverrouiller. Vous devez désormais entrer votre code d’accès pour déverrouiller l’appareil.

### Voir aussi
[Guide d'évaluation de Microsoft Intune](get-started-with-a-30-day-trial-of-microsoft-intune.md)



<!--HONumber=Jun16_HO4-->


