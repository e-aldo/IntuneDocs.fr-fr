---
title: "Définir les conditions générales dans Microsoft Intune"
titleSuffix: Intune Azure preview
description: "Définissez les conditions générales que les utilisateurs voient dans le Portail d’entreprise pour Intune. "
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 05/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4a3a11a8-9c0c-4334-8c6b-6fea4d0a2efb
ms.reviewer: amyro
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: d53e91e24988d1bc71ff8df425f0d82e0fc43b58
ms.contentlocale: fr-fr
ms.lasthandoff: 05/23/2017

---

# <a name="ensure-users-accept-company-terms-for-access"></a>Vérifiez que les utilisateurs acceptent les conditions générales de la société relatives à l’accès

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

En tant qu’administrateur Intune, vous pouvez choisir d’exiger que les utilisateurs acceptent les conditions générales de votre société avant de pouvoir utiliser le portail d’entreprise pour inscrire leurs appareils et accéder aux ressources d’entreprise telles que les applications et la messagerie. La configuration des conditions générales est facultative.

Vous pouvez créer plusieurs ensembles de conditions générales et les affecter à différents groupes, par exemple pour prendre en charge différentes langues.

## <a name="create-terms-and-conditions"></a>Créer des conditions générales
Effectuez ces étapes pour créer les conditions générales. Le nom d’affichage et la description sont destinés à un usage administratif, tandis que les propriétés des conditions générales sont présentées aux utilisateurs du portail d’entreprise.

1. Dans le portail Azure, choisissez **Plus de services** > **Surveillance + gestion** > **Intune**.

2. Dans le panneau Intune, choisissez **Inscription de l’appareil**, puis **Conditions générales**.

3. Sélectionnez **Créer**.
![Capture d’écran du portail Intune montrant le bouton Créer pour les conditions générales](media/terms-create-terms.png)

4. Dans le panneau étendu, spécifiez les informations suivantes :

   - **Nom d’affichage** : nom pour les conditions générales dans le portail Intune. Les utilisateurs ne voient pas ce nom.

   - **Description** : détails facultatifs qui vous aident à identifier cet ensemble de conditions générales dans le portail Intune.

5. Sélectionnez la flèche en regard de Définir la condition d'utilisation pour ouvrir le panneau des Conditions générales, puis entrez les informations suivantes :

   ![Capture de l’écran d’acceptation des conditions générales de l’utilisateur final avec récapitulatif des conditions](./media/terms-summary-create.png)

   - **Titre** : titre visible dans le Portail d’entreprise.

   - **Résumé des conditions** : texte qui explique la signification de l'acceptation par les utilisateurs des Conditions générales. Par exemple, « En inscrivant votre appareil, vous acceptez les conditions d’utilisation définies par Contoso. Lisez les termes du contrat avec soin avant de continuer. ».

   - **Conditions générales** : conditions générales que les utilisateurs voient et doivent accepter ou rejeter.

6. Sélectionnez **OK**, puis **Créer**.

## <a name="assign-terms-and-conditions"></a>Affecter des conditions générales

Vous pouvez affecter des conditions générales à des groupes d’utilisateurs qui doivent les accepter avant d’utiliser le Portail d’entreprise.

1. Dans le portail Azure, choisissez **Plus de services** > **Surveillance + gestion** > **Intune**.

2. Dans le panneau Intune, choisissez **Inscription de l’appareil**, puis **Conditions générales**.

3. Dans la liste des conditions générales, sélectionnez celles à affecter, puis sélectionnez **Groupes affectés**.
![Capture d’écran du panneau Affecter un groupe du portail Intune montrant le bouton Sélectionner un groupe et un bouton Sélectionner pour l’affectation des conditions générales](media/terms-assign-groups.png)

4. Cliquez sur le bouton **Sélectionner un groupe** et, dans le panneau **Sélectionner des groupes**, sélectionnez les groupes auxquels vous souhaitez affecter les conditions générales, puis cliquez sur **Sélectionner**.

5. Dans le panneau **Groupes affectés**, cliquez sur **Enregistrer**.  Les conditions générales sont maintenant affectées aux utilisateurs dans les groupes sélectionnés. Les utilisateurs seront invités à accepter les conditions générales la prochaine fois qu’ils accèderont au portail d’entreprise.

   ![Capture de l’écran d’acceptation des conditions générales de l’utilisateur final avec récapitulatif des conditions](./media/terms-summary-accept.png)

## <a name="monitor-a-terms-and-conditions"></a>Surveiller des conditions générales

1. Dans le portail Azure, choisissez **Plus de services** > **Surveillance + gestion** > **Intune**. Dans le panneau Intune, choisissez **Inscription de l’appareil**, puis **Conditions générales**.
2. Dans la liste des conditions générales, sélectionnez celles pour lesquelles vous souhaitez voir l’acceptation, puis sélectionnez **États d’acceptation**.

## <a name="work-with-multiple-versions-of-terms-and-conditions"></a>Utiliser plusieurs versions des conditions générales
Vous pouvez modifier vos conditions générales et gérer leurs versions. Nous vous recommandons d’incrémenter le numéro de version et d’exiger l’acceptation chaque fois que vous apportez des modifications majeures à vos conditions générales. Conservez le numéro de version actuel si, par exemple, vous corrigez des fautes de frappe ou modifiez la mise en forme.

1. Dans le portail Azure, choisissez **Plus de services** > **Surveillance + gestion** > **Intune**.

2. Dans le panneau Intune, choisissez **Inscription de l’appareil**, **Conditions générales**, sélectionnez les conditions générales que vous souhaitez modifier, puis sélectionnez **Propriétés**.

4. Dans le panneau **Propriétés**, sélectionnez **Conditions générales**, puis modifiez le **Titre**, le **Résumé des conditions** et les **Conditions générales** en fonction des besoins. Si ces modifications exigent que les utilisateurs acceptent les nouvelles conditions générales, cliquez sur **Demandez aux utilisateurs de réaccepter les conditions et passez au numéro de version**

4.  Sélectionnez **OK**, puis **Enregistrer**.

