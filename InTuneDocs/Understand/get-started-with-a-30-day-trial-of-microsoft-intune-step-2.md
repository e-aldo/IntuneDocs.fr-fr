---
# required metadata

title: Ajouter des utilisateurs à votre version d’évaluation de 30 jours de Microsoft Intune | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 9e40999b-46f7-447b-8974-72af82bec7ef

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Ajouter des utilisateurs à votre version d’évaluation de 30 jours de Microsoft Intune
Maintenant que vous avez configuré votre compte, vous allez utiliser l’Assistant **Nouveaux utilisateurs** pour ajouter des comptes d’utilisateur individuels à Intune ou l’Assistant **Ajouter des utilisateurs en bloc** pour ajouter des utilisateurs en bloc (consultez les instructions dans cette section).  Avant de commencer, il est important de comprendre comment Intune gère les comptes d'administrateur.

Un administrateur client se sert du Centre d’administration Office 365 pour ajouter des utilisateurs au **Groupe d’utilisateurs**Microsoft Intune. Les utilisateurs qui sont ajoutés au  **Groupe d'utilisateurs** se voient attribuer une licence d'abonnement Intune et c'est aussi de cette façon qu'ils apparaissent dans la console d'administration Microsoft Intune.

Contrairement aux comptes d’utilisateur standard, les comptes d’administrateur Intune ne sont pas créés dans le Centre d’administration Office 365. En effet, vous attribuez des droits d’administration avec accès en lecture seule ou accès complet aux utilisateurs via la console d’administration de l’espace de travail **Administration** sous **Gestion de l’administration**. Les administrateurs de service qui bénéficient d'un accès en lecture seule ne peuvent pas modifier les paramètres Intune, mais ils peuvent consulter les données et exécuter des rapports. Les administrateurs de service ayant un accès complet disposent de tous les droits d'administration possibles.

Vous pouvez afficher des informations d'administrateur client dans la console d'administration Intune, mais vous ne pouvez pas créer d'administrateurs client à cet emplacement. Par défaut, le propriétaire de l’abonnement devient administrateur client de votre service Microsoft Intune et dispose d’un accès complet au Centre d’administration Office 365 et à la console d’administration Intune. Nous vous recommandons de créer au moins un compte d’administrateur client supplémentaire dans le Centre d’administration Office 365. Cela vous permettra de déléguer plus facilement les tâches et vous serez assuré de pouvoir accéder à votre compte d’administrateur de service Intune si vous oubliez votre mot de passe.

## Ajouter des comptes d'utilisateur individuels
Pour créer des comptes d’utilisateur supplémentaires dans votre client d’évaluation, procédez comme indiqué ci-dessous. Pour rappel, chaque compte d’utilisateur que vous ajoutez représente l’une des 100 licences que vous obtenez dans le cadre de votre version d’évaluation gratuite d’Intune.

1.  Dans le [Centre d’administration Office 365](http://go.microsoft.com/fwlink/?LinkID=787455), choisissez **Ajouter des utilisateurs** &gt; **Nouveau**&gt; **Utilisateur** pour démarrer l’Assistant **Nouveaux utilisateurs**.

2.  Dans la page **Détails** , renseignez les champs requis.

3.  Dans la page **Paramètres** , définissez l' **emplacement** de l'utilisateur.

4.  Dans la page **Groupe**, cliquez sur **Suivant** pour accepter les valeurs par défaut et affecter une licence Intune au compte d’utilisateur.

5.  Dans la page **Adresse de messagerie** , spécifiez jusqu'à 5 adresses de messagerie auxquelles seront envoyées les notifications relatives au nom d'utilisateur et au mot de passe temporaire pour ce compte. Séparez les différentes adresses de messagerie par des points-virgules (;). Quand vous avez terminé, choisissez **Créer** pour ajouter l’utilisateur à votre abonnement.

6.  Dans la page **Résultats** , vous pouvez afficher le nouveau nom de compte et son mot de passe temporaire. Intune crée automatiquement le mot de passe temporaire.

7.  Quand le nouvel utilisateur apparaît dans le Centre d’administration Office 365, vérifiez qu’il a été correctement créé :

    1.  Dans la [console d’administration Intune](https://manage.microsoft.com/), choisissez **Administration** &gt; **Portail d’entreprise**, puis faites défiler la fenêtre jusqu’au bas de l’écran. Copiez l’URL figurant sous **Portail d’entreprise Intune**.

    2.  Ouvrez une nouvelle fenêtre de navigateur en « mode de confidentialité » (dans Internet Explorer, choisissez **Outils** &gt; **Navigation InPrivate**) ou sur un autre appareil, puis accédez à l’URL que vous avez copiée à l’étape précédente. À leur première connexion, les utilisateurs doivent définir un nouveau mot de passe pour le compte.

## Ajouter des utilisateurs en bloc
Pour ajouter des utilisateurs en bloc à Intune, utilisez l’Assistant **Ajouter des utilisateurs en bloc** pour charger un fichier de valeurs séparées par des virgules (CSV) qui contient les données de vos utilisateurs. Vous trouverez dans l'Assistant des liens qui vous permettront de télécharger un modèle vide et un exemple de fichier CSV. La première ligne de votre fichier CSV doit contenir, dans le bon ordre, chaque libellé de colonne de données utilisateur. Ensuite, pour chaque utilisateur mentionné dans le fichier CSV, vous devez inclure le **nom d'utilisateur** (par exemple, **bob@contoso.com**) et un **nom complet** (par exemple, **Bob Kelly**).

1.  Dans le [Centre d’administration Office 365](http://go.microsoft.com/fwlink/?LinkID=787455), choisissez **Utilisateurs** &gt; **Nouveau**.

2.  Choisissez **Ajout en bloc** pour démarrer l’Assistant Ajouter des utilisateurs en bloc.

3.  Dans la page **Sélectionner un fichier**, choisissez **Parcourir** pour spécifier et charger un fichier CSV existant à partir de votre ordinateur. Vous pouvez aussi télécharger un exemple de fichier CSV ou un fichier de modèle vide en suivant les liens fournis dans l'Assistant.

4.  Dans la page **Vérification**, passez en revue les résultats, puis choisissez **Afficher** pour plus de détails.

5.  Dans la page **Paramètres**, confirmez que l’état de connexion est **Autorisé**, puis définissiez l’**emplacement**. Ces paramètres s'appliquent à tous les comptes d'utilisateur ajoutés par le fichier CSV.

6.  Dans la page **Groupe**, choisissez **Suivant** pour accepter les valeurs par défaut et affecter une licence Intune à tous les comptes d’utilisateur ajoutés par le fichier CSV. Par défaut, la case est cochée. Une licence Intune est donc attribuée à chaque compte.

7.  Dans la page **Adresse de messagerie**, spécifiez jusqu’à cinq adresses de messagerie pour recevoir une notification relative aux noms d’utilisateur et mots de passe temporaires créés par Intune pour chaque compte. Séparez les différentes adresses de messagerie avec des points-virgules (;). Choisissez **Créer** pour ajouter les utilisateurs à votre abonnement.

8.  Sur la page **Résultats** , vous pouvez afficher les noms de compte et le mot de passe temporaire pour chaque compte d'utilisateur.

Chaque compte d’utilisateur que vous avez ajouté par importation apparaît désormais dans le nœud **Utilisateurs** du Centre d’administration Office 365. À leur première connexion, les nouveaux utilisateurs doivent définir un nouveau mot de passe pour leur compte d'utilisateur.

### Étapes suivantes
Félicitations ! Vous venez d’effectuer l’étape 2 de la procédure pas à pas de la *version d’évaluation de Microsoft Intune*.

>[!div class="step-by-step"]

>[&larr;**S’inscrire à une version d’évaluation**](.\get-started-with-a-30-day-trial-of-microsoft-intune-step-1.md)     [**Créer des groupes** &rarr;](.\get-started-with-a-30-day-trial-of-microsoft-intune-step-3.md)  


<!--HONumber=Jun16_HO1-->


