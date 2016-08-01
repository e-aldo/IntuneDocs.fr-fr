---
title: "Gérer les applications iOS achetées en volume | Microsoft Intune"
description: "Utilisez Intune pour gérer les applications que vous avez achetées en volume auprès d’Apple, en important les informations de licence à partir du magasin d’applications, en effectuant le suivi du nombre de licences que vous avez utilisées, et en vous empêchant d’installer un nombre de copies de l’application supérieur au nombre dont vous êtes propriétaire."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 07/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1dafc28a-7f8b-4fe0-8619-f977c93d1140
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 6716a3d1fb53dc3de0189f637d5664d0a2023d05
ms.openlocfilehash: 8f7e77f00e6082c5b272a7ec2be835bc1ef97a28


---

# Gérer les applications iOS que vous avez achetées par le biais d’un programme d’achat en volume avec Microsoft Intune
L’App Store iOS vous permet d’acheter plusieurs licences pour une application que vous souhaitez exécuter dans votre entreprise. Vous pouvez ainsi réduire les coûts d’administration liés au suivi de plusieurs copies d’application achetées.

Microsoft Intune vous aide à gérer les applications que vous avez achetées par le biais de ce programme, en important les informations de licence à partir du magasin d’applications, en effectuant le suivi du nombre de licences que vous avez utilisées, et en vous empêchant d’installer un nombre de copies de l’application supérieur au nombre dont vous êtes propriétaire.

> [!Important]
> Actuellement, Intune affecte des licences d’application VPP iOS aux utilisateurs, et non aux appareils. Pour cette raison, les utilisateurs finaux doivent saisir leur mot de passe ID Apple pour installer l’application.

## Gérer les applications pour appareils iOS achetées en volume
Vous achetez plusieurs licences pour des applications iOS par le biais du programme [Apple Volume Purchase Program for Business (VPP)](http://www.apple.com/business/vpp/). Cela implique la configuration d’un compte Apple VPP à partir du site web Apple et du jeton Apple VPP dans Intune.  Vous pouvez ensuite synchroniser vos informations d’achat en volume avec Intune et suivre votre utilisation des applications achetées en volume.

## Avant de commencer
Avant de commencer, vous devez obtenir un jeton VPP auprès d’Apple et le charger vers votre compte Intune. En outre, vous devez comprendre ce qui suit :

* Chaque organisation ne peut avoir qu’un seul compte VPP et jeton.
* Une fois que vous associez un compte Apple VPP à Intune, vous ne pouvez pas associer un autre compte. C’est la raison pour laquelle il est très important que plusieurs personnes possèdent les détails du compte que vous utilisez.
* Si vous avez déjà utilisé un jeton VPP avec un autre produit, vous devez en générer un nouveau à utiliser avec Intune.
* Chaque jeton est valide pendant un an.
* Par défaut, Intune se synchronise avec le service Apple VPP deux fois par jour. Vous pouvez, toutefois, lancer une synchronisation manuelle à tout moment.
* Après avoir importé le jeton VPP dans Intune, n’importez pas le même jeton dans une autre solution de gestion d’appareils, car cela peut entraîner la perte des enregistrements utilisateur et de l’attribution de licence.
* Avant de commencer à utiliser iOS VPP avec Intune, supprimez les comptes d’utilisateur VPP existants créés avec d’autres fournisseurs de gestion des appareils mobiles. En guise de mesure de sécurité, Intune ne synchronise pas ces comptes d’utilisateur dans Intune. Intune synchronise à partir du service Apple VPP uniquement les données qui ont été créées par Intune. 
* Vous ne pouvez pas déployer des applications VPP iOS sur des appareils qui ont été inscrits à l’aide du protocole d’inscription d’appareils (DEP).

## Pour obtenir et charger un jeton Apple VPP

1.  Dans la [console d’administration Microsoft Intune](https://manage.microsoft.com), sélectionnez **Administration** &gt; **iOS et Mac OS X** &gt; **VPP (Volume Purchase Program)**.

2.  Cliquez sur le lien **Compte Apple VPP** et, si ce n’est pas déjà fait, inscrivez-vous au programme « Volume Purchase Program for Business ». Une fois inscrit, téléchargez le jeton Apple VPP pour votre compte.

3.  Dans la page **Gérer un VPP (Volume Purchase Program) Apple** de la console Intune, sélectionnez **Charger le jeton VPP**.

4.  Dans la boîte de dialogue **Charger le jeton VPP**, entrez ou collez le nom du jeton VPP et votre ID Apple, puis sélectionnez **Charger**.

5.  Dans la boîte de dialogue d’avertissement, cochez la case pour indiquer que vous comprenez que vous ne pourrez pas basculer ultérieurement vers un autre compte VPP, puis sélectionnez **Oui**.

Dans la page **VPP (Volume Purchase Program)**, vous pouvez maintenant voir des informations sur le jeton Apple VPP, notamment quand a eu lieu sa dernière mise à jour, ainsi que sa date d’expiration et la date de sa dernière synchronisation avec Intune.

Vous pouvez synchroniser les données détenues par Apple avec Intune à tout moment en sélectionnant **Synchroniser maintenant**.

## Pour déployer une application achetée en volume

1.  Dans la [console d’administration Microsoft Intune](https://manage.microsoft.com), sélectionnez **Applications** &gt; **Logiciels gérés** &gt; **Applications achetées en volume**. Cette liste répertorie toutes les applications qui ont été synchronisées à partir du service Apple VPP.

2.  Choisissez l’application que vous voulez déployer, sélectionnez **Gérer le déploiement**, puis suivez les instructions de la rubrique [Déployer des applications dans Microsoft Intune](deploy-apps-in-microsoft-intune.md) pour effectuer le chargement, la création et le déploiement de l’application.

Quand vous déployez l’application comme **Installation requise**, une licence est utilisée par chaque utilisateur qui l’installe.

Pour récupérer une licence, remplacez l’action de déploiement par **Désinstaller**. La licence est récupérée une fois l’application désinstallée.

Quand un utilisateur avec un appareil éligible essaie pour la première fois d’installer une application VPP, il est invité à participer au programme VPP d’Apple. Il doit accepter pour que l’installation de l’application se poursuivre.

> [!TIP]
> Examinez la colonne **État des conditions d’utilisation du VPP** pour voir l’état d’acceptation de chaque utilisateur pour lequel l’application a été déployée.

S’il n’y a plus de licence disponible, le déploiement échoue.

## Surveiller les applications Apple VPP
Vous pouvez surveiller les applications VPP qui ont été déployées et le nombre de licences utilisées à partir de l’espace de travail **Applications**, dans le nœud **Logiciels gérés** &gt; **Applications achetées en volume**.

> [!TIP]
> Vous pouvez également utiliser des **Filtres** d’application pour examiner l’état de chaque installation d’application.

### Voir aussi
[Déployer des applications dans Microsoft Intune](deploy-apps-in-microsoft-intune.md)




<!--HONumber=Jul16_HO4-->


