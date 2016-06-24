---
# required metadata

title: Règles d’accès Exchange pour les appareils mobiles gérés par Microsoft Intune | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 208b9f45-02d9-413a-b86a-8bad9b5008fa

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Règles d’accès Exchange pour les appareils mobiles
Les règles d’accès Exchange pour les appareils mobiles déterminent le niveau d’accès à Exchange accordé à ces appareils. Ces paramètres affectent tous les appareils mobiles, y compris ceux qui ne sont pas inscrits dans Microsoft Intune. Vous pouvez commencer par définir une **Règle par défaut** qui s'appliquera à tout appareil mobile auquel aucune règle personnalisée n'est appliquée. Le tableau suivant contient les niveaux d'accès gérés par Exchange ActiveSync :

|Niveaux d'accès|Description|
|----------------|---------------|
|**Autoriser tous les appareils mobiles à accéder à Exchange, sauf si une règle personnalisée stipule le contraire**|À l’état *Autoriser l’accès*, un appareil mobile peut se synchroniser par le biais d’ActiveSync Exchange et se connecter au serveur Exchange pour récupérer le courrier électronique et gérer les informations relatives le Calendrier, les Contacts, les Tâches et les Notes. Il en est ainsi tant que l’appareil est conforme à la **Stratégie de sécurité des appareils mobiles Intune** que vous avez configurée, sauf si l’utilisateur ou l’appareil mobile spécifique a été bloqué par l’administrateur Exchange.|
|**Bloquer l'accès à Exchange pour tous les appareils mobiles, sauf si une règle personnalisée stipule le contraire**|À l’état *Bloquer l’accès*, les appareils mobiles sont bloqués et ne sont pas autorisés à se connecter au serveur Exchange. Les appareils reçoivent une erreur HTTP 403 Interdit. L'utilisateur recevra un message électronique envoyé par le serveur Exchange pour l'avertir que l'appareil mobile a été bloqué et qu'il ne peut pas accéder à sa boîte aux lettres. Ce message ne peut pas apparaître sur l’appareil mobile bloqué. Vous pouvez ajouter du texte personnalisé à ce message pour fournir des instructions aux utilisateurs dont les appareils sont bloqués avec la tâche **Définir la notification utilisateur** .|
|**Placer tous les appareils mobiles en quarantaine pour que je décide de l'état de chaque appareil mobile individuel plus tard, sauf si une règle personnalisée stipule le contraire**|Lorsqu'un appareil mobile est mis en quarantaine, il est autorisé à se connecter au serveur Exchange. Toutefois, il bénéficie uniquement d'un accès limité aux données. L'utilisateur peut ajouter du contenu à ses propres dossiers Calendrier, Contacts, Tâches et Notes, mais le serveur n'autorisera pas l'appareil à récupérer le contenu de la boîte aux lettres de l'utilisateur. L’utilisateur recevra un seul message électronique indiquant que l’appareil mobile est mis en quarantaine. Ce message est reçu sur l’appareil et dans la boîte aux lettres de l’utilisateur. Vous pouvez ajouter du texte personnalisé à ce message pour fournir des instructions aux utilisateurs dont les appareils sont mis en quarantaine par le biais de la tâche **Définir la notification utilisateur** .|

Une stratégie d'accès associe une **Règle par défaut** et des **Règles personnalisées** applicables à tous les appareils mobiles connectés à Exchange. Le tableau ci-dessous répertorie certains exemples de stratégies d'accès.

|Stratégie d’accès|Description|
|-------------------|---------------|
|Liste verte|Vous pouvez utiliser une *liste verte* pour accorder l’accès à une liste d’appareils connus et restreindre l’accès pour tout le reste. Pour ce faire, vous devez créer des règles personnalisées afin que les appareils spécifiques de votre choix puissent accéder aux boîtes aux lettres des utilisateurs. Dès que vous créez une telle règle, vous devez définir la règle d'accès par défaut sur le blocage ou la mise en quarantaine de tous les autres appareils. Pour ajouter un nouvel appareil à la liste verte, créez une nouvelle règle personnalisée.|
|Liste rouge|Vous pouvez utiliser une *liste rouge* pour accorder un accès à tous les appareils par défaut, mais pour bloquer l’accès d’un ensemble d’appareils qui ne doivent pas accéder à votre organisation. Créez une liste rouge en créant des règles personnalisées pour bloquer les appareils qui ne doivent pas se synchroniser avec les boîtes aux lettres de l’organisation. La règle par défaut doit être définie sur l'autorisation d'accès de tous les appareils qui ne sont pas explicitement bloqués par les règles existantes. Pour ajouter un nouveau appareil ou un ensemble d'appareils à la liste rouge, créez une nouvelle règle personnalisée.|
|Liste mixte|Outre la création de listes rouges et vertes, vous pouvez mettre en quarantaine des nouveaux appareils mobiles devant être utilisés par l'organisation afin de les évaluer. Par exemple, si vous avez créé une liste rouge pour les appareils mobiles non autorisés au sein de votre organisation, et une liste verte pour les appareils mobiles autorisés au sein de celle-ci, vous pouvez définir la règle par défaut sur la mise en quarantaine. Tous les autres appareils seront automatiquement mis en quarantaine. Cela vous permet de détecter les nouveaux appareils devant être utilisés dans l’organisation et de décider de leur ajout à la liste rouge ou la liste verte.|
La procédure suivante décrit comment créer une règle personnalisée.

## Créer une règle d’accès par défaut

1.  Dans la [Console d’administration Microsoft Intune](http://manage.microsoft.com) &gt; **Stratégie** &gt; **Règles d’accès à Exchange pour les appareils mobiles**.

2.  Dans la liste **Règle par défaut** , sélectionnez la règle d'accès à appliquer à tous les appareils mobiles non couverts par une règle ou une exemption personnelle. Choisissez **Enregistrer**.

La procédure suivante décrit comment créer une règle personnalisée.

## Créer une règle d’accès personnalisée

1. Dans la [Console d’administration Microsoft Intune](http://manage.microsoft.com) &gt; **Stratégie** &gt; **Règles d’accès à Exchange pour les appareils mobiles**.

2.  Dans la liste **Règles personnalisées**, choisissez **Ajouter une règle** et créez une règle personnalisée. Choisissez **Enregistrer**.


<!--HONumber=May16_HO1-->


