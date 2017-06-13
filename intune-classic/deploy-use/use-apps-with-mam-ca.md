---
title: "Utilisation d’applications avec l’accès conditionnel pour la gestion des applications mobiles"
description: "Découvrez dans quelle mesure l’accès conditionnel pour la gestion des applications mobiles peut aider à contrôler les applications qui ont accès aux services O365."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 10/24/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 71dcf9bc-bfd1-4e06-b7ad-14b33a2288d0
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: ee407827c1c4eb7b113d29c301da0b9fa08fa86d
ms.contentlocale: fr-fr
ms.lasthandoff: 05/23/2017


---
# <a name="what-to-expect-when-using-an-app-with-app-based-ca"></a>Ce qui se passe quand une application est utilisée dans le cadre de l’accès conditionnel basé sur les applications

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

L’accès conditionnel basé sur les applications vérifie l’identité de l’application approuvée au moyen d’une application broker qui doit être présente sur l’appareil :
*  Sur **iOS**, l’**application Azure Authenticator** est l’application broker.
* Sur **Android**, l’**application Portail d’entreprise Intune** est l’application broker. 

Les utilisateurs finaux qui se connectent pour la première fois à une application prise en charge par l’accès conditionnel basé sur les applications, comme OneDrive ou Outlook, sont invités à installer l’application broker et à inscrire l’appareil auprès d’Azure AD. L’inscription de l’appareil dans Azure AD (anciennement appelé « jonction d’espace de travail ») entraîne la création d’un enregistrement et d’un certificat d’appareil servant de base à l’émission de jetons.  Cela **n’est pas** la même chose que l’**inscription MDM**. Aucun profil ou stratégie de gestion n’est appliqué et les applications sur l’appareil ne font l’objet d’aucun inventaire.  Le processus d’installation de l’application broker et d’inscription de l’appareil ne se produit qu’à la première utilisation d’une application gérée.

Voici une liste de propriétés qui proviennent directement de l’appareil :

* alternativeSecurityIds (hachage de clé publique et empreinte numérique du certificat Azure Active Directory)
* deviceOSType
* deviceOSVersion
* displayName

> [!NOTE]
> Sur les appareils Android :
  * L’application Portail d’entreprise doit être installée sur l’appareil, mais il n’est pas nécessaire que l’utilisateur final se connecte à l’application.
  * L’inscription de l’appareil doit être effectuée via l’application OneDrive ou Outlook.

## <a name="to-remove-a-device-from-azure-ad-registration"></a>Supprimer un appareil de l’inscription dans Azure AD.
Vous pouvez supprimer l’inscription de l’appareil par le biais de la console d’administration Azure AD, ce qui est généralement effectué par l’administrateur informatique.  L’utilisateur final peut également le faire lui-même sur l’appareil.

* **Console d’administration Azure AD** : dans la console d’administration Azure AD**, supprimez l’appareil que vous voulez retirer.
* **Appareil iOS** : ouvrez l’application Azure Authenticator, faites défiler vers la gauche jusqu’au compte et choisissez d’annuler l’inscription.  
* **Appareil Android** : désinstallez l’application Portail d’entreprise ou supprimez le compte des **paramètres système**.

## <a name="app-based-ca-with-device-based-ca"></a>Accès conditionnel basé sur l’application avec accès conditionnel basé sur l’appareil  

Vous pouvez configurer l’[accès conditionnel basé sur la conformité des appareils](restrict-access-to-email-and-o365-services-with-microsoft-intune.md)(**L’accès conditionnel basé sur la conformité des appareils**) dans la [console Administrateur Intune](https://manage.microsoft.com) ou la [console de gestion Azure AD Premium] (https://manage.windowsazure.com). L’accès conditionnel basé sur la conformité des appareils oblige les utilisateurs à se connecter à Exchange Online uniquement via les appareils gérés par Intune qui sont compatibles avec la stratégie de conformité des appareils Intune ou des PC joints au domaine.  Si un utilisateur appartient à un ou plusieurs groupes de sécurité ciblés par des stratégies d’accès conditionnel basé à la fois sur les applications et les appareils, l’utilisateur doit remplir l’une des deux conditions suivantes :
* L’application utilisée pour accéder au service est une application mobile prise en charge par l’accès conditionnel basé sur les applications. 
* L’appareil sur lequel l’application s’exécute est doté de l’**authentificateur iOS (appareils iOS)** ou de l’**application Portail d’entreprise (appareils Android)**.
* L’appareil utilisé pour accéder au service est **géré par Intune et conforme** à la stratégie de conformité des appareils Intune ou est un **PC joint au domaine**.  Voici quelques exemples :
  * Si un utilisateur tente de se connecter à partir de l’**application de messagerie iOS native**, il doit se trouver sur un **appareil géré et conforme** dans la mesure où l’application de messagerie native n’est pas prise en charge par l’accès conditionnel basé sur les applications.
  * Si un utilisateur tente de se connecter à partir d’un **PC de bureau Windows**, la **stratégie d’accès conditionnel basé sur la conformité des appareils** s’applique, l’obligeant à utiliser un ordinateur joint au domaine.

## <a name="next-steps"></a>Étapes suivantes
[Créer une stratégie Exchange Online pour les applications GAM](mam-ca-for-exchange-online.md)

[Bloquer les applications sans authentification moderne](block-apps-with-no-modern-authentication.md)

### <a name="see-also"></a>Voir aussi

[Protéger les données d’application à l’aide de stratégies de protection des applications](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)

