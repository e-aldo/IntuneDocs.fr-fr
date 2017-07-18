---
title: "Guide pratique d’utilisation des stratégies de configuration d’application Intune pour iOS"
titleSuffix: Intune on Azure
description: "Apprenez à utiliser les stratégies de configuration d’application pour fournir des données de configuration à une application iOS lorsqu’elle est exécutée."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 06/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c9163693-d748-46e0-842a-d9ba113ae5a8
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 112f60ff208c27825ddd0f4c812535b255894333
ms.sourcegitcommit: fd2e8f6f8761fdd65b49f6e4223c2d4a013dd6d9
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/03/2017
---
# <a name="how-to-use-microsoft-intune-app-configuration-policies-for-ios"></a>Guide pratique pour utiliser des stratégies de configuration d’application Microsoft Intune pour iOS

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Utilisez des stratégies de configuration des applications dans Microsoft Intune pour fournir les paramètres pouvant être nécessaires quand les utilisateurs exécutent une application iOS. Par exemple, une application peut exiger que les utilisateurs spécifient les paramètres suivants :

-   Un numéro de port personnalisé.

-   Des paramètres de langue.

-   Des paramètres de sécurité.

-   Des paramètres de personnalisation comme le logo de l’entreprise.

Si les utilisateurs n’entrent pas correctement ces paramètres, ils occasionneront plus de travail à votre assistance technique et mettront plus de temps à adopter les nouvelles applications.

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

1. Connectez-vous au portail Azure.
2. Choisissez **Plus de Services** > **Surveillance + Gestion** > **Intune**.
3. Dans le panneau **Intune**, choisissez **Applications mobiles**.
1.  Dans la charge de travail **Applications mobiles**, choisissez **gérer** > **Stratégies de configuration d’application**.

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

Ensuite, continuez à [Affecter](apps-deploy.md) et [Surveiller](apps-monitor.md) l’application comme d’habitude.

Quand l’application affectée est exécutée sur un appareil, elle s’exécute avec les paramètres que vous avez configurés dans la stratégie de configuration des applications.

> [!TIP]
> Si une ou plusieurs stratégies de configuration des applications sont en conflit, aucune stratégie n’est appliquée.

## <a name="create-a-mam-targeted-configuration-policy"></a>Créer une stratégie de configuration de gestion des applications mobiles ciblée
La configuration ciblée de gestion des applications mobiles permet à une application de recevoir des données de configuration par le biais du SDK d’application Intune. Les variantes et le format de ces données doivent être définis et communiqués aux clients Intune par le propriétaire/développeur d’application. Les administrateurs Intune peuvent cibler et déployer des données de configuration par le biais de la console Intune Azure. Les données de configuration de gestion des applications mobiles ciblée peuvent être fournies via le service de gestion des applications mobiles aux applications compatibles avec la gestion des applications mobiles sans inscription. Par exemple, [Intune Managed Browser](https://docs.microsoft.com/intune/app-configuration-managed-browser) a une liste d’URL autorisées/bloquées. Les données de configuration d’application sont envoyées via notre service de gestion des applications mobiles directement à l’application au lieu de passer par le canal de gestion des appareils mobiles. Les [stratégies de configuration d’application de gestion des appareils mobiles](https://docs.microsoft.com/intune/app-configuration-policies-use-ios#create-an-app-configuration-policy) sont la solution native via la gestion des appareils mobiles. La principale différence avec la configuration ciblée de la gestion des applications mobiles est que l’appareil sur lequel s’exécute l’application n’a pas besoin être inscrit dans la gestion des appareils mobiles. La configuration ciblée de la gestion des applications mobiles est disponible sur iOS et Android. Pour iOS, l’application doit intégrer le SDK d’application Intune pour iOS (v 7.0.1) et participer aux paramètres de configuration d’application. Les étapes de création d’une stratégie de configuration ciblée de gestion des applications mobiles sont les suivantes : 

1. Connectez-vous au **portail Azure**.

2. Choisissez **Intune > Applications mobiles - Stratégies de configuration des applications**.

3. Dans le panneau **Stratégies de configuration des applications**, choisissez **Ajouter**.

4. Saisissez un **Nom** et éventuellement une **Description** pour les paramètres de configuration d’application, et choisissez **Non inscrit avec Intune**.

5. Choisissez **Sélectionner les applications requises** puis, dans le panneau d’applications **Ciblé**, choisissez les applications pour les plateformes prévues. <br>
**Remarque :** pour les applications métier, sélectionnez **Autres applications**. Saisissez l’ID de package pour votre application.

6. Choisissez **OK** pour revenir au panneau **Ajouter une configuration d’application**.

7. Choisissez **Définir la configuration**. Dans le panneau **Configuration**, vous définissez des paires clé / valeur pour fournir des configurations.

8. Une fois que vous avez terminé, choisissez **Enregistrer**.

9. Sur le **Panneau de configuration Ajouter une application**, choisissez **Créer**.

La nouvelle configuration est créée et s’affiche dans le panneau de configuration des applications.

Ensuite, continuez à [Affecter](apps-deploy.md) et [Surveiller](apps-monitor.md) l’application comme d’habitude.

Quand l’application affectée (intégrée avec le SDK d’application Intune) est exécutée sur un appareil, elle s’exécute avec les paramètres que vous avez configurés dans la stratégie de configuration ciblée de gestion des applications mobiles. L’application affectée doit avoir intégré à la version prise en charge du SDK d’application Intune. Pour plus d’informations sur les conditions requises de développement d’application pour utiliser les stratégies de configuration ciblée de gestion des applications mobiles, consultez [Guide d’intégration du SDK d’application Intune iOS](https://docs.microsoft.com/intune/app-sdk-ios).

Pour plus d’informations sur les fonctionnalités de notre API Graph en ce qui concerne les valeurs de configuration ciblée de gestion des applications mobiles, consultez [Configuration ciblée de gestion des applications mobiles de référence pour API Graph](https://graph.microsoft.io/docs/api-reference/beta/api/intune_mam_targetedmanagedappconfiguration_create).

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
