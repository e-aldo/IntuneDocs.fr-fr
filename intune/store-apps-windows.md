---
title: "Guide pratique d’ajout d’applications du Windows Store à Intune"
titleSuffix: Azure portal
description: "Découvrez comment ajouter des applications de Windows Store pour Intune."
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 05/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 07241b6d-86d8-4abb-83a2-3fc5feae5788
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: cdc1696175f26dc4bb89fcdd005d88bc0948f86d
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/25/2018
---
# <a name="how-to-add-windows-store-apps-to-microsoft-intune"></a>Guide pratique pour ajouter des applications du Windows Store à Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]


1. Connectez-vous au portail Azure.
2. Choisissez **Autres services** > **Surveillance + Gestion** > **Intune**.
3. Dans le panneau **Intune**, choisissez **Gérer les applications**.
4. Dans la charge de travail **Applications mobiles**, choisissez **Gérer** > **Applications**.
5. Au-dessus de la liste des applications, choisissez **Ajouter**.
6. Dans le panneau **Ajouter une application**, choisissez **Informations de l’application**.
7. Dans le panneau **Modifier l’application**, configurez les informations suivantes. Une fois cela fait, cliquez sur **Ajouter**. Selon l’application choisie, certaines valeurs de ce panneau peuvent avoir été renseignées automatiquement :
    - **Nom de l’application** : saisissez le nom de l’application tel qu’il sera affiché dans le portail d’entreprise. Assurez-vous que tous les noms d'application que vous utilisez sont uniques. Si le même nom d'application existe deux fois, seule l'une des applications sera proposée aux utilisateurs du portail d'entreprise.
    - **Description de l’application :** saisissez la description de l’application. Ce libellé s'affichera dans le portail d'entreprise.
    - **Éditeur :** entrez le nom de l’éditeur de l’application.
    - **URL de l’App Store** : entrez l’URL de l’App Store que vous souhaitez créer.
    - **Système d’exploitation minimal** : dans la liste, choisissez le système d’exploitation minimal sur lequel l’application peut être installée. Si vous affectez l’application à un appareil avec un système d’exploitation antérieur, elle ne sera pas installée.
    - **Catégorie** : (facultatif) sélectionnez une ou plusieurs des catégories d’applications intégrées ou que vous avez créées. Cela permettra aux utilisateurs de trouver aisément l'application lorsqu'ils parcourront le portail d'entreprise.
    - **Afficher comme application en une sur le portail d’entreprise** : met en valeur l’application sur la page principale du portail d’entreprise lorsque les utilisateurs cherchent des applications.
    - **URL d’informations** : si vous le souhaitez, saisissez l’URL d’un site Web qui contient des informations sur cette application. Cette URL s'affichera dans le portail d'entreprise.
    - **URL de confidentialité** : si vous le souhaitez, saisissez l’URL d’un site Web qui contient des informations de confidentialité pour cette application. Cette URL s'affichera dans le portail d'entreprise.
    - **Développeur** : si vous le souhaitez, saisissez le nom du développeur de l’application.
    - **Propriétaire** : si vous le souhaitez, saisissez un nom pour le propriétaire de cette application, par exemple, **Département des ressources humaines**.
    - **Notes** : saisissez les éventuelles notes que vous souhaitez associer à cette application.
    - **Charger l’icône** : chargez une icône qui sera associée à l'application. Il s'agit de l'icône qui s'affichera avec l'application lorsque les utilisateurs parcourront le portail d'entreprise.
8. Lorsque vous avez terminé, dans le panneau **Ajouter une application**, choisissez **Enregistrer**.

L’application que vous avez créée s’affichera dans la liste des applications, où vous pouvez l’affecter aux groupes que vous choisissez. Pour plus d’aide, consultez [Guide pratique pour attribuer des applications à des groupes](apps-deploy.md).

## <a name="manually-assign-windows-10-company-portal-app"></a>Affecter manuellement l’application Portail d’entreprise Windows 10
Les utilisateurs finaux peuvent installer l’application Portail d’entreprise à partir du Microsoft Store pour gérer des appareils et installer des applications. Si, toutefois, votre entreprise vous impose d’affecter l’application Portail d’entreprise, vous pouvez affecter manuellement l’application Portail d’entreprise Windows 10 directement à partir d’Intune, même si vous n’avez pas intégré Intune à Microsoft Store pour Entreprises.

 > [!NOTE]
 > Cette option nécessite l’affectation de mises à jour manuelles chaque fois qu’une mise à jour d’application est publiée.

1. Connectez-vous à votre compte dans le [Microsoft Store pour Entreprises](https://www.microsoft.com/business-store) et acquérez la version avec **licence hors connexion** de l’application Portail d’entreprise.  
2. Une fois que l’application a été acquise, sélectionnez l’application dans la page **Inventorier**.  
3. Sélectionnez **Tous les appareils Windows 10** comme **plateforme**, puis l’**architecture** appropriée et procédez au téléchargement. Un fichier de licence d’application n’est pas nécessaire pour cette application.
![Image de tous les appareils Windows 10 et des détails du package d’architecture X86 à télécharger](./media/Win10CP-all-devices.png)
4. Téléchargez tous les packages sous « Infrastructures requises ». Vous devez effectuer cette opération pour les architectures x86, x64 et ARM, soit un total de 9 packages, comme indiqué ci-dessous.

![Image des fichiers de dépendance à télécharger ](./media/Win10CP-dependent-files.png)
5. Avant de charger l’application Portail d’entreprise dans Intune, créez un dossier (par exemple, C:/Portail Entreprise) avec les packages structurés de la manière suivante :
  1. Placez le package Portail d’entreprise dans C:\Portail Entreprise. Créez un sous-dossier Dépendances dans cet emplacement également.  
  ![Image du dossier Dépendances enregistré avec le fichier APPXBUN](./media/Win10CP-Dependencies-save.png)
  2. Placez les neuf packages de dépendances dans le dossier Dépendances.  
  Si les dépendances ne sont pas placées dans ce format, Intune ne peut pas les reconnaître ni les charger et le chargement du package échoue avec l’erreur suivante.  
  ![La dépendance d’application Windows pour ce programme d’installation logicielle est introuvable dans le dossier de l’application. Vous pouvez poursuivre la création et l’affectation de l’application, mais cette dernière ne pourra pas fonctionner tant que la dépendance d’application Windows manquante ne sera pas spécifiée.](./media/Win10CP-error-message.png)
6. Revenez à Intune, puis chargez l’application Portail d’entreprise en tant que nouvelle application. Affectez-la en tant qu’application requise pour l’ensemble souhaité d’utilisateurs cibles.  

Pour plus d’informations sur la façon dont Intune gère les dépendances pour les applications universelles, consultez [Deploying an appxbundle with dependencies via Microsoft Intune MDM](https://blogs.technet.microsoft.com/configmgrdogs/2016/11/30/deploying-an-appxbundle-with-dependencies-via-microsoft-intune-mdm/) (Déploiement d’un appxbundle avec dépendances via Microsoft Intune MDM).  

### <a name="how-do-i-update-the-company-portal-on-my-users-devices-if-they-have-already-installed-the-older-apps-from-the-store"></a>Comment modifier le portail d’entreprise sur les appareils de mes utilisateurs si ceux-ci ont déjà installé les applications plus anciennes à partir du Windows Store ?
Si vos utilisateurs ont déjà installé les applications Portail d’entreprise Windows 8.1 ou Windows Phone 8.1 à partir du Windows Store, ils doivent être automatiquement mis à jour vers la nouvelle version sans que l’utilisateur ou vous-même n’ayez à intervenir. Si la mise à jour ne se produit pas, demandez à vos utilisateurs de vérifier s’ils ont activé les mises à jour automatiques pour les applications du Windows Store sur leurs appareils.   

### <a name="how-do-i-upgrade-my-sideloaded-windows-81-company-portal-app-to-the-windows-10-company-portal-app"></a>Comment mettre à niveau mon application de portail d’entreprise Windows 8.1 chargée indépendamment vers l’application Portail d’entreprise Windows 10 ?
Notre option de migration recommandée consiste à supprimer l’attribution de l’application Portail d’entreprise Windows 8.1 en définissant « Désinstaller » pour l’action d’attribution. Une fois cette opération effectuée, l’application Portail d’entreprise Windows 10 peut être affectée à l’aide de l’une des options ci-dessus.  

Si vous avez besoin de charger une version test de l’application et que vous avez affecté le portail d’entreprise Windows 8.1 sans le signer avec le certificat Symantec, suivez les étapes de la section Affecter directement via Intune ci-dessus pour terminer la mise à niveau.

Si vous avez besoin de charger une version test de l’application et que vous avez signé et affecté le portail d’entreprise Windows 8.1 avec le certificat de signature de code Symantec, suivez les étapes décrites dans la section ci-dessous.  

### <a name="how-do-i-upgrade-my-signed-and-sideloaded-windows-phone-81-company-portal-app-or-windows-81-company-portal-app-to-the-windows-10-company-portal-app"></a>Comment mettre à niveau mon application Portail d’entreprise Windows 8.1 ou Windows Phone 8.1 chargée indépendamment et signée vers l’application Portail d’entreprise Windows 10 ?
Notre option de migration recommandée consiste à supprimer l’attribution existante de l’application Portail d’entreprise Windows Phone 8.1 ou de l’application Portail d’entreprise Windows 8.1 en définissant « Désinstaller » pour l’action d’attribution. Une fois cette opération effectuée, l’application Portail d’entreprise Windows 10 peut être affectée normalement.  

Sinon, l’application Portail d’entreprise Windows 10 doit être mise à jour et signée de façon adéquate afin de respecter la procédure de mise à niveau.  

Si l’application Portail d’entreprise Windows 10 est signée et affectée de cette façon, vous devez répéter ce processus pour chaque nouvelle mise à jour de l’application quand elle est disponible dans le Windows Store. L’application ne se met pas automatiquement à jour lorsque le Windows Store est mis à jour.  

Voici comment signer et affecter l’application de cette façon :

1. Téléchargez le script de signature de l’application Portail d’entreprise Windows 10 Microsoft Intune à partir de la page [https://aka.ms/win10cpscript](https://aka.ms/win10cpscript).  Ce script nécessite que le SDK Windows pour Windows 10 soit installé sur l’ordinateur hôte. Pour télécharger le SDK Windows pour Windows 10, visitez la page [https://go.microsoft.com/fwlink/?LinkId=619296](https://go.microsoft.com/fwlink/?LinkId=619296).
2. Téléchargez l’application Portail d’entreprise Windows 10 à partir du Microsoft Store pour Entreprises, comme indiqué ci-dessus.  
3. Exécutez le script avec les paramètres d’entrée détaillés dans l’en-tête de script pour signer l’application Portail d’entreprise Windows 10 (extraite ci-dessous). Les dépendances n’ont pas besoin d’être transmises au script. Elles sont uniquement requises lorsque l’application est en cours de téléchargement vers la console d’administration Intune.

|Paramètre | Description|
| ------------- | ------------- |
|InputWin10AppxBundle |Chemin d’accès au fichier appxbundle source |
|OutputWin10AppxBundle |Chemin de sortie du fichier appxbundle signé.  Win81Appx - Chemin d’accès au fichier (.APPX) Portail d’entreprise Windows 8.1 ou Windows Phone 8.1.|
|PfxFilePath |Chemin d’accès au fichier (.PFX) de signature de code Symantec Enterprise Mobile. |
|PfxPassword| Mot de passe du fichier de signature de code Symantec Enterprise Mobile. |
|PublisherId |ID d’éditeur de l’entreprise. S'il n'est pas fourni, le champ 'Subject' du certificat de signature de code Symantec Enterprise Mobile est utilisé.|
|SdkPath | Chemin du dossier racine du SDK Windows pour Windows 10. Cet argument est facultatif et sa valeur par défaut est ${env:ProgramFiles(x86)}\Windows Kits\10.|
Le script transmet la version de l’application Portail d’entreprise Windows 10 signée lorsque son exécution est terminée. Vous pouvez ensuite affecter la version signée de l’application en tant qu’application métier via Intune, ce qui met à niveau les versions actuellement affectées vers cette nouvelle application.  
