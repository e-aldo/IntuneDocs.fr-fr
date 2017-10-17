---
title: "Ajouter des applications pour les PC Windows exécutant le logiciel client Intune"
description: "Cette rubrique montre comment ajouter des applications pour ordinateurs Windows à Intune avant de les déployer."
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 02/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bc8c8be9-7f4f-4891-9224-55fc40703f0b
ms.reviewer: owenyen
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 7c2352ea47d7dab22867e213169d382b9330c171
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/10/2017
---
# <a name="add-apps-for-windows-pcs-that-run-the-intune-software-client"></a>Ajouter des applications pour les PC Windows exécutant le logiciel client Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Cette rubrique montre comment ajouter des applications à Intune avant de les déployer.

> [!IMPORTANT]
> Les informations de cette rubrique vous aident à ajouter des applications pour les PC Windows que vous gérez à l’aide du logiciel client Intune. Si vous souhaitez ajouter des applications pour des PC Windows inscrits et d’autres appareils mobiles, consultez [Ajouter des applications pour des appareils mobiles dans Microsoft Intune](add-apps-for-mobile-devices-in-microsoft-intune.md).

Les applications que vous installez sur des PC doivent prendre en charge l’installation sans assistance (sans aucune intervention de l’utilisateur). Dans le cas contraire, l’installation échoue.


## <a name="add-the-app"></a>Ajouter l’application
Vous utilisez l’Éditeur de logiciel Microsoft Intune pour configurer les propriétés de l’application et la charger vers votre espace de stockage cloud. Voici la procédure à suivre :

1.  Dans la [console Administrateur Microsoft Intune](https://manage.microsoft.com), sélectionnez **Applications** &gt; **Ajouter des applications** pour démarrer l’éditeur de logiciel Intune.

    > [!TIP]
    > Vous devrez peut-être entrer votre nom d’utilisateur et votre mot de passe Intune avant le démarrage de l’éditeur.

2.  Dans la page **Installation du logiciel** de l’éditeur, sous **Spécifier comment ce logiciel doit être mis à disposition des appareils**, choisissez **Programme d’installation du logiciel**, puis spécifiez :

    - **Sélectionnez le type de fichier du programme d’installation du logiciel**. Indique le type de logiciel que vous souhaitez déployer. Pour un PC Windows, choisissez **Windows Installer**.
    - **Spécifier l’emplacement des fichiers d’installation du logiciel**. Entrez l’emplacement des fichiers d’installation ou choisissez **Parcourir** pour sélectionner l’emplacement dans la liste.
    - **Inclure les autres fichiers et sous-dossiers du dossier**. Certains logiciels qui utilisent Windows Installer nécessitent des fichiers de prise en charge. Il doivent se trouver dans le même dossier que le fichier d’installation. Sélectionnez cette option si vous souhaitez également déployer ces fichiers de prise en charge.

    Par exemple, si vous souhaitez publier une application nommée Application.msi dans Intune, la page ressemble à ceci : ![Page d’installation du logiciel de l’éditeur](./media/publisher-for-pc.png)

   Ce type d'installation utilise une partie de votre espace de stockage cloud.

3.  Dans la page **Description du logiciel**, configurez ce qui suit.

    > [!NOTE]
    > Selon le fichier de programme d'installation que vous utilisez, certaines de ces valeurs ont peut-être été entrées automatiquement ou peuvent ne pas apparaître.

    - **Éditeur**. Entrez le nom de l'éditeur de l'application.
    - **Nom**. Entrez le nom de l'application tel qu'il s'affichera dans le portail d'entreprise.<br />Assurez-vous que tous les noms d'application que vous utilisez sont uniques. Si le même nom d'application existe deux fois, seule l'une des applications sera proposée aux utilisateurs du portail d'entreprise.
    - **Description**. Entrez une description de l'application. Ce libellé s'affichera dans le portail d'entreprise.
    - **URL des informations sur le logiciel** (facultatif). Entrez l’URL d’un site web qui contient des informations sur cette application. Cette URL s'affichera dans le portail d'entreprise.
    - **URL de déclaration de confidentialité** (facultatif). Entrez l’URL d’un site web qui contient des informations de confidentialité sur cette application. Cette URL s'affichera dans le portail d'entreprise.
    - **Catégorie** (facultatif). Sélectionnez l’une des catégories d’applications intégrées. Cela permettra aux utilisateurs de trouver aisément l'application lorsqu'ils parcourront le portail d'entreprise.
    - **Icône** (facultatif). Chargez une icône qui sera associée à l’application. Il s'agit de l'icône qui s'affichera avec l'application lorsque les utilisateurs parcourront le portail d'entreprise.

4.  Dans la page **Configuration requise**, sélectionnez les conditions à remplir avant l’installation de l’application. Choisissez parmi :

    - **Architecture**. Choisissez si cette application peut être installée sur les systèmes d’exploitation 32 bits, 64 bits ou les deux.
    - **Système d’exploitation**. Sélectionnez le système d’exploitation minimal sur lequel cette application peut être installée.

5.  Dans la page **Règles de détection**, vous pouvez configurer des règles pour détecter si l’application que vous configurez actuellement est déjà installée sur un PC. Vous pouvez aussi utiliser les règles de détection par défaut pour remplacer automatiquement toutes les versions de l’application précédemment installées. Cette option est pour Windows Installer (fichiers .exe uniquement).

    Les règles que vous pouvez configurer sont les suivantes :
    - **Le fichier existe**. Spécifiez le chemin du fichier que vous voulez détecter. Vous pouvez effectuer une recherche sous **%ProgramFiles%** (c’est-à-dire dans **Program Files**\&lt;chemin&gt; et **Program Files (x86)**\&lt;chemin&gt;) sur le PC ou **%SystemDrive%** (la recherche s’effectue à partir du lecteur racine du PC, généralement le lecteur C).
    - **Le code de produit MSI existe déjà**. Sélectionnez **Parcourir** pour choisir le fichier Windows Installer (msi) que vous voulez détecter.
    - **Cette clé du Registre existe**. Spécifiez une clé de Registre qui commence par **HKEY_LOCAL_MACHINE\**. La recherche peut porter sur les chemins du Registre 32 bits et 64 bits. Si la clé spécifiée existe dans les deux emplacements, la règle de détection est satisfaite.

    Si l’application répond à l’une des règles que vous avez configurées, elle ne sera pas installée.

6.  Pour le type de fichier **Windows Installer** uniquement (.msi et .exe) : dans la page **Arguments de ligne de commande**, indiquez si vous souhaitez fournir des arguments de ligne de commande facultatifs pour le programme d’installation.
    Les paramètres suivants sont ajoutés automatiquement par Intune :
    - **/install** pour les fichiers .exe ;
    - **/quiet** pour les fichiers .msi.
    Notez que ces options ne fonctionnent que si le créateur du package de l’application a activé les fonctionnalités correspondantes.

7.  Pour le type de fichier **Windows Installer** uniquement (.exe uniquement) : dans la page **Codes de retour**, vous pouvez ajouter de nouveaux codes d’erreur qu’Intune interprète quand l’application est installée sur un PC Windows géré.

    Par défaut, Intune utilise des codes de retour standard pour signaler l’échec ou la réussite de l’installation d’un package d’application : **0** (Réussite) ou **3010** (Réussite avec redémarrage). Vous pouvez aussi ajouter vos propres codes de retour à cette liste. Si vous spécifiez une liste de codes de retour et que l'installation de l'application renvoie un code qui ne figure pas dans la liste, il est interprété comme un échec.

8.  Dans la page **Résumé**, passez en revue les informations que vous avez spécifiées. Quand vous êtes prêt, sélectionnez **Charger**.

9. Sélectionnez **Fermer** pour terminer.

L’application s’affiche sur le nœud **Applications** de l’espace de travail **Applications**.

## <a name="next-steps"></a>Étapes suivantes

Une fois l’application créée, l’étape suivante consiste à la déployer. Pour en savoir plus, consultez [Déployer des applications avec Microsoft Intune](deploy-apps.md).

Pour obtenir des conseils et des astuces à propos du déploiement de logiciels sur des PC Windows, consultez le billet de blog [Support Tip: Best Practices for Intune Software Distribution to PC’s](https://blogs.technet.microsoft.com/intunesupport/2016/06/13/support-tip-best-practices-for-intune-software-distribution-to-pcs/).
