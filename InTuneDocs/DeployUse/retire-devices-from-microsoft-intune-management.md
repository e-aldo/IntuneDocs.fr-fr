---
title: Mettre hors service des appareils | Microsoft Intune
description: "Intune prend en charge une réinitialisation sélective et une réinitialisation complète pour supprimer l’appareil de la gestion Intune en supprimant la stratégie et le portail d’entreprise."
keywords: 
author: NathBarn
manager: angrobe
ms.date: 07/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3dbec400-5d8a-47be-b892-7745811d9de2
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: e9cbf5858cc4e860b540f421b6d463b8e7a429cf
ms.openlocfilehash: 42b723f99c34f03060140e5f280b87287d108ae1


---

# Retirer des appareils de la gestion Intune

Qu’ils soient personnels ou qu’ils appartiennent à l’entreprise, il arrive un moment où les appareils gérés doivent être retirés de la gestion dans Intune. La mise hors service des appareils est relativement simple ; la réinitialisation peut être sélective ou complète.
## Effacer les données et applications des appareils
La réinitialisation sélective et la réinitialisation complète retirent l’appareil de la gestion Intune en supprimant leur stratégie et le portail d’entreprise, ce qui signifie que l’appareil n’a plus les informations d’identification nécessaires pour se connecter aux ressources d’entreprise comme Microsoft SharePoint, la messagerie électronique et Office 365.

L’[effacement sélectif](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md#selective-wipe) est l’action à privilégier pour les employés qui ont inscrit leurs propres appareils dans Intune, car elle n’affecte pas les informations personnelles sur l’appareil. Seules les données d’entreprise sont supprimées.

Pour les appareils d’entreprise, vous pouvez également utiliser la [réinitialisation complète](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md#full-wipe), qui réinitialise l’appareil aux paramètres d’usine.

## Révoquer l'accès au réseau d'entreprise
Si vous mettez un appareil hors service en raison du fait qu’un employé quitte votre société et qu’il n’a pas restitué le matériel appartenant à l’entreprise, vous pouvez également [verrouiller à distance](use-remote-lock-and-passcode-reset-in-microsoft-intune.md) l’appareil. Cette opération empêche que le matériel d'entreprise et les informations d'entreprise soient utilisés à mauvais escient, même si vous devrez peut-être considérer l'appareil comme perdu et inutilisable.

Vous souhaiterez également révoquer la licence du compte d'utilisateur Intune de l'employé. Cela libère la licence, que vous pouvez alors affecter à un nouveau compte d'utilisateur.

## Mettre du matériel hors service
Parfois c'est l'appareil lui-même qui arrive en fin de vie. Dans ce cas, la [réinitialisation complète aux paramètres d’usine](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md) supprime toutes les données et supprime l’appareil dans Intune. Vous pouvez ensuite vous débarrasser du matériel conformément à la politique de votre entreprise.

### Voir aussi
[Protéger vos données avec la réinitialisation complète ou sélective](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md)



<!--HONumber=Jul16_HO4-->


