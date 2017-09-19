---
title: "Profils de configuration d’applications"
description: "Intune vous offre les outils pour déployer de façon proactive une nouvelle stratégie de profil de configuration pour les appareils qui disposent d’applications arrivant prochainement à expiration."
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 86fbe736-7bdb-4f5e-ae21-13c91eb2462c
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: fa78cdbe73f2cca1da011836cecacfdd47dc2291
ms.sourcegitcommit: 769db6599d5eb0e2cca537d0f60a5df9c9f05079
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/15/2017
---
# <a name="use-ios-mobile-provisioning-profile-policies-to-prevent-your-apps-from-expiring"></a>Utiliser les stratégies de profil de configuration iOS mobile pour empêcher l’expiration de vos applications

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Les applications métier Apple iOS déployées sur les iPhone et les iPad intègrent un profil de configuration et du code signé avec un certificat. Lorsque l’application iOS s’exécute, iOS confirme son intégrité et applique les stratégies définies par le profil de configuration. Les validations suivantes se produisent :

- **Intégrité du fichier d’installation** : iOS compare les détails des applications avec la clé publique du certificat de signature d’entreprise. Si ces éléments diffèrent, le contenu de l’application est susceptible d’avoir changé ; celle-ci n’est pas autorisée à s’exécuter.
- **Mise en œuvre des fonctionnalités** : iOS tente d’appliquer les fonctionnalités de l’application à partir du profil de configuration d’entreprise (il ne s’agit pas de profils de configuration de développeurs) inclus dans le fichier d’installation de l’application (.ipa).


Le certificat de signature d’entreprise que vous utilisez pour signer des applications dure généralement trois ans. Toutefois, le profil de configuration expire au bout d’1 an. Tant que le certificat est toujours valide, Intune vous offre les outils pour déployer de façon proactive une nouvelle stratégie de profil de configuration pour les appareils qui disposent d’applications arrivant prochainement à expiration.
Après l’expiration du certificat, vous devez à nouveau signer l’application avec un nouveau certificat et incorporer un nouveau profil de configuration avec la clé du nouveau certificat.



## <a name="how-to-find-out-when-a-line-of-business-app-will-expire"></a>Comment savoir quand une application métier va expirer ?

1. Dans la [console d’administration Microsoft Intune](https://manage.microsoft.com), choisissez **Applications** > **Applications**.
2. Dans la liste des applications, recherchez la colonne **Date d’expiration** pour consulter la date d’expiration de l’application. Vous pouvez également définir la liste déroulante **Filtres** sur **Expiré/sur le point d’expirer** pour afficher uniquement les applications requérant votre attention.

## <a name="how-to-create-an-ios-mobile-provisioning-profile-policy"></a>Comment créer une stratégie de profil de configuration d’application mobile iOS ?


1. Dans la [console d’administration Microsoft Intune](https://manage.microsoft.com), choisissez **Stratégie** > **Vue d’ensemble** > **Ajouter une stratégie**.
2. Dans la boîte de dialogue **Créer une nouvelle stratégie**, choisissez **iOS** > **Stratégie de profil de configuration mobile**, puis **Créer une stratégie**.
3. Sur la page **Général**, configurez les valeurs suivantes :
    - **Nom** : nommez cette stratégie de profil de configuration mobile.
    - **Description** : vous pouvez également fournir une description de la stratégie (facultatif).
    - **Fichier de configuration de profil** : cliquez sur **Importer**, puis choisissez un fichier de profil de configuration mobile Apple (avec l’extension **.mobileprovision**) que vous avez téléchargé depuis le site web Apple Developer.
4. Quand vous avez terminé, choisissez **Enregistrer la stratégie**.
5. Maintenant, déployez la stratégie pour les appareils iOS requis. Pour plus d’informations, consultez [Gérer des paramètres et des fonctionnalités sur vos appareils avec des stratégies Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).
