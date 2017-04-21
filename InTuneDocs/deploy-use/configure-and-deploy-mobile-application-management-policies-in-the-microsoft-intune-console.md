---
title: "Configurer des stratégies de gestion des applications mobiles dans la console Intune | Microsoft Docs"
description: "Vous pouvez utiliser des stratégies de gestion des applications mobiles dans Microsoft Intune pour modifier les fonctionnalités des applications que vous déployez pour qu’elles soient en phase avec les stratégies de conformité et de sécurité de votre entreprise."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 03/17/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b4fb33a8-a2fa-4353-bd89-5bda48b68e83
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: ab6d9b6b296fb4e1fb0aaa9496fede28976728dc
ms.openlocfilehash: dbc5c6afc9f2748b50e064b912e519e8f2de9022
ms.lasthandoff: 04/14/2017


---

# <a name="configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console"></a>Configurer et déployer des stratégies de gestion des applications mobiles dans la console Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Vous pouvez utiliser des stratégies de gestion des applications mobiles (GAM) dans Microsoft Intune pour modifier les fonctionnalités des applications que vous déployez pour qu’elles soient en phase avec les stratégies de conformité et de sécurité de votre entreprise. Par exemple, vous pouvez limiter les opérations Couper, Copier et Coller au sein d’une application gérée, ou configurer une application pour ouvrir tous les liens web dans Managed Browser.

Les stratégies de gestion des applications mobiles prennent en charge :

-   Les appareils qui exécutent Android 4 et ultérieur

-   Les appareils qui exécutent iOS 8.0 et versions ultérieures

> [!TIP]
> Les stratégies de gestion des applications mobiles prennent en charge les appareils inscrits avec Intune.
>
> Si vous recherchez des informations sur la façon de créer des stratégies de gestion des applications pour les appareils que ne gère pas Intune, consultez [Protéger les données d’application à l’aide des stratégies de gestion des applications mobiles avec Microsoft Intune](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md).

Contrairement à d’autres stratégies Intune, vous ne déployez pas directement une stratégie de gestion des applications mobiles. Au lieu de cela, vous associez la stratégie à l'application que vous voulez restreindre. Quand l’application est déployée et installée sur les appareils, les paramètres que vous spécifiez prennent effet.

Pour appliquer des restrictions à une application, celle-ci doit intégrer le SDK d’application Microsoft Intune. Il existe trois méthodes pour obtenir ce type d’application :

-   **Utiliser une application gérée par une stratégie**. Une application gérée par une stratégie intègre le SDK d’application. Pour ajouter ce type d'application, spécifiez un lien vers l'application à partir d'un magasin d'applications tel que l'iTunes Store ou Google Play. Aucun traitement supplémentaire n'est nécessaire pour ce type d'application. Pour plus d’informations, consultez la [liste des applications que vous pouvez utiliser avec les stratégies de gestion des applications mobiles de Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune-apps).

-   **Utiliser une application encapsulée**. Une application encapsulée est une application que vous réempaquetez pour inclure le SDK d’application à l’aide de l’outil de création de package de restrictions d’application Microsoft Intune. Cet outil est généralement utilisé pour traiter les applications d’entreprise qui ont été créées en interne. Vous ne pouvez pas l’utiliser pour traiter les applications qui ont été téléchargées à partir de l’App Store. Pour plus d’informations, consultez [Préparer des applications iOS pour la gestion des applications mobiles avec l’outil de création de package de restrictions d’application Microsoft Intune](prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md) et [Préparer des applications Android pour la gestion des applications mobiles avec l’outil de création de package de restrictions d’application Microsoft Intune](prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md).

- **Écrivez votre propre application qui intègre le SDK d’application Intune**. Le SDK d’application Intune vous permet d’intégrer des fonctionnalités de gestion des applications à une application pendant que vous l’écrivez. Pour plus d’informations, consultez [Vue d’ensemble du Kit de développement logiciel (SDK) de l’application Microsoft Intune](/intune/develop/intune-app-sdk).

Pour savoir si vous devez utiliser l’outil de création de package de restrictions d’application et le SDK d’application Intune, consultez [Décider comment préparer les applications pour la gestion des applications mobiles avec Microsoft Intune](decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune.md).

Certaines applications gérées, comme l’application Outlook pour iOS et Android, prennent en charge *plusieurs identités*. Autrement dit, Intune applique les paramètres de gestion uniquement aux comptes ou aux données d’entreprise dans l’application.

Par exemple, à l'aide de l'application Outlook :

-   Si l’utilisateur configure un compte e-mail d’entreprise et un compte e-mail personnel, Intune applique les paramètres de gestion uniquement au compte d’entreprise et ne gère pas le compte personnel.

-   Si l’appareil est mis hors service ou désinscrit, seules les données Outlook d'entreprise sont supprimées de l’appareil.

-   Le compte d’entreprise doit être le même compte que celui qui a été utilisé pour inscrire l’appareil sur Intune.

> [!TIP]
> Si vous utilisez Intune avec Configuration Manager, consultez [Comment contrôler des applications à l’aide de stratégies de gestion des applications mobiles dans Configuration Manager](https://technet.microsoft.com/library/mt131414.aspx).

## <a name="create-and-deploy-an-app-with-a-mobile-application-management-policy"></a>Créer et déployer une application avec une stratégie de gestion des applications mobiles

-   **Étape 1** : Obtenir le lien vers une application gérée par stratégie, créer une application encapsulée ou utiliser le SDK de l’application Intune pour écrire une application GAM.

-   **Étape 2 :** Publier l’application dans votre espace de stockage cloud.

-   **Étape 3 :** Créer une stratégie de gestion des applications mobiles.

-   **Étape 4 :** Associer l’application à une stratégie de gestion des applications mobiles et la déployer.

-   **Étape 5 :** Surveiller le déploiement de l’application.

## <a name="step-1-get-the-link-to-a-policy-managed-app-create-a-wrapped-app-or-use-the-intune-app-sdk-to-write-a-mam-enabled-app"></a>Étape 1 : Obtenir le lien vers une application gérée par stratégie, créer une application encapsulée ou utiliser le SDK de l’application Intune pour écrire une application GAM

À partir de l’App Store, recherchez et notez l’URL de l’application gérée par une stratégie que vous souhaitez déployer. Par exemple, l’URL de l’application Microsoft Word pour iPad est **https://itunes.apple.com/us/app/microsoft-word-for-ipad/id586447913?mt=8**.


## <a name="step-2-publish-the-app-to-your-cloud-storage-space"></a>Étape 2 : Publier l’application dans votre espace de stockage cloud
Quand vous publiez une application gérée, les procédures diffèrent selon que vous publiez une application gérée par une stratégie ou une application qui a été traitée à l'aide de l'outil de création de package de restrictions d'application Microsoft Intune pour iOS.

#### <a name="to-publish-a-policy-managed-app"></a>Pour publier une application gérée par une stratégie

1.  Quand vous êtes prêt à charger l’application sur votre espace de stockage cloud, suivez les instructions figurant dans [Add apps for mobile devices in Microsoft Intune](add-apps-for-mobile-devices-in-microsoft-intune.md) (Ajouter des applications pour des appareils mobiles dans Microsoft Intune).

2.  Pour les applications iOS, sous **Spécifier comment ce logiciel doit être mis à disposition des appareils**, sélectionnez **Application iOS gérée à partir de l'App Store**.

    Pour les applications Android, sélectionnez **Lien externe**.

3.  Sous **Spécifiez l'URL**, entrez l'URL de l'application gérée par une stratégie que vous avez notée précédemment.

Une fois le téléchargement terminé, **Oui** s’affiche pour **Stratégies de gestion des applications** dans la page **Propriétés du logiciel** de l’application chargée.

Une fois que vous avez vérifié que l’application a été chargée correctement, passez à l’étape 3.

#### <a name="to-publish-an-app-that-was-processed-through-the-microsoft-intune-app-wrapping-tool"></a>Pour publier une application qui a été traitée à l’aide de l’outil de création de package de restrictions d’application Microsoft Intune

1.  Quand vous êtes prêt à charger l’application sur votre espace de stockage cloud, suivez les instructions figurant dans [Ajouter des applications aux appareils mobiles dans Microsoft Intune](add-apps-for-mobile-devices-in-microsoft-intune.md).

2.  Sous **Spécifier comment ce logiciel doit être mis à disposition des appareils**, sélectionnez **Programme d'installation du logiciel**.

3.  Sous **Sélectionnez le type de fichier du programme d’installation du logiciel**, sélectionnez **Package d’application pour iOS (fichier &#42;.ipa)**.

Une fois le téléchargement terminé, **Oui** s’affiche pour **Stratégies de gestion des applications** dans la page **Propriétés du logiciel** de l’application chargée.

Une fois que vous avez vérifié que l’application a été chargée correctement, passez à l’étape 3.

## <a name="step-3-create-a-mobile-application-management-policy"></a>Étape 3 : Créer une stratégie de gestion des applications mobiles

1.  Dans la [console d’administration Microsoft Intune](https://manage.microsoft.com), sélectionnez **Stratégie** &gt; **Vue d’ensemble** &gt; **Ajouter une stratégie**.

2.  Configurez et déployez l’une des stratégies **Logiciel** suivantes, selon le type d’appareil pour lequel vous souhaitez configurer des applications :

    -   **Stratégie de gestion des applications mobiles (Android 4 et versions ultérieures)**

    -   **Stratégie de gestion des applications mobiles (iOS 8.0 et ultérieur)**

    Vous pouvez utiliser les paramètres recommandés ou personnaliser les paramètres. Pour plus d’informations, consultez [Gérer des paramètres et des fonctionnalités sur vos appareils avec des stratégies Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).

3.  Configurez les paramètres suivants en fonction des besoins. Les options peuvent différer selon le type d'appareil pour lequel vous configurez la stratégie.

|Nom du paramètre|Détails|
    |---------|--------------------|
    |**Nom**|Spécifiez un nom pour cette stratégie.|
    |**Description**|Si vous le souhaitez, spécifiez une description pour cette stratégie.|
    |**Afficher le contenu web uniquement dans Managed Browser**|Quand ce paramètre est activé, tous les liens dans l’application sont ouverts dans Managed Browser. Pour que cette option fonctionne, vous devez avoir déployé cette application sur des appareils.|
    |**Interdire les sauvegardes Android** ou **Interdire les sauvegardes iTunes et iCloud**|Ce paramètre désactive la sauvegarde de toutes les informations à partir de l’application.|
    |**Autoriser l'application à transférer des données vers d'autres applications**|Ce paramètre spécifie les applications auxquelles cette application peut envoyer des données. Vous pouvez choisir de n’autoriser le transfert de données vers aucune application, d’autoriser le transfert seulement vers d’autres applications gérées ou d’autoriser le transfert vers toutes les applications. <br /><br />Par exemple, quand vous n'autorisez pas le transfert de données, vous limitez le transfert de données à des services comme la messagerie SMS, l'affectation d'images à des contacts et la publication sur Facebook ou Twitter.<br /><br />Pour les appareils iOS, pour empêcher le transfert de documents entre les applications gérées et non gérées, vous devez aussi configurer et déployer une stratégie de sécurité d'appareil mobile qui désactive le paramètre **Autoriser les documents gérés dans d'autres applications non gérées**. Si vous choisissez d’autoriser le transfert seulement vers d’autres applications gérées, les visionneuses d’images et de PDF Intune (si elles sont déployées) seront utilisées pour ouvrir le contenu de ces types respectifs.<br /><br />En outre, si vous affectez à cette option la valeur **Applications gérées par la stratégie** ou **Aucune**, la fonctionnalité iOS 9 qui autorise la Recherche Spotlight à rechercher des données dans les applications est bloquée.<br><br>Ce paramètre ne contrôle pas l’utilisation de la fonctionnalité « Ouvrir dans » sur les appareils mobiles. Pour gérer la fonctionnalité « Ouvrir dans », consultez [Gérer les transferts de données entre applications iOS avec Microsoft Intune](manage-data-transfer-between-ios-apps-with-microsoft-intune.md).|
    |**Autoriser l'application à recevoir des données d'autres applications**|Ce paramètre spécifie les applications à partir desquelles cette application peut recevoir des données. Vous pouvez choisir de n’autoriser le transfert de données à partir d’aucune application, d’autoriser le transfert seulement à partir d’autres applications gérées, ou d’autoriser le transfert à partir de toutes les applications.<br /><br />Quand un utilisateur accède aux données d’une application qui n’est pas gérée par une stratégie de gestion des applications mobiles, les données sont traitées comme des données d’entreprise et sont protégées par la stratégie. Cela s’applique aux applications iOS prenant en charge plusieurs identités (où Intune applique les paramètres de gestion uniquement aux comptes d’entreprise ou aux données dans l’application). Ou cela s’applique à un appareil inscrit avec une stratégie de gestion des applications mobiles appliquée.|
    |**Interdire « Enregistrer sous »**|Ce paramètre désactive l’utilisation de l’option **Enregistrer sous** pour enregistrer des données à des emplacements de stockage cloud personnels (comme OneDrive ou Dropbox) dans les applications utilisant cette stratégie.|
    |**Restreindre les opérations couper, copier et coller avec d'autres applications**|Ce paramètre spécifie comment les opérations couper, copier et coller peuvent être utilisées avec l’application. Choisissez parmi :<br /><br />**Bloqué**. N’autorise pas les opérations couper, copier et coller entre cette application et d’autres applications.<br /><br />**Applications gérées par la stratégie**. Autorise les opérations Couper, Copier et Coller seulement entre cette application et les autres applications gérées.<br /><br />**Applications gérées par la stratégie avec Coller dans**. Autorise les données coupées ou copiées dans cette application à être collées seulement dans d’autres applications gérées. Autoriser le collage dans cette application de données coupées ou copiées à partir de n'importe quelle application.<br /><br />**N’importe quelle application**. Ne met aucune restriction sur les opérations couper, copier et coller vers ou à partir de cette application.<br /><br />Pour copier et coller des données entre des applications gérées, le paramètre **Applications gérées par la stratégie** ou le paramètre **Applications gérées par la stratégie avec Coller dans** doit être configuré dans les deux applications.|
    |**Demander un code confidentiel simple pour l'accès**|Ce paramètre oblige l’utilisateur à entrer un code confidentiel qu’il spécifie pour utiliser cette application. L'utilisateur sera invité à définir ce code lors de la première exécution de l'application.|
    |**Nombre de tentatives avant réinitialisation du code confidentiel**|Spécifiez le nombre de tentatives dont dispose l’utilisateur pour saisir le code confidentiel avant d’être obligé de réinitialiser le code confidentiel.|
    |**Exiger des informations d'identification d'entreprise pour l'accès**|Ce paramètre exige que l’utilisateur entre ses informations de connexion d’entreprise pour accéder à l’application.|
    |**Exiger la conformité à la stratégie d'entreprise pour l'accès**|Ce paramètre autorise l’utilisation de l’application uniquement si l’appareil n’est pas jailbreaké ou rooté.|
    |**Revérifier les exigences d'accès après (minutes)**|Dans le champ **Délai** , indiquez le délai au bout duquel les conditions d’accès à l’application sont revérifiées une fois l’application ouverte.|
    |**Période de grâce hors connexion**|Si l'appareil est hors connexion, spécifiez le délai au bout duquel les conditions d'accès pour l'application sont revérifiées.|
    |**Chiffrer les données de l'application**|Ce paramètre spécifie que toutes les données associées à cette application seront chiffrées. Cela inclut les données stockées en externe, comme par exemple les cartes SD.<br /><br />**Chiffrement pour iOS**<br /><br />Pour les applications associées à une stratégie de gestion des applications mobiles Intune, les données sont chiffrées au repos à l’aide du chiffrement au niveau de l’appareil que fournit le système d’exploitation. Cette option est activée via une stratégie de code confidentiel d’appareil que définit l’administrateur informatique. Quand un code confidentiel est exigé, les données sont chiffrées selon les paramètres de la stratégie de gestion des applications mobiles. Comme indiqué dans la documentation Apple, [les modules qu’utilise iOS sont certifiés FIPS 140-2](http://support.apple.com/HT202739).<br /><br />**Chiffrement pour Android**<br /><br />Pour les applications associées à une stratégie de gestion des applications mobiles Intune, Microsoft fournit le chiffrement. Les données sont chiffrées de façon synchrone durant les opérations d’E/S de fichier.  Le contenu sur le stockage de l'appareil est toujours chiffré. La méthode de chiffrement est la norme FIPS 140-2 compatible uniquement avec les appareils Samsung KNOX.|
    |**Bloquer la capture d'écran** (appareils Android uniquement)|Ce paramètre spécifie que les fonctionnalités de capture d’écran de l’appareil sont bloquées quand une personne utilise cette application.|

4. Quand vous avez terminé, choisissez **Enregistrer la stratégie**.

La nouvelle stratégie apparaît sous le nœud **Stratégies de configuration** de l’espace de travail **Stratégie**.

## <a name="step-4-associate-the-app-with-a-mobile-application-management-policy-and-then-deploy-the-app"></a>Étape 4 : Associer l’application à une stratégie de gestion des applications mobiles et la déployer
Veillez à sélectionner la stratégie de gestion des applications mobiles dans la page **Gestion des applications mobiles** de la boîte de dialogue **Gérer le déploiement** pour associer la stratégie à l’application.

Pour plus d’informations, consultez [Déployer des applications dans Microsoft Intune](deploy-apps.md).

> [!IMPORTANT]
> Si l’appareil est désinscrit d’Intune, les stratégies ne sont pas supprimées des applications. Les applications pour lesquelles des stratégies étaient appliquées conservent les paramètres de stratégie après la désinstallation et la réinstallation de l’application.

### <a name="what-to-do-when-an-app-is-already-deployed-on-devices"></a>Que faire quand une application est déjà déployée sur des appareils
Quand vous déployez une application, il peut arriver que l’un des utilisateurs ou des appareils ciblés dispose déjà d’une version non gérée de l’application. Par exemple, l’utilisateur peut avoir installé Microsoft Word à partir de l’App Store.

Dans ce cas, vous devez demander à l’utilisateur de désinstaller manuellement la version non gérée pour pouvoir installer la version gérée que vous avez configurée.

Toutefois, pour les appareils qui exécutent iOS 9 et versions ultérieures, Intune demande automatiquement à l’utilisateur l’autorisation de reprendre la gestion de l’application existante. S’il est d’accord, l’application est alors gérée par Intune et les stratégies de gestion des applications mobiles que vous avez associées à l’application sont également appliquées.

> [!TIP]
> Si l’appareil est en mode supervisé, Intune reprend la gestion de l’application existante sans demander l’autorisation aux utilisateurs.

## <a name="step-5-monitor-the-app-deployment"></a>Étape 5 : Surveiller le déploiement de l’application
Après avoir créé et déployé une application associée à une stratégie de gestion des applications mobiles, appliquez la procédure suivante pour analyser l’application et résoudre les éventuels conflits de stratégie.

#### <a name="to-view-the-status-of-the-deployment"></a>Pour afficher l'état du déploiement

1.  Dans la [console d’administration Microsoft Intune](https://manage.microsoft.com), sélectionnez **Groupes** &gt; **Vue d’ensemble**.

2.  Effectuez l'une des étapes suivantes :

    -   Sélectionnez **Tous les utilisateurs**, puis double-cliquez sur l’utilisateur dont vous voulez examiner l’appareil. Dans la page **Propriétés de l’utilisateur**, sélectionnez **Appareils**, puis double-cliquez sur l’appareil à examiner.

    -   Sélectionnez **Tous les appareils** &gt; **Tous les appareils mobiles**. Dans la page **Propriétés du groupe d’appareils**, sélectionnez **Appareils**, puis double-cliquez sur l’appareil à examiner.

3.  Dans la page **Propriétés de l’appareil mobile** , sélectionnez **Stratégie** pour afficher la liste des stratégies de gestion des applications mobiles qui ont été déployées sur l’appareil.

4.  Sélectionnez la stratégie de gestion des applications mobiles dont vous souhaitez afficher l'état. Vous pouvez afficher les détails de la stratégie dans le volet inférieur et développer son nœud pour afficher ses paramètres.

5.  Sous la colonne **État** de chacune des stratégies de gestion des applications mobiles apparaît la mention **Conforme**, **Conforme (en attente)**ou **Erreur** . Si la stratégie sélectionnée a un ou plusieurs paramètres en conflit, **Erreur** apparaît dans ce champ.

6.  Après avoir identifié un conflit, vous pouvez modifier les paramètres de stratégie en conflit pour utiliser le même paramètre ou vous pouvez déployer une seule stratégie vers l’application et l’utilisateur.

### <a name="how-policy-conflicts-are-resolved"></a>Résolution des conflits de stratégie
En cas de conflit de stratégie de gestion des applications mobiles lors du premier déploiement vers l’utilisateur ou l’appareil, la valeur de paramètre spécifique en conflit est supprimée de la stratégie déployée vers l’application. L’application utilise une valeur de conflit intégrée.

En cas de conflit de stratégie de gestion des applications mobiles lors des prochains déploiements vers l’application ou l’utilisateur, la valeur de paramètre spécifique en conflit n’est pas mise à jour sur la stratégie de gestion des applications mobiles déployée vers l’application. L’application utilise la valeur existante pour ce paramètre.

Dans les cas où l'appareil ou l'utilisateur reçoit deux stratégies en conflit, le comportement suivant s'applique :

-   Si une stratégie a déjà été déployée sur l'appareil, les paramètres de stratégie existants ne sont pas remplacés.

-   Si aucune stratégie n'a encore été déployée sur l'appareil et que deux paramètres en conflit sont déployés, le paramètre par défaut intégré à l'appareil est utilisé.

