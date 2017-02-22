---
title: "Ajout de numéros de série Apple Configurator | Version préliminaire d’Intune Azure | Microsoft Docs"
description: "Version préliminaire d’Intune Azure : découvrez comment ajouter des numéros de série pour les appareils iOS d’entreprise à l’aide de l’outil Apple Configurator."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 02/03/17
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d408aa38-7d1e-40df-9067-246e53f6e26f
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 65a6b2e22359bdcb9b0c15a84c6b3586dafe4d6c
ms.openlocfilehash: 71d29a245f8f900a7427528167bae0b52565d42b


---

# <a name="add-apple-configurator-serial-numbers"></a>Ajouter des numéros de série Apple Configurator 

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Suivez ces étapes pour ajouter des numéros de série à Intune lorsque vous souhaitez [inscrire des appareils d’entreprise iOS à l’aide d’Apple Configurator avec l’assistant de programme d’installation]((enroll-ios-devices-with-apple-configurator-and-setup-assistant.md). Vous pouvez ajouter les numéros de série un à la fois, ou télécharger un fichier (CSV) de valeurs de numéros de série séparées par des virgules. Après avoir ajouté des numéros de série, vous pouvez leur attribuer un profil. Le profil contient les paramètres de gestion spécifiques que vous souhaitez appliquer aux appareils. 

Les autres méthodes d’inscription d’appareils iOS sont décrites dans [Choisir comment inscrire des appareils iOS dans Intune](choose-ios-enrollment-method.md).

**Ajouter des numéros de série Apple Configurator à Intune**

1. Créez une liste de valeurs, séparées par des virgules (.csv) avec deux colonnes, sans en-tête. Ajoutez l’identificateur IMEI dans la colonne de gauche et les détails dans la colonne de droite. Le maximum actuel de la liste est de 500 lignes. Dans un éditeur de texte, la liste .csv ressemble à ceci :

    F7TLWCLBX196,détails de l’appareil</br>
    DLXQPCWVGHMJ,détails de l’appareil

2. Dans le portail Azure, choisissez **Plus de services**, entrez **Intune** dans la zone de texte, puis choisissez **Autres** > **Intune**.

3.  Dans le panneau Intune, choisissez **inscrire des appareils**, puis choisissez **Inscription Apple**.

4. Sous **Gérer les paramètres d’inscription d’Apple Configurator**, sélectionnez **Numéros de série d’Apple Configurator**.

5. Dans le panneau **Numéros de série d’Apple Configurator**, sélectionnez **Ajouter**.

6. Dans le panneau **Ajouter des numéros de série**, sélectionnez un profil à appliquer pour les numéros de série que vous importez. Si vous importez un fichier avec de nouvelles informations pour remplacer celles qui existent, sélectionnez Remplacer les informations pour les identificateurs existants afin que les nouvelles informations remplacent celles existantes.

7. Accédez au fichier .csv de numéros de série, puis sélectionnez **Ajouter**.

## <a name="assign-a-profile-to-specific-serial-numbers"></a>Affectation d’un profil à des numéros de série spécifiques

Intune vous permet d’affecter des profils à partir de deux emplacements différents dans le portail Azure. Vous pouvez utiliser les étapes suivantes, ou vous pouvez affecter des profils dans le panneau Profils d’inscription d’Apple Configurator. Vous pouvez y créer le profil (voir [Inscription d’appareils iOS avec Apple Configurator à l’aide de l’assistant de configuration](enroll-ios-devices-with-apple-configurator-and-setup-assistant.md). Vous pouvez utiliser les étapes ci-dessous pour affecter le profil uniquement si vous avez déjà créé le profil.

1. Dans le panneau Intune, choisissez **inscrire des appareils**, puis choisissez **Inscription Apple**.

2. Dans le panneau **Numéros de série d’Apple Configurator**, sélectionnez les numéros de série auxquels vous souhaitez affecter un profil, puis **Affecter un profil**.

3. Dans le panneau **Affecter un profil**, sélectionnez le profil que vous souhaitez affecter, puis **Affecter**.

## <a name="delete-serial-numbers"></a>Supprimer des numéros de série
Vous pouvez supprimer les numéros de série que vous avez importés précédemment. Vous pouvez supprimer les numéros de série uniquement si l’appareil est désinscrit. Lorsque vous supprimez un numéro de série, vous ne pouvez pas utiliser Apple Configurator via l’assistant configuration, sauf si vous ajoutez de nouveau le numéro de série.

## <a name="view-the-state-of-a-device"></a>Afficher l'état d’un appareil
Les numéros de série de l’appareil peuvent avoir un des deux états suivants :

- Inscrit : l’appareil est inscrit, et il est connecté au service Intune
- Non contacté : l’appareil ne s’est jamais connecté au service Intune.
- En attente de réinitialisation : l’appareil est inscrit, mais a été modifié (par exemple, les paramètres d’inscription ou le profil DEP appliqué ont été modifiés). Si vous modifiez le profil DEP d’un appareil, les modifications ne sont pas appliquées jusqu'à ce que l’appareil soit désinscrit, puis réinscrit.

**Pour afficher l’état d’un numéro de série**

Dans le panneau **Numéros de série Apple Configurator**, sélectionnez le numéro de série dont vous souhaitez voir l’état, puis regardez sous l’élément **État**.



<!--HONumber=Feb17_HO1-->


