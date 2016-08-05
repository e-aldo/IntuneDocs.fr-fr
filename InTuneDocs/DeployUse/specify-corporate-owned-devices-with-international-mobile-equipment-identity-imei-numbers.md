---
title: "Spécification de numéros IMEI | Microsoft Intune"
description: "Microsoft Intune permet aux administrateurs d’importer des numéros IMEI pour les plates-formes d’appareils mobiles afin d’identifier les appareils d’entreprise mobiles"
keywords: 
author: NathBarn
manager: angrobe
ms.date: 07/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1712bd39-562b-4409-9cec-155d5f4d8a39
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: e9cbf5858cc4e860b540f421b6d463b8e7a429cf
ms.openlocfilehash: 4e2092182dbda4523c19afeabc34aa0166962c40


---

# Spécifier des appareils d’entreprise avec des numéros IMEI (International Mobile Equipment Identity)
Microsoft Intune permet aux administrateurs d’importer les numéros (IMEI) pour les plateformes d’appareils mobiles disposant de ce type de numéro, pour faciliter l’identification des appareils mobiles d’entreprise. Une fois inscrits auprès d’Intune, les appareils avec des numéros IMEI importés peuvent être affichés sous **Groupes** > **Présentation** > **Tous les appareils**. Les listes de**Groupe d’appareils** indiquent des appareils avec des numéros IMEI importés en tant que **Entreprise** dans la colonne **Propriété**.

1. Dans la [console d’administration Microsoft Intune](http://manage.microsoft.com), choisissez **Groupes** &gt; **Tous les appareils** &gt; **Tous les appareils d’entreprise préinscrits** &gt; **Par IMEI (toutes les plateformes)**, puis choisissez **Ajouter des appareils**. Vous pouvez ajouter des appareils de deux manières :

    -   **Charger un fichier CSV qui contient les numéros de série** : créez une liste de valeurs séparées par des virgules (.csv) de deux colonnes sans en-tête, limitée à 5000 appareils ou à 5 Mo par fichier CSV.

        |||
        |-|-|
        |&lt;IMEI 1&gt;|&lt;Détails de l'appareil 1&gt;|
        |&lt;IMEI 2&gt;|&lt;Détails de l’appareil 2&gt;|
        Dans un éditeur de texte, ce fichier .csv s'affiche comme suit :

        ```
        AABBBBBBCCCCCCD,PO 1234
        AABBBBBBCCCCCCE,PO 1234
        ```

    -   **Ajouter manuellement les détails des appareils** : entrez le numéro IMEI et les détails de cinq appareils au maximum.

   Les *détails* sont destinés à l’administration, pour vous permettre d’identifier le numéro IMEI associé à un appareil. Ces informations ne sont pas envoyées à l’appareil, mais elles apparaissent dans la console Intune.

2.   Choisissez **Suivant**.
3.  Dans le volet **Passer en revue les appareils**, vous pouvez vérifier les numéros IMEI d’appareils importés. Vous pouvez également décider s’il faut remplacer les **Détails** pour les IMEI numéros réimportés. Vous pouvez décocher la case **Remplacer** pour conserver les détails actuels. Choisissez **Terminer** pour importer les numéros IMEI.
4.  Les numéros IMEI ajoutée et les descriptions sont ajoutés à la liste **Par IMEI (toutes les plateformes)**.

Quand l’appareil avec ce numéro IMEI s’inscrit, généralement quand un utilisateur installe l’application Portail d’entreprise et termine le processus d’inscription, l’appareil est étiqueté comme appareil d’entreprise et apparaît inscrit dans le groupe **Appareils IMEI**.



<!--HONumber=Jul16_HO4-->


