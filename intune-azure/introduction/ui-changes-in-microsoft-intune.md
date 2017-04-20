---
title: "Où se trouve ma fonctionnalité Intune dans Azure ?"
titleSuffix: Intune Azure preview
description: "Préversion d’Intune Azure : Vous aide à trouver les fonctionnalités Intune dans la console Azure."
keywords: 
author: dagerrit
ms.author: dagerrit
manager: angrobe
ms.date: 03/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 6a6b64465c95a3edd6fc2e2d4ae3da80ba3367ee
ms.openlocfilehash: 92bd41aa4acc02e67e983c68f818bd656b0b9608
ms.lasthandoff: 04/12/2017


---
# <a name="where-did-my-intune-feature-go-in-azure"></a>Où se trouve ma fonctionnalité Intune dans Azure ?
Lors du transfert d’Intune vers le portail Azure, nous en avons profité pour organiser certaines tâches de manière plus logique. Toutefois, ces améliorations nécessitent de se familiariser avec la nouvelle organisation. Nous avons donc créé ce guide de référence pour ceux d’entre vous qui connaissent parfaitement Intune dans la console classique et qui se demandent comment effectuer certaines tâches spécifiques dans Intune sur Azure. Si cet article ne couvre pas l’une des fonctionnalités que vous recherchez, laissez-nous un commentaire à la fin de l’article pour que nous puissions le mettre à jour.
## <a name="quick-reference-guide"></a>Guide de référence rapide
|Fonctionnalité |Chemin dans la console classique|Chemin dans Intune sur Azure| |------------||---------------|---------------|
|Programme d’inscription des appareils (DEP) |Administration > Gestion des appareils mobiles > iOS et Mac OS X > Programme d’inscription des appareils|[Inscription d’appareil > Inscription Apple > Jeton du Programme d’inscription](#where-did-apple-dep-go) |
|Programme d’inscription des appareils (DEP)| Administration > Gestion des appareils mobiles > iOS et Mac OS X > Programme d’inscription des appareils |[Inscription d’appareil > Inscription Apple > Numéros de série de programme d’inscription](#where-did-apple-dep-go) |
|Règles d’inscription |Administration > Gestion des appareils mobiles > Règles d’inscription|[Inscription d’appareil > Restrictions d’inscription](#where-did-enrollment-rules-go) |
|Groupes par numéro de série iOS |Groupes > Tous les appareils > Appareils d’entreprise préinscrits > Par numéro de série iOS|[Inscription d’appareil > Inscription Apple > Numéros de série de programme d’inscription](#where-did-corporate-pre-enrolled-devices-go) |
|Groupes par numéro de série iOS |Groupes > Tous les appareils > Appareils d’entreprise préinscrits > Par numéro de série iOS| [Inscription d’appareil > Inscription Apple > Numéros de série AC](#where-did-corporate-pre-enrolled-devices-go)|
|Groupes par IMEI (toutes les plateformes)| Groupes > Tous les appareils > Appareils d’entreprise préinscrits > Par IMEI (toutes les plateformes) | [Inscription d’appareil > Identificateurs d’appareil d’entreprise](#by-imei-all-platforms)|
| Profil d’inscription d’appareil professionnel| Stratégie > Inscription d’appareil professionnel | [Inscription d’appareil > Inscription Apple > Profils du programme d’inscription](#where-did-corporate-pre-enrolled-devices-go) |
| Profil d’inscription d’appareil professionnel | Stratégie > Inscription d’appareil professionnel | [Inscription d’appareil > Inscription Apple > Profils AC](#where-did-corporate-pre-enrolled-devices-go) |


## <a name="where-do-i-manage-groups"></a>Où gérer les groupes ?
Intune sur Azure utilise [Azure Active Directory (AD)](https://docs.microsoft.com/azure/active-directory/active-directory-groups-create-azure-portal) pour gérer les groupes.

## <a name="where-did-enrollment-rules-go"></a>Où sont passées les règles d’inscription ?
Dans la console classique, vous pouviez définir des règles régissant l’inscription MDM des appareils Windows et macOS mobiles et récents :

![Image des règles d’inscription des appareils mobiles classiques](./media/ui-changes/01-classic-rules.png)

Ces règles s’appliquaient à tous les utilisateurs de votre compte Intune sans exception. Dans le portail Azure, ces règles apparaissent désormais dans deux types de stratégies distincts : les restrictions de type d’appareil et les restrictions de limite d’appareils :

![Image des restrictions d’inscription d’appareils mobiles Azure](./media/ui-changes/02-azure-enroll-restrictions.png)

La restriction de limite d’appareils par défaut correspond à la limite d’inscription d’appareils dans la console classique :

![Image des restrictions de limite d’appareils Azure](./media/ui-changes/03-azure-device-limit.png)

La restriction de type d’appareils par défaut correspond aux restrictions de plateforme dans la console classique :

![Image des restrictions de type d’appareils Azure](./media/ui-changes/04-azure-platform-restrictions.png)

La capacité à autoriser ou à bloquer les appareils personnels est désormais gérée sous les configurations de plateforme de restriction de type d’appareils :

![Image des paramètres de blocage des appareils personnels Azure](./media/ui-changes/05-azure-personal-block.png)

Les nouvelles fonctionnalités de restriction seront ajoutées uniquement au portail Azure.

## <a name="where-did-apple-dep-go"></a>Où est passé le programme Apple DEP ?
Dans la console classique, vous pouviez configurer Intune pour l’intégrer au programme DEP (Device Enrollment Program) d’Apple et demander manuellement la synchronisation avec le service d’Apple :

![Image de jeton DEP classique](./media/ui-changes/06-classic-dep-token.png)

Dans le portail Azure, vous configurez le Programme d’inscription des appareils Apple en effectuant les mêmes étapes que dans Intune classique :

![Image de jeton DEP Azure](./media/ui-changes/07-azure-dep-token.png)

Toutefois, l’option **Synchroniser** dans la console classique a été déplacée vers le flux de travail de gestion de numéro de série, car c’est là qu’apparaissent les résultats d’une synchronisation manuelle :

![Image de synchronisation DEP Azure](./media/ui-changes/08-azure-dep-sync.png)

## <a name="where-did-corporate-pre-enrolled-devices-go"></a>Où sont passés les appareils d’entreprise pré-inscrits ?
### <a name="by-ios-serial-number"></a>Par numéro de série iOS
Dans la console classique, vous pouviez inscrire des appareils iOS dans le cadre du programme DEP d’Apple et de l’outil Apple Configurator. Ces deux méthodes permettent d’inscrire des appareils par numéro de série et impliquent l’affectation de profils Inscription des appareils d’entreprise spéciaux. Avant l’inscription, l’affectation de profil d’inscription peut être gérée par l’intermédiaire du groupe d’appareils **Appareils d’entreprise préinscrits - Par numéro de série iOS** :

![Image des numéros de série Apple classiques](./media/ui-changes/09-classic-apple-serials.png)

Cette fenêtre répertorie dans une même liste les numéros de série pour l’inscription Apple DEP et Apple Configurator. Pour réduire les risques de non-concordance d’affectation de profil (profil DEP vers numéro de série AC, et vice versa), nous avons réparti les numéros de série en deux listes dans le portail Azure :

**Numéros de série DEP**
![Image des numéros de série Azure DEP](./media/ui-changes/10-azure-dep-serials.png)

**Numéros de série Apple Configurator**
![Image des numéros de série Azure Apple Configurator](./media/ui-changes/11-azure-ac-serials.png)

### <a name="by-imei-all-platforms"></a>Par IMEI (toutes les plateformes)

Dans la console classique, vous pouvez prélister les numéros IMEI des appareils pour les marquer comme appareils d’entreprise lors de leur inscription sur Intune :

![Image de la liste classique des numéros IMEI](./media/ui-changes/12-classic-corp-imei.png)

Dans la console Azure, vous devez charger le même IMEI dans la liste Identificateurs d’appareil d’entreprise avec un fichier de valeurs séparées par des virgules (CSV). Le nouveau portail ne prend pas en charge la saisie manuelle de numéros IMEI :

![Image de la liste des numéros IMEI dans Azure](./media/ui-changes/13-azure-corp-imei.png)

Intune dans le portail Azure est conçu pour prendre en charge ultérieurement d’autres types d’identificateurs en plus de l’IMEI, mais n’autorise actuellement que les numéros IMEI pour la préliste.

## <a name="where-did-corporate-device-enrollment-profiles-go"></a>Où sont passés les profils Inscription d’appareil professionnel ?
Pour inscrire des appareils iOS dans le cadre du Programme d’inscription des appareils Apple ou avec l’outil Apple Configurator, vous devez fournir un profil Inscription d’appareil professionnel à affecter à l’appareil. Dans la console classique, la création et la gestion de ces profils s’effectuaient dans une même liste :

![Image de profils d’inscription d’appareils classiques](./media/ui-changes/14-classic-corp-profiles.png)

Cette liste affiche les profils activés pour une utilisation avec le Programme d’inscription des appareils Apple (**DEP Activé**) et ceux activés uniquement pour une utilisation avec l’outil Apple Configurator (**DEP Désactivé**).

Pour éviter toute confusion entre les deux types de profils et les éventuels non-concordances d’affectation (profil DEP vers appareils Configurator, et vice versa), nous avons séparé la création et la gestion des profils du Programme d’inscription (prise en charge à la fois du Programme d’inscription des appareils Apple et d’Apple School Manager) et des profils Apple Configurator :

**Profils DEP**
![Image de profils DEP Azure](./media/ui-changes/15-azure-dep-profiles.png)

**Profils Apple Configurator**
![Image de profils Azure Apple Configurator](./media/ui-changes/16-azure-ac-profiles.png)

