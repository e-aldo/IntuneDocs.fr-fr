---
title: "Obtenir un certificat Push MDM Apple | Version préliminaire d’Intune Azure | Microsoft Docs"
description: "Version préliminaire d’Intune Azure : découvrez la procédure permettant d’obtenir un certificat Push MDM Apple pour gérer les appareils iOS avec Intune."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6f67fcd2-5682-4f9c-8d74-d4ab69dc978c
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 08dad848a48adad7d9c6f0b5b3286f6550a266bd
ms.openlocfilehash: a6ac1074055892f5ec42fb4057e47e9349fb5a33
ms.lasthandoff: 02/15/2017


---

# <a name="get-an-apple-mdm-push-certificate"></a>Obtenir un certificat Push MDM Apple 

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Intune permet la gestion des appareils mobiles (MDM) pour les appareils iPad, iPhone et Mac OS X, et permet aux utilisateurs d’accéder à la messagerie et aux applications de l’entreprise. Intune requiert un certificat APNS (Apple Push Notification Service) pour gérer les appareils iOS et Mac. Une fois le certificat ajouté à Intune, vos utilisateurs peuvent installer l’application Portail d’entreprise pour inscrire leurs appareils, ou vous pouvez configurer la gestion des appareils iOS d’entreprise.

**Pour obtenir le certificat Push MDM Apple :**<br>
Dans le portail Azure, choisissez **Plus de services** > **Surveillance + gestion** > **Intune**. Dans le panneau Intune, choisissez **Inscrire des appareils** > **Certificat Push MDM Apple**, puis suivez les étapes numérotées dans le portail Azure, qui sont présentées ci-dessous.

**Étape 1. Téléchargez la demande de signature de certificat Intune requise pour créer un certificat Push MDM Apple.**<br>
Sélectionnez **Télécharger votre CSR** pour télécharger et enregistrer le fichier .csr en local. Le fichier .csr est utilisé pour demander un certificat de relation d'approbation à partir du portail Apple Push Certificates.

**Étape 2 : Créez un certificat Push MDM Apple.**<br>
Sélectionnez **Créer votre certificat Push MDM** pour accéder au portail Apple Push Certificates. Connectez-vous avec votre ID Apple d’entreprise pour créer le certificat Push à l’aide du fichier .csr. Après avoir choisi **Télécharger** sur le portail Apple Push Certificates, vous recevrez un fichier .json. Utilisez ce fichier pour le certificat Push. Terminez le téléchargement, revenez au portail Apple Push Certificate pour obtenir des certificats pour serveurs tiers, puis choisissez **Télécharger**. Téléchargez le certificat Push (fichier .pem) et enregistrez le fichier en local.
Remarque

**Étape 3 : Entrez l’ID Apple utilisé pour créer votre certificat Push MDM Apple.**

**Étape 4 :. Accédez à votre certificat Push MDM Apple à télécharger.**<br>
Accédez au fichier du certificat (.pem), choisissez **Ouvrir**, puis **Télécharger**. Avec le certificat Push, Intune peut inscrire et gérer des appareils iOS en envoyant la stratégie aux appareils mobiles inscrits.

