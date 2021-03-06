---
title: Profils de provisionnement d’applications iOS dans Microsoft Intune
titlesuffix: ''
description: Intune vous fournit les outils nécessaires pour affecter de manière proactive un nouveau profil de provisionnement aux appareils dont les applications arrivent à expiration.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/23/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: bbc3ba4a-df48-4aeb-988b-69a177764e3a
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d6394af9affd5087aaf26489be4b49e84568d6e1
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2018
---
# <a name="use-ios-app-provisioning-profiles-to-prevent-your-apps-from-expiring"></a>Utiliser les profils de provisionnement d’application iOS pour empêcher l’expiration de vos applications

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

## <a name="introduction"></a>Introduction

Les applications métier Apple iOS affectées aux iPhone et iPad intègrent un profil de provisionnement et du code signé avec un certificat. Lorsque l’application iOS s’exécute, iOS confirme son intégrité et applique les stratégies définies par le profil de configuration. Les validations suivantes se produisent :

- **Intégrité du fichier d’installation** : iOS compare les détails des applications avec la clé publique du certificat de signature d’entreprise. Si ces éléments diffèrent, le contenu de l’application est susceptible d’avoir changé. L’application n’est pas autorisée à s’exécuter.
- **Mise en œuvre des fonctionnalités** : iOS tente d’appliquer les fonctionnalités de l’application à partir du profil de configuration d’entreprise (il ne s’agit pas de profils de configuration de développeurs) inclus dans le fichier d’installation de l’application (.ipa).


Le certificat de signature d’entreprise que vous utilisez pour signer des applications dure généralement trois ans. Toutefois, le profil de configuration expire au bout d’1 an. Tant que le certificat est toujours valide, Intune vous offre les outils pour affecter de façon proactive un nouveau profil de configuration aux appareils qui disposent d’applications arrivant prochainement à expiration.
Après l’expiration du certificat, vous devez à nouveau signer l’application avec un nouveau certificat et incorporer un nouveau profil de configuration avec la clé du nouveau certificat.

En tant qu’administrateur, vous pouvez inclure et exclure des groupes de sécurité pour affecter une configuration de provisionnement d’application iOS. Par exemple, vous pouvez affecter une configuration de provisionnement d’application iOS à tous les utilisateurs, et exclure un groupe composé de cadres de direction.

## <a name="how-to-create-an-ios-mobile-app-provisioning-profile"></a>Comment créer un profil de configuration d’application mobile iOS

1. Connectez-vous au [portail Azure](https://portal.azure.com).
2. Choisissez **Tous les services** > **Intune**. Intune se trouve dans la section **Surveillance + Gestion**.
3. Dans le volet **Intune**, choisissez **Applications mobiles**.
1.  Dans la charge de travail **Applications mobiles**, choisissez **Gérer** > **Profils de provisionnement d’application iOS**.
2.  Dans le volet de la liste des profils, sélectionnez **Créer un profil**.
3. Dans le volet **Créer un profil**, configurez les valeurs suivantes :
    - **Nom** : nommez ce profil de configuration mobile.
    - **Description** : vous pouvez également fournir une description de la stratégie (facultatif).
    - **Charger le fichier de profil** : choisissez **Importer**, puis un fichier de profil de configuration mobile Apple (avec l’extension **.mobileprovision**) que vous avez téléchargé depuis le site web Apple Developer.
4. Quand vous avez terminé, choisissez **Créer**.

## <a name="next-steps"></a>Étapes suivantes

Affectez le profil aux appareils iOS requis. Pour plus d’informations, suivez les étapes de [Guide pratique pour attribuer des profils d’appareil](device-profile-assign.md).
