---
title: "Résoudre les problèmes de profil de messagerie"
description: "Cette rubrique présente des problèmes de profils de messagerie et fournit des instructions pour les résoudre."
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f5c944ea-32a6-48af-bb57-16d5f1f3c588
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: tscott
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: c8f74ffd45fd46186b8b225fc64212ec61fefdad
ms.sourcegitcommit: 3b397b1dcb780e2f82a3d8fba693773f1a9fcde1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/12/2017
---
# <a name="troubleshoot-email-profiles-in-microsoft-intune"></a>Résoudre les problèmes de profil de messagerie dans Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Vous trouverez ici quelques exemples de problèmes de profils de messagerie et des instructions pour les résoudre.

Si ces informations ne vous permettent pas de remédier à votre problème, consultez [Comment obtenir un support technique pour Microsoft Intune](how-to-get-support-for-microsoft-intune.md) pour accéder à d’autres types d’assistance.


## <a name="unable-to-send-images-from--email-account"></a>Impossible d’envoyer des images à partir du compte de messagerie
Les utilisateurs qui disposent de comptes de messagerie configurés automatiquement ne peuvent pas envoyer des photos ou des images à partir de leur appareil.
Cela se produit lorsque l’option **Autoriser l’envoi de courrier électronique à partir d’applications tierces** n’est pas activée.

### <a name="intune-solution"></a>Solution Intune

1.  Ouvrez la console d’administration Microsoft Intune, sélectionnez **Stratégie** Charge de travail &gt; **Stratégie de configuration**.

2.  Sélectionnez le profil de messagerie et choisissez **Modifier**.

3.  Sélectionnez **Autoriser l’envoi de courrier électronique à partir d’applications tierces**.

### <a name="configuration-manager-integrated-with-intune-solution"></a>Configuration Manager intégré à la solution Intune

1.  Dans la console Configuration Manager, ouvrez &gt; **Ressources et Conformité**.

2.  Développez **Vue d’ensemble** -&gt; **Paramètres de conformité** -&gt; **Accès aux ressources d’entreprise**, puis sélectionnez **Profils de messagerie**.

3.  Cliquez avec le bouton droit sur le profil de messagerie, puis ouvrez **Propriétés**.

4.  Sous l’onglet **Paramètres de synchronisation**, sélectionnez **Autoriser l’envoi de courrier électronique à partir d’applications tierces**.


## <a name="device-already-has-an-email-profile-installed"></a>Un profil de messagerie est déjà installé sur l’appareil

Si l’utilisateur a installé un profil de messagerie avant de configurer un profil via Intune, le résultat du déploiement du profil de messagerie Intune dépend de la plate-forme d’appareil :

-**iOS** : Intune détecte un profil de messagerie existant en double, en fonction de l’adresse e-mail et du nom d’hôte. Le profil de messagerie en double que l’utilisateur a créé bloque le déploiement d’un profil créé par un administrateur Intune. Il s’agit d’un problème courant parce que les utilisateurs iOS créent généralement un profil de messagerie, puis s’inscrivent. Le portail d’entreprise informe les utilisateurs qu’ils ne sont pas conformes en raison de leur profil de messagerie configuré manuellement et les invite à supprimer ce profil. Les utilisateurs doivent supprimer leur profil de messagerie pour que le profil Intune puisse être déployé. Pour éviter ce problème, demandez à vos utilisateurs de s’inscrire avant d’installer le profil de messagerie et d’autoriser Intune à déployer le profil.

-**Windows** : Intune détecte un profil de messagerie existant en double, en fonction de l’adresse e-mail et du nom d’hôte. Intune remplace le profil de messagerie existant que l’utilisateur a créé.

-**Samsung KNOX Standard** : Intune identifie un compte de messagerie en double en fonction de l’adresse e-mail et le remplace par le profil Intune. Si l’utilisateur configure ce compte, il est remplacé à nouveau par le profil Intune. Remarque : cela peut entraîner une certaine confusion pour l’utilisateur dont la configuration de compte est remplacée.

Étant donné que Samsung KNOX n’utilise pas le nom d’hôte pour identifier le profil, nous vous recommandons de ne pas créer plusieurs profils de messagerie à déployer à la même adresse e-mail sur des hôtes différents, car ils se remplaceront l’un l’autre.

## <a name="error--0x87d1fde8-for-knox-standard-device"></a>Erreur 0x87D1FDE8 pour appareil KNOX Standard
**Problème**: Après la création et le déploiement d’un profil de messagerie Exchange Active Sync pour Samsung KNOX Standard pour différents appareils Android, l’erreur **0x87D1FDE8** ou un **échec de la correction** est signalé sous l’onglet de stratégie des propriétés de l’appareil &gt;.

Examinez la configuration de votre profil EAS pour Samsung KNOX et la stratégie source. L’option de synchronisation Samsung Notes n’étant plus prise en charge, nous vous invitons à ne pas la sélectionner dans votre profil. Assurez-vous que les appareils ont eu suffisamment de temps pour traiter la stratégie (jusqu’à 24 heures).

## <a name="next-steps"></a>Étapes suivantes
Si ces informations de dépannage n’ont pas permis de vous aider, contactez le support Microsoft comme décrit dans [Comment obtenir un support technique pour Microsoft Intune](how-to-get-support-for-microsoft-intune.md).
