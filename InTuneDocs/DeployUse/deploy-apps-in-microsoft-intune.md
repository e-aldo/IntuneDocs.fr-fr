---
title: "Déployer des applications | Microsoft Intune"
description: 
keywords: 
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3b42019e-73da-4538-a496-212f11d5bf9b
ms.reviewer: mghadial
ms.suite: ems
ms.sourcegitcommit: c95a776e79cf3e1c7009d6e27f8f50482434d298
ms.openlocfilehash: 46562ed3463c4a23a511eb5c7f28a0b11e84f421

---
# Déployer des applications dans Microsoft Intune

Utilisez les informations de cette rubrique pour vous aider à déployer des applications Microsoft Intune.


## Déployer une application
Dans cette procédure, vous allez déployer l'application vers les appareils ou les utilisateurs sélectionnés.

### Pour déployer une application

1. Dans la [console d’administration Microsoft Intune](https://manage.microsoft.com), cliquez sur **Applications** &gt; **Applications** pour afficher la liste des applications que vous gérez.

2.  Sélectionnez l’application à déployer, puis cliquez sur **Gérer le déploiement**.

3.  Dans la boîte de dialogue *&lt;nom de l’application&gt;*, tout d’abord, dans la page **Sélectionner des groupes**, choisissez les groupes d’utilisateurs ou d’appareils vers lesquels vous souhaitez déployer l’application.

4.  Dans la page **Action de déploiement**, configurez les paramètres suivants :

    - **Approbation** : indiquez si le déploiement est :
        - **Requis** (installation obligatoire)
        - **Disponible** (les utilisateurs effectuent l’installation à la demande à partir du portail d’entreprise)
        - **Non applicable** (l’application n’est pas installée ni affichée dans le portail d’entreprise)
        - **Désinstaller** (l’application est désinstallée des appareils ciblés).
    - **Échéance** : pour les installations requises, choisissez le délai de déploiement de l’application. Vous pouvez choisir l’une des valeurs prédéfinies ou sélectionner **Personnalisé** pour configurer votre propre échéance.

5. Si l’application que vous déployez peut être configurée par une stratégie de gestion des applications mobiles, la page **Gestion des applications mobiles** s’affiche. Dans cette page, choisissez la stratégie de gestion des applications mobiles que vous souhaitez associer à cette application.

    [Découvrez quelles applications Microsoft sont compatibles avec les stratégies de gestion des applications mobiles.](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx)

6. Si l’application que vous déployez est compatible avec les profils VPN Intune, la page **Profil VPN** s’affiche. Dans cette page, vous pouvez choisir d'associer des applications iOS à un profil VPN que vous avez déployé. La connexion VPN s'ouvre automatiquement lorsque l'application est lancée. Pour rendre un profil VPN disponible, le paramètre de profil **Par VPN d’application** doit être activé.
 Pour plus d’informations sur la façon de configurer des profils VPN, notamment sur la prise en charge de l’association de profils à des applications, consultez [Aider les utilisateurs à se connecter à leur travail à l’aide de profils VPN avec Microsoft Intune](vpn-connections-in-microsoft-intune.md).

## Exemple

Dans cet exemple, vous avez déployé l’application en tant qu’application **Disponible** sur un appareil iOS.
Elle s’affichera dans le portail d’entreprise, à partir duquel les utilisateurs pourront l’installer sur leur appareil. Par exemple, dans cette capture d’écran, l’application Bing pour iOS a été déployée à l’aide du type d’installation **Lien externe**, avec une icône personnalisée, et l’option **Affiche comme application proposée et la met en avant dans le portail d’entreprise** a été sélectionnée.
    ![Application disponible iOS](./media/available-install-on-iOS.png)

Si vous avez déployé l’application comme application **Requise** sur un appareil iOS, l’utilisateur recevra une notification indiquant qu’une application est prête à être installée. Par exemple, dans cette capture d’écran, l’application Dossiers de travail pour iOS a été déployée à l’aide du type d’installation **Application iOS gérée à partir de l’App Store**.
    ![Application requise iOS](./media/iOS-Required-install.PNG)

## Étapes suivantes

Après avoir déployé une application, vous pouvez surveiller sa progression. Pour plus d’informations, consultez [Monitor apps in Microsoft Intune](monitor-apps-in-microsoft-intune.md) (Surveiller des applications dans Microsoft Intune).



<!--HONumber=Jun16_HO2-->


