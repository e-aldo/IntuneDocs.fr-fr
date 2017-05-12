---
title: "Configurer les paramètres Windows Update for Business - Intune | Intune Azure en préversion | Microsoft Docs"
description: "Intune Azure en préversion : découvrez comment configurer les paramètres Windows Update for Business dans Intune pour contrôler les mises à jour des appareils Windows 10."
keywords: 
author: dougeby
ms.author: dougeby
manager: angrobe
ms.date: 03/10/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 08f659cf-715e-4e10-9ab2-1bac3c6f2366
ms.reviewer: coryfe
ms.suite: ems
ms.translationtype: Human Translation
ms.sourcegitcommit: 3758df744311392528be01c826527c2a9d879975
ms.openlocfilehash: e825d47860924de1350299c8998d958ed68c0418
ms.contentlocale: fr-fr
ms.lasthandoff: 05/10/2017


---

# <a name="how-to-configure-windows-update-for-business-settings-with-microsoft-intune"></a>Configurer les paramètres Windows Update for Business avec Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

## <a name="introduction"></a>Introduction
Windows en tant que service est la nouvelle façon de fournir des mises à jour pour Windows 10. À partir de Windows 10, les nouvelles mises à jour de fonctionnalités et qualité incluent le contenu de toutes les mises à jour précédentes. Cela signifie que tant que vous avez installé la dernière mise à jour, vous savez que vos appareils Windows 10 sont entièrement à jour. À la différence des versions précédentes de Windows, vous devez maintenant installer la mise à jour complète au lieu d’une partie seulement.

En utilisant Windows Update for Business, vous pouvez simplifier l’expérience de gestion des mises à jour et vous ne devez plus approuver des mises à jour propres à des groupes d’appareils. Vous pouvez toujours gérer les risques dans votre environnement en configurant une stratégie de déploiement de mises à jour afin que Windows Update fasse en sorte que les mises à jour soient installées au moment opportun. Microsoft Intune permet de configurer les paramètres de mise à jour des appareils et vous donne la possibilité de reporter l’installation des mises à jour. Intune ne stocke pas les mises à jour, seulement l’attribution des stratégies de mise à jour. Les appareils accèdent directement à Windows Update. Utilisez Intune pour configurer et gérer les **anneaux de mise à jour Windows 10**. Un anneau de mise à jour contient un groupe de paramètres permettant de configurer le moment et la façon d’installer les mises à jour Windows 10. Par exemple, vous pouvez configurer les paramètres suivants :

- **Branche de maintenance Windows 10** : indiquez si vous souhaitez que des groupes d’appareils reçoivent les mises à jour à partir de Current Branch ou de Current Branch for Business.  
- **Deferral Settings (Paramètres de report)** : configurez les paramètres de report des mises à jour pour différer l’installation des mises à jour pour des groupes d’appareils. Vous avez alors un déploiement des mises à jour par étapes, ce qui vous permet d’examiner la progression tout au long du processus.
- **Suspension** : reportez l’installation des mises à jour si vous détectez un problème à tout moment lors du déploiement des mises à jour.
- **Fenêtre de maintenance** : configurez les heures d’installation des mises à jour.
- **Type de mise à jour** : choisissez le type des mises à jour installées. Par exemple, les mises à jour qualité, des fonctionnalités ou des pilotes.
- **Comportement d’installation** : ce paramètre configure la façon dont la mise à jour est installée. Par exemple, l’appareil redémarre-t-il automatiquement après l’installation ?
- **Peer downloading (Téléchargement d’homologues)** : vous pouvez spécifier s’il faut configurer le téléchargement d’homologues. Si cette option est activée, lorsqu’un appareil a terminé le téléchargement d’une mise à jour, les autres appareils peuvent télécharger la mise à jour à partir de celui-ci. Cela accélère le processus de téléchargement.

Une fois que vous avez créé les anneaux de mise à jour, affectez-les à des groupes d’appareils. En utilisant les anneaux de mise à jour, vous pouvez créer une stratégie de mise à jour qui reflète les besoins de votre entreprise. Pour plus d’informations, consultez [Gérer les mises à jour à l’aide de Windows Update for Business](https://technet.microsoft.com/itpro/windows/manage/waas-manage-updates-wufb).

## <a name="before-you-start"></a>Avant de commencer

- Pour mettre à jour les PC Windows 10, ceux-ci doivent exécuter au minimum Windows 10 Professionnel avec la mise à jour anniversaire de Windows.

- Windows Update prend en charge les versions suivantes de Windows 10 :
    - Windows 10
    - Windows 10 Collaboration (pour les appareils Surface Hub)

 Les appareils qui exécutent Windows 10 Mobile et Windows 10 Holographique ne sont pas pris en charge.

- Sur les appareils Windows, le paramètre **Commentaires et diagnostics** > **Données de diagnostic et d’utilisation** doit être défini au minimum sur **De base**.

    ![Paramètre Windows pour les données de diagnostic et d’utilisation](./media/telemetry-basic.png)

    Vous pouvez configurer ce paramètre manuellement, ou vous pouvez utiliser un profil de restriction d’appareils Intune pour Windows 10 et versions ultérieures. Pour ce faire, configurez le paramètre **Général** > **Envoi de données de diagnostic** sur au minimum **De base**. Pour plus d’informations sur les profils d’appareils, consultez [Guide pratique pour configurer des paramètres de restriction d’appareils](how-to-configure-device-restrictions.md).

- Dans la console d’administration Intune classique, quatre paramètres contrôlent le comportement des mises à jour logicielles. Ces paramètres font partie de la stratégie de configuration générale pour Windows 10 Desktop et les appareils mobiles :
    - **Autoriser les mises à jour automatiques**
    - **Autoriser les fonctionnalités préliminaires**
    - **Jour de l’installation planifiée**
    - **Heure de l’installation planifiée**

  La console classique possède également un nombre limité d’autres paramètres de mises à jour Windows 10 dans le profil de configuration des appareils. Si un de ces paramètres est configuré dans la console d’administration Intune classique lorsque vous migrez vers le portail Azure, nous vous recommandons de procéder comme suit :

1. Créez des anneaux de mise à jour Windows 10 dans le portail Azure avec les paramètres dont vous avez besoin. Le paramètre **Autoriser les fonctionnalités en version préliminaire** n’est pas pris en charge dans le portail Azure, car il n’est plus applicable aux dernières versions de Windows 10. Lorsque vous créez des anneaux de mise à jour, vous pouvez configurer les trois autres paramètres, ainsi que d’autres paramètres de mises à jour Windows 10.

  > [!NOTE]
  > Les paramètres de mises à jour Windows 10 créés dans la console classique ne sont pas affichés dans le portail Azure après la migration. Ils continuent toutefois à s’appliquer. Si vous avez migré un de ces paramètres et que vous modifiez la stratégie migrée à partir du portail Azure, ces paramètres sont supprimés de la stratégie.

2. Supprimez les paramètres de mise à jour dans la console classique. Une fois que vous avez migré vers le portail Azure et ajouté les mêmes paramètres à un anneau de mise à jour, vous devez supprimer les paramètres dans le portail classique pour éviter d’éventuels conflits de stratégies. Par exemple, lorsque le même paramètre est configuré avec des valeurs différentes, il y a un conflit et il n’existe aucun moyen simplifié de le savoir, car le paramètre configuré dans la console classique n’apparaît pas dans le portail Azure.

## <a name="how-to-create-and-assign-update-rings"></a>Guide pratique pour créer et affecter des anneaux de mise à jour

1. Connectez-vous au portail Azure.
2. Choisissez **Plus de Services** > **Surveillance + Gestion** > **Intune**.
3. Dans le panneau **Intune**, choisissez **Mises à jour logicielles**.
4. Dans le panneau **Mises à jour logicielles**, choisissez **Gérer** > **Anneaux de mise à jour Windows 10**.
5. Dans le volet présentant la liste de anneaux de mise à jour, choisissez **Créer**.
6. Dans le panneau **Créer un anneau de mise à jour**, indiquez le nom et une description facultative de l’anneau de mise à jour, puis choisissez **Paramètres**.
7. Dans le panneau **Paramètres**, configurez les informations suivantes :
    - **Branche de maintenance** : définissez la branche pour laquelle l’appareil reçoit les mises à jour Windows (Current Branch ou Current Branch for Business).
    - **Mises à jour Microsoft** : choisissez si vous voulez rechercher des mises à jour d’applications à partir de Microsoft Update.
    - **Pilotes Windows** : choisissez s’il faut ignorer les pilotes Windows Update au cours des mises à jour.
    - **Automatic update behavior (Comportement de mise à jour automatique)** : indiquez comment gérer le comportement de mise à jour automatique pour rechercher, télécharger et installer les mises à jour. Pour plus d’informations, consultez [Update/AllowAutoUpdate](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#update-allowautoupdate).
    - **Quality update deferral period (days)** (Période de report des mises à jour qualité (jours)) : spécifiez le nombre de jours pendant lesquels les mises à jour qualité sont reportées. Vous pouvez différer la réception de ces mises à jour qualité pour une période allant jusqu’à 30 jours à partir de leur publication.  

      Les mises à jour qualité sont en général des correctifs et des améliorations apportées aux fonctionnalités existantes de Windows. Elles sont généralement publiées le premier mardi de chaque mois, mais il se peut qu’elles le soient à d’autres moments par Microsoft. Vous pouvez définir si et pendant combien de temps vous souhaitez différer la réception des mises à jour qualité après leur disponibilité.
    - **Feature update deferral period (days)** (Période de report des mises à jour de fonctionnalités (jours)) : spécifiez le nombre de jours pendant lesquels les mises à jour de fonctionnalités sont reportées. Vous pouvez différer la réception de ces mises à jour de fonctionnalités pour une période allant jusqu’à 180 jours à partir de leur publication.

    Les mises à jour de fonctionnalités correspondent généralement à de nouvelles fonctionnalités de Windows. Une fois que vous avez configuré le paramètre **Branche de maintenance** (**CB** ou **CBB**), vous pouvez définir si et pendant combien de temps vous souhaitez différer la réception des mises à jour de fonctionnalités après leur mise à disposition par Microsoft dans Windows Update.

    Exemple :  
    **Si la branche de maintenance a pour valeur CB et que la période de report est de 30 jours** : supposons qu’une mise à jour de fonctionnalité est publiquement disponible sur Windows Update au format CB en janvier. L’appareil ne reçoit pas la mise à jour avant février (soit 30 jours plus tard).

    **Si la branche de maintenance a pour valeur CBB et que la période de report est de 30 jours** : supposons qu’une mise à jour de fonctionnalité est publiquement disponible sur Windows Update pour l’option CB en janvier. Quatre mois plus tard, en avril, la mise à jour de fonctionnalité en question est publiée pour l’option CBB. L’appareil reçoit la mise à jour de fonctionnalité 30 jours après l’option CBB et se met à jour en mai.

    - **Optimisation de la distribution** : choisissez la méthode avec laquelle les appareils téléchargent les mises à jour Windows. Pour plus d’informations, consultez [DeliveryOptimization/DEDownloadMode](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#deliveryoptimization-dodownloadmode).
8. Quand vous avez terminé, cliquez sur **OK**, puis, dans le panneau **Créer un anneau de mise à jour**, cliquez sur **Créer**.

Le nouvel anneau de mise à jour s’affiche dans la liste des anneaux de mises à jour.

1. Pour affecter l’anneau, dans la liste des anneaux de mise à jour, sélectionnez un anneau, puis sous l’onglet *Ring name (Nom de l’anneau)*, choisissez **Affectations**.
2. Sous l’onglet suivant, choisissez **Sélectionner des groupes**, puis choisissez les groupes auxquels vous souhaitez affecter cet anneau.
3. Quand vous avez terminé, choisissez **Sélectionner** pour terminer l’affectation.



## <a name="update-compliance-reporting"></a>Création de rapports sur la conformité des mises à jour
Vous pouvez surveiller les déploiements de mises à jour Windows 10 à l’aide d’une solution gratuite d’Operations Management Suite (OMS) appelée Conformité de la mise à jour. Pour plus d’informations, consultez [Analyse des mises à jour Windows avec la conformité de la mise à jour](https://technet.microsoft.com/itpro/windows/manage/update-compliance-monitor). Lorsque vous utilisez cette solution, vous pouvez déployer un ID commercial dans un des appareils Windows 10 gérés par Intune pour lequel vous souhaitez générer des rapports sur la conformité des mises à jour.

Dans la console Intune, vous pouvez utiliser les paramètres OMA-URI d’une stratégie personnalisée pour configurer l’ID commercial. Pour plus d’informations, consultez [Paramètres de stratégie Intune pour les appareils Windows 10 dans Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune).   

Le chemin d’accès OMA-URI (sensible à la casse) pour la configuration de l’ID commercial est le suivant : ./Vendor/MSFT/DMClient/Provider/ProviderID/CommercialID

Par exemple, vous pouvez utiliser les valeurs suivantes dans **Ajouter ou modifier un paramètre OMA-URI** :

- **Nom du paramètre** : ID commercial Windows Analytics
- **Description du paramètre** : configuration d’un ID commercial pour les solutions Windows Analytics
- **Type de données :**  chaîne
- **OMA-URI** (sensible à la casse) : ./Vendor/MSFT/DMClient/Provider/ProviderID/CommercialID
- **Valeur** : *utilisez le GUID indiqué sous l’onglet Télémétrie Windows dans votre espace de travail OMS*>

![Paramètre Windows pour les données de diagnostic et d’utilisation](./media/commID.png)

<!--
1. Sign into the Azure portal.
2. Choose **More Services** > **Monitoring + Management** > **Intune**.
3. On the **Intune** blade, choose **Software Updates**.
4. On the **Software Updates** blade, choose **Overview**. From here you can see general information about the status of any update rings you assigned.
4. On the **Windows 10 Updates** blade, choose **Monitor** > **Update ring deployment for devices**, **Update ring deployment for users**, or **Per-setting deployment state** to view more detailed information about update ring assignments.
-->





## <a name="how-to-pause-updates"></a>Guide pratique pour suspendre des mises à jour
Vous pouvez suspendre la réception des mises à jour qualité ou de fonctionnalités d’un appareil pendant une période allant jusqu’à 35 jours à partir du moment où vous interrompez les mises à jour. Une fois que le nombre maximal de jours s’est écoulé, la fonctionnalité mise en pause expire automatiquement et l’appareil recherche les mises à jour applicables dans Windows Update. Suite à cette analyse, vous pouvez suspendre à nouveau les mises à jour.
1. Connectez-vous au portail Azure.
2. Choisissez **Plus de Services** > **Surveillance + Gestion** > **Intune**.
3. Dans le panneau **Intune**, choisissez **Mises à jour logicielles**.
4. Dans le panneau **Mises à jour logicielles**, choisissez **Gérer** > **Anneaux de mise à jour Windows 10**.
5. Dans le volet affichant la liste des anneaux de mise à jour, choisissez l’anneau que vous souhaitez suspendre, puis sélectionnez **...** > **Suspendre les mises à jour qualité** > ou **Suspendre les mises à jour des fonctionnalités**, selon le type de mise à jour que vous souhaitez suspendre.

> [!IMPORTANT]
> Lorsque vous exécutez une commande de suspension, les appareils la reçoivent lorsqu’ils consultent à nouveau le service. Il se peut qu’ils installent une mise à jour planifiée avant d’effectuer la vérification auprès du service.
> En outre, si un appareil cible est désactivé lorsque vous émettez la commande de suspension, lorsque vous l’allumez, il peut télécharger et installer les mises à jour planifiées avant d’effectuer les vérifications avec Intune.

