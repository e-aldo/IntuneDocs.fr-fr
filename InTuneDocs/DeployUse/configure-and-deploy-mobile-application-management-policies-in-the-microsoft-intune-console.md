---
# required metadata

title: Configurer et déployer des stratégies de gestion des applications mobiles dans la console Microsoft Intune | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: b4fb33a8-a2fa-4353-bd89-5bda48b68e83

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: joglocke
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Configurer et déployer des stratégies de gestion des applications mobiles dans la console Microsoft Intune
Vous pouvez utiliser des stratégies de gestion des applications mobiles dans Microsoft Intune pour modifier les fonctionnalités des applications que vous déployez pour qu’elles soient en phase avec les stratégies de conformité et de sécurité de votre entreprise. Par exemple, vous pouvez limiter les opérations Couper, Copier et Coller au sein d'une application gérée, ou configurer une application pour ouvrir tous les liens web dans Managed Browser.

Les stratégies de gestion des applications mobiles prennent en charge :

-   les appareils qui exécutent Android 4 et versions ultérieures ;

-   les appareils qui exécutent iOS 7 et versions ultérieures.

> [!TIP] Les stratégies de gestion des applications mobiles prennent en charge les appareils inscrits avec Intune.
>
> Si vous recherchez des informations sur la façon de créer des stratégies de gestion des applications pour les appareils qui ne sont pas gérés par Intune, consultez [Protect app data using mobile app management policies with Microsoft Intune](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md) (Protéger les données d’application à l’aide des stratégies de gestion des applications mobiles avec Microsoft Intune).

Contrairement à d’autres stratégies Intune, vous ne déployez pas directement une stratégie de gestion des applications mobiles. Au lieu de cela, vous associez la stratégie à l'application que vous voulez restreindre. Quand l'application est déployée et installée sur les appareils, les paramètres que vous spécifiez prennent effet.

Pour appliquer des restrictions à une application, celle-ci doit intégrer le SDK d’application Microsoft Intune. Il existe trois méthodes pour obtenir ce type d’application :

-   **Utiliser une application gérée par une stratégie** : intègre le SDK de l’application. Pour ajouter ce type d'application, spécifiez un lien vers l'application à partir d'un magasin d'applications tel que l'iTunes Store ou Google Play. Aucun traitement supplémentaire n'est nécessaire pour ce type d'application. Consultez la liste des [applications utilisables avec les stratégies de gestion des applications mobiles de Microsoft Intune](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx).

-   **Utiliser une application « encapsulée »** : il s’agit d’applications qui sont réempaquetées pour inclure le SDK d’application à l’aide de l’**outil de création de package de restrictions d’application Microsoft Intune**. On utilise généralement cet outil pour traiter les applications d'entreprise qui ont été créées en interne. Vous ne pouvez pas l'utiliser pour traiter les applications qui ont été téléchargées à partir du magasin d'applications. Consultez [Préparer des applications iOS pour la gestion des applications mobiles avec l’outil de création de package de restrictions d’application Microsoft Intune](prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md) et [Préparer des applications Android pour la gestion des applications mobiles avec l’outil de création de package de restrictions d’application Microsoft Intune](prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md).

- **Écrire votre propre application en y intégrant le SDK d’application Intune**. Le SDK d’application Intune permet d’intégrer des fonctionnalités de gestion des applications à une application pendant que vous l’écrivez. Pour plus d’informations, consultez [Présentation du Kit SDK de l’application Intune](/develop/intune-app-sdk).

Pour savoir si vous devez utiliser l’outil de création de package de restrictions d’application ou le SDK d’application Intune, consultez [Décider comment préparer les applications pour la gestion des applications mobiles avec Microsoft Intune](/deploy-use/decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune).

Certaines applications gérées, comme l’application Outlook pour iOS et Android, prennent en charge **plusieurs identités**. Autrement dit, Intune applique uniquement les paramètres de gestion aux comptes ou aux données d'entreprise dans l'application.

Par exemple, à l'aide de l'application Outlook :

-   Si l’utilisateur configure un compte de messagerie d’entreprise et un compte de messagerie personnel, Intune applique uniquement les paramètres de gestion au compte d’entreprise et ne gère pas le compte personnel.

-   Si l'appareil est mis hors service ou désinscrit, seules les données Outlook d'entreprise sont supprimées de l'appareil.

-   Le compte d’entreprise utilisé doit être le même compte que celui qui a été utilisé pour inscrire l’appareil avec Intune.

> [!TIP] Si vous utilisez Intune avec Configuration Manager, consultez [Comment contrôler des applications à l’aide de stratégies de gestion des applications mobiles dans Configuration Manager](https://technet.microsoft.com/library/mt131414.aspx).

## Créer et déployer une application avec une stratégie de gestion des applications mobiles

-   **Étape 1** : Obtenez le lien vers une application gérée par stratégie, créez une application encapsulée ou utilisez le SDK d’application Intune pour écrire une application GAM.

-   **Étape 2 :** publier l’application dans votre espace de stockage cloud.

-   **Étape 3 :** créer une stratégie de gestion des applications mobiles.

-   **Étape 4 :** déployer l’application en sélectionnant l’option permettant d’associer l’application à une stratégie de gestion des applications mobiles.

-   **Étape 5 :** contrôler le déploiement de l’application.

## **Étape 1** : Obtenez le lien vers une application gérée par stratégie, créez une application encapsulée ou utilisez le SDK d’application Intune pour écrire une application GAM.

-   **Pour obtenir un lien vers une application gérée par une stratégie dans un App Store** : Dans un App Store, notez l’URL de l’application gérée par une stratégie que vous voulez déployer.

    Par exemple, l’URL de l’application Microsoft Word pour iPad est **https://itunes.apple.com/us/app/microsoft-word-for-ipad/id586447913?mt=8**.


## **Étape 2 :** publier l’application dans votre espace de stockage cloud
Quand vous publiez une application gérée, les procédures diffèrent selon que vous publiez une application gérée par une stratégie ou une application qui a été traitée à l'aide de l'outil de création de package de restrictions d'application Microsoft Intune pour iOS.

#### Pour publier une application gérée par une stratégie

1.  Quand vous êtes prêt à charger l’application sur votre espace de stockage cloud, suivez les instructions figurant dans [Add apps for mobile devices in Microsoft Intune](add-apps-for-mobile-devices-in-microsoft-intune.md) (Ajouter des applications pour des appareils mobiles dans Microsoft Intune).

2.  Pour les applications iOS, sous **Spécifier comment ce logiciel doit être mis à disposition des appareils**, sélectionnez **Application iOS gérée à partir de l'App Store**.

    Pour les applications Android, sélectionnez **Lien externe**.

3.  Sous **Spécifiez l'URL**, entrez l'URL de l'application gérée par une stratégie que vous avez notée précédemment.

Une fois le téléchargement terminé, **Oui** s'affiche pour **Stratégies de gestion des applications** dans la page **Propriétés du logiciel** de l'application téléchargée.

Une fois que vous avez vérifié que l'application a été téléchargée correctement, passez à l'étape 3.

#### Pour publier une application qui a été traitée à l'aide de l'outil de création de package de restrictions d'application Microsoft Intune

1.  Quand vous êtes prêt à charger l’application sur votre espace de stockage cloud, suivez les instructions figurant dans [Add apps for mobile devices in Microsoft Intune](add-apps-for-mobile-devices-in-microsoft-intune.md) (Ajouter des applications pour des appareils mobiles dans Microsoft Intune).

2.  Sous **Spécifier comment ce logiciel doit être mis à disposition des appareils**, sélectionnez **Programme d'installation du logiciel**.

3.  Sous **Sélectionnez le type de fichier du programme d’installation du logiciel**, sélectionnez **Package d’application pour iOS (fichier &#42;.ipa)**.

Une fois le téléchargement terminé, **Oui** s'affiche pour **Stratégies de gestion des applications** dans la page **Propriétés du logiciel** de l'application téléchargée.

Une fois que vous avez vérifié que l'application a été téléchargée correctement, passez à l'étape 3.

## **Étape 3 :** créer une stratégie de gestion des applications mobiles

1.  Dans la [console d’administration Microsoft Intune](https://manage.microsoft.com), sélectionnez **Stratégie** &gt; **Vue d’ensemble** &gt; **Ajouter une stratégie**.

2.  Configurez et déployez l'une des stratégies **Logiciel** suivantes, selon le type d'appareil pour lequel vous souhaitez configurer des applications :

    -   **Stratégie de gestion des applications mobiles (Android 4 et versions ultérieures)**

    -   **Stratégie de gestion des applications mobiles (iOS 7 et versions ultérieures)**

    Vous pouvez utiliser les paramètres recommandés ou personnaliser les paramètres. Pour plus d’informations, consultez [Gérer des paramètres et des fonctionnalités sur vos appareils avec des stratégies Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).

3.  Configurez les paramètres suivants en fonction des besoins. Les options peuvent différer selon le type d'appareil pour lequel vous configurez la stratégie.

|Nom du paramètre|Détails|
    |---------|--------------------|
    |**Nom**|Spécifiez un nom pour cette stratégie.|
    |**Description**|Si vous le souhaitez, spécifiez une description pour cette stratégie.|
    |**Afficher le contenu web uniquement dans Managed Browser**|Quand ce paramètre est activé, tous les liens dans l'application sont ouverts dans Managed Browser. Pour que cette option fonctionne, vous devez avoir déployé cette application sur des appareils.|
    |**Interdire les sauvegardes Android** ou **Interdire les sauvegardes iTunes et iCloud**|Désactive la sauvegarde de toutes les informations à partir de l'application.|
    |**Autoriser l'application à transférer des données vers d'autres applications**|Spécifie les applications auxquelles cette application peut envoyer des données. Vous pouvez choisir de n'autoriser le transfert de données vers aucune application, d'autoriser le transfert vers d'autres applications gérées ou d'autoriser le transfert vers toute application. Ce paramètre ne contrôle pas l’utilisation de la fonctionnalité **Ouvrir dans** sur les appareils mobiles.<br /><br />Par exemple, quand vous n'autorisez pas le transfert de données, vous limitez le transfert de données à des services comme la messagerie SMS, l'affectation d'images à des contacts et la publication sur Facebook ou Twitter.<br /><br />Pour les appareils iOS, pour empêcher le transfert de documents entre les applications gérées et non gérées, vous devez également configurer et déployer une stratégie de sécurité d’appareil mobile qui désactive le paramètre **Autoriser les documents gérés dans d’autres applications non gérées** Si vous choisissez d’autoriser le transfert uniquement vers d’autres applications gérées, les visionneuses d’images et PDF Intune (si elles sont déployées) seront utilisées pour ouvrir le contenu des types respectifs.<br /><br />En outre, si vous affectez à cette option la valeur **Applications gérées par la stratégie** ou **Aucune**, la fonctionnalité iOS 9 qui autorise la Recherche Spotlight à rechercher des données dans les applications est bloquée.|
    |**Autoriser l'application à recevoir des données d'autres applications**|Spécifie les applications à partir desquelles cette application peut recevoir des données. Vous pouvez choisir de n’autoriser le transfert de données à partir d’aucune application, d’autoriser uniquement le transfert à partir d’autres applications gérées, ou d’autoriser le transfert à partir de toute application.<br /><br />Pour les applications iOS qui prennent en charge plusieurs identités (où Intune applique uniquement les paramètres de gestion aux comptes d’entreprise ou aux données dans l’application), pour un appareil inscrit où une stratégie de gestion des applications mobiles est appliquée, quand un utilisateur accède aux données à partir d’une application qui n’est pas gérée par une stratégie de gestion des applications mobiles, les données sont traitées comme des données d’entreprise et sont protégées par la stratégie.|
    |**Interdire « Enregistrer sous »**|Désactive l'utilisation de l'option **Enregistrer sous** pour enregistrer des données à des emplacements de stockage cloud personnels (comme OneDrive Personal ou Dropbox) dans les applications utilisant cette stratégie.|
    |**Restreindre les opérations couper, copier et coller avec d'autres applications**|Spécifie comment les opérations couper, copier et coller peuvent être utilisées avec l'application. Choisissez parmi :<br /><br />**Bloqué** : ne pas autoriser les opérations couper, copier et coller entre cette application et d’autres applications.<br /><br />**Applications gérées par la stratégie** : autoriser seulement les opérations Couper, Copier et Coller entre cette application et les autres applications gérées.<br /><br />**Applications gérées par la stratégie avec Coller dans** : autoriser seulement le collage de données coupées ou copiées à partir de cette application vers d’autres applications gérées. Autoriser le collage dans cette application de données coupées ou copiées à partir de n'importe quelle application.<br /><br />**N’importe quelle application** : aucune restriction pour les opérations Couper, Copier et Coller vers ou à partir de cette application.<br /><br />Pour copier et coller des données entre des applications gérées, le paramètre **Applications gérées par la stratégie** ou le paramètre **Applications gérées par la stratégie avec Coller dans** doit être configuré dans les deux applications.|
    |**Demander un code confidentiel simple pour l'accès**|Oblige l'utilisateur à entrer un code confidentiel qu'il spécifie pour utiliser cette application. L'utilisateur sera invité à définir ce code lors de la première exécution de l'application.|
    |**Nombre de tentatives avant réinitialisation du code confidentiel**|Spécifiez le nombre de tentatives de saisie du code confidentiel qui peuvent être effectuées avant que l'utilisateur soit obligé de réinitialiser le code confidentiel.|
    |**Exiger des informations d'identification d'entreprise pour l'accès**|Exige que l'utilisateur entre ses informations d'ouverture de session d'entreprise pour accéder à l'application.|
    |**Exiger la conformité à la stratégie d'entreprise pour l'accès**|Autorise l'utilisation de l'application uniquement si l'appareil n'est pas jailbroken ou rooté.|
    |**Revérifier les exigences d'accès après (minutes)**|Dans le champ **Délai** , indiquez le délai au bout duquel les conditions d'accès pour l'application sont revérifiées après son démarrage.|
    |**Période de grâce hors connexion**|Si l'appareil est hors connexion, spécifiez le délai au bout duquel les conditions d'accès pour l'application sont revérifiées.|
    |**Chiffrer les données de l'application**|Spécifie que toutes les données associées à cette application seront chiffrées, y compris les données stockées en externe, telles que les cartes SD.<br /><br />**Chiffrement pour iOS**<br /><br />Pour les applications associées à une stratégie de gestion des applications mobiles Intune, les données sont chiffrées au repos à l’aide du chiffrement au niveau de l’appareil fourni par le système d’exploitation. Cette option est activée via la stratégie de code confidentiel d'appareil qui doit être définie par l'administrateur informatique. Quand un code confidentiel est nécessaire, les données sont chiffrées selon les paramètres de la stratégie de gestion des applications mobiles. Comme indiqué dans la documentation Apple, [les modules utilisés par iOS 7 sont certifiés FIPS 140-2](http://support.apple.com/en-us/HT202739).<br /><br />**Chiffrement pour Android**<br /><br />Pour les applications associées à une stratégie de gestion des applications mobiles Intune, le chiffrement est fourni par Microsoft. Les données sont chiffrées de façon synchrone durant les opérations d’E/S de fichier.  Le contenu sur le stockage de l'appareil est toujours chiffré. La méthode de chiffrement n'est pas certifiée FIPS 140-2.|
    |**Bloquer la capture d'écran** (appareils Android uniquement)|Spécifie que les fonctionnalités de capture d'écran de l'appareil sont bloquées lors de l'utilisation de cette application.|

4.  Quand vous avez terminé, choisissez **Enregistrer la stratégie**.

La nouvelle stratégie s'affiche sous le nœud **Stratégies de configuration** de l'espace de travail **Stratégie** .

## **Étape 4 :** associer l’application à une stratégie de gestion des applications mobiles, puis la déployer
Déployez l'application, en veillant à sélectionner la stratégie de gestion des applications mobiles dans la page **Gestion des applications mobiles** pour associer la stratégie à l'application.

Pour plus d’informations, consultez [Déployer des applications dans Microsoft Intune](deploy-apps.md).

> [!IMPORTANT] Pour les appareils qui exécutent des systèmes d’exploitation antérieurs à iOS 7.1, les stratégies associées ne sont pas supprimées lors de la désinstallation de l’application.
>
> Si l’appareil est désinscrit d’Intune, les stratégies ne sont pas supprimées des applications ; toute application à laquelle des stratégies étaient appliquées conservera les paramètres de stratégie, même après avoir été désinstallée et réinstallée.

### Que faire quand une application est déjà déployée sur des appareils
Dans certaines situations, quand vous déployez une application, il se peut que l’un des utilisateurs ou des appareils ciblés dispose déjà d’une version non gérée de l’application, par exemple, l’utilisateur a installé Microsoft Word à partir de la boutique d’applications.

Dans ce cas, vous devez demander à l’utilisateur de désinstaller manuellement la version non gérée pour pouvoir installer la version gérée que vous avez configurée.

Toutefois, pour les appareils qui exécutent iOS 9 et versions ultérieures, Intune demande automatiquement à l’utilisateur l’autorisation de reprendre la gestion de l’application existante. S’il est d’accord, l’application est alors gérée par Intune et les stratégies de gestion des applications mobiles que vous avez associées à l’application sont également appliquées.

> [!TIP] Si l’appareil est en mode supervisé, Intune reprend la gestion de l’application existante sans demander l’autorisation aux utilisateurs.

## **Étape 5 :** contrôler le déploiement de l’application.
Une fois que vous avez créé et déployé une application associée à une stratégie de gestion des applications mobiles, appliquez les procédures suivantes pour analyser l'application et résoudre les éventuels conflits de stratégie.

#### Pour afficher l'état du déploiement

1.  Dans la [console d’administration Microsoft Intune](https://manage.microsoft.com), sélectionnez **Groupes** &gt; **Vue d’ensemble**.

2.  Effectuez l'une des étapes suivantes :

    -   Sélectionnez **Tous les utilisateurs**, puis double-cliquez sur l’utilisateur dont vous voulez examiner les appareils. Dans la page **Propriétés de l’utilisateur**, sélectionnez **Appareils**, puis double-cliquez sur l’appareil à examiner.

    -   Sélectionnez **Tous les appareils** &gt; **Tous les appareils mobiles**. Dans la page **Propriétés du groupe d’appareils**, sélectionnez **Appareils**, puis double-cliquez sur l’appareil à examiner.

3.  Dans la page **Propriétés de l’appareil mobile** , sélectionnez **Stratégie** pour afficher la liste des stratégies de gestion des applications mobiles qui ont été déployées sur l’appareil.

4.  Sélectionnez la stratégie de gestion des applications mobiles dont vous souhaitez afficher l'état. Vous pouvez afficher les détails de la stratégie dans le volet inférieur et développer son nœud pour afficher ses paramètres.

5.  Sous la colonne **État** de chacune des stratégies de gestion des applications mobiles est affichée la mention **Conforme**, **Conforme (en attente)**ou **Erreur** . Si la stratégie sélectionnée a un ou plusieurs paramètres en conflit, **Erreur** est affiché dans ce champ.

6.  Une fois que vous avez identifié un conflit, vous pouvez modifier les paramètres de stratégie en conflit pour utiliser le même paramètre ou déployer une seule stratégie vers l'application et l'utilisateur.

### Résolution des conflits de stratégie
En cas de conflit de stratégie de gestion des applications mobiles lors du premier déploiement vers l'utilisateur ou l'appareil, la valeur de paramètre spécifique en conflit est supprimée de la stratégie déployée vers l'application et celle-ci utilise une valeur de conflit intégrée.

En cas de conflit de stratégie de gestion des applications mobiles lors de déploiements ultérieurs vers l'application ou l'utilisateur, la valeur de paramètre spécifique en conflit n'est pas mise à jour sur la stratégie de gestion des applications mobiles déployée vers l'application et celle-ci utilise la valeur existante pour ce paramètre.

Dans les cas où l'appareil ou l'utilisateur reçoit deux stratégies en conflit, le comportement suivant s'applique :

-   Si une stratégie a déjà été déployée sur l'appareil, les paramètres de stratégie existants ne sont pas remplacés.

-   Si aucune stratégie n'a encore été déployée sur l'appareil et que deux paramètres en conflit sont déployés, le paramètre par défaut intégré à l'appareil est utilisé.


<!--HONumber=Jun16_HO2-->


