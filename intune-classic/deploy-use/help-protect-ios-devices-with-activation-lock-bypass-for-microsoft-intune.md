---
title: Gérer le verrou d’activation iOS sur les appareils
description: Microsoft Intune peut vous aider à gérer le verrou d’activation iOS, une fonctionnalité de l’application Rechercher mon iPhone pour les appareils iOS 7.1 et versions ultérieures.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 04/24/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: bb49e926-15c4-4f01-b6eb-cee6f7ee1984
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 37593e8c554cad73182873b01f6388bdb9cb0035
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31020127"
---
# <a name="help-protect-ios-devices-with-activation-lock-bypass-for-microsoft-intune"></a>Aider à protéger les appareils iOS avec le contournement du verrou d'activation pour Microsoft Intune

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Microsoft Intune peut vous aider à gérer le verrou d’activation iOS, une fonctionnalité de l’application Rechercher mon iPhone pour les appareils iOS 8.0 et versions ultérieures. Le verrou d’activation est activé automatiquement lorsqu’un utilisateur ouvre l’application Rechercher mon iPhone sur un appareil. Une fois qu’il est activé, l’ID et le mot de passe Apple de l’utilisateur doivent être entrés pour pouvoir : 

-   Désactiver Rechercher mon iPhone

-   Effacer l'appareil

-   Réactiver l'appareil

## <a name="how-activation-lock-affects-you"></a>Impact du verrou d'activation
Bien qu’il permette de sécuriser les appareils iOS et améliore les chances de récupération des données d’un appareil perdu ou volé, le verrou d’activation peut présenter quelques défis pour les administrateurs informatiques. Par exemple :

-   Un utilisateur configure le verrou d’activation sur un appareil. L'utilisateur quitte ensuite l'entreprise et rend l'appareil. Sans l’ID Apple et le mot de passe de l’utilisateur, il n’existe aucun moyen de réactiver l’appareil.

-   Vous avez besoin d’un rapport répertoriant tous les appareils sur lesquels le verrou d’activation est activé.

-   Vous voulez réaffecter certains appareils à un autre service lors de l’actualisation des appareils au sein de votre organisation. Vous ne pouvez réaffecter que les appareils sur lesquels le verrou d’activation n’est pas activé.

Pour résoudre ces problèmes, Apple a introduit le contournement du verrou d'activation dans iOS 7.1. Il vous permet de supprimer le verrou d'activation des appareils supervisés sans avoir l'ID Apple et le mot de passe de l'utilisateur. Les appareils supervisés peuvent générer un code de contournement du verrou d'activation spécifique à l'appareil, qui est stocké sur le serveur d'activation d'Apple.

> [!TIP]
> Le mode supervisé pour les appareils iOS vous permet d’utiliser l’outil Apple Configurator pour verrouiller un appareil et limiter ainsi la fonctionnalité à des usages professionnels spécifiques. Le mode surveillé est généralement destiné uniquement aux appareils appartenant à l'entreprise.

Vous trouverez un complément d’information sur le verrou d’activation [ici](https://support.apple.com/en-us/HT201365).

## <a name="how-intune-helps-you-manage-activation-lock"></a>Gestion du verrou d'activation dans Intune
Intune peut demander l’état du verrou d’activation des appareils supervisés qui exécutent iOS 8.0 et versions ultérieures. Pour les appareils supervisés uniquement, Intune peut récupérer le code de contournement du verrou d’activation et le transmettre directement à l’appareil. Si l’appareil a été réinitialisé, vous pouvez y accéder directement en utilisant un mot de passe vide et le code comme nom d'utilisateur.

**Les avantages sont les suivants** :

-   L’utilisateur bénéficie des avantages en termes de sécurité offerts par l’application Rechercher mon iPhone.

-   Vous pouvez permettre à l’utilisateur d’effectuer son travail en sachant que l’appareil peut être mis hors service ou déverrouillé lorsque vous devez le réaffecter.

## <a name="before-you-start"></a>Avant de commencer

Avant de pouvoir contourner le verrou d’activation sur les appareils, vous devez d’abord l’activer. Pour cela :

1. Utilisez les informations de la rubrique [Gérer des paramètres et des fonctionnalités sur vos appareils avec des stratégies Microsoft Intune](/intune-classic/deploy-use/ios-policy-settings-in-microsoft-intune).
2. Dans la section **Inscription** de la page Paramètres, configurez le paramètre **Autoriser le verrou d'activation quand l'appareil est en mode supervisé** sur **Oui**.
3. Enregistrez la stratégie et déployez-la sur les appareils sur lesquels vous souhaitez gérer le contournement du verrou d’activation.

## <a name="how-to-use-activation-lock-bypass-from-the-intune-admin-console"></a>Utilisation du contournement du verrou d'activation à partir de la console d'administration Intune
> [!IMPORTANT]
> Une fois que vous avez contourné le verrou d’activation sur un appareil, un nouveau verrou d’activation est automatiquement appliqué lorsque l’application Rechercher mon iPhone est lancée. Pour cette raison, **vous devez être en possession physique de l’appareil avant d’appliquer cette procédure**.

1.  Dans la [console d’administration Microsoft Intune](https://manage.microsoft.com), choisissez **Groupes** &gt; **Tous les appareils** &gt; **Tous les appareils d’entreprise**.

2.  Sélectionnez l’appareil dont vous voulez contourner le verrou d’activation. Choisissez **Contournement du verrou d’activation**.

3.  Lisez le message d’avertissement. Choisissez **Oui** pour continuer.

Vous pouvez examiner l'état de la demande de déverrouillage dans la page de détails de l'appareil.

## <a name="how-to-see-which-devices-are-using-activation-lock"></a>Identification des appareils qui utilisent le verrou d'activation
Vous pouvez identifier les appareils qui utilisent le verrou d'activation de deux manières :

-   Exécutez les **Rapports d'inventaire des appareils mobiles**. Ces rapports contiennent les colonnes **État du verrou d’activation** et **Supervisé**, qui indiquent l’état des appareils. Les valeurs possibles de **Supervisé** sont **Oui** ou **non**et les valeurs possibles de **État du verrou d'activation** sont les suivantes :

    -   Activé avec code de contournement

    -   Activé sans code de contournement (appareil non supervisé)

    -   Activé sans code de contournement (appareil inaccessible)

    -   Non activé

    Le champ **État du verrou d’activation** est vide pour les appareils qui n’exécutent pas iOS 8.0 ou une version ultérieure.

-   Sélectionnez un appareil dans un affichage de groupes pour faire apparaître l’état du verrou d’activation dans le volet d’informations de l’appareil.

    Si vous sélectionnez un appareil dans le nœud **Tous les appareils d’entreprise** et si le verrou d’activation est activé pour cet appareil, le code de contournement est également visible. Vous pouvez utiliser ce code pour émettre manuellement un contournement du verrou d'activation.

    > [!IMPORTANT]
    >Intune récupère un inventaire des appareils pour le verrou d’activation tous les 7 jours. Pour cette raison, il est possible que l’état du verrou d’activation des appareils ne soit pas immédiatement actualisé dans la console Intune.


### <a name="see-also"></a>Voir aussi
[Mettre des appareils hors service](retire-devices-from-microsoft-intune-management.md)
[Protéger vos appareils à l’aide du verrouillage à distance et de la réinitialisation du code secret](use-remote-lock-and-passcode-reset-in-microsoft-intune.md)
