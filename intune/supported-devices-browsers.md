---
title: Appareils pris en charge - Microsoft Intune
description: "Répertorie les plateformes d’appareils et navigateurs pris en charge par pour la gestion des appareils Intune"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 06/07/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5d1ac59c-a885-4276-8576-f3cf81c2d268
ms.reviewer: angrobe
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: df9c4c0a0a23740bf9df4c13e34b8752838aa99a
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/01/2017
---
# <a name="supported-devices-and-browsers"></a>Appareils et navigateurs pris en charge

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

Cet article est destiné aux administrateurs système responsables de la gestion des appareils de l’entreprise. Pour de l’aide sur l’installation de Intune sur votre téléphone, consultez [Utilisation d’appareils gérés pour votre travail](/intune-user-help/company-portal-frequently-asked-questions).

Avant de commencer la configuration de Microsoft Intune, passez en revue les conditions suivantes :

- [Appareils et ordinateurs pris en charge](#intune-supported-devices)
- [Liste des navigateurs web pris en charge pour l’utilisation d’Intune](#intune-supported-web-browsers)

Vous devez également vous familiariser avec l'[utilisation de la bande passante réseau Intune](network-bandwidth-use.md) ([console classique](/intune-classic/get-started/network-bandwidth-use)).

## <a name="intune-supported-devices"></a>Appareils pris en charge par Intune

Vous pouvez gérer les appareils suivants avec la gestion des appareils mobiles Intune :

[!INCLUDE[mdm-supported-devices](./includes/mdm-supported-devices.md)]

Vous ne pouvez pas utiliser Intune pour gérer les systèmes d’exploitation Windows Server.

### <a name="windows-pc-software-client"></a>Logiciel client pour PC Windows

Vous pouvez déployer et installer un [logiciel client Intune](/intune-classic/deploy-use/manage-windows-pcs-with-microsoft-intune) sur les PC Windows en guise d’alternative à l’inscription. Cette fonctionnalité est uniquement disponible dans la console classique Intune. Vous pouvez utiliser le logiciel client Intune pour gérer des PC Windows 7 et versions ultérieures, à l’exception de Windows 10 Édition familiale.

<!--  ### Exchange ActiveSync management

You can manage [Exchange ActiveSync devices](/intune-classic/deploy-use/mobile-device-management-with-exchange-activesync-and-microsoft-intune) from the Intune console. This option provides a limited set of management capabilities when compared to the other methods. See [Capabilities of built-in Mobile Device Management in Office 365](https://support.office.com/article/Capabilities-of-built-in-Mobile-Device-Management-for-Office-365-a1da44e5-7475-4992-be91-9ccec25905b0) for a list of supported devices.  -->

## <a name="intune-supported-web-browsers"></a>Navigateurs web pris en charge par Intune

Différentes tâches administratives vous obligent à utiliser l’un des sites web d’administration suivants.

- [Portail Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Portail Intune](https://portal.azure.com/)

Les navigateurs suivants sont pris en charge pour ces portails :
- Microsoft Edge (dernière version)
- Microsoft Internet Explorer 11
- Safari (dernière version, Mac uniquement)
- Chrome (dernière version)
- Firefox (dernière version)

### <a name="intune-classic-portal"></a>Portail classique Intune

Les fonctionnalités spécifiques à la console classique Intune telles que le client logiciel PC Intune et l’intégration avec les partenaires de protection contre les menaces Mobile sont uniquement disponibles dans le portail classique (https://manage.microsoft.com). La console classique Intune nécessite la prise en charge du navigateur Silverlight.

Les navigateurs Silverlight suivants prennent en charge la console classique Intune :
- Internet Explorer 10 ou version ultérieure
- Google Chrome (versions antérieures à la version 42)
- Mozilla Firefox avec Silverlight activé [En savoir plus](https://go.microsoft.com/fwlink/?linkid=836872)

> [!Note]
> Microsoft Edge et les navigateurs mobiles ne sont pas pris en charge pour la console classique Intune, car ils ne prennent pas en charge [Microsoft Silverlight](https://msdn.microsoft.com/library/cc838158(v=vs.95).aspx).


Seuls les utilisateurs disposant d’autorisations d’administrateur de service ou les administrateurs clients ayant le rôle Administrateur général peuvent se connecter à ce portail. Pour accéder à la console d’administration, votre compte doit posséder une licence d’utilisation de Microsoft Intune et son état de connexion doit être **Autorisé**.
