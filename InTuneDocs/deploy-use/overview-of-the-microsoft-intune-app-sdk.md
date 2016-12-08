---
title: "Vue d’ensemble du Kit SDK d’application Microsoft Intune | Microsoft Intune"
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
ms.sourcegitcommit: eeb85a28ea6f99a0123ec5df3b0d476a678b85cb
ms.openlocfilehash: 4cb153c601b83b113a22b2acf3da5200cdb70472


---

# <a name="overview-of-the-microsoft-intune-app-sdk"></a>Vue d’ensemble du Kit SDK d’application Microsoft Intune
Le Kit SDK d’application Intune est disponible pour les plateformes iOS et Android. Il permet d’utiliser les fonctionnalités de gestion des applications mobiles avec Microsoft Intune. De plus, il s’efforce de réduire le nombre de modifications de code que le développeur doit apporter.

Comme vous pourrez le constater, il est possible d’activer la plupart des fonctionnalités du Kit SDK sans modifier le comportement de votre application. Pour améliorer les expériences utilisateur et administrateur, personnalisez le comportement de votre application à l’aide de nos API pour les fonctionnalités nécessitant sa participation.

Une fois que vous avez activé votre application, les administrateurs informatiques peuvent déployer des stratégies sur les applications gérées par Intune et tirer parti de ces fonctionnalités pour protéger leurs données d’entreprise.

# <a name="features"></a>Fonctionnalités
## <a name="control-users-ability-to-move-corporate-documents"></a>Contrôler la capacité des utilisateurs à déplacer des documents d’entreprise
Les administrateurs informatiques peuvent contrôler le réadressage des fichiers des documents d’entreprise dans les applications gérées par Intune. Par exemple, ils peuvent déployer une stratégie qui empêche les applications de sauvegarde de fichiers de sauvegarder les données d’entreprise dans le cloud.  

## <a name="configure-clipboard-restrictions"></a>Configurer des restrictions de Presse-papiers
Les administrateurs informatiques peuvent configurer le comportement du Presse-papiers dans les applications gérées par Intune. Par exemple, ils peuvent déployer une stratégie empêchant les utilisateurs d’utiliser le Presse-papiers pour couper ou copier du contenu à partir d’une application gérée par Intune et le coller dans une application non gérée.

## <a name="enforce-encryption-on-saved-data"></a>Appliquer un chiffrement aux données enregistrées
Les administrateurs informatiques peuvent appliquer une stratégie garantissant le chiffrement des données enregistrées sur l’appareil par l’application.

## <a name="remotely-wipe-corporate-data"></a>Réinitialiser à distance les données d’entreprise
Les administrateurs informatiques peuvent réinitialiser à distance les données d’entreprise dans une application gérée par Intune quand l’appareil est désinscrit de Microsoft Intune. Cette fonctionnalité est basée sur l’identité et supprime uniquement les fichiers associés à l’identité d’entreprise de l’utilisateur final. Pour cela, la fonctionnalité nécessite la participation de l’application. L’application peut spécifier l’identité pour laquelle la réinitialisation doit se produire en fonction des paramètres utilisateur. Si ces paramètres utilisateur ne sont pas spécifiés dans l’application, le comportement par défaut consiste à réinitialiser le répertoire de l’application et à avertir l’utilisateur final que l’accès aux ressources d’entreprise a été supprimé.

## <a name="enforce-the-use-of-a-managed-browser"></a>Imposer l’utilisation de Managed Browser
Les administrateurs informatiques peuvent imposer l’utilisation de Managed Browser quand les utilisateurs ouvrent des liens à partir d’applications gérées par Intune. Quand les utilisateurs finaux se servent de Microsoft Intune Managed Browser, cela permet de garantir que les liens qui figurent dans les e-mails dans un client de messagerie géré par Intune restent dans le domaine des applications gérées par Intune.

## <a name="enforce-a-pin-policy"></a>Appliquer une stratégie de code confidentiel
Les administrateurs informatiques peuvent appliquer une stratégie de code confidentiel au démarrage d’une application gérée par Intune. Cette stratégie permet de s’assurer que les utilisateurs finaux qui ont inscrit leurs appareils auprès de Microsoft Intune sont les mêmes personnes qui démarrent les applications. Quand un utilisateur final configure son code confidentiel, le SDK d’application Intune utilise Azure Active Directory pour comparer ses informations d’identification à celles qui ont servi à inscrire l’appareil.

## <a name="require-users-to-enter-credentials-before-they-can-start-apps"></a>Demander aux utilisateurs d’entrer des informations d’identification avant de pouvoir démarrer les applications
Les administrateurs informatiques peuvent demander aux utilisateurs finaux d’entrer leurs informations d’identification pour pouvoir démarrer une application gérée par Intune. Le SDK d’application Intune utilise Azure Active Directory pour fournir une expérience d’authentification unique. Cela signifie que les informations d’identification, une fois entrées, sont réutilisées pour les connexions ultérieures. Le SDK prend également en charge l’authentification des solutions de gestion des identités [fédérées à l’aide d’Azure Active Directory](/active-directory/active-directory-aadconnect-federation-compatibility).

## <a name="check-device-health-and-compliance"></a>Vérifier l’intégrité et la conformité des appareils
Les administrateurs informatiques peuvent vérifier l’intégrité de l’appareil et sa conformité aux stratégies d’entreprise avant que les utilisateurs finaux ne puissent accéder aux applications gérées par Intune. Sur la plateforme iOS, cette stratégie vérifie si l’appareil est jailbreakée. Sur la plateforme Android, cette stratégie vérifie si l’appareil est rooté.  



<!--HONumber=Nov16_HO5-->


