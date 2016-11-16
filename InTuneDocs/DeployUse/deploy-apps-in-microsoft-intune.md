---
title: "Comment déployer des applications | Microsoft Intune"
description: "Utilisez les informations de cette rubrique pour déployer des applications avec Microsoft Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 08/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3b42019e-73da-4538-a496-212f11d5bf9b
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: a4f7a503417938eabb4334757dcf12a63f082fd3
ms.openlocfilehash: 6ae7bd35157da261d0627f70933fe2a808f9e677

---
# Déploiement d’applications dans Microsoft Intune

Utilisez les informations de cette rubrique pour déployer des applications avec Microsoft Intune.


## Déployer une application
Dans cette procédure, vous allez déployer une application sur des groupes d’appareils ou d’utilisateurs sélectionnés.

### Pour déployer une application

1. Dans la [console d’administration Microsoft Intune](https://manage.microsoft.com), cliquez sur **Applications** &gt; **Applications** pour afficher la liste des applications que vous gérez.

2.  Sélectionnez l’application à déployer, puis cliquez sur **Gérer le déploiement**.

3.  Dans la boîte de dialogue *&lt;Nom de l’application&gt;*, dans la page **Sélectionner des groupes**, sélectionnez les groupes d’utilisateurs ou d’appareils sur lesquels vous souhaitez déployer l’application.

4.  Dans la page **Action de déploiement**, configurez les paramètres suivants :

    - **Approbation** : indiquez si le déploiement est :
        - **Requis** (installation obligatoire)
        - **Disponible** (les utilisateurs effectuent l’installation à la demande à partir du portail d’entreprise)
        - **Non applicable** (l’application n’est pas installée ni affichée dans le portail d’entreprise)
        - **Désinstaller** (l’application est désinstallée des appareils ciblés)
    - **Échéance** : pour les installations requises, choisissez le délai de déploiement de l’application. Vous pouvez choisir l’une des valeurs prédéfinies ou sélectionner l’option **Personnalisé** pour configurer votre propre échéance.

5. Si l’application que vous déployez peut être configurée par une stratégie de gestion des applications mobiles, la page **Gestion des applications mobiles** s’affiche. Dans cette page, choisissez la stratégie de gestion des applications mobiles que vous souhaitez associer à cette application.

    [Découvrez quelles applications Microsoft sont compatibles avec les stratégies de gestion des applications mobiles.](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx)

6. Si l’application que vous déployez est compatible avec les profils VPN Intune, la page **Profil VPN** s’affiche. Dans cette page, vous pouvez choisir d’associer des applications iOS à un profil VPN que vous avez déployé. La connexion VPN s’ouvre automatiquement lorsque l’application est lancée. Pour rendre un profil VPN disponible, le paramètre de profil **Par VPN d’application** doit être activé.
 Pour obtenir des informations sur la configuration des profils VPN, y compris sur l’association de profils à des applications, consultez la page [Connexions VPN dans Microsoft Intune](vpn-connections-in-microsoft-intune.md).

## Exemple

Dans cet exemple, vous avez déployé l’application en tant qu’application **Disponible** sur un appareil iOS.
L’application s’affiche sur les appareils des utilisateurs dans le Portail d’entreprise, et les utilisateurs peuvent l’installer depuis cet emplacement.

Par exemple, dans cette capture d’écran, l’application Bing pour iOS a été déployée via le type d’installation **Lien externe**, avec une icône personnalisée. L’option **Affiche comme application proposée et la met en avant dans le portail d’entreprise** a été sélectionnée.  
![Application disponible iOS](./media/available-install-on-iOS.png)

Si vous avez déployé l’application comme application **Requise** sur un appareil iOS, l’utilisateur recevra une notification indiquant qu’une application est prête à être installée. Par exemple, dans cette capture d’écran, l’application Dossiers de travail pour iOS a été déployée via le type d’installation **Application iOS gérée à partir de l’App Store**.  
![Application requise iOS](./media/iOS-Required-install.PNG)

## Étapes suivantes

Après avoir déployé une application, vous pouvez surveiller sa progression. Pour plus d’informations, consultez [Monitor apps in Microsoft Intune](monitor-apps-in-microsoft-intune.md) (Surveiller des applications dans Microsoft Intune).



<!--HONumber=Oct16_HO4-->


