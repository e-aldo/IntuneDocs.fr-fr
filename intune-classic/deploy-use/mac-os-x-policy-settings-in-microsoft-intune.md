---
title: "Paramètres de stratégie Mac OS X"
description: "Intune fournit un éventail de paramètres généraux intégrés, que vous pouvez configurer sur les appareils Mac OS X. En outre, vous pouvez recourir à l’outil Apple Configurator pour créer des paramètres personnalisés qui ne sont pas disponibles à partir d’Intune."
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 98b2f19b-bee8-42d7-a215-a716d56a25a3
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 0039ac4552bc1995a1af033cc4572808cbd44d43
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/10/2017
---
# <a name="mac-os-x-configuration-policy-settings-in-microsoft-intune"></a>Paramètres de la stratégie de configuration Mac OS X dans Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Intune fournit un éventail de paramètres généraux intégrés, que vous pouvez configurer sur les appareils Mac OS X. En outre, vous pouvez recourir à l’outil Apple Configurator pour créer des paramètres personnalisés qui ne sont pas disponibles à partir d’Intune.

## <a name="general-configuration-policy-settings"></a>Paramètres de la stratégie de configuration générale

Utilisez la **stratégie de configuration générale Mac OS X** de Microsoft Intune pour configurer les paramètres suivants :

-   **Paramètres de sécurité de l’appareil**. Choisissez des paramètres dans une liste de paramètres prédéfinis, qui vous permettent de contrôler diverses fonctions et fonctionnalités sur l’appareil.

-   **Applications conformes et non conformes**. Spécifiez une liste d’applications conformes ou non conformes au sein de votre entreprise. Le rapport sur les applications non conformes peut être utilisé pour vérifier la conformité des applications spécifiées dans la liste par rapport à celle des applications installées par les utilisateurs (sans qu’il soit possible de bloquer leur installation).

Si le paramètre que vous recherchez n’apparaît pas dans cette liste, vous pourrez peut-être le créer à l’aide d’une stratégie Mac OS X personnalisée, qui vous permet d’importer les paramètres créés avec l’outil Apple Configurator. Pour en savoir plus, consultez la section « Paramètres de la stratégie personnalisée » de la présente rubrique.

### <a name="password-settings"></a>Paramètres de mot de passe

|Nom du paramètre|Détails|
|----------------|---------------|
|**Exiger un mot de passe pour déverrouiller des appareils**|Indique si l’utilisateur doit utiliser un mot de passe pour accéder à son ordinateur Mac. **Important :** Contrairement aux appareils iOS, sur les appareils Mac OS X l’utilisateur ne reçoit pas immédiatement une notification lui demandant de mettre à jour son mot de passe pour se conformer à ce paramètre.|
|**Type de mot de passe requis**|Indique si le mot de passe peut être uniquement de nature **numérique** ou s’il doit être **alphanumérique** (c’est-à-dire, contenir des lettres et des chiffres). **Important :** ce paramètre est uniquement pris en charge sur les systèmes Mac OS X 10.10.3 et les versions ultérieures.|
|**Nombre de caractères complexes requis dans le mot de passe**|Spécifie le nombre de caractères complexes nécessaires dans le mot de passe (de **0** à **4**).<br /><br />Un caractère complexe est un symbole, tel que **?**.|
|**Longueur minimale du mot de passe**|Définit la longueur minimale du mot de passe (entre **4** et **14** caractères).|
|**Autoriser les mots de passe simples**|Permet d’utiliser des mots de passe simples, tels que **0000** ou **1234**.|
|**Minutes d’inactivité avant demande du mot de passe**|Indique la durée pendant laquelle l’ordinateur doit être inactif avant qu’un mot de passe soit requis pour le déverrouiller.|
|**Expiration du mot de passe (jours)**|Spécifie le nombre de jours qui s’écoule avant que l’utilisateur ne doive changer le mot de passe (entre **1** et **255** jours).|
|**Mémoriser l’historique des mots de passe**|Ce paramètre permet d’empêcher l’utilisateur d’employer un mot de passe utilisé précédemment. Lorsque ce paramètre est défini, vous pouvez aussi définir l’option **Empêcher la réutilisation des mots de passe précédents** pour spécifier le nombre de mots de passe précédemment utilisés qui ne peuvent pas être réutilisés (entre **1** et **24**).|
|**Minutes d’inactivité avant activation de l’écran de veille**|Spécifie la durée pendant laquelle l’ordinateur doit être inactif avant que l’écran de veille ne s’active.|

### <a name="settings-for-compliant-and-noncompliant-apps"></a>Paramètres des applications conformes et non conformes
Dans la liste **Applications conformes &amp; non conformes pour Mac OS X**, activez l’option **Paramètres gérés pour les appareils**, puis spécifiez une liste d’applications conformes ou non conformes à l’aide des informations ci-après.

> [!NOTE]
> Une stratégie ne peut contenir qu’une liste d’applications conformes ou une liste d’applications non conformes. Vous ne pouvez pas spécifier les deux dans la même stratégie.
>
> Intune vous permet de vous signaler les appareils comportant des applications non conformes. Cela ne bloque pas l’installation ou ne supprime pas les applications non conformes.

|Nom du paramètre|Détails|
|----------------|---------------|
|**Signaler une non-conformité quand les utilisateurs installent les applications listées**|Répertorie les applications Mac OS X que les utilisateurs ne sont pas autorisés à installer. Si les utilisateurs installent l’une de ces applications, les **rapports d’applications non conformes** le signalent.|
|**Signaler une non-conformité quand les utilisateurs installent les applications non listées**|Affiche les applications Mac OS X que les utilisateurs sont autorisés à installer. Si les utilisateurs installent d’autres applications, les **rapports d’applications non conformes** le signalent.|
|**Ajouter**|Ajoute une application à la liste sélectionnée. Spécifiez un nom de votre choix, éventuellement l’éditeur et l’ID d’offre groupée de l’application. **Astuce :** Pour rechercher l’ID d’offre groupée d’une application, effectuez les étapes suivantes sur un ordinateur Mac où l’application est installée :<ol><li>Ouvrez le dossier dans lequel l’application est installée (par exemple, **/Applications**).</li><li>Sélectionnez l’offre groupée *&lt;Nom application&gt;***.app** et choisissez l’option **Afficher le contenu du package**.</li><li>Ouvrez le fichier **Info.plist**.</li><li>Vérifiez la valeur associée à la clé **CFBundleIdentifier**.</li></ol>Le format de l’ID d’offre groupée est le suivant : **com.contoso.nomapp**.|
|**Importer des applications**|Importe une liste d’applications que vous avez spécifiées dans un fichier de valeurs séparées par des virgules. Dans le fichier, utilisez le format suivant : nom de l’application, éditeur, ID de l’offre groupée d’applications.|
|**Éditer**|Vous permet de modifier le nom, l’éditeur et l’ID de l’offre groupée d’applications pour l’application sélectionnée.|
|**Supprimer**|Supprime l’application sélectionnée dans la liste.|
> [!TIP]
> Pour plus d’informations sur les rapports Intune, consultez [Présentation des opérations Microsoft Intune à l’aide de rapports](understand-microsoft-intune-operations-by-using-reports.md).

> [!IMPORTANT]
> Lorsqu’un appareil Mac OS X est en mode veille, il n’est pas possible de livrer ou d’inventorier les stratégies et les profils. Par conséquent, la console Intune peut afficher temporairement l’état **Paramètres de stratégie erronés** jusqu’à ce que l’appareil sorte du mode veille.

### <a name="monitor-compliant-and-noncompliant-apps"></a>Contrôler les applications conformes et non conformes
Utilisez les **rapports sur les applications non conformes** pour afficher la conformité des applications que vous avez spécifiées.

#### <a name="to-run-a-report"></a>Pour exécuter un rapport

1.  Dans la [console d’administration Microsoft Intune](https://manage.microsoft.com), sélectionnez **Rapports** &gt; **Rapports sur les applications non conformes**.

2.  Sélectionnez les groupes d’appareils que vous voulez vérifier, en indiquant si vous voulez vérifier les applications conformes, non conformes ou les deux, puis choisissez **Afficher le rapport**.

## <a name="mac-os-x-custom-policy-settings-in-microsoft-intune"></a>Paramètres de la stratégie personnalisée Mac OS X dans Microsoft Intune
Utilisez la **stratégie de configuration personnalisée Mac OS X** de Microsoft Intune pour déployer les paramètres que vous avez créés à l’aide de l’[outil Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) sur des appareils Mac OS X. Cet outil vous permet de créer plusieurs paramètres qui contrôlent le fonctionnement de ces appareils et de les exporter vers un profil de configuration. Vous pouvez ensuite importer ce profil de configuration dans une stratégie personnalisée Mac OS X Intune et déployer les paramètres sur les utilisateurs et les appareils de votre organisation.

Cette fonctionnalité vous permet de déployer les paramètres Mac OS X qui ne sont pas configurables avec la stratégie de configuration générale Mac OS X Intune.

### <a name="prerequisites"></a>Conditions préalables
Avant de commencer, vous devez installer l’outil Apple Configurator et créer un fichier de configuration contenant les paramètres que vous souhaitez déployer sur les systèmes des utilisateurs ou les appareils. Visitez le [Mac App Store](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) pour télécharger l’outil Apple Configurator et en savoir plus à son sujet.

> [!NOTE]
> Intune ne signale pas la conformité des paramètres individuels dans une stratégie personnalisée Mac OS X. Toutefois, la conformité d'ensemble de la stratégie est signalée.

### <a name="general-settings"></a>Paramètres généraux :

|Nom du paramètre|Détails|
    |----------------|--------------------|
    |**Nom**|Affectez un nom unique à la stratégie personnalisée Mac OS X pour vous aider à l’identifier dans la console Intune.|
    |**Description**|Fournissez une description générale de la stratégie personnalisée Mac OS X et d'autres informations pertinentes pour mieux la localiser.|


### <a name="custom-settings"></a>Configuration personnalisée

|Nom du paramètre|Détails|
    |----------------|--------------------|
    |**Nom du profil de configuration personnalisé (montré aux utilisateurs)**|Saisissez le nom de la stratégie tel qu’il sera affiché sur l’appareil et dans les rapports de stratégie Intune.|
    |**Fichier de configuration de profil**|Sélectionnez l’option **Importer**, puis accédez au profil de configuration que vous avez créé à l’aide de l’outil Apple Configurator. **Conseil :** Consultez la section « Création d’un fichier de profil de configuration » de la présente rubrique pour en savoir plus sur la création du profil de configuration.|
    |**Détails du profil de configuration**|Affichez le code XML du profil de configuration que vous avez importé.|



### <a name="how-to-create-a-configuration-profile-file"></a>Création d’un fichier de profil de configuration
Vous pouvez créer le fichier de profil de configuration utilisé par la stratégie personnalisée de deux manières :

-   Exportez le fichier (avec l'extension **.mobileconfig**) à partir de l'outil Apple Configurator.

-   Créez le fichier en utilisant le schéma approprié à partir de la [Référence des clés de profil de configuration Apple](https://developer.apple.com/library/ios/featuredarticles/iPhoneConfigurationProfileRef/Introduction/Introduction.html).


### <a name="see-also"></a>Voir aussi
[Gérer des paramètres et des fonctionnalités sur vos appareils avec des stratégies Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)
