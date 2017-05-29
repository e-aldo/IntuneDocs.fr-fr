---
title: "Spécification de numéros IMEI | Microsoft Docs"
description: "Microsoft Intune permet aux administrateurs d’importer des numéros IMEI pour les plateformes d’appareils mobiles afin d’identifier les appareils mobiles d’entreprise"
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/22/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1712bd39-562b-4409-9cec-155d5f4d8a39
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 3388bce5bc4bb675b0342b463ed620c6023d51a2
ms.contentlocale: fr-fr
ms.lasthandoff: 05/23/2017


---

# <a name="specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers"></a>Spécifier des appareils d’entreprise avec des numéros IMEI (International Mobile Equipment Identity)

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Microsoft Intune permet aux administrateurs d’importer des numéros d’identité internationale d’équipement mobile (IMEI, International Mobile Equipment Identity) pour les plateformes d’appareils mobiles afin d’identifier les appareils mobiles d’entreprise. Une fois que les appareils sont inscrits dans Intune, vous pouvez afficher ceux qui ont importé des numéros IMEI sous **Groupes** > **Vue d’ensemble** > **Tous les appareils**. **Groupe d’appareils** répertorie les appareils qui ont importé des numéros IMEI avec **Entreprise** dans la colonne **Propriété**.

1. Dans la [console d’administration Microsoft Intune](https://manage.microsoft.com), choisissez **Groupes** &gt; **Tous les appareils** &gt; **Tous les appareils d’entreprise préinscrits** &gt; **Par IMEI (toutes les plateformes)**, puis choisissez **Ajouter des appareils**. Vous pouvez ajouter des appareils de deux manières :

    -   **Chargez un fichier .csv qui contient les numéros de série** : créez une liste de valeurs séparées par des virgules (.csv) de deux colonnes sans en-tête, limitée à 5 000 appareils ou à 5 Mo par fichier .csv. Le champ des détails est limité à 128 caractères. 

        |||
        |-|-|
        |&lt;IMEI 1&gt;|&lt;Détails de l’appareil 1&gt;|
        |&lt;IMEI 2&gt;|&lt;Détails de l’appareil 2&gt;|
        Dans un éditeur de texte, ce fichier .csv s'affiche comme suit :

        ```
        01234567890123,device details
        02234567890123,device details
        ```

    -   **Ajoutez manuellement les détails des appareils** : entrez le numéro IMEI et les détails de 15 appareils au maximum.

   Le champ *Détails* est destiné à l’administration. Vous pouvez spécifier des détails pour identifier l’appareil dans la liste des appareils d’entreprise répertoriés par ID du matériel. Ces informations ne sont pas envoyées à l’appareil, mais elles apparaissent dans la console Intune.

2.   Choisissez **Suivant**.
3.  Dans le volet **Passer en revue les appareils**, vous pouvez vérifier les numéros IMEI des appareils importés. Vous pouvez également décider s’il convient de remplacer les **détails** pour les numéros IMEI réimportés. Vous pouvez décocher la case **Remplacer** pour conserver les détails actuels. Choisissez **Terminer** pour importer les numéros IMEI.
4.  Les numéros IMEI importés et les descriptions sont ajoutés à la liste **Par IMEI (toutes les plateformes)**.

> [!IMPORTANT]
> Si vous importez des numéros IMEI pour des appareils Android, n’oubliez pas que certains appareils Android peuvent avoir plusieurs numéros IMEI. Si vous importez un numéro IMEI mais qu’il ne s’agit pas de celui signalé à Intune par l’appareil, celui-ci sera classifié comme appareil personnel plutôt que comme appareil d’entreprise.

Quand un appareil avec un numéro IMEI s’inscrit dans Intune, généralement quand un utilisateur installe l’application Portail d’entreprise et termine le processus d’inscription, l’appareil est étiqueté comme appareil d’entreprise et apparaît inscrit dans le groupe **Appareils IMEI**.

>[!NOTE]
> Dès que votre organisation aura migré vers le nouveau portail Azure, vous constaterez que cette fonctionnalité a été modifiée. Dans la console Administrateur Intune, les administrateurs peuvent accepter les détails associés à partir d’un fichier CSV chargé et remplacer les détails existants de chaque identificateur matériel. Dans le nouveau portail Azure, vous pouvez remplacer automatiquement les détails de tous les identificateurs matériels ou ignorer tous les nouveaux détails des identificateurs existants.

Pour obtenir des spécifications détaillées sur les IMEI (International Mobile Equipment Identifiers), consultez [3GGPP TS 23.003](https://portal.3gpp.org/desktopmodules/Specifications/SpecificationDetails.aspx?specificationId=729).

