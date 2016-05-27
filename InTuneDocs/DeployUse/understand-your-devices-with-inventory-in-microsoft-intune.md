---
# required metadata

title: Comprendre vos appareils grâce à l’inventaire de Microsoft Intune | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 312911fe-b963-4949-9911-ae425e0590b2

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Comprendre vos appareils grâce à l’inventaire de Microsoft Intune
Microsoft Intune vous permet d’afficher l’inventaire des appareils inscrits et des ordinateurs Windows qui exécutent le logiciel client Intune.

## Qu’est-ce qui est collecté auprès des appareils inscrits ?
Pour afficher l’inventaire recueilli par les appareils mobiles, exécutez les [rapports d’inventaire des appareils mobiles](understand-microsoft-intune-operations-by-using-reports.md). Intune collecte l’inventaire suivant auprès des appareils inscrits :

|Propriété|Collecte par|
|------------|-----------------------|
|**Nom**|Tous les appareils|
|**Système d'exploitation**|Tous les appareils|
|**Fabricant**|Tous les appareils|
|**Modèle**|Tous les appareils|
|**Canal de gestion**|Tous les appareils|
|**Enregistré avec AAD**|Tous les appareils à l’exception de Mac OS X|
|**Conforme**|Tous les appareils|
|**EAS activé**|Tous les appareils à l’exception de Mac OS X|
|**ID d’activation EAS**|Tous les appareils à l’exception de Mac OS X|
|**Heure d’activation EAS**|Tous les appareils à l’exception de Mac OS X|
|**État de gestion**|Tous les appareils|
|**Adresse de messagerie**|Tous les appareils|
|**ID Exchange ActiveSync**|Tous les appareils|
|**Jailbroken ou rootés**|Appareils iOS et Android uniquement|
|**ID d'appareil unique**|Tous les appareils à l’exception d’Exchange ActiveSync|
|**Numéro de série**|Appareils iOS, Mac OS X, Android, Windows 8.1, Windows 10|
|**Espace de stockage total**|Appareils iOS, Mac OS X, Windows 8.1, Windows 10|
|**Espace de stockage libre**|Appareils iOS, Mac OS X, Windows 8.1, Windows 10|
|**Numéro de téléphone**<br>Les téléphones classés comme appartenant à l’entreprise sont identifiés avec leur numéro de téléphone complet, par exemple, lorsque vous exécutez un rapport d’inventaire des appareils mobiles. Les numéros de téléphone de type « BYOD » sont masqués avec & #42 ; seuls les 4 derniers chiffres s’affichent.|Appareils iOS, Android et Windows Phone|
|**IMEI**|Appareils Exchange ActiveSync, iOS, Android et Windows Phone|
|**MEID**<br>MEID (Mobile Equipment Identifier)|Appareils iOS uniquement|
|**Adresse MAC du réseau Wi-Fi**|Tous les appareils à l’exception d’Exchange ActiveSync|
|**Opérateur de l'abonné**|Appareils iOS et Android uniquement|
|**Technologie cellulaire**|Appareils iOS et Android uniquement|
|**Supervisé**|Appareils iOS uniquement|
|**État du verrou d’activation**|Appareils iOS uniquement|
|**Date d'inscription**|Tous les appareils|
|**Dernière mise à jour**|Tous les appareils|
|**Ethernet MAC**|Appareils Mac OS X uniquement|
|**Verrou d’activation activé**|Appareils iOS uniquement|
|**Chiffrement activé**|Tous les appareils|

## Qu’est-ce qui est collecté auprès des PC Windows ?
> [!IMPORTANT]
> Cette section s’applique uniquement aux ordinateurs Windows qui exécutent le logiciel client Intune Windows PC.

Pour afficher l’inventaire recueilli par les ordinateurs Windows, exécutez les [rapports d’inventaire des ordinateurs](understand-microsoft-intune-operations-by-using-reports.md). Intune collecte l’inventaire suivant auprès des PC Windows :

-   **Nom**

-   **Type de châssis**

-   **Fabricant**

-   **Modèle**

-   **Système d'exploitation**

-   **Version de TPM**

-   **Espace disque total**

-   **Espace disque utilisé**

-   **Espace disque libre**

-   **Nom du disque du système d’exploitation**

-   **Espace du disque du système d’exploitation**

-   **Espace disponible du disque du système d’exploitation**

-   **Mémoire physique**

-   **Nom du processeur**

-   **Architecture du processeur**

-   **Vitesse de l’UC**

-   **Adresse IP**

-   **Numéro de série**

-   **Dernier utilisateur à se connecter**

-   **Utilisateur affecté**

-   **Dernière mise à jour**

### Voir aussi
[Analyse et rapports avec Microsoft Intune](monitoring-and-reports-with-microsoft-intune.md)



<!--HONumber=May16_HO1-->


