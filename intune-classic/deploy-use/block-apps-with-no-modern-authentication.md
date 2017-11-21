---
title: Bloquer les applications sans authentification moderne
description: 
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 10/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 098b652c-01e0-45d1-a731-620b0d3dc7c1
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 848178ecdd5580ca6dcb0b8f853e80abd2959d24
ms.sourcegitcommit: 82088d297eef629e3da6011681ead442ae7e25f7
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/15/2017
---
# <a name="block-apps-that-do-not-use-modern-authentication-adal"></a>Bloquer les applications qui n’utilisent pas l’authentification moderne (ADAL)

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Les stratégies d’accès conditionnel basé sur l’application avec protection des applications reposent sur l’utilisation, par les applications, de l’[authentification moderne](https://support.office.com/article/Using-Office-365-modern-authentication-with-Office-clients-776c0036-66fd-41cb-8928-5495c0f9168a), qui est une implémentation d’OAuth2. Les applications mobiles et de bureau Office les plus récentes utilisent l’authentification moderne ; cependant, il existe des applications tierces et des applications Office plus anciennes qui utilisent d’autres méthodes d’authentification telles que l’authentification de base et l’authentification basée sur les formulaires.

Pour bloquer l’accès à ces applications, nous recommandons l’opération suivante :

* Configurez des règles de revendications AD FS pour bloquer les protocoles autres que l’authentification moderne. Des instructions détaillées sont fournies dans le scénario 3 : [bloquer tout accès à O365, à l’exception des applications basées sur un navigateur](https://technet.microsoft.com/library/dn592182.aspx).
* Pour **SharePoint Online**, désactivez l’authentification plus ancienne dans le service SharePoint Online à l’aide de l’applet de commande PowerShell [Set-SPOTenant](https://technet.microsoft.com/library/fp161390.aspx) pour définir la propriété des protocoles d’authentification existants sur false :

```
 Set-SPOTenant -LegacyAuthProtocolsEnabled $false

```


>[!IMPORTANT]
>L’accès conditionnel basé sur l’application ne doit pas être utilisé avec l’authentification basée sur un certificat Azure Active Directory (Azure AD). Seule l’une ou l’autre peut être configurée à la fois.

### <a name="see-also"></a>Voir aussi
[Autoriser uniquement les applications prises en charge par Intune à accéder aux services O365](allow-policy-managed-apps-access-to-o365.md)
