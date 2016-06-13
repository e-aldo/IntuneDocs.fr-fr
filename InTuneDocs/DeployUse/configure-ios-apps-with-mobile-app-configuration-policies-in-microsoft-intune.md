---
# required metadata

title: Configurer des applications iOS avec des stratégies de configuration des applications mobiles | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: fc6b645a-e837-4b2a-a10f-144065cbd8dd

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Configurer des applications iOS avec des stratégies de configuration des applications mobiles dans Microsoft Intune
Utilisez des stratégies de configuration des applications mobiles dans Microsoft Intune pour fournir les paramètres pouvant être nécessaires quand l’utilisateur exécute une application. Par exemple, une application peut nécessiter que l’utilisateur spécifie les paramètres suivants :

-   Un numéro de port personnalisé pendant son exécution

-   Paramètres de langue

-   Paramètres de sécurité

-   Paramètres de personnalisation comme le logo de l’entreprise

Si ces paramètres ne sont pas correctement entrés par l’utilisateur, non seulement la charge du support technique est alourdie, mais l’adoption de nouvelles applications est également ralentie.

Les stratégies de configuration des applications mobiles peuvent vous aider à éliminer ces problèmes en vous permettant de déployer ces paramètres dans une stratégie avant que les utilisateurs exécutent l’application. Les paramètres sont ensuite fournis automatiquement, et l’utilisateur n’a aucune action à effectuer.

Vous ne déployez pas ces stratégies directement sur les appareils et utilisateurs. Vous associez plutôt la stratégie à une application que vous déployez ensuite. Les paramètres de stratégie sont utilisés chaque fois que l’application les vérifie (en général, lors de sa première exécution).

> [!TIP] Ce type de stratégie est actuellement disponible uniquement pour les appareils exécutant iOS 7.1 et versions ultérieures, et prend en charge les types d’installation d’application suivants :
> 
> -   **Application iOS gérée à partir de l'App Store**
> -   **Package d'application pour iOS**
> 
> Pour plus d’informations sur les types d’installation d’application, consultez [Deploy apps with Microsoft Intune](deploy-apps.md) (Déployer des applications avec Microsoft Intune).

## Configurer une stratégie de configuration des applications mobiles

1.  Dans la [console d’administration Microsoft Intune](https://manage.microsoft.com), cliquez sur **Stratégie** &gt; **Vue d’ensemble** &gt; **Ajouter une stratégie**.

2.  Dans la liste des stratégies, développez **iOS**, cliquez sur **Configuration des applications mobiles**, puis sur **Créer une stratégie**.

    > [!TIP]
    > Vous ne pouvez configurer des paramètres personnalisés que pour ce type de stratégie. Les paramètres recommandés ne sont pas disponibles.

3.  Dans la section **Général** de la page **Créer une stratégie** , fournissez un nom et une description facultative de la stratégie de configuration des applications mobiles.

4.  Dans la section **Stratégie de configuration des applications mobiles** de la page, entrez ou collez dans la zone une liste de propriétés XML qui contient les paramètres de configuration d’application souhaités.

    > [!TIP] Pour en savoir plus sur les listes de propriétés XML, consultez [Understanding XML Property Lists](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/PropertyLists/UnderstandXMLPlist/UnderstandXMLPlist.html) (Présentation des listes de propriétés XML) sur le site iOS Developer Library.
    > 
    > Le format de la liste de propriétés XML varie en fonction de l’application que vous configurez. Pour plus d’informations sur le format exact à utiliser, contactez le fournisseur de l’application.
    > 
    > Intune prend en charge les types de données suivants dans une liste de propriétés :
    > 
    > &lt;integer&gt;
    > &lt;real&gt;
    > &lt;string&gt;
    > &lt;array&gt;
    > &lt;dict&gt;
    > &lt;true /&gt; ou &lt;false /&gt;
    > 
    > Pour plus d’informations sur les types de données, consultez l’article sur les [listes de propriétés](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/PropertyLists/AboutPropertyLists/AboutPropertyLists.html) sur le site iOS Developer Library.
    >
        > De plus, Intune prend en charge les types de jetons suivants dans la liste de propriétés :
    >    
    > \{\{userprincipalname\}\} - (Exemple : **John@contoso.com**) \{\{mail\}\} - (Exemple : **John@contoso.com**) \{\{partialupn\}\} - (Exemple : **John**) \{\{accountid\}\} - (Exemple : **fc0dc142-71d8-4b12-bbea-bae2a8514c81**) \{\{deviceid\}\} - (Exemple : **b9841cd9-9843-405f-be28-b2265c59ef97**) \{\{userid\}\} - (Exemple : **3ec2c00f-b125-4519-acf0-302ac3761822**) \{\{username\}\} - (Exemple : **John Doe**) \{\{serialnumber\}\} - (Exemple : **F4KN99ZUG5V2**) pour les appareils iOS \{\{serialnumberlast4digits\}\} - (Exemple : **G5V2**) pour les appareils iOS
>
> Les caractères \{\{ et \}\} sont utilisés uniquement par les types de jetons. Ils ne doivent pas être utilisés à d’autres fins.




5.  Cliquez sur **Valider** pour vérifier que le format de liste de propriétés du XML entré est valide.

    > [!IMPORTANT]
    > Quand vous cliquez sur **Valider**, Intune vérifie que le format du XML entré est valide. Il ne vérifie pas que la liste de propriétés XML fonctionne avec l’application à laquelle elle est associée.

6.  Une fois terminé, cliquez sur **Enregistrer la stratégie**.

La nouvelle stratégie s’affiche dans le nœud **Stratégies de configuration** .

## Associer une stratégie de configuration des applications mobiles à une application
Après avoir créé une stratégie de configuration des applications mobiles, vous devez l’associer à l’application iOS à laquelle vous voulez appliquer les paramètres de la stratégie de configuration.

Pour cela, suivez les étapes de création d’un déploiement d’applications fournies dans [Ajouter des applications pour des appareils mobiles dans Microsoft Intune[ et ](deploy-apps-in-microsoft-intune.md)Déployer des applications avec Microsoft Intune](add-apps-for-mobile-devices-in-microsoft-intune.md). Quand vous atteignez la page **Configuration des applications mobiles** de l’Assistant, sélectionnez la stratégie que vous voulez associer à l’application dans la liste déroulante **Stratégie de configuration des applications**.

Ensuite, continuez le déploiement de l’application et surveillez-le comme d’habitude.

Quand l’application déployée est exécutée sur un appareil, elle s’exécute avec les paramètres que vous avez configurés dans la stratégie de configuration des applications mobiles.

> [!TIP] Si une ou plusieurs stratégies de configuration des applications mobiles sont en conflit, aucune stratégie n’est appliquée et le conflit est signalé dans le **Tableau de bord** de la console d’administration Intune.

## Exemple de format de fichier XML de configuration d’application mobile

Quand vous créez un fichier de configuration d’application mobile, vous pouvez spécifier une ou plusieurs des valeurs suivantes à l’aide de ce format :

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




<!--HONumber=Jun16_HO1-->


