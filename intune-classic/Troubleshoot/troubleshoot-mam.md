---
title: Résoudre les problèmes de gestion des applications mobiles
description: Cette rubrique fournit des conseils de dépannage pour les déploiements d’accès conditionnel.
keywords: ''
author: oydang
ms.author: oydang
manager: angerobe
ms.date: 12/19/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: cd5a0a3b-0013-4be3-a233-ce6e9083149f
ROBOTS: NOINDEX,NOFOLLOW
ms.custom: intune-classic
ms.openlocfilehash: ec6e663c570399f0adca02772416904d5a9dcc79
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2018
---
# <a name="troubleshoot-mobile-application-management"></a>Résoudre les problèmes de gestion des applications mobiles

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Si vous rencontrez des problèmes avec la gestion des applications mobiles Intune, commencez par lire ce qui suit. Cette rubrique aborde certains problèmes et questions courants que vous pouvez avoir, et fournit des solutions et des réponses.

Si ces informations ne vous permettent pas de remédier à votre problème, consultez [Comment obtenir un support technique pour Microsoft Intune](how-to-get-support-for-microsoft-intune.md) pour accéder à d’autres types d’assistance.


## <a name="common-it-administrator-issues"></a>Problèmes courants pour l’administrateur informatique

Il s’agit de problèmes courants qu’un administrateur informatique peut rencontrer lors de l’utilisation de la stratégie de protection des applications Intune.

| Problème | Description | Solution |
| -- | -- | -- |
| La stratégie n’est pas appliquée à Skype Entreprise | La stratégie de protection des applications sans inscription d’appareil, effectuée dans le portail Azure, ne s’applique pas à l’application Skype Entreprise sur les appareils iOS et Android. | Skype Entreprise doit être configuré pour l’authentification moderne.  Pour configurer l’authentification moderne pour Skype, suivez les instructions fournies dans [Enable your tenant for modern authentication](http://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx) (Activer votre locataire pour l’authentification moderne). |
| La stratégie d’application Office n’est pas appliquée | Les stratégies de protection des applications ne s’appliquent à aucune [application Office prise en charge](https://www.microsoft.com/cloud-platform/microsoft-intune-partners), quel que soit l’utilisateur. | Vérifiez que l’utilisateur a une licence pour Intune et que les applications Office sont ciblées par une stratégie de protection des applications déployée. L’application d’une stratégie de protection des applications récemment déployée peut prendre jusqu’à huit heures. |
| L’administrateur ne peut pas configurer la stratégie de protection des applications dans le portail Azure | L’administrateur informatique ne peut pas configurer de stratégies de protection des applications dans le portail Azure. | Les rôles d’utilisateur suivants ont accès au portail Azure : <ul><li>Administrateur général (rôle à configurer dans le [portail Office](http://portal.office.com/))</li><li>Propriétaire (rôle à configurer dans le [portail Azure](https://portal.azure.com/))</li><li>Collaborateur (rôle à configurer dans le [portail Azure](https://portal.azure.com/))</li></ul>  Pour obtenir de l’aide sur la configuration de ces rôles, consultez [Se préparer à configurer des stratégies de gestion des applications mobiles avec Microsoft Intune](../deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md).|
|Les comptes d’utilisateur manquent dans les rapports de stratégie de protection des applications | Les rapports de la console d’administration ne montrent pas les comptes d’utilisateur sur lesquels la stratégie de protection des applications a été récemment déployée. | Si vous venez de cibler un utilisateur avec une stratégie de protection des applications, il peut s’écouler jusqu’à 24 heures avant que cet utilisateur apparaisse dans les rapports en tant qu’utilisateur ciblé. |
| Les modifications de stratégie ne sont pas mises en œuvre | Il peut s’écouler jusqu’à 8 heures pour que des modifications et des mises à jour d’une stratégie de protection des applications prennent effet. | Le cas échéant l’utilisateur final peut se déconnecter de l’application et s’y reconnecter pour forcer la synchronisation avec le service. |
| La stratégie de protection des applications ne fonctionne ne pas avec DEP | La stratégie de protection des applications ne s’applique pas aux appareils Apple DEP. | Vérifiez que vous utilisez l’Affinité utilisateur avec Apple DEP (Device Enrollment Program). L’affinité utilisateur doit être utilisée pour chaque application qui nécessite une authentification utilisateur dans DEP. <br><br>Pour plus d’informations sur l’inscription iOS DEP, consultez [Inscrire des appareils iOS DEP d’entreprise](../deploy-use/ios-device-enrollment-program-in-microsoft-intune.md).|
| La stratégie de transfert de données ne fonctionne ne pas avec iOS | Les stratégies **Autoriser l'application à transférer des données vers d'autres applications** et **Autoriser l'application à recevoir des données d'autres applications** ne gèrent pas correctement le transfert de données dans iOS. | Voir [Gérer les transferts de données entre applications iOS avec Microsoft Intune](/deploy-use/manage-data-transfer-between-ios-apps-with-microsoft-intune.md). |






## <a name="common-end-user-issues"></a>Problèmes courants pour l’utilisateur final

Les problèmes courants pour l’utilisateur final sont répertoriés selon les catégories suivantes :

* **Scénarios d’utilisation normale** : un utilisateur final peut rencontrer ces scénarios sur des applications comprenant une stratégie de protection d’applications Intune. Il ne s’agit pas de problèmes réels, mais peuvent être perçus comme des bogues ou des erreurs.

* **Boîtes de dialogue d’utilisation normale** : il s’agit de boîtes de dialogue d’utilisation normale qu’un utilisateur final peut voir dans des applications comprenant une stratégie de protection des applications Intune. Ces messages et boîtes de dialogue n’indiquent **pas** d’erreur ou de bogue.

* **Messages d’erreur et boîtes de dialogue** : il s’agit de messages d’erreur et boîtes de dialogue qu’un utilisateur final peut voir dans des applications comprenant une stratégie de protection des applications Intune. Cela indique souvent une erreur effectuée par l’administrateur informatique ou un bogue dans la protection des applications Intune.



### <a name="normal-usage-scenarios"></a>Scénarios d’utilisation normale

Plate-forme | Scénario | Explication |
---| --- | --- |
iOS | L’utilisateur final peut utiliser l’extension de partage iOS pour ouvrir les données professionnelles ou scolaires dans des applications non gérées, même si la stratégie de transfert de données est définie sur les **applications gérées uniquement** ou sur **Aucune application.** Cela ne provoque-t-il pas de fuite de données ? | La stratégie de protection des applications Intune ne peut pas contrôler l’extension de partage iOS sans gérer l’appareil. Par conséquent, **Intune chiffre les données « d’entreprise » avant de les partager à l’extérieur de l’application**. Vous pouvez valider cette action en essayant d’ouvrir le fichier « d’entreprise » en dehors de l’application gérée. Le fichier doit être chiffré et ne peut pas être ouvert en dehors de l’application gérée.
Android | Pourquoi l’utilisateur final **doit-il installer l’application de portail d’entreprise**, même si j’utilise la protection d’application GAM sans inscription de l’appareil ?  | Sur Android, la plupart des fonctionnalités de protection des applications sont intégrées à l’application Portail d’entreprise. **L’inscription d’appareil n’est pas obligatoire, même si l’application Portail d’entreprise est toujours nécessaire**. Pour la protection des applications sans inscription, l’utilisateur final doit simplement disposer de l’application Portail d’entreprise installée sur l’appareil.

### <a name="normal-usage-dialogs"></a>Boîtes de dialogue d’utilisation normale

Plate-forme | Message ou boîte de dialogue | Explication |
--- | --- | --- |
iOS, Android | **Connexion** : pour protéger ses données, votre organisation doit gérer cette application. Pour compléter cette action, connectez-vous avec votre compte professionnel ou scolaire. | L’utilisateur final doit se connecter avec son compte professionnel ou scolaire pour utiliser cette application, ce qui nécessite une stratégie de protection des applications. Pour appliquer la stratégie, l’utilisateur doit s’authentifier dans Azure Active Directory.
iOS, Android |**Redémarrage nécessaire** : votre organisation protège désormais ses données dans cette application. Vous devez redémarrer l’application pour continuer. | L’application vient de recevoir la stratégie de protection des applications Intune et doit redémarrer pour l’appliquer.
iOS, Android |**Action non autorisée** : votre organisation vous autorise uniquement à ouvrir des données professionnelles ou scolaires dans cette application. | L’administrateur a défini le paramètre **Autoriser l'application à recevoir des données d'autres applications** à sur **les applications gérées uniquement**. Par conséquent, l’utilisateur final ne peut transférer des données dans cette application qu’à partir d’autres applications qui disposent d’une stratégie de protection des applications.
iOS, Android |**Action non autorisée** : votre organisation vous autorise uniquement à transférer ses données à d'autres applications gérées. | L’administrateur a défini le paramètre **Autoriser l'application à transférer des données vers d'autres applications** à sur **les applications gérées uniquement**. Par conséquent, l’utilisateur final peut transférer des données que depuis cette application vers d’autres applications qui disposent d’une stratégie de protection des applications.
iOS, Android |**Alerte de réinitialisation** : votre organisation a supprimé ses données associées à cette application. Pour continuer, redémarrez l'application. | L’administrateur informatique a lancé une réinitialisation de l’application à l’aide de la protection des applications Intune.
Android | **Portail d’entreprise nécessaire** : pour utiliser votre compte professionnel ou scolaire avec cette application, vous devez installer l'application Portail d'entreprise Intune. Appuyez sur « Accéder au Store » pour continuer. | Sur Android, la plupart des fonctionnalités de protection des applications sont intégrées à l’application Portail d’entreprise. **L’inscription d’appareil n’est pas obligatoire, même si l’application Portail d’entreprise est toujours nécessaire**. Pour la protection des applications sans inscription, l’utilisateur final doit simplement disposer de l’application Portail d’entreprise installée sur l’appareil.


### <a name="error-messages-and-dialogs-on-ios"></a>Messages d’erreur et boîtes de dialogue dans iOS


Message d’erreur ou boîte de dialogue | Cause | Mise à jour |
-- | --- | --- |
**Application non configurée** : cette application n’a pas été configurée pour que vous puissiez l’utiliser. Contactez votre administrateur informatique pour obtenir de l’aide. | Échec de détection de la stratégie de protection des applications obligatoire pour l’application. |Vérifiez qu’une stratégie de protection des applications iOS est déployée pour le groupe de sécurité de l’utilisateur et qu’elle cible cette application.
**Bienvenue dans Intune Managed Browser** : cette application fonctionne mieux quand elle est gérée par Microsoft Intune. Vous pouvez toujours l’utiliser pour parcourir le web et, quand elle est gérée par Microsoft Intune, vous avez accès à des fonctionnalités de protection de données supplémentaires. | Échec de détection de la stratégie de protection des applications obligatoire pour l’application Intune Managed Browser. <br><br>L’utilisateur peut toujours utiliser l’application pour parcourir le web, mais l’application n’est pas gérée par Intune. | Vérifiez qu’une stratégie de protection des applications iOS est déployée pour le groupe de sécurité de l’utilisateur et qu’elle cible Intune Managed Browser.
**Échec de connexion** : nous ne pouvons pas vous connecter maintenant. Veuillez réessayer plus tard. | L’utilisateur n’a pas réussi à s’inscrire auprès du service GAM après avoir tenté de se connecter avec son compte professionnel ou scolaire. | Vérifiez qu’une stratégie de protection des applications iOS est déployée pour le groupe de sécurité de l’utilisateur et qu’elle cible cette application.
**Compte non configuré** : votre organisation n’a pas configuré votre compte pour accéder aux données professionnelles ou scolaires. Contactez votre administrateur informatique pour obtenir de l’aide. | Le compte d’utilisateur n’a pas de licence Intune A Direct. | Vérifiez qu’une licence Intune est affectée au compte d’utilisateur dans le [portail Office](http://portal.office.com).
**Appareil non conforme** : impossible d’utiliser cette application car vous utilisez un appareil jailbreaké. Contactez votre administrateur informatique pour obtenir de l’aide. | Intune a détecté que l’utilisateur utilisait un appareil jailbreaké. | Rétablissez les paramètres d’usine de l’appareil. Suivez [ces instructions](https://support.apple.com/HT201274) sur le site de support technique d’Apple.
**Connexion Internet obligatoire** : vous devez être connecté à Internet pour vérifier que vous pouvez utiliser cette application. | Cet appareil n’est pas connecté à Internet. | Connectez l’appareil à un réseau Wi-Fi ou un réseau de données.
**Erreur inconnue** : essayez de redémarrer cette application. Si le problème persiste, contactez votre administrateur informatique pour obtenir de l’aide. | Une erreur inconnue s’est produite. | Attendez un moment, puis réessayez. Si l’erreur persiste, créez un ticket de support avec Intune [ici](how-to-get-support-for-microsoft-intune.md).
**Accès aux données de votre organisation** : le compte professionnel ou scolaire que vous avez spécifié n’a pas accès à cette application. Vous devrez peut-être vous connecter avec un compte différent. Contactez votre administrateur informatique pour obtenir de l’aide. | Intune a détecté que l’utilisateur avait tenté de se connecter avec un deuxième compte professionnel ou scolaire différent du compte inscrit auprès du service GAM pour l’appareil. Un seul compte professionnel ou scolaire peut être géré par GAM sur un même appareil. | Demandez à l’utilisateur de se connecter avec le compte dont le nom d’utilisateur est prérenseigné dans l’écran de connexion, <br> <br> ou demandez-lui de se connecter avec le nouveau compte professionnel ou scolaire et supprimez le compte GAM existant.
**Problème de connexion** : Un problème de connexion inattendu s’est produit. Vérifiez votre connexion et réessayez.  |  Erreur inattendue. | Attendez un moment, puis réessayez. Si l’erreur persiste, créez un ticket de support avec Intune [ici](how-to-get-support-for-microsoft-intune.md).
**Alerte** : Cette application ne peut plus être utilisée. Pour plus d'informations, contactez votre administrateur informatique. | Impossible de valider le certificat de l’application. | Vérifiez que la version de l’application est à jour. <br><br> Réinstallez l’agent.
**Erreur** : Cette application a rencontré un problème et doit être fermée. Si l’erreur persiste, contactez votre département informatique. | Impossible de lire le code confidentiel de l’application GAM dans le trousseau Apple iOS. | Redémarrez l’appareil. Vérifiez que la version de l’application est à jour. <br><br> Réinstallez l’agent.


### <a name="error-messages-and-dialogs-on-android"></a>Messages d’erreur et boîtes de dialogue dans Android

Boîte de dialogue/message d’erreur | Cause | Mise à jour |
-- | --- | --- |
**Application non configurée** : Cette application n’a pas été configurée pour votre usage. Contactez votre administrateur informatique pour obtenir de l’aide. | Échec de détection de la stratégie de protection des applications obligatoire pour l’application. |Vérifiez qu’une stratégie de protection des applications Android est déployée pour le groupe de sécurité de l’utilisateur et qu’elle cible cette application.
**Échec de lancement de l’application** : Un problème s’est produit lors du lancement de votre application. Essayez de mettre à jour l’application ou l’application Portail d’entreprise Intune. Si vous avez besoin d’aide, contactez votre administrateur informatique. | Intune a détecté une stratégie de protection des applications valide pour l’application, mais l’application se bloque lors de l’initialisation de la stratégie GAM. | Vérifiez que la version de l’application est à jour. <br><br> Vérifiez que l’application Portail d’entreprise Intune est installée et à jour sur l’appareil. <br><br> Si l’erreur persiste, utilisez l’application Portail d’entreprise pour envoyer des journaux à Intune ou créez un ticket de support [ici](how-to-get-support-for-microsoft-intune.md).
**Aucune application trouvée** : Cet appareil ne contient aucune application autorisée par votre organisation pour ouvrir ce contenu. Contactez votre administrateur informatique pour obtenir de l’aide. | L’utilisateur a essayé d’ouvrir des données professionnelles ou scolaires avec une autre application, mais Intune ne trouve pas d’autre application gérée autorisée à ouvrir les données. | Vérifiez qu’une stratégie de protection des applications Android est déployée sur le groupe de sécurité de l’utilisateur et qu’elle cible au moins une autre application GAM capable d’ouvrir les données en question.
**Échec de connexion** : Réessayez de vous connecter. Si le problème persiste, contactez votre administrateur informatique pour obtenir de l’aide. | Échec d’authentification du compte avec lequel l’utilisateur a tenté de se connecter. | Vérifiez que l’utilisateur se connecte avec le compte professionnel ou scolaire qui est déjà inscrit auprès du service GAM Intune (le premier compte professionnel ou scolaire qui s’est connecté à cette application). <br><br> Effacez les données de l’application. <br><br> Vérifiez que la version de l’application est à jour. <br><br> Vérifiez que la version du Portail d’entreprise est à jour.
**Connexion Internet obligatoire** : Vous devez être connecté à Internet pour vérifier que vous pouvez utiliser cette application. | Cet appareil n’est pas connecté à Internet. | Connectez l’appareil à un réseau Wi-Fi ou un réseau de données.
**Appareil non conforme** : Impossible d’utiliser cette application, car vous utilisez un appareil rooté. Contactez votre administrateur informatique pour obtenir de l’aide. | Intune a détecté que l’utilisateur utilisait un appareil « rooté ». | Rétablissez les paramètres d’usine de l’appareil.
**Compte non configuré** : Cette application doit être gérée par Microsoft Intune, mais votre compte n’a pas été configuré. Contactez votre administrateur informatique pour obtenir de l’aide. | Le compte d’utilisateur n’a pas de licence Intune A Direct. | Vérifiez qu’une licence Intune est affectée au compte d’utilisateur dans le [portail Office](http://portal.office.com).
**Impossible d’inscrire l’application** : Cette application doit être gérée par Microsoft Intune, mais nous n’arrivons pas à l’y inscrire. Contactez votre administrateur informatique pour obtenir de l’aide. | Impossible d’inscrire automatiquement l’application auprès du service GAM quand la stratégie de protection des applications est obligatoire. | Effacez les données de l’application. <br><br> Envoyez des journaux à Intune par le biais de l’application Portail d’entreprise ou créez un ticket de support [ici](how-to-get-support-for-microsoft-intune.md).




### <a name="see-also"></a>Voir aussi
- [Validation de la configuration de la gestion des applications mobiles](../deploy-use/validate-mobile-application-management.md)
- [Se préparer à configurer des stratégies de gestion des applications mobiles avec Microsoft Intune](../deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md)
- [Comment obtenir un support technique pour Microsoft Intune](how-to-get-support-for-microsoft-intune.md)
