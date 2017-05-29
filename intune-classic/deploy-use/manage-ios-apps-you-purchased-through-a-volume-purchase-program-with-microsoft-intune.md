---
title: "Gérer les applications iOS achetées en volume | Microsoft Docs"
description: "Utilisez Intune pour gérer les applications que vous avez achetées en volume auprès d’Apple, en important les informations de licence à partir du magasin d’applications, en effectuant le suivi du nombre de licences que vous avez utilisées, et en vous empêchant d’installer un nombre de copies de l’application supérieur au nombre dont vous êtes propriétaire."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1dafc28a-7f8b-4fe0-8619-f977c93d1140
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: c05c9cb1a0de468f1a6663a7870631af159d9b04
ms.contentlocale: fr-fr
ms.lasthandoff: 05/23/2017


---

# <a name="manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune"></a>Gérer les applications iOS que vous avez achetées par le biais d’un programme d’achat en volume avec Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

L’App Store iOS vous permet d’acheter plusieurs licences pour une application que vous souhaitez exécuter dans votre entreprise. Vous pouvez ainsi réduire les coûts d’administration liés au suivi de plusieurs copies d’application achetées.

Microsoft Intune vous aide à gérer les applications que vous avez achetées par le biais de ce programme, en important les informations de licence à partir du magasin d’applications, en effectuant le suivi du nombre de licences que vous avez utilisées, et en vous empêchant d’installer un nombre de copies de l’application supérieur au nombre dont vous êtes propriétaire.

> [!Important]
> Intune affecte des licences d’application VPP iOS aux utilisateurs, et non aux appareils. Pour cette raison, les utilisateurs doivent saisir leur mot de passe ID Apple pour installer l’application.
> Le Programme d’achats en volume (VPP) Apple pour le secteur de l’éducation n’est pas pris en charge dans cette version.

## <a name="manage-volume-purchased-apps-for-ios-devices"></a>Gérer les applications pour appareils iOS achetées en volume
Vous achetez plusieurs licences pour des applications iOS par le biais du [Programme d’achat en volume (VPP) Apple](http://www.apple.com/business/vpp/). Cela implique la configuration d’un compte Apple VPP à partir du site web Apple et l’importation du jeton Apple VPP dans Intune.  Vous pouvez ensuite synchroniser vos informations d’achat en volume avec Intune et suivre votre utilisation des applications achetées en volume.

## <a name="before-you-start"></a>Avant de commencer
Avant de commencer, vous devez obtenir un jeton VPP auprès d’Apple et l’importer dans votre compte Intune. En outre, vous devez comprendre ce qui suit :

* Avec Intune, vous pouvez ajouter jusqu’à 256 jetons VPP.
* Si vous avez déjà utilisé un jeton VPP avec un autre produit, vous devez en générer un nouveau à utiliser avec Intune.
* Chaque jeton est valide pendant un an.
* Par défaut, Intune se synchronise avec le service Apple VPP deux fois par jour. Vous pouvez lancer une synchronisation manuelle à tout moment.
* Après avoir importé le jeton VPP dans Intune, n’importez pas le même jeton dans une autre solution de gestion d’appareils, car cela peut entraîner la perte des enregistrements utilisateur et de l’attribution de licence.
* Avant de commencer à utiliser iOS VPP avec Intune, supprimez les comptes d’utilisateur VPP existants créés avec d’autres fournisseurs de gestion des appareils mobiles. En guise de mesure de sécurité, Intune ne synchronise pas ces comptes d’utilisateur dans Intune. Intune synchronise uniquement les données du service Apple VPP qui ont été créées par Intune.
* Vous ne pouvez pas déployer des applications VPP iOS sur un appareil qui a été inscrit à l’aide du protocole d’inscription d’appareils (DEP) si l’affinité utilisateur a été configurée pour cet appareil.

## <a name="to-get-and-upload-an-apple-vpp-token"></a>Pour obtenir et charger un jeton Apple VPP

1.  Dans la [console d’administration Microsoft Intune](https://manage.microsoft.com), sélectionnez **Administration** &gt; **iOS et Mac OS X** &gt; **VPP (Volume Purchase Program)**.

2.  Cliquez sur le lien **Compte Apple VPP**. Si ce n’est déjà fait, inscrivez-vous au programme d’achat en volume (VPP) pour les entreprises. Une fois inscrit, téléchargez le jeton Apple VPP pour votre compte.

3.  Dans la page **Gérer un VPP (Volume Purchase Program) Apple** de la console Intune, sélectionnez **Charger le jeton VPP**.

4.  Dans la boîte de dialogue **Charger le jeton VPP**, entrez ou collez le nom du jeton VPP et votre ID Apple, puis sélectionnez **Charger**.

5.  Dans la boîte de dialogue d’avertissement, cochez la case pour indiquer que vous comprenez que vous ne pourrez pas basculer ultérieurement vers un autre compte VPP, puis sélectionnez **Oui**.

Dans la page **VPP (Volume Purchase Program)**, vous pouvez maintenant voir des informations sur le jeton Apple VPP, notamment quand a eu lieu sa dernière mise à jour, ainsi que sa date d’expiration et la date de sa dernière synchronisation avec Intune.

Vous pouvez synchroniser les données détenues par Apple avec Intune à tout moment en sélectionnant **Synchroniser maintenant**.

## <a name="to-deploy-a-volume-purchased-app"></a>Pour déployer une application achetée en volume

1.  Dans la [console d’administration Microsoft Intune](https://manage.microsoft.com), sélectionnez **Applications**&gt; **Applications** &gt; **Applications achetées en volume**. Cette liste répertorie toutes les applications qui ont été synchronisées à partir du service Apple VPP.

2.  Choisissez l’application que vous voulez déployer, sélectionnez **Gérer le déploiement**, puis suivez les instructions de la rubrique [Déployer des applications dans Microsoft Intune](deploy-apps-in-microsoft-intune.md) pour effectuer le chargement, la création et le déploiement de l’application.

> [!TIP]
> Vous devez choisir l’action de déploiement **Requis**. Les installations disponibles ne sont pas prises en charge. En outre, vous pouvez uniquement déployer l’application sur des groupes d’utilisateurs.

Quand vous déployez l’application comme une installation **Requise**, chaque utilisateur qui installe l’application utilise une licence.

Pour récupérer une licence, remplacez l’action de déploiement par **Désinstaller**. La licence est récupérée une fois l’application désinstallée.

Quand un utilisateur avec un appareil éligible essaie pour la première fois d’installer une application VPP, il est invité à participer au programme VPP d’Apple. Il doit accepter pour que l’installation de l’application se poursuivre.

S’il n’y a plus de licence disponible, le déploiement échoue.

## <a name="to-monitor-apple-vpp-apps"></a>Surveiller les applications Apple VPP
Vous pouvez surveiller les applications VPP qui ont été déployées et le nombre de licences utilisées à partir de l’espace de travail **Applications**, dans le nœud **Applications achetées en volume**.

> [!TIP]
> Vous pouvez également utiliser des **Filtres** d’application pour examiner l’état de chaque installation d’application.

### <a name="see-also"></a>Voir aussi
[Déploiement d’applications dans Microsoft Intune](deploy-apps-in-microsoft-intune.md)

