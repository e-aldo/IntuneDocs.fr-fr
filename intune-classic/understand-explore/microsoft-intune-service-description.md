---
title: Description du service | Microsoft Docs
description: "Intune est un service cloud qui vous permet de gérer des appareils Windows, iOS, Mac OS X, Android et Windows Mobile."
keywords: 
author: lindavr
ms.author: lindavr
manager: angrobe
ms.date: 09/22/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 40fa5a2e-6c0f-4150-9740-d5ddc0cdbda0
ms.reviewer: cacamp
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: c302189d8c1f45c7ecdc0ebe2493a48e6a254d53
ms.contentlocale: fr-fr
ms.lasthandoff: 05/23/2017


---

# <a name="microsoft-intune-service-description"></a>Description du service Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Microsoft Intune est un service cloud qui vous permet de gérer des appareils qui exécutent Windows, Mac OS X, iOS, Android ou Windows Mobile. Intune contribue aussi à protéger les applications et les données d’entreprise. Vous pouvez utiliser Intune en mode autonome ou l’intégrer à System Center Configuration Manager pour étendre vos fonctionnalités de gestion.

Microsoft propose le service d'intégration Intune pour les services éligibles dans les plans éligibles. Il vous permet de travailler à distance avec des spécialistes Microsoft pour rendre votre environnement Intune prêt à l’emploi. Pour plus d’informations sur le service d’intégration, consultez [Description du service d’intégration Microsoft Intune](http://go.microsoft.com/fwlink/?LinkId=619281).

Vous pouvez commencer à utiliser Intune avec une version d’évaluation gratuite de 30 jours qui comprend 100 licences utilisateur. Pour démarrer votre évaluation gratuite, [accédez à la page d’inscription Intune](https://www.microsoft.com/server-cloud/products/microsoft-intune/). Si votre organisation dispose d’un Contrat Entreprise ou d’un contrat de licence en volume équivalent, contactez votre représentant Microsoft pour installer votre version d’évaluation gratuite.

> [!NOTE]
> Si votre organisation possède déjà un compte professionnel ou scolaire Microsoft Online Services, et si vous pensez probablement prolonger cet abonnement à Intune en production à l’issue de la période d’essai, alors choisissez dans cette page l’option **Se connecter**, puis authentifiez-vous à l’aide du compte d’administrateur général de votre organisation. Cette action garantit que votre évaluation d’Intune est associée à votre compte professionnel ou scolaire existant.

Pour obtenir la liste des paramètres que vous pouvez configurer sur les appareils mobiles, consultez :

-   [Fonctionnalités de gestion des appareils inscrits de Microsoft Intune](/intune-classic/get-started/mobile-device-management-capabilities-in-microsoft-intune)

-   [Gestion des appareils mobiles (MDM) hybride avec System Center Configuration Manager et Microsoft Intune](https://technet.microsoft.com/library/mt627883.aspx)

Pour plus d’informations sur System Center Configuration Manager, consultez [Documentation pour System Center Configuration Manager](https://technet.microsoft.com/library/mt346023.aspx).

## <a name="learn-how-intune-service-updates-affect-you"></a>Découvrir les effets des mises à jour du service Intune
Intune étant un service en ligne, Microsoft peut le mettre à jour de façon régulière.

Utilisez les informations contenues dans cet article pour découvrir la fréquence des mises à jour du service et la notification préalable que nous vous adressons quand une mise à jour risque de perturber votre utilisation du service.

Pour en savoir plus sur les modifications du service Intune, consultez les [Nouveautés de Microsoft Intune](/intune-classic/deploy-use/whats-new-in-microsoft-intune). Le [blog Microsoft Intune](http://blogs.technet.com/b/microsoftintune/) évoque également les modifications du service et fournit des conseils utiles pour vous permettre de tirer le meilleur parti d’Intune.

Les mises à jour importantes du service vous seront également communiquées dans le Centre de messages du [portail de gestion Office 365](https://portal.office.com/Admin/Default.aspx). Si vous installez l’[application mobile d’administration Office 365](https://support.office.com/article/Office-365-Admin-Mobile-App-e16f6421-2a1a-4142-bf9d-9846600a060a), vous pouvez recevoir des notifications sur votre appareil mobile.

> [!NOTE]
> Vous pouvez surveiller l’état du service Intune dans le [portail de gestion Office 365](https://portal.office.com/Admin/Default.aspx). Choisissez **État du service** dans le volet gauche.  

Voici les types de notifications que Microsoft fournit à propos du service Intune :
-   Pour vous aider à planifier les modifications du service, nous vous notifions au moins 30 à 90 jours avant la mise à niveau du service, selon l’impact de la modification. Ces communiqués empruntent des canaux de communication internes au produit, comme des alertes dans le panneau d’affichage. Ces modifications peuvent inclure ce qui suit :
    * Mises à jour susceptibles d’avoir un impact sur la conformité ou la réglementation.
    * Modification de l’expérience utilisateur, de l’interface utilisateur et des flux de travail
    * API nouvelles ou modifiées : vous êtes invité à tester la compatibilité descendante des applications personnalisées.
    * Évolution de la configuration requise, par exemple, la version minimale requise du navigateur.
    * Mises à jour nécessitant de votre part des mesures pour activer la fonctionnalité ou éviter une interruption du service liée à cette fonctionnalité.
-   Microsoft fournit des informations sur les nouvelles fonctions, les nouvelles fonctionnalités et les améliorations apportées aux fonctionnalités existantes de notre mise à jour mensuelle du service. En général, Microsoft déploie les mises à jour du service aux alentours du 15 de chaque mois. Les mises à jour sont décrites dans [Nouveautés de Microsoft Intune](/intune-classic/deploy-use/whats-new-in-microsoft-intune).
    -   En cas de suppression du service Intune, vous êtes notifié 12 mois à l’avance.

## <a name="choose-the-management-solution-thats-right-for-you"></a>Choisissez la solution de gestion qui vous convient
Vous pouvez configurer Intune de plusieurs manières pour gérer et protéger les appareils mobiles et les ordinateurs de votre entreprise (appelés **appareils** dans cet article).

-**Configuration autonome d’Intune.** Utilisez la console d’administration web intégrée à Intune pour gérer les appareils de votre organisation. Intune peut être utilisé sans infrastructure informatique locale. Si vous utilisez Intune avec les services de domaine Active Directory, vous pouvez utiliser les comptes d’utilisateur de domaine que vous gérez avec les services de domaine avec Intune.

-**Intune avec System Center Configuration Manager.** Utilisez la console d’administration de Configuration Manager pour gérer les ordinateurs et les appareils mobiles de votre entreprise. Cette configuration peut vous aider à gérer tous les appareils de votre organisation par l’intermédiaire d’une seule console, la console d’administration Configuration Manager. Configuration Manager prend en charge un très grand nombre d’appareils mobiles, de serveurs et d’ordinateurs. Pour plus d’informations sur Configuration Manager, consultez [Gestion des appareils mobiles (MDM) hybride avec System Center Configuration Manager et Microsoft Intune](https://technet.microsoft.com/library/mt627883.aspx). Pour déterminer l’approche la plus appropriée pour vous, consultez [Choisir entre une gestion des appareils mobiles Microsoft Intune autonome et une gestion des appareils mobiles hybride avec Configuration Manager](https://technet.microsoft.com/library/mt706478.aspx).


## <a name="learn-more-about-intune"></a>En savoir plus sur Intune
Découvrez plus en détail Intune par le biais de ces ressources :

- Le [Centre de gestion de la confidentialité Microsoft Intune](https://www.microsoft.com/server-cloud/products/intune-trust-center/) fournit des informations sur les pratiques de sécurité, de confidentialité et de conformité d’Intune, et décrit certaines certifications d’Intune.

- [Fonctionnalités de gestion des appareils inscrits de Microsoft Intune](/intune-classic/get-started/mobile-device-management-capabilities-in-microsoft-intune)

### <a name="see-also"></a>Voir aussi
[Microsoft Intune]/intune-classic/) [Bibliothèque de documentation pour System Center 2012 Configuration Manager](https://technet.microsoft.com/library/gg682041.aspx)

[Nouveautés de Microsoft Intune](/intune-classic/deploy-use/whats-new-in-microsoft-intune)

