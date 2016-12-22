---
title: "Résoudre les problèmes de gestion des applications mobiles | Documentation Microsoft"
description: "Cette rubrique fournit des conseils de dépannage pour les déploiements d’accès conditionnel."
keywords: 
author: NathBarn
ms.author: oldang
manager: angerobe
ms.date: 09/12/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: cd5a0a3b-0013-4be3-a233-ce6e9083149f
translationtype: Human Translation
ms.sourcegitcommit: d50a5751a5afd987196336e9443dc5a429a283fd
ms.openlocfilehash: b333c0f5097fec38bf0dd78726a028fd7aaccd2f


---

# <a name="troubleshoot-mobile-application-management"></a>Résoudre les problèmes de gestion des applications mobiles

Si vous rencontrez des problèmes avec la gestion des applications mobiles Intune, commencez par lire ce qui suit. Cette rubrique aborde certains problèmes et questions courants que vous pouvez avoir, et fournit des solutions et des réponses.

## <a name="common-it-administrator-issues"></a>Problèmes courants pour l’administrateur informatique

1. **Problème :** la stratégie de protection des applications sans inscription d’appareil, effectuée dans le portail Azure, ne s’applique pas à l’application Skype Entreprise sur les appareils iOS et Android.

  **Résolution** : Skype Entreprise doit être configuré pour l’authentification moderne.  Pour configurer l’authentification moderne pour Skype, suivez les instructions fournies dans [Enable your tenant for modern authentication](http://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx) (Activer votre locataire pour l’authentification moderne).

2. **Problème :** les stratégies de protection des applications ne s’appliquent à aucune [application Office prise en charge](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-partners), quel que soit l’utilisateur.

  **Résolution** : vérifiez que l’utilisateur a une licence pour Intune et que les applications Office sont ciblées par une stratégie de protection des applications déployée. L’application d’une stratégie de protection des applications récemment déployée peut prendre jusqu’à huit heures.

3. **Problème** : l’administrateur informatique ne peut pas configurer de stratégies de protection des applications dans le portail Azure.

  **Résolution** :

  Les rôles d’utilisateur suivants ont accès au portail Azure :

  - Administrateur général (rôle à configurer dans le [portail Office](http://portal.office.com/))
  - Propriétaire (rôle à configurer dans le [portail Azure](https://portal.azure.com/))
  - Collaborateur (rôle à configurer dans le [portail Azure](https://portal.azure.com/))<br>

  Pour obtenir de l’aide sur la configuration de ces rôles, consultez [Se préparer à configurer des stratégies de gestion des applications mobiles avec Microsoft Intune](../deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md).

4. **Problème :** les rapports de la console d’administration ne montrent pas les comptes d’utilisateur sur lesquels la stratégie de protection des applications a été récemment déployée.

  **Résolution** : si vous venez de cibler un utilisateur avec une stratégie de protection des applications, il peut s’écouler jusqu’à 24 heures avant que cet utilisateur apparaisse dans les rapports en tant qu’utilisateur ciblé.

5. **Problème** : il faut parfois jusqu’à 8 heures pour que les modifications ou mises à jour apportées à la stratégie soient appliquées.  

  **Résolution** : l’utilisateur final peut se déconnecter de l’application et s’y reconnecter pour forcer la synchronisation avec le service.  

6. **Problème :** la stratégie de protection des applications ne s’applique aux appareils Apple DEP.

  **Résolution** : vérifiez que vous utilisez l’affinité utilisateur avec Apple DEP (Device Enrollment Program). L’affinité utilisateur doit être utilisée pour chaque application qui nécessite une authentification utilisateur dans DEP.
Pour plus d’informations sur l’inscription iOS DEP, consultez [Inscrire des appareils iOS DEP d’entreprise](../deploy-use/ios-device-enrollment-program-in-microsoft-intune.md).

## <a name="common-end-user-issues"></a>Problèmes courants pour l’utilisateur final

### <a name="issues-on-ios"></a>Problèmes sur iOS

Boîte de dialogue/message d’erreur | Cause | Mise à jour |
-- | --- | --- |
**Application non configurée** : cette application n’a pas été configurée pour que vous puissiez l’utiliser. Contactez votre administrateur informatique pour obtenir de l’aide. | Échec de détection de la stratégie de protection des applications obligatoire pour l’application. |Vérifiez qu’une stratégie de protection des applications iOS est déployée pour le groupe de sécurité de l’utilisateur et qu’elle cible cette application.
**Bienvenue dans Intune Managed Browser** : cette application fonctionne mieux quand elle est gérée par Microsoft Intune. Vous pouvez toujours l’utiliser pour parcourir le web et, quand elle est gérée par Microsoft Intune, vous avez accès à des fonctionnalités de protection de données supplémentaires. | Échec de détection de la stratégie de protection des applications obligatoire pour l’application Intune Managed Browser. <br><br>L’utilisateur peut toujours utiliser l’application pour parcourir le web, mais l’application n’est pas gérée par Intune. | Vérifiez qu’une stratégie de protection des applications iOS est déployée pour le groupe de sécurité de l’utilisateur et qu’elle cible Intune Managed Browser.
**Échec de connexion** : nous ne pouvons pas vous connecter maintenant. Veuillez réessayer plus tard. | L’utilisateur n’a pas réussi à s’inscrire auprès du service GAM après avoir tenté de se connecter avec son compte professionnel ou scolaire. | Vérifiez qu’une stratégie de protection des applications iOS est déployée pour le groupe de sécurité de l’utilisateur et qu’elle cible cette application.
**Compte non configuré** : votre organisation n’a pas configuré votre compte pour accéder aux données professionnelles ou scolaires. Contactez votre administrateur informatique pour obtenir de l’aide. | Le compte d’utilisateur n’a pas de licence Intune A Direct. | Vérifiez qu’une licence Intune est affectée au compte d’utilisateur dans le [portail Office](http://portal.office.com).
**Appareil non conforme** : impossible d’utiliser cette application car vous utilisez un appareil jailbreaké. Contactez votre administrateur informatique pour obtenir de l’aide. | Intune a détecté que l’utilisateur utilisait un appareil jailbreaké. | Rétablissez les paramètres d’usine de l’appareil. Suivez [ces instructions](https://support.apple.com/en-us/HT201274) sur le site de support technique d’Apple.
**Connexion Internet obligatoire** : vous devez être connecté à Internet pour vérifier que vous pouvez utiliser cette application. | Cet appareil n’est pas connecté à Internet. | Connectez l’appareil à un réseau Wi-Fi ou un réseau de données.
**Erreur inconnue** : essayez de redémarrer cette application. Si le problème persiste, contactez votre administrateur informatique pour obtenir de l’aide. | Une erreur inconnue s’est produite. | Attendez un moment, puis réessayez. Si l’erreur persiste, créez un ticket de support avec Intune [ici](/how-to-get-support-for-microsoft-intune.md).
**Accès aux données de votre organisation** : le compte professionnel ou scolaire que vous avez spécifié n’a pas accès à cette application. Vous devrez peut-être vous connecter avec un compte différent. Contactez votre administrateur informatique pour obtenir de l’aide. | Intune a détecté que l’utilisateur avait tenté de se connecter avec un deuxième compte professionnel ou scolaire différent du compte inscrit auprès du service GAM pour l’appareil. Un seul compte professionnel ou scolaire peut être géré par GAM sur un même appareil. | Demandez à l’utilisateur de se connecter avec le compte dont le nom d’utilisateur est prérenseigné dans l’écran de connexion, <br> <br> ou demandez-lui de se connecter avec le nouveau compte professionnel ou scolaire et supprimez le compte GAM existant.
**Problème de connexion** : Un problème de connexion inattendu s’est produit. Vérifiez votre connexion et réessayez.  |  Erreur inattendue. | Attendez un moment, puis réessayez. Si l’erreur persiste, créez un ticket de support avec Intune [ici](/how-to-get-support-for-microsoft-intune.md).
**Alerte** : Cette application ne peut plus être utilisée. Pour plus d'informations, contactez votre administrateur informatique. | Impossible de valider le certificat de l’application. | Vérifiez que la version de l’application est à jour. <br><br> Réinstallez l’agent.
**Erreur** : Cette application a rencontré un problème et doit être fermée. Si l’erreur persiste, contactez votre département informatique. | Impossible de lire le code confidentiel de l’application GAM dans le trousseau Apple iOS. | Redémarrez l’appareil. Vérifiez que la version de l’application est à jour. <br><br> Réinstallez l’agent.


### <a name="issues-on-android"></a>Problèmes sur Android

Boîte de dialogue/message d’erreur | Cause | Mise à jour |
-- | --- | --- |
**Application non configurée** : Cette application n’a pas été configurée pour votre usage. Contactez votre administrateur informatique pour obtenir de l’aide. | Échec de détection de la stratégie de protection des applications obligatoire pour l’application. |Vérifiez qu’une stratégie de protection des applications iOS est déployée pour le groupe de sécurité de l’utilisateur et qu’elle cible cette application.
**Échec de lancement de l’application** : Un problème s’est produit lors du lancement de votre application. Essayez de mettre à jour l’application ou l’application Portail d’entreprise Intune. Si vous avez besoin d’aide, contactez votre administrateur informatique. | Intune a détecté une stratégie de protection des applications valide pour l’application, mais l’application se bloque lors de l’initialisation de la stratégie GAM. | Vérifiez que la version de l’application est à jour. <br><br> Vérifiez que l’application Portail d’entreprise Intune est installée et à jour sur l’appareil. <br><br> Si l’erreur persiste, utilisez l’application Portail d’entreprise pour envoyer des journaux à Intune ou créez un ticket de support [ici](/how-to-get-support-for-microsoft-intune.md).
**Aucune application trouvée** : Cet appareil ne contient aucune application autorisée par votre organisation pour ouvrir ce contenu. Contactez votre administrateur informatique pour obtenir de l’aide. | L’utilisateur a essayé d’ouvrir des données professionnelles ou scolaires avec une autre application, mais Intune ne trouve pas d’autre application gérée autorisée à ouvrir les données. | Vérifiez qu’une stratégie de protection des applications Android est déployée sur le groupe de sécurité de l’utilisateur et qu’elle cible au moins une autre application GAM capable d’ouvrir les données en question.
**Échec de connexion** : Réessayez de vous connecter. Si le problème persiste, contactez votre administrateur informatique pour obtenir de l’aide. | Échec d’authentification du compte avec lequel l’utilisateur a tenté de se connecter. | Vérifiez que l’utilisateur se connecte avec le compte professionnel ou scolaire qui est déjà inscrit auprès du service GAM Intune (le premier compte professionnel ou scolaire qui s’est connecté à cette application). <br><br> Effacez les données de l’application. <br><br> Vérifiez que la version de l’application est à jour. <br><br> Vérifiez que la version du Portail d’entreprise est à jour.
**Connexion Internet obligatoire** : Vous devez être connecté à Internet pour vérifier que vous pouvez utiliser cette application. | Cet appareil n’est pas connecté à Internet. | Connectez l’appareil à un réseau Wi-Fi ou un réseau de données.
**Appareil non conforme** : Impossible d’utiliser cette application, car vous utilisez un appareil « rooté ». Contactez votre administrateur informatique pour obtenir de l’aide. | Intune a détecté que l’utilisateur utilisait un appareil « rooté ». | Rétablissez les paramètres d’usine de l’appareil.
**Compte non configuré** : Cette application doit être gérée par Microsoft Intune, mais votre compte n’a pas été configuré. Contactez votre administrateur informatique pour obtenir de l’aide. | Le compte d’utilisateur n’a pas de licence Intune A Direct. | Vérifiez qu’une licence Intune est affectée au compte d’utilisateur dans le [portail Office](http://portal.office.com).
**Impossible d’inscrire l’application** : Cette application doit être gérée par Microsoft Intune, mais nous n’arrivons pas à l’y inscrire. Contactez votre administrateur informatique pour obtenir de l’aide. | Impossible d’inscrire automatiquement l’application auprès du service GAM quand la stratégie de protection des applications est obligatoire. | Effacez les données de l’application. <br><br> Envoyez des journaux à Intune par le biais de l’application Portail d’entreprise ou créez un ticket de support [ici](/how-to-get-support-for-microsoft-intune.md).





### <a name="see-also"></a>Voir aussi
- [Validation de la configuration de la gestion des applications mobiles](../deploy-use/validate-mobile-application-management.md)
- [Se préparer à configurer des stratégies de gestion des applications mobiles avec Microsoft Intune](../deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Dec16_HO2-->


