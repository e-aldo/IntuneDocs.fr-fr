---
title: "Importer des paramètres Wi-Fi pour Windows 8.1 et versions ultérieures"
titleSuffix: Azure portal
description: "Comment importer des paramètres Wi-Fi de Windows dans un profil Wi-Fi Intune."
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 1/25/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 5b4b77f9c9c1c957e3332c20e010a5e8e8ec2b56
ms.sourcegitcommit: 93622d740cbd12043eedc25a9699cc4256e23e7e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/01/2018
---
# <a name="how-to-import-wi-fi-settings-for-windows-81-and-later-devices-in-microsoft-intune"></a>Guide pratique pour importer des paramètres Wi-Fi pour appareils Windows 8.1 et versions ultérieures dans Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Pour les appareils qui exécutent Windows 8.1, Windows 10 Desktop ou Mobile, ou Windows Holographic for Business, vous pouvez importer un profil de configuration Wi-Fi précédemment exporté dans un fichier.

## <a name="export-wi-fi-settings-from-a-windows-device"></a>Exportation des paramètres Wi-Fi depuis un appareil Windows

Dans Windows, recourez à l’utilitaire **netsh wlan** pour exporter un profil Wi-Fi existant dans un fichier XML lisible par Intune. Sur un ordinateur Windows où le profil Wi-Fi requis est déjà installé, utilisez la procédure suivante.
1. Créez un dossier local pour les profils Wi-Fi exportés, comme **c:\WiFi**.
1. Ouvrez une invite de commandes en tant qu’administrateur.
1. Exécutez la commande **netsh wlan show profiles** et notez le nom du profil que vous voulez exporter. Dans cet exemple, le nom du profil est **WiFiName**.
1. Exécutez cette commande : **netsh wlan export profile name="ProfileName" folder=c:\Wifi**. Elle crée un fichier de profil Wi-Fi nommé **Wi-Fi-WiFiName.xml** dans votre dossier cible.

## <a name="import-the-wi-fi-settings-into-intune"></a>Importation des paramètres Wi-Fi dans Intune

1. Connectez-vous au portail Azure.
2. Choisissez **Plus de Services** > **Surveillance + Gestion** > **Intune**.
3. Dans le panneau **Intune**, choisissez **Configuration de l’appareil**.
2. Dans le panneau **Configuration de l’appareil**, choisissez **Gérer** > **Profils**.
3. Dans le panneau de profils, cliquez sur **Créer un profil**.
4. Dans le panneau **Créer un profil**, entrez un **Nom** et une **Description** pour le profil de restriction de l’appareil.

   > [!WARNING]
   > Le nom **doit** être le même que l’attribut de nom dans le fichier XML du profil Wi-Fi, sinon la commande échoue.

5. À partir de la liste déroulante **Plateforme**, sélectionnez **Windows 8.1 et versions ultérieures**.
6. À partir de la liste déroulante de types **Profil**, choisissez **Importation Wi-Fi**.
7. Dans le panneau **Wi-Fi de base**, configurez les paramètres suivants :
    - **Nom de connexion** : saisissez le nom de la connexion Wi-Fi. Ce nom s’affiche pour les utilisateurs finaux quand ils parcourent les réseaux Wi-Fi disponibles.
    - **XML du profil** : cliquez sur le bouton Parcourir pour sélectionner le fichier XML contenant les paramètres de profil Wi-Fi que vous voulez importer dans Intune.
    - **Contenu du fichier** : affiche le code XML du profil de configuration que vous avez sélectionné.
8. Lorsque vous avez terminé, revenez au panneau **Créer un profil** et appuyez sur **Créer**.

Le profil est créé et s’affiche dans le panneau de la liste des profils.
