---
title: Appareils pris en charge - Microsoft Intune
description: "Répertorie les plateformes d’appareils et navigateurs pris en charge par pour la gestion des appareils Intune"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 11/06/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5d1ac59c-a885-4276-8576-f3cf81c2d268
ms.reviewer: angrobe
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: b168cbf5282b4e016133d071c56c8abd54c2e23b
ms.sourcegitcommit: dc2595bec05206a826cd10cb834bf6043145c917
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/14/2017
---
# <a name="supported-devices-and-browsers"></a>Appareils et navigateurs pris en charge

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

Cet article est destiné aux administrateurs système responsables de la gestion des appareils de l’entreprise. Pour de l’aide sur l’installation de Intune sur votre téléphone, consultez [Utilisation d’appareils gérés pour votre travail](/intune-user-help/company-portal-frequently-asked-questions).

Avant de commencer la configuration de Microsoft Intune, passez en revue les conditions suivantes :

- [Appareils et ordinateurs pris en charge](#intune-supported-devices)
- [Liste des navigateurs web pris en charge pour l’utilisation d’Intune](#intune-supported-web-browsers)

Vous devez également vous familiariser avec [l’utilisation de la bande passante réseau Intune](network-bandwidth-use.md) ([portail classique](/intune-classic/get-started/network-bandwidth-use)).

## <a name="intune-supported-devices"></a>Appareils pris en charge par Intune

Vous pouvez gérer les appareils suivants avec la gestion des appareils mobiles Intune :

[!INCLUDE[mdm-supported-devices](./includes/mdm-supported-devices.md)]

### <a name="supported-samsung-knox-standard-devices"></a>Appareils Samsung KNOX Standard pris en charge

L’application Portail d’entreprise tente l’activation de Samsung KNOX lors de l’inscription à MDM si l’appareil figure dans la [liste des appareils KNOX pris en charge](https://www.samsungknox.com/knox-supported-devices/knox-workspace). Ceci permet d’éviter les erreurs d’activation de KNOX qui empêchent l’inscription à MDM. Les appareils qui ne prennent pas en charge l’activation de Samsung KNOX s’inscrivent en tant qu’appareils Android standard. Les appareils Samsung peuvent avoir des numéros de modèles qui prennent en charge KNOX, alors que d’autres ne le prennent pas en charge. Vérifiez la compatibilité de KNOX auprès du revendeur de votre appareil avant d’acheter et de déployer des appareils Samsung.

La liste suivante contient les modèles d’appareils Samsung qui ne prennent pas en charge KNOX et qui sont inscrits en tant qu’appareils Android natifs par l’application Portail d’entreprise pour Android :

| **Nom de l’appareil** | **Numéro de modèle de l’appareil** |
| --- | --- |
| Galaxy Avant | SM-G386T |
| Galaxy Core 2/Core 2 Duos | SM-G355H<br>SM-G355M |
| Galaxy Core Lite | SM-G3588V |
| Galaxy Core Prime | SM-G360H |
| Galaxy Core LTE | SM-G386F<br>SM-G386W |
| Galaxy Grand | GT-I9082L<br>GT-I9082<br>GT-I9080L |
| Galaxy Grand 3 | SM-G7200 |
| Galaxy Grand Neo | GT-I9060I |
| Galaxy Grand Prime Value Edition | SM-G531H |
| Galaxy J Max | SM-T285YD |
| Galaxy J1 | SM-J100H<br>SM-J100M<br>SM-J100ML |
| Galaxy J1 Ace | SM-J110F<br>SM-J110H |
| Galaxy J1 Mini | SM-J105M |
| Galaxy J2/J2 Pro | SM-J200H<br>SM-J210F |
| Galaxy J3 | SM-J320F<br>SM-J320FN<br>SM-J320H<br>SM-J320M |
| Galaxy K Zoom | SM-C115 |
| Galaxy Light | SGH-T399N |
| Galaxy Note 3 | SM-N9002<br>SM-N9009 |
| Galaxy Note 7/Note 7 Duos | SM-N930S<br>SM-N9300<br>SM-N930F<br>SM-N930T<br>SM-N9300<br>SM-N930F<br>SM-N930S<br>SM-N930T |
| Galaxy Note 10.1 3G | SM-P602 |
| Galaxy S2 Plus | GT-I9105P |
| Galaxy S3 Mini | SM-G730A<br>SM-G730V |
| Galaxy S3 Neo | GT-I9300<br>GT-I9300I |
| Galaxy S4 | SM-S975L |
| Galaxy S4 Neo | SM-G318ML |
| Galaxy S5 | SM-G9006W |
| Galaxy S6 Edge | 404SC |
| Galaxy Tab A 7.0&quot; | SM-T280<br>SM-T285 |
| Galaxy Tab 3 7&quot;/Tab 3 Lite 7&quot; | SM-T116<br>SM-T210<br>SM-T211 |
| Galaxy Tab 3 8.0&quot; | SM-T311 |
| Galaxy Tab 3 10.1&quot; | GT-P5200<br>GT-P5210<br>GT-P5220 |
| Galaxy Trend 2 Lite | SM-G318H |
| Galaxy V Plus | SM-G318HZ |
| Galaxy Young 2 Duos | SM-G130BU |

Vous ne pouvez pas utiliser Intune pour gérer les systèmes d’exploitation Windows Server.

### <a name="windows-pc-software-client"></a>Logiciel client pour PC Windows

Vous pouvez déployer et installer un [logiciel client Intune](/intune-classic/deploy-use/manage-windows-pcs-with-microsoft-intune) sur les PC Windows en guise d’alternative à l’inscription. Cette fonctionnalité est uniquement disponible dans le portail classique Intune. Vous pouvez utiliser le logiciel client Intune pour gérer des PC Windows 7 et versions ultérieures, à l’exception de Windows 10 Édition familiale.

<!--  ### Exchange ActiveSync management

You can manage [Exchange ActiveSync devices](/intune-classic/deploy-use/mobile-device-management-with-exchange-activesync-and-microsoft-intune) from the Intune console. This option provides a limited set of management capabilities when compared to the other methods. See [Capabilities of built-in Mobile Device Management in Office 365](https://support.office.com/article/Capabilities-of-built-in-Mobile-Device-Management-for-Office-365-a1da44e5-7475-4992-be91-9ccec25905b0) for a list of supported devices.  -->

## <a name="intune-supported-web-browsers"></a>Navigateurs web pris en charge par Intune

Différentes tâches administratives vous obligent à utiliser l’un des sites web d’administration suivants.

- [Portail Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Portail Azure](https://portal.azure.com/)

Les navigateurs suivants sont pris en charge pour ces portails :
- Microsoft Edge (dernière version)
- Microsoft Internet Explorer 11
- Safari (dernière version, Mac uniquement)
- Chrome (dernière version)
- Firefox (dernière version)

### <a name="intune-classic-portal"></a>Portail classique Intune

Les fonctionnalités spécifiques à la console classique Intune, telles que le client logiciel PC Intune et l’intégration avec les partenaires de protection contre les menaces Mobile, sont uniquement disponibles dans le portail classique Intune (https://manage.microsoft.com). Le portail classique Intune nécessite la prise en charge du navigateur Silverlight.

Les navigateurs Silverlight suivants prennent en charge la console Intune :
- Internet Explorer 10 ou version ultérieure
- Google Chrome (versions antérieures à la version 42)
- Mozilla Firefox avec Silverlight activé [En savoir plus](https://go.microsoft.com/fwlink/?linkid=836872)

> [!Note]
> Microsoft Edge et les navigateurs mobiles ne sont pas pris en charge pour le portail classique Intune, car ils ne prennent pas en charge [Microsoft Silverlight](https://msdn.microsoft.com/library/cc838158(v=vs.95).aspx).

Seuls les utilisateurs disposant d’autorisations d’administrateur de service ou les administrateurs clients ayant le rôle Administrateur général peuvent se connecter à ce portail. Pour accéder à la console d’administration, votre compte doit posséder une licence d’utilisation de Microsoft Intune et son état de connexion doit être **Autorisé**.
