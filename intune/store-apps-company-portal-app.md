---
title: "Ajouter manuellement l’application Portail d’entreprise Windows 10"
titleSuffix: Microsoft Intune
description: "Découvrez comment ajouter manuellement l’application Portail d’entreprise Windows 10."
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/06/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bfe1a2d3-f611-4dbb-adef-c0dff4d7b810
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 06ed9395d06e2d64edcedcaadfe819ad03f1d495
ms.sourcegitcommit: 8a235b7af6ec3932c29a76d0b1aa481d983054bc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/12/2018
---
# <a name="manually-add-the-windows-10-company-portal-app-using-microsoft-intune"></a>Ajouter manuellement l’application Portail d’entreprise Windows 10 à l’aide de Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Les utilisateurs finaux peuvent installer l’application Portail d’entreprise à partir du Microsoft Store pour gérer des appareils et installer des applications. Si, toutefois, votre entreprise vous impose d’affecter l’application Portail d’entreprise, vous pouvez affecter manuellement l’application Portail d’entreprise Windows 10 directement à partir d’Intune, même si vous n’avez pas intégré Intune à Microsoft Store pour Entreprises.

 > [!NOTE]
 > Cette option nécessite l’affectation de mises à jour manuelles chaque fois qu’une mise à jour d’application est publiée.

## <a name="configure-settings-to-show-offline-apps"></a>Configurer les paramètres permettant d’afficher les applications hors connexion
1. Accédez au [Microsoft Store pour Entreprises](https://www.microsoft.com/business-store) et vérifiez que vous êtes connecté avec votre compte d’administrateur.
2. Sélectionnez l’onglet **Gérer** en haut de la fenêtre.
3. Sélectionnez **Paramètres** dans la colonne de navigation de gauche.
4. Dans la section **Expérience d’achat**, définissez **Afficher les applications hors connexion** sur **Activé**. Les applications sous licence hors connexion s’affichent alors dans le Microsoft Store pour Entreprise.

## <a name="download-the-offline-company-portal-app"></a>Télécharger l’application Portail d’entreprise hors connexion
1. Recherchez et sélectionnez l’application **Portail d’entreprise**.
2. Définissez le **Type de licence** sur **Hors connexion**.
3. Cliquez sur **Obtenir l’application** pour acquérir l’application Portail d’entreprise hors connexion et l’ajouter à votre inventaire.
4. Cliquez sur **Gérer** dans la page de l’application **Portail d’entreprise**.
5. Sélectionnez **Tous les appareils Windows 10** comme **Plateforme**, puis sélectionnez les valeurs appropriées pour **Version minimale**, **Architecture** et Télécharger les métadonnées de l’application**. 
6. Cliquez sur **Télécharger** pour enregistrer le fichier sur votre ordinateur local.

    ![Image de tous les appareils Windows 10 et des détails du package d’architecture X86 à télécharger](./media/Win10CP-all-devices.png)

7. Téléchargez tous les packages sous « Infrastructures requises ». Vous devez effectuer cette opération pour les architectures x86, x64 et ARM, soit un total de 12 packages.
8. Avant de charger l’application Portail d’entreprise dans Intune, créez un dossier (par exemple, C:&#92;Portail Entreprise) en structurant les packages de la manière suivante :
  - Placez le package Portail d’entreprise dans C:\Portail Entreprise. Créez un sous-dossier Dépendances dans cet emplacement également.  

    ![Image du dossier Dépendances enregistré avec le fichier APPXBUN](./media/Win10CP-Dependencies-save.png)

  - Placez les packages de dépendances dans le dossier *Dépendances*. 

     > [!NOTE]
     > Si les dépendances ne sont pas placées dans le bon format, Intune ne peut pas reconnaître et charger les fichiers pendant le chargement du package, ce qui conduit à l’échec du chargement avec l’erreur suivante.

9. Revenez à Microsoft Intune dans le portail Azure.
10. Chargez l’application Portail d’entreprise comme nouvelle application. Affectez-la en tant qu’application requise pour l’ensemble souhaité d’utilisateurs cibles.  

Pour plus d’informations sur la façon dont Intune gère les dépendances pour les applications universelles, consultez [Deploying an appxbundle with dependencies via Microsoft Intune MDM](https://blogs.technet.microsoft.com/configmgrdogs/2016/11/30/deploying-an-appxbundle-with-dependencies-via-microsoft-intune-mdm/) (Déploiement d’un appxbundle avec dépendances via Microsoft Intune MDM).  

## <a name="how-do-i-update-the-company-portal-on-my-users-devices-if-they-have-already-installed-the-older-apps-from-the-store"></a>Comment modifier le portail d’entreprise sur les appareils de mes utilisateurs si ceux-ci ont déjà installé les applications plus anciennes à partir du Windows Store ?
Si vos utilisateurs ont déjà installé les applications Portail d’entreprise Windows 8.1 ou Windows Phone 8.1 à partir du Windows Store, ils doivent être automatiquement mis à jour vers la nouvelle version sans que l’utilisateur ou vous-même n’ayez à intervenir. Si la mise à jour ne se produit pas, demandez à vos utilisateurs de vérifier s’ils ont activé les mises à jour automatiques pour les applications du Windows Store sur leurs appareils.   

## <a name="how-do-i-upgrade-my-sideloaded-windows-81-company-portal-app-to-the-windows-10-company-portal-app"></a>Comment mettre à niveau mon application de portail d’entreprise Windows 8.1 chargée indépendamment vers l’application Portail d’entreprise Windows 10 ?
Nous vous recommandons de supprimer l’affectation de l’application Portail d’entreprise Windows 8.1 en définissant l’action d’affectation sur « Désinstaller ». Une fois ce paramètre défini, l’application Portail d’entreprise Windows 10 peut être affectée à l’aide de l’une des options ci-dessus.  

Si vous avez besoin de charger une version test de l’application et que vous avez affecté le portail d’entreprise Windows 8.1 sans le signer avec le certificat Symantec, suivez les étapes de la section Affecter directement via Intune ci-dessus pour terminer la mise à niveau.

Si vous avez besoin de charger une version test de l’application et que vous avez signé et affecté le portail d’entreprise Windows 8.1 avec le certificat de signature de code Symantec, suivez les étapes décrites dans la section ci-dessous.  

## <a name="how-do-i-upgrade-my-signed-and-sideloaded-windows-phone-81-company-portal-app-or-windows-81-company-portal-app-to-the-windows-10-company-portal-app"></a>Comment mettre à niveau mon application Portail d’entreprise Windows 8.1 ou Windows Phone 8.1 chargée indépendamment et signée vers l’application Portail d’entreprise Windows 10 ?
Notre option de migration recommandée consiste à supprimer l’attribution existante de l’application Portail d’entreprise Windows Phone 8.1 ou de l’application Portail d’entreprise Windows 8.1 en définissant « Désinstaller » pour l’action d’attribution. Une fois ce paramètre défini, l’application Portail d’entreprise Windows 10 peut être affectée normalement.  

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

## <a name="next-steps"></a>Étapes suivantes

- [Guide pratique pour affecter des applications à des groupes](apps-deploy.md)

