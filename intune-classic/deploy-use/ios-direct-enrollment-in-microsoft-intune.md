---
title: Inscription directe pour les appareils iOS | Microsoft Docs
description: "Utilisez l’outil Apple Configurator pour inscrire directement les appareils iOS d’entreprise avec une stratégie prédéfinie en vous connectant via USB à un ordinateur Mac."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 01/29/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a692b90c-72ae-47d1-ba9c-67a2e2576cc2
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 8b2bd3ecba0b597bc742ea08872ffe8fc58155cf
ms.openlocfilehash: ee0320db2c4a1a977326f62fcd20597fa39aba24
ms.lasthandoff: 04/24/2017


---

# <a name="directly-enroll-ios-devices-by-using-apple-configurator"></a>Inscrire directement des appareils iOS en utilisant Apple Configurator

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Intune prend en charge l’inscription d’appareils iOS d’entreprise à l’aide de l’outil [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017) s’exécutant sur un ordinateur Mac. Ce processus ne réinitialise pas l’appareil aux paramètres d’usine et l’inscrit avec une stratégie prédéfinie. Cette méthode est destinée aux appareils n’ayant **Aucune affinité utilisateur** et implique de connecter l’appareil iOS à un ordinateur Mac via une connexion USB pour configurer l’inscription d’entreprise.

Quand vous inscrivez directement des appareils iOS, vous pouvez inscrire un appareil sans obtenir son numéro de série. Vous pouvez également nommer l’appareil à des fins d’identification avant qu’Intune capture son nom lors de l’inscription. L’application Portail d’entreprise n’est pas prise en charge pour les appareils inscrits directement. Cette aide suppose que vous utilisez Apple Configurator 2.0 sur un ordinateur Mac.

>[!NOTE]
>Cette méthode d’inscription ne peut pas être utilisée avec celle du [gestionnaire d’inscription d’appareil](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md).

1.  Si ce n’est déjà fait, créez un profil d’inscription d’appareil pour les appareils iOS inscrits par le biais d’Apple Configurator. Un profil d'inscription d'appareil définit les paramètres appliqués aux appareils.

    1.  Dans la [console d’administration Microsoft Intune](https://manage.microsoft.com), accédez à **Stratégie** &gt; **Inscription d’appareil professionnel**, puis choisissez **Ajouter**.

        ![Page Créer un profil d’inscription d’appareils](../media/pol-sa-corp-enroll.png)

    2.  Entrez les détails des profils d'appareils :

        -   **Nom** : nom du profil d’inscription d’appareil. Non visible pour les utilisateurs.

        -   **Description** : description du profil d’inscription d’appareil. Non visible pour les utilisateurs.

        -   **Affiliation utilisateur** : spécifie la façon dont les appareils sont inscrits. Pour l’inscription directe, choisissez **Aucune affinité utilisateur**.

        -   **Affectation préalable du groupe d’appareils** : tous les appareils qui ont ce profil appartiennent initialement à ce groupe. Vous pouvez réaffecter les appareils après l'inscription.

            [!INCLUDE[groups deprecated](../includes/group-deprecation.md)]

    3.  Choisissez **Enregistrer le profil** pour ajouter le profil.

5.  Exportez un profil en tant que fichier .mobileconfig à déployer sur des appareils iOS :

    1.   Sélectionnez le profil d’appareil que vous avez créé.

    2.   Choisissez **Exporter** dans la barre des tâches.

    3.   Choisissez **Télécharger le profil** et enregistrez le fichier .mobileconfig téléchargé.

6.  Transférez le fichier en copiant le fichier .mobileconfig téléchargé sur un ordinateur Mac.
    > [!NOTE]
    > L’URL du profil d’inscription est valide pendant les deux semaines qui suivent son exportation. Après deux semaines, vous devez exporter une nouvelle URL de profil d’inscription pour inscrire des appareils iOS avec l’Assistant Configuration.

7.  Préparez l’appareil avec Apple Configurator. Les appareils iOS sont connectés à l'ordinateur Mac et inscrits pour la gestion des appareils mobiles.

    1.  Sur un ordinateur Mac, ouvrez **Apple Configurator 2.0**.

    2.  Connectez l’appareil iOS à l’ordinateur Mac avec un câble USB. Fermez **Photos**, **iTunes** et toutes les autres applications qui s’ouvrent quand l’appareil est détecté.

    3.  Dans Apple Configurator, choisissez l’appareil iOS connecté, puis cliquez sur le bouton **Ajouter**. Les options qui peuvent être ajoutées à l’appareil s’affichent dans la liste déroulante. Choisissez **Profils**.

    4.  Utilisez le sélecteur de fichiers pour sélectionner le fichier .mobileconfig que vous avez exporté à partir d’Intune, puis choisissez **Ajouter**. Le profil est ajouté à l’appareil.  Si l’appareil est **Non supervisé**, l’installation nécessite d’être acceptée sur l’appareil.

8.  Vous êtes prêt à installer le profil sur l’appareil iOS. L’appareil doit avoir terminé l’Assistant Configuration et être prêt à l’emploi. Si l’inscription entraîne des déploiements d’applications, un ID Apple doit être configuré sur l’appareil, car les déploiements d’applications nécessitent de s’être connecté à l’APP Store avec un ID Apple.

    1.  Déverrouillez l’appareil iOS.

    2.  Dans la boîte de dialogue **Install profile** (Installer le profil) de **Management profile** (Gestion du profil), choisissez **Install** (Installer).

    3.  Spécifiez le code d’accès d’appareil (**Device Passcode**) ou l’**Apple ID**, si nécessaire.

    4.  Acceptez l’avertissement (**Warning**), puis choisissez **Install** (Installer).

    5.  Acceptez l’avertissement distant (**Remote Warning**), puis choisissez **Trust** (Approuver).

    6.  Quand la boîte de dialogue **Profile Installed** (Profil installé) confirme que le profil est **installé**, cliquez sur **Done** (Terminé).

9.  Sur l’appareil iOS, ouvrez **Settings** (Réglages) et accédez à **General** (Général) &gt; **Device Management**(Gestion des appareils) &gt; **Management Profile** (Profil de gestion). Assurez-vous que l’installation du profil est répertoriée, puis vérifiez les restrictions de stratégie iOS et les applications installées. L’affichage des applications et des restrictions de stratégie sur l’appareil peut prendre jusqu’à dix minutes.

10.  Distribuez des appareils. L’appareil iOS est maintenant inscrit et géré dans Intune.

