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
ms.openlocfilehash: d33768206c53550ec1cb34d5c1ad5e2f33e4f8c8
ms.sourcegitcommit: dbea918d2c0c335b2251fea18d7341340eafd673
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-create-exceptions-to-the-intune-mobile-application-management-mam-data-transfer-policy"></a>Comment créer des exceptions à la stratégie de transfert de données de la Gestion des applications mobiles Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

En tant qu’administrateur, vous pouvez créer des exceptions à la stratégie de transfert de données de la Gestion des applications mobiles Intune. Une exception vous permet de choisir spécifiquement quelles applications non gérées peuvent transférer des données vers et depuis des applications gérées. Les applications non gérées que vous avez incluses dans la liste d’exceptions doivent être approuvées par le département informatique. 

>[!WARNING] 
> Vous êtes responsable des modifications apportées à la stratégie des exceptions de transfert de données. Les ajouts à cette stratégie autorisent les applications non gérées (les applications qui ne sont pas gérées par Intune) à accéder aux données protégées par les applications gérées. Cet accès à des données protégées peut entraîner des fuites de sécurité des données. Ajoutez seulement des exceptions de transfert de données pour les applications que votre organisation doit utiliser, mais qui ne prennent pas en charge les stratégies de protection d’application Intune. Ajoutez des exceptions seulement pour les applications dont vous ne considérez pas qu’elles représentent des risques de fuite de données.

Cette fonctionnalité s’applique quand vous créez une stratégie de protection d’application Intune avec le transfert de données défini sur **Applications gérées uniquement**. À part les exceptions que vous créez, quand votre stratégie de transfert de données est définie sur **Applications gérées uniquement**, le transfert reste limité aux applications gérées par Intune. Vous pouvez créer les restrictions à l’aide de protocoles (iOS) ou de packages (Android).

Vous pouvez configurer cette fonctionnalité pour activer les exceptions à la stratégie de protection d’application de la Gestion des applications mobiles Intune **Limiter le transfert de données**. Cette stratégie est nécessaire seulement si vous voulez autoriser le transfert de données vers une application qui ne prend pas en charge les stratégies de protection d’application Intune. Cette stratégie permet aux applications gérées par Intune avec les paramètres pour le transfert de données définis sur **Applications gérées uniquement**  d’appeler des applications non gérées basées sur un protocole d’URL (iOS) ou sur un nom de package (Android). Intune ajoute des applications natives essentielles à la liste par défaut des exceptions. 

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
