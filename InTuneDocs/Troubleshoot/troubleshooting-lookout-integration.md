---
title: "Résoudre les problèmes d’intégration de Lookout | Documentation Microsoft"
description: "Cette rubrique décrit comment résoudre des problèmes courants liés à l’intégration de Lookout"
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 09/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bbe0b5f4-b8bc-49f3-85a9-51fb2f226fca
ms.reviewer: sandera
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: d6ff74f0b46baf384dbdedf13ad75538dd33a089
ms.openlocfilehash: 416f200bdb72bae98897cb8d279dbdb767757da9


---

# <a name="troubleshoot-lookout-integration-with-intune"></a>Résoudre les problèmes d’intégration de Lookout avec Intune
Cette rubrique décrit quelques problèmes courants susceptibles de se produire avec la configuration de votre protection contre les menaces mobiles (MTP) de Lookout.
## <a name="troubleshoot-login-errors"></a>Résoudre les erreurs de connexion
### <a name="403-errors"></a>Erreurs 403
Une erreur 403 peut s’afficher quand vous vous connectez à la [console Lookout MTP](https://aad.lookout.com) : **vous n’êtes pas autorisé à accéder au service**. Cette erreur peut se produire si vous avez spécifié un nom d’utilisateur qui n’est pas membre du groupe Azure Active Directory (Azure AD) configuré pour accéder à Lookout MTP.

Lookout MTP est configuré pour autoriser l’accès uniquement pour les utilisateurs qui appartiennent à un groupe Azure AD configuré. Si vous ne savez pas quel groupe est configuré avec un accès à Lookout MTP, contactez le support technique de Lookout.

Vous pouvez contacter le support technique de Lookout de l’une des façons suivantes :

* E-mail : enterprisesupport@lookout.com
* En vous connectant à la [console MTP](http://aad.lookout.com) et en accédant au module **Support**
* En effectuant une demande de support sur le site https://enterprise.support.lookout.com/hc/en-us/requests

### <a name="unable-to-sign-in"></a>Connexion impossible
L’erreur suivante peut se produire si l’administrateur général Azure AD n’a pas accepté l’installation initiale de Lookout.

![Capture de l’écran de connexion à Lookout montrant l’échec de la connexion](../media/mtp/lookout-mtp-consent-not-accepted-error.png)

Pour résoudre ce problème, l’administrateur général doit se connecter à https://aad.lookout.com/les?action=consent et accepter l’invite à lancer le programme d’installation. Pour plus d’informations, consultez la rubrique [Configurer votre abonnement à Lookout MTP](../deploy-use/set-up-your-subscription-with-lookout-mtp.md).

## <a name="troubleshoot-device-status-issues"></a>Résoudre les problèmes liés à l’état de l’appareil

### <a name="device-not-showing-up-in-the-lookout-mtp-console-device-list"></a>L’appareil ne s’affiche pas dans la liste d’appareils de la console Lookout MTP

Cette erreur peut se produire dans les scénarios suivants :
* L’utilisateur propriétaire de l’appareil n’est pas membre du **Groupe d’inscription** spécifié dans la **Console Lookout MTP**.  Dans le module **Système**, accédez à l’onglet **Connecteur Intune** et vérifiez les paramètres **Gestion des inscriptions**.  Vous devez normalement voir un ou plusieurs groupes Azure AD configurés pour l’inscription.  Vérifiez que l’utilisateur à qui appartient l’appareil manquant est membre de l’un des groupes Azure AD spécifiés.  Après l’ajout d’un nouvel utilisateur au groupe d’inscription, un délai d’attente correspondant au maximum à l’intervalle d’interrogation configuré (5 minutes par défaut) peut être nécessaire pour voir s’afficher l’appareil dans le module **Appareils** de la console Lookout MTP.

* L’appareil n’est pas pris en charge par Lookout MTP.  Les appareils non pris en charge sont affichés dans la section **Appareils gérés** des paramètres du connecteur dans la console Lookout MTP.

### <a name="device-continues-to-be-reported-as-pending"></a>L’appareil reste toujours dans l’état **en attente**

Quand l’appareil s’affiche dans l’état **en attente**, cela signifie que l’utilisateur final n’a pas ouvert l’application Lookout for Work ni appuyé sur le bouton **Activer**. Pour plus d’informations sur l’activation de l’appareil avec l’application Lookout for Work, consultez la rubrique suivante :

[Vous êtes invité à installer Lookout for Work sur votre appareil Android ](http://docs.microsoft.com/intune/enduser/you-are-prompted-to-install-lookout-for-work-android)

### <a name="in-the-lookout-mtp-console-a-device-is-showing-as-active-but-does-not-have-a-device-id"></a>Dans la console Lookout MTP, un appareil est affiché comme étant actif, mais il n’a pas d’ID d’appareil.  
Cela signifie que l’utilisateur propriétaire de cet appareil n’est pas membre du groupe d’inscription spécifié dans la console Lookout MTP.   Un appareil peut avoir cet état si l’utilisateur qui possède l’appareil a été supprimé du groupe d’inscription ou si le groupe d’inscription auquel appartient l’utilisateur a été supprimé.

Dans le module **Système** de la console Lookout MTP, accédez à l’onglet **Connecteur Intune** et vérifiez les paramètres **Inscription**.  Vous devez normalement voir un ou plusieurs groupes Azure AD configurés pour l’inscription.  Vérifiez que l’utilisateur propriétaire de l’appareil est membre de l’un des groupes Azure AD spécifiés.  

Quand un appareil est dans cet état, Lookout continue d’avertir l’utilisateur des menaces détectées, mais il n’envoie pas d’informations à leur sujet à Intune.

### <a name="device-shows-disconnected-state"></a>L’appareil s’affiche dans l’état déconnecté

L’état déconnecté signifie que Lookout MTP n’a pas enregistré d’activité sur l’appareil au cours de la période préconfigurée (30 jours par défaut, avec un minimum de 7 jours). Cela signifie que l’application Portail d’entreprise ou l’application Lookout for Work n’est pas installée sur l’appareil ou qu’elle a été désinstallée. Pour résoudre ce problème, réinstallez l’application. Quand l’utilisateur ouvre l’application Lookout for Work et l’active, l’appareil est resynchronisé avec Lookout MTP et Intune.    

### <a name="forcing-a-resync-on-the-device"></a>Forcer une resynchronisation sur l’appareil
Dans le module **Appareils** de la console Lookout MTP, l’administrateur peut sélectionner l’appareil pour le supprimer.   Quand l’utilisateur propriétaire de l’appareil rouvre ensuite l’application Lookout for Work et appuie sur **Activer**, l’état de l’appareil est entièrement resynchronisé.

### <a name="the-owner-of-the-device-is-no-longer-using-this-device"></a>Cet appareil n’est plus utilisé par son propriétaire
Vous devez réinitialiser l’appareil et demander au nouvel utilisateur de l’inscrire.  Dans la [console Administrateur Intune](https://manage.microsoft.com), sélectionnez l’appareil, cliquez avec le bouton droit et choisissez **Mettre hors service/Réinitialiser** pour supprimer l’appareil de la gestion. Après cette opération, vous pouvez supprimer l’appareil.

![Capture d’écran du module Appareils de la console Administrateur Intune montrant l’option Mettre hors service/Réinitialiser](../media/mtp/mtp-retire-device-intune-console.png)

Vous pouvez également accéder au module **Appareils** dans la console Lookout MTP et choisir **Supprimer**.  

Si le nouvel utilisateur est membre d’un des groupes d’inscription spécifiés dans la console Lookout MTP, l’appareil s’affiche une fois qu’Azure AD l’a associé avec le nouvel utilisateur.

## <a name="compliance-remediation-workflows"></a>Étapes de la correction de conformité
[Vous êtes invité à installer Lookout for Work sur votre appareil Android]( http://docs.microsoft.com/intune/enduser/you-are-prompted-to-install-lookout-for-work-android)

[Vous devez résoudre une menace que Lookout for Work a détectée sur votre appareil Android ](http://docs.microsoft.com/intune/enduser/you-need-to-resolve-a-threat-found-by-lookout-for-work-android)


### <a name="see-also"></a>Voir aussi
[Configurer votre abonnement à Lookout MTP](https://docs.microsoft.com/en-us/intune/deploy-use/set-up-your-subscription-with-lookout-mtp)



<!--HONumber=Dec16_HO2-->


