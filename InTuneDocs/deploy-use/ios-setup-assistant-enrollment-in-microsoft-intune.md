---
title: "Inscrire des appareils iOS avec l’Assistant Configuration | Microsoft Docs"
description: "Inscrivez des appareils iOS d’entreprise en utilisant l’outil Apple Configurator pour réinitialiser vos appareils aux paramètres d’usine et les préparer à l’exécution de l’Assistant de configuration."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 02/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 46e5b027-4280-4809-b45f-651a6ab6d0cd
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: a2e840797c06322b9efc59438e0675e57b7cdb24
ms.openlocfilehash: facae5f49b52760dcea0653bd261e16e13e11bbf


---

# <a name="enroll-ios-devices-with-apple-configurator-by-using-setup-assistant"></a>Inscription des appareils iOS avec Apple Configurator à l’aide de l’Assistant de configuration

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Intune prend en charge l’inscription d’appareils iOS d’entreprise à l’aide d’[Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017) s’exécutant sur un ordinateur Mac. Ce processus réinitialise l’appareil aux paramètres d’usine et le prépare à exécuter l’Assistant de configuration, en installant les stratégies de l’entreprise pour le nouvel utilisateur de l’appareil.

>[!NOTE]
>Cette méthode d’inscription ne peut pas être utilisée avec celle du [gestionnaire d’inscription d’appareil](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md).

À l’aide d’Apple Configurator, vous pouvez réinitialiser un appareil iOS aux paramètres d’usine et le préparer à être configuré pour son nouvel utilisateur. Cette méthode implique de connecter l’appareil iOS à un ordinateur Mac via une connexion USB pour configurer l’inscription d’entreprise, et suppose que vous utilisez Apple Configurator 2.0. La plupart des scénarios nécessitent que la stratégie appliquée à l’appareil iOS comprenne l’**affinité utilisateur** pour activer l’application Portail d’entreprise Intune.

## <a name="prerequisites-for-enrolling-ios-devices-by-using-apple-configurator-with-setup-assistant"></a>Prérequis pour inscrire des appareils iOS à l’aide d’Apple Configurator avec l’Assistant Configuration

- [Installer un certificat APNs](set-up-ios-and-mac-management-with-microsoft-intune.md)

- Vérifier que vous pouvez accéder physiquement aux appareils iOS &mdash; Les appareils doivent être réinitialisés aux paramètres d’usine sans protection par mot de passe

- Obtenir les numéros de série des appareils &mdash; Consulter [Localisation du numéro de série de votre produit Apple](https://support.apple.com/en-us/HT204308)

- Disposer de câbles de connexion USB

- Disposer d’un ordinateur Mac avec [Apple Configurator 2.0](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12)


## <a name="steps-to-enroll-ios-devices-by-using-apple-configurator-with-setup-assistant"></a>Étapes d’inscription des appareils iOS à l’aide d’Apple Configurator avec l’Assistant Configuration

Les étapes suivantes décrivent la première inscription d’appareils iOS à l’aide d’Apple Configurator avec l’Assistant Configuration. Vous pourrez répéter certaines de ces étapes pour ajouter et supprimer des appareils dans votre organisation, par exemple, ajouter ou supprimer des numéros de série, comme décrit plus bas.

### <a name="create-mobile-device-groups-optional"></a>Créer des groupes d’appareils mobiles (facultatif)

Si votre entreprise a besoin de groupes d’appareils mobiles pour faciliter la gestion des appareils, vous pouvez créer ces groupes. Pour plus d’informations, consultez la page [Utiliser des groupes pour gérer les utilisateurs et les appareils avec Microsoft Intune](use-groups-to-manage-users-and-devices-with-microsoft-intune.md).

### <a name="create-a-profile-for-devices"></a>Créer un profil pour des appareils

Un profil d'inscription d'appareil définit les paramètres appliqués à un groupe d'appareils.

1. Dans la [console d’administration Microsoft Intune](http://manage.microsoft.com), accédez à **Stratégie** &gt; **Inscription d’appareil professionnel**, puis choisissez **Ajouter**.

  ![Création d’un profil d’inscription d’appareils](../media/pol-sa-corp-enroll.png)

2. Entrez les détails des profils d'appareils :

   -   **Nom**&mdash;Nom du profil d’inscription d’appareil (non visible pour les utilisateurs).

   -   **Description**&mdash;Description du profil d’inscription d’appareil (non visible pour les utilisateurs).

   -   **Détails de l’inscription**&mdash;Indique comment les appareils sont inscrits.

       -   **Demander l’affinité utilisateur**&mdash;L’appareil doit être affilié à un utilisateur pendant l’installation initiale. Il peut ensuite être autorisé à accéder aux données et aux e-mails de l’entreprise. L’**affinité utilisateur** doit être configurée pour les appareils gérés par DEP qui appartiennent à des utilisateurs et doivent utiliser le portail d’entreprise pour les services tels que l’installation d’applications.

       -   **Aucune affinité utilisateur**&mdash;L’appareil n’est pas affilié à un utilisateur. Utilisez cette affiliation pour les appareils qui effectuent des tâches sans accéder aux données de l'utilisateur local. Les applications qui nécessitent l’affiliation d’un utilisateur (y compris l’application Portail d’entreprise utilisée pour l’installation des applications métier) ne fonctionneront pas.

   -   **Affectation préalable du groupe d’appareils**&mdash;Tous les appareils déployés avec ce profil appartiennent initialement à ce groupe. Vous pouvez réaffecter les appareils après l'inscription.

   > [!Important]
   > L’attribution de groupes passe d’Intune à Azure Active Directory. Une fois que votre compte Intune reçoit la mise à jour applicable, l’option **Attribuer des appareils au groupe suivant** ne s’affiche pas. [En savoir plus](/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune#changes-to-intune-group-assignments).

   -  **Device Enrollment Program (DEP)**&mdash;Vous ne pouvez pas utiliser Apple Device Enrollment Program (DEP) avec l’inscription par le biais de l’Assistant de configuration. Vérifiez que ce commutateur est **désactivé**.

3.  Choisissez **Enregistrer le profil** pour ajouter le profil.

### <a name="add-ios-devices-to-enroll-with-setup-assistant"></a>Ajouter des appareils iOS à inscrire avec l’Assistant Configuration

1. Dans la [console d’administration Microsoft Intune](http://manage.microsoft.com), accédez à **Groupes** &gt; **Tous les appareils** &gt; **Tous les appareils d’entreprise** &gt; **Tous les appareils**, puis choisissez **Ajouter des appareils**. 

   Vous pouvez ajouter des appareils de deux manières :

   ![Boîte de dialogue Ajouter des appareils](../media/pol-SA-enroll-iOS-SetupAssistant.png)

   -  **Charger un fichier CSV qui contient les numéros de série**&mdash;Créez une liste de valeurs séparées par des virgules (.csv) de deux colonnes sans en-tête, limitée à 5 000 appareils ou à 5 Mo par fichier .csv.

    |||
    |-|-|
    |&lt;Série 1&gt;|&lt;Détails de l’appareil 1&gt;|
    |&lt;Série 2&gt;|&lt;Détails de l’appareil 2&gt;|

  Dans un éditeur de texte, ce fichier .csv s’affiche comme suit :

    ```
    0000000,PO 1234
    111111111,PO 1234
    ```

  -  **Ajouter manuellement les détails des appareils** &mdash; Entrez le numéro de série et des remarques ou détails pour 15 appareils au maximum.

  Dans le panneau **Passer en revue les appareils**, vous pouvez vérifier les numéros de série. Vous pouvez également décider s’il faut remplacer les **Détails** des numéros de série réimportés, ou vous pouvez décocher la case **Remplacer** pour conserver les détails actuels. 

> [!NOTE] 
> Dans la console Administrateur Intune, les administrateurs peuvent accepter les détails associés à partir d’un fichier CSV chargé et remplacer les détails existants de chaque numéro de série. Dans le nouveau portail Azure, vous pouvez uniquement remplacer les détails de tous les numéros de série ou ignorer les nouveaux détails de tous les numéros de série.

  > [!NOTE]
  > Si, par la suite, vous voulez supprimer des appareils d’entreprise de la gestion Intune, vous devrez peut-être accéder au groupe d’appareils **Par numéro de série iOS** sous **Appareils d’entreprise préinscrits** et supprimer le numéro de série des appareils dans Intune pour désactiver leur inscription. Si Intune effectue une procédure de récupération d’urgence pendant que vous supprimez des numéros de série ou aux environs de cette période, vous devez vérifier que seuls les numéros de série des appareils actifs sont présents dans ce groupe.

2. Choisissez **Suivant**.

3. Sélectionnez les appareils à inscrire. Il n'est pas possible d'importer des numéros de série déjà inscrits ou inscrits par d'autres moyens. Cliquez sur **Suivant** pour continuer.

### <a name="assign-a-profile"></a>Attribuer un profil

Spécifiez le profil à attribuer aux appareils ajoutés de la liste des profils disponibles, vérifiez les **Détails du profil d’inscription**, puis choisissez **Terminer**. Les appareils ajoutés manuellement peuvent être affectés à n’importe quel profil d’inscription.

> [!Important]
> Actuellement, Intune vous permet de désigner un profil d’inscription d’appareil « par défaut ». Dans ce cas, les nouveaux numéros de série sont automatiquement attribués à ce profil par défaut quand vous les synchronisez avec le service Apple DEP. Dès que votre client aura migré vers le nouveau portail Azure, vous ne pourrez plus définir de profil par défaut et les numéros de série ne seront plus automatiquement attribués à ce profil. Vous devrez attribuer les numéros de série à un profil. [En savoir plus](https://docs.microsoft.com/intune-azure/enroll-devices/enroll-ios-devices-using-device-enrollment-program)

### <a name="export-a-profile-to-deploy-to-ios-devices"></a>Exporter un profil à déployer sur des appareils iOS

1. Dans la [console d’administration Microsoft Intune](http://manage.microsoft.com) accédez à **Stratégie** &gt; **Inscription d’appareil professionnel**, puis sélectionnez le profil d’appareil à déployer sur les appareils mobiles. 

2. Choisissez **Exporter** dans la barre des tâches. Copiez et enregistrez la valeur **URL de profil**. Vous la chargerez dans Apple Configurator plus tard pour définir le profil Intune utilisé par les appareils iOS.

  Vous devez modifier l’URL du profil 2.0 pour prendre en charge Apple Configurator 2. Pour cela, remplacez ce code :
    ```
    https://manage.microsoft.com/EnrollmentServer/Discovery.svc/iOS/ESProxy?id=
    ```
    Par celui-ci :

    ```
    https://appleconfigurator2.manage.microsoft.com/MDMServiceConfig?id=
    ```

   Vous allez télécharger l’URL de ce profil sur le service Apple DEP avec Apple Configurator au cours de la procédure suivante pour définir le profil Intune utilisé par les appareils iOS.



### <a name="prepare-the-device-with-apple-configurator"></a>Préparer l’appareil avec Apple Configurator

Les appareils iOS sont connectés à l'ordinateur Mac et inscrits pour la gestion des appareils mobiles.

1.  Sur un ordinateur Mac, ouvrez **Apple Configurator 2**. Dans la barre de menus, choisissez **Apple Configurator 2**, puis cliquez sur **Préférences**.

   > [!WARNING]
   > Les paramètres d'usine des appareils sont rétablis pendant le processus d'inscription. En guise de bonne pratique, vous devez réinitialiser l’appareil et l’allumer. Les appareils doivent afficher l’écran **Hello** quand vous les connectez.

2. Dans le volet Préférences, sélectionnez **Serveurs** et cliquez sur le symbole plus (« + ») pour lancer l’assistant de serveur MDM. Choisissez **Suivant**.

3. Entrez le **Nom** et l’**URL d’inscription** pour le serveur MDM issus de l’étape 6 de la section Inscription Assistant Configuration pour les appareils iOS avec Microsoft Intune. Pour l’URL d’inscription, entrez l’URL du profil d’inscription exporté depuis Intune. Choisissez **Suivant**.  

   Vous pouvez ignorer sans risque un avertissement indiquant « L’URL du serveur n’est pas vérifiée ». Pour continuer, cliquez sur **Suivant** jusqu’à ce que l’Assistant soit terminé.

4.  Connectez les appareils mobiles iOS à l’ordinateur Mac à l’aide d’un adaptateur USB.

    > [!WARNING]
    > Les paramètres d'usine des appareils sont rétablis pendant le processus d'inscription. En guise de bonne pratique, vous devez réinitialiser l’appareil et l’allumer. Les appareils doivent afficher l’écran **Hello** quand vous lancez l’Assistant de configuration.

5.  Choisissez **Préparer**. Dans le volet Prepare iOS Device (Préparer l’appareil iOS), sélectionnez **Manual** (Manuel), puis **Next** (Suivant).

6. Dans le volet Enroll in MDM Server (Inscription dans un serveur MDM), sélectionnez le nom du serveur que vous avez créé, puis cliquez sur **Next** (Suivant).

7. Dans le volet Supervise Devices (Surveiller les appareils), sélectionnez le niveau de surveillance, puis cliquez sur **Next** (Suivant).

8. Dans le volet Create an Organization (Créer une organisation), choisissez l’organisation (**Organization**) ou créez-en une, puis cliquez sur **Next** (Suivant).

9. Dans le volet Configure iOS Setup Assistant (Configurer l’Assistant d’installation iOS), choisissez les étapes à présenter à l’utilisateur, puis choisissez **Prepare** (Préparer). Si vous y êtes invité, authentifiez-vous pour mettre à jour les paramètres d’approbation.  

10. Une fois la préparation de l’appareil iOS terminée, déconnectez le câble USB.  

### <a name="distribute-devices"></a>Distribuer des appareils

Les appareils sont désormais prêts pour l'inscription d'entreprise. 

Éteignez les appareils et distribuez-les aux utilisateurs. Quand les utilisateurs allument leur appareil, l’Assistant Configuration démarre.


### <a name="see-also"></a>Voir aussi
[Prérequis pour l’inscription des appareils](prerequisites-for-enrollment.md)



<!--HONumber=Feb17_HO2-->


