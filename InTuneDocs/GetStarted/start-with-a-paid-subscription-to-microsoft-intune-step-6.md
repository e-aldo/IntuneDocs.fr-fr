---
title: "Créer des stratégies et publier une application | Microsoft Intune"
description: "Explique comment créer des stratégies et publier un exemple d’application pour votre abonnement Intune"
keywords: 
author: barlanmsft
manager: angrobe
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e0d8e98f-7dd8-4cbf-887c-a9af63ffe970
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 6d1c7c670341692d4ea0c823e4a9a96746b83067
ms.openlocfilehash: da46c83d43f4ce4c5ae22b87638ad747a57b9e3f


---

# créer des stratégies et publier une application
Les stratégies Intune fournissent des paramètres qui vous permettent de contrôler les paramètres de sécurité des appareils mobiles, de gérer les paramètres du Pare-feu Windows et d’Endpoint Protection pour les ordinateurs, et de déployer des applications. Pour plus d’informations, consultez [Gérer des paramètres et des fonctionnalités sur vos appareils avec des stratégies Microsoft Intune](/Intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies) et [Contribuer à la sécurisation des PC Windows avec Endpoint Protection pour Microsoft Intune](/Intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune).

Vous pouvez effectuer deux types d'installations d'applications à l'aide d'Intune. La première est une **installation requise**, qui déploie automatiquement l'application sur les ordinateurs gérés. L’autre est une **installation disponible**, qui déploie l’application (ou un lien vers l’application) dans le portail d’entreprise Intune pour laisser le choix aux utilisateurs de l’installer sur leurs ordinateurs ou sur leurs appareils mobiles.

Les étapes suivantes vous aideront à configurer une stratégie de configuration d’appareil mobile, une stratégie de pare-feu d’ordinateur Windows et à configurer Skype en tant qu’installation disponible pour les appareils mobiles une fois ceux-ci inscrits.

> [!TIP]
> Après avoir ajouté et déployé une nouvelle stratégie, tous les utilisateurs ou appareils du groupe dans lequel vous avez déployé la stratégie héritent des paramètres comme stratégie de base. Vous pouvez par la suite toujours examiner et modifier les détails de ces stratégies à partir de l'espace de travail Stratégie.


## Créer et déployer une stratégie de configuration d'appareil mobile

1.  Ouvrez la [console d'administration Intune](https://manage.microsoft.com/).

2.  Dans le volet de gauche, cliquez sur l’icône **Stratégie**.

    ![admin-console-policy-workspace](./media/policy.png)

3.  Dans la liste **Tâches** de la page **Vue d’ensemble de la stratégie**, choisissez **Ajouter une stratégie**.

4.  Dans la liste des stratégies, développez la plateforme pour laquelle vous voulez créer une stratégie, puis choisissez **Configuration générale** > **Créer et déployer une stratégie avec les paramètres recommandés** > **Créer une stratégie**.

> [!NOTE]
> Il n’existe aucun paramètre recommandé pour les stratégies de configuration d’appareil, car vous pouvez choisir parmi de nombreuses options. Vous devez créer une stratégie de configuration d’appareil personnalisée.


5.  Quand vous êtes invité à **Sélectionner les groupes sur lesquels vous souhaitez déployer cette stratégie**, choisissez un groupe dans la liste des groupes disponibles, puis sélectionnez **Ajouter** > **OK**.

Votre stratégie s’affiche dans la liste des stratégies de configuration et a été déployée dans le groupe **Utilisateurs Intune**. Double-cliquez sur la stratégie pour afficher ses paramètres.

## Publier l'application Skype pour les appareils mobiles

1.  Dans la [console d’administration Intune](https://manage.microsoft.com/), sélectionnez l’icône **Applications**, puis **Applications** > **Ajouter une application**. Si vous y êtes invité, entrez vos informations d'identification de compte [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].

    ![admin-console-apps-workspace](./media/apps.png)

    > [!NOTE]
    > Quand vous démarrez l' **Éditeur de logiciel Intune** pour la première fois, un bref délai se produit pendant l'installation de l'application.

2.  Lisez l’avertissement de sécurité, puis choisissez **Exécuter**.

3.  Dans la page **Avant de commencer**, choisissez **Suivant**.

4.  Dans la page **Installation du logiciel**, dans **Spécifier comment ce logiciel doit être mis à disposition des appareils**, choisissez **Lien externe**.

5.  Entrez le lien externe pour le logiciel dans **Spécifiez l’URL**, puis cliquez sur **Suivant**. Veillez à faire précéder l’URL de **http://**. Pour l'application Skype, utilisez le lien ci-dessous qui correspond à la plateforme d'appareil mobile que vous utilisez :

    -   **iOS :**   [https://itunes.apple.com/us/app/skype-for-iphone/id304878510?mt%3D8](https://itunes.apple.com/us/app/skype-for-iphone/id304878510?mt%3D8)

    -   **Android :**  [https://play.google.com/store/apps/details?id=com.skype.raider](https://play.google.com/store/apps/details?id=com.skype.raider)

    -   **Windows Phone 8 ou Windows Phone 8.1 :**  [http://www.windowsphone.com/en-us/store/app/skype/c3f8e570-68b3-4d6a-bdbb-c0a3f4360a51](http://www.windowsphone.com/en-us/store/app/skype/c3f8e570-68b3-4d6a-bdbb-c0a3f4360a51)

6.  Dans la page **Description du logiciel**, fournissez les informations que les utilisateurs pourront afficher pour le logiciel dans le portail d’entreprise, puis cliquez sur **Suivant**. Les paramètres suivants sont disponibles (cet exemple fait référence à Skype) :

    -   **Éditeur :** entrez le nom de l'éditeur, « Microsoft ».

    -   **Nom :** entrez **Skype**

    -   **Description :** entrez la description du logiciel, par exemple, **Application de communication Skype**

    -   **Catégorie :** sélectionnez la catégorie qui correspond le mieux à ce logiciel, en l'occurrence, **Collaboration**

    -   **Affiche comme application proposée et la met en avant dans le portail d’entreprise :** sélectionnez cette option pour afficher l’application en premier plan dans le portail d’entreprise sur les appareils mobiles.

    -   **Icône :** choisissez d’associer ou non une icône au logiciel. La taille maximale de l’icône facultative est de 250 x 250 pixels et la taille recommandée est de 32 x 32 pixels.

7.  Dans la page **Résumé**, vérifiez les informations du logiciel, puis cliquez sur **Télécharger**. Cliquez sur **Fermer** pour quitter l’Assistant.

8.  Dans la [console d’administration Intune](https://manage.microsoft.com/), choisissez **Applications** > **Applications** > **Skype** > **Gérer le déploiement**.

9. Dans la page **Sélectionner des groupes**, choisissez **Utilisateurs Intune** pour déployer le logiciel sur ce groupe d’utilisateurs, puis choisissez **Ajouter** > **Suivant**.

10. Dans la page **Action de déploiement** , sélectionnez **Installation disponible** dans la colonne **Approbation** pour chaque groupe.

11. Choisissez **Terminer**.

L’application Skype peut maintenant être installée sur des appareils mobiles à partir du portail d’entreprise, mais vous devez d’abord installer le logiciel [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] sur les ordinateurs et les appareils mobiles.


### Étapes suivantes
Félicitations ! Vous venez d’effectuer l’étape 6 du *guide de démarrage rapide Intune*.

>[!div class="step-by-step"]

>[&larr;**Organiser les utilisateurs et les appareils**](.\start-with-a-paid-subscription-to-microsoft-intune-step-5.md)       [**Personnaliser le portail d’entreprise** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-7.md)  



<!--HONumber=Aug16_HO4-->


