---
title: Gérer la liaison utilisateur-appareil pour les PC Windows
description: Comment lier un utilisateur à un PC Windows géré par Intune.
keywords: ''
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 12/15/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 53c99d63-c312-442a-8a71-de1b10fcd39b
ms.reviewer: owenyen
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 751355c34fc18cd9a1ededd498724d4652fc1368
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2018
---
# <a name="manage-user-device-linking-for-windows-pcs"></a>Gérer la liaison utilisateur-appareil pour les PC Windows

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Les informations de cette rubrique s’appliquent uniquement aux bureaux Windows que vous gérez en tant que PC à l’aide du client logiciel Intune. 

Avant de pouvoir déployer des logiciels vers un utilisateur, vous devez lier l'utilisateur à un ordinateur. Vous pouvez associer un utilisateur à plusieurs ordinateurs, mais chaque ordinateur ne peut être lié qu'à un seul utilisateur. Les utilisateurs sont automatiquement liés à tous les ordinateurs qu’ils inscrivent dans Intune à l’aide du portail de l’entreprise.

Pour lier un utilisateur à un ordinateur :

1. Dans la [console d’administration Microsoft Intune](https://manage.microsoft.com/), choisissez **Groupes** &gt; **Tous les appareils** (ou un autre groupe qui contient l’ordinateur que vous voulez lier à un utilisateur).

2. Sélectionnez l’ordinateur que vous souhaitez lier à un utilisateur, puis choisissez **Lier un utilisateur**.

   La boîte de dialogue **Lier un utilisateur** affiche une liste des utilisateurs disponibles avec leur nom complet, leur ID utilisateur, ainsi que le nombre d'ordinateurs lié à chacun. Si un utilisateur est déjà lié à l'ordinateur sélectionné, son nom et ID utilisateur s'affichent sous **Utilisateur actuel**. Si l'ordinateur n'est lié à aucun utilisateur, **Aucun utilisateur** n'apparaît sous **Utilisateur actuel**.

3. Effectuez l'une des opérations suivantes :

   - Pour laisser l’ordinateur lié à son utilisateur actuel, le cas échéant, choisissez **Annuler**.

   - Pour supprimer le lien vers l’utilisateur actuel, le cas échéant, choisissez <strong>Supprimer le lien **&gt; **OK</strong>.

   - Pour relier l'ordinateur à un nouvel utilisateur, sélectionnez un utilisateur dans la liste **Tous les utilisateurs** . Vérifiez que les données utilisateur sont correctes, puis choisissez **OK**.

> [!TIP]
> Si vous souhaitez limiter la capacité des utilisateurs finaux à se lier à des ordinateurs, activez l’option **Limiter la capacité des utilisateurs à se lier à des ordinateurs** dans la stratégie **Paramètres de l’Agent Microsoft Intune**.

### <a name="see-also"></a>Voir aussi

[Tâches courantes de gestion des PC Windows avec le client logiciel Intune](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md)