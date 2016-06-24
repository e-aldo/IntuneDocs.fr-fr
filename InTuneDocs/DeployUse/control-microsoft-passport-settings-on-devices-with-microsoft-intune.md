---
# required metadata

title: Contrôler les paramètres de Microsoft Passport sur les appareils | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 402bc5a1-ada3-4c4c-a0de-292d026b4444

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Contrôler les paramètres de Microsoft Passport sur les appareils avec Microsoft Intune
Vous pouvez intégrer Microsoft Intune à **Microsoft Passport for Work**, et disposer ainsi d’une autre méthode de connexion qui utilise Active Directory ou un compte Azure Active Directory pour remplacer un mot de passe, une carte à puce ou une carte à puce virtuelle.

Passport vous permet d’utiliser un **mouvement utilisateur**, au lieu d’un mot de passe, pour vous connecter. Un mouvement utilisateur peut être un simple code confidentiel, une authentification biométrique telle que Windows Hello ou un appareil externe tel qu’un lecteur d’empreintes digitales.

Intune s’intègre à Passport for Work de deux manières :

-   Vous pouvez utiliser la stratégie Intune pour contrôler les mouvements que les utilisateurs peuvent et ne peuvent pas utiliser pour se connecter.

-   Vous pouvez stocker des certificats d’authentification dans le fournisseur de stockage de clés de Passport for Work. Pour plus d’informations, consultez [Secure resource access with certificate profiles in Microsoft Intune](secure-resource-access-with-certificate-profiles.md) (Sécuriser l’accès aux ressources avec des profils de certificat dans Microsoft Intune).

## Pour créer une stratégie Passport for Work

1.  Dans la [console d’administration Microsoft Intune](https://manage.microsoft.com), cliquez sur **Administration** &gt; **Gestion des appareils mobiles** &gt; **Windows** &gt; **Passport for Work** pour ouvrir la page Passport for Work illustrée ci-dessous.

    ![Page Passport for Work](../media/passport.png)

2.  Choisissez l’un des paramètres suivants :
    - **Désactiver Passport for Work sur les appareils inscrits** : si vous ne souhaitez pas utiliser Passport for Work sur les appareils Windows 10, sélectionnez ce paramètre. Tous les autres paramètres à l’écran sont désactivés.
    - **Activer Passport for Work sur les appareils inscrits** : sélectionnez ce paramètre si vous souhaitez configurer les paramètres Passport for Work sur tous les appareils Windows 10.
    - **Non configuré** : sélectionnez ce paramètre si vous ne souhaitez pas utiliser Intune pour contrôler les paramètres Passport for Work. Les paramètres existants de Passport for Work sur les appareils Windows 10 ne seront pas modifiés. Tous les autres paramètres à l’écran sont désactivés.
3.  Si vous avez sélectionné **Activer Passport for Work sur les appareils inscrits**, configurez les paramètres requis qui seront appliqués à tous les appareils Windows 10 et Windows 10 Mobile inscrits.
3.  Quand vous avez terminé, cliquez sur **Enregistrer**.

## Passport for Work : paramètres de code confidentiel

  
- **Exiger une longueur minimale du code confidentiel**/**Exiger une longueur maximale du code confidentiel** : configure les appareils pour qu’ils utilisent les longueurs minimale et maximale de code confidentiel que vous spécifiez, afin d’aider à sécuriser la connexion. Le code confidentiel par défaut comporte six caractères, mais vous pouvez appliquer une longueur minimale de quatre caractères. La longueur maximale du code confidentiel est de 127 caractères.
- **Exiger des minuscules dans le code confidentiel**/**Exiger des majuscules dans le code confidentiel**/**Exiger des caractères spéciaux dans le code confidentiel** : vous pouvez aussi appliquer un code confidentiel plus fort en exigeant l’utilisation de majuscules, de minuscules et de caractères spéciaux dans le code confidentiel. Choisissez parmi :
    - **Autorisé** : les utilisateurs peuvent utiliser le type de caractère dans leur code confidentiel, mais cela n’est pas obligatoire.
    - **Requis** : les utilisateurs doivent inclure au moins l’un des types de caractères dans leur code confidentiel. Par exemple, il est courant d’exiger au moins une majuscule et un caractère spécial.
    - **Non autorisé** (par défaut) : les utilisateurs ne doivent pas utiliser ces types de caractères dans leur code confidentiel (ce comportement vaut également si le paramètre n’est pas configuré).
    > [!TIP] Les caractères spéciaux sont les suivants : **! " # $ % &amp; ' ( ) &#42; + , - . / : ; &lt; = &gt; ? @ [ \ ] ^ _ &#96; { &#124; } ~**.
- **Expiration du code confidentiel (jours)** : nous vous conseillons de spécifier une période d’expiration pour un code confidentiel, après laquelle les utilisateurs finaux doivent le modifier. La valeur par défaut est 41 jours. 
- **Conserver l’historique des codes confidentiels** : utilisez ce paramètre pour limiter la réutilisation des codes confidentiels précédemment utilisés. Par défaut, les cinq derniers codes confidentiels utilisés ne peuvent pas être réutilisés.


## Passport for Work : autres paramètres

- **Utiliser un module de plateforme sécurisée (TPM) :** une puce de module de plateforme sécurisée (TPM) fournit une couche supplémentaire de sécurité des données.<br>Choisissez l'une des valeurs suivantes :
    - **Requis** (par défaut) : seuls les appareils avec un module de plateforme sécurisée accessible peuvent approvisionner Passport for Work.
    - **Préféré** : les appareils tentent d’abord d’utiliser un module de plateforme sécurisée. Si ce n’est pas possible, ils peuvent utiliser un chiffrement logiciel.
- **Autoriser l’authentification biométrique** : permet d’utiliser l’authentification biométrique, telle que la reconnaissance des visages ou les empreintes digitales, à la place d’un code confidentiel pour Passport for Work. Les utilisateurs doivent toujours configurer un code confidentiel professionnel en cas d’échec de l’authentification biométrique. Choisissez parmi :
    - **Oui** : Passport for Work autorise l’authentification biométrique.
    - **Non** : Passport for Work empêche l’authentification biométrique (pour tous les types de compte).
- **Utiliser la détection d’usurpation avancée, si disponible** : détermine si les fonctionnalités d’anti-usurpation d’identité de Windows Hello sont utilisées sur les appareils qui les prennent en charge (par exemple, détection d’une photo de visage au lieu d’un visage réel).<br>Si cette option est définie sur **Oui**, Windows nécessite que tous les utilisateurs utilisent la détection d’usurpation pour les fonctions de reconnaissance faciale, si disponible.
- **Utiliser Remote Passport** : si cette option a la valeur **Oui**, les utilisateurs peuvent utiliser un appareil Remote Passport comme appareil mobile pour l’authentification d’ordinateur de bureau. L’ordinateur de bureau doit être joint à Azure Active Directory, et l’appareil mobile doit être configuré avec un code confidentiel Passport for Work.

## Informations supplémentaires
Pour plus d’informations sur Microsoft Passport, consultez [le guide](https://technet.microsoft.com/library/mt589441.aspx) dans la documentation de Windows 10.




<!--HONumber=Jun16_HO1-->


