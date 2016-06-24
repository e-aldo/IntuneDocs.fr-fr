---
# required metadata

title: Gérer des paramètres et des fonctionnalités sur vos appareils avec des stratégies | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 06/14/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 09bae0b9-4f79-4658-8ca1-a71ab992c1b2

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: heenamac
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Gérer des paramètres et des fonctionnalités sur vos appareils avec des stratégies Microsoft Intune
Les **stratégies Intune** sont des groupes de paramètres qui contrôlent les fonctionnalités des appareils mobiles et des ordinateurs. Vous créez des stratégies à l'aide de modèles qui contiennent des paramètres recommandés ou personnalisés, puis vous les déployez sur l'appareil ou des groupes d'utilisateurs.

## Quels types de stratégies peuvent être utilisés ?

Les stratégies Intune appartiennent aux catégories suivantes : La catégorie que vous utilisez affecte la façon de créer et déployer la stratégie.


- **Stratégies de configuration :** Ces stratégies sont couramment utilisées pour gérer les paramètres de sécurité et les fonctionnalités sur vos appareils. Utilisez les informations de cette rubrique pour en savoir plus sur la façon de créer et déployer ces stratégies et pour explorer les paramètres disponibles.
- **Stratégies de conformité des appareils :** Ces stratégies de conformité définissent les règles et les paramètres auxquels un appareil doit se conformer pour être considéré comme conforme par les stratégies d’accès conditionnel. Vous pouvez également utiliser des stratégies de conformité pour surveiller et corriger les problèmes de conformité des appareils indépendamment de l’accès conditionnel.
Pour plus d’informations, consultez [Stratégies de conformité d’appareils dans Microsoft Intune](introduction-to-device-compliance-policies-in-microsoft-intune.md).
- **Stratégies d’accès conditionnel :** Ces stratégies vous aident à sécuriser la messagerie et d’autres services en fonction de conditions que vous spécifiez.
Pour plus d’informations, consultez [Limiter l’accès à la messagerie et aux services Office 365 avec Microsoft Intune](restrict-access-to-email-and-o365-services-with-microsoft-intune.md).
- [Stratégies d’inscription des appareils d’entreprise :](set-up-ios-and-mac-management-with-microsoft-intune.md) Pour plus d’informations sur les stratégies d’inscription des appareils d’entreprise, consultez **Configurer la gestion iOS et Mac avec Microsoft Intune**.
- **Stratégies d’accès aux ressources :** Les stratégies de ce groupe œuvrent ensemble pour aider vos utilisateurs à accéder aux fichiers et aux ressources dont ils ont besoin pour effectuer leur travail, où qu’ils soient.
Pour plus d’informations, consultez [Activer l’accès aux ressources de l’entreprise avec Microsoft Intune](enable-access-to-company-resources-with-microsoft-intune.md).


Pour obtenir la liste complète des stratégies Intune, consultez le [Guide de référence des stratégies Microsoft Intune](microsoft-intune-policy-reference.md).




## Créer une stratégie de configuration

1.  Dans la [console d’administration Microsoft Intune](https://manage.microsoft.com/), sélectionnez **Stratégie** &gt; **Stratégies de configuration** &gt; **Ajouter**.

2.  Sélectionnez la stratégie souhaitée, choisissez d’utiliser les paramètres recommandés pour la stratégie (le cas échéant, mais vous pouvez les modifier plus tard) ou de créer une stratégie personnalisée avec vos propres paramètres.

    > [!TIP] Pour choisir la bonne stratégie, consultez le [Guide de référence des stratégies Microsoft Intune](microsoft-intune-policy-reference.md).

3.  Quand vous êtes prêt, sélectionnez **Créer une stratégie**.

4.  Dans l’écran **Créer une stratégie** , configurez un nom et une description facultative de la stratégie.

5.  Configurez les paramètres de stratégie nécessaires, puis sélectionnez **Enregistrer la stratégie**.

    Si vous avez besoin d’aide avec les paramètres de stratégie, choisissez votre type de stratégie à partir de la liste suivante :

    - [Paramètres pour les appareils iOS](ios-policy-settings-in-microsoft-intune.md)
    - [Paramètres pour les appareils Android](android-policy-settings-in-microsoft-intune.md)
    - [Paramètres pour les appareils Windows 8 et Windows 8.1](windows-configuration-policy-settings-in-microsoft-intune.md)
    - [Paramètres pour les appareils Windows Phone 8.1](windows-phone-8-1-policy-settings-in-microsoft-intune.md)
    - [Paramètres pour les appareils de bureau et mobiles Windows 10](windows-10-policy-settings-in-microsoft-intune.md)
    - [Paramètres pour les appareils Windows Collaboration](windows-team-configuration-policy-settings-in-microsoft-intune.md)
    - [Paramètres pour la mise à niveau de la version de Windows](edition-upgrade-policy-settings-in-microsoft-intune.md)
    - [Paramètres pour les appareils Mac OS X](mac-os-x-policy-settings-in-microsoft-intune.md)
    - [Paramètres pour Exchange ActiveSync](exchange-activesync-policy-settings-in-microsoft-intune.md)
    - [Paramètres pour la stratégie de conditions générales](terms-and-condition-policy-settings-in-microsoft-intune.md)
    - [Paramètres généraux pour les appareils mobiles (hérité)](mobile-device-security-policy-settings-in-microsoft-intune.md)

4.  Dans la boîte de dialogue de confirmation, sélectionnez **Oui** pour déployer la stratégie ou sur **Non** pour créer la stratégie sans la déployer.

Vous pouvez afficher et modifier la nouvelle stratégie en parcourant les sections de chaque type de stratégie dans l’espace de travail **Stratégie** .

Lorsque vous créez une stratégie qui utilise les paramètres recommandés, le nom de la nouvelle stratégie est une combinaison du nom du modèle, de la date et de l'heure. Lorsque vous modifiez la stratégie, le nom est mis à jour avec l'heure et la date de la modification.

Maintenant que vous avez créé une stratégie, vous voulez probablement la déployer sur un ou plusieurs groupes d’utilisateurs ou appareils.

> [!TIP]
> Vous ne pouvez pas déployer tous les types de stratégie. Par exemple, la stratégie de gestion des applications mobiles n’est pas déployée. Ce type de stratégie est plutôt associé à une application, que vous déployez ensuite.

## Déployer une stratégie de configuration

1.  Dans l’espace de travail **Stratégie**, sélectionnez la stratégie à déployer, puis choisissez **Gérer le déploiement**.

2.  Dans la boîte de dialogue **Gérer le déploiement** :

    -   **Pour déployer la stratégie** : sélectionnez un ou plusieurs groupes sur lesquels déployer la stratégie, puis choisissez **Ajouter** &gt; **OK**.

    -   **Pour fermer la boîte de dialogue sans la déployer**, choisissez **Annuler**.

Quand vous sélectionnez une stratégie déployée, vous pouvez afficher d’autres informations sur le déploiement dans la partie inférieure de la liste de stratégies.

## Gérer les stratégies

1.  Dans la [console d’administration Microsoft Intune](https://manage.microsoft.com/), sélectionnez **Stratégie**, puis recherchez et sélectionnez la stratégie que vous voulez gérer.

2.  Sélectionnez une des opérations suivantes :

- **Modifier** - Ouvre les propriétés de la stratégie sélectionnée pour vous permettre d’apporter des modifications.
- **Supprimer** - Supprime la stratégie sélectionnée.<br>Lorsque vous supprimez une stratégie, elle est supprimée de tous les groupes sur lesquels elle a été déployée.
- **Gérer le déploiement** : sélectionnez le groupe sur lequel vous voulez déployer la stratégie, puis sélectionnez **Ajouter**.


## Forum aux questions sur les stratégies Intune

### Combien de temps faut-il pour que les appareils mobiles obtiennent la stratégie ou les applications une fois qu’elles ont été déployées ?
Quand une stratégie ou une application est déployée, Intune essaie d’envoyer immédiatement une notification à l’appareil pour qu’il s’enregistre auprès du service Intune. Cette opération prend généralement moins de cinq minutes.

Si un appareil ne se manifeste pas pour obtenir la stratégie après l’envoi de la première notification, 3 autres tentatives sont effectuées.  Si l’appareil est hors connexion (par exemple, s’il est éteint ou n’est pas connecté à un réseau), il ne peut pas recevoir de notifications.

Dans ce cas, l’appareil obtiendra la stratégie lors de son prochain enregistrement planifié auprès du service Intune, de la manière suivante :

- iOS - Toutes les 6 heures
- Android - Toutes les 8 heures
- Windows Phone - Toutes les 8 heures
- Appareils Windows RT inscrits – Toutes les 24 heures
- PC Windows 8.1 et Windows 10 inscrits en tant qu’appareils – Toutes les 8 heures

Si l’appareil vient d’être inscrit, la fréquence d’enregistrement est plus fréquente :

- iOS - Toutes les 15 minutes pendant 6 heures, puis toutes les 6 heures
- Android - Toutes les 3 minutes pendant 15 minutes, puis toutes les 15 minutes pendant 2 heures, puis toutes les 8 heures
- Windows Phone - Toutes les 5 minutes pendant 15 minutes, puis toutes les 15 minutes pendant 2 heures, puis toutes les 8 heures
- PC Windows inscrits en tant qu’appareils - Toutes les 3 minutes pendant 30 minutes, puis toutes les 24 heures

Les utilisateurs peuvent également lancer l’application Portail d’entreprise et synchroniser l’appareil pour qu’il recherche immédiatement les stratégies à tout moment.

### Quelles sont les actions qui déclenchent l’envoi immédiat d’une notification par Intune ?
Les appareils s’enregistrent auprès d’Intune quand ils reçoivent une notification leur demandant de s’enregistrer ou lors de leur enregistrement régulièrement planifié, comme indiqué dans les tableaux ci-dessus.  Quand vous ciblez un appareil ou un utilisateur spécifiquement avec une action de type réinitialisation, verrouillage, réinitialisation de code secret, déploiement d’application, déploiement de profil (Wi-Fi, VPN, messagerie, etc.) ou déploiement de stratégie, Intune essaie immédiatement d’indiquer à l’appareil qu’il doit s’enregistrer auprès du service Intune pour recevoir ces mises à jour.

D’autres modifications, comme la modification des coordonnées dans le portail d’entreprise, ne déclenchent pas l’envoi immédiat d’une notification aux appareils.

> [!TIP]
> Quand une stratégie contenant des paramètres est déployée sur un appareil Android, l’utilisateur est invité à effectuer une action pour se conformer à la stratégie. Tant que l’utilisateur n’aura pas effectué cette action ou que l’appareil n’aura pas été redémarré, les nouveaux paramètres de stratégie ne prendront pas effet.

### Si plusieurs stratégies sont déployées sur le même utilisateur ou appareil, quels sont les paramètres appliqués ?
Quand plus de deux stratégies sont déployées sur le même utilisateur ou appareil, l’évaluation du paramètre à appliquer est effectuée au niveau de chaque paramètre.

-   Les paramètres de stratégie de conformité ont toujours priorité sur les paramètres de stratégie de configuration

-   En présence de deux stratégies de conformité, c’est le paramètre de la stratégie de conformité la plus restrictive qui est appliqué

-   En présence de deux stratégies de configuration, c’est le paramètre de la stratégie de configuration la plus restrictive qui est appliqué

### Que se passe-t-il quand des stratégies de gestion des applications mobiles (MAM) entrent en conflit ? Laquelle est appliquée à l’application ?
Les valeurs en conflit sont les paramètres les plus restrictifs disponibles dans une stratégie de gestion des applications mobiles, à l’exception des champs d’entrée numérique (comme le nombre de tentatives autorisées avant la réinitialisation du code confidentiel).  Les champs d’entrée numérique sont définis sur les mêmes valeurs que quand vous créez une stratégie MAM dans la console en choisissant les paramètres recommandés.

Des conflits se produisent quand deux paramètres de stratégie sont identiques.  Par exemple, vous avez configuré deux stratégies MAM identiques, à l’exception du paramètre de copier/coller.  Dans ce scénario, le paramètre de copier/coller est défini sur la valeur la plus restrictive, mais le reste des paramètres est appliqué selon leur configuration.

Si une stratégie est déployée sur l’application et active, puis qu’une deuxième stratégie est déployée, la première est prioritaire et reste appliquée, tandis que la deuxième s’affiche comme étant en conflit. Toutefois, si elles sont appliquées en même temps, ce qui signifie qu’aucune des deux stratégies n’est prioritaire, elles sont toutes deux en conflit et tous les paramètres conflictuels sont définis sur les valeurs les plus restrictives.

### Que se passe-t-il quand les stratégies personnalisées iOS entrent en conflit ?
Intune n’évalue pas la charge utile des fichiers de configuration Apple ou de la stratégie OMA-URI personnalisée, son rôle se limite simplement au mécanisme de livraison.

Par conséquent, quand vous déployez une stratégie personnalisée, vérifiez que les paramètres configurés ne sont pas en conflit avec les stratégies de conformité, de configuration ou d’autres stratégies personnalisées. Dans le cas d’une stratégie personnalisée avec des paramètres en conflit, l’ordre dans lequel les paramètres sont appliqués est aléatoire.

### Que se passe-t-il quand une stratégie est supprimée ou qu’elle n’est plus applicable ?
Quand vous supprimez une stratégie ou retirez un appareil d'un groupe sur lequel une stratégie a été déployée, la stratégie et les paramètres sont supprimés de cet appareil conformément aux tableaux suivants :

#### Appareils inscrits

- Profils Wi-Fi, VPN, de certificat et de messagerie - Ces profils sont supprimés de tous les appareils inscrits et pris en charge.
- Tous les autres types de stratégie
    - **Appareils Windows et Android** - Les paramètres ne sont pas supprimés de l’appareil.
    - **Appareils Windows Phone 8.1** - Les paramètres suivants sont supprimés :
        - Exiger un mot de passe pour déverrouiller des appareils mobiles
        - Autoriser les mots de passe simples
        - Longueur minimale du mot de passe
        - Type de mot de passe requis
        - Expiration du mot de passe (jours)
        - Mémoriser l'historique des mots de passe
        - Nombre d'échecs de connexion successifs autorisé avant réinitialisation de l'appareil – Minutes d’inactivité avant demande du mot de passe – Type de mot de passe requis – Nombre minimum de jeux de caractères – Autoriser l’appareil photo – Exiger le chiffrement sur l’appareil mobile – Autoriser le stockage amovible – Autoriser le navigateur web – Autoriser la boutique d’applications – Autoriser la capture d’écran – Autoriser la géolocalisation – Autoriser un compte Microsoft – Autoriser la fonction copier-coller – Autoriser la connexion Wi-Fi – Autoriser la connexion automatique aux points d’accès Wi-Fi gratuits – Autoriser l’indication des points d’accès Wi-Fi – Autoriser la réinitialisation aux paramètres d’usine – Autoriser Bluetooth – Autoriser NFC – Autoriser le Wi-Fi
    
    - **iOS** - Tous les paramètres sont supprimés, sauf :
        - Autoriser l'itinérance vocale
        - Autoriser l'itinérance des données
        - Autoriser la synchronisation automatique lors de l'itinérance

#### PC Windows exécutant le logiciel client Intune

- **Paramètres Endpoint Protection** - Les paramètres sont restaurés sur leurs valeurs recommandées. La seule exception est le paramètre **Rejoindre Microsoft Active Protection Service** pour lequel la valeur par défaut est **Non**. Pour plus d’informations, consultez [Contribuer à la sécurisation des PC Windows avec Endpoint Protection pour Microsoft Intune](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md).
- **Paramètres de mises à jour logicielles** - Les paramètres sont réinitialisés à l’état par défaut du système d’exploitation. Pour plus d’informations, consultez [Maintenir des PC Windows à jour avec les mises à jour logicielles dans Microsoft Intune](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md).
- **Paramètres de Microsoft Intune Center** : les informations de contact du support qui ont été configurées par la stratégie sont supprimées des ordinateurs.
- **Paramètres du Pare-feu Windows** : les paramètres sont réinitialisés sur les valeurs par défaut du système d’exploitation. Pour plus d’informations, consultez [Contribuer à la sécurisation des PC Windows avec Endpoint Protection pour Microsoft Intune](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md).


### Comment actualiser les stratégies sur un appareil pour vérifier qu’elles sont à jour ? (s’applique aux ordinateurs Windows exécutant le logiciel client Intune uniquement)

1.  Dans un groupe d’appareils, sélectionnez les appareils sur lesquels vous voulez actualiser les stratégies, puis sélectionnez **Tâches à distance** &gt; **Actualiser les stratégies**.
2.  Sélectionnez **Tâches à distance** dans le coin inférieur droit de la console d’administration Intune pour vérifier l’état de la tâche.

### Où puis-je trouver de l’aide concernant mes problèmes de stratégies ?

Consultez [Résoudre les problèmes de stratégie dans Microsoft Intune](../Troubleshoot/troubleshoot-policies-in-microsoft-intune).


<!--HONumber=Jun16_HO3-->


