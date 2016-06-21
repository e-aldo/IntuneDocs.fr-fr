---
# required metadata

title: Résoudre les problèmes de stratégie | Microsoft Intune
description:
keywords:
author: Nbigman
manager: jeffgilb
ms.date: 05/26/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 99fb6db6-21c5-46cd-980d-50f063ab8ab8

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Résoudre les problèmes de stratégie dans Microsoft Intune

Vous trouverez ici quelques exemples de problèmes qui peuvent survenir après avoir configuré vos stratégies Microsoft Intune, ainsi que des recommandations pour les résoudre.

Si ces informations ne vous permettent pas de remédier à votre problème, consultez [Comment obtenir un support technique pour Microsoft Intune](how-to-get-support-for-microsoft-intune.md) pour accéder à d’autres types d’assistance.


## La stratégie est-elle appliquée à l’appareil ?
**Problème :** vous n’êtes pas certain qu’une stratégie est appliquée à un appareil, ou un appareil a un comportement contraire à une stratégie.

Vérifiez les informations de stratégie disponibles pour chaque appareil afin de comprendre l’effet d’une stratégie sur un appareil déterminé.

Dans la console d’administration Intune, à chaque appareil correspond un onglet Stratégie en dessous de **Propriétés de l’appareil**. Si ce n’est pas le cas, il se peut que l’inscription de l’appareil soit toujours en cours ou qu’aucune stratégie ne lui a été appliquée. Chaque stratégie contient une **Valeur prévue** et un **État**. La valeur prévue est la valeur que vous souhaitez obtenir lors de l'attribution de la stratégie. L'état est ce vous obtenez au bout du compte quand toutes les stratégies qui s'appliquent à l'appareil, ainsi que les restrictions et les conditions requises du matériel et du système d'exploitation, sont regroupées. Les états possibles sont :

-   **Conforme**: l’appareil a reçu la stratégie et indique au service qu’il est conforme au paramètre.

-   **Non applicable**: le paramètre de stratégie n’est pas applicable. Par exemple, les paramètres de messagerie pour appareils iOS ne peuvent pas s’appliquer à un appareil Android.

-   **En attente**: la stratégie a été envoyée à l’appareil, mais son état n’a pas été communiqué au service. Tel est le cas notamment du chiffrement sur Android, qui impose à l’utilisateur de l’activer et qui, de ce fait, peut être en attente.

La capture d’écran ci-dessous illustre clairement ce point à travers deux exemples :

-   **Autoriser les mots de passe simples** est défini avec la valeur **Oui**, comme indiqué dans la colonne **Valeur prévue** , mais son **État** a la valeur **Non applicable**. Cela est dû au fait que les mots de passe simples ne sont pas pris en charge par les appareils Android.

-   De même, l’élément de stratégie développé **Paramètres de messagerie pour les appareils iOS** n’est pas appliqué à cet appareil, car il s’agit d’un appareil Android.

![Stratégie des appareils Intune](../media/Intune-Device-Policy-v.2.jpg)

> [!NOTE] N’oubliez pas que quand deux stratégies avec différents niveaux de restriction s’appliquent au même appareil ou utilisateur, la stratégie la plus restrictive prévaut dans la pratique.

## Stratégie d’actualisation et intervalles de mise à jour
Sachez que les stratégies sont actualisées et mises à jour à intervalles réguliers. En général, les stratégies doivent être inscrites sur les appareils dans les 15 minutes qui suivent une modification. Voici quelques détails supplémentaires sur les intervalles réguliers d’actualisation de stratégie :

-   **Appareil Windows inscrit pour la gestion des appareils mobiles** : l’actualisation est déclenchée par une tâche planifiée à 03h00 heure locale sur l’appareil et se produit tous les jours.

-   **Windows Phone** : la stratégie est mise à jour toutes les huit heures. Vous pouvez forcer la mise à jour en effectuant une actualisation dans le portail d’entreprise, sous **Paramètres**.

-   **iOS** : la stratégie est mise à jour une fois par jour à un intervalle de temps aléatoire. Vous pouvez aussi forcer la mise à jour en ouvrant le portail d’entreprise, en sélectionnant l’appareil et en choisissant **Synchroniser**.

-   **Android** : la stratégie est mise à jour une fois par jour à un intervalle de temps aléatoire. Vous pouvez aussi forcer la mise à jour en ouvrant le portail d’entreprise, en sélectionnant l’appareil et en choisissant **Synchroniser**.

## Erreurs liées aux stratégies Microsoft Intune dans policyplatform.log
Pour les appareils Windows non soumis à la gestion des appareils mobiles, les erreurs de stratégie dans le fichier policyplatform.log peuvent être dues à des paramètres définis sur des valeurs autres que les valeurs par défaut dans le Contrôle de compte d’utilisateur Windows sur l’appareil. Certains paramètres de Contrôle de compte d’utilisateur autres que les paramètres par défaut peuvent affecter les installations du client Microsoft Intune et l’exécution des stratégies.

### Pour résoudre les problèmes liés au Contrôle de compte d’utilisateur

1.  Mettez hors service l’ordinateur, comme décrit dans [Mettre hors service des appareils en cas de gestion Microsoft Intune](/intune/deploy-use/retire-devices-from-microsoft-intune-management).

2.  Attendez 20 minutes que le logiciel client soit supprimé.

    > [!NOTE] N’essayez pas de supprimer le client à partir de Programmes et fonctionnalités.

3.  Dans le menu Démarrer, tapez **UAC** pour ouvrir les paramètres de Contrôle de compte d’utilisateur.

4.  Déplacez le curseur de notification sur le paramètre par défaut.

## Erreur 0x87D1FDE8 pour appareil KNOX
**Problème **: après avoir créé et déployé un profil de messagerie Exchange Active Sync pour Samsung KNOX pour différents appareils Android, ceux-ci font état de l’erreur **0x87D1FDE8** ou d’un **échec de la correction** dans l’onglet stratégie des propriétés de l’appareil &gt; .

Examinez la configuration de votre profil EAS pour Samsung KNOX et la stratégie source. L’option de synchronisation Samsung Notes n’étant plus prise en charge, nous vous invitons à ne pas la sélectionner dans votre profil. Assurez-vous que les appareils ont eu suffisamment de temps pour traiter la stratégie (jusqu’à 24 heures).

## Alerte : L’enregistrement de règles d’accès dans Exchange a échoué
**Problème**: vous recevez l’alerte **L’enregistrement de règles d’accès dans Exchange a échoué**  dans la console d’administration.

Si vous avez créé des stratégies dans l’espace de travail Stratégie Exchange sur site de la Console d’administration, mais que vous utilisez O365, les paramètres de stratégie configurés ne sont pas appliqués par Intune. Notez la source de la stratégie indiquée dans l’alerte.  Dans l’espace de travail Stratégie Exchange sur site, supprimez les règles existantes, car ce sont des règles Exchange globales qui se trouvent dans Intune et qui concernent Exchange sur site et non O365. Créez ensuite une stratégie pour O365.

## Erreur : Impossible d’obtenir la valeur de l’ordinateur, 0x80041013
Cela peut se produire si l’heure sur le système local présente une écart de synchronisation d’au moins cinq minutes. Si l’heure sur l’ordinateur local n’est pas synchronisée, les transactions sécurisées échouent car que les horodatages ne sont pas valides.

Pour résoudre ce problème, réglez l’heure du système local le plus proche possible de l’heure Internet ou à l’heure définie sur les contrôleurs de domaine du réseau.

## Impossible de modifier la stratégie de sécurité pour différents appareils GPM
Les appareils Windows Phone et Windows RT n’autorisent pas d’assouplir les stratégies de sécurité définies via GPM ou EAS a posteriori. Tel est le cas, par exemple, si vous fixez le **nombre minimal de caractères des mots de passe** à 8, puis que vous essayez de le réduire à 4. La stratégie la plus restrictive a déjà été appliquée à l’appareil.

Selon la plateforme d’appareil, si vous voulez attribuer à la stratégie une valeur moins sûre, vous devrez peut-être réinitialiser les stratégies de sécurité.
Par exemple, dans Windows RT, sur le bureau, balayez à partir de la droite pour ouvrir la barre **Icônes**, puis choisissez **Paramètres** &gt; **Panneau de configuration**.  Sélectionnez l’applet **Comptes d’utilisateurs** .
Au bas du menu de navigation gauche figure le lien **Réinitialiser les stratégies de sécurité** . Choisissez-le, puis choisissez le bouton **Réinitialiser les stratégies** .
Pour pouvoir appliquer une stratégie moins restrictive, vous devrez peut-être retirer les autres appareils GPM (par exemple, Android, Windows Phone 8.1 et versions ultérieures et iOS), puis les réinscrire dans le service.

## Les appareils Android n’imposent pas les changements de stratégie de sécurité sans l’approbation de l’utilisateur final
La fonctionnalité GPM Android n’autorise pas le service à imposer des modifications à la stratégie initiale sur les appareils comme l’y autorisent d’autres plateformes. Cela est dû à une fonctionnalité Android et n’a pas de lien avec le service Intune. Les appareils Android affichent une invite à l’utilisateur final via la fenêtre qui notifie la modification de stratégie correspondante (par exemple, Mot de passe, Chiffrement, etc.).  L’utilisateur final doit répondre à l’invite et dès lors qu’il a accepté la stratégie, elle doit s’appliquer.

## Impossible de créer une stratégie ou d’inscrire des clients si le nom de l’entreprise contient des caractères spéciaux
**Problème :** vous ne pouvez pas créer des stratégies, ni inscrire des clients.

**Résolution :** dans le [Centre d’administration Office 365](https://portal.office.com/), supprimez les caractères spéciaux du nom de l’entreprise et enregistrez les informations de l’entreprise.

### Étapes suivantes
Si ces informations de dépannage n’ont pas permis de vous aider, contactez le support Microsoft comme décrit dans [Comment obtenir un support technique pour Microsoft Intune](how-to-get-support-for-microsoft-intune.md).


<!--HONumber=Jun16_HO1-->


