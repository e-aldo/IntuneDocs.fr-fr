---
title: "Installer des applications Office 365 ProPlus sur des appareils Windows 10 à l’aide d’Intune"
titleSuffix: Intune on Azure
description: "Découvrez comment utiliser Intune pour faciliter l’installation d’applications Office 365 sur des appareils Windows 10."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 07/17/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3292671a-5f5a-429e-90f7-b20019787d22
ms.reviewer: aiwang
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0f6a3cdc2b5d95f57f1ffc1f68b6748b357f2ef4
ms.sourcegitcommit: 21a9db380956a50031dbea360b4c76664cbc2768
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/17/2017
---
# <a name="how-to-assign-office-365-proplus-2016-apps-to-windows-10-devices-with-microsoft-intune"></a>Guide pratique pour affecter des applications Office 365 ProPlus 2016 à des appareils Windows 10 avec Microsoft Intune

À l’aide de ce nouveau type d’application, vous pouvez affecter facilement des applications Office 365 ProPlus 2016 aux appareils Windows 10 que vous gérez. Vous pouvez également installer des applications pour Microsoft Project Online Desktop Client et Microsoft Visio Pro pour Office 365 si vous disposez des licences appropriées. Les applications souhaitées apparaissent sous la forme d’une application unique dans la liste des applications de la console Intune.


## <a name="before-you-start"></a>Avant de commencer

>[!IMPORTANT]
>Cette méthode d’installation d’Office est uniquement prise en charge si aucune autre version de Microsoft Office n’est installée sur l’appareil.

- Les appareils sur lesquels vous déployez ces applications doivent exécuter Windows 10 Creators Update ou ultérieur.
- Intune prend uniquement en charge l’ajout d’applications Office provenant de la suite Office 365 ProPlus 2016.
- Si des applications Office sont ouvertes au moment où Intune installe la suite d’applications, les utilisateurs finaux risquent de perdre les données contenues dans des fichiers non enregistrés.
- Si vous installez Office sur un appareil sur lequel Office est déjà installé, tenez compte des points suivants :
    - Quelle que soit la version d’Office que vous utilisez, vous ne pouvez pas installer des produits Office 32 bits et 64 bits sur le même appareil.
    - Vous ne pouvez pas installer la même version d’Office sur le même appareil (installation Office « Démarrer en un clic » ou MSI), mais vous pouvez installer des versions principales différentes.
    - Si vous avez déjà installé une version antérieure d’Office à l’aide de la technologie Office « Démarrer en un clic », vous devez supprimer toutes les applications que vous souhaitez remplacer par la version plus récente. Par exemple, si vous avez une version antérieure de Word sur l’appareil et que vous souhaitez affecter la version la plus récente, vous devez d’abord supprimer l’ancienne version.
    - Si Office 365 est déjà installé sur un appareil et que vous affectez la suite Office 365 ProPlus 2016 à cet appareil, vous devrez peut-être changer votre niveau d’abonnement Office.


## <a name="get-started"></a>Prise en main

1.  Connectez-vous au portail Azure.
2.  Choisissez **Plus de Services** > **Surveillance + Gestion** > **Intune**.
3.  Dans le panneau **Intune**, choisissez **Applications mobiles**.
4.  Dans la charge de travail **Applications mobiles**, choisissez **Gérer** > **Applications**.
5.  Au-dessus de la liste des applications, choisissez **Ajouter**.
6.  Dans le panneau **Ajouter une application**, choisissez **Suite Office 365 ProPlus (Windows 10)**.

## <a name="configure-the-app-suite"></a>Configurer la suite d’applications

Dans cette étape, choisissez les applications Office à affecter aux appareils.

1.  Dans le panneau **Ajouter une application**, choisissez **Configurer la suite d’applications**.
2.  Dans le panneau **Configurer la suite d’applications**, choisissez les applications Office standard à affecter aux appareils. Vous pouvez également installer des applications pour Microsoft Project Online Desktop Client et Microsoft Visio Pro pour Office 365 si vous disposez des licences appropriées.
3.  Une fois terminé, cliquez sur **OK**.

>[!IMPORTANT]
> Une fois la suite d’applications créée, vous ne pouvez plus modifier ses propriétés. Pour configurer des propriétés différentes, supprimez la suite d’applications et créez-en une autre.

## <a name="configure-app-information"></a>Configurer les informations de l’application

Dans cette étape, indiquez des informations sur la suite d’applications. Ces informations vous permettent d’identifier la suite dans la console Intune. Elles aident aussi les utilisateurs finaux à trouver la suite dans l’application Portail d’entreprise.

1.  Dans le panneau **Ajouter une application**, choisissez **Informations sur la suite d’applications**.
2.  Dans le panneau **Informations sur la suite d’applications**, indiquez les informations suivantes : 
    - **Nom de la suite** : entrez le nom de la suite d’applications tel qu’il apparaît dans le portail d’entreprise. Vérifiez que chaque nom de suite que vous utilisez est unique. Si un même nom de suite d’applications est utilisé deux fois, une seule application est proposée aux utilisateurs du portail d’entreprise.
    - **Description de la suite** : entrez la description de la suite d’applications. Vous pouvez par exemple répertorier les applications que vous avez choisies d’inclure.
    - **Éditeur :** entrez le nom de l’éditeur de l’application.
    - **Catégorie** : si vous le souhaitez, sélectionnez une ou plusieurs des catégories d’applications intégrées ou que vous avez créées. Ceci permet de faciliter la recherche de la suite d’applications pour les utilisateurs qui naviguent dans le portail d’entreprise.
    - **Proposer cette application dans le portail d’entreprise** : met en avant la suite d’applications dans la page principale du portail d’entreprise quand les utilisateurs cherchent des applications.
    - **URL d’informations** : si vous le souhaitez, saisissez l’URL d’un site Web qui contient des informations sur cette application. Cette URL est présentée aux utilisateurs du portail d’entreprise.
    - **URL de confidentialité** : si vous le souhaitez, saisissez l’URL d’un site Web qui contient des informations de confidentialité pour cette application. Cette URL est présentée aux utilisateurs du portail d’entreprise.
    - **Développeur** : si vous le souhaitez, saisissez le nom du développeur de l’application.
    - **Propriétaire** : si vous le souhaitez, saisissez un nom pour le propriétaire de cette application, par exemple, **Département des ressources humaines**.
    - **Notes** : saisissez les éventuelles notes que vous souhaitez associer à cette application.
    - **Charger l’icône** : chargez une icône qui s’affiche avec l’application quand les utilisateurs parcourent le portail d’entreprise.
3.  Une fois terminé, cliquez sur **OK**.

## <a name="configure-app-settings"></a>Configurer les paramètres de l’application

Dans cette étape, configurez les options d’installation de la suite d’applications. Les paramètres s’appliquent à toutes les applications que vous avez ajoutées à la suite.

1.  Dans le panneau **Ajouter une application**, choisissez **Paramètres de la suite d’applications**.
2.  Dans le panneau **Paramètres de la suite d’applications**, indiquez les informations suivantes : 
    - **Version d’Office** : choisissez si vous souhaitez affecter la version 32 bits ou 64 bits d’Office. Vous pouvez installer la version 32 bits sur des appareils 32 bits et 64 bits, mais vous ne pouvez installer la version 64 bits que sur des appareils 64 bits.
    - **Canal de mise à jour** : choisissez le mode de mise à jour d’Office sur les appareils. Pour plus d’informations sur les différents canaux de mise à jour, consultez Vue d’ensemble des canaux de mise à jour pour Office 365 ProPlus. Choisissez parmi : 
        - **Actuel**
        - **Différé**
        - **Canal actuel de la première version**
        - **Canal différé de la première version**
    - **Accepter automatiquement le contrat de licence utilisateur final de l’application** : sélectionnez cette option si les utilisateurs finaux ne sont pas tenus d’accepter le contrat de licence. Intune accepte alors automatiquement le contrat.
    - **Utiliser l’activation d’ordinateurs partagés** : l’activation d’ordinateurs partagés est utilisée quand plusieurs utilisateurs partagent un ordinateur. Pour plus d’informations, consultez Vue d’ensemble de l’activation d’ordinateurs partagés pour Office 365 ProPlus.
    - **Langues** : Office s’installe automatiquement dans toute langue prise en charge installée avec Windows sur l’appareil de l’utilisateur final. Sélectionnez cette option pour installer des langues supplémentaires avec la suite d’applications.

>[!IMPORTANT]
> Une fois la suite d’applications créée, vous ne pouvez plus modifier ses propriétés. Pour configurer des propriétés différentes, supprimez la suite d’applications et créez-en une autre.

## <a name="finish-up"></a>Terminer

Lorsque vous avez terminé, dans le panneau **Ajouter une application**, choisissez **Enregistrer**. L’application que vous avez créée s’affiche dans la liste des applications.

## <a name="error-codes-when-installing-the-app-suite"></a>Codes d’erreur durant l’installation de la suite d’applications

Le tableau suivant répertorie les codes d’erreur fréquemment rencontrés et leur signification.

### <a name="status-for-office-csp"></a>État pour Office CSP : 

||||
|-|-|-|
|Status|Phase|Description|
|1460 (ERROR_TIMEOUT)|Télécharger|Échec du téléchargement de l’outil Déploiement d’Office|    
|13 (ERROR_INVALID_DATA)|-|Impossible de vérifier la signature de l’outil Déploiement d’Office téléchargé| 
|Code d’erreur de CertVerifyCertificateChainPolicy|-|Échec de la vérification de certification pour l’outil Déploiement d’Office téléchargé|    
|997|WIP|En cours d'installation| 
|0|Après l’installation|Installation réussie|    
|1603 (ERROR_INSTALL_FAILURE)|-|Échec de la vérification des prérequis, par exemple :<br>- SxS (tentative d’installation alors que la version MSI 2016 est installée)<br>- non-concordance des versions<br>- etc.|     
|0x8000ffff (E_UNEXPECTED)|-|Tentative de désinstallation alors qu’aucune installation Office « Démarrer en un clic » n’est présente sur l’ordinateur.|    
|17002|-|Échec de l’exécution du scénario (installation). Raisons possibles :<br>- Installation annulée par l’utilisateur<br>- Installation annulée par une autre installation<br>- Espace insuffisant durant l’installation<br>- ID de langue inconnu| 
|17004|-|Références SKU inconnues|   


### <a name="office-deployment-tool-error-codes"></a>Codes d’erreur de l’outil Déploiement d’Office

|||||
|-|-|-|-|
|Scénario|Code de retour|Interface utilisateur du service|Remarque| 
|Tentative de désinstallation en l’absence d’une installation Office « Démarrer en un clic »|-2147418113, 0x8000ffff ou 2147549183|Code d’erreur : 30088-1008<br>Code d’erreur : 30125-1011 (404)|Outil Déploiement d’Office| 
|Installation alors qu’une version MSI est installée|1603|-|Outil Déploiement d’Office| 
|Installation annulée par l’utilisateur ou par une autre installation|17002|-|Office « Démarrer en un clic »| 
|Tentative de désinstallation d’une version 64 bits sur un appareil sur lequel la version 32 bits est installée.|1603|-|Code de retour de l’outil Déploiement d’Office| 
|Tentative d’installation d’une référence SKU inconnue (il ne s’agit pas d’un cas d’usage légitime pour Office CSP puisque seules des références SKU valides doivent être passées)|17004|-|Office « Démarrer en un clic »| 
|Espace insuffisant|17002|-|Office « Démarrer en un clic »| 
|Échec du démarrage du client Office « Démarrer en un clic » (inattendu)|17000|-|Office « Démarrer en un clic »| 
|Échec de la mise en file d’attente du scénario par le client Office « Démarrer en un clic » (inattendu)|17001|-|Office « Démarrer en un clic »| 

## <a name="next-steps"></a>Étapes suivantes

Vous pouvez maintenant affecter les applications aux groupes de votre choix. Pour plus d’aide, consultez [Guide pratique pour attribuer des applications à des groupes](/intune-azure/manage-apps/deploy-apps).

             


