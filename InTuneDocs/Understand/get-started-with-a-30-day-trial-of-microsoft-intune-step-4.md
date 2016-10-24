---
title: "Créer des stratégies et publier une application pour les utilisateurs | Microsoft Intune"
description: "Cette rubrique explique comment créer des stratégies et publier une application lorsque vous vous inscrivez à un essai gratuit de 30 jours d’Intune"
keywords: 
author: lindavr
ms.author: lindavr
manager: angrobe
ms.date: 08/09/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c3a17884-442a-44f5-bc81-4589e823f65e
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 581e880fa4308ec627f5b2c1242fb5b30b713743
ms.openlocfilehash: 0fbc8fc23ce65987e4694bce0748362d8ce10153


---


# Créer des stratégies et publier une application pour les utilisateurs de la version d’évaluation
Les stratégies Intune fournissent des paramètres qui vous permettent de contrôler les paramètres de sécurité des appareils mobiles, de gérer les paramètres du Pare-feu Windows et d’Endpoint Protection pour les ordinateurs, et de déployer des applications. Si, à l’issue de la période d’évaluation, vous prévoyez d’utiliser Intune pour des appareils que vous configurez pour la production, il est absolument essentiel de suivre les instructions contenues dans les rubriques [Gérer des paramètres et des fonctionnalités sur vos appareils avec des stratégies Microsoft Intune](/intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies) et [Contribuer à la sécurisation des PC Windows avec Endpoint Protection pour Microsoft Intune](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune).

Vous pouvez effectuer deux types d'installations d'applications à l'aide d'Intune. La première est une **installation requise**, qui déploie automatiquement l'application sur les ordinateurs gérés. L’autre est une **installation disponible**, qui déploie l’application (ou un lien vers l’application) dans le portail d’entreprise Intune pour laisser le choix aux utilisateurs de l’installer sur leurs ordinateurs ou sur leurs appareils mobiles.

Avant de déployer des applications à l'aide d'Intune, assurez-vous de disposer des licences appropriées pour publier, distribuer et utiliser les applications. L’espace de travail **Licences** vous permet d’ajouter et de gérer des informations sur les contrats de licence pour les applications ou les logiciels achetés dans le cadre de contrats de licence en volume Microsoft et pour les applications ou les logiciels Microsoft ou d’autres éditeurs achetés par d’autres moyens. Vous pouvez ensuite créer des rapports de licence qui affichent des informations sur l'utilisation des licences gérées à l'échelle de votre entreprise pour vous tenir informé de l'activité d'utilisation de licences.

Dans ces étapes, vous allez configurer une stratégie de configuration d'appareil mobile et une stratégie de pare-feu d'ordinateur Windows, puis configurer Skype en tant qu'installation disponible pour les appareils mobiles une fois ceux-ci inscrits. Après avoir ajouté et déployé une nouvelle stratégie, tous les utilisateurs ou appareils du groupe dans lequel vous avez déployé la stratégie héritent des paramètres comme stratégie de base. Vous pouvez par la suite toujours examiner et modifier les détails de ces stratégies à partir de l'espace de travail **Stratégie** dans la console d'administration.

## Créer et déployer une stratégie de configuration d'appareil mobile

1.  Ouvrez la [console d'administration Intune](https://manage.microsoft.com/).

2.  Dans le volet de gauche, cliquez sur l’icône **Stratégie**.

3.  Dans la liste **Tâches** de la page **Vue d’ensemble de la stratégie**, choisissez **Ajouter une stratégie**.

4.  Dans la liste des stratégies, développez la plateforme pour laquelle vous voulez créer une stratégie, sélectionnez **Configuration générale**, choisissez **Créer et déployer une stratégie avec les paramètres recommandés**, puis cliquez sur **Créer une stratégie**.

5.  Quand vous êtes invité à **Sélectionner les groupes sur lesquels vous souhaitez déployer cette stratégie**, sélectionnez **Utilisateurs de mon évaluation** dans la liste, puis cliquez sur **Ajouter** &gt; **OK**.

Votre stratégie s'affiche dans la liste des stratégies de configuration et a été déployée dans le groupe **Mes utilisateurs d'évaluation** . Double-cliquez sur la stratégie pour afficher ses paramètres.

## Publier l'application Skype pour les appareils mobiles

1.  Dans la [console d’administration Intune](https://manage.microsoft.com/), sélectionnez l’icône **Applications**, puis **Applications** &gt; **Ajouter une application**. Si l'invite s'affiche, saisissez votre identifiant et votre mot de passe.

    > [!NOTE]
    > Quand vous démarrez l' **Éditeur de logiciel Intune** pour la première fois, un bref délai se produit pendant l'installation de l'application.

2.  Lisez l’avertissement de sécurité, puis choisissez **Exécuter**.

3.  Dans la page **Avant de commencer**, choisissez **Suivant**.

4.  Dans la page **Installation du logiciel** dans **Spécifier comment ce logiciel doit être mis à disposition des appareils**, sélectionnez **Lien externe**.

5.  Entrez le lien externe pour le logiciel dans **Spécifiez l’URL**, puis cliquez sur **Suivant**. Veillez à faire précéder l’URL de **https://**. Pour l'application Skype, utilisez le lien ci-dessous qui correspond à la plateforme d'appareil mobile que vous utilisez :

    -   **iOS :** [https://itunes.apple.com/us/app/skype-for-iphone/id304878510?mt%3D8](https://itunes.apple.com/us/app/skype-for-iphone/id304878510?mt%3D8)

    -   **Android :** [https://play.google.com/store/apps/details?id=com.skype.raider](https://play.google.com/store/apps/details?id=com.skype.raider)

    -   **Windows Phone 8.1 :** [http://www.windowsphone.com/en-us/store/app/skype/c3f8e570-68b3-4d6a-bdbb-c0a3f4360a51](http://www.windowsphone.com/en-us/store/app/skype/c3f8e570-68b3-4d6a-bdbb-c0a3f4360a51)

6.  Dans la page **Description du logiciel**, fournissez les informations que les utilisateurs pourront afficher pour le logiciel dans le portail d’entreprise, puis cliquez sur **Suivant**. Les paramètres suivants sont disponibles (cet exemple fait référence à Skype) :

    -   **Éditeur :** entrez le nom de l’éditeur, **Microsoft**

    -   **Nom :** entrez **Skype**

    -   **Description :** entrez la description du logiciel, par exemple, **Application de communication Skype**

    -   **Catégorie :** sélectionnez la catégorie qui correspond le mieux à ce logiciel, en l'occurrence, **Collaboration**

    -   **Affiche comme application proposée et la met en avant dans le portail d’entreprise :** sélectionnez cette option pour afficher l’application en premier plan dans le portail d’entreprise sur les appareils mobiles.

    -   **Icône :**  (facultatif) choisissez d'associer ou non une icône au logiciel. La taille d'icône maximale est de 250 x 250 pixels, mais la taille recommandée est de 32 x 32 pixels.

7.  Dans la page **Résumé**, vérifiez les informations du logiciel, puis cliquez sur **Télécharger**. Cliquez sur **Fermer** pour quitter l’Assistant.

8.  Dans la [console d’administration Intune](https://manage.microsoft.com/), choisissez **Applications** &gt; **Applications** &gt; **Skype** &gt; **Gérer le déploiement**.

9. Dans la page **Sélectionner des groupes**, sélectionnez **Utilisateurs de mon évaluation** pour déployer le logiciel vers ce groupe d’utilisateurs, puis cliquez sur **Ajouter** &gt; **Suivant**.

10. Dans la page **Action de déploiement** , sélectionnez **Installation disponible** dans la colonne **Approbation** pour chaque groupe.

11. Choisissez **Terminer**.

L’application Skype peut maintenant être installée sur des appareils mobiles à partir du portail d’entreprise, mais vous devez d’abord installer le logiciel Intune sur les PC et les appareils mobiles.

### Étapes suivantes
Félicitations ! Vous venez d’effectuer l’étape 4 de la procédure pas à pas de la *version d’évaluation de Microsoft Intune*.

>[!div class="step-by-step"]

>[&larr; **Créer des groupes**](.\get-started-with-a-30-day-trial-of-microsoft-intune-step-3.md)     [**Inscrire des appareils** &rarr;](.\get-started-with-a-30-day-trial-of-microsoft-intune-step-5.md)  



<!--HONumber=Oct16_HO2-->


