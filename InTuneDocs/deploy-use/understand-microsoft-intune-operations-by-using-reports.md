---
title: "Présentation des opérations à l’aide de rapports | Microsoft Docs"
description: "Créez et gérez des rapports sur les logiciels, le matériel et les licences logicielles de votre organisation."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/27/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 857309c2-61c9-4c22-becf-4839fedeaece
ms.reviewer: pbala
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: cc1a3c8c3e2f25ee154db964de2601510e32f1ea
ms.openlocfilehash: 41354f0eee051bd9c691a27830264f6c95502fa5
ms.lasthandoff: 02/28/2017



---

# <a name="understand-microsoft-intune-operations-by-using-reports"></a>Présentation des opérations Microsoft Intune à l’aide de rapports

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Utilisez les informations de cette rubrique pour créer et gérer des rapports Microsoft Intune qui fournissent des informations sur les logiciels, le matériel et les licences logicielles de votre organisation.

## <a name="using-reports"></a>Utilisation des rapports
Les rapports Intune fournissent des informations sur les logiciels, le matériel et les licences logicielles de votre organisation. Ces rapports peuvent vous aider à confirmer les besoins actuels et à prévoir les futures dépenses. L'espace de travail **Rapports** vous donne les outils nécessaires pour créer et gérer les rapports. 

### <a name="report-types"></a>Types de rapport

|Type de rapport|Description|
|---------------|---------------|
|**Rapports sur les mises à jour**|Affichent les mises à jour logicielles qui se sont correctement installées sur les ordinateurs de votre organisation. Ils indiquent également celles qui ont échoué, qui sont en attente ou qui sont nécessaires. Pour plus d’informations sur les mises à jour logicielles, consultez [Maintenir des PC Windows à jour avec les mises à jour logicielles](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md).|
|**Rapports sur les logiciels détectés**|Affichent les logiciels installés sur les ordinateurs de votre organisation. Les versions des logiciels sont incluses. Vous pouvez filtrer les informations qui s'affichent en fonction de l'éditeur du logiciel et de la catégorie de logiciels. Vous pouvez développer les mises à jour dans la liste pour afficher d’autres détails (par exemple les ordinateurs sur lesquels une mise à jour est installée) en choisissant la flèche directionnelle située en regard de l’élément de liste.<br /><br />Quand vous mettez hors service des ordinateurs ou modifiez leur appartenance aux groupes dans Intune, cela peut prendre plusieurs minutes avant que ces modifications soient prises en compte dans le rapport des logiciels détectés. Pour obtenir les données d'inventaire logiciel les plus précises, patientez quelques minutes après avoir déclassé des ordinateurs ou modifié leur appartenance aux groupes avant d'exécuter un rapport de logiciels détectés qui inclut ces ordinateurs.|
|**Rapports sur l’inventaire des ordinateurs**|Affiche des informations sur les ordinateurs gérés de votre organisation. Utilisez ce rapport pour planifier les achats de matériel et pour en savoir plus sur les besoins en matériel des utilisateurs de votre organisation. Pour plus d’informations sur l’utilisation des ordinateurs gérés, consultez [Gérer des PC Windows avec Microsoft Intune](manage-windows-pcs-with-microsoft-intune.md).|
|**Rapports sur l’inventaire des appareils mobiles**|Affiche des informations sur les appareils mobiles de votre organisation. Vous pouvez filtrer les informations qui s'affichent en fonction des groupes, du caractère « jailbreaké » ou rooté de l'appareil et du système d'exploitation.|
|**Rapports sur l’achat de licences**|Affichent les titres de tous les logiciels sous licence dans les groupes de licences sélectionnés, en fonction de leurs contrats de licence. Si les informations de licence logicielle n'ont pas été actualisées dans plus de 24 heures, elles sont actualisées lorsque vous générez un rapport de licence. Un rapport de licence n'est pas un calcul exact des titres de logiciel utilisés ou une preuve de la conformité aux contrats. Le rapport est un outil pour vous aider à prendre des décisions sur les licences pour votre organisation. Intune peut ne pas détecter certains produits pouvant avoir une licence en volume Microsoft. Les filtres disponibles sont les suivants :<br /><br />**Tous les contrats** affiche tous les produits logiciels sous licence qui sont gérés par Intune.<br /><br />Le filtre **Contrats de licence en volume** affiche uniquement les produits logiciels du Centre de gestion des licences en volume (VLSC).<br /><br />Le filtre **Autres contrats de licence logicielle** affiche les produits logiciels qui sont gérés en dehors du Centre de gestion des licences en volume (VLSC).|
|**Rapports sur l’installation des licences**|Comparent les logiciels installés sur les ordinateurs de votre organisation à la couverture du contrat de licence actuel, conformément au Centre de gestion des licences en volume (VLSC). Les filtres incluent :<br /><br />**Tous les contrats** affiche tous les produits logiciels sous licence qui sont gérés par Intune.<br /><br />**Contrats de licence en volume** affiche uniquement les produits logiciels provenant du Centre de gestion des licences en volume.<br /><br />Le filtre **Autres contrats de licence logicielle** affiche les produits logiciels qui sont gérés en dehors du Centre de gestion des licences en volume (VLSC).|
|**Rapports sur les conditions générales**|Indiquent si les utilisateurs ont accepté les conditions générales que vous avez déployées, ainsi que la version qu’ils ont acceptée. Vous pouvez consulter l’acceptation des conditions générales qui ont été déployées pour 10 utilisateurs maximum, ou afficher l’état d’acceptation d’une condition particulière déployée.|
|**Rapports sur les applications non conformes**|Affichent des informations sur les utilisateurs qui disposent d'applications installées figurant sur vos listes d'applications conformes et non conformes. Ce rapport permet de rechercher des utilisateurs et des appareils qui ne sont pas compatibles avec les stratégies d'application de votre société.|
|**Rapport sur la conformité des certificats**|Montrez quels certificats ont été délivrés aux utilisateurs et aux appareils via SCEP ou PKCS #12 (.PFX). Utilisez ce rapport pour rechercher les certificats émis, expirés et révoqués.|
|**Rapports sur l’historique des appareils**|Affichez le journal de l’historique des actions de mise hors service, de réinitialisation et de suppression. Utilisez ce rapport pour déterminer qui a initié des actions sur les appareils par le passé.|
|**Rapports d’attestation d’intégrité**|Affichez l’état des appareils mobiles.|
|**Rapport matériel Mac OS X**|Affiche les détails matériels de tous les appareils Mac OS X inscrits dans les groupes que vous sélectionnez. Pour plus d’informations sur l’inventaire matériel collecté à partir de ces appareils, consultez [Comprendre vos appareils grâce à l’inventaire de Microsoft Intune](understand-your-devices-with-inventory-in-microsoft-intune.md).|
|**Rapport logiciel Mac OS X**|Affiche les logiciels installés sur tous les appareils Mac OS X dans les groupes que vous avez sélectionnés. Le rapport répertorie le nom du logiciel (comme ID de groupe), le nom de la version abrégée (ou nom convivial), la version et le nombre d’appareils où le logiciel est installé.|

#### <a name="to-create-a-report"></a>Pour créer un rapport

1.  Dans la console d’administration Intune, choisissez **Rapports**. Choisissez ensuite le type de rapport à générer, comme décrit dans le tableau précédent.

2.  Dans la page **Créer un rapport** , acceptez les valeurs par défaut ou personnalisez-les pour filtrer les résultats qui seront renvoyés par le rapport. Par exemple, vous pouvez décider que seuls les logiciels publiés par Microsoft seront affichés dans le rapport sur les logiciels détectés.

3.  Choisissez **Afficher le rapport** pour ouvrir le rapport dans une nouvelle fenêtre.

Pour trier le rapport en fonction de l’une des colonnes affichées, cliquez sur l’en-tête de la colonne. Certains rapports vous permettent également de développer les éléments de la liste pour afficher plus de détails.

## <a name="more-report-actions"></a>Autres opérations relatives aux rapports
Les rapports prennent aussi en charge les actions suivantes :

|Action|Plus d'informations|
|----------|--------------------|
|**Imprimer**|Dans un rapport ouvert, cliquez sur l’icône d’impression et suivez les instructions.|
|**Exporterer**|Dans un rapport ouvert, cliquez sur l’icône d’exportation et suivez les instructions. Vous pouvez exporter un rapport vers un fichier de valeurs séparées par des virgules (.csv) ou au format HTML.|
|**Enregistrer**|Sur la page **Créer un rapport**, chaque utilisateur peut enregistrer jusqu'à 100 rapports. Configurez les paramètres du rapport selon vos besoins, puis choisissez **Enregistrer**ou **Enregistrer sous** (si vous voulez utiliser un autre nom).|
|**Charger**|Dans la page **Créer un rapport**, cliquez sur **Charger** pour extraire tous les paramètres de rapport déjà enregistrés.|
|**Supprimer**|Dans l’espace de travail **Rapports**, sélectionnez le type de rapport souhaité et choisissez **Charger**. Ensuite, dans la liste des rapports, choisissez l’icône Supprimer (x) à côté du rapport.|



