---
title: Navigateurs et appareils mobiles pris en charge | Microsoft Intune
description: Appareils mobiles et ordinateurs pris en charge par Intune
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 11/22/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: aeeccfa4-0f14-447e-a3df-c8435c8a4bb2
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 149f3a3310907d131affeaad4bd372aa60be9206
ms.openlocfilehash: 80541567c535cfeb7fca3eda3c9143f4b11d7abb


---

# <a name="supported-mobile-devices-and-computers"></a>Ordinateurs et appareils mobiles pris en charge

Vous pouvez inscrire, puis gérer les types d’appareils suivants :

[!INCLUDE[mdm-supported-devices](../includes/mdm-supported-devices.md)]

En inscrivant des appareils, vous bénéficiez de [ces fonctionnalités](/Intune/get-started/choose-how-to-manage-devices).

Vous pouvez également gérer les PC Windows avec le logiciel client PC Intune. Le logiciel client Intune PC prend en charge Windows 7 et versions ultérieures, à l’exception de Windows 10 Famille. La gestion des PC avec le logiciel client fournit [ces fonctionnalités](https://docs.microsoft.com/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune).

Les clients qui ont Enterprise Management Suite peuvent également utiliser Azure Active Directory (Azure AD) pour inscrire des appareils Windows 10.

## <a name="microsoft-intune-supported-web-browsers"></a>Navigateurs web pris en charge par Microsoft Intune

Différentes tâches administratives vous obligent à utiliser l’un des sites web d’administration suivants.

- [Portail Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Console d'administration Microsoft Intune](https://admin.manage.microsoft.com/)

> [!Note]
> Microsoft Edge et les navigateurs mobiles ne sont pas pris en charge pour la console d’administration, car ils ne prennent pas en charge [Microsoft Silverlight](https://msdn.microsoft.com/en-us/library/cc838158(v=vs.95).aspx). La console Intune quitte progressivement Silverlight ; à terme, toutes les fonctionnalités de gestion d’applications et d’appareils mobiles d’Intune seront [disponibles dans le nouveau portail Microsoft Azure](https://blogs.technet.microsoft.com/enterprisemobility/2015/11/17/enhancing-managed-mobile-productivity/).

|Fonctionnalité Intune |Navigateurs pris en charge|
|---------|---------|
|Console d’administration Intune     |  Internet Explorer 10 ou version ultérieure<br /><br />Google Chrome (versions antérieures à la version 42)<br /><br />Mozilla Firefox avec Silverlight activé<br /><br />**Remarque** : Microsoft Edge et les navigateurs mobiles ne sont pas pris en charge par la console d’administration.                      
|Centre d’administration Office 365     |Tous les navigateurs, y compris les navigateurs mobiles et gérés  |
|Site web Portail d’entreprise     |**Sur les appareils mobiles :** Utiliser le navigateur web par défaut pour chaque plateforme prise en charge   <br /><br />**Sur les PC Windows :** Internet Explorer 10 ou version ultérieure, ou Microsoft Edge<br /><br />**Sur Mac OS X 10.9 ou version ultérieure :** Apple Safari    |

> [!Note]
> Microsoft Edge et les navigateurs mobiles ne sont pas pris en charge pour la console d’administration, car ils ne prennent pas en charge [Microsoft Silverlight](https://msdn.microsoft.com/en-us/library/cc838158(v=vs.95).aspx). La console Intune quitte progressivement Silverlight ; à terme, toutes les fonctionnalités de gestion d’applications et d’appareils mobiles d’Intune seront [disponibles dans le nouveau portail Microsoft Azure](https://blogs.technet.microsoft.com/enterprisemobility/2015/11/17/enhancing-managed-mobile-productivity/).

### <a name="office-365-portalhttpgomicrosoftcomfwlinkplinkid698854"></a>[Portail Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854)

**En tant qu’administrateur client, utilisez ce portail pour gérer votre abonnement**, y compris les tâches suivantes quand votre rôle d’administrateur l’autorise :

- Gérez les comptes d’utilisateur de l’abonnement et configurez la synchronisation d’annuaires à partir de votre instance Active Directory locale.
- Gérez des groupes d'utilisateurs, appelés groupes de sécurité.
- Attribuez aux utilisateurs des licences d’utilisation de Microsoft Intune.
- Configurez le nom de domaine que vous utilisez avec votre abonnement. Le nom de domaine définit le compte avec lequel les utilisateurs se connectent.
- Gérez la facturation et les détails de l'achat de votre abonnement, notamment le nombre de licences dont vous disposez ou la quantité d'espace de stockage cloud que vous pouvez utiliser.
- Trouvez des liens pour afficher l’intégrité du service Intune.
- En tant qu’administrateur client, vous pouvez vous connecter au portail Office 365 pour gérer l’abonnement même si votre compte ne possède pas de licence d’utilisation pour Intune.
- Tout utilisateur qui possède une licence Intune mais qui n’est pas administrateur peut utiliser ce portail pour réinitialiser le mot de passe de son compte et modifier son profil.
- Pour accéder au portail Office 365, l’état de connexion de votre compte doit être **Autorisé**. Cet état diffère de celui défini pour la possession d’une licence pour l’abonnement. Par défaut, tous les comptes d’utilisateur sont définis avec l’état **Autorisé**.


### <a name="microsoft-intune-administrator-consolehttpsmanagemicrosoftcom"></a>[Console d'administration Microsoft Intune](https://manage.microsoft.com/)

**En tant qu’administrateur de services, utilisez ce portail pour gérer les opérations quotidiennes**, notamment :

- Définir des stratégies pour les ordinateurs et les appareils mobiles.
- Télécharger et déployer des logiciels, comme des mises à jour logicielles et des applications.
- Gérez Endpoint Protection sur les ordinateurs.
- Afficher l'état des appareils et exécuter des rapports.
- Connectez-vous à ce portail. Vous devez avoir des autorisations d’administrateur de service ou être un administrateur client avec le rôle Administrateur général pour vous connecter à ce portail.


Seuls les utilisateurs disposant d’autorisations d’administrateur de service ou les administrateurs clients ayant le rôle Administrateur général peuvent se connecter à ce portail. Pour accéder à la console d’administration, votre compte doit posséder une licence d’utilisation de Microsoft Intune et son état de connexion doit être **Autorisé**.



<!--HONumber=Nov16_HO4-->


