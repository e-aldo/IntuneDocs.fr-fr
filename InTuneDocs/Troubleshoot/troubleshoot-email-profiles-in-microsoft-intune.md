---
# required metadata

title: Résoudre les problèmes de profil de messagerie | Microsoft Intune
description:
keywords:
author: Nbigman
manager: jeffgilb
ms.date: 05/26/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: f5c944ea-32a6-48af-bb57-16d5f1f3c588

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Résoudre les problèmes de profil de messagerie dans Microsoft Intune
Vous trouverez ici quelques exemples de problèmes de profils de messagerie et des instructions pour les résoudre.

Si ces informations ne vous permettent pas de remédier à votre problème, consultez [Comment obtenir un support technique pour Microsoft Intune](how-to-get-support-for-microsoft-intune.md) pour accéder à d’autres types d’assistance.


## Impossible d’envoyer des images à partir du compte de messagerie
Les utilisateurs qui disposent de comptes de messagerie configurés automatiquement ne peuvent pas envoyer des photos ou des images à partir de leur appareil.
Cela se produit lorsque l’option **Autoriser l’envoi de courrier électronique à partir d’applications tierces** n’est pas activée.

### Solution Intune

1.  Ouvrez la console d’administration Microsoft Intune, sélectionnez **Stratégie** Charge de travail &gt; **Stratégie de configuration**.

2.  Sélectionnez le profil de messagerie et choisissez **Modifier**.

3.  Sélectionnez **Autoriser l’envoi de courrier électronique à partir d’applications tierces**.

### Configuration Manager intégré à la solution Intune

1.  Dans la console Configuration Manager, ouvrez &gt; **Ressources et Conformité**.

2.  Développez **Vue d’ensemble** -&gt; **Paramètres de conformité** -&gt; **Accès aux ressources d’entreprise**, puis sélectionnez **Profils de messagerie**.

3.  Cliquez avec le bouton droit sur le profil de messagerie, puis ouvrez **Propriétés**.

4.  Sous l’onglet **Paramètres de synchronisation**, sélectionnez **Autoriser l’envoi de courrier électronique à partir d’applications tierces**.

## Étapes suivantes
Si ces informations de dépannage n’ont pas permis de vous aider, contactez le support Microsoft comme décrit dans [Comment obtenir un support technique pour Microsoft Intune](how-to-get-support-for-microsoft-intune.md).


<!--HONumber=Jun16_HO1-->


