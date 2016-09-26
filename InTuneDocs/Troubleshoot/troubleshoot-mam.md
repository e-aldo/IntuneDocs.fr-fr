---
title:
- "Résoudre les problèmes de gestion des applications mobiles | Microsoft Intune"
description: 
keywords: 
author: karaman
manager: angerobe
ms.date: 09/12/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: cd5a0a3b-0013-4be3-a233-ce6e9083149f
translationtype: Human Translation
ms.sourcegitcommit: 9cfb3694b2fae919fd0554a6e21b497cdcf19c72
ms.openlocfilehash: f33e8de82ee07bb4571a5bfaff63af72f9086376


---

# Résoudre les problèmes de gestion des applications mobiles

Si vous rencontrez des problèmes avec la gestion des applications mobiles, commencez par lire ce qui suit. Cette rubrique contient certains problèmes courants que vous pouvez rencontrer avec les solutions.


**Problème** : la stratégie de gestion des applications mobiles (GAM) sans inscription de la console Azure n’est pas appliquée à l’application Skype Entreprise sur les appareils iOS et Android.

Résolution : Skype Entreprise doit être configuré pour l’authentification moderne.  Pour configurer l’authentification moderne pour Skype, suivez les instructions fournies dans [Enable your tenant for modern authentication](http://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx) (Activer votre locataire pour l’authentification moderne).

**Problème** : les stratégies de gestion des applications mobiles (GAM) sans inscription ne sont pas appliquées aux applications Office prises en charge [https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-partners] pour aucun utilisateur.
 
Résolution : vérifiez que l’utilisateur a une licence valide pour Intune.  

**Problème** : l’administrateur informatique ne peut pas configurer de stratégies GAM dans le portail Azure.

Résolution : les rôles suivants ont accès au portail Azure :

- Administrateur général (rôle à configurer dans le [portail Office](http://portal.office.com/))
- Propriétaire (rôle à configurer dans le [portail Azure](https://portal.azure.com/))
- Collaborateur (rôle à configurer dans le [portail Azure](https://portal.azure.com/))

Pour obtenir de l’aide sur la configuration de ces rôles, consultez [Se préparer à configurer des stratégies de gestion des applications mobiles avec Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune). 

**Problème** : le rapport de l’application n’affiche pas les utilisateurs récemment ciblés par une stratégie GAM.

Résolution : si vous venez de cibler un utilisateur avec une stratégie GAM, il peut s’écouler jusqu’à 24 heures avant que cet utilisateur apparaisse dans les rapports en tant qu’utilisateur ciblé. 

**Problème** : il faut parfois jusqu’à 8 heures pour que les modifications ou mises à jour apportées à la stratégie soient appliquées.  

Résolution : l’utilisateur final peut se déconnecter de l’application et s’y reconnecter pour forcer la synchronisation avec le service.  

**Problème** : la stratégie GAM n’est pas appliquée aux appareils Apple DEP.

Résolution : vérifiez que vous utilisez l’affinité utilisateur avec Apple DEP (Device Enrollment Program). L’affinité utilisateur doit être utilisée pour chaque application qui nécessite une authentification utilisateur dans DEP.
Pour plus d’informations sur l’inscription iOS DEP, consultez [Inscrire des appareils iOS DEP d’entreprise](https://docs.microsoft.com/en-us/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune).


### Voir aussi
- [Validation de la configuration de la gestion des applications mobiles](https://docs.microsoft.com/en-us/intune/deploy-use/validate-mobile-application-management)
- [Se préparer à configurer des stratégies de gestion des applications mobiles avec Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune) 





<!--HONumber=Sep16_HO2-->


