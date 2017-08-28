---
title: "Problèmes connus dans la Microsoft Intune sur Azure"
titleSuffix: Intune on Azure
description: "Consulter les problèmes connus dans Intune"
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 08/14/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f33a6645-a57e-4424-a1e9-0ce932ea83c5
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 5a9b7f69cded9258efb6c8a897e0c026f3228a6b
ms.sourcegitcommit: c248b5a15894f0ade23bad4644c3b7035a9fcce8
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/15/2017
---
# <a name="known-issues-in-microsoft-intune"></a>Problèmes connus dans Microsoft Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]


Utilisez cette rubrique pour en savoir plus sur les problèmes connus dans Microsoft Intune.

Si vous souhaitez signaler un bogue qui n’est pas répertorié ici, [créez une demande de support](get-support.md).

Si vous souhaitez voir une nouvelle fonctionnalité dans Intune, envisagez d’envoyer un rapport sur notre site [UserVoice](https://microsoftintune.uservoice.com/forums/291681-ideas/category/189016-azure-admin-console).

## <a name="migration"></a>Migration

### <a name="groups-created-by-intune-during-migration-might-affect-functionality-of-other-microsoft-products"></a>Les groupes créés par Intune pendant la migration peuvent affecter les fonctionnalités d’autres produits Microsoft

Lorsque vous migrez depuis la version Intune classique vers le portail Azure, un nouveau groupe nommé **Tous les utilisateurs - b0b08746-4dbe-4a37-9adf-9e7652c0b421** peut s’afficher. Ce groupe contient tous les utilisateurs dans votre Azure Active Directory, pas seulement les utilisateurs Intune sous licence. Cette utilisation peut entraîner des problèmes avec d’autres produits Microsoft si vous prévoyez que certains utilisateurs existants ou nouveaux ne soient membres d’aucun groupe.

### <a name="secondary-migration-required-for-select-capabilities"></a>Migration secondaire requise pour les fonctionnalités de sélection

Les comptes Intune créés avant janvier 2017 doivent être migrés avant de pouvoir utiliser les fonctionnalités suivantes dans le portail Azure :

- Profils d'inscription des appareils d'entreprise
- Programme d'inscription d'appareils Apple
- Prédéclarer les appareils d’entreprise par numéro de série iOS
- Comptes de gestionnaire d’inscription d’appareil
- Programme d’achats en volume (VPP) Apple

Parce que ces fonctionnalités ne peuvent pas être gérées à partir de la console Intune classique (Silverlight) et du portail Azure, la migration :
- Les désactive dans la console classique
- Les active dans le portail Azure  

À partir du 11 septembre 2017, la migration de ces fonctionnalités est fusionnée dans la migration principale vers Azure. Si votre compte a déjà été migré pour utiliser le portail Azure, cette migration secondaire aura lieu entre le 11 et le 22 septembre 2017. Une fois que la migration de votre compte commence, elle se termine le même jour. La migration peut prendre jusqu'à 6 heures à partir de la désactivation de ces fonctionnalités dans la console Intune classique.

Si vous gérez maintenant ces fonctionnalités Intune dans le portail Azure, tenez compte des points suivants :

#### <a name="removes-default-corporate-device-enrollment-profiles-in-apple-dep"></a>Supprime les profils d’inscription d’appareil professionnel par défaut dans Apple DEP
Le portail Azure ne prend pas en charge de profil d’inscription d’appareil d’entreprise « Par défaut » pour les appareils Apple DEP. Cette fonctionnalité, disponible dans la console Intune classique (Silverlight), est interrompue pour empêcher l’attribution de profils involontaire. Lorsque des numéros de série DEP sont synchronisés dans le portail Azure, aucun profil d’inscription d’appareil d’entreprise n’est affecté. Un profil d’inscription doit être affecté avant d’utiliser l’appareil.

#### <a name="apple-dep-token-restored-with-migration"></a>Jeton DEP Apple restauré avec la migration

Si vous avez supprimé un jeton du programme d’inscription des appareils Apple dans le portail Intune classique (Silverlight) et que vous ne chargez pas de nouveau jeton dans le portail Azure, le jeton d’origine est restauré dans le portail Azure quand vous effectuez la migration. Pour supprimer ce jeton et empêcher l’inscription au programme DEP, supprimez le jeton du portail Azure.

### <a name="status-blades-for-migrated-policies-do-not-work"></a>Les panneaux d’état pour les stratégies migrées ne fonctionnent pas

Vous ne pouvez pas afficher les informations d’état pour les stratégies qui ont été migrées à partir du portail classique dans le portail Azure. Toutefois, vous pouvez continuer à afficher des rapports pour ces stratégies dans le portail classique. Pour afficher les informations d’état pour les stratégies de configuration migrées, recréez-les dans le portail Azure.

## <a name="apps"></a>Applications

### <a name="ios-volume-purchased-apps-only-available-in-default-intune-tenant-language"></a>Applications iOS achetées en volume disponibles uniquement dans la langue du client Intune par défaut
Les applications iOS achetées en volume sont affichées et peuvent être affectées uniquement pour le même code de pays que votre compte Intune. Intune synchronise uniquement les applications ayant les mêmes paramètres régionaux iTunes que le code de pays du compte de client Intune. Par exemple, si vous achetez une application disponible uniquement dans le Store des États-Unis, mais que votre compte Intune est allemand, Intune n’affiche pas cette application.

### <a name="multiple-copies-of-the-same-ios-volume-purchase-program-are-uploaded"></a>Plusieurs copies du même programme d’achat en volume iOS sont chargées
Ne cliquez pas à plusieurs reprises sur le bouton **Charger** pour le même jeton VPP, sinon des jetons VPP en double seraient chargés et les applications seraient synchronisées plusieurs fois pour le même jeton VPP.

<!-- ## Groups -->

## <a name="device-configuration"></a>Configuration des appareils

### <a name="you-cannot-save-a-windows-information-protection-policy-for-some-devices"></a>Vous ne pouvez pas enregistrer une stratégie de protection des informations Windows pour certains appareils

Pour les appareils non inscrits avec Intune, vous pouvez spécifier un seul domaine principal dans le champ **Identité d’entreprise** dans les paramètres d’une stratégie de protection des informations Windows.
Si vous ajoutez des domaines supplémentaires (dans **Paramètres avancés** > **Réseau de périmètre** > **Ajouter un domaine protégé**), vous ne pouvez pas enregistrer la stratégie. Le message d’erreur affiché sera prochainement modifié pour être plus précis.

### <a name="cisco-anyconnect-vpn-client-support"></a>Prise en charge du client VPN Cisco AnyConnect

La dernière version du client VPN Cisco AnyConnect (4.0.07072) n’est pas compatible actuellement avec Intune.
Une mise à jour ultérieure d’Intune inclura la compatibilité avec cette version du client VPN. En attendant, nous vous recommandons de ne pas mettre à jour votre client VPN Cisco AnyConnect et de continuer à utiliser la version existante.

### <a name="using-the-numeric-password-type-with-macos-sierra-devices"></a>Utilisation du type de mot de passe numérique avec les appareils macOS Sierra

Actuellement, si vous sélectionnez le **type de mot de passe requis** **numérique** dans un profil de restriction d’appareil pour des appareils macOS Sierra, il est appliqué en tant que valeur **Alphanumérique**. Si vous souhaitez utiliser un mot de passe numérique avec ces appareils, ne configurez pas ce paramètre.
Ce problème sera peut-être corrigé dans une future version de macOS.

Pour plus d’informations sur ces paramètres, consultez [Paramètres de restriction des appareils macOS dans Microsoft Intune](device-restrictions-macos.md).

## <a name="compliance"></a>Compatibilité

### <a name="compliance-policies-from-intune-do-not-show-up-in-new-console"></a>Les stratégies de conformité d’Intune ne s’affichent pas dans la nouvelle console

Les stratégies de conformité créées dans le portail classique sont migrées, mais ne s’affichent pas dans le portail Azure en raison de changements de conception dans le portail Azure. Les stratégies de conformité créées dans le portail Intune classique sont toujours appliquées, mais vous devez les consulter et les modifier dans le portail Intune classique.
En outre, les nouvelles stratégies de conformité que vous créez dans le portail Azure ne sont pas visibles dans le portail Intune classique.

Pour plus d’informations, consultez [Qu’est-ce que la compatibilité des appareils ?](device-compliance.md).

<!-- ## Enrollment -->


## <a name="data-protection"></a>Protection des données

### <a name="ios-app-protection-policies"></a>Stratégies de protection des applications iOS

Vous pouvez définir des [stratégies de protection des applications pour iOS](app-protection-policy-settings-ios.md). Ces stratégies sont proposées aux utilisateurs d’appareils gérés par l’intermédiaire de la gestion des applications mobiles (GAM) sans inscription. En raison d’une erreur temporaire, vous pouvez uniquement définir ces stratégies pour les versions d’iOS à une seule décimale. Ainsi, au lieu de définir iOS 10.3.1 comme version minimale, définissez iOS 10.3. Ce problème sera résolu dans une prochaine mise à jour du SDK iOS.


## <a name="administration-and-accounts"></a>Administration et comptes

Les administrateurs globaux (également appelés administrateurs de clients) peuvent continuer à effectuer des tâches d’administration quotidiennes sans licence Intune ou Enterprise Mobility Suite (EMS) distincte. Toutefois, pour utiliser le service, par exemple pour inscrire leur propre appareil ou un appareil d’entreprise, ou pour utiliser le portail d’entreprise Intune, ils doivent avoir une licence Intune ou EMS.

<!-- ## Additional items -->
