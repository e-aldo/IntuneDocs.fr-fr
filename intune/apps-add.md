---
title: "Guide pratique pour ajouter des applications à Microsoft Intune"
titlesuffix: 
description: "Découvrez comment ajouter des applications à Microsoft Intune et affecter les applications à des utilisateurs et à des appareils. Intune prend en charge un large éventail de types d’application différents."
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/01/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a1ded457-0ecf-4f9c-a2d2-857d57f8d30a
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 91762eafbba5f96ce04f3ffd4d83f63434a3ac74
ms.sourcegitcommit: aafed032492c1b5861d7097a335f9bbb29ce3221
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/02/2018
---
# <a name="how-to-add-an-app-to-microsoft-intune"></a>Guide pratique pour ajouter une application à Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Pour pouvoir affecter, surveiller, configurer ou protéger des applications, vous devez les ajouter à Intune. Intune prend en charge un large éventail de types d’application différents. Les options disponibles diffèrent pour chaque type d’application.

Intune vous permet d’ajouter et d’affecter les types d’application suivants :
| Type d’application                                  | Installation                                                                  | Updates                       |
|------------------------------------------ |----------------------------------------------------------------------------   |---------------------------    |
| Applications sur le web                           | Intune crée un raccourci vers l’application web sur l’écran d’accueil de l’appareil          | Les mises à jour de l’application sont automatiques     |
| Applications écrites en interne (cœur de métier)  | Intune installe l’application sur l’appareil (vous fournissez le fichier d’installation)    | Vous devez mettre à jour l’application       |
| Applications du Store                       | Intune installe l’application sur l’appareil                                       | Les mises à jour de l’application sont automatiques     |
| Applications intégrées                        | Intune installe l’application sur l’appareil                                       | Les mises à jour de l’application sont automatiques     |


En plus des applications web, Intune prend en charge les plateformes spécifiques suivantes pour les applications du Store et les applications métier :
- Applications du Windows Store
    - Applications de l’App Store Android
    - Applications de l’App Store iOS
    - Application du Windows Phone 8.1 Store
    - Applications du Windows Store
    - Applications Android for Work
    - Applications Office 365 pour Windows
    - Applications Office 365 pour macOS
- Générer votre application (métier)
    - Applications métier Android
    - Applications métier iOS
    - Applications métier Windows Phone (fichiers .xap)
    - Applications métier Windows (fichiers .msi uniquement)
- Applications intégrées    

>[!TIP]
> Une application métier est une application que vous ajoutez à partir d’un fichier d’installation d’application. Par exemple, pour installer une application métier iOS, vous ajoutez l’application en choisissant **Application métier** comme **Type d’application** à partir du panneau **Ajouter une application**. Sélectionnez ensuite le fichier de package d’application (extension .ipa). Ces types d’applications sont généralement écrites en interne.

## <a name="assess-application-requirements"></a>Évaluer les besoins pour les applications 
En tant qu’administrateur informatique, vous devez déterminer non seulement les applications que votre groupe doit utiliser, mais également les fonctionnalités nécessaires pour chaque groupe et sous-groupe. Pour chaque application, vous devez déterminer les plateformes nécessaires, les groupes d’utilisateurs qui ont besoin de l’application, les stratégies de configuration à appliquer à ces groupes et les stratégies de protection à appliquer.  

De plus, vous devez déterminer si vous devez vous concentrer sur la gestion des appareils mobiles (MDM) ou uniquement sur la gestion des applications mobiles (MAM). Il est utile de gérer l’appareil à l’aide d’Intune (gestion des appareils mobiles) dans les cas suivants :
- Les utilisateurs ont besoin d’un profil Wi-Fi ou de connectivité d’entreprise WPN pour être productifs.
- Les utilisateurs ont besoin qu’un ensemble d’applications soit envoyé sur leur appareil.
- Votre organisation doit se conformer à des normes ou à des stratégies qui exigent des contrôles de gestion des appareils mobiles (MDM) spécifiques, tels que la sécurité ou le chiffrement.

Il est utile de gérer les applications avec Intune (gestion des applications mobiles) sans gérer l’appareil dans les cas suivants :
- Vous voulez permettre aux utilisateurs d’utiliser leur propre appareil (BYOD).
- Plutôt qu’une notification permanente au niveau de l’appareil, vous voulez fournir une fenêtre contextuelle qui ne s’affiche qu’une seule fois pour indiquer aux utilisateurs que des protections de gestion des applications mobiles sont en place.
- Vous voulez vous conformer à des stratégies qui exigent moins de fonctionnalités de gestion sur les appareils personnels. Par exemple, vous voulez gérer les données d’entreprise pour les applications, au lieu de les gérer pour l’ensemble de l’appareil.

Pour plus d’informations, consultez [Comparer MDM et MAM](byod-technology-decisions.md).

### <a name="determine-who-will-use-the-app"></a>Déterminer qui utilisera l’application
Après avoir ajouté une application à Intune, vous affectez un groupe d’utilisateurs qui peuvent utiliser l’application. Vous devez d’abord déterminer le groupe approprié qui doit avoir accès à l’application en fonction de la sensibilité des données que l’application contient. Vous devrez peut-être inclure ou exclure certains types de rôles au sein de votre organisation. Par exemple, seules certaines applications métier peuvent être nécessaires pour votre groupe de ventes, alors que les personnes travaillant essentiellement dans l’ingénierie, la finance, les ressources humaines ou dans le secteur juridique n’ont peut-être pas besoin d’utiliser les applications métier. De plus, votre groupe de ventes peut nécessiter une protection des données supplémentaires et un accès aux services d’entreprise internes sur leurs appareils mobiles. Vous devez déterminer la façon dont ce groupe se connectera aux ressources à l’aide de l’application. Les données auxquelles l’application accède sont-elles dans le cloud ou locales ? De plus, comment les utilisateurs se connecteront-ils aux ressources avec l’application ? Intune prend également en charge l’activation de l’accès aux applications mobiles qui nécessitent un accès sécurisé aux données locales, comme un serveur d’applications métier. Ce type d’accès s’effectue généralement à l’aide de [certificats gérés par Intune](certificates-configure.md) pour le contrôle d’accès, combinés à une passerelle VPN standard ou à un proxy dans le périmètre, comme le proxy d’application Microsoft Azure Active Directory. [L’outil de création de package de restrictions d’application et le SDK d’application](apps-prepare-mobile-application-management.md) d’Intune permettent de limiter les données utilisées dans votre application métier pour ne pas transmettre des données d’entreprise à des applications ou services de particuliers.

Utilisez le [Guide de planification, de conception et d’implémentation du déploiement Intune](planning-guide.md) pour déterminer la façon dont vous identifiez les groupes d’organisation qui sont associés à chaque scénario d’utilisation d’application principal et secondaire. Pour plus d’informations sur l’attribution d’applications à des groupes, consultez [Guide pratique pour attribuer des applications à des groupes avec Microsoft Intune](apps-deploy.md). 

### <a name="determine-the-type-of-app-for-your-solution"></a>Déterminer le type d’application pour votre solution
Vous pouvez choisir entre les types d’applications suivants :
- **Applications sur le web** : une application web est une application client-serveur. Le serveur fournit l’application web, ce qui inclut l’interface utilisateur, le contenu et les fonctionnalités. De plus, les plateformes d’hébergement web modernes offrent généralement, entre autres avantages, la sécurité et l’équilibrage de charge. Ce type d’application est géré séparément sur le web. Vous utilisez Intune pour pointer vers ce type d’application. Vous affectez également les groupes d’utilisateurs qui peuvent accéder à cette application. Notez qu’Android ne prend pas en charge les applications web.
- **Applications écrites en interne (métier)** : les applications créées en interne sont des applications métier. Les fonctionnalités de ce type d’application ont été créées pour l’une des plateformes Intune prises en charge, comme Windows, iOS ou Android. Votre organisation crée et vous fournit des mises à jour dans un fichier distinct. Vous fournissez des mises à jour de l’application aux utilisateurs en ajoutant et en déployant les mises à jour à l’aide d’Intune. 
- **Applications du Store** : une application du Store est une application qui a été chargée sur le Windows Store, le Store iOS ou l’Android Store. Le fournisseur de l’application de Store gère et fournit les mises à jour sur l’application. Vous sélectionnez l’application à partir de la liste de stores et vous l’ajoutez à l’aide d’Intune comme application disponible pour vos utilisateurs.

Quand vous déterminez les applications nécessaires à votre organisation, tenez compte de la façon dont ces applications s’intègrent aux services cloud, des données auxquelles les applications accèdent, si les applications sont disponibles pour les utilisateurs BYOD et si les applications nécessitent un accès à Internet.

Pour plus d’informations sur la détermination du type d’applications dont votre organisation a besoin, consultez **Applications** dans la section **Exigences concernant les fonctionnalités** de [Créer un design](planning-guide-design.md#feature-requirements).

### <a name="understanding-app-management-and-protection-policies"></a>Présentation de la gestion des applications et des stratégies de protection
Intune vous permet de modifier les fonctionnalités des applications que vous déployez pour les mettre en phase avec les stratégies de conformité et de sécurité de votre entreprise. Ce contrôle vous permet de déterminer la façon dont les données de votre entreprise sont protégées. Les applications gérées par Intune sont activées avec un ensemble complet de stratégies de protection des applications mobiles, comme les suivantes :

- Restriction des fonctions Copier-coller et Enregistrer sous
- Configuration des liens web pour qu’ils ouvrent dans l’application Intune Managed Browser
- Activation de l’utilisation de plusieurs identités et de l’accès conditionnel au niveau de l’application

Les applications gérées par Intune peuvent également activer la protection des applications sans inscription obligatoire, ce qui vous donne la possibilité d’appliquer des stratégies de protection contre la perte de données sans gérer l’appareil de l’utilisateur. De plus, vous pouvez incorporer la gestion des applications mobiles à vos applications mobiles et métier à l’aide du SDK d’application Intune et de l’outil de création de package de restrictions d’application. Pour plus d’informations sur ces outils, consultez [Vue d’ensemble du SDK d’application Intune](app-sdk.md).

### <a name="understanding-licensed-apps"></a>Présentation des applications sous licence
En plus des applications web, des applications de Store et des applications métier, vous devez également avoir connaissance de la destination des applications du programme d’achat en volume et des applications sous licence, comme les suivantes :     
- **Programme d’achat en volume Apple pour les entreprises (iOS et MacOS)** : l’App Store iOS vous permet d’acheter plusieurs licences d’une application que vous voulez exécuter dans votre entreprise. Le fait d’acheter plusieurs copies aide à gérer efficacement les applications de l’entreprise. Pour plus d’informations, consultez [Gérer les applications iOS achetées en volume](vpp-apps-ios.md).
- **Android for Work (Android)** : l’affectation d’applications sur des appareils Android for Work diffère de leur affectation sur des appareils Android standard. Toutes les applications que vous installez pour Android for Work proviennent du Google Play for Work Store. Vous vous connectez au Store, recherchez les applications souhaitées et les approuvez. L’application apparaît alors dans le nœud Applications sous licence du portail Azure. À partir de là, vous pouvez gérer l’affectation de l’application de la même façon que pour toute autre application.
- **Windows Store pour Entreprises (Windows 10)** : le Microsoft Store pour Entreprises est un endroit où vous pouvez trouver et acheter des applications pour votre organisation, individuellement ou en volume. En connectant le Windows Store à Microsoft Intune, vous pouvez gérer les applications achetées en volume depuis le portail Azure. Pour plus d’informations, consultez [Gérer des applications à partir du Microsoft Store pour Entreprises](windows-store-for-business.md). 

## <a name="before-you-start"></a>Avant de commencer
Tenez compte des points suivants avant de commencer à ajouter et affecter des applications.

- Quand vous ajoutez et affectez une application à partir d’un Store, les utilisateurs finaux doivent avoir un compte sur ce Store pour pouvoir installer l’application.
- Certaines applications ou certains éléments que vous affectez peuvent dépendre d’applications iOS intégrées. Par exemple, si vous affectez un livre à partir de l’App Store iOS, l’application iBooks doit être présente sur l’appareil. Si vous avez supprimé l’application iBook intégrée, vous ne pouvez pas utiliser Intune pour la réactiver.

## <a name="cloud-storage-space"></a>Espace de stockage cloud
Toutes les applications que vous créez en utilisant le type d’installation de programme d’installation de logiciel (par exemple, une application métier) sont empaquetées et chargées dans le stockage cloud Intune. Un abonnement d’essai à Intune inclut 2 Go de stockage cloud, utilisé pour stocker les applications gérées et les mises à jour. Un abonnement complet inclut 20 Go d’espace de stockage.

Vous pouvez utiliser la méthode de paiement d’origine pour acheter du stockage supplémentaire pour Intune.  Si vous avez payé par facture ou carte de crédit, visitez le [portail Gestion des abonnements](https://portal.office.com/adminportal/home?switchtomodern=true#/subscriptions).  Dans le cas contraire, contactez votre partenaire ou vendeur.

La configuration requise pour l’espace de stockage cloud est la suivante :

-   Tous les fichiers d’installation de l’application doivent être dans le même dossier.
-   La taille maximale de chaque fichier que vous chargez s’élève à 2 Go.

## <a name="how-to-create-and-edit-categories-for-apps"></a>Comment créer et modifier des catégories pour les applications

Vous pouvez utiliser les catégories d’applications pour trier les applications, afin que les utilisateurs finaux puissent les trouver plus facilement dans le portail d’entreprise. Vous pouvez affecter une ou plusieurs catégories à une application, par exemple, **Applications pour développeurs** ou **Applications de communication**.
Lorsque vous ajoutez une application à Intune, vous avez la possibilité de sélectionner la catégorie souhaitée. Utilisez les rubriques spécifiques à la plateforme pour ajouter une application et attribuer des catégories. Pour créer et modifier vos propres catégories, procédez comme suit :

1. Connectez-vous au [portail Azure](https://portal.azure.com).
2. Choisissez **Tous les services** > **Intune**. Intune se trouve dans la section **Surveillance + Gestion**.
3. Dans le panneau **Intune**, choisissez **Applications mobiles**.
4. Dans la charge de travail **Mobile Apps**, choisissez **Installation** > **Catégories d’application**.
5. Dans le panneau **Catégories d’application**, la liste des catégories actuelles s’affiche. Sélectionnez une des actions suivantes :
    - **Créer une catégorie** : sélectionnez **Ajouter** pour afficher le panneau **Créer une catégorie**, puis ajoutez un nom pour la nouvelle catégorie. Les noms peuvent être entrés dans une seule langue et ne sont pas traduits par Intune. Quand vous avez terminé, cliquez sur **Créer**.
    - **Modifier une catégorie** : pour n’importe quelle catégorie dans la liste, choisissez «**...**  ». Cette option affiche un menu contextuel vous permettant d’**Épingler au tableau de bord** ou de **Supprimer** la catégorie.

## <a name="apps-added-automatically-by-intune"></a>Applications automatiquement ajoutées par Intune

Intune contenait auparavant un nombre d’applications intégrées que vous pouviez affecter rapidement. En réponse à vos commentaires, cette liste a été supprimée et les applications intégrées n’apparaîtront plus.
Toutefois, si vous avez déjà affecté des applications intégrées, celles-ci resteront visibles dans la liste des applications. Vous pouvez continuer à affecter ces applications en fonction de vos besoins.
Dans une version ultérieure, nous prévoyons d’ajouter une méthode plus simple pour sélectionner et affecter les applications intégrées à partir du portail Azure.

## <a name="next-steps"></a>Étapes suivantes

Choisissez une des rubriques suivantes afin de savoir comment ajouter à Intune des applications pour chaque plateforme :

- [Applications de l’App Store Android](store-apps-android.md)
- [Applications métier Android](lob-apps-android.md)
- [Applications de l’App Store iOS](store-apps-ios.md)
- [Applications métier iOS](lob-apps-ios.md)
- [Applications Web (pour toutes les plateformes)](web-app.md)
- [Application du Windows Phone 8.1 Store](store-apps-windows-phone-8-1.md)
- [Applications métier Windows Phone](lob-apps-windows-phone.md)
- [Applications Windows Store](store-apps-windows.md)
- [Application métier Windows](lob-apps-windows.md)
- [Applications Office 365 pour Windows 10](apps-add-office365.md)
- [Applications intégrées](apps-add-built-in.md)

