---
title: "Gérer des paramètres d’appareils avec des stratégies"
description: "Utilisez Intune pour créer et déployer des stratégies qui contrôlent les paramètres et fonctionnalités sur les appareils inscrits que vous gérez."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 11/02/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 09bae0b9-4f79-4658-8ca1-a71ab992c1b2
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 362c7f4dc9acfe574eb6a98819339e2db44cb9ec
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/10/2017
---
# <a name="manage-settings-and-features-on-your-devices-with-microsoft-intune-policies"></a>Gérer des paramètres et des fonctionnalités sur vos appareils avec des stratégies Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Les *stratégies* Microsoft Intune sont des groupes de paramètres qui contrôlent les fonctionnalités des appareils mobiles et des ordinateurs. Vous créez des stratégies en utilisant des modèles qui contiennent des paramètres recommandés ou personnalisés, puis vous les déployez sur l'appareil ou des groupes d’utilisateurs.

## <a name="types-of-policies"></a>Types de stratégie

Les stratégies Intune appartiennent aux catégories suivantes : La catégorie que vous utilisez affecte la façon de créer et de déployer la stratégie.


- **Stratégies de configuration** : celles-ci sont couramment utilisées pour gérer les paramètres de sécurité et les fonctionnalités sur vos appareils. Utilisez les informations de cette rubrique pour en savoir plus sur la façon de créer et déployer ces stratégies et pour explorer les paramètres disponibles.
- **Stratégies de conformité des appareils** : celles-ci définissent les règles et les paramètres qu’un appareil doit respecter pour être considéré comme conforme par les stratégies d’accès conditionnel. Vous pouvez également utiliser des stratégies de conformité pour surveiller et corriger les problèmes de conformité des appareils indépendamment de l’accès conditionnel.
Pour plus d’informations, consultez [Stratégies de conformité d’appareils dans Microsoft Intune](introduction-to-device-compliance-policies-in-microsoft-intune.md).
- **Stratégies d’accès conditionnel** : celles-ci vous aident à sécuriser la messagerie et d’autres services en fonction de conditions que vous spécifiez.
Pour plus d’informations, consultez [Limiter l’accès à la messagerie et aux services Office 365 avec Microsoft Intune](restrict-access-to-email-and-o365-services-with-microsoft-intune.md).
- [Stratégies d’inscription des appareils d’entreprise](set-up-ios-and-mac-management-with-microsoft-intune.md) : pour plus d’informations sur les stratégies d’inscription des appareils d’entreprise, consultez **Configurer la gestion iOS et Mac avec Microsoft Intune**.
- **Stratégies d’accès aux ressources** : celles-ci œuvrent ensemble pour aider vos utilisateurs à accéder aux fichiers et aux ressources dont ils ont besoin pour effectuer leur travail, où qu’ils soient.
Pour plus d’informations, consultez [Activer l’accès aux ressources de l’entreprise avec Microsoft Intune](enable-access-to-company-resources-with-microsoft-intune.md).


Pour obtenir la liste complète des stratégies Intune, consultez le [Guide de référence des stratégies Microsoft Intune](microsoft-intune-policy-reference.md).

## <a name="create-a-configuration-policy"></a>Créer une stratégie de configuration

1.  Dans la [console d’administration Microsoft Intune](https://manage.microsoft.com/), sélectionnez **Stratégie** &gt; **Stratégies de configuration** &gt; **Ajouter**.

2.  Sélectionnez une stratégie, choisissez d’utiliser les paramètres recommandés associés (le cas échéant, mais vous pouvez les modifier plus tard) ou de créer une stratégie personnalisée avec vos propres paramètres.

    > [!TIP]
    > Pour choisir la bonne stratégie, consultez le [guide de référence des stratégies Microsoft Intune](microsoft-intune-policy-reference.md).

3.  Quand vous êtes prêt, sélectionnez **Créer une stratégie**.

4.  Sur la page **Créer une stratégie** , configurez un nom et une description facultative de la stratégie.

5.  Configurez les paramètres de stratégie nécessaires, puis sélectionnez **Enregistrer la stratégie**.

    Si vous avez besoin d’aide avec les paramètres de stratégie, choisissez votre type de stratégie à partir de la liste suivante :

    - [Paramètres pour les appareils iOS](ios-policy-settings-in-microsoft-intune.md)
    - [Paramètres pour les appareils Android](android-policy-settings-in-microsoft-intune.md)
    - [Paramètres pour les appareils Android for Work](android-for-work-policy-settings-in-microsoft-intune.md)
    - [Paramètres pour les appareils Windows 8 et Windows 8.1](windows-configuration-policy-settings-in-microsoft-intune.md)
    - [Paramètres pour les appareils Windows Phone 8.1](windows-phone-8-1-policy-settings-in-microsoft-intune.md)
    - [Paramètres pour les ordinateurs et les appareils mobiles Windows 10](windows-10-policy-settings-in-microsoft-intune.md)
    - [Paramètres pour les appareils Windows Collaboration](windows-team-configuration-policy-settings-in-microsoft-intune.md)
    - [Paramètres pour la mise à niveau de la version de Windows](edition-upgrade-policy-settings-in-microsoft-intune.md)
    - [Paramètres pour les appareils Mac OS X](mac-os-x-policy-settings-in-microsoft-intune.md)
    - [Paramètres pour Exchange ActiveSync](exchange-activesync-policy-settings-in-microsoft-intune.md)
    - [Paramètres pour la stratégie de conditions générales](terms-and-condition-policy-settings-in-microsoft-intune.md)
    - [Paramètres généraux pour les appareils mobiles (hérités)](mobile-device-security-policy-settings-in-microsoft-intune.md)

4.  Dans la boîte de dialogue de confirmation, sélectionnez **Oui** pour déployer la stratégie ou sur **Non** pour créer la stratégie sans la déployer.

Vous pouvez afficher et modifier la nouvelle stratégie en parcourant les sections de chaque type de stratégie dans l’espace de travail **Stratégie** .

Lorsque vous créez une stratégie qui utilise les paramètres recommandés, le nom de la nouvelle stratégie est une combinaison du nom du modèle, de la date et de l'heure. Lorsque vous modifiez la stratégie, le nom est mis à jour avec l’heure et la date de la modification.

Maintenant que vous avez créé une stratégie, vous pouvez la déployer sur un ou plusieurs groupes d’utilisateurs ou appareils.

> [!TIP]
> Vous ne pouvez pas déployer tous les types de stratégie. Par exemple, la stratégie de gestion des applications mobiles n’est pas déployée. Ce type de stratégie est plutôt associé à une application, que vous déployez ensuite.

## <a name="deploy-a-configuration-policy"></a>Déployer une stratégie de configuration

1.  Dans l’espace de travail **Stratégie**, sélectionnez la stratégie à déployer, puis choisissez **Gérer le déploiement**.

2.  Dans la boîte de dialogue **Gérer le déploiement** :

    -   Pour déployer la stratégie : sélectionnez un ou plusieurs groupes sur lesquels déployer la stratégie, puis choisissez **Ajouter** &gt; **OK**.

    -   Pour fermer la boîte de dialogue sans déployer la stratégie, choisissez **Annuler**.

Quand vous sélectionnez une stratégie déployée, vous pouvez afficher d’autres informations sur le déploiement dans la partie inférieure de la liste de stratégies.

## <a name="manage-policies"></a>Gérer les stratégies

1.  Dans la [console d’administration Microsoft Intune](https://manage.microsoft.com/), sélectionnez **Stratégie**, puis recherchez et sélectionnez la stratégie que vous voulez gérer.

2.  Sélectionnez une des opérations suivantes :

- **Modifier** : ouvre les propriétés de la stratégie sélectionnée afin que vous puissiez y apporter des modifications.
- **Supprimer** : supprime la stratégie sélectionnée.<br>Lorsque vous supprimez une stratégie, elle est supprimée de tous les groupes sur lesquels elle a été déployée.
- **Gérer le déploiement** : sélectionnez le groupe sur lequel vous voulez déployer la stratégie, puis sélectionnez **Ajouter**.


## <a name="frequently-asked-questions-about-intune-policies"></a>Forum aux questions sur les stratégies Intune

### <a name="how-long-does-it-take-for-mobile-devices-to-get-a-policy-or-apps-after-they-have-been-deployed"></a>Combien de temps faut-il pour que les appareils mobiles obtiennent une stratégie ou les applications une fois que celles-ci ont été déployées ?
Quand une stratégie ou une application est déployée, Intune essaie d’envoyer immédiatement une notification à l’appareil pour qu’il s’enregistre auprès du service Intune. Cette opération prend généralement moins de 5 minutes.

Si un appareil ne se manifeste pas pour obtenir la stratégie après l’envoi de la première notification, Intune effectue trois autres tentatives.  Si l’appareil est hors connexion (par exemple, s’il est éteint ou n’est pas connecté à un réseau), il ne peut pas recevoir de notifications. Dans ce cas, l’appareil obtiendra la stratégie lors de son prochain enregistrement planifié auprès du service Intune, de la manière suivante :

- iOS et Mac OS X : toutes les 6 heures.
- Android  : toutes les 8 heures.
- Windows Phone : toutes les 8 heures.
- PC Windows 8.1 et Windows 10 inscrits en tant qu’appareils : toutes les 8 heures.

Si l’appareil vient d’être inscrit, la fréquence d’enregistrement est plus fréquente :

- iOS et Mac OS X : toutes les 15 minutes pendant 6 heures, puis toutes les 6 heures.
- Android : toutes les 3 minutes pendant 15 minutes, puis toutes les 15 minutes pendant 2 heures, puis toutes les 8 heures.
- Windows Phone : toutes les 5 minutes pendant 15 minutes, puis toutes les 15 minutes pendant 2 heures, puis toutes les 8 heures.
- PC Windows inscrits en tant qu’appareils : toutes les 3 minutes pendant 30 minutes, puis toutes les 8 heures.

Les utilisateurs peuvent également ouvrir l’application Portail d’entreprise et synchroniser l’appareil pour qu’il recherche immédiatement les stratégies à tout moment.

### <a name="what-actions-cause-intune-to-immediately-send-a-notification-to-a-device"></a>Quelles sont les actions qui déclenchent l’envoi immédiat d’une notification par Intune ?
Les appareils s’enregistrent auprès d’Intune quand ils reçoivent une notification leur demandant de s’enregistrer ou lors de leur enregistrement régulièrement planifié.  Quand vous ciblez un appareil ou un utilisateur spécifiquement avec une action de type réinitialisation, verrouillage, réinitialisation de code secret, déploiement d’application, déploiement de profil (Wi-Fi, VPN, messagerie, etc.) ou déploiement de stratégie, Intune essaie immédiatement d’indiquer à l’appareil qu’il doit s’enregistrer auprès du service Intune pour recevoir ces mises à jour.

D’autres modifications, comme la modification des coordonnées dans le portail d’entreprise, ne déclenchent pas l’envoi immédiat d’une notification aux appareils.

### <a name="if-multiple-policies-are-deployed-to-the-same-user-or-device-how-do-i-know-which-settings-will-get-applied"></a>Si plusieurs stratégies sont déployées sur le même utilisateur ou appareil, quels sont les paramètres appliqués ?
Quand plusieurs stratégies sont déployées sur le même utilisateur ou appareil, l’évaluation du paramètre à appliquer est effectuée au niveau de chaque paramètre :

-   Les paramètres de stratégie de conformité ont toujours la priorité sur les paramètres de stratégie de configuration.

-   En présence de deux stratégies de conformité, c’est le paramètre de la stratégie de conformité la plus restrictive qui est appliqué.

-   Si un paramètre de stratégie de configuration entre en conflit avec un paramètre dans une autre stratégie de configuration, ce conflit apparaît dans la console Intune. Vous devez corriger ces conflits manuellement.

### <a name="what-happens-when-mobile-application-management-policies-conflict-with-each-other-which-one-will-be-applied-to-the-app"></a>Que se passe-t-il quand des stratégies de gestion des applications mobiles entrent en conflit ? Laquelle est appliquée à l’application ?
Les valeurs en conflit sont les paramètres les plus restrictifs disponibles dans une stratégie de gestion des applications mobiles, à l’exception des champs d’entrée numérique (comme le nombre de tentatives autorisées avant la réinitialisation du code confidentiel).  Les champs d’entrée numérique sont définis sur les mêmes valeurs que quand vous créez une stratégie de gestion des applications mobiles dans la console en choisissant les paramètres recommandés.

Des conflits se produisent quand deux paramètres de stratégie sont identiques.  Par exemple, vous avez configuré deux stratégies MAM identiques, à l’exception du paramètre de copier/coller.  Dans ce scénario, le paramètre de copier/coller est défini sur la valeur la plus restrictive, mais le reste des paramètres est appliqué selon leur configuration.

Si une stratégie est déployée sur l’application et active, puis qu’une deuxième stratégie est déployée, la première est prioritaire et reste appliquée, tandis que la deuxième s’affiche comme étant en conflit. Si elles sont appliquées en même temps, ce qui signifie qu’il n’existe aucune stratégie précédente, elles sont alors en conflit. Tous les paramètres en conflit sont définis sur les valeurs les plus limitées.

### <a name="what-happens-when-ios-custom-policies-conflict"></a>Que se passe-t-il quand les stratégies personnalisées iOS entrent en conflit ?
Intune n’évalue pas la charge utile des fichiers de configuration Apple ni la stratégie OMA-URI personnalisée. Son rôle se limite simplement au mécanisme de livraison.

Lorsque vous déployez une stratégie personnalisée, vérifiez que les paramètres configurés ne sont pas en conflit avec les stratégies de conformité, de configuration ou d’autres stratégies personnalisées. Dans le cas d’une stratégie personnalisée avec des paramètres en conflit, l’ordre dans lequel les paramètres sont appliqués est aléatoire.

### <a name="what-happens-when-a-policy-is-deleted-or-no-longer-applicable"></a>Que se passe-t-il quand une stratégie est supprimée ou qu’elle n’est plus applicable ?
Quand vous supprimez une stratégie ou retirez un appareil d’un groupe sur lequel une stratégie a été déployée, la stratégie et les paramètres sont supprimés de cet appareil conformément aux listes suivantes.

#### <a name="enrolled-devices"></a>Appareils inscrits

- Profils Wi-Fi, VPN, de certificat et de messagerie : ces profils sont supprimés de tous les appareils inscrits et pris en charge.
- Tous les autres types de stratégie :
    - **Appareils Windows et Android** : les paramètres ne sont pas supprimés de l’appareil.
    - **Appareils Windows Phone 8.1** : les paramètres suivants sont supprimés :
        - Exiger un mot de passe pour déverrouiller des appareils mobiles
        - Autoriser les mots de passe simples
        - Longueur minimale du mot de passe
        - Type de mot de passe requis
        - Expiration du mot de passe (jours)
        - Mémoriser l'historique des mots de passe
        - Nombre d'échecs de connexion répétée autorisé avant réinitialisation de l'appareil
        - Minutes d'inactivité avant demande du mot de passe
        - Type de mot de passe requis - Nombre minimum de jeux de caractères
        - Autoriser l'appareil photo
        - Exiger le chiffrement sur l'appareil mobile
        - Autoriser le stockage amovible
        - Autoriser le navigateur web
        - Autoriser la boutique d'applications
        - Autoriser la capture d'écran
        - Autoriser la géolocalisation
        - Autoriser le compte Microsoft
        - Autoriser la fonction copier-coller
        - Autoriser la connexion Wi-Fi
        - Autoriser la connexion automatique aux points d'accès Wi-Fi gratuits
        - Autoriser l'indication des points d'accès Wi-Fi
        - Autoriser la réinitialisation aux paramètres d'usine
        - Autoriser Bluetooth
        - Autoriser NFC
        - Autoriser le Wi-Fi

    - **iOS** : tous les paramètres sont supprimés, sauf :
        - Autoriser l'itinérance vocale
        - Autoriser l'itinérance des données
        - Autoriser la synchronisation automatique lors de l'itinérance

#### <a name="windows-pcs-running-the-intune-client-software"></a>PC Windows exécutant le logiciel client Intune

- **Paramètres Endpoint Protection** : les paramètres sont restaurés sur leurs valeurs recommandées. La seule exception est le paramètre **Rejoindre Microsoft Active Protection Service** pour lequel la valeur par défaut est **Non**. Pour plus d’informations, consultez [Contribuer à la sécurisation des PC Windows avec Endpoint Protection pour Microsoft Intune](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md).
- **Paramètres de mises à jour logicielles** : les paramètres sont réinitialisés à l’état par défaut du système d’exploitation. Pour plus d’informations, consultez [Maintenir des PC Windows à jour avec les mises à jour logicielles dans Microsoft Intune](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md).
- **Paramètres de Microsoft Intune Center** : les informations de contact du support qui ont été configurées par la stratégie sont supprimées des ordinateurs.
- **Paramètres du Pare-feu Windows** : les paramètres sont réinitialisés sur les valeurs par défaut du système d’exploitation. Pour plus d’informations, consultez [Contribuer à la sécurisation des PC Windows avec Endpoint Protection pour Microsoft Intune](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md).


### <a name="how-can-i-refresh-the-policies-on-a-device-to-ensure-that-they-are-current-applies-to-windows-pcs-running-the-intune-client-software-only"></a>Comment actualiser les stratégies sur un appareil pour vérifier qu’elles sont à jour (s’applique aux ordinateurs Windows exécutant le logiciel client Intune uniquement) ?

1.  Dans un groupe d’appareils, sélectionnez les appareils sur lesquels vous voulez actualiser les stratégies, puis sélectionnez **Tâches à distance** &gt; **Actualiser les stratégies**.
2.  Sélectionnez **Tâches à distance** dans le coin inférieur droit de la console d’administration Intune pour vérifier l’état de la tâche.

### <a name="where-can-i-find-help-troubleshooting-policies"></a>Où puis-je trouver de l’aide concernant mes problèmes de stratégies ?

Consultez [Résoudre les problèmes de stratégie dans Microsoft Intune](/intune-classic/troubleshoot/troubleshoot-policies-in-microsoft-intune).
