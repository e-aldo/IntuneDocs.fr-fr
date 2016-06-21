---
# required metadata

title: Paramètres de la stratégie Mac OS X | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 98b2f19b-bee8-42d7-a215-a716d56a25a3

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Paramètres de la stratégie de configuration Mac OS X dans Microsoft Intune

## Paramètres de la stratégie de configuration générale

Utilisez la **stratégie de configuration générale Mac OS X** de Microsoft Intune pour configurer les paramètres suivants :

-   **Paramètres de sécurité des appareils** : choisissez des paramètres dans une liste de paramètres prédéfinis qui vous permettent de contrôler diverses fonctions et fonctionnalités sur l’appareil.

-   **Applications conformes et non conformes** : spécifiez une liste d’applications conformes ou non conformes dans votre entreprise. Le rapport sur les applications non conformes permet d’afficher la conformité des applications que vous avez spécifiées dans la liste par rapport à celle des applications installées par les utilisateurs (sans qu’il soit possible de bloquer l’installation de l’application).

Si le paramètre que vous recherchez n’apparaît pas dans cette liste, essayez de le créer à l’aide d’une stratégie personnalisée Mac OS X qui vous permet d’importer les paramètres créés avec l’outil Apple Configurator. Pour plus d’informations, consultez **Paramètres de stratégie personnalisée** plus loin dans cette rubrique.

### Paramètres de mot de passe

|Nom du paramètre|Détails|
|----------------|---------------|
|**Exiger un mot de passe pour déverrouiller des appareils**|Spécifie si l’utilisateur doit utiliser un mot de passe pour accéder à son ordinateur Mac. **Important :** Contrairement aux appareils iOS, sur les appareils Mac OS X l’utilisateur ne reçoit pas immédiatement une notification lui demandant de mettre à jour son mot de passe pour se conformer à ce paramètre.|
|**Type de mot de passe requis**|Spécifie si le mot de passe peut être uniquement numérique ou s'il doit être **alphanumérique** (c’est-à-dire contenir des lettres et des chiffres). **Important :** Ce paramètre est pris en charge uniquement sur Mac OS X 10.10.3 et versions ultérieures.|
|**Nombre de caractères complexes requis dans le mot de passe**|Spécifie le nombre de caractères complexes nécessaires dans le mot de passe (**0** - **4**).<br /><br />Un caractère complexe est un symbole, tel que «**?**».|
|**Longueur minimale du mot de passe**|Spécifie la longueur minimale du mot de passe (entre **4** et **14** caractères).|
|**Autoriser les mots de passe simples**|Permet d'utiliser des mots de passe simples, tels que «**0000**» ou «**1234**».|
|**Minutes d'inactivité avant demande du mot de passe**|Spécifie la durée pendant laquelle l’ordinateur doit être inactif avant qu’un mot de passe soit requis pour le déverrouiller.|
|**Expiration du mot de passe (jours)**|Spécifie le nombre de jours qui s’écoule avant que l’utilisateur doive changer le mot de passe (entre **1** - **255** jours).|
|**Mémoriser l'historique des mots de passe**|Ce paramètre permet d’empêcher l’utilisateur d’employer un mot de passe utilisé précédemment. Quand ce paramètre est défini, vous pouvez aussi définir **Empêcher la réutilisation des mots de passe précédents** pour spécifier le nombre de mots de passe précédemment utilisés qui ne peuvent pas être réutilisés (**1** - **24**).|
|**Minutes d’inactivité avant activation de l’écran de veille**|Spécifie la durée pendant laquelle l’ordinateur doit être inactif avant que l’écran de veille s’active.|

### Paramètres des applications conformes et non conformes
Dans la liste **Applications conformes &amp; non conformes pour Mac OS X**, activez **Paramètres gérés pour les appareils**, puis spécifiez une liste d’applications conformes ou non conformes à l’aide des informations suivantes :

> [!NOTE]
> Une stratégie ne peut contenir qu'une liste d'applications conformes ou une liste d'applications non conformes. Vous ne pouvez pas spécifier les deux dans la même stratégie.
> 
> Intune vous permet de vous signaler les appareils comportant des applications non conformes. Cela ne bloque pas l’installation et ne supprime pas les applications non conformes.

|Nom du paramètre|Détails|
|----------------|---------------|
|**Signaler une non-conformité quand les utilisateurs installent les applications listées**|Répertorie les applications Mac OS X que les utilisateurs ne sont pas autorisés à installer. Si les utilisateurs installent une de ces applications, cela est signalé dans les **Rapports d'applications non conformes**.|
|**Signaler une non-conformité quand les utilisateurs installent les applications non listées**|Répertorie les applications Mac OS X que les utilisateurs sont autorisés à installer. Si les utilisateurs installent d’autres applications, cela est signalé dans les **Rapports d'applications non conformes**.|
|**Ajouter**|Ajoute une application à la liste sélectionnée. Spécifiez un nom de votre choix, éventuellement l’éditeur de l’application, et l’ID d’offre groupée de l’application. **Astuce :** Pour rechercher l’ID d’offre groupée d’une application, effectuez les étapes suivantes sur un ordinateur Mac où l’application est installée :<ol><li>Ouvrez le dossier dans lequel l’application est installée (par exemple, **/Applications**)</li><li>Sélectionnez l’offre groupée *&lt;<Nom de l’application>&gt;***.app** et choisissez **Afficher le contenu du package**</li><li>Ouvrez le fichier **Info.plist**</li><li>Vérifiez la valeur associée à la clé **CFBundleIdentifier**</li></ol>L’ID d'offre groupée figure dans le format **com.contoso.nomapp**|
|**Importer des applications**|Importe une liste d'applications que vous avez spécifiée dans un fichier de valeurs séparées par des virgules. Utilisez le format, le nom de l’application, l’éditeur et l’ID d’offre groupée dans le fichier.|
|**Éditer**|Vous permet de modifier le nom, l’éditeur et l’ID d’offre groupée de l’application sélectionnée.|
|**Supprimer**|Supprime l'application sélectionnée dans la liste.|
> [!TIP] Pour plus d’informations sur les rapports Intune, consultez [Présentation des opérations Microsoft Intune à l’aide de rapports](understand-microsoft-intune-operations-by-using-reports.md).

> [!IMPORTANT]
> Quand un appareil Mac OS X est en mode veille, il n’est pas possible de remettre ou d’inventorier les stratégies et les profils. Par conséquent, la console Intune peut afficher temporairement l’état **Paramètres de stratégie erronés** jusqu’à ce que l’appareil sorte du mode veille.

### Contrôler les applications conformes et non conformes
Utilisez le **Rapport sur les applications non conformes** pour afficher la conformité des applications que vous avez spécifiées.

#### Pour exécuter le rapport

1.  Dans la [console d’administration Microsoft Intune](https://manage.microsoft.com), cliquez sur **Rapports** &gt; **Rapports sur les applications non conformes**.

2.  Sélectionnez les groupes d'appareils que vous souhaitez vérifier, si vous souhaitez vérifier les applications conformes, les applications non conformes ou les deux, puis cliquez sur **Afficher le rapport**.

## Paramètres de la stratégie personnalisée Mac OS X dans Microsoft Intune
Utilisez la **stratégie de configuration personnalisée Mac OS X** Microsoft Intune pour déployer les paramètres que vous avez créés à l’aide de l’[outil Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) sur des appareils Mac OS X. Cet outil vous permet de créer plusieurs paramètres qui contrôlent le fonctionnement de ces appareils et de les exporter vers un profil de configuration. Vous pouvez ensuite importer ce profil de configuration dans une stratégie personnalisée Mac OS X Intune et déployer les paramètres sur les utilisateurs et les appareils de votre organisation.

Cette fonctionnalité est conçue pour vous permettre de déployer les paramètres Mac OS X qui ne sont pas configurables avec une stratégie de configuration générale Mac OS X Intune.

### Conditions préalables
Avant de commencer, vous devez installer l'outil Apple Configurator et créer un fichier de configuration contenant les paramètres que vous souhaitez déployer sur les utilisateurs ou les appareils. Visitez le [Mac App Store](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12)pour télécharger l’outil Apple Configurator et en savoir plus

> [!NOTE]
> Intune ne signale pas la conformité des paramètres individuels dans une stratégie personnalisée Mac OS X. Toutefois, la conformité d'ensemble de la stratégie est signalée.

### Paramètres généraux :

|Nom du paramètre|Détails|
    |----------------|--------------------|
    |**Nom**|Affectez un nom unique à la stratégie personnalisée Mac OS X pour vous aider à l’identifier dans la console Intune.|
    |**Description**|Fournissez une description générale de la stratégie personnalisée Mac OS X et d'autres informations pertinentes pour mieux la localiser.|


### Configuration personnalisée

|Nom du paramètre|Détails|
    |----------------|--------------------|
    |**Nom du profil de configuration personnalisé (montré aux utilisateurs)**|Entrez le nom de la stratégie tel qu’il sera affiché sur l’appareil et dans les rapports de stratégie Intune.|
    |**Fichier de configuration de profil**|Cliquez sur **Importer**, puis recherchez le profil de configuration que vous avez créé à l'aide de l'outil Apple Configurator. **Conseil :** consultez [Création d’un fichier de profil de configuration](#BKMK_Prof) dans cette rubrique pour de l’aide au sujet de la création du profil de configuration.|
    |**Détails du profil de configuration**|Affiche le code XML du profil de configuration que vous avez importé.|



### Création d’un fichier de profil de configuration
Vous pouvez créer le fichier de profil de configuration utilisé par la stratégie personnalisée de deux manières :

-   Exportez le fichier (avec l'extension **.mobileconfig**) à partir de l'outil Apple Configurator.

-   Créez le fichier en utilisant le schéma approprié à partir de la [Référence des clés de profil de configuration](https://developer.apple.com/library/ios/featuredarticles/iPhoneConfigurationProfileRef/Introduction/Introduction.html).


> [!IMPORTANT]
> Quand un appareil Mac OS X est en mode veille, il n’est pas possible de remettre ou d’inventorier les stratégies et les profils. Par conséquent, la console Intune peut afficher temporairement l’état **Paramètres de stratégie erronés** jusqu’à ce que l’appareil sorte du mode veille.

### Voir aussi
[Gérer des paramètres et des fonctionnalités sur vos appareils avec des stratégies Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)



<!--HONumber=Jun16_HO1-->


