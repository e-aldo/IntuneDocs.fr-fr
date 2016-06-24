---
# required metadata

title: Présentation des opérations à l’aide de rapports | Microsoft Intune
description:
keywords:
author: Nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 857309c2-61c9-4c22-becf-4839fedeaece

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: pbala
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Présentation des opérations Microsoft Intune à l’aide de rapports
Utilisez les informations de cette rubrique pour créer et gérer des rapports Microsoft Intune qui fournissent des informations sur les logiciels, le matériel et les licences logicielles de votre organisation.

## Utilisation de rapports
Les rapports Intune fournissent des informations sur les logiciels, le matériel et les licences logicielles de votre organisation. Ces rapports peuvent vous aider à confirmer les besoins actuels et à prévoir les futures dépenses. L'espace de travail **Rapports** vous donne les outils nécessaires pour créer et gérer les rapports. Pour plus d’informations sur les rapports, consultez [Présentation des opérations Microsoft Intune à l’aide de rapports](understand-microsoft-intune-operations-by-using-reports.md).

### Types de rapport

|Type de rapport|Description|
|---------------|---------------|
|**Rapports de mise à jour**|Affiche les mises à jour logicielles qui ont été installées correctement sur les ordinateurs de votre organisation, en plus des mises à jour qui ont échoué, qui sont en attente ou qui sont nécessaires. Pour plus d’informations sur les mises à jour logicielles, consultez [Maintenir des PC Windows à jour avec les mises à jour logicielles](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md).|
|**Rapports sur les logiciels détectés**|Affiche les logiciels installés sur les ordinateurs de votre organisation et inclut les versions des logiciels. Vous pouvez filtrer les informations qui s'affichent en fonction de l'éditeur du logiciel et de la catégorie de logiciels. Vous pouvez développer les mises à jour dans la liste pour afficher plus de détails (par exemple les ordinateurs sur lesquels elles sont installées) en cliquant sur la flèche directionnelle à côté de l'élément de liste.<br /><br />Quand vous mettez hors service des ordinateurs ou modifiez leur appartenance aux groupes dans Intune, cela peut prendre plusieurs minutes avant que ces modifications soient prises en compte dans le rapport des logiciels détectés. Pour obtenir les données d'inventaire logiciel les plus précises, patientez quelques minutes après avoir déclassé des ordinateurs ou modifié leur appartenance aux groupes avant d'exécuter un rapport de logiciels détectés qui inclut ces ordinateurs.|
|**Rapports d'inventaire informatique**|Affiche des informations sur les ordinateurs gérés de votre organisation. Utilisez ce rapport pour planifier les achats de matériel et pour en savoir plus sur les besoins en matériel des utilisateurs de votre organisation. Pour plus d’informations sur l’utilisation des ordinateurs gérés, consultez [Gérer des PC Windows avec Microsoft Intune](manage-windows-pcs-with-microsoft-intune.md).|
|**Rapports d'inventaire des appareils mobiles**|Affiche des informations sur les appareils mobiles de votre organisation. Vous pouvez filtrer les informations qui s'affichent en fonction des groupes, du caractère « jailbroken » (débridé) ou rooté de l'appareil et du système d'exploitation.|
|**Rapports d'achat de licence**|Affichent les titres de tous les logiciels sous licence dans les groupes de licences sélectionnés, en fonction de leurs contrats de licence. Si les informations de licence logicielle n'ont pas été actualisées dans plus de 24 heures, elles sont actualisées lorsque vous générez un rapport de licence. Un rapport de licence n'est pas un calcul exact des titres de logiciel utilisés ou une preuve de la conformité aux contrats. Le rapport est un outil pour vous aider à prendre des décisions sur les licences pour votre organisation. Intune peut ne pas détecter certains produits pouvant avoir une licence en volume Microsoft. Les filtres disponibles sont les suivants :<br /><br />**Tous les contrats** affiche tous les produits logiciels sous licence qui sont gérés par Intune.<br /><br />**Contrats de licence en volume** affiche uniquement les produits logiciels provenant du Centre de gestion des licences en volume.<br /><br />**Autres contrats de licence logicielle** affiche les produits logiciels qui sont gérés en dehors du Centre de gestion des licences en volume.|
|**Rapports d'installation de licence**|Comparez les logiciels installés sur les ordinateurs de votre organisation à la couverture de contrat de licence actuelle selon le Centre de gestion des licences en volume. Les filtres incluent :<br /><br />**Tous les contrats** affiche tous les produits logiciels sous licence qui sont gérés par Intune.<br /><br />**Contrats de licence en volume** affiche uniquement les produits logiciels provenant du Centre de gestion des licences en volume.<br /><br />**Autres contrats de licence logicielle** affiche les produits logiciels qui sont gérés en dehors du Centre de gestion des licences en volume.|
|**Rapports sur les conditions générales**|Affichent les utilisateurs qui ont accepté les conditions générales que vous avez déployées, ainsi que la version qu’ils ont acceptée. Vous pouvez spécifier jusqu’à 10 utilisateurs ayant accepté les conditions générales qui ont été déployées, ou afficher l’état d’acceptation pour une condition particulière déployée.|
|**Rapports d'applications non conformes**|Affichent des informations sur les utilisateurs qui disposent d'applications installées figurant sur vos listes d'applications conformes et non conformes. Ce rapport permet de rechercher des utilisateurs et des appareils qui ne sont pas compatibles avec les stratégies d'application de votre société.|
|**Rapports de conformité du certificat**|Affichent les certificats délivrés aux utilisateurs et aux appareils via SCEP ou PKCS #12 (.PFX). Utilisez ce rapport pour rechercher les certificats émis, expirés et révoqués.|
|**Rapports d'historique de l'appareil**|Affiche l'historique des actions de mise hors service, de réinitialisation et de suppression. Utilisez ce rapport pour déterminer qui a initié des actions sur les appareils par le passé.|
|**Rapport matériel Mac OS X**|Affiche les détails matériels de tous les appareils Mac OS X inscrits dans les groupes que vous sélectionnez. Pour plus d’informations sur l’inventaire matériel collecté à partir de ces appareils, consultez [Comprendre vos appareils grâce à l’inventaire de Microsoft Intune](understand-your-devices-with-inventory-in-microsoft-intune.md).|
|**Rapport logiciel Mac OS X**|Affiche les logiciels installés sur tous les appareils Mac OS X dans les groupes que vous avez sélectionnés. Le rapport répertorie le nom du logiciel (comme ID de groupe), le nom de la version abrégée (ou nom convivial), la version et le nombre d’appareils où le logiciel est installé.|

#### Pour créer un rapport

1.  Dans la console d’administration Intune, cliquez sur **Rapports**, puis cliquez sur le type de rapport que vous voulez générer, tel que décrit dans le tableau ci-dessus.

2.  Dans la page **Créer un rapport** , acceptez les valeurs par défaut ou personnalisez-les pour filtrer les résultats qui seront renvoyés par le rapport. Par exemple, vous pouvez décider que seuls les logiciels publiés par Microsoft seront affichés dans le rapport de logiciels détectés.

3.  Cliquez sur **Afficher le rapport** pour ouvrir le rapport dans une nouvelle fenêtre.

Pour trier le rapport en fonction de l'une des colonnes affichées, cliquez sur l'en-tête de la colonne. En outre, certains rapports vous permettent de développer les éléments de la liste pour afficher plus de détails.

## Autres opérations relatives aux rapports
En outre, les rapports prennent en charge les actions suivantes :

|Action|Plus d'informations|
|----------|--------------------|
|**Imprimer**|Dans un rapport ouvert, cliquez sur l'icône d'impression et suivez les instructions.|
|**Exporter**|Dans un rapport ouvert, cliquez sur l'icône exportation et suivez les instructions. Vous pouvez exporter un rapport vers un fichier de valeurs séparées par des virgules (.csv) ou au format HTML.|
|**Enregistrer**|Sur la page **Créer un rapport** , chaque utilisateur peut enregistrer jusqu'à 100 rapports. Configurez les paramètres du rapport selon vos besoins, puis cliquez sur **Enregistrer**ou **Enregistrer sous** si vous voulez utiliser un autre nom.|
|**Chargement**|Sur la page **Créer un rapport** , cliquez sur **Charger** pour extraire tous les paramètres de rapport précédemment enregistrés.|
|**Supprimer**|Dans l'espace de travail **Rapports** , sélectionnez le type de rapport souhaité, cliquez sur **Charger**, puis dans la liste des rapports, cliquez sur l'icône (x) en regard du rapport.|

### Voir aussi
[Analyse et rapports avec Microsoft Intune](monitoring-and-reports-with-microsoft-intune.md)



<!--HONumber=Jun16_HO1-->


