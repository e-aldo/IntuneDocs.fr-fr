---
title: "Définir les conditions générales dans Microsoft Intune | Version préliminaire d’Intune Azure | Microsoft Docs"
description: "Version préliminaire d’Intune Azure: définissez les conditions générales que les utilisateurs voient dans le Portail d’entreprise pour Intune. "
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 11/30/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4a3a11a8-9c0c-4334-8c6b-6fea4d0a2efb
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 990062ecf03a117dad74eb71e3f40abb79f22be6
ms.openlocfilehash: 694e5ac5eff0e2d39d44d992fe9dcc2262c112ce

---

# <a name="set-terms-and-conditions"></a>Définition des conditions générales 

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Vous pouvez déployer les conditions générales d’Intune sur des groupes d’utilisateurs pour expliquer comment l’inscription, l’accès aux ressources de travail et l’application Portail d’entreprise affectent les utilisateurs et les appareils. Les utilisateurs doivent accepter les conditions générales avant de pouvoir utiliser le Portail d’entreprise pour s’inscrire et accéder à leur travail.

Vous pouvez créer et déployer plusieurs stratégies contenant différentes conditions générales. Vous pouvez également produire des versions des mêmes conditions générales dans différentes langues et les déployer pour les groupes appropriés.

**Pour créer des conditions générales** :

1. Dans le portail Azure, choisissez **Plus de services**, entrez **Intune** dans la zone de texte, puis choisissez **Autres** > **Intune**.

2. Dans le panneau Intune, choisissez **Inscrire des appareils**, puis choisissez **Conditions générales**.

3. Sélectionnez **Créer**.

4. Dans le panneau **Créer des conditions générales**, spécifiez les informations suivantes :

   - **Nom complet** : nom à utiliser pour les conditions générales. Les utilisateurs voient ce nom dans l'application Portail d’entreprise.

   - **Description** : détails facultatifs qui vous aident à identifier la stratégie dans le portail Azure.

5. Sélectionnez la flèche en regard de Définir la condition d'utilisation pour ouvrir le panneau des Conditions générales, puis entrez les informations suivantes :

   - **Titre** : le titre visible dans le Portail d’entreprise.

   - **Résumé des conditions** : texte qui explique la signification de l'acceptation par les utilisateurs des Conditions générales.

   - **Conditions générales** : l’étiquette légale que les utilisateurs voient et doivent accepter ou rejeter, par exemple, « J’accepte les conditions générales ».

6. Sélectionnez **OK**.



<!--HONumber=Feb17_HO1-->


