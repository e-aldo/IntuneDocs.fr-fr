---
title: "Définition des restrictions d’inscription dans Intune | Version préliminaire d’Intune Azure | Microsoft Docs"
description: "Version préliminaire d&quot;Intune Azure : restriction de l’inscription par la plateforme et définition d’une limite d’inscriptions d’appareils dans Intune. "
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 11/30/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9691982c-1a03-4ac1-b7c5-73087be8c5f2
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 990062ecf03a117dad74eb71e3f40abb79f22be6
ms.openlocfilehash: 1bdefce35c20ce24b94ee701a2d13b5408f435ce

---

# <a name="set-enrollment-restrictions"></a>Définir des restrictions d’inscription 

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Vous pouvez restreindre les types d'appareils qui sont autorisés à s’inscrire dans Intune en spécifiant les plateformes autorisées. Vous pouvez également définir le nombre maximal d’appareils qu’un utilisateur est autorisé à inscrire.

## <a name="set-device-type-restrictions"></a>Définition des restrictions de type d'appareil

1. Dans le portail Azure, choisissez **Plus de services**, entrez **Intune** dans la zone de texte, puis choisissez **Autres** > **Intune**

2. Dans le panneau Intune, choisissez **Inscrire des appareils**, puis choisissez **Restrictions d’inscription**.

3. Sous **Restrictions de type d'appareil**, sélectionnez **Par défaut**.

4. Dans le panneau **Tous les utilisateurs**, sélectionnez **plateformes**.

5. Pour les plateformes qui sont autorisées à s’inscrire dans Intune, sélectionnez **Autoriser**. Pour les plateformes pour lesquelles vous souhaitez empêcher l’inscription, sélectionnez **Bloquer**.

6. Sélectionnez **Enregistrer**.

7. Sélectionnez **Configurations des plateformes**.

8. Choisissez d’Autoriser ou Bloquer les appareils iOS personnels pour l’inscription.

9. Sélectionnez **Enregistrer**.

## <a name="set-device-limit-restrictions"></a>Définition des restrictions de limite d'appareil

1. Dans le panneau Intune du portail Azure, choisissez **Inscrire des appareils**, puis **Restrictions d’inscription**.

2. Sous **Restrictions de limite d’appareil**, sélectionnez **par défaut**.

3. Dans le panneau **Tous les utilisateurs**, sélectionnez **Limite d’appareil**.

4. Sélectionnez le nombre maximal d'appareils qu'un utilisateur peut inscrire, puis sélectionnez **Enregistrer**.



<!--HONumber=Feb17_HO1-->


