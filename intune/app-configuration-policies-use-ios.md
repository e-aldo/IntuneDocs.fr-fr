---
title: "Guide pratique d’utilisation des stratégies de configuration d’application Intune pour iOS"
titleSuffix: Intune on Azure
description: "Apprenez à utiliser les stratégies de configuration d’application pour fournir des données de configuration à une application iOS lorsqu’elle est exécutée."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 07/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c9163693-d748-46e0-842a-d9ba113ae5a8
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0cbcf70af17ba7690f54196790da04becd8ba1eb
ms.sourcegitcommit: 388c5f59bc992375ac63968fd7330af5d84a1348
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/12/2017
---
# <a name="how-to-use-microsoft-intune-app-configuration-policies-for-ios"></a>Guide pratique pour utiliser des stratégies de configuration d’application Microsoft Intune pour iOS

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Utilisez des stratégies de configuration des applications dans Microsoft Intune pour fournir les paramètres nécessaires quand les utilisateurs exécutent une application iOS. Par exemple, une application peut exiger que les utilisateurs spécifient les paramètres suivants :

-   Un numéro de port personnalisé.

-   Des paramètres de langue.

-   Des paramètres de sécurité.

-   Des paramètres de personnalisation comme le logo de l’entreprise.

Si les utilisateurs n’entrent pas correctement ces paramètres, cela peut occasionner plus de travail à votre assistance technique et ralentir l’adoption des nouvelles applications.

Les stratégies de configuration des applications peuvent vous aider à éliminer ces problèmes en vous permettant d’affecter ces paramètres dans une stratégie avant que les utilisateurs exécutent l’application. Les paramètres sont alors fournis automatiquement, les utilisateurs n’ont aucune action à effectuer.

Vous n’affectez pas ces stratégies directement sur les appareils et utilisateurs. Vous associez plutôt une stratégie à une application que vous affectez ensuite. Les paramètres de stratégie sont utilisés chaque fois que l’application les vérifie (en général, lors de sa première exécution).

> [!TIP]
> Ce type de stratégie est disponible uniquement pour les appareils exécutant iOS 8.0 ou version ultérieure. Elle prend en charge les types d’installation d’application suivants :
>
> -   **Application iOS gérée à partir de l’App Store**
> -   **Package d'application pour iOS**
>
> Pour plus d’informations sur les types d’installation d’application, consultez [Guide pratique pour ajouter une application à Microsoft Intune](apps-add.md).

## <a name="create-an-app-configuration-policy"></a>Créer une stratégie de configuration des applications
1.  Connectez-vous au portail Azure.
2.  Choisissez **Plus de Services** > **Surveillance + Gestion** > **Intune**.
3.  Dans le panneau **Intune**, choisissez **Applications mobiles**.
4.  Dans la charge de travail **Applications mobiles**, choisissez **gérer** > **Stratégies de configuration d’application**.
5.  Dans le panneau de liste de stratégies, choisissez **Ajouter**.
6.  Dans le panneau **Ajouter une stratégie de configuration**, indiquez un **nom** et éventuellement une **description** pour la stratégie de configuration d’application.
7.  Pour **Type d'inscription de l'appareil**, choisissez parmi :
    - **Inscrit dans Intune** : pour les applications qui intègrent le Kit de développement logiciel (SDK) d’application Intune et qui sont gérées par Intune.
    - **Non inscrit dans Intune** : pour les applications qui intègrent le Kit de développement logiciel (SDK) d’application Intune et qui ne sont pas gérées par Intune, ou qui sont gérées par une autre solution.
8.  Pour **Plateforme**, choisissez **iOS** (pour les appareils inscrits dans Intune uniquement)
9.  Choisissez **Application associée**, puis, dans le panneau **Application associée**, choisissez l’application gérée pour laquelle vous souhaitez appliquer la configuration.
10. Dans le panneau **Ajouter une stratégie de configuration**, choisissez **Paramètres de configuration**
11. Dans le panneau **Paramètres de configuration**, choisissez la façon dont vous souhaitez spécifier les valeurs XML qui composent le profil de configuration à partir de :
    - **Entrer des données XML** (pour les appareils inscrits dans Intune uniquement) : entrez ou collez une liste de propriétés XML contenant les paramètres de configuration d’application souhaités. Le format de la liste de propriétés XML varie en fonction de l’application que vous configurez. Pour plus d’informations sur le format exact à utiliser, contactez le fournisseur de l’application.
Intune vérifie que le format du XML entré est valide. Il ne vérifie pas que la liste de propriétés XML fonctionne avec l’application à laquelle elle est associée.
Pour en savoir plus sur les listes de propriétés XML, consultez [Understanding XML Property Lists](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/PropertyLists/UnderstandXMLPlist/UnderstandXMLPlist.html) sur le site iOS Developer Library.
    - **Utiliser le concepteur de configuration** (que l’appareil soit inscrit ou non dans Intune) : vous permet de spécifier les paires clé / valeur XML directement dans le portail.
11. Lorsque vous avez terminé, revenez au panneau **Ajouter une stratégie de configuration** et appuyez sur **Créer**.

La stratégie est créée et s’affiche dans le panneau de liste des stratégies.



>[!Note]
>Vous pouvez utiliser le [Kit de développement logiciel (SDK) d’application Intune](https://docs.microsoft.com/intune/app-sdk-ios) pour préparer les applications métier qui seront gérées par les stratégies de protection des applications Intune et les stratégies de configuration d’applications, que l’appareil soit inscrit ou non dans Intune. Par exemple, vous pouvez utiliser une stratégie de configuration d’applications afin de configurer les URL autorisées et bloquées pour [Intune Managed Browser](app-configuration-managed-browser.md). Une fois qu’une application est compatible avec ces stratégies, vous pouvez la configurer à l’aide d’une stratégie.


Quand l’application affectée est exécutée sur un appareil, elle s’exécute avec les paramètres que vous avez configurés dans la stratégie de configuration des applications.
Consultez la documentation de l’application que vous configurez pour plus d’informations sur ce qui se passe si une ou plusieurs stratégies de configuration d’applications sont en conflit.

>[!Tip]
>En outre, vous pouvez utiliser l’API Graph pour accomplir ces tâches. Pour plus d’informations, consultez [Configuration ciblée de gestion des applications mobiles de référence pour API Graph](https://graph.microsoft.io/docs/api-reference/beta/api/intune_mam_targetedmanagedappconfiguration_create).


## <a name="information-about-the-xml-file-format"></a>Informations sur le format de fichier XML

Intune prend en charge les types de données suivants dans une liste de propriétés :

- &lt;integer&gt;
- &lt;real&gt;
- &lt;string&gt;
- &lt;array&gt;
- &lt;dict&gt;
- &lt;true /&gt; ou &lt;false /&gt;

Pour plus d’informations sur les types de données, consultez l’article sur les [listes de propriétés](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/PropertyLists/AboutPropertyLists/AboutPropertyLists.html) sur le site iOS Developer Library.

De plus, Intune prend en charge les types de jetons suivants dans la liste de propriétés :
- \{\{userprincipalname\}\} - (Exemple : **John@contoso.com**)
- \{\{mail\}\} - (Exemple : **John@contoso.com**)
- \{\{partialupn\}\} - (Exemple : **John**)
- \{\{accountid\}\} - (Exemple : **fc0dc142-71d8-4b12-bbea-bae2a8514c81**)
- \{\{deviceid\}\} - (Exemple : **b9841cd9-9843-405f-be28-b2265c59ef97**)
- \{\{userid\}\} - (Exemple : **3ec2c00f-b125-4519-acf0-302ac3761822**)
- \{\{username\}\} - (Exemple : **John Doe**)
- \{\{serialnumber\}\} - (Exemple : **F4KN99ZUG5V2**) pour les appareils iOS
- \{\{serialnumberlast4digits\}\} - (Exemple : **G5V2**) pour les appareils iOS

Les caractères \{\{ et \}\} sont utilisés uniquement par les types de jetons. Ils ne doivent pas être utilisés à d’autres fins.

## <a name="example-format-for-an-app-configuration-xml-file"></a>Exemple de format de fichier XML de configuration d’application

Quand vous créez un fichier de configuration d’application, vous pouvez spécifier une ou plusieurs des valeurs suivantes à l’aide de ce format :

```
<dict>
  <key>userprincipalname</key>
  <string>{{userprincipalname}}</string>
  <key>mail</key>
  <string>{{mail}}</string>
  <key>partialupn</key>
  <string>{{partialupn}}</string>
  <key>accountid</key>
  <string>{{accountid}}</string>
  <key>deviceid</key>
  <string>{{deviceid}}</string>
  <key>userid</key>
  <string>{{userid}}</string>
  <key>username</key>
  <string>{{username}}</string>
  <key>serialnumber</key>
  <string>{{serialnumber}}</string>
  <key>serialnumberlast4digits</key>
  <string>{{serialnumberlast4digits}}</string>
  <key>udidlast4digits</key>
  <string>{{udidlast4digits}}</string>
</dict>

```

## <a name="next-steps"></a>Étapes suivantes

Continuez à [affecter](apps-deploy.md) et à [surveiller](apps-monitor.md) l’application comme d’habitude.