---
title: "Ajouter des stratégies de configuration pour les applications gérées sans inscription d’appareil | Microsoft Docs"
titlesuffix: Azure portal
description: "Découvrez comment utiliser des stratégies de configuration d’applications pour les applications gérées sans inscription d’appareil."
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: E61C1618-79D0-41A1-B61F-4123FB6672FC
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 750ce7dbb0dccf08757e076826e2d3650b6e6ab5
ms.sourcegitcommit: 67c037af31c1f167ec9b4f4baa754631c817e7d1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/01/2017
---
# <a name="add-app-configuration-policies-for-managed-apps-without-device-enrollment"></a>Ajouter des stratégies de configuration pour les applications gérées sans inscription d’appareil

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Vous pouvez utiliser des stratégies de configuration d’applications avec des applications gérées qui prennent en charge le SDK d’application Intune même sur les appareils qui ne sont pas inscrits. 

1. Connectez-vous au portail Azure.
2. Choisissez **Autres services** > **Surveillance + Gestion** + **Intune**.
3. Choisissez la charge de travail **Applications mobiles**.
4. Cliquez sur **Stratégies de configuration des applications** dans le groupe **Gérer**, puis cliquez sur **Ajouter**.
5. Définissez les détails suivants :
    - **Nom**  
      Nom du profil qui s’affiche dans le portail Azure.
    - **Description**  
      Description du profil qui s’affiche dans le portail Azure.
    - **Type d’inscription de l’appareil**  
      Choisissez **Gérer les applications**.
6. Sélectionnez **Application associée** pour choisir l’application que vous vous apprêtez à configurer. Sélectionnez l’application dans la liste d’applications que vous avez approuvées et synchronisées avec Intune.
7. Pour chaque paramètre de configuration pris en charge par l’application, tapez le **Nom** et la **Valeur**, puis cliquez sur les points de suspension (**...**).  
    Pour supprimer une configuration, cliquez sur les points de suspension (**...**), puis sélectionnez **Supprimer**.  
    Les applications compatibles avec le SDK d’application Intune prennent en charge les configurations de paires clé-valeur. Consultez la documentation de chaque application pour savoir quelles sont les configurations clé-valeur prises en charge.  
    Vous pouvez aussi utiliser des jetons qui sont renseignés dynamiquement avec les données générées par l’application.

## <a name="configuration-values-using-tokens"></a>Valeurs de configuration utilisant des jetons

Intune peut générer certains jetons et les envoyer à l’application gérée. Par exemple, si la configuration de votre application peut utiliser un paramètre d’e-mail, vous pouvez ajouter un e-mail dynamique à l’aide d’un jeton. Tapez le nom attendu par l’application dans le champ **Nom**, puis `\{\{mail\}\}` dans le champ **Valeur**.

Intune prend en charge les types de jetons suivants dans les paramètres de configuration :

- \{\{userprincipalname\}\} - (Exemple : **John@contoso.com**)
- \{\{mail\}\} - (Exemple : **John@contoso.com**)
- \{\{partialupn\}\} - (Exemple : **John**)
- \{\{accountid\}\} - (Exemple : **fc0dc142-71d8-4b12-bbea-bae2a8514c81**)
- \{\{deviceid\}\} - (Exemple : **b9841cd9-9843-405f-be28-b2265c59ef97**)
- \{\{userid\}\} - (Exemple : **3ec2c00f-b125-4519-acf0-302ac3761822**)
- \{\{username\}\} - (Exemple : **John Doe**)
- \{\{PrimarySMTPAddress\}\} - (Exemple : testuser@ad.domain.com) 


> [!Note]  
> Les caractères \{\{ et \}\} sont utilisés uniquement par les types de jetons. Ils ne doivent pas être utilisés à d’autres fins.

## <a name="next-steps"></a>Étapes suivantes

Continuez à [affecter](apps-deploy.md) et à [surveiller](apps-monitor.md) l’application comme d’habitude.