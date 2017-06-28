---
title: "Résoudre les problèmes d’intégration de Lookout"
description: "Cette rubrique décrit comment résoudre des problèmes courants liés à l’intégration de Lookout"
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 12/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bbe0b5f4-b8bc-49f3-85a9-51fb2f226fca
ms.reviewer: sandera
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: df3c42d8b52d1a01ddab82727e707639d5f77c16
ms.openlocfilehash: cd3c2809161aa438eb7aef91a65d68cb0f657607
ms.contentlocale: fr-fr
ms.lasthandoff: 06/08/2017


---

# <a name="troubleshoot-lookout-integration-with-intune"></a>Résoudre les problèmes d’intégration de Lookout avec Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Cette rubrique décrit quelques problèmes courants susceptibles de se produire avec la configuration de votre protection contre les menaces mobiles (MTP) de Lookout.

**Erreurs de connexion**

## <a name="403-errors"></a>Erreurs 403
Lorsque vous vous connectez à la [console Lookout MTP](https://aad.lookout.com), une erreur 403 s’affiche : **vous n’êtes pas autorisé à accéder à ce service**. Cette erreur peut se produire si vous avez spécifié un nom d’utilisateur qui n’est pas membre du groupe Azure Active Directory (Azure AD) configuré pour accéder à Lookout MTP.

Lookout MTP autorise uniquement les utilisateurs d’un groupe Azure AD configuré à accéder au service. Pour déterminer le groupe configuré avec un accès à Lookout MTP, contactez le support technique de Lookout :

* E-mail : enterprisesupport@lookout.com
* En vous connectant à la [console MTP](http://aad.lookout.com) et en accédant au module **Support**
* En effectuant une demande de support sur le site https://enterprise.support.lookout.com/hc/requests.

## <a name="unable-to-sign-in"></a>Connexion impossible
L’erreur suivante se produit si l’administrateur général Azure AD n’a pas accepté l’installation initiale de Lookout.

![Capture de l’écran de connexion à Lookout montrant l’échec de la connexion](../media/mtp/lookout-mtp-consent-not-accepted-error.png)

Pour résoudre ce problème, l’administrateur général doit se connecter à https://aad.lookout.com/les?action=consent et accepter l’invite à lancer le programme d’installation. Pour plus d’informations, consultez la rubrique [Configurer votre abonnement à Lookout MTP](../deploy-use/setup-your-lookout-mtd-subscription.md).

**Problèmes d'état de l’appareil**

## <a name="device-missing-from-lookout-device-list"></a>Appareil manquant dans la liste d’appareils Lookout

Cette erreur peut se produire dans les scénarios suivants :
* L’utilisateur de l’appareil n’est pas dans le **groupe d’inscription** spécifié dans la **Console Lookout MTP**.  Dans la [Console Lookout](http://aad.lookout.com), accédez à **System (Système)** > **Intune Connector (Connecteur Intune)** > **Enrollment Management (Gestion des inscriptions)**.  Passez en revue les groupes Azure AD configurés pour l’inscription et vérifiez que l’utilisateur de l’appareil fait partie de l’un des groupes Azure AD.  Après l’ajout d’un utilisateur au groupe d’inscription, un délai d’attente correspondant au maximum à l’intervalle d’interrogation configuré (5 minutes par défaut) peut être nécessaire pour voir s’afficher l’appareil dans le module **Appareils** de la console Lookout MTP.
* L’appareil n’est pas pris en charge par Lookout MTP.  Les appareils non pris en charge sont affichés dans la section **Appareils gérés** des paramètres du connecteur dans la console Lookout MTP.

### <a name="device-reported-as-pending"></a>Appareil signalé comme **en attente**

L’appareil s’affiche à l’état **en attente** si l’utilisateur final n’a pas ouvert l’application Lookout for Work ni appuyé sur le bouton **Activer**. Pour plus d’informations sur l’activation d’appareils avec l’application Lookout for Work, consultez [Vous êtes invité à installer Lookout for Work sur votre appareil Android](http://docs.microsoft.com/intune-user-help/you-are-prompted-to-install-lookout-for-work-android) ou [Vous êtes invité à installer Lookout for Work sur votre appareil iOS](https://docs.microsoft.com/intune-user-help/you-are-prompted-to-install-lookout-for-work-ios).

## <a name="device-whos-active-but-has-no-device-id"></a>Appareil actif, mais ne possédant aucun ID d’appareil
Dans la console Lookout MTP, l’utilisateur de l’appareil ne fait pas partie du groupe d’inscription si un périphérique actif ne comporte aucun ID d’appareil. Un appareil peut avoir cet état si son utilisateur été supprimé du groupe d’inscription ou si le groupe d’inscription a été supprimé.

Dans la [Console Lookout](http://aad.lookout.com), accédez à **System (Système)** > **Intune Connector (Connecteur Intune)** > **Enrollment (Inscription)** pour vérifier les paramètres.  Passez en revue les groupes Azure AD et vérifiez que l’utilisateur de l’appareil fait partie de l’un des groupes Azure AD.

Quand un appareil est dans cet état, Lookout continue d’avertir l’utilisateur des menaces détectées, mais il n’envoie pas d’informations à leur sujet à Intune.

## <a name="device-reported-as-disconnected"></a>Appareil signalé comme **déconnecté**

L’état **Déconnecté** signifie que l’appareil n’est pas synchronisé avec Lookout MTP dans l’intervalle configuré (30 jours par défaut avec un minimum de 7 jours). L’application Portail d’entreprise ou Lookout for Work manque dans l’appareil. Pour résoudre ce problème, réinstallez l’application. Quand l’utilisateur ouvre l’application Lookout for Work et l’active, l’appareil est resynchronisé avec Lookout MTP et Intune.

### <a name="forcing-a-device-sync"></a>Forçage d’une synchronisation de l’appareil
Dans le module **Appareils** de la console Lookout MTP, l’administrateur peut sélectionner l’appareil pour le supprimer.   Quand l’utilisateur propriétaire de l’appareil rouvre ensuite l’application Lookout for Work et appuie sur **Activer**, l’état de l’appareil est entièrement resynchronisé.

## <a name="device-has-a-new-user"></a>L’appareil a un nouvel utilisateur
Vous devez réinitialiser l’appareil et demander au nouvel utilisateur de l’inscrire.  Dans la [console Administrateur Intune](https://manage.microsoft.com), sélectionnez l’appareil, cliquez avec le bouton droit et choisissez **Mettre hors service/Réinitialiser** pour supprimer l’appareil de la gestion. Après cette opération, vous pouvez supprimer l’appareil.

![Capture d’écran du module Appareils de la console Administrateur Intune montrant l’option Mettre hors service/Réinitialiser](../media/mtp/mtp-retire-device-intune-console.png)

Vous pouvez également accéder au module **Appareils** dans la [console Lookout](http://aad.lookout.com) et choisir **Supprimer**.

Si le nouvel utilisateur est membre d’un groupe d’inscription Lookout MTP, l’appareil s’affiche une fois qu’Azure AD l’a associé au nouvel utilisateur.

## <a name="compliance-remediation-workflows"></a>Étapes de la correction de conformité
- [Vous êtes invité à installer Lookout for Work sur votre appareil Android]( http://docs.microsoft.com/intune-user-help/you-are-prompted-to-install-lookout-for-work-android)
- [Vous devez résoudre une menace que Lookout for Work a détectée sur votre appareil Android](http://docs.microsoft.com/intune-user-help/you-need-to-resolve-a-threat-found-by-lookout-for-work-android)
- [Vous devez résoudre une menace que Lookout for Work a détectée sur votre appareil iOS](https://docs.microsoft.com/intune-user-help/you-need-to-resolve-a-threat-found-by-lookout-for-work-ios)


### <a name="see-also"></a>Voir aussi
[Configurer votre abonnement à Lookout MTP](/intune-classic/deploy-use/set-up-your-subscription-with-lookout-mtp)

