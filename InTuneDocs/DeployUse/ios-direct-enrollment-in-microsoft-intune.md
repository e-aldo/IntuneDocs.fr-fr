---
title: Inscription directe pour les appareils iOS | Microsoft Intune
description: "Utilisez l’outil Apple Configurator pour inscrire directement les appareils iOS d’entreprise avec une stratégie prédéfinie en vous connectant via USB à un ordinateur Mac."
keywords: 
author: NathBarn
manager: arob98
ms.date: 07/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a692b90c-72ae-47d1-ba9c-67a2e2576cc2
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: aabe68a3621a02b8f3142ab3f593190cc23053dd
ms.openlocfilehash: 17836bc826bc89e3f041f7b369be09c1cce9ea4f


---

# Inscrire directement des appareils iOS en utilisant Apple Configurator
Intune prend en charge l’inscription d’appareils iOS d’entreprise avec l’outil [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017) s’exécutant sur un ordinateur Mac. Ce processus ne réinitialise pas l’appareil aux paramètres d’usine et l’inscrit avec une stratégie prédéfinie. Cette méthode est destinée aux appareils n’ayant **Aucune affinité utilisateur** et implique de connecter l’appareil iOS à un ordinateur Mac via une connexion USB pour configurer l’inscription d’entreprise. Lors de l’inscription directe des appareils iOS, vous pouvez inscrire un appareil sans obtenir son numéro de série. Vous pouvez également nommer l’appareil à des fins d’identification avant qu’Intune capture son nom lors de l’inscription. L’application Portail d’entreprise n’est pas prise en charge pour les appareils inscrits directement. Cette aide suppose que vous utilisez Apple Configurator 2.0 sur un ordinateur Mac.

1.  **Créer un profil pour des appareils** Un profil d'inscription d'appareil définit les paramètres appliqués aux appareils. Si ce n'est déjà fait, créez un profil d'inscription d'appareil pour les appareils iOS inscrits à l'aide d'Apple Configurator.

    1.  Dans la [console d'administration Microsoft Intune](http://manage.microsoft.com), accédez à **Stratégie** &gt; **Inscription d'appareil professionnel**, puis choisissez **Ajouter**.

        ![Page Créer un profil d’inscription d’appareils](../media/pol-sa-corp-enroll.png)

    2.  Entrez les détails des profils d'appareils :

        -   **Nom** : nom du profil d'inscription d'appareil. Non visible pour les utilisateurs.

        -   **Description** : description du profil d’inscription d’appareil. Non visible pour les utilisateurs.

        -   **Affiliation utilisateur** : spécifie la façon dont les appareils sont inscrits. Pour l’inscription directe, sélectionnez **Aucune affinité utilisateur**.

        -   **Affectation préalable du groupe d’appareils** : tous les appareils déployés dans ce profil appartiennent initialement à ce groupe. Vous pouvez réaffecter les appareils après l'inscription.

            [!INCLUDE[groups deprecated](../includes/group-deprecation.md)]

    3.  Choisissez **Enregistrer le profil** pour ajouter le profil.

5.  **Exporter un profil comme .mobileconfig à déployer sur des appareils iOS** Sélectionnez le profil d’appareil que vous avez créé. Choisissez **Exporter...** dans la barre des tâches. Choisissez **Télécharger le profil** et enregistrez le fichier .mobileconfig téléchargé.

6.  **Transférer le fichier** Copiez le fichier .mobileconfig téléchargé sur un ordinateur Mac.
    > [!NOTE]
    > L’URL du profil d’inscription est valide pendant les deux semaines qui suivent son exportation. Après deux semaines, vous devez exporter une nouvelle URL de profil d’inscription pour inscrire des appareils iOS avec l’Assistant Configuration.
7.  **Préparer l'appareil avec Apple Configurator** Les appareils iOS sont connectés à l'ordinateur Mac et inscrits pour la gestion des appareils mobiles.

    1.  Sur un ordinateur Mac, démarrez **Apple Configurator 2.0**.

    2.  Connectez l’appareil iOS à l’ordinateur Mac avec un câble USB. Fermez **Photos**, **iTunes** et toutes les autres applications qui s’ouvrent quand l’appareil est détecté.

    3.  Dans Apple Configurator, cliquez sur l’appareil iOS connecté, puis cliquez sur le bouton **Add** (Ajouter). Les options qui peuvent être ajoutées à l’appareil s’affichent dans la liste déroulante. Choisissez **Profiles** (Profils).

    4.  Utilisez le sélecteur de fichiers pour sélectionner le fichier .mobileconfig que vous avez exporté à partir d’Intune, puis choisissez **Add** (Ajouter). Le profil est ajouté à l’appareil.  Si l’appareil est non supervisé (**Unsupervised**), l’installation nécessite l’acceptation sur l’appareil.

8.  **Installer le profil** Vous êtes prêt à installer le profil sur l’appareil iOS. L’appareil doit avoir terminé l’Assistant Configuration et être prêt à l’emploi.  Si l’inscription entraîne des déploiements d’applications, un ID Apple doit être configuré sur l’appareil, car les déploiements d’applications nécessitent de s’être connecté à l’APP Store avec un ID Apple.

    1.  Déverrouillez l’appareil iOS.

    2.  Dans la boîte de dialogue **Install profile** de **Management profile**, appuyez sur **Install**.

    3.  Spécifiez le code d’accès d’appareil (**Device Passcode**) ou l’**Apple ID**, si nécessaire.

    4.  Acceptez l’avertissement (**Warning**), puis appuyez sur **Install**.

    5.  Acceptez l’avertissement distant (**Remote Warning**), puis appuyez sur **Trust**.

    6.  Quand la boîte de dialogue **Profile Installed** (Profil installé) confirme que le profil a été **installé**, cliquez sur **Done** (Terminé).

9. **Vérifier le profil** 
    Sur l’appareil iOS, lancez **Settings** (Paramètres) et accédez à **General** (Général) &gt; **Device Management** (Gestion des appareils) &gt; **Management Profile** (Profil de gestion) &gt;, puis vérifiez que l’installation du profil est répertoriée et vérifiez les restrictions de stratégie iOS et les applications installées. L’affichage des applications et des restrictions de stratégie sur l’appareil peut prendre jusqu’à dix minutes.

10. **Distribuer les appareils** L’appareil iOS est maintenant inscrit et géré dans Intune.



<!--HONumber=Aug16_HO1-->


