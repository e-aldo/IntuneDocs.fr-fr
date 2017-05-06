---
title: "Utilisation de la bande passante réseau Intune | Microsoft Docs"
description: "Utilisation de la bande passante réseau Intune"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/07/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0f737d48-24bc-44cd-aadd-f0a1d59f6893
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: c8715f96f532ee6bacda231e1147d03226ecbb48
ms.openlocfilehash: 5211d2222e5e8ef9328f60ed13f0146925194c5f
ms.lasthandoff: 04/26/2017


---

# <a name="intune-network-bandwidth-use"></a>Utilisation de la bande passante réseau Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

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

Pour gérer les ordinateurs qui se trouvent derrière des pare-feu et des serveurs proxy, vous devez configurer les pare-feu et les serveurs proxy afin d’autoriser les communications pour Intune.

### <a name="requirements-for-proxy-servers"></a>Configuration requise pour les serveurs proxy
Pour gérer les ordinateurs qui se trouvent derrière un serveur proxy, gardez à l’esprit que :

-   Le serveur proxy doit prendre en charge les protocoles **HTTP** et **HTTPS**, car les clients Intune utilisent ces deux protocoles
-   Intune prend en charge les serveurs proxy non authentifiés

Vous pouvez modifier les paramètres du serveur proxy sur des ordinateurs clients spécifiques ou utiliser des paramètres de stratégie de groupe pour modifier les paramètres pour tous les ordinateurs clients qui se trouvent derrière un serveur proxy spécifique.

### <a name="requirements-for-firewalls-ports-and-domains"></a>Configuration requise pour les pare-feu, les ports et les domaines
Les appareils gérés nécessitent des configurations qui permettent à **Tous les utilisateurs** d’accéder à des services à travers des pare-feu.

Le tableau suivant répertorie les ports et services auxquels le client Intune accède.

|**Domaine**|**Ports**|**Adresse IP**|
|------|----|---|
|manage.microsoft.com<br>a.manage.microsoft.com<br>admin.manage.microsoft.com<br>enterpriseenrollment.manage.microsoft.com<br>enterpriseenrollment-s.manage.microsoft.com<br>i.manage.microsoft.com<br>p.manage.microsoft.com<br>r.manage.microsoft.com|80 et 443|134.170.168.254<br>134.170.51.126
|m.manage.microsoft.com|80 et 443| 13.91.59.243<br>40.68.30.140
|portal.manage.microsoft.com|80 et 443|40.121.50.69<br>52.169.30.159
|account.manage.microsoft.com|80 et 443|157.56.13.59
|fef.msua01.manage.microsoft.com|80 et 443|138.91.243.97
|fef.msua02.manage.microsoft.com|80 et 443|23.96.112.46
|fef.msua04.manage.microsoft.com|80 et 443|23.96.112.28
|fef.msua05.manage.microsoft.com|80 et 443|138.91.244.151
|fef.msub01.manage.microsoft.com|80 et 443|137.135.128.214
|fef.msub02.manage.microsoft.com|80 et 443|137.135.130.29
|fef.msub03.manage.microsoft.com|80 et 443|23.97.165.17
|fef.msub05.manage.microsoft.com|80 et 443|23.97.166.52
|fef.msuc01.manage.microsoft.com|80 et 443|207.46.225.1
|fef.msuc02.manage.microsoft.com|80 et 443|23.98.66.118
|fef.msuc03.manage.microsoft.com|80 et 443|23.101.0.100
|fef.msuc05.manage.microsoft.com|80 et 443|207.46.154.33
|fef.msua06.manage.microsoft.com|80 et 443|104.42.188.1
|fei.msua01.manage.microsoft.com|80 et 443|138.91.240.131
|fei.msua02.manage.microsoft.com|80 et 443|23.96.112.143
|fei.msua04.manage.microsoft.com|80 et 443|23.96.112.147
|fei.msua05.manage.microsoft.com|80 et 443|138.91.240.163
|fei.msub01.manage.microsoft.com|80 et 443|137.135.130.85
|fei.msub02.manage.microsoft.com|80 et 443|137.135.132.149
|fei.msub03.manage.microsoft.com|80 et 443|23.97.160.232
|fei.msub05.manage.microsoft.com|80 et 443|23.97.162.250
|fei.msuc01.manage.microsoft.com|80 et 443|207.46.224.73
|fei.msuc02.manage.microsoft.com|80 et 443|23.98.66.194
|fei.msuc03.manage.microsoft.com|80 et 443|23.101.2.105
|fei.msuc05.manage.microsoft.com|80 et 443|207.46.147.126
|fei.msua06.manage.microsoft.com|80 et 443|138.91.149.190
|m.fei.msua01.manage.microsoft.com|80 et 443|138.91.240.131
|m.fei.msua02.manage.microsoft.com|80 et 443|23.96.112.143
|m.fei.msua04.manage.microsoft.com|80 et 443|23.96.112.147
|m.fei.msua05.manage.microsoft.com|80 et 443|138.91.240.163
|m.fei.msub01.manage.microsoft.com|80 et 443|137.135.130.85
|m.fei.msub02.manage.microsoft.com|80 et 443|137.135.132.149
|m.fei.msub03.manage.microsoft.com|80 et 443|23.97.160.232
|m.fei.msub05.manage.microsoft.com|80 et 443|23.97.162.250
|m.fei.msuc01.manage.microsoft.com|80 et 443|207.46.224.73
|m.fei.msuc02.manage.microsoft.com|80 et 443|23.98.66.194
|m.fei.msuc03.manage.microsoft.com|80 et 443|23.101.2.105
|m.fei.msuc05.manage.microsoft.com|80 et 443|207.46.147.126
|m.fei.msua06.manage.microsoft.com|80 et 443|138.91.149.190
|m.msua01.manage.microsoft.com|80 et 443|157.55.50.182
|m.msua02.manage.microsoft.com|80 et 443|134.170.49.121
|m.msua04.manage.microsoft.com|80 et 443|134.170.49.126
|m.msua05.manage.microsoft.com|80 et 443|157.55.240.190
|m.msua06.manage.microsoft.com|80 et 443|134.170.49.114
|m.msub01.manage.microsoft.com|80 et 443|94.245.121.50
|m.msub02.manage.microsoft.com|80 et 443|94.245.121.58
|m.msub03.manage.microsoft.com|80 et 443|94.245.121.56
|m.msub05.manage.microsoft.com|80 et 443|157.56.113.123
|m.msuc01.manage.microsoft.com|80 et 443|104.44.84.187
|m.msuc02.manage.microsoft.com|80 et 443|104.44.84.188
|m.msuc03.manage.microsoft.com|80 et 443|104.44.84.189
|m.msuc05.manage.microsoft.com|80 et 443|111.221.76.60
|msua01.manage.microsoft.com|80 et 443|157.55.50.182
|msua02.manage.microsoft.com|80 et 443|134.170.49.121
|msua04.manage.microsoft.com|80 et 443|134.170.49.126
|msua05.manage.microsoft.com|80 et 443|157.55.240.190
|msub01.manage.microsoft.com|80 et 443|94.245.121.50
|msub02.manage.microsoft.com|80 et 443|94.245.121.58
|msub03.manage.microsoft.com|80 et 443|94.245.121.56
|msub05.manage.microsoft.com|80 et 443|157.56.113.123
|msuc01.manage.microsoft.com|80 et 443|104.44.84.187
|msuc02.manage.microsoft.com|80 et 443|104.44.84.188
|msuc03.manage.microsoft.com|80 et 443|104.44.84.189
|msuc05.manage.microsoft.com|80 et 443|111.221.76.60
|msua06.manage.microsoft.com|80 et 443|134.170.49.114
|ncufun.account.manage.microsoft.com|80 et 443|157.55.252.224
|neufun.account.manage.microsoft.com|80 et 443|65.52.229.134
|portal.fei.msua01.manage.microsoft.com|80 et 443|138.91.240.131
|portal.fei.msua02.manage.microsoft.com|80 et 443|23.96.112.143
|portal.fei.msua04.manage.microsoft.com|80 et 443|23.96.112.147
|portal.fei.msua05.manage.microsoft.com|80 et 443|138.91.240.163
|portal.fei.msub01.manage.microsoft.com|80 et 443|137.135.130.85
|portal.fei.msub02.manage.microsoft.com|80 et 443|137.135.132.149
|portal.fei.msub03.manage.microsoft.com|80 et 443|23.97.160.232
|portal.fei.msub05.manage.microsoft.com|80 et 443|23.97.162.250
|portal.fei.msuc01.manage.microsoft.com|80 et 443|207.46.224.73
|portal.fei.msuc02.manage.microsoft.com|80 et 443|23.98.66.194
|portal.fei.msuc03.manage.microsoft.com|80 et 443|23.101.2.105
|portal.fei.msuc05.manage.microsoft.com|80 et 443|207.46.147.126
|portal.fei.msua06.manage.microsoft.com|80 et 443|138.91.149.190
|portal.msua01.manage.microsoft.com|80 et 443|157.55.50.182
|portal.msua02.manage.microsoft.com|80 et 443|134.170.49.121
|portal.msua04.manage.microsoft.com|80 et 443|134.170.49.126
|portal.msua05.manage.microsoft.com|80 et 443|157.55.240.190
|portal.msub01.manage.microsoft.com|80 et 443|94.245.121.50
|portal.msub02.manage.microsoft.com|80 et 443|94.245.121.58
|portal.msub03.manage.microsoft.com|80 et 443|94.245.121.56
|portal.msub05.manage.microsoft.com|80 et 443|157.56.113.123
|portal.msuc01.manage.microsoft.com|80 et 443|104.44.84.187
|portal.msuc02.manage.microsoft.com|80 et 443|104.44.84.188
|portal.msuc03.manage.microsoft.com|80 et 443|104.44.84.189
|portal.msuc05.manage.microsoft.com|80 et 443|111.221.76.60
|portal.msua06.manage.microsoft.com|80 et 443|134.170.49.114
|ssu2.manage.microsoft.com|80 et 443|157.55.99.181
|status.manage.microsoft.com|80 et 443|157.55.99.170
|swda01.manage.microsoft.com<br>swda02.manage.microsoft.com<br>swdb01.manage.microsoft.com<br>swdb02.manage.microsoft.com<br>swdc01.manage.microsoft.com<br>swdc02.manage.microsoft.com|80 et 443|93.184.215.200
|*.microsoftonline-p.com|80 et 443||
|has.spserv.microsoft.com<br>Requis pour le service d’attestation d’intégrité des appareils|443||
|*.microsoftonline-p.net|80 et 443||
|*.portal.office.com|80 et 443||
|*.spynet2.microsoft.com|443||
|c.microsoft.com|80 et 443||
|c1.microsoft.com|80 et 443||
|blob.core.windows.net|80 et 443||
|ajax.aspnetcdn.com|80 et 443||
|*.googleapis.com<br>Ce domaine est requis pour la prise en charge de JQuery lorsque vous utilisez le site Web du portail d'entreprise.|80 et 443||
|wustat.microsoft.com|80 et 443||
|Services Microsoft Update|\*.update.microsoft.com<br>download.microsoft.com<br>update.microsoft.com<br>\*.download.windowsupdate.com<br>download.windowsupdate.com<br>\*.windowsupdate.com<br>windowsupdate.microsoft.com<br>ntservicepack.microsoft.com|80 et 443|
|Demandes de recherche DNS|manage.microsoft.com.nsatc.net|80|
|Communication des appareils Samsung KNOX Standard via le pare-feu|Pour permettre aux appareils Samsung KNOX Standard de contacter des serveurs KNOX Standard par le biais du pare-feu, suivez les instructions contenues dans le FAQ Samsung KNOX Standard.||
|Communication par accès conditionnel|443|204.79.197.200|
|Documentation, aide et support</br></br>*.livemeeting.com<br>\*.microsoftonline.com<br>\*.social.technet.microsoft.com<br>blogs.technet.com<br>go.microsoft.com<br>onlinehelp.microsoft.com<br>www.microsoft.com|80|||


>[!div class="step-by-step"]

>[&larr; **Conditions préalables**](what-to-know-before-you-start-microsoft-intune.md)     [**Abonnement** &rarr;](start-with-a-paid-subscription-to-microsoft-intune-step-1.md)  

