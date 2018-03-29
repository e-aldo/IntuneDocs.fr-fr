---
title: Rechercher un nom de famille de packages (NFP) pour un VPN par application
description: Recherchez un nom de famille de packages (PFN) pour configurer un VPN par application.
keywords: ''
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 10/25/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 74643d1d-4fd9-4cff-ac79-1a42281d2f76
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: tycast
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: de1a5beafae900a21f685cf1daeb2302cbf245b3
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/22/2018
---
# <a name="find-a-package-family-name-pfn-for-per-app-vpn-configuration"></a>Rechercher un nom de famille de packages (PFN) pour la configuration d’un VPN par application

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Il existe deux façons de trouver un PFN pour pouvoir configurer un VPN par application.

## <a name="find-a-pfn-for-an-app-thats-installed-on-a-windows-10-computer"></a>Rechercher un NFP pour une application installée sur un ordinateur Windows 10

Si l’application que vous utilisez est déjà installée sur un ordinateur Windows 10, vous pouvez utiliser l’applet de commande PowerShell [Get-AppxPackage](https://technet.microsoft.com/library/hh856044.aspx) pour obtenir le PFN.

La syntaxe de Get-AppxPackage est la suivante :

` Parameter Set: __AllParameterSets`
` Get-AppxPackage [[-Name] <String> ] [[-Publisher] <String> ] [-AllUsers] [-User <String> ] [ <CommonParameters>]`

> [!NOTE]
Vous devrez peut-être exécuter PowerShell en tant qu’administrateur pour récupérer le PFN.

Par exemple, pour obtenir des informations sur toutes les applications universelles installées sur l’ordinateur, utilisez `Get-AppxPackage`.

Pour obtenir des informations sur une application dont vous connaissez le nom ou une partie du nom, utilisez `Get-AppxPackage *<app_name>`. Notez l’utilisation du caractère générique, particulièrement utile si vous n’êtes pas sûr du nom complet de l’application. Par exemple, pour obtenir les informations pour OneNote, utilisez `Get-AppxPackage *OneNote`.


Voici les informations récupérées pour OneNote :

`Name                   : Microsoft.Office.OneNote`

`Publisher              : CN=Microsoft Corporation, O=Microsoft Corporation, L=Redmond, S=Washington, C=US`

`Architecture           : X64`

`ResourceId             :`

`Version                : 17.6769.57631.0`

`PackageFullName        : Microsoft.Office.OneNote_17.6769.57631.0_x64__8wekyb3d8bbwe`

`InstallLocation        : C:\Program Files\WindowsApps`

`\Microsoft.Office.OneNote_17.6769.57631.0_x64__8wekyb3d8bbwe`

`IsFramework            : False`

**`PackageFamilyName      : Microsoft.Office.OneNote_8wekyb3d8bbwe`**

`PublisherId            : 8wekyb3d8bbwe`



## <a name="find-a-pfn-if-the-app-is-not-installed-on-a-computer"></a>Rechercher un NFP si l’application n’est pas installée sur un ordinateur

1.  Accédez à https://www.microsoft.com/store/apps.
2.  Entrez le nom de l’application dans la barre de recherche. Pour notre exemple, recherchez OneNote.
3.  Choisissez le lien vers l’application. Notez que l’URL se termine par une série de lettres. Dans notre exemple, l’URL ressemble à ceci : `https://www.microsoft.com/store/apps/onenote/9wzdncrfhvjl`.
4.  Sous un autre onglet, collez l’URL suivante : `https://bspmts.mp.microsoft.com/v1/public/catalog/Retail/Products/<app id>/applockerdata`. Remplacez `<app id>` par l’ID d’application que vous avez obtenu de https://www.microsoft.com/store/apps : la série de lettres à la fin de l’URL à l’étape 3. Dans notre exemple avec OneNote, vous devez coller : `https://bspmts.mp.microsoft.com/v1/public/catalog/Retail/Products/9wzdncrfhvjl/applockerdata`.

Microsoft Edge affiche les informations souhaitées. Dans Internet Explorer, choisissez **Ouvrir** pour visualiser les informations. La valeur du PFN figure sur la première ligne. Voici les résultats de notre exemple :


`{`
`  "packageFamilyName": "Microsoft.Office.OneNote_8wekyb3d8bbwe",`
`  "packageIdentityName": "Microsoft.Office.OneNote",`
`  "windowsPhoneLegacyId": "ca05b3ab-f157-450c-8c49-a1f127f5e71d",`
`  "publisherCertificateName": "CN=Microsoft Corporation, O=Microsoft Corporation, L=Redmond, S=Washington, C=US"`
`}`
