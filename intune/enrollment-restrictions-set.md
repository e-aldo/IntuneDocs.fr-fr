---
title: Définir des restrictions d’inscription dans Microsoft Intune
titlesuffix: ''
description: Restriction de l’inscription par la plateforme et définition d’une limite d’inscriptions d’appareils dans Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/02/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 9691982c-1a03-4ac1-b7c5-73087be8c5f2
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: aa91e0c0adcd1182f82c4a09746f154302fae326
ms.sourcegitcommit: 77ed48ab52b55e92ceaa89e9edf53b892fc62adb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/17/2018
ms.locfileid: "40251576"
---
# <a name="set-enrollment-restrictions"></a>Définir des restrictions d’inscription

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

En tant qu’administrateur Intune, vous pouvez créer et gérer des restrictions d’inscription qui définissent le nombre et les types d’appareils qui peuvent être inscrits en vue d’être gérés par Intune. Vous pouvez créer plusieurs restrictions et les appliquer à différents groupes d’utilisateurs. Vous pouvez définir [l’ordre de priorité](#change-enrollment-restriction-priority) pour vos différentes restrictions.

>[!NOTE]
>Les restrictions d’inscription ne sont pas des fonctionnalités de sécurité. Des appareils compromis peuvent falsifier leur caractère. Ces restrictions représentent une barrière de meilleur effort pour les utilisateurs non malveillants.

Parmi les restrictions d’inscription spécifiques que vous pouvez créer, citons les suivantes :

- Nombre maximal d’appareils inscrits
- Plateformes d’appareils qui peuvent s’inscrire :
  - Android.
  - Profil professionnel Android.
  - iOS.
  - macOS
  - Windows.
- Version du système d’exploitation des plateformes pour iOS, Android, Profil professionnel Android et Windows. (Seules les versions de Windows 10 peuvent être utilisées. Laissez ce champ vide si Windows 8.1 est autorisé.)
  - Version minimale
  - Version maximale
- Restreindre les appareils personnels (iOS, Android, Profil professionnel Android, macOS uniquement).

## <a name="default-restrictions"></a>Restrictions par défaut

Les restrictions par défaut sont automatiquement fournies pour les restrictions d’inscription de type d’appareil et de limite d’appareils. Vous pouvez changer les options pour les valeurs par défaut. Les restrictions par défaut s’appliquent à l’ensemble des inscriptions utilisateur et sans utilisateur. Vous pouvez remplacer ces valeurs par défaut en créant de nouvelles restrictions avec des priorités plus élevées.

## <a name="create-a-restriction"></a>Créer une restriction

1. Connectez-vous au portail Azure.
2. Sélectionnez **Autres services**, recherchez **Intune**, puis choisissez **Intune**.
3. Sélectionnez **Inscription de l’appareil** > **Restrictions d’inscription**.
4. Sélectionnez **Créer une restriction**.
5. Donnez un nom et une description à la restriction.
6. Choisissez un **Type de restriction**, puis sélectionnez **Créer**.
7. Pour les restrictions de limite d’appareils, sélectionnez **Limite d’appareils** pour définir le nombre maximal d’appareils qu’un utilisateur peut inscrire.
8. Pour les restrictions de type d’appareil, sélectionnez **Plateformes** et **Configurations de plateforme** pour autoriser ou bloquer des plateformes et des versions.
9. Sélectionnez **Affectations** > **+ Sélectionner des groupes**.
10. Sous **Sélectionner des groupes**, sélectionnez un ou plusieurs groupes, puis choisissez **Sélectionner**. La restriction s’applique uniquement aux groupes auxquels elle est affectée. Si vous n’affectez pas une restriction à au moins un groupe, elle n’a aucun effet.
11. Sélectionnez **Enregistrer**.
12. La nouvelle restriction est créée avec une priorité juste au-dessus de la valeur par défaut. Vous pouvez [changer la priorité](#change-enrollment-restriction-priority).

## <a name="set-device-type-restrictions"></a>Définition des restrictions de type d'appareil

Pour changer les paramètres d’une restriction de type d’appareil, effectuez les étapes suivantes :

1. Connectez-vous au portail Azure.
2. Sélectionnez **Autres services**, recherchez **Intune**, puis choisissez **Intune**.
3. Sélectionnez **Inscription de l’appareil** > **Restrictions d’inscription**.
4. Sous **Restrictions de type d’appareil**, choisissez la restriction à définir.
5. Sous le nom de la restriction (**Tous les utilisateurs** pour la restriction par défaut), sélectionnez **Plateformes**. Choisissez **Autoriser** ou **Bloquer** pour chaque plateforme répertoriée.
6. Sélectionnez **Enregistrer**.
7. Sous le nom de la restriction (**Tous les utilisateurs** pour la restriction par défaut), sélectionnez **Configurations de plateforme**. Ensuite, sélectionnez les **Versions** minimale et maximale pour les plateformes répertoriées. Les formats de version pris en charge sont notamment :
    - Profil professionnel Android prend en charge majeur.mineur.révision.build.
    - iOS prend en charge major.minor.rev.
    - Windows prend en charge major.minor.rev.build pour Windows 10 uniquement.
  Les versions du système d’exploitation ne s’appliquent pas aux appareils Apple inscrits par le biais du Programme d’inscription des appareils, d’Apple School Manager ou de l’application Apple Configurator.
8. Spécifiez s’il faut **Autoriser** ou **Bloquer** les appareils **personnels** pour chaque plateforme répertoriée.
    ![Espace de travail de restrictions sur les appareils avec les configurations de plateforme d’appareils par défaut indiquant les paramètres de propriété personnelle configurés](media/device-restrictions-platform-configurations.png)
9. Sélectionnez **Enregistrer**.


>[!NOTE]
>- Si vous bloquez l’inscription des appareils Android personnels, les appareils avec profil professionnel Android personnels peuvent quand même être inscrits.
>- Par défaut, les paramètres de vos appareils avec profil professionnel Android sont identiques à ceux de vos appareils Android. Ce ne sera plus le cas une fois que vous aurez modifié vos paramètres de profil professionnel Android.
>- Si vous bloquez l’inscription du profil professionnel Android personnel, seuls les appareils Android d’entreprise peuvent s’inscrire en tant que profil professionnel Android.

## <a name="set-device-limit-restrictions"></a>Définition des restrictions de limite d'appareil

Pour changer les paramètres d’une restriction de limite d’appareils, effectuez les étapes suivantes :

1. Connectez-vous au portail Azure.
2. Sélectionnez **Autres services**, recherchez **Intune**, puis choisissez **Intune**.
3. Sélectionnez **Inscription de l’appareil** > **Restrictions d’inscription**.
4. Sous **Restrictions de type d’appareils**, choisissez la restriction à définir.
5. Sélectionnez **Limite d’appareils** puis, dans la liste déroulante, sélectionnez le nombre maximal d’appareils qu’un utilisateur peut inscrire.
    ![Panneau des restrictions de limite d’appareils avec les restrictions de limite d’appareils](./media/device-restrictions-limit.png)
6. Sélectionnez **Enregistrer**.


Les utilisateurs reçoivent une notification qui leur indique qu’ils ont atteint le nombre limite d’appareils inscrits. Par exemple, sur iOS, la notification ressemble à ce qui suit :

![Notification du nombre limite d’appareils iOS](./media/enrollment-restrictions-ios-set-limit-notification.png)

## <a name="change-enrollment-restriction-priority"></a>Changer la priorité des restrictions d’inscription

Une priorité est utilisée quand un utilisateur existe dans plusieurs groupes auxquels des restrictions sont affectées. Les utilisateurs sont uniquement soumis à la restriction avec la priorité le plus élevée affectée à un groupe dans lequel ils se trouvent. Par exemple, Jean est dans un groupe A affecté à des restrictions de priorité 5 et aussi dans un groupe B affecté à des restrictions de priorité 2. Jean n’est soumis qu’aux restrictions de priorité 2.

Quand vous créez une restriction, elle est ajoutée à la liste juste au-dessus de la valeur par défaut.

L’inscription d’appareil inclut les restrictions par défaut pour les restrictions de type d’appareil et de limite d’appareils. Ces deux restrictions s’appliquent à tous les utilisateurs, sauf si elles sont remplacées par des restrictions avec une priorité plus élevée.

Vous pouvez changer la priorité d’une restriction différente de celle par défaut.

1. Connectez-vous au portail Azure.
2. Sélectionnez **Autres services**, recherchez **Intune**, puis choisissez **Intune**.
3. Sélectionnez **Inscription de l’appareil** > **Restrictions d’inscription**.
4. Pointez sur la restriction dans la liste des priorités.
5. À l’aide des trois points verticaux, faites glisser la priorité à la position souhaitée dans la liste.
