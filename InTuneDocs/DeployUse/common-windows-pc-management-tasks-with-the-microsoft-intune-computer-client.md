---
# required metadata

title: Tâches courantes de gestion des PC Windows | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: eb912c73-54d2-4d78-ac34-3cbe825804c7

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Tâches courantes de gestion des PC Windows avec le client Microsoft Intune
Passez en revue les tâches de cette rubrique pour découvrir comment gérer vos ordinateurs qui exécutent le client Intune. Si vous n’avez pas encore installé le client sur vos ordinateurs, consultez [Installer le client de PC Windows avec Microsoft Intune](install-the-windows-pc-client-with-microsoft-intune.md).


## Utiliser des stratégies pour simplifier la gestion des PC
### Gérer le Pare-feu Windows
Les stratégies simplifient l'administration des paramètres du Pare-feu Windows sur les ordinateurs gérés. Pour plus d’informations, consultez [Protéger les PC Windows à l’aide de stratégies de Pare-feu Windows dans Microsoft Intune](help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune.md).

### Gérer Microsoft Intune Center
Microsoft Intune Center permet aux utilisateurs d’effectuer les opérations suivantes :

-   Obtenir des applications à partir du portail d'entreprise.

-   Rechercher des mises à jour.

-   Gérer Microsoft Intune Endpoint Protection.

-   Demander l'assistance à distance.

Microsoft Intune Center est installé sur tous les ordinateurs gérés. Vous pouvez configurer les paramètres suivants dans une stratégie Intune. Ceux-ci s’affichent pour les utilisateurs dans Microsoft Intune Center :

|Paramètre de stratégie|Détails|
|------------------|--------------------|
|**Nom**|Nom de l'administrateur responsable de la gestion de l'ordinateur.<br /><br />Longueur maximale : 40 caractères|
|**Numéro de téléphone**|Numéro de téléphone de l'administrateur responsable de la gestion de l'ordinateur.<br /><br />Longueur maximale : 20 caractères|
|**Adresse de messagerie**|Adresse e-mail de l'administrateur responsable de la gestion de l'ordinateur.<br /><br />Longueur maximale : 40 caractères|
|**Nom du site web**|Nom de votre site web de support pour les utilisateurs.<br /><br />Longueur maximale : 40 caractères|
|**URL du site web**|L'URL de votre site web de support.<br /><br />Longueur maximale : 150 caractères|
|**Remarques**|Remarque affichée pour les utilisateurs.<br /><br />Longueur maximale : 120 caractères|

### Gérer les paramètres des mises à jour logicielles
Utilisez des stratégies pour configurer les paramètres que les ordinateurs gérés utilisent pour rechercher et télécharger des mises à jour logicielles publiées par Microsoft et d'autres parties. Pour plus d’informations, consultez [Maintenir des PC Windows à jour avec les mises à jour logicielles](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md).

### Gérer les paramètres Endpoint Protection
Utilisez des stratégies pour configurer les paramètres Endpoint Protection à déployer ensuite sur les ordinateurs gérés. Cela inclut les planifications de l'analyse, les actions à entreprendre lorsqu'un programme malveillant est détecté et bien plus encore. Pour plus d’informations, consultez [Contribuer à la sécurisation des PC Windows avec Endpoint Protection pour Microsoft Intune](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md).

## Afficher l'Inventaire matériel et logiciel
Intune recueille des informations détaillées sur le matériel et les logiciels des ordinateurs gérés. Utilisez les informations contenues dans les procédures suivantes pour apprendre à créer :

-   Un rapport qui répertorie les informations sur les capacités matérielles de vos ordinateurs.

-   Un rapport qui répertorie les logiciels installés sur chaque ordinateur.

-   Procédure d'actualisation d'un inventaire des ordinateurs pour vous assurer que les données du rapport sont récentes.

### Pour afficher les informations concernant vos ordinateurs

1.  Dans la [console d’administration Microsoft Intune](https://manage.microsoft.com/), choisissez **Rapports** &gt; **Rapports d’inventaire des ordinateurs**.

2.  Dans la page **Créer un rapport** , acceptez les valeurs par défaut ou personnalisez-les pour filtrer les résultats qui seront renvoyés par le rapport. Par exemple, vous pouvez sélectionner que seuls les ordinateurs qui exécutent Windows 8.1 s'afficheront dans le rapport.

3.  Choisissez **Afficher le rapport** pour ouvrir le **Rapport d’inventaire informatique** dans une nouvelle fenêtre.

    Vous pouvez trier le rapport en fonction des différentes colonnes, telles que le **Nom**, le **Type de châssis** ou le **Fabricant** en sélectionnant chaque en-tête de colonne.

### Pour afficher les logiciels installés sur vos ordinateurs

1.  Dans la [console d’administration Microsoft Intune](https://manage.microsoft.com/), choisissez **Rapports** &gt; **Rapports de logiciels détectés**.

2.  Dans la page **Créer un rapport** , acceptez les valeurs par défaut ou personnalisez-les pour filtrer les résultats qui seront renvoyés par le rapport. Par exemple, vous pouvez décider que seuls les logiciels publiés par Microsoft seront affichés dans le rapport.

3.  Choisissez **Afficher le rapport** pour ouvrir le **Rapport de logiciels détectés** dans une nouvelle fenêtre.

    Vous pouvez trier le rapport en fonction des différentes colonnes, telles que le **Nom**, l’**Éditeur** ou la **Catégorie** en sélectionnant chaque en-tête de colonne. Vous pouvez développer les mises à jour dans la liste pour afficher plus de détails (par exemple les ordinateurs sur lesquels elles sont installées) en cliquant sur la flèche directionnelle à côté de l'élément de liste.

### Pour actualiser les ressources de l'ordinateur pour vérifier qu'elles sont récentes

1.  Dans la [console d’administration Microsoft Intune](https://manage.microsoft.com/), choisissez **Groupes** &gt; **Tous les appareils** (ou un autre groupe qui contient l’ordinateur pour lequel vous souhaitez actualiser l’inventaire).

2.  Sélectionnez un ordinateur ou maintenez la touche **Ctrl** enfoncée pour sélectionner plusieurs ordinateurs.

3.  Dans la barre des tâches, choisissez **Tâches à distance** &gt; **Actualiser l’inventaire**.

4.  Pour afficher l’état des tâches, choisissez **Tâches à distance** dans le coin inférieur droit de la page.

    La boîte de dialogue **État de la tâche** affiche les tâches à distance en cours, l'état de la tâche, le nom de l'appareil et toutes les erreurs signalées et fournit un lien permettant de corriger ces informations.


## Redémarrer à distance un PC Windows

1.  Dans la [console d’administration Microsoft Intune](https://manage.microsoft.com/), choisissez **Groupes** &gt; **Tous les appareils** (ou un autre groupe qui contient l’ordinateur que vous voulez redémarrer).

2.  Sélectionnez un ou plusieurs ordinateurs, puis cliquez sur **Tâches à distance** &gt; **Redémarrer l’ordinateur**.

3.  Pour afficher l’état des tâches, choisissez **Tâches à distance** dans le coin inférieur droit de la page.

4.  Dans la boîte de dialogue **État de tâche** , passez en revue les tâches à distance en cours, l'état de la tâche, le nom d'appareil et les erreurs signalées.

## Mettre hors service un ordinateur

1.  Dans la [console d’administration Microsoft Intune](https://manage.microsoft.com/), choisissez **Groupes** &gt; **Tous les appareils** (ou un autre groupe qui contient l’ordinateur que vous voulez mettre hors service).

2.  Sélectionnez les appareils que vous souhaitez mettre hors service, puis choisissez **Mettre hors service/Réinitialiser**.

Pour réinscrire un ordinateur dans Intune, réinstallez le logiciel client sur l’ordinateur à l’aide des informations contenues dans la rubrique [Installer le client de PC Windows avec Microsoft Intune](install-the-windows-pc-client-with-microsoft-intune.md).

Si un ordinateur ne peut pas se connecter à Intune, un message s’affiche dans l’espace de travail **Tableau de bord**.

Lorsque vous mettez hors service un ordinateur :

-   Il est supprimé de l’inventaire Intune et la licence associée à l’ordinateur devient disponible pour une réutilisation.

-   Son état ne s’affiche plus dans la console Intune.

-   Intune supprime le logiciel client de l’ordinateur. Si l’ordinateur n’est pas connecté au service Intune, le logiciel client sera supprimé la prochaine fois qu’il se connectera.

-   Microsoft Intune Endpoint Protection est supprimé de l’ordinateur. Si l’ordinateur dispose d’une autre application de point de terminaison installée et qu’elle est désactivée, cette application peut être réactivée après la suppression de Microsoft Intune Endpoint Protection pour garantir la protection de vos ordinateurs.

-   Toutes les stratégies sont supprimées de l'ordinateur et les valeurs qui ont été définies par les stratégies vont être modifiées.

-   L’ordinateur ne reçoit plus les mises à jour de logiciels ou les mises à jour de définition des programmes malveillants à partir du service Intune.

-   Selon la façon dont ils sont configurés, les ordinateurs mis hors service peuvent continuer à recevoir des mises à jour à l'aide de Windows Server Update Services, Windows Update ou Microsoft Update.

    > [!IMPORTANT]
    > Si le logiciel client a été installé à l'aide d'un objet de stratégie de groupe, vous devez supprimer celui-ci pour pouvoir supprimer le logiciel client afin d'empêcher la réinstallation du logiciel.

    Si la désinstallation du client échoue, lisez [Résoudre les problèmes de protection de point de terminaison](/intune/troubleshoot/troubleshoot-endpoint-protection-in-microsoft-intune) pour obtenir une aide supplémentaire.

## Gérer la liaison utilisateur-appareil
Avant de pouvoir déployer des logiciels vers un utilisateur, vous devez lier l'utilisateur à un ordinateur. Vous pouvez associer un utilisateur à plusieurs ordinateurs, mais chaque ordinateur ne peut être lié qu'à un seul utilisateur. Les utilisateurs sont automatiquement liés à tous les ordinateurs qu’ils inscrivent dans Intune à l’aide du portail de l’entreprise.

### Pour lier un utilisateur à un ordinateur

1.  Dans la [console d’administration Microsoft Intune](https://manage.microsoft.com/), choisissez **Groupes** &gt; **Tous les appareils** (ou un autre groupe qui contient l’ordinateur que vous voulez lier à un utilisateur).

2.  Sélectionnez l’ordinateur que vous souhaitez lier à un utilisateur, puis choisissez **Lier un utilisateur**.

    La boîte de dialogue **Lier un utilisateur** affiche une liste des utilisateurs disponibles avec leur nom complet, leur ID utilisateur, ainsi que le nombre d'ordinateurs lié à chacun. Si un utilisateur est déjà lié à l'ordinateur sélectionné, son nom et ID utilisateur s'affichent sous **Utilisateur actuel**. Si l’ordinateur n’est lié à aucun utilisateur, **Aucun utilisateur** est affiché sous **Utilisateur actuel**.

3.  Effectuez l'une des opérations suivantes :

    -   Pour laisser l’ordinateur lié à son utilisateur actuel, le cas échéant, choisissez **Annuler**.

    -   Pour supprimer le lien vers l’utilisateur actuel, le cas échéant, choisissez **Supprimer le lien**&gt;**OK**.

    -   Pour relier l'ordinateur à un nouvel utilisateur, sélectionnez un utilisateur dans la liste **Tous les utilisateurs** . Vérifiez que les données utilisateur sont correctes, puis choisissez **OK**.

> [!TIP]
> Si vous souhaitez limiter la capacité des utilisateurs finaux à se lier à des ordinateurs, activez l’option **Limiter la capacité des utilisateurs à se lier à des ordinateurs** dans la stratégie **Paramètres de l’Agent Microsoft Intune**.

## Répondre à une demande de support à distance
Les utilisateurs peuvent demander une assistance en utilisant l'Assistance à distance via Microsoft Easy Assist qui est installé automatiquement sur les ordinateurs gérés. Quand une demande est faite, une alerte s’affiche dans la console Intune.

> [!IMPORTANT]
> L'assistance à distance n'est pas prise en charge sur les ordinateurs exécutant Windows 8 ou version ultérieure.
>
> Si vous acceptez une demande d'assistance à distance à partir d'un ordinateur qui ne dispose pas de Microsoft Easy Assist, l'utilisateur est invité à l'installer. L'ordinateur doit être redémarré après l'installation. Envisagez de précharger Microsoft Easy Assist sur les ordinateurs de vos utilisateurs afin d'éviter ce redémarrage.

### Pour gérer une demande d'assistance à distance

1.  Dans la [console d’administration Microsoft Intune](https://manage.microsoft.com/), choisissez **Alertes** &gt; **Assistance à distance**.

2.  Sélectionnez une demande d'assistance à distance dans la liste **Alertes** pour ouvrir la page de propriétés de la requête.

3.  Choisissez **Approuver une demande et lancer l’assistance à distance** pour ouvrir une boîte de dialogue qui fournit des options pour la résolution de l’alerte.

4.  Effectuez l'une des opérations suivantes :

    -   **Accepter la demande** : pour participer à la session à distance, choisissez **Accepter la demande d’assistance à distance**.

        L'utilisateur voit le message : **Votre demande a été acceptée. Suivez les instructions dans Easy Assist pour partager un programme ou votre bureau avec votre administrateur système**.

        > [!IMPORTANT]
        > Vous ne pouvez pas accepter une demande d’assistance à distance sur un ordinateur Mac qui exécute la console d’administration Intune.

    -   **Refuser la demande** : fermez la fenêtre **Afficher les informations de dépannage**, puis choisissez **Fermer cette alerte** dans la fenêtre de propriétés des alertes.

        La demande est fermée et l'utilisateur voit un message indiquant que la demande a été refusée. Pour demander à nouveau une assistance à distance, l'utilisateur doit envoyer une nouvelle demande d'assistance à distance. Si vous fermez accidentellement une alerte d'assistance à distance, contactez l'utilisateur qui l'avait envoyée et demandez-lui d'envoyer une nouvelle demande.


<!--HONumber=May16_HO1-->


