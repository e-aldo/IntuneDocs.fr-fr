---
title: "Configurer votre abonnement à Lookout MTP | Microsoft Intune"
description: "Cette rubrique décrit comment configurer Lookout MTP."
keywords: 
author: karthikaraman
manager: angrobe
ms.date: 09/13/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 8477a2f1-2e1d-4d42-8bcb-e1181cc900bb
ms.reviewer: sandera
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ba2196ff03975df1f8969e1522f7af459343694d
ms.openlocfilehash: 530a34c7c75a4fa73cbb62873e2d28883b91b57e


---

# Configurer votre abonnement pour la protection contre les menaces mobiles de Lookout
Pour préparer votre abonnement au service Lookout MTP, le support technique de Lookout (enterprisesupport@lookout.com) a besoin des informations suivantes relatives à votre abonnement Azure Active Directory (Azure AD). 

* **ID de locataire Azure AD**
* **ID d’objet de groupe Azure AD** pour l’accès **complet** à la console Lookout MTP
* **ID d’objet de groupe Azure AD** pour l’accès **restreint** à la console Lookout MTP (facultatif)

Consultez la section suivante pour savoir comment collecter les informations demandées par l’équipe du support technique Lookout.  

## Obtenir vos informations Azure AD
### ID de locataire Azure AD
Connecte-vous au [portail de gestion Azure AD](https://manage.windowsazure.com) et sélectionnez votre abonnement. 

![capture d’écran de la page Azure AD montrant le nom du locataire](../media/mtp/aad_tenant_name.png) Quand vous choisissez le nom de votre abonnement, l’URL affichée inclut l’ID d’abonnement.  Si vous ne trouvez pas votre ID d’abonnement, consultez cet [article du support technique Microsoft](https://support.office.com/en-us/article/Find-your-Office-365-tenant-ID-6891b561-a52d-4ade-9f39-b492285e2c9b?ui=en-US&rs=en-US&ad=US) qui fournit des conseils à cette fin.   
### Obtention de votre ID de groupe Azure AD
La console Lookout MTP offre deux niveaux d’accès :  
* **Accès complet** : l’administrateur Azure AD peut créer un groupe rassemblant les utilisateurs qui bénéficieront d’un accès complet et, éventuellement, créer un autre groupe pour les utilisateurs qui auront un accès restreint.  Seuls les utilisateurs qui sont membres de ces groupes seront autorisés à se connecter à la **console Lookout MTP**.
* **Accès restreint** : les utilisateurs de ce groupe n’auront pas accès à plusieurs modules d’inscription et de configuration dans la console Lookout MTP, et pourront accéder en lecture seule au module **Stratégie de sécurité** dans la console Lookout MTP.  

Pour plus d’informations sur les autorisations, consultez [cet article](https://personal.support.lookout.com/hc/en-us/articles/114094105653) sur le site web de Lookout.

L’**ID d’objet de groupe** est indiqué dans la page **Propriétés** du groupe dans la **console de gestion Azure AD**.

![capture d’écran de la page des propriétés montrant le champ ID de groupe en surbrillance](../media/mtp/aad_group_object_id.png)

Une fois que vous avez collecté ces informations, contactez le support technique Lookout (e-mail : enterprisesupport@lookout.com).

Le support technique Lookout travaillera avec votre contact principal pour intégrer votre abonnement et créer votre compte d’entreprise Lookout MTP sur la base des informations que vous avez collectées.


## Configurer votre abonnement à Lookout MTP
### Étape 1 : Configurer votre MTP
Une fois que le support technique Lookout a créé votre compte d’entreprise Lookout MTP, vous pouvez vous connecter à la console Lookout MTP.   Lookout envoie un e-mail au contact principal de votre entreprise, avec un lien vers cette URL de connexion : https://aad.lookout.com/les?action=consent

Quand vous vous connectez à la console Lookout MTP pour la première fois, vous devez utiliser un compte d’utilisateur ayant le rôle Azure AD Administrateur général, car Lookout MTP en a besoin pour inscrire votre locataire Azure AD.   Pour les connexions suivantes, il n’est pas nécessaire d’avoir ce niveau de privilège Azure AD.  À la première connexion, une page de consentement s’affiche. Choisissez **Accepter** pour terminer l’inscription.

![capture d’écran de la page de première connexion dans la console Lookout MTP](../media/mtp/lookout_mtp_initial_login.png) Une fois que vous avez donné votre consentement, vous êtes redirigé vers la console Lookout MTP. Après l’inscription initiale, vous pouvez vous connecter directement en utilisant cette URL : https://aad.lookout.com

Consultez l’[article sur le dépannage](https://docs.microsoft.com/en-us/intune/troubleshoot/troubleshooting-lookout-integration) si vous rencontrez des problèmes de connexion.

Les étapes suivantes décrivent les tâches que vous devez effectuer pour terminer la configuration de Lookout MTP dans la [console Lookout MTP](https://aad.lookout.com).

### Étape 2 : Configurer le connecteur Intune

1.  Dans la console Lookout MTP, accédez au module **Système**, choisissez l’onglet **Connecteurs**, puis sélectionnez **Intune**.

  ![capture d’écran de la console Lookout MTP montrant l’onglet Connecteurs ouvert et l’option Intune mise en surbrillance](../media/mtp/lookout_mtp_setup-intune-connector.png)

2.  Dans l’option Paramètres de connexion, définissez la fréquence de pulsations (en minutes).  Votre connecteur Intune est maintenant prêt.  

  ![capture d’écran de l’onglet Paramètres de connexion montrant la fréquence de pulsations définie](../media/mtp/lookout-mtp-connection-settings.png)

### Étape 3 : Configurer les groupes d’inscription
Dans l’option **Gestion des inscriptions**, définissez un ensemble d’utilisateurs dont les appareils doivent être inscrits dans Lookout. La bonne pratique consiste à commencer avec un petit groupe d’utilisateurs pour faire des tests et vous familiariser avec le fonctionnement de l’intégration.  Quand vous êtes satisfait de vos résultats de test, vous pouvez étendre l’inscription à d’autres groupes d’utilisateurs.

Pour la prise en main des groupes d’inscription, définissez d’abord un groupe de sécurité Azure AD pour un ensemble initial d’utilisateurs que vous souhaitez inscrire dans Lookout MTP. Après avoir créé le groupe dans Azure AD, dans la console Lookout MTP, accédez à l’option **Gestion des inscriptions** et ajoutez le **nom complet** du groupe de sécurité Azure AD à inscrire.

Quand un utilisateur est membre d’un groupe d’inscription, tous ses appareils qui sont identifiés et pris en charge dans Azure AD sont inscrits et éligibles à l’activation dans Lookout MTP.  La première fois que l’utilisateur ouvre l’application Lookout for Work sur un appareil pris en charge, cet appareil est activé dans Lookout MTP.
![capture d’écran de la page d’inscription dans le connecteur Intune](../media/mtp/lookout-mtp-enrollment.png)

La bonne pratique consiste à utiliser la valeur par défaut (5 minutes) pour l’incrément de durée de recherche de nouveaux appareils.

>[!IMPORTANT]
> Le nom complet respecte la casse.  Utilisez le **nom complet** indiqué dans la page **Propriétés** du groupe de sécurité dans le portail Azure. Notez que le nom complet utilise une casse mixte dans la page **Propriétés** du groupe de sécurité illustrée ci-dessous.  Le titre, qui est entièrement en minuscules, ne doit pas être utilisé pour la connexion à la console Lookout MTP.
>![capture d’écran de la page des propriétés du service Azure Active Directory dans le portail Azure](../media/mtp/aad-group-display-name.png)

La version actuelle présente les limitations suivantes :  
* Les noms complets des groupes ne sont pas validés.  Assurez-vous d’utiliser la valeur du champ **NOM COMPLET** affiché dans le portail Azure pour le groupe de sécurité Azure AD.
* La création de groupes à l’intérieur d’autres groupes n’est pas prise en charge.  Les groupes de sécurité Azure AD spécifiés ne peuvent contenir que des utilisateurs (les groupes imbriqués ne sont pas autorisés).


### Étape 4 : Configurer la synchronisation des états
Dans l’option **Synchronisation des états**, spécifiez le type de données à envoyer à Intune.  Actuellement, vous devez activer l’état de l’appareil et l’état de la menace pour que l’intégration Lookout Intune fonctionne correctement.  Ces deux états sont activés par défaut.
### Étape 5 : Configurer le destinataire des rapports d’erreurs envoyés par e-mail
Dans l’option **Gestion des erreurs**, entrez l’adresse e-mail à laquelle doivent être envoyés les rapports d’erreurs.

![capture d’écran de la page Gestion des erreurs dans le connecteur Intune](../media/mtp/lookout-mtp-connector-error-notifications.png)

### Étape 6 : Configurer les notifications par e-mail
Si vous souhaitez recevoir des alertes sur les menaces par e-mail, connectez-vous à la [console Lookout MTP](https://aad.lookout.com) avec le compte d’utilisateur qui doit recevoir les notifications. Sous l’onglet **Préférences** du module **Système**, définissez les notifications souhaitées sur **ACTIVÉ**. Enregistrez vos modifications.

![capture d’écran de la page des préférences pour le compte d’utilisateur connecté](../media/mtp/lookout-mtp-email-notifications.png) Si vous ne souhaitez plus recevoir de notifications par e-mail, définissez les notifications sur **DÉSACTIVÉ**, puis enregistrez vos modifications.
### Étape 7 : Configurer la classification des menaces
Lookout MTP classe les menaces mobiles dans différents types. Les [classifications des menaces dans Lookout MTP](http://personal.support.lookout.com/hc/en-us/articles/114094130693) ont des niveaux de risque par défaut qui leur sont associés. Ces niveaux peuvent être modifiés à tout moment en fonction des besoins de votre entreprise.

![capture d’écran de la page de stratégie montrant des menaces et des classifications](../media/mtp/lookout-mtp-threat-classification.png)

>[!IMPORTANT]
> Les niveaux de risque spécifiés ici sont un aspect important de MTP, car le processus d’intégration Intune s’en sert pour évaluer la conformité des appareils au moment de l’exécution. En d’autres termes, l’administrateur Intune définit une règle de stratégie qui identifie un appareil comme non conforme si celui-ci présente une menace active du niveau minimum configuré (haut, moyen ou faible). La stratégie de classification des menaces dans MTP a donc un impact direct sur l’évaluation de la conformité des appareils dans Intune.

## Surveillance de l’inscription
Une fois la configuration terminée, Lookout MTP commence à interroger Azure AD pour rechercher les appareils qui correspondent aux groupes d’inscription spécifiés.  Les informations sur les appareils inscrits se trouvent dans le module Appareils.  Les appareils s’affichent dans l’état initial En attente.  L’état de l’appareil change une fois que l’application Lookout for Work est installée, ouverte et activée sur l’appareil.  Pour plus d’informations sur le transfert (pushing) de l’application Lookout for Work sur l’appareil, consultez la rubrique [Configurer et déployer l’application Lookout for Work](configure-and-deploy-lookout-for-work-apps.md).
## Étapes suivantes
[Activer la connexion à Lookout MTP dans la console d’administration Intune](enable-lookout-mtp-connection-in-intune.md)



<!--HONumber=Sep16_HO3-->


