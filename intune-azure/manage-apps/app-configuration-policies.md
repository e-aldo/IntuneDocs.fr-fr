---
title: "Guide pratique d’utilisation des stratégies de configuration d’application Intune"
titleSuffix: Intune Azure preview
description: "Préversion Intune Azure : Apprenez à utiliser les stratégies de configuration d’application pour fournir des données de configuration à une application iOS lorsqu’elle est exécutée."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c9163693-d748-46e0-842a-d9ba113ae5a8
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: 73360154765d53fe1f42e4e97699ad9385bfda6f
ms.lasthandoff: 02/18/2017

---

# <a name="how-to-use-microsoft-intune-app-configuration-policies"></a>Guide pratique pour utiliser des stratégies de configuration d’application Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Utilisez des stratégies de configuration des applications dans Microsoft Intune pour fournir les paramètres pouvant être nécessaires quand les utilisateurs exécutent une application. Par exemple, une application peut exiger que les utilisateurs spécifient les paramètres suivants :

-   Un numéro de port personnalisé.

-   Des paramètres de langue.

-   Des paramètres de sécurité.

-   Des paramètres de personnalisation comme le logo de l’entreprise.

Si les utilisateurs n’entrent pas correctement ces paramètres, ils occasionneront plus de travail à votre assistance technique et mettront plus de temps à adopter les nouvelles applications.

Les stratégies de configuration des applications peuvent vous aider à éliminer ces problèmes en vous permettant d’affecter ces paramètres dans une stratégie avant que les utilisateurs exécutent l’application. Les paramètres sont alors fournis automatiquement, les utilisateurs n’ont aucune action à effectuer.

Vous n’affectez pas ces stratégies directement sur les appareils et utilisateurs. Vous associez plutôt la stratégie à une application, que vous déployez ensuite. Les paramètres de stratégie sont utilisés chaque fois que l’application les vérifie (en général, lors de sa première exécution).

> [!TIP]
> Ce type de stratégie est disponible uniquement pour les appareils exécutant iOS 8.0 ou version ultérieure. Elle prend en charge les types d’installation d’application suivants :
>
> -   **Application iOS gérée à partir de l’App Store**
> -   **Package d'application pour iOS**
>
> Pour plus d’informations sur les types d’installation d’application, consultez [Guide pratique pour ajouter une application à Microsoft Intune](/intune-azure/manage-apps/add-apps).

## <a name="create-an-app-configuration-policy"></a>Créer une stratégie de configuration des applications

1. Connectez-vous au portail Azure.
2. Choisissez **Plus de services** > **Autres** > **Intune**.
3. Dans le panneau **Intune**, choisissez **Gérer les applications**.
1.  Dans la charge de travail **Gérer les applications**, choisissez **gérer** > **Stratégies de configuration d’application**.

2.  Dans le panneau de liste de stratégies, choisissez **Ajouter**.

3.  Dans le panneau **Ajouter une stratégie de configuration**, indiquez un nom et éventuellement une description pour la stratégie de configuration d’application.
4.  Choisissez **Application associée**, puis, dans le panneau **Application associée**, choisissez l’application gérée pour laquelle vous souhaitez appliquer la configuration.
5.  Dans le panneau **Ajouter une stratégie de configuration**, choisissez **Paramètres de configuration** puis, dans le panneau Paramètres de configuration, choisissez la façon dont vous souhaitez spécifier les valeurs XML qui composent le profil de configuration à partir de :
    - **Entrer des données XML** : entrez ou collez une liste de propriétés XML contenant les paramètres de configuration d’application souhaités. Le format de la liste de propriétés XML varie en fonction de l’application que vous configurez. Pour plus d’informations sur le format exact à utiliser, contactez le fournisseur de l’application.
    Intune vérifie que le format du XML entré est valide. Il ne vérifie pas que la liste de propriétés XML fonctionne avec l’application à laquelle elle est associée.
    Pour en savoir plus sur les listes de propriétés XML, consultez [Understanding XML Property Lists](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/PropertyLists/UnderstandXMLPlist/UnderstandXMLPlist.html) sur le site iOS Developer Library.
    - **Utiliser le concepteur de configuration** : vous permet de spécifier les paires clé / valeur XML directement dans le portail.
8. Lorsque vous avez terminé, revenez au panneau **Ajouter une stratégie de configuration** et appuyez sur **Créer**.

La stratégie est créée et s’affiche dans le panneau de liste des stratégies.

Ensuite, continuez à [Affecter](deploy-apps.md) et [Surveiller](monitor-apps.md) l’application comme d’habitude.

Quand l’application affectée est exécutée sur un appareil, elle s’exécute avec les paramètres que vous avez configurés dans la stratégie de configuration des applications.

> [!TIP]
> Si une ou plusieurs stratégies de configuration des applications sont en conflit, aucune stratégie n’est appliquée.

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

