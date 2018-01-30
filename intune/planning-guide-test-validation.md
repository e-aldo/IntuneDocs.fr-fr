---
title: Test et validation Intune
description: "Détails que vous devez prendre en considération au moment de tester et valider une solution Intune basée uniquement sur le cloud dans votre environnement."
keywords: 
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4f82ee0c-4bd6-4623-9b10-9249d316ccf5
ms.reviewer: jeffbu, cgerth
ms.suite: ems
ms.openlocfilehash: 8521ae12062ad73dfddb0f03aeac8c07ce65de58
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/25/2018
---
# <a name="intune-testing-and-validation"></a>Test et validation Intune

La phase de test se produit pendant et après la phase d’implémentation. Vous avez besoin de comptes, de groupes et d’appareils de test pour tester tous les scénarios administrateur informatique et utilisateur final (cas d’utilisation) que vous avez préalablement identifiés.

Nous vous recommandons d’impliquer votre personnel de support et d’assistance informatique dans la phase de test afin de créer une documentation de support et permettre au personnel de se familiariser avec le produit. Si un composant ou scénario ne fonctionne pas dans un cas d’utilisation, veillez à documenter les modifications nécessaires et à inclure la raison pour laquelle une modification a été apportée.

## <a name="before-you-begin"></a>Avant de commencer

Nous vous recommandons de documenter les éléments suivants :

-   **Critères de test :** identifient les tests d’évaluation à effectuer.

-   **Composants de conception :** doivent figurer dans au moins un des critères de test.

Si un composant de conception ne figure pas dans au moins un des critères de test en adéquation avec une exigence ou un scénario, déterminez si ce composant de conception est nécessaire ou non. En outre, assurez-vous de disposer des éléments suivants :

-   **Comptes :** comptes de test concédés sous licence pour EMS et Office 365 pour tester tous les scénarios de cas d’utilisation.

-   **Appareils :** appareils de test qui peuvent être réinitialisés ou dont les paramètres d’usine peuvent être rétablis.

-   **Composants d’intégration :** tous les composants d’intégration (Certificate Connector, connecteur service à service Intune pour Exchange hébergé et connecteur Intune Exchange local) doivent être installés et configurés, si nécessaire.

Des modifications de conception peuvent s’avérer nécessaires pour prendre en compte les problèmes imprévus. En outre, toutes les modifications de conception doivent être entièrement documentées en justifiant chaque changement. Voici un exemple de modification :

<blockquote>Vous réalisez que vous ne répondez pas aux exigences du Service d’inscription de périphérique réseau (NDES) et apprenez aussi que les profils VPN et Wi-Fi peuvent être configurés avec une autorité de certification racine qui répond aux mêmes exigences sans nécessiter d’implémentation NDES.</blockquote>

Vous pouvez rencontrer des difficultés qui requièrent des conseils techniques ou un dépannage spécialisé pendant le processus de test et de validation. Nous vous recommandons de demander de l’aide via les canaux de support Microsoft.

-   [Découvrir comment obtenir du support Intune](get-support.md)

-   [Contacter le support par téléphone pour Microsoft Intune](/intune-classic/troubleshoot/contact-assisted-phone-support-for-microsoft-intune)

## <a name="functional-validation-testing"></a>Test de validation fonctionnel

La validation fonctionnelle consiste à tester chaque composant et configuration pour vérifier son fonctionnement. Vous trouverez un exemple de test de validation dans le tableau ci-dessous.

![Section 9 tableau 1](./media/section-9-image-1-table.PNG)

## <a name="use-case-validation-testing"></a>Test de validation de cas d'utilisation

Procédez à un test de validation de cas d’utilisation pour vérifier que les scénarios sont complets et fonctionnels. Il existe deux types de scénarios : administrateur informatique et utilisateur final.

### <a name="it-admin"></a>Administrateur informatique

Procédez à un test de validation administrateur informatique pour vérifier que les actions d’administration effectuées sur un appareil ou un utilisateur fonctionnent correctement. Voici un exemple de scénario de validation administrateur informatique de bout en bout.

![Section 9 tableau 2](./media/section-9-image-2-table.PNG)

### <a name="end-user"></a>Utilisateur final

Procédez à un test de validation utilisateur final pour vérifier que l’expérience de l’utilisateur final se déroule et se présente comme prévu dans toutes les communications de l’utilisateur. Il est important de vérifier que l’expérience de l’utilisateur final est correcte. À défaut, vous risquez d’enregistrer des taux d’adoption plus faibles et un nombre d’appels au support technique plus élevé.

![Section 9 tableau 3](./media/section-9-image-3-table.PNG)

## <a name="next-steps"></a>Étapes suivantes

Maintenant que vous avez testé et validé vos scénarios fonctionnels et de cas d’utilisation Intune, vous êtes prêt pour le [déploiement de production Intune](planning-guide-rollout-plan.md).

Pour obtenir des informations et des modèles de planification supplémentaires, consultez [Ressources supplémentaires](planning-guide-resources.md).
