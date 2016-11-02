---
title: "Applications iOS avec les stratégies de gestion des applications mobiles | Microsoft Intune"
description: "Cette rubrique décrit ce qui se passe quand votre application iOS est gérée par les stratégies de gestion des applications mobiles."
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 10/18/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b57e6525-b57c-4cb4-a84c-9f70ba1e8e19
ms.reviewer: andcerat
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 389daf0ed39fa2cd4b2e5d6e52cbd6809a568c9e
ms.openlocfilehash: 3f9d9c7cafcdac0db21e5ba35f713fe630c65b99


---

# Ce qui se passe quand votre application iOS est gérée par des stratégies GAM
 Cette rubrique décrit l’expérience de l’utilisateur des applications avec des stratégies GAM. Les stratégies de gestion des applications mobiles (GAM) ne sont appliquées que quand les applications sont utilisées dans le contexte professionnel, par exemple dans le cadre de l’accès aux applications à l’aide de votre compte professionnel ou de l’accès aux fichiers stockés à l’emplacement OneDrive Entreprise de votre société.
##  Accès aux applications

Si l’appareil **n’est pas inscrit dans Intune**, l’utilisateur final est invité à redémarrer l’application quand il l’utilise pour la première fois.  Un redémarrage est nécessaire pour que les stratégies GAM soient appliquées à l’application. La capture d’écran suivante illustre cela avec l’application Skype :


![capture d’écran de l’appareil iOS affichant l’invite du code confidentiel](../media/appmanagement/iOS_AppPINPrompt.png)

Si l’appareil est **inscrit pour la gestion dans Intune**, l’utilisateur voit un message indiquant que son application est désormais gérée :

![capture d’écran de l’appareil iOS montrant le message Géré par votre entreprise avec l’invite du code confidentiel](../media/appmanagement/ios-managed-devices-pin-prompt.png)

##  Utilisation d’applications avec prise en charge de plusieurs identités

Les stratégies GAM n’étant appliquées que dans le cadre de l’utilisation professionnelle de l’application, le comportement de celle-ci peut différer selon qu’elle est utilisée dans un contexte professionnel ou personnel.  

Pour les applications qui prennent en charge plusieurs identités, Intune n’applique les stratégies GAM que quand l’utilisateur final utilise l’application dans le contexte professionnel.  Par exemple, l’utilisateur final reçoit une invite de code confidentiel quand il accède aux données professionnelles.  Pour l’**application Outlook**, l’utilisateur final est invité à entrer un code confidentiel au lancement de l’application. Pour l’**application OneDrive**, cela se produit quand l’utilisateur final tape le compte professionnel.  Pour Microsoft **Word**, **PowerPoint* et **Excel**, cela se produit quand l’utilisateur final accède à des documents stockés à l’emplacement OneDrive Entreprise de votre société.
##  Gestion des comptes d’utilisateur sur l’appareil

Intune prend en charge le déploiement de stratégies GAM vers un seul compte d’utilisateur par appareil.

* Il est possible que le deuxième utilisateur soit bloqué sur l’appareil, mais cela dépend de l’application utilisée. Toutefois, dans tous les cas, seul le premier utilisateur sujet aux stratégies GAM est affecté par la stratégie.
  * **Microsoft Word**, **Excel** et **PowerPoint** ne bloquent pas un deuxième compte d’utilisateur, mais celui-ci n’est pas affecté par les stratégies GAM.  

  * Pour les **applications OneDrive et Outlook**, vous ne pouvez utiliser qu’un seul compte professionnel.  L’ajout de plusieurs comptes professionnels est bloqué sur ces applications.  Toutefois, vous pouvez supprimer un utilisateur et en ajouter un autre sur l’appareil.

* Si un appareil a plusieurs comptes d’utilisateur existants avant le déploiement des stratégies, le premier compte vers lequel les stratégies GAM sont déployées est géré par les stratégies GAM Intune.


Lisez l’exemple de scénario ci-dessous pour mieux comprendre le comportement quand il existe plusieurs comptes d’utilisateur.

L’utilisateur A travaille pour deux sociétés : **Société X** et **Société Y**. L’utilisateur A a un compte professionnel pour chaque société, et tous deux utilisent Intune pour déployer des stratégies GAM. **Société X** déploie des stratégies GAM **avant** **Société Y**. Le compte associé à **Société X** est soumis à la stratégie GAM, contrairement au compte associé à Société Y. Si vous souhaitez que le compte d’utilisateur associé à Société Y soit géré par les stratégies GAM, vous devez supprimer le compte d’utilisateur associé à Société X.
### Ajout d’un deuxième compte

Sur un appareil iOS, si vous essayez d’ajouter un deuxième compte professionnel, un message de blocage peut s’afficher.  Les comptes s’affichent et vous pouvez choisir le compte à supprimer.

![Capture d’écran de la boîte de dialogue avec le message de blocage et les options Oui et Non](../media/AppManagement/iOS_SwitchUser.PNG)
## Étapes suivantes
[Ce qui se passe quand votre application Android est gérée par des stratégies GAM](user-experience-for-mam-enabled-android-apps-with-microsoft-intune.md)
### Voir aussi
[Créer et déployer des stratégies de gestion des applications mobiles à l’aide de Microsoft Intune](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Oct16_HO3-->


