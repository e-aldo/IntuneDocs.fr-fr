---
title: "Archive des nouveautés | Microsoft Intune"
description: 
keywords: 
author: Lindavr
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ed2db991-4729-49a7-a1e6-be2ffa0d03d1
ROBOTS: noindex,nofollow
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 779127bfd39145010f0d9b6609286aaf4dedfdc8
ms.openlocfilehash: 051d06afb0f29f2a97c1f06dc1102138e5f2be8f


---


## Septembre 2015
### Mises à jour relatives à la gestion des applications et des appareils mobiles
**Toutes les fonctionnalités de gestion iOS d’Intune prennent désormais en charge iOS 9** Pour plus d’informations sur les fonctionnalités de gestion d’iOS 9, consultez [ce billet de blog](http://blogs.technet.com/b/microsoftintune/archive/2015/09/09/day-zero-support-for-ios-9-with-intune.aspx).

**Nouvelle stratégie de configuration des applications mobiles pour iOS** La nouvelle stratégie de configuration des applications mobiles vous permet de fournir automatiquement les paramètres dont peut avoir besoin une application iOS au moment de son exécution. Par exemple, vous pouvez fournir un port réseau ou un nom d’utilisateur. Pour plus d’informations, consultez [Configurer des applications avec des stratégies de configuration des applications mobiles dans Microsoft Intune](https://technet.microsoft.com/library/mt481447.aspx).

**Une gestion des applications simplifiée pour les utilisateurs d’iOS 9**
 Dans cette version, vous pouvez intégrer les applications déjà déployées à la gestion Intune pour les utilisateurs d’iOS 9. Pour les versions antérieures d’iOS, quand vous déployez une application alors qu’une version non gérée de l’application est déjà installée sur un appareil, vous devez quand même demander à l’utilisateur de désinstaller l’application manuellement pour qu’Intune puisse installer l’application gérée.

 À compter de cette version d’Intune, vous pouvez inviter les utilisateurs d’appareils iOS 9 à autoriser Intune à contrôler la gestion de l’application et à appliquer des stratégies de gestion des applications mobiles pertinentes.

 **Gestion Windows 10** La nouvelle [stratégie de configuration générale de Windows 10](https://technet.microsoft.com/library/mt404697.aspx) vous permet de configurer les paramètres de mot de passe, d’appareil, de navigateur et autres pour les appareils inscrits qui exécutent Windows 10 et Windows 10 Mobile.

 **Créer et déployer des applications sur les appareils Windows 10 inscrits** Un nouveau type de programme d’installation de logiciel, Windows Installer via MDM (&#42;.msi), vous permet de créer et de déployer des applications Windows Installer sur des appareils inscrits qui exécutent Windows 10. Pour plus d’informations, consultez [Prendre en main le déploiement d’applications dans Microsoft Intune](https://technet.microsoft.com/library/dn646955.aspx).

### Modifications et mises à jour des applications Portail d'entreprise de Microsoft
Les modifications suivantes ont été apportées aux applications de portail d'entreprise dans cette version :

**iOS**
* Microsoft recueille automatiquement des données anonymes sur les performances et l'utilisation du portail d'entreprise pour améliorer les produits et services Microsoft. Les utilisateurs finaux peuvent désactiver la collecte de données à l'aide du paramètre Données d'utilisation sur leur appareil, mais les administrateurs n'ont aucun contrôle sur la collecte de données et ne peuvent pas changer la sélection de l'utilisateur final pour ce paramètre.
* Prise en charge de la résolution plein écran sur iPhone 6 et 6 Plus
* Correction de bogues pour améliorer la sécurité

### Nouveautés de la documentation Intune -- Septembre 2015
**Nouvelles rubriques**

|Nom|Détails|
|----|--------|
|[Paramètres de la stratégie de configuration Windows 10 dans Microsoft Intune](https://technet.microsoft.com/library/mt404697.aspx)|Nouvelle stratégie de configuration qui permet de gérer les paramètres et les fonctionnalités des appareils qui exécutent Windows 10 et Windows 10 Mobile.
| [Configurer des applications avec des stratégies de configuration des applications mobiles dans Microsoft Intune](https://technet.microsoft.com/library/mt481447.aspx)|Nouveau type de stratégie qui permet de fournir automatiquement des paramètres qui peuvent être nécessaires quand l’utilisateur exécute une application iOS. |

**Rubriques mises à jour**

|Nom|Détails|
|----|-------|
|[Utiliser des stratégies pour gérer les ordinateurs et appareils mobiles avec Microsoft Intune](https://technet.microsoft.com/library/dn743712.aspx)|Documentation mise à jour pour inclure les informations les plus récentes pour vous aider à comprendre et créer les stratégies.|

## Août 2015
### Mises à jour relatives à la gestion des applications et des appareils mobiles
* Les**conditions générales** qui régissent l'inscription et l'accès des entreprises à Intune sont [désormais gérées à l'aide de stratégies](https://technet.microsoft.com/library/mt405893.aspx). Vous pouvez cibler différents jeux de conditions générales pour répondre à des exigences spécifiques de groupes d'utilisateurs. Par exemple, vous pouvez déployer des conditions générales dans différentes langues en fonction de la zone géographique des groupes d'utilisateurs. Vous pouvez aussi [modifier vos conditions générales](https://technet.microsoft.com/library/mt405893.aspx#BKMK_TCVers) et spécifier une incrémentation des numéros de version, en demandant aux utilisateurs d'accepter les nouvelles conditions générales avant de pouvoir utiliser le portail d'entreprise.
* **Un certain nombre de stratégies Intune ont été renommées** pour améliorer la cohérence générale du produit et pour les trouver plus facilement. Pour obtenir la liste de toutes les stratégies Intune disponibles, consultez [Utiliser des stratégies pour gérer les ordinateurs et les appareils mobiles avec Microsoft Intune](https://technet.microsoft.com/library/dn743712.aspx).
* Les **profils de certificat PKCS #12 (.PFX)** sont disponibles pour Android 4.0 ou version ultérieure et Windows 10 (Desktop et Mobile) et versions ultérieures. L'utilisation de profils de certificat .PFX ne nécessite pas de serveur NDES. Découvrez comment utiliser des profils de certificat .PFX dans [Activer l’accès aux ressources d’entreprise en utilisant des profils de certificat avec Microsoft Intune](http://technet.microsoft.com/library/dn818904.aspx).
* **Les paramètres des limites réseau de l’entreprise pour Windows 10 Desktop et Mobile** permettent de bénéficier de paramètres VPN granulaires, comme décrit dans [Aider les utilisateurs à se connecter à leur travail à l’aide de profils VPN avec Microsoft Intune](https://technet.microsoft.com/library/dn818905.aspx)
* **L’application OneDrive pour Android prend désormais en charge les identités multiples**. Cette mise à jour ainsi que d'autres mises à jour relatives aux stratégies de gestion des applications mobiles sont décrites dans la [liste des applications Microsoft que vous pouvez gérer](https://technet.microsoft.com/library/dn708489.aspx).
* **Contournement du verrou d'activation iOS**. Si les appareils iOS appartenant à l'entreprise sont protégés par le verrou d'activation, vous devez entrer l'ID Apple et le mot de passe de l'utilisateur pour pouvoir effacer ou réactiver l'appareil. Cela peut présenter un défi quand les utilisateurs quittent l'entreprise et rendent un appareil appartenant à l'entreprise sans désactiver le verrou d'activation. Pour résoudre ce problème, vous pouvez utiliser le [contournement du verrou d’activation Intune](https://technet.microsoft.com/library/mt414176.aspx)

### Accès conditionnel pour les PC
Vous pouvez désormais configurer des stratégies d'accès conditionnel pour les PC. Ces stratégies permettent aux applications de bureau Office d'accéder à Exchange Online et aux services SharePoint Online.
Pour activer la stratégie d'accès conditionnel pour les PCs, il faut que le PC soit joint au domaine ou soit compatible.
* Consultez la section **Prise en main** dans [Gérer l’accès à la messagerie et à SharePoint avec Microsoft Intune](http://technet.microsoft.com/library/dn818907).aspx) pour obtenir la liste complète des conditions requises pour activer l’accès conditionnel pour les PC.
* Pour connaître les options que vous pouvez configurer pour activer l’accès conditionnel à la messagerie électronique, consultez la rubrique [Gérer l’accès à la messagerie avec Microsoft Intune](https://technet.microsoft.com/library/dn705841.aspx).
* Pour connaître les options que vous pouvez définir pour activer l’accès conditionnel à SharePoint Online, consultez [Gérer l’accès à SharePoint Online avec Microsoft Intune](https://technet.microsoft.com/library/dn705844.aspx).

### Modifications et mises à jour des applications Portail d'entreprise de Microsoft
Les modifications suivantes ont été apportées aux applications de portail d'entreprise dans cette version :

**Android**

Une fois connectés, les utilisateurs verront désormais s'afficher des instructions pour inscrire les appareils s'ils n'ont pas encore inscrit le leur.

### Nouveautés dans la documentation Intune -- Août 2015
**Nouvelles rubriques**

|Titre|Détails|
|-----|-------|
|[Aider à protéger les appareils iOS avec le contournement du verrou d'activation pour Microsoft Intune](https://technet.microsoft.com/library/mt414176.aspx)|Découvrez comment contourner le verrou d'activation iOS avec Intune quand un utilisateur quitte l'entreprise et qu'il restitue un appareil verrouillé.|

**Rubriques mises à jour**

|Titre|Détails|
|-----|-------|
|[Applications Microsoft utilisables avec les stratégies de gestion des applications mobiles de Microsoft Intune](https://technet.microsoft.com/library/dn708489.aspx)|Mise à jour des informations concernant les applications que vous pouvez gérer à l'aide de stratégies de gestion d'applications mobiles.
|[Utiliser des stratégies pour gérer les ordinateurs et appareils mobiles avec Microsoft Intune](http://technet.microsoft.com/library/dn743712.aspx)|Mise à jour mentionnant les dernières stratégies ajoutées à Intune.|
<!---
## July 2015
July updates for Intune are limited to behind-the-scenes enhancements that allow us to continue providing you with a high-quality service experience. New features are not included in this service update.

### Intune Onboarding benefit
Microsoft offers the Intune Onboarding benefit for eligible plans. The Onboarding benefit lets you work remotely with Microsoft specialists to get your Intune environment ready for use. For more information, see [Microsoft Intune Onboarding benefit description](https://technet.microsoft.com/library/mt228266.aspx)
### Changes and updates to Microsoft Company Portal apps
The following changes have been made to the company portal apps in this release.

**Android**

Microsoft automatically collects anonymous data about the performance and use of the company portal to improve Microsoft products and services. End users can turn off data collection by using the Usage Data setting on their device, but administrators have no control over the data collection and cannot change the end user’s selection for this setting.--->



<!--HONumber=Jun16_HO4-->


