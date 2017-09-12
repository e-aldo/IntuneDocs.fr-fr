---
title: "Profils de configuration d’applications"
titlesuffix: Azure portal
description: "Intune vous offre les outils pour affecter de façon proactive un nouveau profil de configuration pour les appareils qui disposent d’applications arrivant prochainement à expiration."
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 05/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bbc3ba4a-df48-4aeb-988b-69a177764e3a
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: bc627198aa4f1a2f5ebb9116ba85758c4669158e
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/09/2017
---
# <a name="use-ios-mobile-provisioning-profiles-to-prevent-your-apps-from-expiring"></a>Utiliser les profils de configuration iOS mobile pour empêcher l’expiration de vos applications

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <a name="introduction"></a>Introduction

Les applications métier Apple iOS affectées aux iPhone et iPad intègrent un profil de configuration et du code signé avec un certificat. Lorsque l’application iOS s’exécute, iOS confirme son intégrité et applique les stratégies définies par le profil de configuration. Les validations suivantes se produisent :

- **Intégrité du fichier d’installation** : iOS compare les détails des applications avec la clé publique du certificat de signature d’entreprise. Si ces éléments diffèrent, le contenu de l’application est susceptible d’avoir changé ; celle-ci n’est pas autorisée à s’exécuter.
- **Mise en œuvre des fonctionnalités** : iOS tente d’appliquer les fonctionnalités de l’application à partir du profil de configuration d’entreprise (il ne s’agit pas de profils de configuration de développeurs) inclus dans le fichier d’installation de l’application (.ipa).


Le certificat de signature d’entreprise que vous utilisez pour signer des applications dure généralement trois ans. Toutefois, le profil de configuration expire au bout d’1 an. Tant que le certificat est toujours valide, Intune vous offre les outils pour affecter de façon proactive un nouveau profil de configuration aux appareils qui disposent d’applications arrivant prochainement à expiration.
Après l’expiration du certificat, vous devez à nouveau signer l’application avec un nouveau certificat et incorporer un nouveau profil de configuration avec la clé du nouveau certificat.


## <a name="how-to-create-an-ios-mobile-app-provisioning-profile"></a>Comment créer un profil de configuration d’application mobile iOS

1. Connectez-vous au portail Azure.
2. Choisissez **Plus de Services** > **Surveillance + Gestion** > **Intune**.
3. Dans le panneau **Intune**, choisissez **Applications mobiles**.
1.  Dans la charge de travail **Applications mobiles**, choisissez **Gérer** > **Profils de configuration iOS**.
2.  Dans le panneau de la liste des profils, sélectionnez **Créer un profil**.
3. Dans le panneau **Créer un profil**, configurez les valeurs suivantes :
    - **Nom** : nommez ce profil de configuration mobile.
    - **Description** : vous pouvez également fournir une description de la stratégie (facultatif).
    - **Charger le fichier de profil** : choisissez **Importer**, puis un fichier de profil de configuration mobile Apple (avec l’extension **.mobileprovision**) que vous avez téléchargé depuis le site web Apple Developer.
4. Quand vous avez terminé, choisissez **Créer**.

## <a name="next-steps"></a>Étapes suivantes

Affectez le profil aux appareils iOS requis. Pour plus d’informations, suivez les étapes de [Guide pratique pour attribuer des profils d’appareil](device-profile-assign.md).
