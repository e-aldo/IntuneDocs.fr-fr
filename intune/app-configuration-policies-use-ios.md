---
title: "Ajouter des stratégies de configuration d’applications pour les appareils iOS gérés | Microsoft Docs"
titlesuffix: Azure portal
description: "Apprenez à utiliser les stratégies de configuration d’applications pour fournir des données de configuration à une application iOS quand elle est exécutée."
keywords: 
author: erikre
ms.author: erikre
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c9163693-d748-46e0-842a-d9ba113ae5a8
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: a39b2d120a804d32b93b7a240af246327514b1b7
ms.sourcegitcommit: 67ec0606c5440cffa7734f4eefeb7121e9d4f94f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/08/2017
---
# <a name="add-app-configuration-policies-for-managed-ios-devices"></a>Ajouter des stratégies de configuration d’applications pour les appareils iOS gérés | Microsoft Docs

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Utilisez des stratégies de configuration d’applications dans Microsoft Intune pour fournir des paramètres quand les utilisateurs exécutent une application iOS. Vous n’affectez pas ces stratégies directement sur les appareils et utilisateurs. Vous associez plutôt une stratégie à une application que vous affectez ensuite. Les paramètres de stratégie sont utilisés quand l’application les vérifie, en général, à sa première exécution.

> [!TIP]
> Ce type de stratégie est disponible uniquement pour les appareils exécutant iOS 8.0 ou version ultérieure. Elle prend en charge les types d’installation d’application suivants :
>
> -   **Application iOS gérée à partir de l’App Store**
> -   **Package d'application pour iOS**
>
> Pour plus d’informations sur les types d’installation d’application, consultez [Guide pratique pour ajouter une application à Microsoft Intune](apps-add.md).

## <a name="create-an-app-configuration-policy"></a>Créer une stratégie de configuration des applications

1. Connectez-vous au portail Azure.
2. Choisissez **Autres services** > **Surveillance + Gestion** + **Intune**.
3. Choisissez la charge de travail **Applications mobiles**.
4. Choisissez **Stratégies de configuration des applications** dans le groupe **Gérer**, puis choisissez **Ajouter**.
5. Définissez les détails suivants :
    - **Nom**<br>
      Nom du profil qui s’affiche dans le portail Azure.
    - **Description**<br>
      Description du profil qui s’affiche dans le portail Azure.
    - **Type d’inscription de l’appareil**<br>
      Choisissez **Appareils gérés**.
6. Sélectionnez **iOS** comme **Plateforme**.
7.  Choisissez **Application associée**. Ensuite, dans le panneau **Application associée**, choisissez l’application gérée pour laquelle vous souhaitez appliquer la configuration.
8.  Dans le panneau **Ajouter une stratégie de configuration**, choisissez **Paramètres de configuration**.
9. Sélectionnez **Format des paramètres de configuration**. Sélectionnez l’un des paramètres suivants :
    - **[Utiliser le concepteur de configuration](#Use-the-configuration-designer)**
    - **[Entrer des données XML](#enter-xml-data)**
10. Choisissez **OK**, puis **Ajouter**.

## <a name="use-configuration-designer"></a>Utiliser le concepteur de configuration

Vous pouvez utiliser le concepteur de configuration pour les applications sur les appareils qui sont inscrits ou non inscrits dans Intune. Le concepteur vous permet de configurer des valeurs et des clés de configuration spécifiques. Vous devez également spécifier le type de données pour chaque valeur. Les paramètres sont automatiquement fournis aux applications lors de leur installation.

### <a name="add-a-setting"></a>Ajouter un paramètre

1. Pour chaque clé et valeur de la configuration, définissez les éléments suivants :
   - **Clé de configuration**<br>
     Clé qui identifie de façon unique la configuration des paramètres spécifique.
   - **Type de valeur**<br>
     Type de données de la valeur de configuration. Les types incluent Integer, Real, String ou Boolean.
   - **Valeur de configuration**<br>
     Valeur de la configuration.
2. Choisissez **OK** pour définir vos paramètres de configuration.

### <a name="delete-a-setting"></a>Supprimer un paramètre

1. Choisissez le bouton de sélection (**...** ) en regard du paramètre.
2. Sélectionnez **Supprimer**.

Les caractères \{\{ et \}\} sont utilisés uniquement par les types de jetons. Ils ne doivent pas être utilisés à d’autres fins.

## <a name="enter-xml-data"></a>Entrer des données XML

Vous pouvez taper ou coller une liste de propriétés XML contenant les paramètres de configuration d’application pour les appareils inscrits dans Intune. Le format de la liste de propriétés XML varie en fonction de l’application que vous configurez. Pour plus d’informations sur le format exact à utiliser, contactez le fournisseur de l’application.

Intune valide le format XML. Toutefois, il ne vérifie pas que la liste de propriétés XML (PList) fonctionne avec l’application cible.

Pour en savoir plus sur les listes de propriétés XML :

  -  Consultez [Configurer des applications iOS avec des stratégies de configuration d’applications mobiles dans Microsoft Intune](/intune-classic/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune).
  -  Reportez-vous à [Understand XML Property Lists](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/PropertyLists/UnderstandXMLPlist/UnderstandXMLPlist.html) (Présentation des listes de propriétés XML) sur le site iOS Developer Library.

### <a name="example-format-for-an-app-configuration-xml-file"></a>Exemple de format de fichier XML de configuration d’application

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
### <a name="supported-xml-plist-data-types"></a>Types de données PList XML pris en charge

Intune prend en charge les types de données suivants dans une liste de propriétés :

- &lt;integer&gt;
- &lt;real&gt;
- &lt;string&gt;
- &lt;array&gt;
- &lt;dict&gt;
- &lt;true /&gt; ou &lt;false /&gt;

### <a name="tokens-used-in-the-property-list"></a>Jetons utilisés dans la liste des propriétés

De plus, Intune prend en charge les types de jetons suivants dans la liste de propriétés :
- \{\{userprincipalname\}\} : par exemple, **John@contoso.com**
- \{\{mail\}\} : par exemple, **John@contoso.com**
- \{\{partialupn\}\} : par exemple, **John**
- \{\{accountid\}\} : par exemple, **fc0dc142-71d8-4b12-bbea-bae2a8514c81**
- \{\{deviceid\}\} : par exemple, **b9841cd9-9843-405f-be28-b2265c59ef97**
- \{\{userid\}\} : par exemple, **3ec2c00f-b125-4519-acf0-302ac3761822**
- \{\{username\}\} : par exemple, **John Doe**
- \{\{serialnumber\}\} : par exemple, **F4KN99ZUG5V2** (pour les appareils iOS)
- \{\{serialnumberlast4digits\}\} : par exemple, **G5V2** (pour les appareils iOS)

## <a name="next-steps"></a>Étapes suivantes

Continuez à [affecter](apps-deploy.md) et à [surveiller](apps-monitor.md) l’application comme d’habitude.