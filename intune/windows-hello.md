---
title: Guide pratique pour utiliser Windows Hello Entreprise
titleSuffix: Azure portal
description: "Apprenez à créer une stratégie permettant de contrôler l’utilisation de Windows Hello Entreprise sur les appareils gérés."
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 1/25/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3fb7de9fb320b74895b702167750e149eba34e1e
ms.sourcegitcommit: 93622d740cbd12043eedc25a9699cc4256e23e7e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/01/2018
---
# <a name="use-windows-hello-for-business"></a>Utilisation de Windows Hello Entreprise


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Microsoft Intune s’intègre à Windows Hello Entreprise (anciennement Microsoft Passport for Work), autre méthode de connexion qui utilise Active Directory ou un compte Azure Active Directory pour remplacer un mot de passe, une carte à puce ou une carte à puce virtuelle.

Hello Entreprise vous permet d’utiliser un *mouvement utilisateur*, au lieu d’un mot de passe, pour vous connecter. Un mouvement utilisateur peut être un simple code confidentiel, une authentification biométrique telle que Windows Hello ou un appareil externe tel qu’un lecteur d’empreintes digitales.

Intune s’intègre à Hello Entreprise de deux manières :

-   Vous pouvez utiliser la stratégie Intune pour contrôler les mouvements que les utilisateurs peuvent et ne peuvent pas utiliser pour se connecter.

<!--- -   You can store authentication certificates in the Windows Hello for Business key storage provider (KSP). For more information, see [Secure resource access with certificate profiles in Microsoft Intune](secure-resource-access-with-certificate-profiles.md). --->

> [!IMPORTANT]
> Dans les versions Windows 10 Desktop et Mobile antérieures à la mise à jour anniversaire, vous pouviez définir deux différents codes confidentiels pour l’authentification auprès de ressources :
- Le **code confidentiel de l’appareil** pouvait être utilisé pour déverrouiller l’appareil et se connecter aux ressources de cloud.
- Le **code confidentiel professionnel** servait à accéder aux ressources Azure AD sur les appareils personnels de l’utilisateur (BYOD).

>Dans la mise à jour anniversaire, ces deux codes confidentiels ont été fusionnés dans un même code confidentiel d’appareil.
Les stratégies de configuration Intune que vous définissez pour contrôler le code confidentiel de l’appareil, ainsi que toutes les stratégies Windows Hello Entreprise que vous avez configurées, définissent à présent la valeur de ce nouveau code confidentiel.
Si vous avez défini ces deux types de stratégie pour contrôler le code PIN, la stratégie Windows Hello Entreprise est appliquée aux appareils Windows 10 Desktop et Mobile.
Pour garantir la résolution des conflits de stratégie et l’application de la stratégie de code confidentiel, mettez à jour votre stratégie Windows Hello Entreprise en fonction des paramètres de votre stratégie de configuration, puis demandez à vos utilisateurs de synchroniser leurs appareils dans l’application Portail d’entreprise.



## <a name="create-a-windows-hello-for-business-policy"></a>Créer une stratégie Windows Hello Entreprise

1.  Dans le portail Azure, choisissez **Autres services** > **Surveillance + gestion** > **Intune**.

2.  Dans le panneau Intune, choisissez **Endpoint Protection**, puis **Gérer** > **Windows Hello Entreprise**.

3.  Dans le panneau qui s’ouvre, cliquez sur les paramètres **Par défaut**.

4.  Dans le panneau **Tous les utilisateurs**, cliquez sur **Propriétés**, puis entrez un **Nom** et éventuellement une **Description** pour les paramètres de Windows Hello Entreprise.

5. Dans le panneau **Tous les utilisateurs**, cliquez sur **Paramètres**, puis choisissez une des options suivantes pour **Configurer Windows Hello Entreprise** :

    - **Désactivé**. Si vous ne souhaitez pas utiliser Windows Hello Entreprise, sélectionnez ce paramètre. Tous les autres paramètres affichés à l’écran cessent d’être disponibles.
    - **Activée**. Sélectionnez ce paramètre si vous souhaitez configurer les paramètres Windows Hello Entreprise.
    - **Non configuré**. Sélectionnez ce paramètre si vous ne souhaitez pas utiliser Intune pour contrôler les paramètres Windows Hello Entreprise. Les paramètres Windows Hello Entreprise qui existent sur les appareils Windows 10 ne sont pas changés. Tous les autres paramètres dans le panneau ne sont pas disponibles.

6.  Si vous avez sélectionné **Activé** à l’étape précédente, configurez les paramètres nécessaires qui sont appliqués à tous les appareils Windows 10 et Windows 10 Mobile inscrits.

 - **Utiliser un module de plateforme sécurisée (TPM)**. Une puce TPM fournit une couche supplémentaire de sécurité des données.<br>Choisissez l'une des valeurs suivantes :

     - **Requis** (par défaut). Seuls les appareils avec un module de plateforme sécurisée (TPM) accessible peuvent configurer Windows Hello Entreprise.
     - **Préféré**. Les appareils tentent d’abord d’utiliser un module de plateforme sécurisée. Si ce n’est pas possible, ils peuvent utiliser le chiffrement logiciel.

 - **Exiger une longueur minimale du code confidentiel**/**Exiger une longueur maximale du code confidentiel**. Ce paramètre configure les appareils pour qu’ils utilisent les longueurs minimale et maximale de code confidentiel que vous spécifiez, afin d’optimiser la sécurisation de la connexion. Le code PIN par défaut comporte six caractères, mais vous pouvez appliquer une longueur minimale de quatre caractères. La longueur maximale du code confidentiel est de 127 caractères.

 - **Exiger des minuscules dans le code confidentiel**/**Exiger des majuscules dans le code confidentiel**/**Exiger des caractères spéciaux dans le code confidentiel**. Vous pouvez appliquer un code confidentiel plus puissant en exigeant l’utilisation de majuscules, de minuscules et de caractères spéciaux dans ce code. Choisissez parmi :

     - **Autorisé**. Les utilisateurs peuvent utiliser le type de caractère dans leur code confidentiel, mais cela n’est pas obligatoire.

     - **Requis**. Les utilisateurs doivent inclure au moins l’un des types de caractères dans leur code confidentiel. Par exemple, il est courant d’exiger au moins une majuscule et un caractère spécial.

     - **Non autorisé** (par défaut). Les utilisateurs ne doivent pas utiliser ces types de caractères dans leur code confidentiel. (Il s’agit également du comportement appliqué si le paramètre n’est pas configuré.)<br>Les caractères spéciaux comprennent : **! " # $ % &amp; ' ( ) &#42; + , - . / : ; &lt; = &gt; ? @ [ \ ] ^ _ &#96; { &#124; } ~**

 - **Expiration du code confidentiel (en jours)**. Nous vous conseillons de spécifier une période d’expiration pour un code confidentiel, après laquelle les utilisateurs finaux doivent le modifier. La valeur par défaut est 41 jours.

 - **Conserver l’historique des codes confidentiels**. Limite la réutilisation des codes confidentiels précédemment utilisés. Par défaut, les 5 derniers codes confidentiels ne peuvent pas être réutilisés.

 - **Autoriser l’authentification biométrique**. Permet d’utiliser l’authentification biométrique, telle que la reconnaissance faciale ou les empreintes digitales, à la place d’un code confidentiel pour Windows Hello Entreprise. Les utilisateurs doivent toujours configurer un code confidentiel professionnel en cas d’échec de l’authentification biométrique. Choisissez parmi :

     - **Oui**. Windows Hello Entreprise autorise l’authentification biométrique.
     - **Non**. Windows Hello Entreprise empêche l’authentification biométrique (pour tous les types de compte).

 - **Utiliser la détection d’usurpation avancée, si disponible**. Détermine si les fonctionnalités d’anti-usurpation d’identité de Windows Hello sont utilisées sur les appareils qui les prennent en charge (par exemple, la détection d’une photo de visage au lieu d’un visage réel).<br>Si cette option est définie sur **Oui**, Windows nécessite que tous les utilisateurs utilisent la détection d’usurpation pour les fonctions de reconnaissance faciale, si disponible.

 - **Utiliser la connexion par téléphone**. Si cette option est définie sur **Oui**, les utilisateurs peuvent utiliser un appareil Remote Passport comme appareil mobile pour l’authentification d’ordinateur du bureau. L’ordinateur de bureau doit être joint à Azure Active Directory, et l’appareil mobile doit être configuré avec un code confidentiel Windows Hello Entreprise.

## <a name="windows-holographic-for-business-support"></a>Prise en charge de Windows Holographic for Business

Windows Holographic for Business prend en charge les paramètres Windows Hello Entreprise suivants :

- Utiliser un module de plateforme sécurisée (TPM)
- Longueur minimale du code PIN
- Longueur maximale du code PIN
- Lettres minuscules dans le code PIN
- Lettres majuscules dans le code PIN
- Caractères spéciaux dans le code PIN
- Expiration du code confidentiel (jours)
- Mémoriser l’historique des codes confidentiels

## <a name="further-information"></a>Informations supplémentaires
Pour plus d’informations sur Microsoft Passport, consultez [le guide](https://technet.microsoft.com/library/mt589441.aspx) dans la documentation de Windows 10.
