---
title: "Accès conditionnel à O365 en fonction de l’application | Microsoft Intune"
description: "Découvrez dans quelle mesure l’accès conditionnel pour la gestion des applications mobiles peut aider à contrôler les applications qui ont accès aux services O365."
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 10/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bd6bee60-5e39-42c8-a2e9-f5865ac3573f
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 64eaba6918c4a5c7ccc39fb8ccfeae729a34ff4c
ms.openlocfilehash: a03faa57f9bf1ec6784f0b1ec2d41d3f4cd88a12


---

# Créer une stratégie qui autorise uniquement les applications mobiles prenant en charge les stratégies GAM Intune à accéder aux services Office 365
Les [stratégies de gestion des applications mobiles Intune (GAM)](protect-apps-and-data-with-microsoft-intune.md) vous aident à protéger vos données d’entreprise sur les appareils qui sont inscrits pour la gestion dans Intune. Vous pouvez également utiliser des stratégies GAM sur les **appareils détenus par l’employé qui ne sont pas inscrits pour la gestion dans Intune**.  Dans ce cas, même si vous ne gérez pas l’appareil, vous devez toujours vous assurer que vos données et ressources d’entreprise sont protégées. À l’aide de l’accès conditionnel pour la gestion des applications mobiles, vous pouvez créer une stratégie qui autorise uniquement les applications mobiles prenant en charge les stratégies GAM Intune à accéder aux services O365 tels qu’Exchange Online.

Par exemple, en autorisant uniquement l’**application Microsoft Outlook** à accéder à Exchange Online, vous pouvez **bloquer les applications de messagerie intégrée sur iOS et Android**, qui ne bénéficient pas de la protection des données des stratégies GAM Intune pour récupérer des e-mails sur **Exchange Online**.

## Conditions préalables
**Avant** de pouvoir configurer une stratégie d’accès conditionnel pour la gestion des applications mobiles, vous devez avoir **un abonnement Enterprise Mobility + Security ou Azure Active Directory Premium**, et les utilisateurs doivent disposer d’une licence EMS ou Azure AD. Pour plus d’informations, consultez la [page de tarification d’Enterprise Mobility](https://www.microsoft.com/en-us/cloud-platform/enterprise-mobility-pricing) ou la [page de tarification d’Azure Active Directory](https://azure.microsoft.com/en-us/pricing/details/active-directory/).


## Applications prises en charge
**Exchange Online**
* Microsoft Outlook pour Android et iOS

## Chevauchement avec d’autres méthodes d’accès conditionnel et d’authentification
### Accès conditionnel pour la gestion des applications mobiles avec l’authentification basée sur un certificat Azure Active Directory

L’accès conditionnel pour la gestion des applications mobiles ne doit pas être utilisé avec l’authentification basée sur un certificat Azure Active Directory (Azure AD). Seule l’une ou l’autre peut être configurée à la fois.
### Accès conditionnel pour la gestion des applications mobiles avec accès conditionnel basé sur la conformité des appareils  

Vous pouvez configurer l’[accès conditionnel basé sur la conformité des appareils](restrict-access-to-email-and-o365-services-with-microsoft-intune.md)**** dans la [console Administrateur Intune](https://manage.microsoft.com) ou la [console de gestion Azure AD Premium] (https://manage.windowsazure.com). L’accès conditionnel basé sur la conformité des appareils oblige les utilisateurs à se connecter à Exchange Online uniquement via les appareils gérés par Intune qui sont compatibles avec la stratégie de conformité des appareils Intune ou des PC joints au domaine.  Si un utilisateur appartient à un ou plusieurs groupes de sécurité ciblés par des stratégies d’accès conditionnel pour la gestion des applications mobiles ou d’accès conditionnel basé sur la conformité des appareils, il doit satisfaire à l’une des deux conditions suivantes :
* L’application utilisée pour accéder au service est une application mobile prise en charge par l’accès conditionnel pour la gestion des applications mobiles, et l’appareil sur lequel l’application s’exécute est doté de l’**authentificateur iOS (appareils iOS)**, ou de l’**application Portail d’entreprise (appareils Android)**.
* L’appareil utilisé pour accéder au service est **géré par Intune et conforme** à la stratégie de conformité des appareils Intune ou est un **PC joint au domaine**.  Voici quelques exemples :
  * Si un utilisateur tente de se connecter à partir de l’**application de messagerie iOS native**, il doit se trouver sur un **appareil géré et conforme** dans la mesure où l’application de messagerie native n’est pas prise en charge par l’accès conditionnel pour la gestion des applications mobiles.
  * Si un utilisateur tente de se connecter à partir d’un **PC de bureau Windows**, la **stratégie d’accès conditionnel basé sur la conformité des appareils** s’applique, l’obligeant à utiliser un ordinateur joint au domaine.


## Ce qui se passe quand une application est utilisée dans le cadre de l’accès conditionnel pour la gestion des applications mobiles
L’accès conditionnel pour la gestion des applications mobiles vérifie l’identité de l’application approuvée au moyen d’une application broker qui doit être présente sur l’appareil :
*  Sur **iOS**, l’**application Azure Authenticator** est l’application broker.
* Sur **Android**, l’**application Portail d’entreprise Intune** est l’application broker. 

Les utilisateurs finaux qui se connectent pour la première fois à une application prise en charge par l’accès conditionnel pour la gestion des applications mobiles, telle que OneDrive ou Outlook, sont invités à installer l’application broker et à inscrire l’appareil auprès d’Azure AD. L’inscription de l’appareil dans Azure AD (anciennement appelé « jonction d’espace de travail ») entraîne la création d’un enregistrement et d’un certificat d’appareil servant de base à l’émission de jetons.  Cela **n’est pas** la même chose que l’**inscription MDM**. Aucun profil ou stratégie de gestion n’est appliqué et les applications sur l’appareil ne font l’objet d’aucun inventaire.  Le processus d’installation de l’application broker et d’inscription de l’appareil ne se produit qu’à la première utilisation d’une application gérée.


## Étapes suivantes
[Créer une stratégie Exchange Online pour les applications GAM](mam-ca-for-exchange-online.md)

[Bloquer les applications dépourvues de l’authentification moderne](block-apps-with-no-modern-authentication.md)

### Voir aussi

[Protéger les données d’application avec des stratégies GAM](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Oct16_HO2-->


