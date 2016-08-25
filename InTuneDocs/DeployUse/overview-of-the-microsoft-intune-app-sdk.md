---
title: "Vue d’ensemble du Kit de développement logiciel (SDK) de l’application Microsoft Intune | Microsoft Intune"
description: 
keywords: 
author: Msmbaldwin
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ef1751bb-3a2f-4662-a922-38c076869eb3
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 779127bfd39145010f0d9b6609286aaf4dedfdc8
ms.openlocfilehash: 8a9dfe8224b4e0e441691043eaffea73c456b3ec


---

# Vue d’ensemble du Kit de développement logiciel (SDK) de l’application Microsoft Intune
Le Kit de développement logiciel (SDK) de l’application Intune est disponible pour les plateformes iOS et Android et permet d’utiliser les fonctionnalités de gestion des applications mobiles avec Microsoft Intune. De plus, nous nous efforçons de réduire le nombre de modifications de code nécessaires de la part du développeur. Comme vous pourrez le constater, il est possible d’activer la plupart des fonctionnalités du Kit de développement logiciel (SDK) sans modifier le comportement de votre application. Pour une expérience utilisateur et administrateur améliorée, vous pouvez utiliser nos API dans le but de personnaliser le comportement de votre application pour les fonctionnalités qui la sollicitent. 

Une fois que vous avez activé votre application, les administrateurs informatiques peuvent déployer des stratégies sur les applications gérées par Intune et tirer parti de ces fonctionnalités pour protéger leurs données d’entreprise.

# Fonctionnalités
## Contrôler la capacité des utilisateurs à déplacer des documents d’entreprise
Les administrateurs informatiques peuvent contrôler le réadressage des fichiers des documents d’entreprise dans les applications gérées par Intune. Par exemple, ils peuvent déployer une stratégie qui empêche les applications de sauvegarde de fichiers de sauvegarder les données d’entreprise dans le cloud.  

## Configurer des restrictions de Presse-papiers
Les administrateurs informatiques peuvent configurer le comportement du Presse-papiers dans les applications gérées par Intune. Par exemple, ils peuvent déployer une stratégie empêchant les utilisateurs d’utiliser le Presse-papiers pour couper/copier du contenu à partir d’une application gérée par Intune et le coller dans une application non gérée.

## Configurer des restrictions de capture d’écran
Les administrateurs informatiques peuvent empêcher les utilisateurs d’effectuer des captures d’écran si une application gérée par Intune est affichée. Cette restriction empêche la capture et la divulgation de contenu d’entreprise confidentiel. Cette fonctionnalité est disponible uniquement pour les appareils Android. 

## Appliquer un chiffrement aux données enregistrées
Les administrateurs informatiques peuvent appliquer une stratégie garantissant le chiffrement des données enregistrées sur l’appareil par l’application.

## Réinitialiser à distance les données d’entreprise
Les administrateurs informatiques peuvent réinitialiser à distance les données d’entreprise dans une application gérée par Intune quand l’appareil est désinscrit de Microsoft Intune. Cette fonctionnalité est basée sur l’identité et supprime uniquement les fichiers associés à l’identité d’entreprise de l’utilisateur final. Pour cela, la fonctionnalité nécessite la participation de l’application. L’application peut spécifier l’identité pour laquelle la réinitialisation doit se produire en fonction des paramètres utilisateur. Si ces paramètres utilisateur ne sont pas spécifiés dans l’application, le comportement par défaut consiste à réinitialiser le répertoire de l’application et à avertir l’utilisateur final que l’accès aux ressources d’entreprise a été supprimé. 

## Imposer l’utilisation de Managed Browser
Les administrateurs informatiques peuvent imposer l’utilisation de Managed Browser quand il s’agit d’ouvrir des liens à partir d’applications gérées par Intune. Microsoft Intune Managed Browser permet de garantir que les liens qui figurent dans les messages électroniques (dans un client de messagerie géré par Intune) restent dans le domaine des applications gérées par Intune.

## Appliquer une stratégie de code confidentiel
Les administrateurs informatiques peuvent appliquer une stratégie de code confidentiel au démarrage d’une application gérée par Intune. Cette stratégie permet de s’assurer que les utilisateurs finaux qui ont inscrit leurs appareils auprès de Microsoft Intune sont les mêmes personnes qui démarrent les applications. Quand un utilisateur final configure son code confidentiel, le SDK d’application Intune utilise Azure Active Directory pour comparer les informations d’identification de l’utilisateur final à celles qui ont servi à inscrire l’appareil. 

## Demander aux utilisateurs d’entrer des informations d’identification avant de pouvoir démarrer les applications
Les administrateurs informatiques peuvent demander aux utilisateurs d’entrer leurs informations d’identification pour pouvoir démarrer une application gérée par Intune. Le Kit de développement logiciel (SDK) de l’application Intune utilise Azure Active Directory pour fournir une expérience d’authentification unique, dans laquelle les informations d’identification, une fois entrées, sont réutilisées pour les connexions suivantes. Nous prenons aussi en charge l’authentification des solutions de gestion d’identité [fédérées à l’aide d’Azure Active Directory](https://msdn.microsoft.com/en-us/library/azure/jj679342.aspx). 

## Vérifier l’intégrité et la conformité des appareils
Les administrateurs informatiques peuvent vérifier l’intégrité de l’appareil et sa conformité aux stratégies d’entreprise avant que les utilisateurs finaux accèdent aux applications gérées par Intune. Sur la plateforme iOS, cette stratégie vérifie si l’appareil est jailbroken. Sur la plateforme Android, cette stratégie vérifie si l’appareil est rooté.  





<!--HONumber=Jun16_HO4-->


