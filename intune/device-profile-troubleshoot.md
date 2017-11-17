---
title: "Résoudre les problèmes de profil d’appareil dans Microsoft Intune"
titlesuffix: Azure portal
description: "Si vous ne savez pas comment vous y prendre, utilisez cette rubrique pour vous aider à résoudre les problèmes de profils d’appareil Intune."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 11/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ff950ce35c491ca576dc9cc77ab561e2cfef0381
ms.sourcegitcommit: 1df625330f4e8f7f661b5f2b9f16b5590971838d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/10/2017
---
# <a name="troubleshooting-device-profiles-in-microsoft-intune"></a>Résoudre les problèmes de profil d’appareil dans Microsoft Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Les informations contenues dans cette rubrique peuvent être utilisées pour vous aider à résoudre les problèmes courants avec les profils d’appareil Intune.

## <a name="why-doesnt-a-user-get-a-new-profile-when-changing-a-password-or-passphrase-on-an-existing-wi-fi-profile"></a>Pourquoi un utilisateur n’obtient-il pas un nouveau profil lors de la modification d’un mot de passe ou d’une phrase secrète dans un profil Wi-Fi existant ? 
Quand vous créez un profil Wi-Fi d’entreprise, déployez le profil sur un groupe, modifiez le mot de passe et enregistrez le profil, vous pourriez vous attendre à ce que l’utilisateur obtienne le nouveau profil. Toutefois, il est possible que ce ne soit pas le cas. 

Pour résoudre ce problème, veillez à disposer d’un profil Wi-Fi invité de telle sorte que l’utilisateur bascule vers ce profil Wi-Fi invité en cas de défaillance du profil Wi-Fi d’entreprise. Le paramètre de connexion automatique doit être activé. Ce profil Wi-Fi invité doit être déployé sur tous les utilisateurs.

Vous pouvez aussi respecter les bonnes pratiques suivantes :
- Étant donné que le réseau Wi-Fi auquel vous vous connectez prend un mot de passe ou une phrase secrète, vérifiez que vous pouvez vous connecter directement au routeur Wi-Fi. Vous pouvez faire le test avec un appareil iOS.
- Une fois que vous vous êtes connecté au point de terminaison Wi-Fi (routeur Wi-Fi), notez le SSID et les informations d’identification utilisées (il s’agit du mot de passe ou de la phrase secrète.)
- Entrez le SSID et les informations d’identification (mot de passe ou phrase secrète) dans le champ Clé prépartagée. 
- Effectuez le déploiement sur un groupe de test ayant un nombre d’utilisateurs limité, de préférence uniquement l’équipe informatique. 
- Synchronisez votre appareil iOS avec Intune. Procédez à l’inscription si ce n’est déjà fait. 
- Testez à nouveau la connexion au même point de terminaison Wi-Fi (comme indiqué à la première étape).
- Déployez sur des groupes plus volumineux, puis finalement sur tous les utilisateurs attendus dans votre organisation. 

## <a name="how-long-does-it-take-for-mobile-devices-to-get-a-policy-or-apps-after-they-have-been-assigned"></a>Combien de temps faut-il pour que les appareils mobiles obtiennent une stratégie ou les applications une fois que celles-ci ont été affectées ?
Quand une stratégie ou une application est affectée, Intune essaie d’envoyer immédiatement une notification à l’appareil pour qu’il s’enregistre auprès du service Intune. Cette opération prend généralement moins de 5 minutes.

Si un appareil ne se manifeste pas pour obtenir la stratégie après l’envoi de la première notification, Intune effectue trois autres tentatives.  Si l’appareil est hors connexion (par exemple, s’il est éteint ou n’est pas connecté à un réseau), il ne peut pas recevoir de notifications. Dans ce cas, l’appareil obtiendra la stratégie lors de son prochain enregistrement planifié auprès du service Intune, de la manière suivante :

- iOS et macOS : toutes les 6 heures.
- Android  : toutes les 8 heures.
- Windows Phone : toutes les 8 heures.
- PC Windows 8.1 et Windows 10 inscrits en tant qu’appareils : toutes les 8 heures.

Si l’appareil vient d’être inscrit, la fréquence d’enregistrement est plus fréquente :

- iOS et macOS : toutes les 15 minutes pendant 6 heures, puis toutes les 6 heures.
- Android : toutes les 3 minutes pendant 15 minutes, puis toutes les 15 minutes pendant 2 heures, puis toutes les 8 heures.
- Windows Phone : toutes les 5 minutes pendant 15 minutes, puis toutes les 15 minutes pendant 2 heures, puis toutes les 8 heures.
- PC Windows inscrits en tant qu’appareils : toutes les 3 minutes pendant 30 minutes, puis toutes les 8 heures.

Les utilisateurs peuvent également ouvrir l’application Portail d’entreprise et synchroniser l’appareil pour qu’il recherche immédiatement les stratégies à tout moment.

## <a name="what-actions-cause-intune-to-immediately-send-a-notification-to-a-device"></a>Quelles sont les actions qui déclenchent l’envoi immédiat d’une notification par Intune ?
Les appareils s’enregistrent auprès d’Intune quand ils reçoivent une notification leur demandant de s’enregistrer ou lors de leur enregistrement régulièrement planifié.  Quand vous ciblez un appareil ou un utilisateur spécifiquement avec une action de type réinitialisation, verrouillage, réinitialisation de code secret, attribution d’application, attribution de profil (Wi-Fi, VPN, messagerie, etc.) ou attribution de stratégie, Intune essaie immédiatement d’indiquer à l’appareil qu’il doit s’enregistrer auprès du service Intune pour recevoir ces mises à jour.

D’autres modifications, comme la modification des coordonnées dans le portail d’entreprise, ne déclenchent pas l’envoi immédiat d’une notification aux appareils.

## <a name="if-multiple-policies-are-assigned-to-the-same-user-or-device-how-do-i-know-which-settings-will-get-applied"></a>Si plusieurs stratégies sont affectées au même utilisateur ou appareil, quels sont les paramètres appliqués ?
Quand plusieurs stratégies sont affectées au même utilisateur ou appareil, l’évaluation du paramètre à appliquer est effectuée au niveau de chaque paramètre :

-   Les paramètres de stratégie de conformité ont toujours la priorité sur les paramètres de stratégie de configuration.

-   En présence de deux stratégies de conformité, c’est le paramètre de la stratégie de conformité la plus restrictive qui est appliqué.

-   Si un paramètre de stratégie de configuration entre en conflit avec un paramètre dans une autre stratégie de configuration, ce conflit apparaît dans le portail Azure. Vous devez corriger ces conflits manuellement.

## <a name="what-happens-when-app-protection-policies-conflict-with-each-other-which-one-will-be-applied-to-the-app"></a>Que se passe-t-il quand des stratégies de protection d’application entrent en conflit ? Laquelle est appliquée à l’application ?
Les valeurs en conflit sont les paramètres les plus restrictifs disponibles dans une stratégie de protection d’application, à l’exception des champs d’entrée numérique (comme le nombre de tentatives autorisées avant la réinitialisation du code PIN).  Les champs d’entrée numérique sont définis sur les mêmes valeurs que quand vous créez une stratégie de gestion des applications mobiles dans la console en choisissant les paramètres recommandés.

Des conflits se produisent quand deux paramètres de profil sont identiques.  Par exemple, vous avez configuré deux stratégies MAM identiques, à l’exception du paramètre de copier/coller.  Dans ce scénario, le paramètre de copier/coller est défini sur la valeur la plus restrictive, mais le reste des paramètres est appliqué selon leur configuration.

Si un profil est affecté à l’application et entre en vigueur, puis qu’un deuxième profil est affecté, le premier est prioritaire et reste appliqué, tandis que le deuxième s’affiche comme étant en conflit. S’ils sont appliqués en même temps, ce qui signifie qu’il n’existe aucun profil précédent, ils sont alors tous deux en conflit. Tous les paramètres en conflit sont définis sur les valeurs les plus limitées.

## <a name="what-happens-when-ios-custom-policies-conflict"></a>Que se passe-t-il quand les stratégies personnalisées iOS entrent en conflit ?
Intune n’évalue pas la charge utile des fichiers de configuration Apple ni le profil OMA-URI (Open Mobile Alliance Uniform Resource Identifier) personnalisé. Son rôle se limite simplement au mécanisme de livraison.

Quand vous affectez un profil personnalisé, vérifiez que les paramètres configurés ne sont pas en conflit avec les stratégies de conformité, de configuration, ou d’autres stratégies personnalisées. Dans le cas d’un profil personnalisé avec des paramètres en conflit, l’ordre dans lequel les paramètres sont appliqués est aléatoire.

## <a name="what-happens-when-a-profile-is-deleted-or-no-longer-applicable"></a>Que se passe-t-il quand un profil est supprimé ou n’est plus applicable ?
Quand vous supprimez un profil ou retirez un appareil d’un groupe auquel un profil a été affecté, le profil et les paramètres sont supprimés de cet appareil conformément aux listes suivantes.

### <a name="enrolled-devices"></a>Appareils inscrits

- Profils Wi-Fi, VPN, de certificat et de messagerie : ces profils sont supprimés de tous les appareils inscrits et pris en charge.
- Tous les autres types de profils :
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

## <a name="i-changed-a-device-restriction-profile-but-the-changes-havent-taken-effect"></a>J’ai modifié un profil de restriction d’appareil, mais les modifications n’ont pas pris effet
Les appareils Windows Phone n’autorisent pas d’assouplir les stratégies de sécurité définies via MDM ou EAS a posteriori. Tel est le cas, par exemple, si vous fixez le **nombre minimal de caractères des mots de passe** à 8, puis que vous essayez de le réduire à 4. Le profil le plus restrictif a déjà été appliqué à l’appareil.

Selon la plateforme d’appareil, si vous voulez attribuer au profil une valeur moins sûre, vous devrez peut-être réinitialiser les stratégies de sécurité.
Par exemple, dans Windows, sur le Bureau, balayez à partir de la droite pour ouvrir la barre **Icônes**, puis choisissez **Paramètres** &gt; **Panneau de configuration**.  Sélectionnez l’applet **Comptes d’utilisateurs**.
Au bas du menu de navigation gauche figure le lien **Réinitialiser les stratégies de sécurité**. Choisissez-le, puis choisissez le bouton **Réinitialiser les stratégies**.
Pour pouvoir appliquer un profil moins restrictif, vous devrez peut-être retirer les autres appareils de gestion des appareils mobiles (par exemple Android, Windows Phone 8.1 et versions ultérieures, et iOS), puis les réinscrire dans le service.


### <a name="next-steps"></a>Étapes suivantes
Si ces informations de dépannage n’ont pas permis de vous aider, contactez le support Microsoft comme décrit dans [Comment obtenir un support technique pour Microsoft Intune](get-support.md).