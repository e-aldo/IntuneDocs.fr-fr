---
title: Résoudre les problèmes liés aux stratégies
description: Résolvez les problèmes de configuration de stratégie.
keywords: ''
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 01/04/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 99fb6db6-21c5-46cd-980d-50f063ab8ab8
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: tscott
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 9d9fa95e7992488e8c25e713136be17bcd1580bf
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2018
---
# <a name="troubleshoot-policies-in-microsoft-intune"></a>Résoudre les problèmes de stratégie dans Microsoft Intune

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Si vous rencontrez des problèmes de déploiement et de gestion des stratégies Intune, lisez ce qui suit. Cette rubrique contient certains problèmes courants que vous pouvez rencontrer avec les solutions.

## <a name="general-issues"></a>Problèmes généraux

### <a name="was-a-deployed-policy-applied-to-the-device"></a>Une stratégie déployée a-t-elle été appliquée à l’appareil ?
**Problème :**  Vous ne savez pas si une stratégie a été correctement appliquée.

Dans la console d’administration Intune, à chaque appareil correspond un onglet Stratégie en dessous de **Propriétés de l’appareil**. Chaque stratégie contient une **Valeur prévue** et un **État**. La valeur prévue est la valeur que vous souhaitez obtenir lors de l'attribution de la stratégie. L’état est ce que vous appliquez au bout du compte quand toutes les stratégies qui s’appliquent à l’appareil, ainsi que les restrictions et les conditions requises du matériel et du système d’exploitation, sont regroupées. Les états possibles sont :

-   **Conforme**: l’appareil a reçu la stratégie et indique au service qu’il est conforme au paramètre.

-   **Non applicable**: le paramètre de stratégie n’est pas applicable. Par exemple, les paramètres de messagerie pour appareils iOS ne peuvent pas s’appliquer à un appareil Android.

-   **En attente**: la stratégie a été envoyée à l’appareil, mais son état n’a pas été communiqué au service. Tel est le cas notamment du chiffrement sur Android, qui impose à l’utilisateur de l’activer et qui, de ce fait, peut être en attente.

La capture d’écran ci-dessous illustre clairement ce point à travers deux exemples :

-   **Autoriser les mots de passe simples** est défini avec la valeur **Oui**, comme indiqué dans la colonne **Valeur prévue**, mais son **État** a la valeur **Non applicable**. Cela est dû au fait que les mots de passe simples ne sont pas pris en charge par les appareils Android.

-   De même, l’élément de stratégie développé **Paramètres de messagerie pour les appareils iOS** n’est pas appliqué à cet appareil, car il s’agit d’un appareil Android.

![Stratégie des appareils Intune](../media/Intune-Device-Policy-v.2.jpg)

> [!NOTE]
> N’oubliez pas que quand deux stratégies avec différents niveaux de restriction s’appliquent au même appareil ou utilisateur, la stratégie la plus restrictive prévaut dans la pratique.


## <a name="issues-with-enrolled-devices"></a>Problèmes liés aux appareils inscrits

### <a name="alert-saving-of-access-rules-to-exchange-has-failed"></a>Alerte : L’enregistrement de règles d’accès dans Exchange a échoué
**Problème**: vous recevez l’alerte **L’enregistrement de règles d’accès dans Exchange a échoué** dans la console d’administration.

Si vous avez créé des stratégies dans l’espace de travail Stratégie Exchange sur site de la Console d’administration, mais que vous utilisez O365, les paramètres de stratégie configurés ne sont pas appliqués par Intune. Notez la source de la stratégie indiquée dans l’alerte.  Dans l’espace de travail Stratégie Exchange sur site, supprimez les règles existantes, car ce sont des règles Exchange globales qui se trouvent dans Intune et qui concernent Exchange sur site et non O365. Créez ensuite une stratégie pour O365.

### <a name="cannot-change-security-policy-for-various-enrolled-devices"></a>Impossible de modifier la stratégie de sécurité pour différents appareils inscrits
Les appareils Windows Phone n’autorisent pas d’assouplir les stratégies de sécurité définies via GPM ou EAS a posteriori. Tel est le cas, par exemple, si vous fixez le **nombre minimal de caractères des mots de passe** à 8, puis que vous essayez de le réduire à 4. La stratégie la plus restrictive a déjà été appliquée à l’appareil.

Selon la plateforme d’appareil, si vous voulez attribuer à la stratégie une valeur moins sûre, vous devrez peut-être réinitialiser les stratégies de sécurité.
Par exemple, dans Windows, sur le Bureau, balayez à partir de la droite pour ouvrir la barre **Icônes**, puis choisissez **Paramètres** &gt; **Panneau de configuration**.  Sélectionnez l’applet **Comptes d’utilisateurs**.
Au bas du menu de navigation gauche figure le lien **Réinitialiser les stratégies de sécurité**. Choisissez-le, puis choisissez le bouton **Réinitialiser les stratégies**.
Pour pouvoir appliquer une stratégie moins restrictive, vous devrez peut-être retirer les autres appareils MDM (par exemple, Android, Windows Phone 8.1 et versions ultérieures et iOS), puis les réinscrire dans le service.

## <a name="issues-with-pcs-that-run-the-intune-software-client"></a>Problèmes liés aux ordinateurs qui exécutent le client logiciel Intune

### <a name="microsoft-intune-policy-related-errors-in-policyplatformlog"></a>Erreurs liées aux stratégies Microsoft Intune dans policyplatform.log
Pour les appareils Windows gérés avec le client logiciel Intune, les erreurs de stratégie dans le fichier policyplatform.log peuvent être dues à des paramètres définis sur des valeurs autres que les valeurs par défaut dans le Contrôle de compte d’utilisateur Windows sur l’appareil. Certains paramètres de Contrôle de compte d’utilisateur autres que les paramètres par défaut peuvent affecter les installations du client Microsoft Intune et l’exécution des stratégies.

#### <a name="to-resolve-uac-issues"></a>Pour résoudre les problèmes liés au Contrôle de compte d’utilisateur

1.  Mettez hors service l’ordinateur, comme décrit dans [Mettre hors service des appareils en cas de gestion Microsoft Intune](/intune-classic/deploy-use/retire-devices-from-microsoft-intune-management).

2.  Attendez 20 minutes que le logiciel client soit supprimé.

    > [!NOTE]
    > N’essayez pas de supprimer le client à partir de Programmes et fonctionnalités.

3.  Dans le menu Démarrer, tapez **UAC** pour ouvrir les paramètres de Contrôle de compte d’utilisateur.

4.  Déplacez le curseur de notification sur le paramètre par défaut.

### <a name="error-cannot-obtain-the-value-from-the-computer-0x80041013"></a>Erreur : Impossible d’obtenir la valeur de l’ordinateur, 0x80041013
Cela peut se produire si l’heure sur le système local présente un écart de synchronisation d’au moins cinq minutes. Si l’heure sur l’ordinateur local n’est pas synchronisée, les transactions sécurisées échouent car que les horodatages ne sont pas valides.

Pour résoudre ce problème, réglez l’heure du système local le plus proche possible de l’heure Internet ou à l’heure définie sur les contrôleurs de domaine du réseau.








### <a name="next-steps"></a>Étapes suivantes
Si ces informations de dépannage n’ont pas permis de vous aider, contactez le support Microsoft comme décrit dans [Comment obtenir un support technique pour Microsoft Intune](how-to-get-support-for-microsoft-intune.md).
