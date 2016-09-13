---
title: Notes de publication pour Microsoft Intune | Microsoft Intune
description: Notes de publication Intune
keywords: 
author: Staciebarker
manager: angrobe
ms.date: 09/08/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: db9479b2-582d-4a1a-9fbc-fbfc6c680e6f
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 7549b5af84e5a1712c2e1649b1afe03718d53dcc
ms.openlocfilehash: ad95830b37d3b83554b64d2f82fa537e603190d6


---

# Notes de publication pour Microsoft Intune
Microsoft Intune est une solution cloud intégrée de gestion de clients qui fournit des outils, des rapports et des licences de mise à niveau vers la dernière version de Windows et vous aide à maintenir vos ordinateurs à jour et sécurisés. De plus, Intune vous permet de gérer des appareils mobiles sur le réseau avec Exchange ActiveSync ou directement par le biais d’Intune. Les notes de publication suivantes décrivent les informations importantes et les problèmes connus dans Microsoft Intune.


## Les utilisateurs Android ne peuvent pas envoyer de courriers électroniques lorsque l’accès conditionnel à Exchange Online est mis en place

Les utilisateurs d’appareils sous Samsung Android 5.1.1 et versions supérieures ne peuvent pas envoyer de courriers électroniques lorsque l’accès conditionnel à Exchange Online est configuré. Samsung reconnaît que le problème se trouve dans son client de messagerie intégré dans Android 5.1.1 et versions ultérieures et étudie actuellement la possibilité d’un correctif.

**Solution de contournement 1 :** conseiller aux utilisateurs finaux d’utiliser l’application Outlook pour Android.

**Solution de contournement 2 :** pour permettre aux utilisateurs concernés d’envoyer des courriers électroniques, vous pouvez suivre les étapes suivantes :

1. Placez l’utilisateur concerné dans un groupe de sécurité de la section « groupes exemptés » de la stratégie d’accès conditionnel à Exchange Online.
2. Autorisez l’utilisateur à synchroniser temporairement la messagerie sur le client de messagerie intégré.
3. Supprimer l’utilisateur concerné du groupe exempté et vérifiez que l’utilisateur peut maintenant envoyer des courriers électroniques.

Microsoft continuera à travailler étroitement avec Samsung sur un correctif ou d’autres solutions de contournement.



## La modification des profils d’accès aux ressources entre les groupes pour iOS et Android peut échouer
**Problème :** quand vous modifiez des profils d’accès aux ressources de messagerie ou SCEP (Simple Certificate Enrollment Protocol) entre des groupes, les profils peuvent entrer en conflit et échouer. Par exemple, imaginez qu’un profil de messagerie existant pointe vers un serveur Exchange local et cible le Groupe A, et que vous créez ensuite un profil de messagerie qui pointe vers Exchange Online et cible le Groupe B. Quand vous déplacez des utilisateurs du Groupe A vers le Groupe B, les appareils conservent le profil de messagerie Exchange local et tentent d’installer le profil de messagerie Exchange Online ciblant le Groupe B.

À ce stade, l’une des actions suivantes se produit : 
* Si les profils de messagerie A et B sont identiques, l’appareil rejette le profil de messagerie B, car celui-ci contient déjà le profil de messagerie A.
* Si le profil de messagerie A est différent du profil de messagerie B, comme indiqué dans l’exemple ci-dessus, l’appareil se retrouve avec deux profils de messagerie.

**Remarque :** Le nom d’hôte et l’attribut utilisé pour le nom d’utilisateur sont vérifiés, afin de distinguer un profil de messagerie d’un autre.

Dans les deux cas ci-dessus, le profil d’accès aux ressources (profil de messagerie) n’a pas été supprimé de l’appareil, afin d’éviter la suppression involontaire de l’accès à la messagerie d’un utilisateur ou du certificat SCEP du client.

**Solution de contournement :** aucune.

## Lorsque vous inscrivez un appareil Windows 8.1 qui doit s'authentifier auprès d'un serveur proxy, le processus d'inscription échoue sans aucune indication visible sur la cause de l'échec.
**Problème :** quand vous inscrivez un appareil Windows 8.1 et que celui-ci doit s’authentifier auprès d’un serveur proxy pendant l’inscription, le processus échoue si l’appareil n’a pas mis en cache les informations d’identification du serveur proxy. Lorsque les informations d’identification du serveur proxy ne sont pas mises en cache sur l’appareil, le processus d’inscription doit attendre que l’utilisateur entre ces informations d’identification. Toutefois, l'invitation à fournir les informations d'identification du serveur proxy ne s'affiche pas au cours du processus d'inscription. Il en résulte que le processus d'inscription ne peut pas s'authentifier auprès du serveur proxy et qu'il n'existe aucune indication de cet échec visible à l'utilisateur.

**Solution de contournement :** pour les appareils Windows 8.1 qui doivent s’inscrire sur un réseau nécessitant l’utilisation d’un serveur proxy authentifié, configurez et enregistrez les informations d’identification du serveur proxy avant l’inscription de l’appareil. Pour configurer et enregistrer les informations d’identification sur un appareil Windows 8.1 :

1.  Sur l’appareil Windows 8.1, ouvrez **Internet Explorer**.

2.  Lorsque vous y êtes invité, entrez les informations d'identification du serveur proxy, puis sélectionnez l'option **Mémoriser mes informations d'identification**.

3.  Inscrivez l'appareil.

## Les appareils Windows Phone 8.1 ne parviennent pas à s'inscrire à Microsoft Intune quand l'authentification de l'appareil est activée dans AD FS
**Problème :** quand vous inscrivez un appareil Windows Phone 8.1, l’inscription échoue si le paramètre facultatif d’authentification des appareils est activé dans le cadre de la stratégie d’authentification globale des services fédérés Active Directory (AD FS).

**Solution de contournement :** désactivez l’authentification des appareils sur le serveur AD FS en décochant l’option **Activer l’authentification des appareils** dans **Modifier la stratégie d’authentification globale**. Pour plus d'informations, consultez [Configuration des stratégies d'authentification](http://technet.microsoft.com/library/dn486781.aspx)


## L'outil de création de package de restrictions d'application Microsoft Intune pour Android n'intègre aucune fonctionnalité de désinstallation
**Problème :** l’outil **Microsoft App Wrapping Tool for Android** n’intègre aucune fonctionnalité permettant de le désinstaller.

**Solution de contournement :** accédez à l’emplacement où vous avez installé l’outil, puis supprimez le répertoire. L’emplacement d’installation par défaut est : **C:\Program Files (x86)\Microsoft Intune Mobile Application Management\Android\App Wrapping Tool**. Pour plus d’informations sur App Wrapping Tool, consultez [Préparer des applications Android pour la gestion avec App Wrapping Tool](/intune/deploy-use/prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool).

## L'assistance à distance n'est pas disponible sur les ordinateurs qui exécutent Windows 8 ou Windows 8.1
**Problème :** dans cette version, la fonctionnalité d’assistance à distance n’est pas disponible sur les ordinateurs qui exécutent Windows 8 ou Windows 8.1.

**Solution de contournement :** aucune.

## Les notifications d'alerte pour les destinataires qui sont automatiquement ajoutés peuvent ne pas fonctionner.
**Problème :** si un destinataire est automatiquement ajouté à une notification d'alerte, il se peut qu'il ne reçoive pas toujours une notification.

**Solution de contournement :** pour vous assurer que les destinataires recevront la notification, vous devez ajouter manuellement des destinataires de notifications d'alerte.

## Prise en charge linguistique dans le portail Azure en version préliminaire
Le portail Azure en version préliminaire repose sur une nouvelle plateforme et prend en charge les langues suivantes : chinois (simplifié), chinois (traditionnel), tchèque, néerlandais, anglais, allemand, hongrois, italien, japonais, portugais (Brésil), portugais (Portugal), russe, espagnol, anglais, français, coréen, polonais, suédois, turc.

L’expérience mobile visible par l’utilisateur final et la console d’administration Intune prennent en charge le danois, le grec, le finnois, le norvégien et le roumain, en plus des langues prises en charge par le portail Azure en version préliminaire.



<!--HONumber=Sep16_HO2-->


