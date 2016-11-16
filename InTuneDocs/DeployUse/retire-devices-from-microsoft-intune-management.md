---
title: Mettre hors service des appareils | Microsoft Intune
description: "Intune prend en charge une réinitialisation sélective et une réinitialisation complète pour supprimer l’appareil de la gestion Intune en supprimant la stratégie et le portail d’entreprise."
keywords: 
author: staciebarker
ms.author: staciebarker
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
ms.sourcegitcommit: b76e9e16ef1fa6870783326630ae74d07ae59cbb
ms.openlocfilehash: be3a30535fc9cebad5d4a167b75c484ddafd7f85


---

# <a name="retire-devices-from-intune-management"></a>Retirer des appareils de la gestion Intune

Qu’ils soient personnels ou qu’ils appartiennent à l’entreprise, les appareils gérés sont appelés à être supprimés du portail de gestion Intune. Vous pouvez être amené à mettre un appareil hors service pour plusieurs raisons :

-   l’utilisateur quitte une entreprise d’une manière planifiée (départ « géré ») ;
-   l’utilisateur quitte l’entreprise brusquement (il est renvoyé, démissionne etc.) ;
-   l’appareil est perdu ;
-   un appareil est réaffecté (affecté à un autre utilisateur, réutilisé dans un autre contexte).

Vous pouvez effectuer une réinitialisation sélective ou complète sur un appareil géré en tant qu’appareil mobile ou vous pouvez verrouiller un appareil et réinitialiser son mot de passe. En réinitialisant l’appareil, vous libérez l’abonnement de l’utilisateur pour ajouter un autre appareil. Vous pouvez également mettre hors service des ordinateurs gérés à l’aide du logiciel client Intune.

## <a name="wipe-data-and-apps-from-devices"></a>Effacer les données et applications des appareils
Une réinitialisation sélective et une réinitialisation complète suppriment l’appareil de la gestion Intune en supprimant sa stratégie et le portail d’entreprise. Ainsi, l’appareil n’a plus les informations d’identification nécessaires pour se connecter aux ressources d’entreprise comme Microsoft SharePoint, l’e-mail ou Office 365.

L’[effacement sélectif](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md#selective-wipe) est l’action à privilégier pour les employés qui ont inscrit leurs propres appareils dans Intune, car elle n’affecte pas les informations personnelles sur l’appareil. Seules les données d’entreprise sont supprimées.

Pour les appareils devant changer de fonction, vous pouvez également utiliser la [réinitialisation complète](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md#full-wipe), qui réinitialise l’appareil aux paramètres d’usine.

## <a name="to-delete-devices-in-the-azure-active-directory-portal"></a>Pour supprimer des appareils dans le portail Azure Active Directory

1.  Connectez-vous à l’aide des informations d’identification de votre entreprise sur [http://aka.ms/accessaad](http://aka.ms/accessaad) ou [https://portal.office.com](https://portal.office.com), puis choisissez **Centres d’administration** &gt; **AD Azure**.

2.  Créez un abonnement Azure si vous n’en avez pas. Cette opération ne doit pas nécessiter de carte de crédit ou un paiement si vous disposez d’un compte payant. Choisissez le lien d’abonnement **Inscrire votre annuaire Azure Active Directory gratuit**.

4.  Choisissez **Active Directory**, puis le nom de votre organisation.

5.  Choisissez l’onglet **Utilisateurs**.

6.  Choisissez l’utilisateur dont vous voulez supprimer les appareils.

7.  Choisissez **Appareils**.

8.  Choisissez les appareils, puis **Supprimer l’appareil**. L’appareil sera supprimé lors de la prochaine synchronisation avec Active Directory. La synchronisation a lieu généralement toutes les quatre heures. Après la synchronisation, l’appareil est supprimé du portail de gestion. L’un des appareils de l’utilisateur est donc supprimé, et un autre pourra être ajouté, dans la limite autorisée pour cet utilisateur.

## <a name="retire-managed-computers"></a>Mettre hors service des ordinateurs gérés
Les ordinateurs que gère le logiciel client Intune peuvent être supprimés de la gestion dans la console d’administration Intune. Dans ce cas, le logiciel client est désinstallé et la stratégie Intune supprimée de l’ordinateur. Pour plus d’informations, consultez la section concernant la [mise hors service d’ordinateurs gérés à l’aide du logiciel client Intune](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client#retire-a-computer.md).

## <a name="block-access-a-device"></a>Bloquer l’accès à un appareil
Si un appareil est perdu ou si vous devez mettre un appareil hors service parce qu’un employé a quitté l’entreprise sans le rendre, vous pouvez également [réinitialiser le code d’accès et verrouiller à distance](use-remote-lock-and-passcode-reset-in-microsoft-intune.md) l’appareil. Ces opérations empêchent que les informations d’entreprise ne soient utilisées à mauvais escient, même si vous devrez peut-être considérer l’appareil comme perdu et inutilisable.

Vous souhaiterez également révoquer la licence du compte d'utilisateur Intune de l'employé. Cela libère la licence, que vous pouvez alors affecter à un nouveau compte d’utilisateur.

## <a name="retire-hardware"></a>Mettre du matériel hors service
Parfois c'est l'appareil lui-même qui arrive en fin de vie. Dans ce cas, la [réinitialisation complète aux paramètres d’usine](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md) supprime toutes les données et supprime l’appareil dans Intune. Vous pouvez ensuite vous débarrasser du matériel conformément à la politique de votre entreprise.

### <a name="see-also"></a>Voir aussi
[Protéger vos données avec la réinitialisation complète ou sélective](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md)



<!--HONumber=Nov16_HO3-->


