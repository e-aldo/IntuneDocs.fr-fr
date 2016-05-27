---
# required metadata

title: Spécifier des appareils d’entreprise avec des numéros IMEI (International Mobile Equipment Identity) | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 1712bd39-562b-4409-9cec-155d5f4d8a39

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Spécifier des appareils d’entreprise avec des numéros IMEI (International Mobile Equipment Identity)
Microsoft Intune permet aux administrateurs d’importer les numéros (IMEI) pour les plateformes d’appareils mobiles disposant de ce type de numéro, pour faciliter l’identification des appareils mobiles d’entreprise. Une fois inscrit dans Intune, les appareils avec des numéros IMEI importés sont marqués comme appareils d’entreprise, ce qui peut être utilisé pour appliquer des stratégies différentes de celles appliquées aux appareils personnels.

1. Dans la [console d’administration Microsoft Intune](http://manage.microsoft.com), accédez à **Groupes** &gt; **Tous les appareils** &gt; **Tous les appareils d’entreprise préinscrits** &gt; **Par IMEI (toutes les plateformes)**, puis cliquez sur **Ajouter des appareils**…. Vous pouvez ajouter des appareils de deux manières :

    -   **Charger un fichier CSV qui contient les numéros de série** : créez une liste de valeurs séparées par des virgules (.csv) de deux colonnes sans en-tête, limitée à 5000 appareils ou à 5 Mo par fichier CSV.

        |||
        |-|-|
        |&lt;IMEI 1&gt;|&lt;Détails de l'appareil 1&gt;|
        |&lt;IMEI 2&gt;|&lt;Détails de l’appareil 2&gt;|
        Dans un éditeur de texte, ce fichier .csv s'affiche comme suit :

        ```
        AA-BBBBBB-CCCCCC-D,PO 1234
        AA-BBBBBB-CCCCCC-E,PO 1234
        ```

    -   **Ajouter manuellement les détails des appareils** : entrez le numéro IMEI et les détails de cinq appareils au maximum.

   Les *détails* sont destinés à l’administration, pour vous permettre d’identifier le numéro IMEI associé à un appareil. Ces informations ne sont pas envoyées à l’appareil, mais elles apparaissent dans la console Intune.

2.   Cliquez sur **Suivant**.
3.  Dans le volet **Passer en revue les appareils**, vous pouvez vérifier les numéros IMEI d’appareils importés. Vous pouvez également décider s’il faut remplacer les **Détails** pour les IMEI numéros réimportés. Vous pouvez décocher la case **Remplacer** pour conserver les détails actuels. Cliquez sur **Terminer** pour importer les numéros IMEI.
4.  Les numéros IMEI ajoutée et les descriptions sont ajoutés à la liste **Par IMEI (toutes les plateformes)**.

Quand l’appareil avec ce numéro IMEI s’inscrit, généralement quand un utilisateur installe l’application Portail d’entreprise et termine le processus d’inscription, l’appareil est étiqueté comme appareil d’entreprise et apparaît inscrit dans le groupe **Appareils IMEI**.


<!--HONumber=May16_HO1-->


