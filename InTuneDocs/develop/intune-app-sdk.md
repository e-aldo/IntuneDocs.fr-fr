---
title: "Avantages du SDK d’application Intune | Documentation Microsoft"
description: 
keywords: 
author: mtillman
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: cd9f05e7-26e6-45e0-8d38-67d8232b1cae
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 613e293d9bd853d6de7cdc0d753cc8473afc180b
ms.openlocfilehash: e8f96499f006af590b6e7da295503696110dad4e


---

# <a name="intune-app-sdk-overview"></a>Présentation du Kit SDK d’application Intune
Le Kit SDK d’application Intune est disponible pour les plateformes iOS et Android et permet d’utiliser les fonctionnalités de gestion des applications mobiles avec Microsoft Intune. Il s’efforce de minimiser la quantité de modifications du code pour les développeurs d’applications. Vous pourrez constater qu’il est possible d’activer la plupart des fonctionnalités du SDK sans changer le comportement de votre application. Pour une meilleure expérience utilisateur et administrateur, personnalisez le comportement de votre application à l’aide de nos API, pour les fonctionnalités nécessitant sa participation. 

Une fois que vous avez activé votre application, les administrateurs informatiques peuvent déployer des stratégies sur les applications gérées par Intune et tirer parti de ces fonctionnalités pour protéger leurs données d’entreprise.

## <a name="regular-features"></a>Fonctionnalités standard

### <a name="control-users-ability-to-move-corporate-documents"></a>Contrôler la capacité des utilisateurs à déplacer des documents d’entreprise
Les administrateurs informatiques peuvent contrôler le réadressage des fichiers des documents d’entreprise dans les applications gérées par Intune. Par exemple, ils peuvent déployer une stratégie qui empêche les applications de sauvegarde de fichiers de sauvegarder les données d’entreprise dans le cloud.

### <a name="configure-clipboard-restrictions"></a>Configurer des restrictions de Presse-papiers
Les administrateurs informatiques peuvent configurer le comportement du Presse-papiers dans les applications gérées par Intune. Par exemple, ils peuvent déployer une stratégie empêchant les utilisateurs finaux d’utiliser le Presse-papiers pour couper/copier du contenu depuis une application gérée par Intune et le coller dans une application personnelle non gérée.

### <a name="enforce-encryption-on-saved-data"></a>Appliquer un chiffrement aux données enregistrées
Les administrateurs informatiques peuvent appliquer une stratégie garantissant le chiffrement des données enregistrées sur l’appareil par l’application.

### <a name="remotely-wipe-corporate-data"></a>Réinitialiser à distance les données d’entreprise
Les administrateurs informatiques peuvent réinitialiser à distance des données d’entreprise dans une application gérée par Intune. Cette fonctionnalité est basée sur l’identité et supprime seulement les fichiers associés à l’identité d’entreprise de l’utilisateur final. Pour cela, la fonctionnalité nécessite la participation de l’application. L’application peut spécifier l’identité pour laquelle la réinitialisation doit se produire en fonction des paramètres utilisateur. Si ces paramètres utilisateur ne sont pas spécifiés dans l’application, le comportement par défaut est de réinitialiser le répertoire de l’application et d’avertir l’utilisateur final que l’accès a été supprimé.

### <a name="enforce-the-use-of-a-managed-browser"></a>Imposer l’utilisation de Managed Browser
Les administrateurs informatiques peuvent imposer l’utilisation de l’application Intune Managed Browser lors de l’ouverture de liens à partir d’applications gérées par Intune. Ceci garantit que les liens qui apparaissent dans un environnement d’entreprise sont conservés dans le domaine des applications gérées par Intune.

### <a name="enforce-a-pin-policy"></a>Appliquer une stratégie de code confidentiel
Les administrateurs informatiques peuvent appliquer une stratégie de code confidentiel au lancement d’une application gérée par Intune. Ceci garantit que l’utilisateur qui lance l’application est celui qui s’est initialement connecté avec un compte professionnel ou scolaire inscrit. Quand un utilisateur final configure son code confidentiel, le SDK d’application Intune utilise Azure Active Directory pour comparer les informations d’identification de l’utilisateur final à celles du compte Intune inscrit.

### <a name="require-users-to-enter-credentials-before-they-can-start-apps"></a>Demander aux utilisateurs d’entrer des informations d’identification avant de pouvoir démarrer les applications
Les administrateurs informatiques peuvent demander aux utilisateurs d’entrer leurs informations d’identification pour pouvoir démarrer une application gérée par Intune. Le SDK d’application Intune utilise Azure Active Directory pour fournir une expérience d’authentification unique, dans laquelle les informations d’identification, une fois entrées, sont réutilisées pour les connexions suivantes. Nous prenons également en charge l’authentification des solutions de gestion d’identité [fédérées à l’aide d’Azure Active Directory](https://msdn.microsoft.com/library/azure/jj679342.aspx).

### <a name="check-device-health-and-compliance"></a>Vérifier l’intégrité et la conformité des appareils
Les administrateurs informatiques peuvent vérifier l’intégrité de l’appareil et sa conformité aux stratégies d’entreprise avant que les utilisateurs finaux accèdent aux applications gérées par Intune. Sur la plateforme iOS, cette stratégie vérifie si l’appareil est jailbreakée. Sur la plateforme Android, cette stratégie vérifie si l’appareil est rooté.

### <a name="sdk-multi-identity-support"></a>Prise en charge de la multi-identité par le SDK
La prise en charge de plusieurs identités est une fonctionnalité qui permet la coexistence de comptes gérés par stratégie (d’entreprise) et non gérés (personnels) dans une même application.

Par exemple, beaucoup d’utilisateurs configurent à la fois des comptes de messagerie d’entreprise et personnels dans l’application Outlook pour iOS et Android. Quand un utilisateur accède aux données de son compte d’entreprise, l’administrateur doit être certain que la gestion des stratégies GAM sera appliquée. Toutefois, quand un utilisateur accède à un compte de messagerie personnel, ces données doivent être hors du contrôle de l’administrateur. À cet effet, Microsoft Intune cible la stratégie de gestion sur le compte d’entreprise uniquement, dans l’application. Cette fonctionnalité multi-identité permet de résoudre le problème de protection des données auquel les organisations sont confrontées, avec des appareils et des applications prenant en charge à la fois des comptes personnels et professionnels.

* **Comment prendre en charge la multi-identité**Les API du SDK d’application Microsoft Intune vous permettent de spécifier un nom d’utilisateur principal (UPN) avec des opérations de données spécifiques, comme les opérations de Presse-papiers et les opérations de fichiers. Le SDK utilise le nom UPN pour mettre en correspondance l’appel passé et le nom UPN qui a été utilisé pour inscrire l’appareil auprès du service Microsoft Intune. Si les noms UPN correspondent, l’appel est traité comme un appel de « données d’entreprise » et les données sont protégées. Si les noms UPN ne correspondent pas, l’appel est traité comme un appel de « données personnelles » et les données ne sont pas protégées.

### <a name="app-management-without-device-enrollment"></a>Gestion des applications sans inscription de l’appareil

>[!IMPORTANT]
>La gestion des applications mobiles Intune sans inscription de l’appareil est disponible avec le SDK d’application Intune pour iOS uniquement. 


De nombreux utilisateurs dotés d’appareils personnels souhaitent voir et utiliser les données d’entreprise sans inscrire leur appareil personnel à un produit de gestion d’appareils mobiles (MDM). Étant donné que l’inscription MDM nécessite un contrôle global de l’appareil, les utilisateurs hésitent à donner ce contrôle global de leur propre appareil personnel à leur entreprise.

La gestion des applications sans inscription d’appareil permet au service Microsoft Intune de déployer une stratégie MAM sur une application directement, sans s’appuyer sur un canal MDM pour déployer la stratégie. Comme aucun canal MDM n’est nécessaire, l’inscription MDM ne l’est pas non plus.



<!--HONumber=Dec16_HO2-->


