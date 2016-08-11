---
title: Migrer vers Intune | Microsoft Intune
description: 
keywords: 
author: jeffgilb
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 88936b8a-7453-4410-b6db-29f636ba3e72
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 317b8cc277eb8dffc1cb29739f3f78cfa3241602
ms.openlocfilehash: c6bd34c910f56e7dfad142034ef6fd7a027cd2c4


---

# Migrer vers Intune


Vous pouvez procéder comme suit pour migrer vers Intune depuis votre solution de gestion de mobilité d’entreprise :

![Étapes de migration pour Intune](./media/migrate-intune-steps.png)

## Notification aux utilisateurs

Une fois que vous êtes certain que le déploiement pilote Intune répond à vos besoins, annoncez à vos utilisateurs la future migration de leurs appareils vers Intune. Des e-mails, des instructions et des [affiches](https://gallery.technet.microsoft.com/Intune-End-User-Enrollment-3a0c9b0c?WT.mc_id=Blog_Intune_General_PCIT) peuvent aider à cerner les attentes et fournir des détails d’inscription pour les étapes que l’utilisateur doit suivre pour maintenir une connectivité ininterrompue aux ressources d’entreprise et aux applications. Assurez-vous que votre équipe de support est prête à aider les utilisateurs dans le processus de migration.

## Modification de votre solution de gestion de mobilité d’entreprise existante

Selon la manière dont vous souhaitez gérer les stratégies d’accès conditionnel entre votre solution de gestion de mobilité d’entreprise existante et Intune, vous devrez peut-être désactiver vos stratégies d’accès conditionnel existant. Vous désactiverez vos stratégies d’accès conditionnel existantes OU n’inclurez pas les utilisateurs/appareils que vous vous apprêtez à migrer vers Intune dans les stratégies d’accès conditionnel existantes.  N’utilisez pas Intune et votre solution de gestion de mobilité d’entreprise pour appliquer des stratégies d’accès conditionnel aux mêmes utilisateurs/appareils.

## Activation de stratégies d’accès conditionnel Intune (facultatif)

Si vous avez décidé d’appliquer immédiatement les stratégies d’accès conditionnel sans une période de grâce pour la migration des appareils, activez des stratégies d’accès conditionnel dans Intune au cours de cette étape.  Assurez-vous que cette décision est bien communiquée à vos utilisateurs et à votre équipe de support technique.  Si les appareils ne sont pas inscrits à Intune et ne sont pas conformes aux stratégies Intune, les utilisateurs ne pourront pas accéder aux ressources d’entreprise jusqu’à ce qu’ils s’inscrivent à Intune et que les appareils soient conformes aux stratégies Intune.

## Désinscription d’appareils de votre solution de gestion mobilité d’entreprise existante

Les appareils doivent être désinscrits de votre solution de gestion de mobilité d’entreprise existante avant leur inscription à Intune. Nous recommandons d’autoriser les utilisateurs d’annuler l’inscription de leurs appareils eux-mêmes pour une expérience utilisateur optimale.  Suivez les conseils de désinscription donnés par le fournisseur de votre solution pour vous assurer que vous supprimez correctement les utilisateurs et les appareils de votre plateforme et garantir une interruption minimale pour vos utilisateurs finaux.

## Inscription des appareils à Intune

Les utilisateurs planifiés pour la migration doivent immédiatement s’inscrire à Intune pour éviter la perte de l’accès aux ressources d’entreprise, aux e-mails et aux applications ou rétablir cet accès. Si vous avez configuré l’accès conditionnel et que les utilisateurs essaient de se connecter à la messagerie électronique avant de s’inscrire auprès d’Intune, leur accès est refusé et un e-mail d’inscription leur est envoyé. Cet e-mail les guide lors du processus d’inscription de leur appareil auprès d’Intune.  Les utilisateurs peuvent également s’inscrire à Intune par le biais de l’application Portail d’entreprise Intune ou en mode natif par le biais des systèmes d’exploitation Windows 8.1 et Windows 10 Mobile. Reportez-vous à [Ce qu'il faut dire à vos utilisateurs finaux concernant l'utilisation de Microsoft Intune](what-to-tell-your-end-users-about-using-microsoft-intune.md) pour obtenir des conseils supplémentaires sur les étapes d’inscription par plateforme.

## Configuration d’un accès conditionnel Intune (facultatif)

Si vous avez autorisé une période de grâce pour l’application de l’accès conditionnel, activez des stratégies d’accès conditionnel dans Intune pour démarrer la mise en œuvre lorsque la période de grâce que vous avez communiquée à vos utilisateurs finaux est terminée. Tous les appareils devront répondre immédiatement aux exigences de la stratégie d’accès conditionnel Intune.

## Inscription des appareils et des utilisateurs restants

Maintenant que vous avez activé l’accès conditionnel, tous les utilisateurs doivent s’inscrire à Intune et répondre aux stratégies de conformité de votre organisation pour accéder aux ressources d’entreprise. Si vous avez migré vos utilisateurs dans une inscription en plusieurs phases (pas simultanément), répétez les étapes ci-dessus jusqu’à ce que tous les appareils et tous les utilisateurs soient inscrits et gérés par Intune.

## Mise hors service de la précédente solution de gestion de mobilité d’entreprise

Une fois que vous avez migré tous vos utilisateurs et tous les appareils dans Intune et que vous avez validé la réussite des migrations vers Intune, vous pouvez mettre hors service la solution de gestion mobilité précédente et/ou annuler l’abonnement au service. Suivez les instructions du fournisseur de solutions pour vous assurer que vous avez supprimé correctement les exigences d’infrastructure inutiles et annulé toutes les licences/tous les abonnements.

## Ressources supplémentaires sur la migration

Avez-vous besoin d’une aide supplémentaire pour la migration vers Intune ? Nous fournissons des options d’assistance par des experts pour garantir une migration sans problème :

<!--- - [Microsoft Intune Onboarding](/em/solutions/fasttrack-center-benefit-for-enterprise-mobility-suite-ems)--->
- [Services de conseil Microsoft](https://www.microsoft.com/en-us/microsoftservices/default.aspx)
- [Support Intune technique et non-technique](/intune/troubleshoot/how-to-get-support-for-microsoft-intune)
- [Forum TechNet Microsoft Intune](https://social.technet.microsoft.com/Forums/en-US/home?forum=microsoftintuneprod)

## Obtenir une copie téléchargeable de ce guide

Pour obtenir une copie téléchargeable de ce guide dans son intégralité, accédez à la [Galerie TechNet](https://gallery.technet.microsoft.com/Migrating-to-Intune-ea439387).



<!--HONumber=Aug16_HO1-->


