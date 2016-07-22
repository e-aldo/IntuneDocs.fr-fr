---
title: "Utiliser le verrouillage à distance et la réinitialisation du code d'accès | Microsoft Intune"
description: 
keywords: 
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 970f8c81-7c7f-4789-9ed4-2133d50b9db6
translationtype: Human Translation
ms.sourcegitcommit: 6d9b79a09eef2546d78a19e061ba5cc3f24f645c
ms.openlocfilehash: 34379881b8299a2e3f9886b14b6d83e9dfe83373

---
# Protéger vos appareils à l’aide du verrouillage à distance et de la réinitialisation du code d’accès
Microsoft Intune fournit des fonctionnalités de verrouillage à distance et de réinitialisation du code d’accès.

## Verrouiller un appareil à distance
Si un utilisateur perd son appareil, vous pouvez verrouiller celui-ci à distance. Le tableau ci-dessous indique la méthode de verrouillage à distance sur des plates-formes mobiles différentes.

|Plate-forme|Verrouillage à distance|
|------------|---------------|
|iOS|Pris en charge|
|Android|Pris en charge|
|Windows 10 Mobile|Pris en charge|
|Windows Phone 8 et Windows Phone 8.1|Pris en charge|
|Windows RT 8.1 et Windows RT|Prise en charge si l'utilisateur actuel de l'appareil est le même utilisateur qui a inscrit l'appareil.|
|Windows 8.1|Prise en charge si l'utilisateur actuel de l'appareil est le même utilisateur qui a inscrit l'appareil.|


### Pour verrouiller un appareil mobile à distance par le biais de la console Intune

1.  Dans la [console d’administration Intune](https://manage.microsoft.com/), choisissez **Groupes** &gt; **Tous les appareils** &gt; **Tous les appareils mobiles**.

2.  Choisissez **Tous les appareils gérés par gestion directe** pour les appareils inscrits dans Intune ou **Tous les appareils gérés par Exchange ActiveSync**.

    > [!TIP]
    > Vous pouvez également accéder à un appareil par l'utilisateur. Sélectionnez **Tous les utilisateurs**. Dans la page des propriétés de l’utilisateur, sélectionnez **Appareils**, puis le nom de l’appareil mobile à réinitialiser.

3.  Dans la liste, cliquez sur le ou les appareils à verrouiller. Dans la barre des tâches, choisissez **Tâches à distance**, puis sélectionnez **Verrouillage à distance**.

## Réinitialiser le code d’accès d’un appareil
Si un utilisateur oublie son code d'accès, vous pouvez l'aider à résoudre ce problème en supprimant le code d'accès d'un appareil ou en forçant l'application d'un nouveau code accès temporaire sur un appareil. Le tableau ci-dessous indique la méthode de réinitialisation du code d'accès sur des plates-formes mobiles différentes.

|Plate-forme|Réinitialiser le code secret|
|------------|------------------|
|iOS|Prise en charge de l'effacement du code d'accès d'un appareil. Ne crée pas un nouveau code d'accès temporaire.|
|Android|Prise en charge et création d'un nouveau code d'accès temporaire.|
|Windows 10 Mobile|Pris en charge|
|Windows Phone 8 et Windows Phone 8.1|Pris en charge|
|Windows RT 8.1 et Windows RT|Non pris en charge|
|Windows 8.1|Non pris en charge|

### Pour réinitialiser un code d’accès

1.  Dans la [console d’administration Intune](https://manage.microsoft.com/), choisissez **Groupes** &gt; **Tous les appareils** &gt; **Tous les appareils mobiles**.

2.  Choisissez **Tous les appareils gérés par gestion directe** pour les appareils inscrits dans Intune ou **Tous les appareils gérés par Exchange ActiveSync**.

    > [!TIP]
    > Vous pouvez également accéder à un appareil par l'utilisateur. Cliquez sur **Tous les utilisateurs**. Dans la page Propriétés de l’utilisateur, cliquez sur **Appareils**, puis sur le nom de l’appareil mobile à réinitialiser.

3.  Dans la liste, cliquez sur le ou les appareils à verrouiller. Dans la barre des tâches, choisissez **Tâches à distance**, puis sélectionnez **Réinitialisation du code d’accès**.


### Voir aussi
[Mettre des appareils hors service](retire-devices-from-microsoft-intune-management.md)
[Windows Selective Wipe for Device Data Management](http://technet.microsoft.com/library/dn486874.aspx)



<!--HONumber=Jun16_HO4-->


