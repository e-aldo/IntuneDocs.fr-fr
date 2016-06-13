---
# required metadata

title: Aider à protéger les appareils iOS avec le contournement du verrou d’activation | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: bb49e926-15c4-4f01-b6eb-cee6f7ee1984

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Aider à protéger les appareils iOS avec le contournement du verrou d'activation pour Microsoft Intune
Microsoft Intune peut vous aider à gérer le verrou d’activation iOS, une fonctionnalité de l’application Rechercher mon iPhone pour les appareils iOS 7.1 et versions ultérieures. Le verrou d'activation est activé automatiquement quand l'application Rechercher mon iPhone est utilisée sur un appareil. Une fois qu’il est activé, l’ID et le mot de passe Apple de l’utilisateur doivent être entrés pour pouvoir :

-   désactiver Rechercher mon iPhone ;

-   effacer l'appareil ;

-   réactiver l'appareil.

## Impact du verrou d'activation
Bien que le verrou d’activation permette de sécuriser les appareils iOS et améliore les chances de récupération en cas de perte ou de vol, cette fonctionnalité peut présenter quelques défis pour les administrateurs informatiques. Exemple :

-   L'un de vos utilisateurs configure le verrou d'activation sur un appareil. L'utilisateur quitte ensuite l'entreprise et rend l'appareil. Sans l’ID Apple et le mot de passe de l’utilisateur, il n’existe aucun moyen de réactiver l’appareil.

-   Vous avez besoin d’un rapport répertoriant tous les appareils sur lesquels le verrou d’activation est activé.

-   Lors d'une actualisation des appareils de votre organisation, vous souhaitez réaffecter certains appareils à un autre service. Vous ne pouvez réaffecter que les appareils sur lesquels le verrou d’activation n’est pas activé.

Pour résoudre ces problèmes, Apple a introduit le contournement du verrou d'activation dans iOS 7.1. Il vous permet de supprimer le verrou d'activation des appareils supervisés sans avoir l'ID Apple et le mot de passe de l'utilisateur. Les appareils supervisés peuvent générer un code de contournement du verrou d'activation spécifique à l'appareil, qui est stocké sur le serveur d'activation d'Apple.

> [!TIP]
> Le mode supervisé pour les appareils iOS vous permet d'utiliser l'outil de configuration Apple pour verrouiller un appareil et limiter ainsi la fonctionnalité à des usages professionnels spécifiques. Le mode surveillé est généralement destiné uniquement aux appareils appartenant à l'entreprise.

## Gestion du verrou d'activation dans Intune
Intune peut demander l’état du verrou d’activation des appareils supervisés et non supervisés qui exécutent iOS 7.1 et versions ultérieures. Pour les appareils supervisés uniquement, Intune peut récupérer le code de contournement du verrou d’activation et le transmettre directement à l’appareil. Si l’appareil a été réinitialisé, vous pouvez y accéder directement en utilisant le code comme nom d’utilisateur et un mot de passe vide.

**Les avantages sont les suivants** :

-   L’utilisateur bénéficie des avantages en termes de sécurité offerts par l’application Rechercher mon iPhone.

-   Vous pouvez laisser l’utilisateur effectuer son travail en sachant que, quand vous devez réaffecter l’appareil, vous pouvez le mettre hors service ou le déverrouiller.

## Utilisation du contournement du verrou d'activation à partir de la console d'administration Intune
> [!IMPORTANT]
> Une fois que vous avez contourné le verrou d'activation sur un appareil, il applique automatiquement un nouveau verrou d'activation en cas d'ouverture de l'application Rechercher mon iPhone. Pour cette raison, **vous devez être en possession physique de l’appareil avant d’appliquer cette procédure**.

1.  Dans la [console d’administration Microsoft Intune](https://manage.microsoft.com), choisissez **Groupes** &gt; **Tous les appareils** &gt; **Tous les appareils d’entreprise**.

2.  Sélectionnez l’appareil dont vous voulez contourner le verrou d’activation. Choisissez **Contournement du verrou d’activation**.

3.  Lisez le message d’avertissement. Choisissez **Oui** pour continuer.

Vous pouvez examiner l'état de la demande de déverrouillage dans la page de détails de l'appareil.

## Identification des appareils qui utilisent le verrou d'activation
Vous pouvez identifier les appareils qui utilisent le verrou d'activation de deux manières :

-   Exécutez les **Rapports d'inventaire des appareils mobiles**. Ces rapports contiennent les colonnes **État du verrou d'activation** et **Supervisé** qui indiquent l'état des appareils. Les valeurs possibles de **Supervisé** sont **Oui** ou **non**et les valeurs possibles de **État du verrou d'activation** sont les suivantes :

    -   Activé avec code de contournement

    -   Activé sans code de contournement (appareil non supervisé)

    -   Activé sans code de contournement (appareil inaccessible)

    -   Non activé

    Le champ **État du verrou d'activation** est vide pour les appareils qui n'exécutent pas iOS 7.1 ou version ultérieure.

-   Sélectionnez un appareil dans un affichage de groupes. L'état du verrouillage d'activation est visible dans le volet d'informations de l'appareil.

    Si vous sélectionnez un appareil dans le nœud **Tous les appareils d’entreprise** et que le verrou d’activation est activé pour l’appareil, le code de contournement est également visible. Vous pouvez utiliser ce code pour émettre manuellement un contournement du verrou d'activation.

### Voir aussi
[Mettre des appareils hors service](retire-devices-from-microsoft-intune-management.md)
[Protéger vos appareils à l’aide du verrouillage à distance et de la réinitialisation du code d’accès](use-remote-lock-and-passcode-reset-in-microsoft-intune.md)


<!--HONumber=Jun16_HO1-->


