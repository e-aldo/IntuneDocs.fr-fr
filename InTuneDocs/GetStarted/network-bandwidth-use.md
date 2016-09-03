---
title: "Utilisation de la bande passante réseau Intune | Microsoft Intune"
description: "Utilisation de la bande passante réseau Intune"
keywords: 
author: barlanmsft
manager: angrobe
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0f737d48-24bc-44cd-aadd-f0a1d59f6893
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 6d1c7c670341692d4ea0c823e4a9a96746b83067
ms.openlocfilehash: 6534eb7bbff2fba39e1dfa9be4ad01196156cc15


---

# Utilisation de la bande passante réseau Intune

Avant de configurer [!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)], consultez cette rubrique et les autres conditions requises répertoriées dans [Informations à connaître avant de commencer à utiliser Microsoft Intune](what-to-know-before-you-start-microsoft-intune.md).

Utilisez les informations contenues dans les sections suivantes pour planifier le trafic réseau des clients [!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)].

## Trafic réseau moyen
Le tableau suivant répertorie la taille et la fréquence approximatives du contenu commun qui transite sur le réseau pour chaque client.

> [!NOTE]
> Pour garantir que les ordinateurs et les appareils mobiles reçoivent les mises à jour et le contenu nécessaires du service [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)], ils doivent être régulièrement connectés à Internet. Le temps nécessaire pour recevoir des mises à jour ou un contenu varie, mais en règle générale, ils doivent rester connectés en continu à Internet au moins une heure par jour.

|Type de contenu|Taille approximative|Fréquence et détails|
|----------------|--------------------|-------------------------|
|[!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] .<br /><br />**Les conditions requises suivantes s’ajoutent à l’installation du client [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]**|125 Mo|**Une fois**<br /><br />La taille du téléchargement du client varie en fonction du système d'exploitation de l'ordinateur client.|
|Package d'inscription du client|15 Mo|**Une fois**<br /><br />D'autres téléchargements sont possibles lorsqu'il existe des mises à jour pour ce type de contenu.|
|Agent Endpoint Protection|65 Mo|**Une fois**<br /><br />D'autres téléchargements sont possibles lorsqu'il existe des mises à jour pour ce type de contenu.|
|Agent Operations Manager|11 Mo|**Une fois**<br /><br />D'autres téléchargements sont possibles lorsqu'il existe des mises à jour pour ce type de contenu.|
|Agent de stratégie|3 Mo|**Une fois**<br /><br />D'autres téléchargements sont possibles lorsqu'il existe des mises à jour pour ce type de contenu.|
|Assistance à distance via l'agent Microsoft Easy Assist|6 Mo|**Une fois**<br /><br />D'autres téléchargements sont possibles lorsqu'il existe des mises à jour pour ce type de contenu.|
|Opérations quotidiennes du client|6 Mo|**Tous les jours**<br /><br />Le client [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] communique régulièrement avec le service [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] pour vérifier l'existence de mises à jour et stratégies, et pour signaler l'état du client au service.|
|Mises à jour des définitions de logiciels malveillants pour Endpoint Protection|Varie<br /><br />Généralement entre 40 Ko et 2 Mo|**Tous les jours**<br /><br />Jusqu'à trois fois par jour.|
|Mise à jour du moteur Endpoint Protection|5 Mo|**Tous les mois**|
|Mises à jour logicielles|Varie<br /><br />La taille varie selon les mises à jour que vous déployez.|**Tous les mois**<br /><br />En règle générale, les mises à jour logicielles sont publiées le deuxième mardi de chaque mois.<br /><br />Un ordinateur nouvellement inscrit ou déployé peut utiliser plus de bande passante lors du téléchargement de l'ensemble des mises à jour précédemment publiées.|
|Service Packs ;|Varie<br /><br />La taille varie pour chaque Service Pack que vous déployez.|**Varie**<br /><br />Dépend du moment auquel vous déployez les Service Pack.|
|Distribution de logiciels|Varie<br /><br />La taille varie selon les logiciels que vous déployez.|**Varie**<br /><br />Dépend du moment auquel vous déployez les logiciels.|

## Possibilités de réduction de la bande passante réseau
Vous pouvez utiliser une ou plusieurs des méthodes suivantes pour réduire l'utilisation de la bande passante réseau par les clients [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].

### Utiliser un serveur proxy pour mettre en cache les requêtes de contenu
Vous pouvez utiliser un serveur proxy capable de mettre en cache le contenu afin de réduire les téléchargements en double et l'utilisation de la bande passante réseau par les clients qui demandent du contenu depuis Internet.

Un serveur proxy de mise en cache reçoit les requêtes de contenu provenant des ordinateurs clients de votre réseau, récupère ce contenu auprès d'Internet, puis est capable de mettre en cache à la fois les réponses HTTP et les téléchargements binaires. Le serveur utilise les informations mises en cache pour répondre aux requêtes ultérieures à partir des ordinateurs clients [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].

Voici les paramètres par défaut à utiliser pour un serveur proxy mettant en cache du contenu pour les clients [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].

|Paramètre|Valeur recommandée|Détails|
|-----------|---------------------|-----------|
|Taille du cache|De 5 à 30 Go|La valeur varie en fonction du nombre d'ordinateurs clients dans votre réseau et des configurations que vous utilisez. Pour éviter que des fichiers soient supprimés trop tôt, ajustez la taille du cache pour votre environnement.|
|Taille du fichier de cache individuel|950 Mo|Ce paramètre n'est peut-être pas disponible dans tous les serveurs proxy de mise en cache.|
|Types d'objet à mettre en cache|HTTP<br /><br />HTTPS<br /><br />BITS|[!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] sont des fichiers CAB extraits par téléchargement BITS (Service de transfert intelligent en arrière-plan) via HTTP.|
Pour plus d'informations sur l'utilisation d'un serveur proxy pour mettre en cache du contenu, consultez la documentation de votre solution de serveur proxy.

### Utiliser le service de transfert intelligent en arrière-plan sur les ordinateurs
[!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)] prend en charge l'utilisation du service de transfert intelligent en arrière-plan (BITS) sur un ordinateur Windows pour réduire la bande passante réseau utilisée pendant les périodes que vous configurez. Vous pouvez configurer une stratégie pour BITS dans la page **Bande passante réseau** de la stratégie de l’agent [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].

Pour en savoir plus sur BITS et les ordinateurs Windows, consultez [Background Intelligent Transfer Service](http://technet.microsoft.com/library/bb968799.aspx) (Service de transfert intelligent en arrière-plan) dans la bibliothèque TechNet.

### Utiliser BranchCache sur les ordinateurs
[!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] peuvent utiliser BranchCache pour réduire le trafic WAN. Les systèmes d'exploitation suivants qui sont pris en charge en tant que clients prennent également en charge BranchCache :

-   [!INCLUDE[nextref_client_7](../includes/nextref_client_7_md.md)]

-   [!INCLUDE[win8_client_2](../includes/win8_client_2_md.md)]

-   [!INCLUDE[winblue_client_2](../includes/winblue_client_2_md.md)]

Pour utiliser BranchCache, il doit être activé sur l’ordinateur client et ce dernier doit être configuré pour le **mode cache distribué**.

Par défaut, BranchCache et le mode cache distribué sont activés sur un ordinateur lors de l'installation du client [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]. Toutefois, si le client a déjà une stratégie de groupe qui désactive BranchCache, [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] ne remplace pas cette stratégie et BranchCache reste désactivé sur cet ordinateur.

Si vous utilisez BranchCache, vous devez communiquer avec les autres administrateurs de votre organisation qui gèrent la stratégie de groupe et la stratégie du pare-feu [!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)] pour vérifier qu'elles ne déploient pas une stratégie qui désactive BranchCache ou des exceptions de pare-feu. Pour plus d’informations sur BranchCache, consultez [Vue d’ensemble de BranchCache](http://technet.microsoft.com/library/hh831696.aspx).

### Voir aussi
[Informations à connaître avant de commencer à utiliser Microsoft Intune](what-to-know-before-you-start-microsoft-intune.md)



<!--HONumber=Aug16_HO4-->


