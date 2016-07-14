---
title: "Gérer l’accès à Internet à l’aide de stratégies Managed Browser | Microsoft Intune"
description: 
keywords: 
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dc946303-e09b-4d73-8bf4-87742299bc54
ms.reviewer: jeffgilb
ms.suite: ems
ms.sourcegitcommit: 2df44199ecd904dcfb6774a942244338c1384186
ms.openlocfilehash: c4462af584d54225084159dfa35f5e1d07c36397


---

# Gérer l'accès à Internet à l'aide de stratégies Managed Browser avec Microsoft Intune
Managed Browser est une application de navigation web que vous pouvez déployer dans votre organisation à l’aide de Microsoft Intune. Une stratégie Managed Browser configure une liste autorisée ou une liste bloquée qui restreint les sites web auxquels les utilisateurs de Managed Browser ont accès.

Comme il s'agit d'une application gérée, vous pouvez aussi lui appliquer des stratégies de gestion des applications mobiles, notamment pour contrôler l'utilisation des fonctions couper, copier et coller, pour empêcher les captures d'écran ou encore pour vous assurer que les liens vers du contenu sur lesquels les utilisateurs cliquent s'ouvrent uniquement dans d'autres applications gérées. Pour plus d’informations, consultez [Configurer et déployer des stratégies de gestion des applications mobiles dans la console Microsoft Intune](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md).

> [!IMPORTANT]
>Si des utilisateurs installent Managed Browser à partir de l’App Store et qu’il n’est pas géré par Intune, le comportement suivant s’applique : iOS : l’application Managed Browser peut être utilisée comme navigateur web de base, mais certaines fonctionnalités ne seront pas disponibles et elle ne pourra pas accéder à des données d’autres applications gérées par Intune.
Android : l’application Managed Browser ne peut pas être utilisée.
Si des utilisateurs installent eux-mêmes Managed Browser sur un appareil iOS dont la version est inférieure à iOS 9, il ne sera pas géré par les stratégies que vous créez. Pour s'assurer que le navigateur est géré par Intune, les utilisateurs doivent désinstaller l'application avant de la déployer en tant qu'application gérée. Sur iOS 9 et versions ultérieures, si l’utilisateur installe lui-même Managed Browser, il sera invité à autoriser sa gestion par la stratégie.

Vous pouvez créer des stratégies Managed Browser pour les types d'appareils suivants :

-   les appareils qui exécutent Android 4 et versions ultérieures ;

-   Appareils qui exécutent iOS 7.1 et versions ultérieures

Intune Managed Browser prend en charge l’ouverture de contenu web des [partenaires de l’application Microsoft Intune](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx).

## Créer une stratégie Managed Browser

1.  Dans la [console d’administration Microsoft Intune](https://manage.microsoft.com), cliquez sur **Stratégie** &gt; **Ajouter une stratégie**.

2.  Configurez l'un des types de stratégies **Logiciel** suivants :

    -   **Stratégie Managed Browser (Android 4 et versions ultérieures)**

    -   **Stratégie Managed Browser (iOS 7.1 et versions ultérieures)**

    Pour plus d’informations sur la façon de créer et de déployer des stratégies, consultez la rubrique [Gérer des paramètres et des fonctionnalités sur vos appareils avec des stratégies Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).

3.  Utilisez le tableau suivant pour vous aider à configurer les paramètres de la stratégie Managed Browser :

|Nom du paramètre|Détails|
    |----------------|--------------------|
    |**Nom**|Affectez un nom unique à la stratégie Managed Browser pour vous aider à l’identifier dans la console Intune.|
    |**Description**|Indiquez une description générale de la stratégie Managed Browser et d'autres informations pertinentes pour mieux la localiser.|
    |**Activer une liste autorisée ou une liste bloquée pour restreindre les URL pouvant être ouvertes par Managed Browser**|Sélectionnez l’une des options suivantes :<br /><br />**Autoriser Managed Browser à ouvrir seulement les URL répertoriées ci-dessous** : spécifiez une liste d’URL pouvant être ouvertes par Managed Browser.<br /><br />**Empêcher Managed Browser d’ouvrir les URL répertoriées ci-dessous** : spécifiez une liste d’URL ne pouvant pas être ouvertes par Managed Browser. **Remarque** : Vous ne pouvez pas inclure des URL autorisées et bloquées dans la même stratégie Managed Browser.<br />Pour plus d’informations sur les formats d’URL que vous pouvez spécifier, consultez **Format des URL autorisées et des URL bloquées** dans cette rubrique.|

4.  Quand vous avez terminé, cliquez sur **Enregistrer la stratégie**.

La nouvelle stratégie s'affiche sous le nœud **Stratégies de configuration** de l'espace de travail **Stratégie** .

## Créer un déploiement pour l’application Managed Browser
Après avoir défini la stratégie Managed Browser, vous pouvez créer un déploiement de logiciel pour l'application Managed Browser et l'associer à la stratégie Managed Browser que vous venez de créer.

> [!IMPORTANT]
> Les stratégies Managed Browser ne sont pas déployées de la même façon que les autres stratégies Intune. Ce type de stratégie doit être associé au package logiciel Managed Browser.

Déployez l'application en veillant à sélectionner la stratégie Managed Browser dans la page **Gestion des applications mobiles** pour associer la stratégie à l'application.

Pour plus d’informations sur la façon de déployer des applications, consultez la page [Déployer des applications dans Microsoft Intune](deploy-apps-in-microsoft-intune.md).

## Sécurité et confidentialité de Managed Browser

-   Sur les appareils iOS, les utilisateurs ne peuvent pas ouvrir les sites web possédant un certificat qui a expiré ou qui n'est pas approuvé.

-   Les paramètres du navigateur intégré définis par les utilisateurs sur leur appareil ne sont pas utilisés par Managed Browser. Cela est dû au fait que Managed Browser n'a pas accès à ces paramètres.

-   Si vous configurez l'option **Demander un code confidentiel simple pour l'accès** ou **Exiger des informations d'identification d'entreprise pour l'accès** dans une stratégie de gestion des applications mobiles associée à Managed Browser et qu'un utilisateur clique sur le lien d'aide dans la page d'authentification, l'utilisateur peut visiter n'importe quel site Internet, même si celui-ci a été ajoutée à une liste bloquée dans la stratégie Managed Browser.

-   Managed Browser peut uniquement bloquer l'accès aux sites qui font l'objet d'un accès direct. Il ne peut pas bloquer l'accès quand des services intermédiaires (tels qu'un service de traduction) sont utilisés pour accéder au site.

-   Pour permettre l’authentification et pour s’assurer que la documentation d’Intune est accessible, **&#42;.microsoft.com** n’est pas soumis aux paramètres de liste verte ou rouge et est toujours autorisé.

### Désactiver les données d’utilisation
Microsoft collecte automatiquement des données anonymes sur le fonctionnement et l’utilisation de Managed Browser pour améliorer les produits et services Microsoft, mais les utilisateurs peuvent désactiver la collecte de données à l’aide du paramètre **Données d’utilisation** de leur appareil. Vous n’avez aucun contrôle sur la collecte de ces données.

## Informations de référence

### Format des URL autorisées et des URL bloquées
Utilisez les informations suivantes pour en savoir plus sur les formats et les caractères génériques que vous pouvez utiliser pour spécifier des URL dans les listes autorisées et les listes bloquées.

-   Vous pouvez utiliser le caractère générique « **&#42;** » en fonction des règles de la liste de modèles autorisés ci-dessous.

-   Veillez à faire précéder toutes les URL du préfixe **http** ou **https** quand vous les entrez dans la liste.

-   Vous pouvez spécifier des numéros de port dans l'adresse. Si vous ne spécifiez pas un numéro de port, les valeurs suivantes sont utilisées :

    -   Port 80 pour http

    -   Port 443 pour https

    Vous ne pouvez pas utiliser de caractères génériques pour le numéro de port. Par exemple, **http&colon;//www&period;contoso&period;com:*;** et **http&colon;//www&period;contoso&period;com: /*;**

-   Utilisez le tableau suivant pour en savoir plus sur les modèles autorisés que vous pouvez utiliser pour spécifier des URL :

|Adresse URL|Détails|Correspond à|Ne correspond pas à|
    |-------|---------------|-----------|------------------|
    |http://www.contoso.com|Correspond à une page unique|www.contoso.com|host.contoso.com<br /><br />www.contoso.com/images<br /><br />contoso.com/|
    |http://contoso.com|Correspond à une page unique|contoso.com/|host.contoso.com<br /><br />www.contoso.com/images<br /><br />www.contoso.com|
    |http://www.contoso.com/&#42;|Correspond à toutes les URL commençant par www.contoso.com|www.contoso.com<br /><br />www.contoso.com/images<br /><br />www.contoso.com/videos/tvshows|host.contoso.com<br /><br />host.contoso.com/images|
    |http://&#42;.contoso.com/&#42;|Correspond à tous les sous-domaines sous contoso.com|developer.contoso.com/resources<br /><br />news.contoso.com/images<br /><br />news.contoso.com/videos|contoso.host.com|
    |http://www.contoso.com/images|Correspond à un dossier unique|www.contoso.com/images|www.contoso.com/images/dogs|
    |http://www.contoso.com:80|Correspond à une page unique avec un numéro de port|http://www.contoso.com:80||
    |https://www.contoso.com|Correspond à une page unique sécurisée|https://www.contoso.com|http://www.contoso.com|
    |http://www.contoso.com/images/&#42;|Correspond à un dossier unique et à tous ses sous-dossiers|www.contoso.com/images/dogs<br /><br />www.contoso.com/images/cats|www.contoso.com/videos|

-   Voici quelques exemples de certaines entrées que vous ne pouvez pas spécifier :

    -   &#42;.com

    -   &#42;.contoso/&#42;

    -   www.contoso.com/&#42;images

    -   www.contoso.com/&#42;images&#42;pigs

    -   www.contoso.com/page&#42;

    -   Adresses IP

    -   https://&#42;

    -   http://&#42;

    -   http://www.contoso.com:&#42;

    -   http://www.contoso.com: /&#42;

### Résolution des conflits entre la liste autorisée et la liste bloquée
Si plusieurs stratégies Managed Browser sont déployées sur un appareil et qu'un conflit se produit entre les paramètres, le mode (autorisé ou bloqué) et les listes d'URL sont évalués pour déterminer les conflits. En cas de conflit, le comportement suivant s'applique :

-   Si les modes dans chaque stratégie sont les mêmes, mais que les listes d'URL sont différentes, les URL ne sont pas appliquées sur l'appareil.

-   Si les modes dans chaque stratégie sont différents, mais que les listes d'URL sont les mêmes, les URL ne sont pas appliquées sur l'appareil.

-   Si un appareil reçoit des stratégies Managed Browser pour la première fois et qu'un conflit se produit entre deux stratégies, les URL ne sont pas appliquées sur l'appareil. Utilisez le nœud **Conflits de stratégies** de l'espace de travail **Stratégie** pour afficher les conflits.

-   Si un appareil a déjà reçu une stratégie Managed Browser et qu'une deuxième stratégie est déployée avec des paramètres en conflit, les paramètres d'origine restent sur l'appareil. Utilisez le nœud **Conflits de stratégies** de l'espace de travail **Stratégie** pour afficher les conflits.



<!--HONumber=Jul16_HO2-->


