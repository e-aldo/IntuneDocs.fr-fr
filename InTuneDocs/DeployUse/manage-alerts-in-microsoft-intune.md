---
# required metadata

title: Gérer les alertes | Microsoft Intune
description:
keywords:
author: Nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 74dc4ce4-21da-4f40-a07f-3eea34561eee

# optional metadata

ROBOTS: noindex,nofollow
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Gérer les alertes dans Microsoft Intune
Utilisez l’espace de travail **Alertes** de la console d’administration Intune pour évaluer l’état d’intégrité global des appareils de votre organisation et pour identifier les problèmes.

#### Affichage des alertes actives

1.  Dans la console d’administration Intune, effectuez une des opérations suivantes :

    -   **Pour afficher des informations générales sur les alertes**, notamment sur les trois premières alertes et le nombre total d’alertes actives, cliquez sur **Vue d’ensemble du système**. Vous pouvez cliquer sur les liens de ces alertes pour accéder à plus d'informations.

    -   **Pour afficher des données de synthèse pour les alertes**, cliquez sur **Alertes &gt; Vue d’ensemble**. Dans la page **Vue d’ensemble des alertes**, la zone **Résumé des types d’alerte** affiche un résumé des alertes. Les alertes critiques sont affichées en premier. Vous pouvez cliquer sur les liens de ces alertes pour accéder à plus d'informations.

        > [!NOTE]
        > Dans certains cas, un type d’alerte peut apparaître plusieurs fois dans la liste **Résumé des types d’alerte**.
        > 
        > Par exemple, les instances suivantes du type d'alerte Espace libre sur disque logique peuvent apparaître dans la liste :
        > 
        > -   3 Espace libre sur disque logique
        > -   2 Espace libre sur disque logique
        > 
        > Ce comportement se produit lorsque le même type d'alerte est généré pour les appareils exécutant différents systèmes d'exploitation. Dans l’exemple, la première instance du type d’alerte Espace libre sur disque logique, 3 Espace libre sur disque logique, peut avoir été générée par des ordinateurs exécutant Windows® 7. La deuxième instance du type d’alerte Espace libre sur disque logique peut avoir été générée par des ordinateurs exécutant Windows Vista®.

    -   **Pour afficher toutes les alertes actives**, cliquez sur **Alertes &gt; Toutes les alertes**. La page **Alertes** affiche une liste de toutes les alertes actives avec les colonnes suivantes :

        1.  **Nom** : nom du type d'alerte qui a généré l'alerte.

        2.  **Source** : lien vers la source de l'alerte. Si le seuil d’affichage du type d’alerte est défini sur **Afficher tout**, alors ce lien affiche un seul appareil. Si le seuil d'affichage du type d'alerte est défini sur une valeur, alors ce lien affiche la liste de tous les appareils concernés par cette alerte.

        3.  **Dernière modification** : indique l’heure de la dernière modification de l’alerte. Si une alerte est fermée, la date et l'heure de sa fermeture sont affichées.

        4.  **Gravité** : indique la gravité de l’alerte

## Affichage des alertes du panneau d'affichage
Le panneau d'affichage indique les annonces de service importantes telles qu'une prochaine mise à niveau, opération de maintenance ou interruption du service. Utilisez cette procédure pour afficher et gérer les alertes du panneau d'affichage.

#### Pour afficher et gérer les alertes du panneau d'affichage

1.  Dans la console d’administration Intune, cliquez sur **Vue d’ensemble du système**.

2.  Le cas échéant, les informations importantes concernant le service sont affichées dans la zone **Panneau d’affichage**.

3.  Pour exporter une alerte du panneau d’affichage vers un fichier HTML ou de valeurs séparées par des virgules (.csv), dans la console d’administration Intune, cliquez sur **Alertes &gt; Toutes les alertes &gt; Remarques**. Sélectionnez une alerte, cliquez sur l'icône d'exportation de la liste, puis suivez les instructions.

## Examen des états Intune
Dans l’espace de travail **Vue d’ensemble du système**, consultez les récapitulatifs d’état du système relatifs à Endpoint Protection, aux mises à jour, à l’intégrité de l’Agent, à la stratégie et aux logiciels pour identifier les problèmes et de donner la priorité à ceux nécessitant votre attention immédiate. Un lien vers le récapitulatif **État du service** est également fourni dans les messages d’erreur lorsque le système est interrompu. Le récapitulatif **État du service** donne des détails sur le problème de chaque emplacement et indique toujours l’heure et la date de la dernière mise à jour.

#### Pour afficher l'état de votre abonnement

1.  Dans la console d’administration Intune, cliquez sur **Vue d’ensemble du système**.

2.  Dans la zone **État du système**, vous pouvez examiner l’état des différents composants de Microsoft Intune. La plupart des éléments contiennent des liens qui vous permettent d'accéder à plus d'informations. Par exemple, sous **Endpoint Protection**, sélectionner le nombre d’instances permet d’afficher l’espace de travail **Endpoint Protection** avec la liste des programmes malveillants détectés. Sélectionner le nombre d’appareils affiche l’espace de travail **Groupes** avec une liste des appareils sur lesquels des logiciels malveillants ont été détectés.

## Fermeture et réactivation des alertes
Les alertes Intune restent actives jusqu’à ce qu’un des événements suivants se produise :

-   Le problème qui a causé la génération de l'alerte est résolu.

-   L'alerte est fermée manuellement.

-   5 jours passent une fois que l'alerte a été générée. Après 45 jours, l'alerte arrive à expiration et est automatiquement fermée.

Les alertes qui sont marquées comme fermées sont définitivement supprimées au bout de 90 jours.

#### Fermeture manuelle d'une alerte

1.  Dans la console d’administration Intune, effectuez une des opérations suivantes :

    1.  **Pour fermer une alerte à partir de la liste Alertes**, cliquez sur **Alertes &gt; Toutes les alertes**. Sélectionnez une alerte, puis cliquez sur **Fermer l’alerte**.

    2.  **Pour fermer une alerte pour un appareil spécifique**, cliquez sur **Groupes &gt; Tous les appareils**. Sélectionnez un appareil, puis cliquez sur **Afficher les propriétés**. Ensuite, sous l’onglet **Alertes**, sélectionnez une alerte, puis cliquez sur **Fermer l’alerte**.

    3.  **Pour fermer une alerte du panneau d’affichage**, cliquez sur **Vue d’ensemble du système**. Cliquez sur le **X** situé en regard de l’alerte du panneau d’affichage.

#### Pour afficher et réactiver des alertes fermés

1.  Dans la console d’administration Intune, cliquez sur **Alertes&gt; Toutes les alertes**.

2.  Dans la liste **Filtres**, cliquez sur **Fermée**..

    Les noms et les informations supplémentaires sur les alertes apparaissent dans le volet de la liste de gestion. Les détails de l'alerte sélectionnée apparaissent dans le volet de visualisation.

3.  Pour réactiver l’alerte sélectionnée, cliquez sur **Réactiver l’alerte**.

### Voir aussi
[Recevoir des alertes Microsoft Intune](get-notified-by-microsoft-intune-alerts.md)



<!--HONumber=May16_HO1-->


