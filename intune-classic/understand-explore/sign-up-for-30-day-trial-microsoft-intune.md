---
title: "S’inscrire à une version d’évaluation gratuite de 30 jours de Microsoft Intune | Microsoft Intune"
description: "Inscrivez-vous à une version d’évaluation gratuite de 30 jours de Microsoft Intune et installez-la."
keywords: 
author: lindavr
ms.author: lindavr
manager: angrobe
ms.date: 11/29/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 619a1d11-3d22-4635-8f70-770eba3e1712
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 560765fa9d9afa4a1050515e1b2304c998f8c158
ms.contentlocale: fr-fr
ms.lasthandoff: 05/23/2017


---

# <a name="sign-up-for-a-microsoft-intune-free-trial"></a>S’inscrire à une version d’évaluation gratuite de Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Cet article vous explique comment vous inscrire à une version d’évaluation Intune et comment préparer votre version d’évaluation avec quelques utilisateurs afin que vous puissiez ensuite suivre le guide d’évaluation associé pour voir comment Intune gère les appareils mobiles. <!---or app data when devices are not enrolled in Intune.--->

>[!Note]
> À compter de décembre 2016, Microsoft Intune sera migré vers le portail Azure et certaines inscriptions à des évaluations gratuites se trouveront dans Intune dans le portail Azure et d’autres dans l’Intune classique. Si votre version d’évaluation se trouve dans le portail Azure, vous trouverez le [contenu Intune Azure en version préliminaire](/intune/what-is--intune) plus utile si vous avez terminé les étapes décrites dans cet article.

## <a name="assumptions"></a>Hypothèses
Cet article d’inscription et le guide d’évaluation partent du principe que vous utilisez la version d’évaluation uniquement à des fins d’évaluation et que vous envisagez de démarrer avec un environnement propre quand vous allez vous abonner.

Pour vous permettre de démarrer facilement avec la version d’évaluation, nous configurons un environnement très simple qui utilise uniquement Intune et sera supposément votre seule méthode de gestion des appareils (appelée autorité de gestion des appareils mobiles). Toutefois, tout au long du guide, nous vous indiquerons du contenu technique plus approfondi si vous souhaitez en savoir plus sur certains points.

Dans la version d’évaluation, vous pouvez effectuer les mêmes opérations que dans une version d’abonnement ; la seule différence est que vous êtes limité à 100 comptes d’utilisateur dans la version d’évaluation.

## <a name="sign-up-for-your-trial"></a>S’inscrire à votre version d’évaluation
Visitez la page d’[inscription Intune](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0%20) et remplissez le formulaire pour vous inscrire afin d’obtenir un abonnement d’évaluation.

Si vous avez un compte professionnel ou scolaire que vous voulez utiliser pour votre version d’évaluation Intune, suivez plutôt ces [instructions de connexion](/intune-classic/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-1). Toutefois, cet article et ses guides d’évaluation supposent que vous n’utilisez pas un tel compte.

> [!TIP]
> Si la plupart des utilisateurs et opérations informatiques ont des paramètres régionaux différents des vôtres, vous pouvez définir ces paramètres régionaux pour votre version d’évaluation afin de tester les performances.

### <a name="post-sign-up-considerations"></a>Éléments à prendre en considération après l’inscription
Quand vous vous inscrivez pour obtenir une version d’évaluation, vous recevez un e-mail contenant les informations de votre compte à l’adresse e-mail que vous avez fournie lors de l’inscription. Cet e-mail confirme que votre version d’évaluation est active.

À la fin du processus d’inscription, vous serez redirigé vers une page permettant d’ajouter des utilisateurs et de leur attribuer des licences à l’aide du Centre d’administration Office 365. La prochaine fois que vous vous connecterez à **Intune classique** (https://manage.microsoft.com), vous serez automatiquement dirigé vers la console d’administration Intune.

Si votre version d’évaluation se trouve dans le **portail Azure**, accédez à https://portal.azure.com et connectez-vous avec vos informations d’identification de la version d’évaluation d’Intune.

## <a name="add-users"></a>Ajouter des utilisateurs
Avant de quitter le Centre d’administration Office 365 pour Intune, vous devez ajouter des utilisateurs à votre compte d’évaluation.

Dans le Centre d’administration Office 365, vous pouvez ajouter des utilisateurs individuellement ou en bloc en chargeant un fichier .csv. Nous effectuerons les deux opérations pour configurer votre version d’évaluation. Toutefois, dans votre environnement de production, vous souhaiterez probablement tirer parti de vos comptes d’utilisateur Azure Active Directory. Pour en savoir plus, consultez notre [Guide de prise en main](/intune-classic/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-3) et la section [Étapes suivantes](#Next-steps) de cet article.

### <a name="add-an-individual-user"></a>Ajouter un utilisateur individuel
1. Choisissez l’une des options d’ajout d’un utilisateur pour ouvrir un formulaire qui vous permet de créer un utilisateur. Seuls les éléments marqués d’un astérisque (\*) sont obligatoires.
![Image des options du bouton Ajouter un utilisateur](./media/sign-up/add-user.png)


2.  Quand vous ajoutez l’utilisateur, l’étape finale consiste à lui envoyer un e-mail avec son mot de passe Intune temporaire. Dans le cadre de cette évaluation, utilisez votre propre adresse e-mail professionnelle pour obtenir les informations de connexion et voir l’e-mail que vos utilisateurs recevront. Vous pouvez ensuite utiliser ces identités d’utilisateurs pour inscrire des appareils de test.<br/>

 ![Image de l’étape finale d’ajout d’utilisateur](./media/sign-up/new-user-2.png)

3. Si vous souhaitez affecter un rôle d’administrateur à un utilisateur après sa création, vous pouvez modifier le rôle dans le Centre d’administration Office 365 en sélectionnant le nom de l’utilisateur dans la liste d’utilisateurs, puis en choisissant **Modifier** dans la ligne de rôle pour afficher la liste des rôles d’utilisateur que vous pouvez sélectionner et affecter à cet utilisateur.

 ![Image des options de rôle d’utilisateur](./media/sign-up/change-user-role.png)

### <a name="import-multiple-users"></a>Importer plusieurs utilisateurs
1. Vous trouverez l’Assistant d’importation de plusieurs utilisateurs dans la liste **Plus**.

 ![Image de l’option permettant d’ajouter plusieurs utilisateurs](./media/sign-up/add-multiple-users.png)

2. Pour vous aider à configurer votre fichier .csv correctement, vous pouvez télécharger un fichier de modèle à remplir avec les données de vos utilisateurs. Téléchargez le fichier .csv qui contient des en-têtes et des exemples d’informations utilisateur pour voir exactement le type de données nécessaire pour chaque champ.

 ![Image de la première étape de l’Assistant Inscription en bloc](./media/sign-up/bulk-enroll-step-1.png)


3. Une fois que vous avez créé et enregistré votre fichier .csv, choisissez **Parcourir** pour sélectionner le fichier. Procédez aux vérifications, puis choisissez **Suivant**. Les utilisateurs sont chargés et ajoutés à votre liste d’utilisateurs actifs.

> [!NOTE]
> Les utilisateurs ne s’affichent pas dans Intune tant qu’ils n’ont pas inscrit un appareil à gérer.

Il est maintenant temps de passer à Intune pour commencer à gérer les utilisateurs, leurs appareils et leurs applications.

## <a name="keeping-the-admin-experiences-straight"></a>Assurer la clarté des expériences d’administration
### <a name="classic-intune"></a>Intune classique
Il existe deux portails que vous utiliserez pour Intune classique :
- Le Centre d’administration Office 365 ([portal.office.com](https://portal.office.com))
- La console d'administration Intune ([manage.microsoft.com](https://manage.microsoft.com))

Normalement, vous effectuerez votre travail dans la console d’administration Intune, illustrée ci-dessous. Il s’agit du site où vous configurez et gérez vos groupes, stratégies, appareils et applications.

![Image de la console d’administration Intune](./media/sign-up/intune-admin-console.png)

Toutefois, vous allez utiliser le Centre d’administration Office 365, illustré ci-dessous, pour ajouter et gérer vos utilisateurs et d’autres aspects de votre compte, notamment la facturation et le support.

![Image du Centre d’administration Office 365](./media/sign-up/office-admin-center.png)

Vous pouvez passer du Centre d’administration Office 365 à la console d’administration Intune. Les Centres d’administration sont situés sous le dernier élément dans le volet de navigation gauche. Choisissez **Intune** pour ouvrir la console d’administration Intune dans un nouvel onglet.

![Image du lien vers la console d’administration Intune](./media/sign-up/link-to-intune.png)

Pour revenir au Centre d’administration Office 365 à partir d’Intune, choisissez la tâche **Ajouter des utilisateurs** dans la page Vue d’ensemble des groupes.

![Image du lien vers le centre d’administration Office 365](./media/sign-up/task-add-users.png)

### <a name="intune-azure-preview"></a>Intune Azure (préversion)
Il existe trois portails que vous pouvez utiliser pour la version préliminaire d’Intune Azure :
- Le Centre d’administration Office 365 ([portal.office.com](https://portal.office.com))
- Le tableau de bord Intune dans Azure ([portal.azure.com](https://portal.azure.com))
- La console d'administration Intune classique ([manage.microsoft.com](https://manage.microsoft.com))

La première fois que vous vous connectez à Intune dans Azure, il est possible vous ne voyiez pas votre tableau de bord Azure. Pour ajouter le service Intune à votre tableau de bord Azure :
1. Choisissez **Autres services >** dans la liste des services Azure à gauche du tableau de bord, puis entrez Intune dans la zone de recherche.
2. Choisissez **Intune** dans la liste, puis sélectionnez l’étoile pour ajouter le service à la liste des services.<br/> ![Image de la sélection d’Intune dans la liste des services](./media/sign-up/azure-add-intune1.png)
3. Choisissez **Intune** dans la liste des services pour ouvrir le tableau de bord Intune.

Normalement, vous effectuez votre travail dans le tableau de bord Intune, comme indiqué ci-dessous. Il s’agit du site où vous configurez et gérez vos groupes, stratégies, appareils et applications. Vous pouvez accéder à la console d’administration Intune classique à partir du tableau de bord en choisissant la vignette **Ouvrir le portail Intune classique**. Pour revenir à la préversion d’Intune Azure, entrez https://portal.azure.com dans la barre d’adresse de votre navigateur, puis choisissez **Intune** dans la liste des services.

 ![Image du tableau de bord Intune](./media/sign-up/intune-azure-dashboard.png)


Toutefois, vous allez utiliser le Centre d’administration Office 365, illustré ci-dessous, pour ajouter et gérer vos utilisateurs et d’autres aspects de votre compte, notamment la facturation et le support.

![Image du Centre d’administration Office 365](./media/sign-up/office-admin-center.png)

Pour passer du Centre d’administration Office 365 au tableau de bord Intune, entrez https://portal.azure.com dans la barre d’adresse de votre navigateur. Choisissez **Intune** dans la liste des services.

Pour revenir d’Intune au Centre d’administration Office 365, entrez https://portal.office.com dans la barre d’adresse de votre navigateur. Si vous êtes déjà connecté à Intune, vous accéderez directement au Centre d’administration Office 365.

## <a name="next-steps"></a>Étapes suivantes
### <a name="classic-intune"></a>Intune classique
Scénario d’évaluation : [Évaluer la gestion des appareils mobiles dans Microsoft Intune](mobile-device-management-trial-guide-microsoft-intune.md)

### <a name="intune-azure-preview"></a>Intune Azure (préversion)
En savoir plus sur [Intune dans le portail Azure en version préliminaire](/intune/what-is-intune)

### <a name="integration-with-other-products"></a>Intégration dans d'autres produits
En savoir plus sur l’utilisation de vos comptes d’utilisateur Azure Active Directory avec Intune :
- [Configuration requise pour les identités](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-overview#design-considerations-overview)
- [Configuration requise pour la synchronisation d’annuaires](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-directory-sync-requirements)
- [Configuration requise pour l’authentification multifacteur](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-multifactor-auth-requirements)

En savoir plus sur l’utilisation d’[Intune avec System Center Configuration Manager](https://docs.microsoft.com/sccm/mdm/understand/hybrid-mobile-device-management)

