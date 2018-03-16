---
title: "Obtenir un certificat Push MDM Apple"
titlesuffix: Microsoft Intune
description: "Découvrez la procédure permettant d’obtenir un certificat Push MDM Apple pour gérer les appareils iOS avec Intune."
keywords: 
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 1/29/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6f67fcd2-5682-4f9c-8d74-d4ab69dc978c
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ed6ae1812e49fa0ceda3079d25afd92ceeac01bd
ms.sourcegitcommit: aafed032492c1b5861d7097a335f9bbb29ce3221
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/02/2018
---
# <a name="get-an-apple-mdm-push-certificate"></a>Obtenir un certificat Push MDM Apple

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Intune permet la gestion des appareils mobiles (MDM) pour les iPad, iPhone et ordinateurs Mac et permet aux utilisateurs d’accéder à la messagerie et aux applications de l’entreprise. Intune requiert un certificat Push MDM pour qu’Intune puisse gérer les appareils iOS et Mac. Une fois le certificat ajouté à Intune, vos utilisateurs peuvent installer l’application Portail d’entreprise pour inscrire leurs appareils. Vous pouvez également configurer la gestion des appareils iOS d’entreprise avec le programme DEP d’Apple ou inscrire des appareils à l’aide d’Apple Configurator, par exemple. Pour plus d’informations sur les options d’inscription, consultez [Choisir comment inscrire des appareils iOS](enrollment-method-choose-ios.md).

## <a name="steps-to-get-your-certificate"></a>Procédure pour obtenir le certificat
Dans le [portail Azure](https://portal.azure.com), choisissez **Inscription d’appareil** > **Inscription Apple** > **Certificat Push MDM Apple**, puis suivez les étapes ci-après dans le [portail Azure](https://portal.azure.com).

**Étape 1. Téléchargez la demande de signature de certificat Intune requise pour créer un certificat Push MDM Apple.**<br>
Sélectionnez **Télécharger votre CSR** pour télécharger et enregistrer le fichier de demande en local. Le fichier est utilisé pour demander un certificat de relation d’approbation à partir du portail Apple Push Certificates.

  ![Écran Configurer le certificat Push MDM avec Push MDM non configuré.](./media/create-mdm-push-certificate.png)

**Étape 2. Créez un certificat Push MDM Apple.**<br>
Sélectionnez **Créer votre certificat Push MDM** pour accéder au portail Apple Push Certificates. Connectez-vous avec votre identifiant Apple d’entreprise, puis cliquez sur **Créer un certificat**. Sélectionnez **Choisir un fichier** et accédez au fichier de demande de signature de certificat, puis choisissez **Charger**. Dans la page Confirmation, choisissez **Télécharger** pour télécharger le fichier de certificat (.pem), puis enregistrez-le localement.

> [!NOTE]
> Le certificat est associé à l’identifiant Apple utilisé pour le créer. Bonne pratique : utilisez un identifiant Apple d’entreprise pour les tâches de gestion. N’utilisez jamais un identifiant Apple personnel.

**Étape 3. Entrez l’identifiant Apple utilisé pour créer votre certificat Push MDM Apple.**<br>
Notez cet identifiant qui vous servira quand vous devrez renouveler ce certificat.

**Étape 4 :. Accédez à votre certificat Push MDM Apple à télécharger.**<br>
Accédez au fichier du certificat (.pem), choisissez **Ouvrir**, puis **Télécharger**. Avec le certificat Push, Intune peut inscrire et gérer des appareils Apple.

## <a name="renew-apple-mdm-push-certificate"></a>Renouveler un certificat Push MDM Apple
Le certificat Push MDM Apple est valide pendant un an et doit être renouvelé tous les ans pour assurer la gestion des appareils iOS et macOS. Si votre certificat a expiré, les appareils Apple inscrits ne peuvent pas être contactés.

Le certificat est associé à l’identifiant Apple utilisé pour le créer. Renouvelez le certificat Push MDM avec le même identifiant Apple utilisé pour le créer.

1. Dans le [portail Azure](https://portal.azure.com), choisissez **Inscription d’appareil** > **Inscription Apple**, puis **Certificat Push MDM Apple**.
2. Choisissez **Télécharger votre CSR** pour télécharger et enregistrer le fichier de demande en local. Le fichier est utilisé pour demander un certificat de relation d’approbation à partir du portail Apple Push Certificates.
3. Sélectionnez **Créer votre certificat Push MDM** pour accéder au portail Apple Push Certificates. Recherchez le certificat que vous souhaitez renouveler et sélectionnez **Renouveler**.
4. Dans l’écran **Renouveler le certificat Push**, ajoutez une note qui vous permettra d’identifier le certificat par la suite, sélectionnez **Choisir un fichier** pour accéder au nouveau fichier de demande que vous avez téléchargé, puis choisissez **Charger**.
   > [!TIP]
   > Un certificat peut être identifié par son UID. Examinez **l’ID d’objet** dans les détails du certificat pour trouver la partie GUID de l’UID. Sinon, sur un appareil iOS inscrit, accédez à **Settings** > **General** > **Device** **Management** > **Management Profile** > **More Details** > **Management Profile** (Paramètres, Général, Appareil, Gestion, Profil de gestion, Plus de détails, Profil de gestion). La deuxième ligne, **Topic** (Rubrique), contient le GUID unique que vous pouvez associer au certificat dans le portail Apple Push Certificates.
 
6. Dans l’écran **Confirmation**, sélectionnez **Télécharger** et enregistrez le fichier .pem localement.
7. Dans le [portail Azure](https://portal.azure.com), sélectionnez l’icône de navigation **Certificat Push MDM Apple**, sélectionnez le fichier .pem téléchargé à partir d’Apple, puis choisissez **Charger**.

Votre certificat Push MDM Apple apparaît **Actif** et valide pendant 365 jours.
