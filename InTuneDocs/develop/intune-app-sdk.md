---
title: "Avantages du SDK de l’application Intune | Microsoft Intune"
description: 
keywords: 
author: Msmbaldwin
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: cd9f05e7-26e6-45e0-8d38-67d8232b1cae
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b7f62c5ee18d8f69fa174f09a1c46b6925c7517c
ms.openlocfilehash: 3abf566831348de11f718370d6267e3ff4355bfb


---

# Présentation du Kit SDK de l’application Intune
Le Kit de développement logiciel (SDK) de l’application Intune est disponible pour les plateformes iOS et Android et permet d’utiliser les fonctionnalités de gestion des applications mobiles avec Microsoft Intune. De plus, nous nous efforçons de réduire le nombre de modifications de code nécessaires de la part du développeur. Comme vous pourrez le constater, il est possible d’activer la plupart des fonctionnalités du Kit de développement logiciel (SDK) sans modifier le comportement de votre application. Pour une expérience utilisateur et administrateur améliorée, vous pouvez utiliser nos API dans le but de personnaliser le comportement de votre application pour les fonctionnalités qui la sollicitent. Une fois que vous avez activé votre application, les administrateurs informatiques peuvent déployer des stratégies sur les applications gérées par Intune et tirer parti de ces fonctionnalités pour protéger leurs données d’entreprise.

## Fonctionnalités standard

### Contrôler la capacité des utilisateurs à déplacer des documents d’entreprise
Les administrateurs informatiques peuvent contrôler le réadressage des fichiers des documents d’entreprise dans les applications gérées par Intune. Par exemple, ils peuvent déployer une stratégie qui empêche les applications de sauvegarde de fichiers de sauvegarder les données d’entreprise dans le cloud.

### Configurer des restrictions de Presse-papiers
Les administrateurs informatiques peuvent configurer le comportement du Presse-papiers dans les applications gérées par Intune. Par exemple, ils peuvent déployer une stratégie empêchant les utilisateurs d’utiliser le Presse-papiers pour couper/copier du contenu à partir d’une application gérée par Intune et le coller dans une application non gérée.

### Configurer des restrictions de capture d’écran
Les administrateurs informatiques peuvent empêcher les utilisateurs d’effectuer des captures d’écran si une application gérée par Intune est affichée. Cette restriction empêche la capture et la divulgation de contenu d’entreprise confidentiel. Cette fonctionnalité est disponible uniquement pour les appareils Android.

### Appliquer un chiffrement aux données enregistrées
Les administrateurs informatiques peuvent appliquer une stratégie garantissant le chiffrement des données enregistrées sur l’appareil par l’application.

### Réinitialiser à distance les données d’entreprise
Les administrateurs informatiques peuvent réinitialiser à distance les données d’entreprise dans une application gérée par Intune quand l’appareil est désinscrit de Microsoft Intune. Cette fonctionnalité est basée sur l’identité et supprime uniquement les fichiers associés à l’identité d’entreprise de l’utilisateur final. Pour cela, la fonctionnalité nécessite la participation de l’application. L’application peut spécifier l’identité pour laquelle la réinitialisation doit se produire en fonction des paramètres utilisateur. Si ces paramètres utilisateur ne sont pas spécifiés dans l’application, le comportement par défaut consiste à réinitialiser le répertoire de l’application et à avertir l’utilisateur final que l’accès aux ressources d’entreprise a été supprimé.

### Imposer l’utilisation de Managed Browser
Les administrateurs informatiques peuvent imposer l’utilisation de Managed Browser quand il s’agit d’ouvrir des liens à partir d’applications gérées par Intune. Microsoft Intune Managed Browser permet de garantir que les liens qui figurent dans les messages électroniques (dans un client de messagerie géré par Intune) restent dans le domaine des applications gérées par Intune.

### Appliquer une stratégie de code confidentiel
Les administrateurs informatiques peuvent appliquer une stratégie de code confidentiel au démarrage d’une application gérée par Intune. Cette stratégie permet de s’assurer que les utilisateurs finaux qui ont inscrit leurs appareils auprès de Microsoft Intune sont les mêmes personnes qui démarrent les applications. Quand un utilisateur final configure son code confidentiel, le SDK de l’application Intune utilise Azure Active Directory pour comparer les informations d’identification de l’utilisateur final à celles qui ont servi à inscrire l’appareil

### Demander aux utilisateurs d’entrer des informations d’identification avant de pouvoir démarrer les applications
Les administrateurs informatiques peuvent demander aux utilisateurs d’entrer leurs informations d’identification pour pouvoir démarrer une application gérée par Intune. Le Kit de développement logiciel (SDK) de l’application Intune utilise Azure Active Directory pour fournir une expérience d’authentification unique, dans laquelle les informations d’identification, une fois entrées, sont réutilisées pour les connexions suivantes. Nous prenons également en charge l’authentification des solutions de gestion d’identité [fédérées à l’aide d’Azure Active Directory](https://msdn.microsoft.com/library/azure/jj679342.aspx).

### Vérifier l’intégrité et la conformité des appareils
Les administrateurs informatiques peuvent vérifier l’intégrité de l’appareil et sa conformité aux stratégies d’entreprise avant que les utilisateurs finaux accèdent aux applications gérées par Intune. Sur la plateforme iOS, cette stratégie vérifie si l’appareil est jailbroken. Sur la plateforme Android, cette stratégie vérifie si l’appareil est rooté.

## Fonctionnalités préliminaires
Le Kit de développement logiciel (SDK) de l’application Microsoft Intune inclut plusieurs fonctionnalités encore en phase préliminaire. Vous pouvez commencer l’intégration avec des API préliminaires, mais à des fins de test uniquement. Notez que ces fonctionnalités préliminaires s’ajoutent aux scénarios existants au lieu de les remplacer.

### Prise en charge de plusieurs identités dans le Kit de développement logiciel (SDK) de l’application Microsoft Intune
La prise en charge de plusieurs identités est une fonctionnalité qui permet la coexistence de comptes gérés par stratégie (d’entreprise) et non gérés (personnels) dans une même application.

### Exemple de scénario à plusieurs identités
De nombreux utilisateurs configurent à la fois des comptes de messagerie d’entreprise et personnels dans l’application Outlook pour iOS et Android. Quand un utilisateur accède aux données de son compte d’entreprise, l’administrateur doit être certain que la gestion des stratégies GAM sera appliquée. Toutefois, quand un utilisateur accède à un compte de messagerie personnel, ces données doivent être hors du contrôle de l’administrateur. À cet effet, Microsoft Intune cible la stratégie de gestion sur le compte d’entreprise uniquement, dans l’application. Cette fonctionnalité multi-identité permet de résoudre le problème de protection des données auquel les organisations sont confrontées, avec des appareils et des applications prenant en charge à la fois des comptes personnels et professionnels.

### Comment prendre en charge plusieurs identités
Les API préliminaires vous permettent de spécifier un nom d’utilisateur principal (UPN) avec les opérations de données spécifiques, telles que les opérations du Presse-papiers et les opérations de fichier. Le Kit de développement logiciel (SDK) de l’application Microsoft Intune utilise le nom UPN pour mettre en correspondance l’appel passé et le nom UPN qui a été utilisé pour inscrire l’appareil au service Microsoft Intune. Si les noms UPN correspondent, l’appel est traité comme un appel de « données d’entreprise » et les données sont protégées. Si les noms UPN ne correspondent pas, l’appel est traité comme un appel de « données personnelles » et les données ne sont pas protégées.

### Gestion des applications sans inscription de l’appareil
De nombreux utilisateurs dotés d’appareils personnels souhaitent voir et utiliser les données d’entreprise sans inscrire leur appareil personnel à un produit de gestion d’appareils mobiles (MDM). Étant donné que l’inscription MDM nécessite un contrôle global de l’appareil, les utilisateurs hésitent à donner ce contrôle global de leur propre appareil personnel à leur entreprise.

La gestion des applications sans inscription d’appareil permet au service Microsoft Intune de déployer une stratégie MAM sur une application directement, sans s’appuyer sur un canal MDM pour déployer la stratégie. Comme aucun canal MDM n’est nécessaire, l’inscription MDM ne l’est pas non plus.




<!--HONumber=Jul16_HO3-->


