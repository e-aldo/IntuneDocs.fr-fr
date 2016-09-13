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
ms.sourcegitcommit: cf471320f122eea7804ff6cd6cad208f8cd5a692
ms.openlocfilehash: 29d13dcbc367c18d64f9522fa9a3b962226feebb


---

# Retirer des appareils de la gestion Intune

Qu’ils soient personnels ou qu’ils appartiennent à l’entreprise, il arrive un moment où les appareils gérés doivent être supprimés du portail de gestion Intune. Un appareil peut devoir être mis hors service pour plusieurs raisons :

-   l’utilisateur quitte une entreprise d’une manière planifiée (départ « géré ») ;
-   l’utilisateur quitte l’entreprise brusquement (il est renvoyé, démissionne etc..) ;
-   l’appareil est perdu ;
-   un appareil est réaffecté (affecté à un autre utilisateur, réutilisé dans un autre contexte).

Vous pouvez effectuer une réinitialisation sélective ou complète sur des appareils gérés en tant qu’appareils mobiles ou verrouiller un appareil et réinitialiser son mot de passe. En réinitialisant l’appareil, vous libérez l’abonnement de l’utilisateur pour ajouter un autre appareil. Vous pouvez également mettre hors service des ordinateurs gérés à l’aide du logiciel client Intune.

## Effacer les données et applications des appareils
La réinitialisation sélective et la réinitialisation complète retirent l’appareil de la gestion Intune en supprimant leur stratégie et le portail d’entreprise, ce qui signifie que l’appareil n’a plus les informations d’identification nécessaires pour se connecter aux ressources d’entreprise comme Microsoft SharePoint, la messagerie électronique et Office 365.

L’[effacement sélectif](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md#selective-wipe) est l’action à privilégier pour les employés qui ont inscrit leurs propres appareils dans Intune, car elle n’affecte pas les informations personnelles sur l’appareil. Seules les données d’entreprise sont supprimées.

Pour les appareils devant changer de fonction, vous pouvez également utiliser la [réinitialisation complète](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md#full-wipe), qui réinitialise l’appareil aux paramètres d’usine.

## Pour supprimer des appareils dans le portail Azure Active Directory

1.  Connectez-vous à l’aide des informations d’identification de votre entreprise sur [http://aka.ms/accessaad](http://aka.ms/accessaad) ou [https://portal.office.com](https://portal.office.com), puis sélectionnez **Centres d’administration** &gt; **AD Azure**.

2.  Créez un abonnement Azure si vous n’en avez pas. Vous ne devriez pas avoir besoin de carte de crédit ni d’effectuer un paiement si vous disposez d’un compte payant (choisissez le lien d’abonnement **Enregistrer votre abonnement Azure Active Directory gratuit**).

4.  Sélectionnez **Active Directory** , puis le nom de votre organisation.

5.  Sélectionnez l’onglet **Utilisateurs** .

6.  Sélectionnez l’utilisateur dont vous voulez supprimer les appareils.

7.  Choisissez **Appareils**.

8.  Sélectionnez les appareils, puis choisissez **Supprimer l’appareil**. L’appareil sera supprimé lors de la prochaine synchronisation avec Active Directory. La synchronisation a lieu généralement toutes les 4 heures. Après la synchronisation, l’appareil est supprimé du portail de gestion. L’un des appareils de l’utilisateur est donc supprimé, et un autre pourra être ajouté, dans la limite autorisée pour cet utilisateur.

## Mettre hors service des ordinateurs gérés
Les ordinateurs gérés avec le logiciel client Intune peuvent être supprimés de la gestion Intune à partir de la console d’administration Intune. Dans ce cas, le logiciel client est désinstallé et la stratégie Intune supprimée de l’ordinateur. Pour plus d’informations, consultez la section concernant la [mise hors service d’ordinateurs gérés à l’aide du logiciel client Intune](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client#retire-a-computer.md).

## Bloquer l’accès à un appareil
Si un appareil est perdu ou si vous devez mettre un appareil hors service parce qu’un employé a quitté l’entreprise sans le rendre, vous pouvez également [réinitialiser le code d’accès et verrouiller à distance](use-remote-lock-and-passcode-reset-in-microsoft-intune.md) l’appareil. Ces opérations empêchent que les informations d’entreprise ne soient utilisées à mauvais escient, même si vous devrez peut-être considérer l’appareil comme perdu et inutilisable.

Vous souhaiterez également révoquer la licence du compte d'utilisateur Intune de l'employé. Cela libère la licence, que vous pouvez alors affecter à un nouveau compte d’utilisateur.

## Mettre du matériel hors service
Parfois c'est l'appareil lui-même qui arrive en fin de vie. Dans ce cas, la [réinitialisation complète aux paramètres d’usine](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md) supprime toutes les données et supprime l’appareil dans Intune. Vous pouvez ensuite vous débarrasser du matériel conformément à la politique de votre entreprise.

### Voir aussi
[Protéger vos données avec la réinitialisation complète ou sélective](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md)



<!--HONumber=Aug16_HO4-->


