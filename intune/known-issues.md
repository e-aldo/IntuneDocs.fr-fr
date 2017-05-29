---
title: "Problèmes connus dans la préversion de Microsoft Intune"
titleSuffix: Intune Azure preview
description: "Préversion Intune Azure : en savoir plus sur les problèmes connus dans la préversion"
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/25/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f33a6645-a57e-4424-a1e9-0ce932ea83c5
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 36b35e5311f6262c545a266003fb72b2febb277c
ms.contentlocale: fr-fr
ms.lasthandoff: 05/23/2017


---

# <a name="known-issues-in-the-microsoft-intune-preview"></a>Problèmes connus dans la préversion de Microsoft Intune


[!INCLUDE[azure_preview](./includes/azure_preview.md)]


Utilisez cette rubrique pour en savoir plus sur les problèmes connus dans la préversion d’Intune.

Si vous souhaitez signaler un bogue qui n’est pas répertorié ici, [créez une demande de support](https://docs.microsoft.com/intune-classic/troubleshoot/get-support).

Si vous souhaitez ajouter une nouvelle fonctionnalité à Intune, envisagez d’envoyer un rapport sur notre site [UserVoice](https://microsoftintune.uservoice.com/forums/291681-ideas/category/189016-azure-admin-console).

### <a name="groups-created-by-intune-during-migration-might-affect-functionality-of-other-microsoft-products"></a>Les groupes créés par Intune pendant la migration peuvent affecter les fonctionnalités d’autres produits Microsoft

Lorsque vous migrez depuis la version Intune classique vers le portail Azure, un nouveau groupe nommé **Tous les utilisateurs - b0b08746-4dbe-4a37-9adf-9e7652c0b421** peut s’afficher. Notez que ce groupe contient tous les utilisateurs dans votre Azure Active Directory, pas seulement les utilisateurs Intune sous licence. Ceci peut entraîner des problèmes avec d’autres produits Microsoft si vous prévoyez que certains utilisateurs existants ou nouveaux ne soient membres d’aucun groupe.

### <a name="altering-groups-created-by-intune-during-migration-will-delay-migration"></a>La modification des groupes créés par Intune pendant la migration retardera la migration

Pour préparer la migration, vos groupes sont copiés depuis Intune vers Azure AD. Toute autre modification que vous apportez dans le portail classique Intune sera actualisée dans le groupe Azure AD. Toutefois, les modifications apportées dans Azure AD ne seront pas synchronisées avec la console Intune classique. Cela peut entraîner l’échec de la migration vers le portail Azure, ainsi que des délais de migration.

### <a name="compliance-policies-from-intune-will-not-show-up-in-new-console"></a>Les stratégies de conformité d’Intune ne s’afficheront pas dans la nouvelle console

Les stratégies de conformité créées dans le portail Intune classique sont migrées, mais ne s’affichent pas dans le portail Azure. Cela est dû à une modification de la conception dans le portail Azure. Les stratégies de conformité créées dans le portail Intune classique sont toujours appliquées, mais vous devez les consulter et les modifier dans le portail classique.
En outre, les nouvelles stratégies de conformité que vous créez dans le portail Azure ne seront pas visibles dans le portail classique.
Pour plus d’informations, consultez [Qu’est-ce que la compatibilité des appareils ?](device-compliance.md).




### <a name="administration-and-accounts"></a>Administration et comptes

Les administrateurs globaux (également appelés administrateurs de clients) peuvent continuer à effectuer des tâches d’administration quotidiennes sans licence Intune ou Enterprise Mobility Suite (EMS) distincte. Toutefois, si les administrateurs généraux souhaitent utiliser le service, par exemple pour inscrire leur propre appareil ou un appareil d’entreprise, ou pour utiliser le portail d’entreprise Intune, ils doivent avoir une licence Intune ou EMS comme tout autre utilisateur.

### <a name="apple-enrollment-profile-migration"></a>Migration d’un profil d’inscription Apple
Dans quelques mois, Intune vous permettra de gérer les inscriptions au programme DEP (Device Enrollment Program) et à Apple Configurator par le biais du nouveau portail Azure. Si vous supprimez le jeton du programme DEP d’Apple et que vous ne chargez pas de jeton mis à jour, le jeton d’origine est restauré dans le nouveau portail Azure dans le cadre de la migration de votre compte Intune. Pour supprimer ce jeton et empêcher l’inscription au programme DEP, supprimez simplement le jeton dans le portail Azure. 

### <a name="rbac-for-apple-corporate-owned-device-enrollment"></a>RBAC pour l’inscription des appareils d’entreprise Apple
Les rôles Azure AD Locataire ou Administrateur de service sont nécessaires pour effectuer des tâches d’inscription Apple DEP et Apple Configurator, malgré le fait que les autorisations RBAC sont mentionnées et disponibles sous le rôle Utilisateur personnalisé. La prise en charge des rôles RBAC pour ces fonctionnalités sera annoncée ultérieurement.

