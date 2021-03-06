---
title: Exceptions de la stratégie de transfert de données pour les applications
titleSuffix: Microsoft Intune
description: Créez des exceptions à la stratégie de transfert de données de la Gestion des applications mobiles Intune.
keywords: ''
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 03/28/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f9015e3a-c22c-42eb-90e6-ba48dee3a41d
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 812f73cb0857298f01967cebbb36f0b8220fb9c6
ms.sourcegitcommit: 179bea63fe52a8cce236b6ca8d82a6bd51bf17a5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2018
---
# <a name="how-to-create-exceptions-to-the-intune-mobile-application-management-mam-data-transfer-policy"></a>Comment créer des exceptions à la stratégie de transfert de données de la Gestion des applications mobiles Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

En tant qu’administrateur, vous pouvez créer des exceptions à la stratégie de transfert de données de la Gestion des applications mobiles Intune. Une exception vous permet de choisir spécifiquement quelles applications non gérées peuvent transférer des données vers et depuis des applications gérées. Les applications non gérées que vous incluez dans la liste d’exceptions doivent être approuvées par le département informatique. 

>[!WARNING] 
> Vous êtes responsable des modifications apportées à la stratégie des exceptions de transfert de données. Les ajouts à cette stratégie autorisent les applications non gérées (les applications qui ne sont pas gérées par Intune) à accéder aux données protégées par les applications gérées. Cet accès à des données protégées peut entraîner des fuites de sécurité des données. Ajoutez seulement des exceptions de transfert de données pour les applications que votre organisation doit utiliser, mais qui ne prennent pas en charge les stratégies de protection d’application Intune. Ajoutez des exceptions seulement pour les applications dont vous ne considérez pas qu’elles représentent des risques de fuite de données.

Dans une stratégie de protection d’application Intune, si vous affectez la valeur **Applications gérées par la stratégie** à **Autoriser l’application à transférer des données vers d’autres applications**, cela signifie que l’application peut transférer des données uniquement aux applications qui sont gérées par Intune. Si vous avez besoin d’autoriser le transfert de données vers des applications spécifiques qui ne prennent pas en charge les stratégies de protection d’application Intune, vous pouvez créer des exceptions à cette stratégie à l’aide de **Sélectionner les applications à exempter**. Les exemptions permettent aux applications gérées par Intune d’appeler des applications non gérées en fonction du protocole d’URL (iOS) ou du nom du package (Android). Par défaut, Intune ajoute des applications natives essentielles à cette liste d’exceptions. 

## <a name="ios-data-transfer-exceptions"></a>Exceptions du transfert des données iOS
Pour une stratégie ciblant iOS, vous pouvez configurer des exceptions de transfert de données par protocole d’URL. Pour ajouter une exception, consultez la documentation fournie par le développeur de l’application pour rechercher des informations sur les protocoles d’URL pris en charge. Pour plus d’informations sur les exceptions de transfert de données iOS, consultez [Paramètres de stratégie de protection d’application iOS - Exemptions du transfert de données](app-protection-policy-settings-ios.md#data-transfer-exemptions).

## <a name="android-data-transfer-exceptions"></a>Exceptions du transfert de données Android
Pour une stratégie ciblant Android, vous pouvez configurer des exceptions de transfert de données par nom de package d’application. Vous pouvez consulter la page de **Google Play Store** pour trouver le nom de package de l’application pour laquelle vous voulez ajouter une exception. Pour plus d’informations sur les exceptions du transfert de données Android, consultez [Paramètres de stratégie de protection d’application Android - Exemptions du transfert de données](app-protection-policy-settings-android.md#data-transfer-exemptions).


>[!TIP]
> Vous pouvez connaître l’ID de package d’une application en accédant à l’application dans le Google Play Store. L’ID de package est contenu dans l’URL de la page d’application. Par exemple, l’ID de package de l’application Microsoft Word est **com.microsoft.office.word**.

### <a name="example"></a>Exemple
Si vous ajoutez le package **Webex** comme exception à la stratégie de transfert des données de la Gestion des applications mobiles, les liens Webex qui se trouvent dans un e-mail d’une application Outlook gérée sont autorisés à s’ouvrir directement dans l’application Webex. Le transfert de données reste toujours limité dans les autres applications non gérées.

- Exemple **Webex** iOS : pour exempter l’application **Webex** et l’autoriser à être appelée par des applications gérées par Intune, vous devez ajouter une exception de transfert de données pour la chaîne suivante : <code>wbx</code>
    
 - Exemple **Plans** iOS : pour exempter l’application native **Plans** et l’autoriser à être appelée par des applications gérées par Intune, vous devez ajouter une exception de transfert de données pour la chaîne suivante : <code>maps</code>

- Exemple **Webex** Android : pour exempter l’application **Webex** et l’autoriser à être appelée par des applications gérées par Intune, vous devez ajouter une exception de transfert de données pour la chaîne suivante : <code>com.cisco.webex.meetings</code>
    
- Exemple **SMS** Android : pour exempter l’application native **SMS** et l’autoriser à être appelée par des applications gérées par Intune parmi diverses applications de messagerie et divers appareils Android, vous devez ajouter des exceptions de transfert de données pour les chaînes suivantes : 
    <code>com.google.android.apps.messaging</code>
    
    <code>com.android.mms</code>
    
    <code>com.samsung.android.messaging</code>

## <a name="next-steps"></a>Étapes suivantes

- [Créer et déployer des stratégies de protection d’applications](app-protection-policies.md)
- [Paramètres de stratégie de protection d’application iOS - Exemptions du transfert de données](app-protection-policy-settings-ios.md#data-transfer-exemptions)
- [Paramètres de stratégie de protection d’application Android - Exemptions du transfert de données](app-protection-policy-settings-android.md#data-transfer-exemptions)
