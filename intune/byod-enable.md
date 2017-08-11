---
title: Activer le BYOD avec Microsoft Intune
description: "Un flux de travail de niveau supérieur pour la configuration d’Intune, de façon à offrir à votre organisation la possibilité de bénéficier d’une solution BYOD (« Apportez votre propre appareil »)."
keywords: 
author: lindavr
ms.author: lindavr
manager: angrobe
ms.date: 07/26/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 
ms.reviewer: vlpetros
ms.suite: ems
ms.openlocfilehash: 8684ea31420edd836038dc9337bd8bdf56e78ba6
ms.sourcegitcommit: 79116d4c7f11bafc7c444fc9f5af80fa0b21224e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/03/2017
---
# <a name="enable-byod-with-intune"></a>Activer le BYOD avec Intune

Cette rubrique vous propose un flux de travail général pour configurer Intune de façon à offrir à votre organisation la possibilité de bénéficier d’une solution BYOD (« Apportez votre propre appareil »). Elle organise la tâche en trois processus et propose des liens vers des rubriques de guide pratique.

Le flux de travail est divisé en trois processus décrits ci-dessous. Vous pouvez adapter certains aspects de chaque processus en fonction des besoins de votre organisation.

-   **[Inscrire des appareils et vérifier leur conformité](#enroll-devices-and-check-for-compliance)** explique comment permettre aux utilisateurs d’inscrire leurs appareils personnels pour la gestion avec Intune. Intune gère les appareils iOS, macOS, Android et Windows. Cette section explique aussi comment déployer des stratégies sur les appareils et vérifier qu’ils respectent les exigences de sécurité de base.

- **[Donner accès aux ressources d’entreprise](#provide-access-to-company-resources)**  vous montre comment permettre aux utilisateurs l’accès aux ressources d’entreprise de manière simple et sécurisée. Il suffit pour cela de déployer des profils d’accès sur les appareils gérés. Cette section explique aussi comment gérer les déploiements d’applications achetées en volume avec Intune.

-   **[Protéger les données d’entreprise](#protect-company-data)** vous explique comment fournir un accès conditionnel à des ressources d’entreprise, éviter les pertes de données et supprimer des applications et des données d’entreprise sur des appareils dont vous ne vous servez plus professionnellement ou qui ont été perdus ou volés.

[![Schéma du flux de travail général d’activation de BYOD avec Microsoft Intune](./media/workflow-diagram-for-byod.png)](./media/workflow-diagram-for-byod.png)

<!--- > <sup>You can download this infographic at https://gallery.technet.microsoft.com/Infographic-Management-3644ae41.</sup> --->

## <a name="before-you-begin"></a>Avant de commencer
Pour permettre aux utilisateurs d’inscrire leurs appareils, vous devez tout d’abord préparer le service Intune proprement dit. Pour ce faire, [attribuez des licences aux utilisateurs](licenses-assign.md) et [définissez l’autorité de gestion des appareils mobiles](mdm-authority-set.md).

Dans le même temps, vous pouvez aussi [personnaliser le portail d’entreprise](company-portal-customize.md). Ajoutez le logo de l’entreprise et fournissez des informations de support aux utilisateurs. Vous créez ainsi une expérience d’inscription et de support digne de confiance pour vos utilisateurs. Vous pouvez également créer des [conditions d’utilisation](terms-and-conditions-create.md) que les utilisateurs doivent accepter avant de s’inscrire, ou des [restrictions sur les appareils](enrollment-restrictions-set.md) pour spécifier les plateformes que vous prenez en charge.

## <a name="enroll-devices-and-check-for-compliance"></a>Inscrire des appareils et vérifier leur conformité

Après avoir préparé le service Intune, vous devez remplir les diverses conditions d’inscription pour les différents types d’appareil que vous souhaitez gérer. Le processus d’inscription d’appareils pour la gestion est simple, mais il varie légèrement d’un type d’appareil à un autre.

-   **Appareils iOS et Mac** : vous devez vous [procurer un certificat Push MDM Apple](apple-mdm-push-certificate-get.md) pour inscrire des appareils de type iPad, iPhone ou MacOS. Une fois que vous avez chargé votre certificat Push MDM sur Intune, les utilisateurs peuvent [inscrire des appareils iOS](/intune-user-help/enroll-your-device-in-intune-ios) à l’aide de l’application Portail d’entreprise et utiliser le site web du même nom pour [inscrire des appareils MacOS](/intune-user-help/enroll-your-device-in-intune-macos).

-   **Appareils Android** : vous n’avez rien à faire pour préparer le service Intune à l’inscription d’appareils Android. Les utilisateurs peuvent simplement [inscrire leurs appareils Android](/intune-user-help/enroll-your-device-in-intune-android) pour la gestion à l’aide de l’application Portail d’entreprise disponible sur Google Play.

-   **Appareils Windows Phone et PC** Les appareils Windows peuvent être inscrits au moyen d’une configuration supplémentaire. Pour simplifier l’expérience de vos utilisateurs, vous pouvez activer l’inscription automatique pour les PC et appareils mobiles Windows 10 dans Azure Active Directory (AD) Premium. Si vous n’avez pas Azure AD Premium, ou si vous devez prendre en charge Windows 8.1, vous pouvez créer [un alias DNS pour le serveur d’inscription](windows-enroll.md#enable-windows-enrollment-without-azure-ad-premium) et ainsi faciliter l’inscription.


### <a name="make-sure-that-managed-devices-meet-basic-security-requirements"></a>Vérifier que les appareils gérés respectent les exigences de sécurité de base

Une fois que les utilisateurs ont inscrit leurs appareils pour la gestion, le service informatique doit vérifier que les appareils utilisés pour accéder aux données et applications de l’entreprise respectent les exigences de sécurité de base. Ces règles peuvent inclure l’utilisation d’un code confidentiel pour accéder aux appareils et le chiffrement des données stockées sur les appareils. Un ensemble de règles de ce type est appelé une [stratégie de conformité](device-compliance.md).

Quand vous [déployez une stratégie de conformité](device-compliance-get-started.md) pour un utilisateur, Intune vérifie que tous les appareils qu’il a inscrits pour la gestion dans Intune respectent les exigences de sécurité de base que vous avez définies dans votre stratégie BYOD. Après avoir fait l’objet d’une vérification de conformité, un appareil retourne un rapport d’état à Intune. Dans certains cas, il peut être demandé aux utilisateurs de corriger les paramètres, par exemple le code confidentiel ou le chiffrement de l’appareil. À d’autres occasions, l’application Portail d’entreprise leur signale simplement les paramètres qui ne sont pas conformes à votre stratégie.

## <a name="provide-access-to-company-resources"></a>Fournir un accès aux ressources de l’entreprise

La première chose que la plupart des employés veulent sur leur appareil mobile est un accès aux e-mails et documents de la société. En outre, ils s’attendent à configurer cet accès sans passer par une procédure complexe ni appeler le support technique. Intune facilite la [création et le déploiement des paramètres de messagerie](email-settings-configure.md) des applications de messagerie natives qui sont préinstallées sur les appareils mobiles.


> [!NOTE]
> Intune prend en charge la configuration de profils de messagerie Android for Work pour les applications de messagerie Gmail et Nine Work qui se trouvent dans Google Play Store.

Intune vous permet aussi de mieux contrôler et protéger l’accès aux données d’entreprise locales quand les utilisateurs travaillent hors site. Les profils de messagerie, [VPN](wi-fi-settings-configure.md) et [Wi-Fi](vpn-settings-configure.md) d’Intune œuvrent ensemble pour autoriser l’accès aux fichiers et aux ressources dont ils ont besoin dans leur travail, où qu’ils se trouvent. Les applications et les services web de votre entreprise hébergés localement peuvent également être accessibles en toute sécurité et protégées en utilisant le proxy d’application Azure Active Directory et l’accès conditionnel.

### <a name="manage-volume-purchased-apps"></a>Gérer les applications achetées en volume
Intune permet d’effectuer facilement les tâches suivantes :
* Importer les informations de licence en volume à partir d’un App Store
* Suivre le nombre de licences utilisées
* Empêcher les utilisateurs d’installer plus de copies de l’application que vous n’en avez
* [Livrer des applications du Store aux appareils gérés](apps-deploy.md)
* Cibler des applications sur des appareils non gérés via le site web Portail d’entreprise

Intune vous permet aussi de gérer et déployer les applications que vous avez achetées en volume sur l’App Store iOS et le Windows Store pour Entreprises. Vous pouvez ainsi réduire les coûts d’administration liés au suivi des applications achetées en volume.

> [!TIP]
> Vous pouvez [configurer l’authentification unique (SSO) avec Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect). SSO permet aux utilisateurs de se connecter aux applications avec le nom d’utilisateur et le mot de passe de domaine qu’ils utilisent localement. Par ailleurs, vous pouvez [fournir un accès Internet aux applications web hébergées localement](https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-get-started) à l’aide du Proxy d’application Azure Active Directory.

-   [Gérer les applications achetées en volume pour appareils iOS](vpp-apps-ios.md). Vous achetez plusieurs licences d’applications iOS via le [Programme d’achat en volume (VPP) Apple pour les entreprises](http://www.apple.com/business/vpp/). Vous devez configurer un compte Apple VPP sur le site web Apple et charger le jeton Apple VPP sur Intune. Vous pouvez alors synchroniser vos informations d’achat en volume avec Intune et suivre votre utilisation des applications achetées en volume.

-   [Gérez les applications achetées sur le Windows Store pour Entreprises](windows-store-for-business.md). [Windows Store pour Entreprises](https://www.microsoft.com/business-store) est l’emplacement idéal pour trouver et acheter des applications pour votre organisation, individuellement ou en volume. En connectant le Store à Intune, vous pouvez gérer les applications achetées en volume à partir du portail Intune.

## <a name="protect-company-data"></a>Protéger les données d’entreprise

Intune protège les données d’entreprise à travers diverses couches de technologie. Dans la couche d’identité, l’accès conditionnel protège l’accès aux services. L'accès conditionnel autorise uniquement les appareils gérés et conformes à accéder aux ressources d’entreprise. Dans la couche d’application cliente, la gestion des applications mobiles (GAM) protège contre la perte de données.  Les stratégies de protection des applications empêchent le déplacement des données vers les applications ou les emplacements de stockage non protégés. Ces stratégies vous permettent aussi de réinitialiser les données d’entreprise en cas de perte ou de vol d’un appareil.

### <a name="enforce-conditional-access-to-company-resources"></a>Appliquer un accès conditionnel aux ressources d’entreprise

Vous pouvez combiner des stratégies de conformité à des [stratégies d’accès conditionnel](device-compliance.md) pour vérifier si les appareils respectent les exigences de sécurité de base imposées par votre stratégie BYOD. Si un appareil ne respecte pas les exigences, les règles s’appliquent et l’accès est refusé tant que l’appareil ne respecte pas les exigences de la stratégie. Cela garantit que seuls les appareils gérés et conformes peuvent accéder aux données de l’entreprise à partir de services comme Exchange ([Exchange sur site](exchange-connector-install.md) ou [Exchange Online](conditional-access-exchange-create.md)), SharePoint Online, Skype Entreprise Online, etc.
<!---first link was (https://docs.microsoft.com/intune/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune)
third link was (https://docs.microsoft.com/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune). check with Andre--->

> [!IMPORTANT]
> Les stratégies d’accès conditionnel ne fonctionnent pas si aucune stratégie de conformité n’est en place pour valider la conformité.

### <a name="prevent-data-loss-of-company-data-with-application-protection-policies"></a>Éviter la perte de données d’entreprise avec les stratégies de protection des applications

Grâce aux stratégies de protection des applications Intune, vous pouvez choisir le mode d’accès à vos données (avec ou sans inscription d’appareils). Cette souplesse vous permet de protéger les données d’entreprise de sorte que même si un utilisateur n’inscrit pas son appareil dans Intune, il peut toujours accéder aux données d’entreprise en toute sécurité.

Vous pouvez utiliser des [stratégies de protection des applications Intune](app-protection-policies.md) pour mieux protéger les données d’entreprise accessibles aux appareils iOS et Android de vos utilisateurs. En utilisant ces stratégies au niveau de l’application, vous pouvez contrôler la façon dont les données d’entreprise sont utilisées et partagées par les employés, même si l’appareil lui-même n’est pas géré par Intune.

Utilisez les [stratégies de protection des informations Windows](app-protection-policies-configure-windows-10.md) pour faire de même avec les appareils Windows 10 gérés. Ces stratégies fonctionnent sans interférer avec l’expérience de l’employé. Elles n’exigent pas de modifier votre environnement réseau ou d’autres applications.

### <a name="wipe-company-data-while-leaving-personal-data-intact"></a>Effacer les données d’entreprise tout en conservant les données personnelles intactes

Dès qu’un appareil est devenu inutile au travail, qu’il est réaffecté ou simplement perdu, vous pouvez supprimer les données et applications d’entreprise de celui-ci. Pour ce faire, vous pouvez utiliser les fonctionnalités de réinitialisation sélective et de réinitialisation complète d’Intune. Vos utilisateurs peuvent aussi réinitialiser à distance leurs appareils personnels à partir du portail d’entreprise Intune si ces appareils sont inscrits dans Intune.

Une [réinitialisation complète](devices-wipe.md) rétablit les paramètres d’usine de l’appareil et supprime les données et paramètres utilisateur. Une [réinitialisation sélective](devices-wipe.md#selective-wipe) supprime uniquement les données d’entreprise de l’appareil, mais garde intactes les données personnelles des utilisateurs.

Une fois l’opération lancée, l’appareil entame immédiatement le processus de réinitialisation sélective pour être extrait de la gestion. À l’issue du processus, toutes les données d’entreprise sont supprimées et le nom de l’appareil est retiré du portail Intune. Cela met fin au cycle de vie de gestion de l’appareil.
