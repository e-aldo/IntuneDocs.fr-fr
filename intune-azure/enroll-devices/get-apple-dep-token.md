---
title: "Obtenir un certificat DEP Apple pour Intune | Version préliminaire d’Intune Azure | Microsoft Docs"
description: "Version préliminaire d’Intune Azure : instructions relatives à la configuration et au téléchargement d’un certificat Push MDM, composant requis pour la gestion des appareils Apple dans Intune. "
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 02/03/17
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7e5c79c5-2883-4841-9be6-74cba16ee447
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 65a6b2e22359bdcb9b0c15a84c6b3586dafe4d6c
ms.openlocfilehash: c740dedebdc4afd909a8c38447f698c2724de5a1

---

# <a name="get-an-apple-dep-certificate"></a>Obtenir un certificat DEP Apple 

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Avant de pouvoir inscrire des appareils iOS d’entreprise à l’aide du programme DEP, vous devez obtenir un jeton approprié auprès d’Apple. Ce jeton permet à Intune de synchroniser les informations sur les appareils participant à ce programme et appartenant à votre entreprise. Il permet également à Intune d'effectuer des téléchargements de profil d'inscription sur Apple et d'attribuer des appareils à ces profils.

Pour gérer les appareils iOS d’entreprise avec le programme d’inscription des appareils (DEP) d’Apple, votre organisation doit participer au programme et obtenir des appareils par le biais de ce programme. Les détails de cette procédure sont disponibles à l’adresse suivante : https://deploy.apple.com. Les avantages du programme incluent la configuration automatique des appareils sans utiliser de câble USB pour connecter chaque appareil à un ordinateur.

> [!NOTE]
> Lisez cette note uniquement si vous êtes un client qui a été migré de la console d’administration Intune vers le portail Azure. Si vous avez supprimé un jeton DEP Apple de la console d’administration Intune pendant la période de migration, il est possible que le jeton DEP ait été restauré dans votre compte Intune. Dans ce cas, supprimez simplement le jeton DEP à partir du portail Azure. 

**Pour obtenir le certificat DEP Apple**</br>
Dans le portail Azure, choisissez **Plus de services**, entrez **Intune** dans la zone de texte, puis choisissez **Autres** > **Intune**. Dans le panneau Intune, choisissez **Inscrire des appareils** > **Jeton DEP Apple**, puis suivez les étapes numérotées dans le portail Azure, qui sont présentées ci-dessous.

**Étape 1. Téléchargez un certificat de clé publique Intune nécessaire à la création d’un jeton DEP Apple.**<br>
Sélectionnez **Télécharger votre clé publique** pour télécharger et enregistrer le fichier de clé de chiffrement (.pem) en local. Le fichier .pem est utilisé pour demander un certificat de relation d'approbation à partir du portail du programme d'inscription d'appareils d'Apple.

**Étape 2 : Téléchargez un jeton DEP Apple à partir du site web Apple approprié.**<br>
Sélectionnez [Créer un jeton DEP via les programmes de déploiement Apple](https://deploy.apple.com) (https://deploy.apple.com) et connectez-vous avec votre ID Apple d’entreprise. Vous devez utiliser cet ID Apple pour renouveler votre jeton DEP.

   1.  Dans le [portail du Programme d’inscription d’appareils](https://deploy.apple.com), accédez à **Programme d’inscription d’appareils** &gt; **Gérer les serveurs**, puis choisissez **Ajouter un serveur MDM**.

   2.  Entrez le **Nom du serveur MDM**, puis choisissez **Suivant**. Le nom du serveur vous permet d’identifier le serveur de gestion des appareils mobiles (MDM) uniquement. Il ne s’agit pas du nom ou de l’URL du serveur Microsoft Intune.

   3.  La boîte de dialogue **Ajouter&lt;nom_serveur&gt;** s’ouvre. Choisissez **Choisir un fichier** pour charger le fichier .pem, puis choisissez **Suivant**.

   4.  La boîte de dialogue **Ajouter&lt;nom_serveur&gt;** affiche un lien **Votre jeton de serveur**. Téléchargez le fichier de jeton de serveur (.p7m) sur votre ordinateur, puis choisissez **Terminé**.

    Ce fichier de certificat (.p7m) est utilisé pour établir une relation d'approbation entre le serveur Intune et le serveur du programme d'inscription d'appareils d'Apple.

**Étape 3 : Entrez l’ID Apple utilisé pour créer votre jeton DEP Apple. Cet ID peut être utilisé pour renouveler votre jeton DEP Apple.**

**Étape 4 :. Accédez à votre jeton DEP Apple à télécharger. Intune se synchronise automatiquement avec votre compte DEP.**<br>
Accédez au fichier du certificat (.pem), choisissez **Ouvrir**, puis **Télécharger**. Avec le certificat Push, Intune peut inscrire et gérer des appareils iOS en envoyant la stratégie aux appareils mobiles inscrits.



<!--HONumber=Feb17_HO1-->


