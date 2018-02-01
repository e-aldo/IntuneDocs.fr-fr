---
title: "Configurer Intune pour l’authentification unique des appareils iOS"
titlesuffix: Azure portal
description: "Découvrez comment configurer Intune pour l’authentification unique des appareils iOS."
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 12/7/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 07ac355232c1e4ac290c87191d3764e3df45327e
ms.sourcegitcommit: 4509039cbfd4d450324a3475fb5841906720baa1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2018
---
# <a name="configure-intune-for-ios-device-single-sign-on"></a>Configurer Intune pour l’authentification unique des appareils iOS

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

La plupart des applications métier nécessitent un certain niveau d’authentification utilisateur pour prendre en charge la sécurité. Dans de nombreux cas, cela oblige l’utilisateur à taper plusieurs fois les mêmes informations d’identification, ce qui peut être frustrant. Pour améliorer l’expérience utilisateur, les développeurs peuvent créer des applications qui utilisent l’authentification unique, réduisant ainsi le nombre de fois où un utilisateur doit fournir des informations d’identification.

Pour tirer parti de l’authentification unique des appareils iOS, les conditions suivantes doivent être remplies:

- Il doit y avoir une application codée pour rechercher le magasin d’informations d’identification utilisateur dans la charge utile d’authentification unique sur l’appareil iOS.
- Intune doit être configuré pour l’authentification unique des appareils iOS.

## <a name="to-configure-intune-for-ios-device-single-sign-on"></a>Pour configurer Intune pour l’authentification unique des appareils iOS


1. Connectez-vous au [portail Azure](https://portal.azure.com).
2. Choisissez **Autres services** > **Surveillance + Gestion** > **Intune**.
3. Dans le panneau **Intune**, choisissez **Configuration de l’appareil**.
2. Dans le panneau **Configuration de l’appareil**, choisissez **Profils**.
3. Dans le panneau des profils, choisissez **Créer un profil**, fournissez un nom et une description, puis configurez les paramètres suivants :
   - **Plateforme** : choisissez **iOS**. 
   - **Type de profil** : choisissez **Fonctionnalités de l’appareil**.
4. Dans le panneau **Fonctionnalités de l’appareil**, sélectionnez **Authentification unique**.

   ![Panneau Authentification unique](./media/sso-blade.png)

2. Utilisez le tableau récapitulatif suivant pour vous aider à remplir les champs du panneau **Authentification unique**. Pour plus d’informations, consultez les sections après le tableau.
   
   |Champ  |Notes|
   |---------|---------|
   |**Attribut de nom d’utilisateur d’AAD**|Attribut recherché par Intune dans AAD pour chaque utilisateur, et renseigné dans le champ correspondant (par exemple, UPN) avant de générer la charge utile XML installée sur l’appareil.|
   |**Domaine**|Partie domaine de l’URL.|
   |**Préfixes d’URL qui utiliseront l’authentification unique**|URL de votre organisation qui nécessitent une authentification unique de l’utilisateur.|
   |**Applications qui utiliseront l’authentification unique**|Applications sur l’appareil de l’utilisateur final qui utilisent la charge utile d’authentification unique.|
   |**Certificat de renouvellement des informations d’identification**|Si vous utilisez des certificats pour l’authentification, sélectionnez le certificat SCEP ou PFX déployé pour l’utilisateur en tant que certificat d’authentification.|

Les sections suivantes fournissent plus d’informations sur chacun des champs d’authentification unique.

### <a name="username-attribute-from-aad-and-realm"></a>Attribut de nom d’utilisateur d’AAD

- Si vous sélectionnez **Nom d’utilisateur principal** pour ce champ, il est analysé de la manière suivante :

   ![Attribut de nom d’utilisateur](media/User-name-attribute.png)

   Vous avez également la possibilité de remplacer le domaine par le texte que vous tapez dans la zone de texte **Domaine**.

   Par exemple, la société Contoso peut avoir plusieurs sous-régions telles qu’Amérique du Nord, Europe et Asie. Elle peut souhaiter que les utilisateurs en Asie utilisent la charge utile d’authentification unique et que l’application exige le nom d’utilisateur principal au format *username@asia.contoso.com*. Dans ce cas, si vous sélectionnez **Nom d’utilisateur principal**, par défaut le domaine pour chaque utilisateur est extrait d’AAD et peut être simplement *contoso.com*. Si vous le souhaitez, vous pouvez créer spécialement cette charge utile pour les utilisateurs en Asie, et remplacer le domaine par la valeur *asia.contoso.com*. Maintenant, le nom d’utilisateur principal de l’utilisateur final devient *username@asia.contoso.com*, et non *username@contoso.com*.

- Si vous sélectionnez **ID d’appareil**, Intune sélectionne automatiquement l’ID d’appareil Intune.

   Par défaut, les applications ont besoin d’utiliser uniquement l’ID d’appareil. Mais si votre application utilise le domaine en plus de l’ID d’appareil, vous pouvez taper le domaine dans la zone de texte **Domaine**.

   > [!NOTE]
   > Par défaut, vous devez laisser le champ de domaine vide si vous utilisez l’ID d’appareil.

### <a name="url-prefixes-that-will-use-single-sign-on"></a>Préfixes d’URL qui utiliseront l’authentification unique

Tapez ici les URL qui existent dans votre organisation et qui nécessitent une authentification de l’utilisateur.

Par exemple, quand un utilisateur se connecte à l’un de ces sites, l’appareil iOS utilise les informations d’identification d’authentification unique et l’utilisateur n’a pas besoin d’entrer d’informations d’identification supplémentaires. Toutefois, si vous avez activé l’authentification multifacteur, les utilisateurs doivent entrer la deuxième authentification.

> [!NOTE]
> Ces URL doivent être spécifiées sous la forme de noms de domaine complets correctement mis en forme. Apple exige qu’elles soient spécifiées au format `http://<yourURL.domain>`.

Les modèles de correspondance d’URL doivent commencer par `http://` ou `https://`. Une correspondance de chaîne simple est effectuée. Par conséquent, le préfixe d’URL `http://www.contoso.com/` ne correspond pas à `http://www.contoso.com:80/`. Avec iOS 9.0 ou version ultérieure, en revanche, vous pouvez utiliser un caractère générique * pour spécifier toutes les valeurs correspondantes. Par exemple, `http://*.contoso.com/` correspond à la fois à `http://store.contoso.com/` et à `http://www.contoso.com`.
Les modèles `http://.com` et `https://.com` correspondent respectivement à toutes les URL HTTP et HTTPS.

### <a name="apps-that-will-use-single-sign-on"></a>Applications qui utiliseront l’authentification unique

Indique les applications sur l’appareil de l’utilisateur final qui peuvent utiliser la charge utile d’authentification unique.

Le tableau `AppIdentifierMatches` doit contenir des chaînes qui correspondent aux ID de bundles d’applications. Ces chaînes peuvent être des correspondances exactes (par exemple, `com.contoso.myapp`) ou peuvent spécifier une correspondance de préfixe sur l’ID d’ensemble à l’aide du caractère générique *\. Le caractère générique doit apparaître après un point (.), et ne peut apparaître qu’une seule fois, à la fin de la chaîne (par exemple `com.contoso.*`). Quand un caractère générique est inclus, toute application dont l’ID de bundle commence par le préfixe bénéficie de l’accès au compte.

Le champ **Nom de l’application** sert à ajouter un nom convivial afin de vous aider à identifier l’ID de bundle.

### <a name="credential-renewal-certificate"></a>Certificat de renouvellement des informations d’identification

Si vous authentifiez vos utilisateurs finaux avec des certificats (et non des mots de passe), utilisez ce champ pour sélectionner le certificat SCEP ou PFX qui est déployé pour l’utilisateur en tant que certificat d’authentification. En général, il s’agit du même certificat que celui déployé pour l’utilisateur pour d’autres profils tels que VPN, Wi-Fi ou E-mail.

## <a name="next-steps"></a>Étapes suivantes

Pour obtenir des informations supplémentaires sur la configuration des fonctionnalités des appareils, consultez [Guide pratique pour configurer les paramètres de fonctionnalités d’appareil dans Microsoft Intune](device-features-configure.md).
