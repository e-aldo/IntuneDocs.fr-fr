---
title: "Applications iOS avec les stratégies de gestion des applications mobiles | Microsoft Intune"
description: "Cette rubrique décrit ce qui se passe quand votre application iOS est gérée par les stratégies de gestion des applications mobiles."
keywords: 
author: NathBarn
ms.author: nathbarn
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
ms.sourcegitcommit: 87e37cd8334ddb9331c0662b691545cd0ab0553a
ms.openlocfilehash: 3aa6728036ff66ea489176063af2d136bef4c7cc


---

# <a name="what-to-expect-when-your-ios-app-is-managed-by-mam-policies"></a>Ce qui se passe quand votre application iOS est gérée par des stratégies GAM
 Cette rubrique décrit l’expérience de l’utilisateur des applications avec des stratégies GAM (gestion des applications mobiles). Les stratégies GAM ne sont appliquées que quand les applications sont utilisées dans le contexte professionnel, par exemple quand l’utilisateur accède à des applications à l’aide d’un compte professionnel ou accède à des fichiers stockés à l’emplacement OneDrive Entreprise d’une société.

##  <a name="access-apps"></a>Accéder aux applications

Si l’appareil **n’est pas inscrit dans Intune**, l’utilisateur est invité à redémarrer l’application quand il l’utilise pour la première fois.  Un redémarrage est nécessaire pour que les stratégies GAM soient appliquées à l’application. La capture d’écran suivante de l’application Skype illustre cette demande de redémarrage :


![Capture d’écran de l’appareil iOS affichant l’invite du code confidentiel](../media/appmanagement/iOS_AppPINPrompt.png)

Si l’appareil est **inscrit pour la gestion dans Intune**, l’utilisateur voit un message indiquant que son application est désormais gérée :

![Capture d’écran de l’appareil iOS montrant le message qui signale que l’application est maintenant gérée par votre entreprise, avec l’invite du code confidentiel](../media/appmanagement/ios-managed-devices-pin-prompt.png)

##  <a name="use-apps-with-multi-identity-support"></a>Utiliser des applications avec prise en charge de plusieurs identités

Les stratégies GAM sont appliquées uniquement dans le contexte professionnel. Ainsi, l’application peut se comporter différemment selon qu’il s’agit d’un contexte professionnel ou personnel.

 Par exemple, l’utilisateur reçoit une invite de code confidentiel quand il accède à des données professionnelles. Pour l’**application Outlook**, l’utilisateur est invité à entrer un code confidentiel quand il lance l’application. Pour l’**application OneDrive**, l’utilisateur est invité à entrer un code confidentiel quand il entre son compte professionnel.  Pour Microsoft **Word**, **PowerPoint** et **Excel**, l’utilisateur est invité à entrer un code confidentiel quand il accède à des documents stockés à l’emplacement OneDrive Entreprise de la société.

##  <a name="manage-user-accounts-on-the-device"></a>Gérer les comptes d’utilisateur sur l’appareil

Intune prend en charge le déploiement de stratégies GAM sur un seul compte d’utilisateur par appareil.

* Il est possible que le deuxième utilisateur soit bloqué sur l’appareil, mais cela dépend de l’application utilisée. Toutefois, dans tous les cas, seul le premier utilisateur sujet aux stratégies GAM est affecté par la stratégie.
  * **Microsoft Word**, **Excel** et **PowerPoint** ne bloquent pas un deuxième compte d’utilisateur, mais celui-ci n’est pas affecté par les stratégies GAM.  

  * Pour les **applications OneDrive** et **Outlook**, vous ne pouvez utiliser qu’un seul compte professionnel. Vous ne pouvez pas ajouter plusieurs comptes professionnels pour ces applications. Toutefois, vous pouvez supprimer un utilisateur et en ajouter un autre sur l’appareil.

* Si un appareil a plusieurs comptes d’utilisateur existants avant le déploiement des stratégies, le premier compte sur lequel les stratégies GAM sont déployées est géré par les stratégies GAM Intune.


Lisez l’exemple de scénario suivant pour mieux comprendre le comportement quand il existe plusieurs comptes d’utilisateur.

L’utilisateur A travaille pour deux sociétés : **Société X** et **Société Y**. L’utilisateur A a un compte professionnel pour chaque société, et tous deux utilisent Intune pour déployer des stratégies GAM. **Société X** déploie des stratégies GAM **avant** **Société Y**. Le compte associé à **Société X** est soumis à la stratégie GAM, contrairement au compte associé à Société Y. Si vous souhaitez que le compte d’utilisateur associé à Société Y soit géré par les stratégies GAM, vous devez supprimer le compte d’utilisateur associé à Société X.

### <a name="add-a-second-account"></a>Ajouter un deuxième compte

Sur un appareil iOS, si vous essayez d’ajouter un deuxième compte professionnel, un message de blocage peut s’afficher. Les comptes s’affichent et vous pouvez choisir le compte à supprimer.

![Capture d’écran de la boîte de dialogue avec le message de blocage et les options Oui et Non](../media/AppManagement/iOS_SwitchUser.PNG)
## <a name="next-steps"></a>Étapes suivantes
[Ce qui se passe quand votre application Android est gérée par des stratégies GAM](user-experience-for-mam-enabled-android-apps-with-microsoft-intune.md)
### <a name="see-also"></a>Voir aussi
[Créer et déployer des stratégies de gestion des applications mobiles à l’aide de Microsoft Intune](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Dec16_HO2-->


