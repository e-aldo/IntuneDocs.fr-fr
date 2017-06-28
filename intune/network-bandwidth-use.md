---
title: "Utilisation de la bande passante réseau Intune"
description: "Utilisation de la bande passante réseau Intune"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 06/07/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0f737d48-24bc-44cd-aadd-f0a1d59f6893
ms.reviewer: angerobe
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: df3c42d8b52d1a01ddab82727e707639d5f77c16
ms.openlocfilehash: 030aa380a1491eb3be4fd8f480b0ddc9a7860448
ms.contentlocale: fr-fr
ms.lasthandoff: 06/08/2017


---

# <a name="intune-network-bandwidth-use"></a>Utilisation de la bande passante réseau Intune

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

Ce guide aide les administrateurs Intune à comprendre la configuration réseau requise pour le service Intune. Vous pouvez utiliser ces informations pour comprendre les besoins en bande passante et les paramètres d’adresse IP et de port nécessaires pour les paramètres de proxy.

## <a name="average-network-traffic"></a>Trafic réseau moyen
Ce tableau répertorie la taille et la fréquence approximatives du contenu commun qui transite sur le réseau pour chaque client.

> [!NOTE]
> Pour garantir que les ordinateurs et les appareils mobiles reçoivent les mises à jour et le contenu nécessaires du service Intune, ils doivent être régulièrement connectés à Internet. Le temps nécessaire pour recevoir des mises à jour ou un contenu varie, mais en règle générale, ils doivent rester connectés en continu à Internet au moins une heure par jour.

|Type de contenu|Taille approximative|Fréquence et détails|
|----------------|--------------------|-------------------------|
|Installation du client Intune<br /><br />**Les conditions requises suivantes s’ajoutent à l’installation du client Intune**|125 Mo|**Une fois**<br /><br />La taille du téléchargement du client varie en fonction du système d'exploitation de l'ordinateur client.|
|Package d'inscription du client|15 Mo|**Une fois**<br /><br />D'autres téléchargements sont possibles lorsqu'il existe des mises à jour pour ce type de contenu.|
|Agent Endpoint Protection|65 Mo|**Une fois**<br /><br />D'autres téléchargements sont possibles lorsqu'il existe des mises à jour pour ce type de contenu.|
|Agent Operations Manager|11 Mo|**Une fois**<br /><br />D'autres téléchargements sont possibles lorsqu'il existe des mises à jour pour ce type de contenu.|
|Agent de stratégie|3 Mo|**Une fois**<br /><br />D'autres téléchargements sont possibles lorsqu'il existe des mises à jour pour ce type de contenu.|
|Assistance à distance via l'agent Microsoft Easy Assist|6 Mo|**Une fois**<br /><br />D'autres téléchargements sont possibles lorsqu'il existe des mises à jour pour ce type de contenu.|
|Opérations quotidiennes du client|6 Mo|**Tous les jours**<br /><br />Le client Intune communique régulièrement avec le service Intune pour vérifier l’existence de mises à jour et stratégies, et pour signaler l’état du client au service.|
|Mises à jour des définitions de logiciels malveillants pour Endpoint Protection|Varie<br /><br />Généralement entre 40 Ko et 2 Mo|**Tous les jours**<br /><br />Jusqu'à trois fois par jour.|
|Mise à jour du moteur Endpoint Protection|5 Mo|**Tous les mois**|
|Mises à jour logicielles|Varie<br /><br />La taille varie selon les mises à jour que vous déployez.|**Tous les mois**<br /><br />En règle générale, les mises à jour logicielles sont publiées le deuxième mardi de chaque mois.<br /><br />Un ordinateur nouvellement inscrit ou déployé peut utiliser plus de bande passante lors du téléchargement de l'ensemble des mises à jour précédemment publiées.|
|Service Packs ;|Varie<br /><br />La taille varie pour chaque Service Pack que vous déployez.|**Varie**<br /><br />Dépend du moment auquel vous déployez les Service Pack.|
|Distribution de logiciels|Varie<br /><br />La taille varie selon les logiciels que vous déployez.|**Varie**<br /><br />Dépend du moment auquel vous déployez les logiciels.|

## <a name="ways-to-reduce-network-bandwidth-use"></a>Possibilités de réduction de la bande passante réseau
Vous pouvez utiliser une ou plusieurs des méthodes suivantes pour réduire l’utilisation de la bande passante réseau par les clients Intune.

### <a name="use-a-proxy-server-to-cache-content-requests"></a>Utiliser un serveur proxy pour mettre en cache les requêtes de contenu
Vous pouvez utiliser un serveur proxy capable de mettre en cache le contenu afin de réduire les téléchargements en double et l'utilisation de la bande passante réseau par les clients qui demandent du contenu depuis Internet.

Un serveur proxy de mise en cache reçoit les requêtes de contenu provenant des ordinateurs clients de votre réseau, récupère ce contenu auprès d'Internet, puis est capable de mettre en cache à la fois les réponses HTTP et les téléchargements binaires. Le serveur utilise les informations mises en cache pour répondre aux requêtes ultérieures à partir des ordinateurs clients Intune.

Voici les paramètres par défaut à utiliser pour un serveur proxy mettant en cache du contenu pour les clients Intune.

|Paramètre|Valeur recommandée|Détails|
|-----------|---------------------|-----------|
|Taille du cache|De 5 à 30 Go|La valeur varie en fonction du nombre d'ordinateurs clients dans votre réseau et des configurations que vous utilisez. Pour éviter que des fichiers soient supprimés trop tôt, ajustez la taille du cache pour votre environnement.|
|Taille du fichier de cache individuel|950 Mo|Ce paramètre n'est peut-être pas disponible dans tous les serveurs proxy de mise en cache.|
|Types d'objet à mettre en cache|HTTP<br /><br />HTTPS<br /><br />BITS|Les packages Intune sont des fichiers CAB extraits par téléchargement BITS (Service de transfert intelligent en arrière-plan) via HTTP.|
Pour plus d'informations sur l'utilisation d'un serveur proxy pour mettre en cache du contenu, consultez la documentation de votre solution de serveur proxy.

### <a name="use-background-intelligent-transfer-service-on-computers"></a>Utiliser le service de transfert intelligent en arrière-plan sur les ordinateurs
Intune prend en charge l’utilisation du service de transfert intelligent en arrière-plan (BITS) sur un ordinateur Windows pour réduire la bande passante réseau utilisée pendant les périodes que vous configurez. Vous pouvez configurer une stratégie pour BITS dans la page **Bande passante réseau** de la stratégie de l’agent Intune.

Pour en savoir plus sur BITS et les ordinateurs Windows, consultez [Background Intelligent Transfer Service](http://technet.microsoft.com/library/bb968799.aspx) (Service de transfert intelligent en arrière-plan) dans la bibliothèque TechNet.

### <a name="use-branchcache-on-computers"></a>Utiliser BranchCache sur les ordinateurs
Les clients Intune peuvent utiliser BranchCache pour réduire le trafic WAN. Les systèmes d'exploitation suivants qui sont pris en charge en tant que clients prennent également en charge BranchCache :

- Windows 7
- Windows 8.0
- Windows 8.1
- Windows 10

Pour utiliser BranchCache, il doit être activé sur l’ordinateur client et ce dernier doit être configuré pour le **mode cache distribué**.

Par défaut, BranchCache et le mode cache distribué sont activés sur un ordinateur lors de l’installation du client Intune. Toutefois, si le client a déjà une stratégie de groupe qui désactive BranchCache, Intune ne remplace pas cette stratégie et BranchCache reste désactivé sur cet ordinateur.

Si vous utilisez BranchCache, vous devez communiquer avec les autres administrateurs de votre organisation qui gèrent la stratégie de groupe et la stratégie du pare-feu Intune pour vérifier qu’elles ne déploient pas une stratégie qui désactive BranchCache ou des exceptions de pare-feu. Pour plus d’informations sur BranchCache, consultez [Vue d’ensemble de BranchCache](http://technet.microsoft.com/library/hh831696.aspx).

## <a name="network-communication-requirements"></a>Configuration requise des communications du réseau

Vous devez activer les communications du réseau entre les appareils que vous gérez et que vous utilisez pour gérer votre abonnement Intune, et les sites web requis pour les services cloud.

Intune n’utilise aucune infrastructure locale (comme des serveurs exécutant le logiciel Intune), mais il existe des possibilités d’utiliser une infrastructure locale comprenant des outils de synchronisation Exchange et Active Directory.

Pour gérer les ordinateurs qui se trouvent derrière des pare-feu et des serveurs proxy, vous devez configurer les pare-feu et les serveurs proxy afin d’autoriser les communications pour Intune. Pour gérer les ordinateurs qui se trouvent derrière un serveur proxy, gardez à l’esprit que :

-   Le serveur proxy doit prendre en charge les protocoles **HTTP (80)** et **HTTPS (443)**, car les clients Intune utilisent ces deux protocoles
-   Intune prend en charge les serveurs proxy non authentifiés

Vous pouvez modifier les paramètres du serveur proxy sur des ordinateurs clients spécifiques ou utiliser des paramètres de stratégie de groupe pour modifier les paramètres pour tous les ordinateurs clients qui se trouvent derrière un serveur proxy spécifique.

Les appareils gérés nécessitent des configurations qui permettent à **Tous les utilisateurs** d’accéder à des services à travers des pare-feu.

Les tableaux suivants répertorient les ports et services auxquels le client Intune accède :

|**Domaines**|**Adresse IP**|
|---------------------|-----------|
|portal.manage.microsoft.com<br> m.manage.microsoft.com |40.86.181.86<br>13.82.59.78<br>13.74.184.100<br>40.68.188.2<br>13.75.42.6<br>52.230.25.184 |
| sts.manage.microsoft.com | 13.93.223.241 <br>52.170.32.182 <br>52.164.224.159 <br>52.174.178.4 <br>13.75.122.143 <br>52.163.120.84|
|Manage.microsoft.com <br>i.manage.microsoft.com <br>r.manage.microsoft.com <br>a.manage.microsoft.com <br>p.manage.microsoft.com <br>EnterpriseEnrollment.manage.microsoft.com <br>EnterpriseEnrollment-s.manage.microsoft.com | 104.40.82.191 <br>13.82.96.212 <br>52.169.9.87 <br>52.174.26.23 <br>40.83.123.72 <br>13.76.177.110 |
|portal.fei.msua01.manage.microsoft.com<br>m.fei.msua01.manage.microsoft.com |13.64.196.170|
|fei.msua01.manage.microsoft.com<br> portal.fei.msua01.manage.microsoft.com <br>m.fei.msua01.manage.microsoft.com |40.71.34.120 |
|fei.msua02.manage.microsoft.com<br>portal.fei.msua02.manage.microsoft.com<br>m.fei.msua02.manage.microsoft.com |13.64.198.190|
|fei.msua02.manage.microsoft.com<br>portal.fei.msua02.manage.microsoft.com<br> m.fei.msua02.manage.microsoft.com |  13.64.198.190|
|fei.msua04.manage.microsoft.com<br> portal.fei.msua04.manage.microsoft.com <br>m.fei.msua04.manage.microsoft.com |13.64.188.173|
|fei.msua04.manage.microsoft.com<br> portal.fei.msua04.manage.microsoft.com <br>m.fei.msua04.manage.microsoft.com |40.71.32.174|
|fei.msua05.manage.microsoft.com <br>portal.fei.msua05.manage.microsoft.com <br>m.fei.msua05.manage.microsoft.com |13.64.197.181 |
|fei.msua05.manage.microsoft.com <br>portal.fei.msua05.manage.microsoft.com <br>m.fei.msua05.manage.microsoft.com |40.71.38.205|
|fei.amsua0502.manage.microsoft.com <br>portal.fei.amsua0502.manage.microsoft.com <br>m.fei.amsua0502.manage.microsoft.com |13.64.191.182 |
|fei.amsua0502.manage.microsoft.com <br>portal.fei.amsua0502.manage.microsoft.com <br>m.fei.amsua0502.manage.microsoft.com |40.71.37.51 |
|fei.msua06.manage.microsoft.com <br>portal.fei.msua06.manage.microsoft.com <br>m.fei.msua06.manage.microsoft.com |40.118.250.246 |
|fei.msua06.manage.microsoft.com <br>portal.fei.msua06.manage.microsoft.com <br>m.fei.msua06.manage.microsoft.com |13.90.142.194 |
|fei.amsua0602.manage.microsoft.com <br>portal.fei.amsua0602.manage.microsoft.com <br>m.fei.amsua0602.manage.microsoft.com |13.64.250.226 |
|fei.amsua0602.manage.microsoft.com <br>portal.fei.amsua0602.manage.microsoft.com <br>m.fei.amsua0602.manage.microsoft.com |13.90.151.142 |
|fei.msub01.manage.microsoft.com <br>portal.fei.msub01.manage.microsoft.com <br>m.fei.msub01.manage.microsoft.com |52.169.155.165 |
|fei.msub01.manage.microsoft.com <br>portal.fei.msub01.manage.microsoft.com <br>m.fei.msub01.manage.microsoft.com |52.174.188.97 |
|fei.amsub0102.manage.microsoft.com <br>portal.fei.amsub0102.manage.microsoft.com <br>m.fei.amsub0102.manage.microsoft.com |52.178.190.24 |
|fei.amsub0102.manage.microsoft.com <br>portal.fei.amsub0102.manage.microsoft.com <br>m.fei.amsub0102.manage.microsoft.com |52.174.16.215 |
|fei.msub02.manage.microsoft.com <br>portal.fei.msub02.manage.microsoft.com <br>m.fei.msub02.manage.microsoft.com |40.69.69.27 |
|fei.msub02.manage.microsoft.com <br>portal.fei.msub02.manage.microsoft.com <br>m.fei.msub02.manage.microsoft.com |52.166.196.199 |
|fei.msub03.manage.microsoft.com <br>portal.fei.msub03.manage.microsoft.com <br>m.fei.msub03.manage.microsoft.com |40.69.71.164 |
|fei.msub03.manage.microsoft.com <br>portal.fei.msub03.manage.microsoft.com <br>m.fei.msub03.manage.microsoft.com |52.174.182.102 |
|fei.msub05.manage.microsoft.com <br>portal.fei.msub05.manage.microsoft.com <br>m.fei.msub05.manage.microsoft.com |40.69.78.145 |
|fei.msub05.manage.microsoft.com <br>portal.fei.msub05.manage.microsoft.com <br>m.fei.msub05.manage.microsoft.com |52.174.192.105 |
|fei.msuc01.manage.microsoft.com <br>portal.fei.msuc01.manage.microsoft.com <br>m.fei.msuc01.manage.microsoft.com |13.94.46.250|
|fei.msuc01.manage.microsoft.com <br>portal.fei.msuc01.manage.microsoft.com <br>m.fei.msuc01.manage.microsoft.com |52.163.119.15 |
|fei.msuc02.manage.microsoft.com <br>portal.fei.msuc02.manage.microsoft.com <br>m.fei.msuc02.manage.microsoft.com |13.75.124.145 |
|fei.msuc02.manage.microsoft.com <br>portal.fei.msuc02.manage.microsoft.com <br>m.fei.msuc02.manage.microsoft.com |52.163.119.5|
|fei.msuc03.manage.microsoft.com <br>portal.fei.msuc03.manage.microsoft.com <br>m.fei.msuc03.manage.microsoft.com |52.175.35.226|
|fei.msuc03.manage.microsoft.com <br>portal.fei.msuc03.manage.microsoft.com <br>m.fei.msuc03.manage.microsoft.com |52.163.119.6|
|fei.msuc05.manage.microsoft.com <br>portal.fei.msuc05.manage.microsoft.com <br>m.fei.msuc05.manage.microsoft.com |52.175.38.24|
|fei.msuc05.manage.microsoft.com <br>portal.fei.msuc05.manage.microsoft.com <br>m.fei.msuc05.manage.microsoft.com |52.163.119.3|

