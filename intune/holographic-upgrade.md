---
title: Mettre à niveau Windows Holographique vers Windows Holographic for Business
titleSuffix: Microsoft Intune
description: Découvrir comment mettre à niveau les appareils exécutant Windows Holographique vers Windows Holographic for Business
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 3/6/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 08763aa527f24ff7b357603be5e3bd4da5083b45
ms.sourcegitcommit: dbea918d2c0c335b2251fea18d7341340eafd673
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/26/2018
---
# <a name="upgrade-devices-running-windows-holographic-to-windows-holographic-for-business"></a>Mettre à niveau les appareils exécutant Windows Holographique vers Windows Holographic for Business


Pour gérer les appareils qui exécutent Windows Holographique avec Microsoft Intune, vous devez mettre à niveau les appareils Windows Holographique vers Windows Holographic for Business. Vous pouvez créer un profil Mise à niveau d’édition pour effectuer la mise à niveau. Pour Microsoft HoloLens, vous pouvez acheter Commercial Suite afin d’obtenir la licence nécessaire pour la mise à niveau. Pour plus d’informations, consultez [Déverrouiller les fonctionnalités de Windows Holographic for Business](https://docs.microsoft.com/en-us/hololens/hololens-upgrade-enterprise).

## <a name="to-set-up-an-edition-upgrade-device-configuration-profile"></a>Pour installer un profil de configuration d’appareil de mise à niveau d’édition

1. Connectez-vous au [portail Azure](https://portal.azure.com) avec votre compte d’administrateur.


2.  Cliquez sur **Configuration de l’appareil**, **Profils**, puis cliquez sur **+ Créer un profil**.

    ![Créer un profil](media/Holographic-create-profile.png)

3.  Dans la page **Créer un profil**, tapez un nom pour le profil, sélectionnez **Windows 10 et versions ultérieures** comme plateforme, puis sélectionnez **Mise à niveau d’édition** comme type de profil. Cliquez sur **Configuration des paramètres**.

5. Dans la page **Mise à niveau d’édition**, dans **Édition vers laquelle mettre à niveau**, sélectionnez **Windows 10 Holographic for Business**. Dans **Fichier de licence**, recherchez et sélectionnez le fichier de licence XML qui vous a été fourni.

    ![Entrer le nom du fichier XML](media/Holographic-edition-upgrade.png)
 
5.  Cliquez sur **OK**, puis sur **Créer** pour créer le profil.


## <a name="deploy-the-edition-upgrade-policy"></a>Déployer la stratégie de mise à niveau d’édition

Ensuite, vous affectez le profil de mise à niveau d’édition aux groupes ou appareils sélectionnés.

1. Dans le profil que vous avez créé dans les étapes précédentes, cliquez sur **Affectations**.

2. Dans la page **Affectations**, sélectionnez les groupes d’utilisateurs et les appareils à inclure et exclure avec la stratégie.

![Inclure et exclure des groupes](media/Holographic-groups.PNG)

Quand ces utilisateurs ou appareils sont inscrits dans Intune, le profil de mise à niveau d’édition est appliqué. 

## <a name="next-steps"></a>Étapes suivantes

Pour plus d'informations sur les groupes, consultez [Bien démarrer avec les groupes](get-started-groups.md).


