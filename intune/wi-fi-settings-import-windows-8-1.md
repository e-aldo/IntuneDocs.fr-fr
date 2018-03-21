---
title: "Importer des paramètres Wi-Fi pour Windows 8.1 et versions ultérieures"
titleSuffix: Microsoft Intune
description: "Comment importer des paramètres Wi-Fi de Windows dans un profil Wi-Fi Intune."
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 03/02/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 890a10ecf4212656c189adaf46bb2839898758c1
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/08/2018
---
# <a name="import-wi-fi-settings-for-windows-81-and-later-devices-in-microsoft-intune"></a>Importer des paramètres Wi-Fi pour appareils Windows 8.1 et ultérieur dans Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Pour les appareils qui exécutent Windows 8.1, Windows 10 Desktop ou Mobile, ou Windows Holographic for Business, vous pouvez importer un profil de configuration Wi-Fi précédemment exporté dans un fichier.

## <a name="export-wi-fi-settings-from-a-windows-device"></a>Exportation des paramètres Wi-Fi depuis un appareil Windows

Dans Windows, recourez à l’utilitaire **netsh wlan** pour exporter un profil Wi-Fi existant dans un fichier XML lisible par Intune. Sur un ordinateur Windows où le profil Wi-Fi requis est déjà installé, utilisez la procédure suivante.
1. Créez un dossier local pour les profils Wi-Fi exportés, comme **c:\WiFi**.
1. Ouvrez une invite de commandes en tant qu’administrateur.
1. Exécutez la commande **netsh wlan show profiles** et notez le nom du profil que vous voulez exporter. Dans cet exemple, le nom du profil est **WiFiName**.
1. Exécutez cette commande : **netsh wlan export profile name="ProfileName" folder=c:\Wifi**. Elle crée un fichier de profil Wi-Fi nommé **Wi-Fi-WiFiName.xml** dans votre dossier cible.

## <a name="import-the-wi-fi-settings-into-intune"></a>Importation des paramètres Wi-Fi dans Intune

1. Connectez-vous au [portail Azure](https://portal.azure.com).
2. Choisissez **Tous les services** > **Intune**. Intune se trouve dans la section **Monitoring + Gestion**.
3. Dans le volet **Intune**, choisissez **Configuration de l’appareil**.
4. Dans le volet **Configuration de l’appareil**, sous la section **Gérer**, choisissez **Profils**.
5. Dans le volet Profils, cliquez sur **Créer un profil**.
6. Dans le volet **Créer un profil**, entrez un **Nom** et une **Description** du profil de restriction d’appareil.


   > [!WARNING]
   > Le nom **doit** être le même que l’attribut de nom dans le fichier XML du profil Wi-Fi, sinon la commande échoue.

7. À partir de la liste déroulante **Plateforme**, sélectionnez **Windows 8.1 et versions ultérieures**.
8. À partir de la liste déroulante **Type de profil**, choisissez **Importation Wi-Fi**.
9. Dans le volet **Wi-Fi**, configurez les paramètres suivants :
    - **Nom de connexion** : saisissez le nom de la connexion Wi-Fi. Ce nom s’affiche pour les utilisateurs finaux quand ils parcourent les réseaux Wi-Fi disponibles.
    - **XML du profil** : cliquez sur le bouton Parcourir pour sélectionner le fichier XML contenant les paramètres de profil Wi-Fi que vous voulez importer dans Intune.
    - **Contenu du fichier** : affiche le code XML du profil de configuration que vous avez sélectionné.
10. Lorsque vous avez terminé, choisissez **OK**, revenez au volet **Créer un profil** et sélectionnez **Créer**.

Le profil est créé et apparaît dans le volet de la liste des profils.
