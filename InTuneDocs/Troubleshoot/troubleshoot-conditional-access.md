---
title: "Résoudre les problèmes d’accès conditionnel | Microsoft Intune"
description: 
keywords: 
author: nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 433fc32c-ca9c-4bad-9616-852c72faf996
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 4f79d2890c450a803bfb84ffa3c12b0de58a158c
ms.openlocfilehash: 373b9bf9794840f999d5e5b21fc411ff621a23e1


---

# Résoudre les problèmes d’accès conditionnel

Cette rubrique décrit les actions à entreprendre quand vos utilisateurs ne parviennent pas à accéder à des ressources par le biais de l’accès conditionnel Intune. 

### Ce qu’il faut savoir pour réussir l’accès conditionnel

Pour que l’accès conditionnel fonctionne, les conditions suivantes doivent être remplies :

-   L’appareil doit être géré par Intune.
-   L’utilisateur doit être inscrit auprès d’Azure Active Directory (AAD).
-   L’appareil doit être conforme aux stratégies de conformité que vous avez configurées dans Intune. 
-   EAS doit être activé sur l’appareil si l’utilisateur récupère ses e-mails par l’intermédiaire du client de messagerie natif de l’appareil, plutôt que par l’intermédiaire d’Outlook.

Ces conditions sont visibles sur chaque appareil dans le portail de gestion Azure et dans le rapport d’inventaire des appareils.





En général, l’utilisateur tente d’accéder à ses e-mails ou à SharePoint et reçoit une invitation à s’inscrire. Cette invitation le conduit au portail d’entreprise. Voici des explications possibles de ce comportement, ainsi que les solutions suggérées :

## Scénarios d’authentification moderne

### Problèmes d’inscription

 -  L’appareil n’est pas inscrit. L’inscription résoudra le problème.
 -  L’utilisateur a inscrit l’appareil, mais la jonction au lieu de travail a échoué. L’utilisateur doit mettre à jour l’inscription à partir du portail d’entreprise. 
 
### Problèmes de conformité

 -  L’appareil n’est pas conforme à la stratégie Intune. Les critères de chiffrement et de mot de passe font partie des problèmes courants. L’utilisateur est redirigé vers le portail d’entreprise, où il peut configurer son appareil pour qu’il soit conforme.
 -  Pour les appareils iOS, un profil de messagerie existant créé par l’utilisateur bloque le déploiement d’un profil conforme (créé par l’administrateur Intune) à partir d’Intune. Il s’agit d’un problème courant parce que les utilisateurs iOS créent généralement un profil de messagerie, puis s’inscrivent. Le portail d’entreprise informe les utilisateurs qu’ils ne sont pas conformes en raison de leur profil de messagerie configuré manuellement et les invite à supprimer ce profil. Les utilisateurs doivent supprimer leur profil de messagerie pour que le profil Intune puisse être déployé. Pour éviter ce problème, demandez à vos utilisateurs de s’inscrire sans installer de profil de messagerie et d’autoriser Intune à déployer le profil.  
 -  L’inscription des informations de conformité d’un appareil peut demander un certain temps. Attendez quelques minutes et réessayez.

### Problèmes de stratégie

Quand vous créez une stratégie de conformité et que vous la liez à une stratégie de messagerie, les deux stratégies doivent être déployées sur le même utilisateur. Par conséquent, soyez vigilant quand vous planifiez quelles stratégies sont déployées sur quels groupes. Les utilisateurs auxquels une seule stratégie est appliquée découvriront probablement que leurs appareils ne sont pas conformes.


## Scénarios Exchange ActiveSync


- Un appareil Android inscrit et conforme peut quand même recevoir une notification de mise en quarantaine quand vous tentez d’accéder à des ressources d’entreprise. Avant de cliquer sur le lien indiquant **Commencer**, l’utilisateur doit vérifier que le portail d’entreprise n’était pas ouvert quand il a tenté d’accéder aux ressources. Les utilisateurs doivent fermer le portail d’entreprise, réessayer d’accéder aux ressources, puis cliquer sur le lien **Commencer**.

- Un appareil mis hors service peut continuer à avoir accès aux ressources pendant plusieurs heures après sa mise hors service. En effet, Exchange met en cache les droits d’accès pendant 6 heures. Envisagez d’autres moyens de protéger les données sur les appareils mis hors service dans ce scénario.
- Problème potentiel : Impossibilité d’appliquer le correctif de l’ID EAS à AAD. La limitation constitue une cause courante de ce problème. Par conséquent, attendez quelques minutes et réessayez. 

## Collecte des journaux de boîte aux lettres OWA

Si vos problèmes de connectivité Exchange persistent après le dépannage de votre déploiement, collectez les journaux de boîte aux lettres OWA avant de contacter le support technique Microsoft comme décrit dans [Comment obtenir un support technique pour Microsoft Intune](how-to-get-support-for-microsoft-intune.md).

1. Connectez-vous par le biais d’OWA et choisissez le symbole Paramètres (engrenage) en regard de votre nom en haut à droite. 
2. Choisissez **Options**.
3. Choisissez **Téléphone** (ou bien **Appareils mobiles**) dans la colonne sur le côté gauche.
4. Dans le menu affiché en haut, choisissez **Appareils mobiles**. 
5. Choisissez votre appareil dans la liste, puis **Démarrer l’enregistrement dans le journal**. 
6. Quand vous y êtes invité, choisissez **Oui** dans la boîte de dialogue contextuelle. 
7. Exécutez l’action qui a provoqué le problème pour pouvoir le reproduire. 
8. Patientez 1 à 2 minutes, puis revenez à la liste de téléphones dans OWA, vérifiez que votre téléphone est sélectionné dans la liste, puis dans le menu principal, choisissez **Récupérer le journal**. 
9. Vous devez maintenant avoir un e-mail de vous-même avec une pièce jointe. Quand vous ouvrez un ticket de support, fournissez le contenu de l’e-mail au support technique Microsoft.


### Étapes suivantes
Si ces informations de dépannage n’ont pas permis de vous aider, contactez le support Microsoft comme décrit dans [Comment obtenir un support technique pour Microsoft Intune](how-to-get-support-for-microsoft-intune.md).



<!--HONumber=Jun16_HO4-->


