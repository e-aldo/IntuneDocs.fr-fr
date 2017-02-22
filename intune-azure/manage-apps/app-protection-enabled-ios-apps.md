---
title: "Applications avec iOS avec stratégies de protection d’application | Version préliminaire d’Intune Azure | Microsoft Docs"
description: "Version préliminaire d’Intune Azure : cette rubrique décrit ce qui se passe quand votre application iOS est gérée par les stratégies de protection d’application."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 586d9440-3813-4dec-b865-8bd319befde0
ms.reviewer: andcerat
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 89afae81076d563f4ebba289f8fa82eaea6ab234
ms.openlocfilehash: ae646cf3dd1b1469b9f87ac66ad7171d77ef6518


---

# <a name="what-to-expect-when-your-ios-app-is-managed-by-app-protection-policies"></a>Ce qui se passe quand votre application iOS est gérée par des stratégies de protection d'application
[!INCLUDE[azure_preview](../includes/azure_preview.md)]Cette rubrique décrit l’expérience de l’utilisateur des applications avec des stratégies de protection d'application. Les stratégies de protection d'application ne sont appliquées que quand les applications sont utilisées dans le contexte professionnel, par exemple dans le cadre de l’accès aux applications à l’aide de votre compte professionnel ou de l’accès aux fichiers stockés à l’emplacement OneDrive Entreprise de votre société.
##  <a name="accessing-apps"></a>Accès aux applications

Si l’appareil **n’est pas inscrit dans Intune**, l’utilisateur final est invité à redémarrer l’application quand il l’utilise pour la première fois.  Un redémarrage est nécessaire pour que les stratégies de protection d'application soient appliquées à l’application. La capture d’écran suivante illustre cela avec l’application Skype :


![capture d’écran de l’appareil iOS affichant l’invite du code confidentiel](../media/ios-pin-prompt.png)

Si l’appareil est **inscrit pour la gestion dans Intune**, l’utilisateur voit un message indiquant que son application est désormais gérée :

![capture d’écran de l’appareil iOS montrant le message Géré par votre entreprise avec l’invite du code confidentiel](../media/ios-managed-devices-pin-prompt.png)

##  <a name="using-apps-with-multi-identity-support"></a>Utilisation d’applications avec prise en charge de plusieurs identités

Les stratégies de protection d'application n’étant appliquées que dans le cadre de l’utilisation professionnelle de l’application, le comportement de celle-ci peut différer selon qu’elle est utilisée dans un contexte professionnel ou personnel.  

Pour les applications qui prennent en charge plusieurs identités, Intune n’applique les stratégies de protection d'application que quand l’utilisateur final utilise l’application dans le contexte professionnel.  Par exemple, l’utilisateur final reçoit une invite de code confidentiel quand il accède aux données professionnelles.  Pour l’**application Outlook**, l’utilisateur final est invité à entrer un code confidentiel au lancement de l’application. Pour l’**application OneDrive**, cela se produit quand l’utilisateur final tape le compte professionnel.  Pour Microsoft **Word**, **PowerPoint* et **Excel**, cela se produit quand l’utilisateur final accède à des documents stockés à l’emplacement OneDrive Entreprise de votre société.
##  <a name="managing-user-accounts-on-the-device"></a>Gestion des comptes d’utilisateur sur l’appareil

Intune prend en charge le déploiement de stratégies de protection d'application vers un seul compte d’utilisateur par appareil.

* Il est possible que le deuxième utilisateur soit bloqué sur l’appareil, mais cela dépend de l’application utilisée. Toutefois, dans tous les cas, seul le premier utilisateur sujet aux stratégies de protection d'application est affecté par la stratégie.
  * **Microsoft Word**, **Excel** et **PowerPoint** ne bloquent pas un deuxième compte d’utilisateur, mais celui-ci n’est pas affecté par les stratégies de protection d'application.  

  * Pour les **applications OneDrive et Outlook**, vous ne pouvez utiliser qu’un seul compte professionnel.  L’ajout de plusieurs comptes professionnels est bloqué sur ces applications.  Toutefois, vous pouvez supprimer un utilisateur et en ajouter un autre sur l’appareil.

* Si un appareil a plusieurs comptes d’utilisateur existants avant le déploiement des stratégies, le premier compte vers lequel les stratégies de protection d'application sont déployées est géré par les stratégies de protection d'application Intune.


Lisez l’exemple de scénario ci-dessous pour mieux comprendre le comportement quand il existe plusieurs comptes d’utilisateur.

L’utilisateur A travaille pour deux sociétés : **Société X** et **Société Y**. L’utilisateur A a un compte professionnel pour chaque société, et tous deux utilisent Intune pour déployer des stratégies de protection d'application. **Société X** déploie des stratégies de protection d'application **avant** **Société Y**. Le compte associé à **Société X** est soumis à la stratégie de protection d’application, contrairement au compte associé à Société Y. Si vous souhaitez que le compte d’utilisateur associé à Société Y soit géré par les stratégies de protection d’application, vous devez supprimer le compte d’utilisateur associé à Société X.
### <a name="adding-a-second-account"></a>Ajout d’un deuxième compte

Sur un appareil iOS, si vous essayez d’ajouter un deuxième compte professionnel, un message de blocage peut s’afficher.  Les comptes s’affichent et vous pouvez choisir le compte à supprimer.

![Capture d’écran de la boîte de dialogue avec le message de blocage et les options Oui et Non](../media/ios-switch-user.PNG)

## <a name="next-steps"></a>Étapes suivantes
[Ce qui se passe quand votre application Android est gérée par des stratégies de protection d'application](app-protection-enabled-android-apps.md)
### <a name="see-also"></a>Voir aussi
[Créer et déployer des stratégies de protection d’application à l’aide de Microsoft Intune](app-protection-policies.md)



<!--HONumber=Feb17_HO1-->


