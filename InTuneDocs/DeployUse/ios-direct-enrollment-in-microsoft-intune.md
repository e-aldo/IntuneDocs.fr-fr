---
# required metadata

title: Inscription directe pour les appareils iOS avec Microsoft Intune | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: a692b90c-72ae-47d1-ba9c-67a2e2576cc2

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Inscrire directement des appareils iOS en utilisant Apple Configurator
Intune prend en charge l’inscription d’appareils iOS d’entreprise avec l’outil [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017) s’exécutant sur un ordinateur Mac. Ce processus ne réinitialise pas l’appareil aux paramètres d’usine et inscrit l’appareil avec une stratégie prédéfinie. Cette méthode est destinée aux appareils n’ayant **Aucune affinité utilisateur** et implique de connecter l’appareil iOS à un ordinateur Mac via une connexion USB pour configurer l’inscription d’entreprise. L’application Portail d’entreprise n’est pas prise en charge pour les appareils inscrits directement. Cette aide suppose que vous utilisez Apple Configurator 2.0 sur un ordinateur Mac.

1.  **Créer un profil pour des appareils**
    Un profil d'inscription d'appareil définit les paramètres appliqués aux appareils. Si ce n'est déjà fait, créez un profil d'inscription d'appareil pour les appareils iOS inscrits à l'aide d'Apple Configurator.

    #### Pour créer un profil

    1.  Dans la [console d’administration Microsoft Intune](http://manage.microsoft.com), accédez à **Stratégie** &gt; **Inscription d’appareil professionnel**, puis cliquez sur **Ajouter...**.

        ![Page Créer un profil d’inscription d’appareils](../media/pol-sa-corp-enroll.png)

    2.  Entrez les détails des profils d'appareils :

        -   **Nom** : nom du profil d'inscription d'appareil. Non visible pour les utilisateurs.

        -   **Description** : description du profil d’inscription d’appareil. Non visible pour les utilisateurs.

        -   **Affiliation utilisateur** : spécifie la façon dont les appareils sont inscrits. Pour l’inscription directe, sélectionnez **Pas d’affinité utilisateur**..

        -   **Affectation préalable du groupe d’appareils** : tous les appareils déployés dans ce profil appartiennent initialement à ce groupe. Vous pouvez réaffecter les appareils après l'inscription.

    3.  Cliquez sur **Enregistrer le profil** pour ajouter le profil.

2.  **Ajouter des appareils iOS à inscrire avec Apple Configurator**
    Dans la [console d’administration Microsoft Intune](http://manage.microsoft.com), accédez à **Groupes** &gt; **Tous les appareils** &gt; **Tous les appareils d’entreprise préinscrits** &gt; **Par numéro de série iOS**, puis cliquez sur **Ajouter des appareils...**.

    ![Assistant Configuration d’iOS](../media/pol-SA-enroll-iOS-SetupAssistant.png)

      Vous pouvez ajouter des appareils de deux manières :

    -   **Charger un fichier CSV qui contient les numéros de série** : créez une liste de valeurs séparées par des virgules (.csv) de deux colonnes sans en-tête, limitée à 5000 appareils ou à 5 Mo par fichier CSV.

        |||
        |-|-|
        |&lt;Série 1&gt;|&lt;Détails de l'appareil 1&gt;|
        |&lt;Série 2&gt;|&lt;Détails de l’appareil 2&gt;|
        Dans un éditeur de texte, ce fichier .csv s'affiche comme suit :

        ```
        0000000,PO 1234
        111111111,PO 1234
        ```

    -   **Ajouter manuellement les détails des appareils** : entrez le numéro de série et les détails de cinq appareils au maximum, puis cliquez sur **Suivant**..

    > [!NOTE]
    > Si vous devez supprimer par la suite des appareils d’entreprise de la gestion Intune, vous devez retirer de Microsoft Intune les numéros de série des appareils dans le groupe **Appareils d’entreprise** pour désactiver l’inscription des appareils.  Si Intune effectue une procédure de récupération d'urgence pendant la suppression des numéros de série ou aux environs de cette période, vous devez vérifier que seuls les numéros de série des appareils actifs sont présents dans ce groupe.

3.  **Sélectionner les appareils à inscrire**
    Confirmez les appareils à inscrire. Il n'est pas possible d'importer des numéros de série déjà inscrits ou inscrits par d'autres moyens. Cliquez sur **Suivant** pour continuer.

4.  **Attribuer un profil**
    Spécifiez le profil à attribuer aux appareils ajoutés de la liste des profils disponibles, vérifiez les **Détails du profil d'inscription**, puis cliquez sur **Terminer**. Les appareils ajoutés manuellement peuvent être affectés à n’importe quel profil d’inscription.

5.  **Sélectionner un profil à déployer sur des appareils iOS**
    Dans la [console d’administration Microsoft Intune](http://manage.microsoft.com), accédez à **Stratégie** &gt; **Inscription d’appareil professionnel**, puis sélectionnez le profil d’appareil à déployer sur les appareils mobiles. Ce profil doit être que celui que vous avez attribué pour le déploiement lors de l’étape précédente. Cliquez sur **Exporter** dans la barre des tâches. Cliquez sur **Télécharger le profil** et enregistrez le fichier .mobileconfig téléchargé.

6.  **Transférer le fichier**
    Copiez le fichier .mobileconfig téléchargé sur un ordinateur Mac.
    > [!NOTE]
    > L’URL du profil d’inscription est valide pendant les deux semaines qui suivent son exportation. Après deux semaines, vous devez exporter une nouvelle URL de profil d’inscription pour inscrire des appareils iOS avec l’Assistant Configuration.
7.  **Préparer l’appareil avec Apple Configurator**
    Les appareils iOS sont connectés à l'ordinateur Mac et inscrits pour la gestion des appareils mobiles.

    1.  Sur un ordinateur Mac, démarrez **Apple Configurator 2.0**..

    2.  Connectez l’appareil iOS à l’ordinateur Mac avec un câble USB. Fermez **Photos**, **iTunes** et toutes les autres applications qui s’ouvrent quand l’appareil est détecté.

    3.  Dans Apple Configurator, cliquez sur l’appareil iOS connecté, puis cliquez sur le bouton **Add**. Les options qui peuvent être ajoutées à l’appareil s’affichent dans la liste déroulante. Cliquez sur **Profiles** . .

    4.  Utilisez le sélecteur de fichiers pour sélectionner le fichier .mobileconfig que vous avez exporté à partir d’Intune, puis cliquez sur **Add**. Le profil est ajouté à l’appareil.  Si l’appareil est non supervisé (**Unsupervised**), l’installation nécessite l’acceptation sur l’appareil.

8.  **Installer le profil**
    Vous êtes prêt à installer le profil sur l’appareil iOS. L’appareil doit avoir terminé l’Assistant Configuration et être prêt à l’emploi.  Si l’inscription entraîne des déploiements d’applications, un ID Apple doit être configuré sur l’appareil, car les déploiements d’applications nécessitent de s’être connecté à l’APP Store avec un ID Apple.

    ###### Acceptation de profil pour les appareils iOS non supervisés

    1.  Déverrouillez l’appareil iOS.

    2.  Dans la boîte de dialogue **Install profile** de **Management profile**, appuyez sur **Install**..

    3.  Spécifiez le code d’accès d’appareil (**Device Passcode**) ou l’**Apple ID**, si nécessaire.

    4.  Acceptez l’avertissement (**Warning**), puis appuyez sur **Install**..

    5.  Acceptez l’avertissement distant (**Remote Warning**), puis appuyez sur **Trust**..

    6.  Quand la boîte de dialogue **Profile Installed** confirme que le profil a été **installé**, cliquez sur **Done**..

9. **Vérifier le profil**
    Sur l’appareil iOS, lancez **Settings** et accédez à **General** &gt; **Device Management** &gt; **Management Profile** &gt;, puis vérifiez que l’installation du profil est répertoriée et vérifiez les restrictions de stratégie iOS et les applications installées. L’affichage des applications et des restrictions de stratégie sur l’appareil peut prendre jusqu’à dix minutes.

10. **Distribuer des appareils**
    L’appareil iOS est maintenant inscrit et géré dans Intune.


### Voir aussi
[Se préparer à inscrire des appareils](get-ready-to-enroll-devices-in-microsoft-intune.md)


<!--HONumber=May16_HO1-->


