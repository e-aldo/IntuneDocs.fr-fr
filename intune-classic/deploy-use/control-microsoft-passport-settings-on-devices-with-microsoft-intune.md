---
title: Contrôler les paramètres Windows Hello Entreprise sur des appareils
description: Découvrez comment Intune s’intègre à Windows Hello Entreprise, autre méthode de connexion qui utilise Active Directory ou un compte Azure Active Directory pour remplacer un mot de passe, une carte à puce ou une carte à puce virtuelle.
keywords: ''
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 09/27/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 402bc5a1-ada3-4c4c-a0de-292d026b4444
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 63532456edbaf3579b9b6da8c0f376e7f4409c88
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/22/2018
---
# <a name="control-windows-hello-for-business-settings-on-devices-with-microsoft-intune"></a>Contrôler les paramètres Windows Hello Entreprise sur des appareils avec Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Microsoft Intune s’intègre à Windows Hello Entreprise (anciennement Microsoft Passport for Work), autre méthode de connexion qui utilise Active Directory ou un compte Azure Active Directory pour remplacer un mot de passe, une carte à puce ou une carte à puce virtuelle.

Hello Entreprise vous permet d’utiliser un *mouvement utilisateur*, au lieu d’un mot de passe, pour vous connecter. Un geste utilisateur peut être un simple code confidentiel, une authentification biométrique telle que Windows Hello ou un appareil externe tel qu’un lecteur d’empreintes digitales.

Intune s’intègre à Hello Entreprise de deux manières :

-   Vous pouvez utiliser la stratégie Intune pour contrôler les mouvements que les utilisateurs peuvent et ne peuvent pas utiliser pour se connecter.

-   Vous pouvez stocker des certificats d’authentification dans le fournisseur de stockage de clés de Windows Hello Entreprise. Pour plus d’informations, consultez [Sécuriser l’accès aux ressources avec des profils de certificat dans Microsoft Intune](secure-resource-access-with-certificate-profiles.md).

> [!IMPORTANT]
> Dans les versions Windows 10 Desktop et Mobile antérieures à la mise à jour anniversaire, vous pouviez définir deux différents codes confidentiels pour l’authentification auprès de ressources :
- Le **code confidentiel de l’appareil** pouvait être utilisé pour déverrouiller l’appareil et se connecter aux ressources de cloud.
- Le **code confidentiel professionnel** servait à accéder aux ressources Azure AD sur les appareils personnels de l’utilisateur (BYOD).

>Dans la mise à jour anniversaire, ces deux codes confidentiels ont été fusionnés dans un même code confidentiel d’appareil.
Les stratégies de configuration Intune que vous définissez pour contrôler le code confidentiel de l’appareil, ainsi que toutes les stratégies Windows Hello Entreprise que vous avez configurées, définissent à présent la valeur de ce nouveau code confidentiel.
Si vous avez défini ces deux types de stratégie pour contrôler le code confidentiel, la stratégie Windows Hello Entreprise sera appliquée aux appareils Windows 10 Desktop et Mobile.
Pour garantir la résolution des conflits de stratégie et l’application de la stratégie de code confidentiel, mettez à jour votre stratégie Windows Hello Entreprise en fonction des paramètres de votre stratégie de configuration, puis demandez à vos utilisateurs de synchroniser leurs appareils dans l’application Portail d’entreprise.



## <a name="create-a-windows-hello-for-business-policy"></a>Créer une stratégie Windows Hello Entreprise

1.  Dans la [console d’administration Microsoft Intune](https://manage.microsoft.com), choisissez **Administration** &gt; **Gestion des appareils mobiles** &gt; **Windows** &gt; **Windows Hello Entreprise** pour ouvrir la page Windows Hello Entreprise.

    ![Page Windows Hello Entreprise](../media/passport.png)

2.  Choisissez l’un des paramètres suivants :
    - **Désactiver Windows Hello Entreprise sur les appareils inscrits**. Si vous ne souhaitez pas utiliser Windows Hello Entreprise, sélectionnez ce paramètre. Tous les autres paramètres affichés à l’écran cessent d’être disponibles.
    - **Activer Windows Hello Entreprise sur les appareils inscrits**. Sélectionnez ce paramètre si vous souhaitez configurer les paramètres Windows Hello Entreprise.
    - **Non configuré**. Sélectionnez ce paramètre si vous ne souhaitez pas utiliser Intune pour contrôler les paramètres Windows Hello Entreprise. Les paramètres existants de Windows Hello Entreprise sur les appareils Windows 10 ne seront pas modifiés. Tous les autres paramètres affichés à l’écran sont indisponibles.
3.  Si vous avez sélectionné **Activer Windows Hello Entreprise sur les appareils inscrits**, configurez les paramètres obligatoires qui seront appliqués à tous les appareils Windows 10 et Windows 10 Mobile inscrits.
4.  Lorsque vous avez terminé, choisissez **Enregistrer**.


## <a name="settings-for-the-windows-hello-for-business-policy"></a>Paramètres pour la stratégie Windows Hello Entreprise

- **Utiliser un module de plateforme sécurisée (TPM)**. Une puce TPM fournit une couche supplémentaire de sécurité des données.<br>Choisissez l'une des valeurs suivantes :
    - **Requis** (par défaut). Seuls les appareils avec un module de plateforme sécurisée (TPM) accessible peuvent configurer Windows Hello Entreprise.
    - **Préféré**. Les appareils tentent d’abord d’utiliser un module de plateforme sécurisée. Si ce n’est pas possible, ils peuvent utiliser le chiffrement logiciel.
- **Exiger une longueur minimale du code confidentiel**/**Exiger une longueur maximale du code confidentiel**. Ce paramètre configure les appareils pour qu’ils utilisent les longueurs minimale et maximale de code confidentiel que vous spécifiez, afin d’optimiser la sécurisation de la connexion. Le code confidentiel par défaut comporte six caractères, mais vous pouvez appliquer une longueur minimale de quatre caractères. La longueur maximale du code confidentiel est de 127 caractères.
- **Exiger des minuscules dans le code confidentiel**/**Exiger des majuscules dans le code confidentiel**/**Exiger des caractères spéciaux dans le code confidentiel**. Vous pouvez appliquer un code confidentiel plus puissant en exigeant l’utilisation de majuscules, de minuscules et de caractères spéciaux dans ce code. Choisissez parmi :
    - **Autorisé**. Les utilisateurs peuvent utiliser le type de caractère dans leur code confidentiel, mais cela n’est pas obligatoire.
    - **Requis**. Les utilisateurs doivent inclure au moins l’un des types de caractères dans leur code confidentiel. Par exemple, il est courant d’exiger au moins une majuscule et un caractère spécial.
    - **Non autorisé** (par défaut). Les utilisateurs ne doivent pas utiliser ces types de caractères dans leur code confidentiel. (Il s’agit également du comportement appliqué si le paramètre n’est pas configuré.)<br>Les caractères spéciaux comprennent : **! " # $ % &amp; ' ( ) &#42; + , - . / : ; &lt; = &gt; ? @ [ \ ] ^ _ &#96; { &#124; } ~**.
- **Expiration du code confidentiel (en jours)**. Nous vous conseillons de spécifier une période d’expiration pour un code confidentiel, après laquelle les utilisateurs finaux doivent le modifier. La valeur par défaut est 41 jours.
- **Conserver l’historique des codes confidentiels**. Limite la réutilisation des codes confidentiels précédemment utilisés. Par défaut, les 5 derniers codes confidentiels ne peuvent pas être réutilisés.
- **Autoriser l’authentification biométrique**. Permet d’utiliser l’authentification biométrique, telle que la reconnaissance faciale ou les empreintes digitales, à la place d’un code confidentiel pour Windows Hello Entreprise. Les utilisateurs doivent toujours configurer un code confidentiel professionnel en cas d’échec de l’authentification biométrique. Choisissez parmi :
    - **Oui**. Windows Hello Entreprise autorise l’authentification biométrique.
    - **Non**. Windows Hello Entreprise empêche l’authentification biométrique (pour tous les types de compte).
- **Utiliser la détection d’usurpation avancée, si disponible**. Détermine si les fonctionnalités d’anti-usurpation d’identité de Windows Hello sont utilisées sur les appareils qui les prennent en charge (par exemple, la détection d’une photo de visage au lieu d’un visage réel).<br>Si cette option est définie sur **Oui**, Windows nécessite que tous les utilisateurs utilisent la détection d’usurpation pour les fonctions de reconnaissance faciale, si disponible.
- **Utiliser la connexion par téléphone**. Si cette option est définie sur **Oui**, les utilisateurs peuvent utiliser un appareil Remote Passport comme appareil mobile pour l’authentification d’ordinateur du bureau. L’ordinateur de bureau doit être joint à Azure Active Directory, et l’appareil mobile doit être configuré avec un code confidentiel Windows Hello Entreprise.

## <a name="further-information"></a>Informations supplémentaires
Pour plus d’informations sur Microsoft Passport, consultez [le guide](https://technet.microsoft.com/library/mt589441.aspx) dans la documentation de Windows 10.
