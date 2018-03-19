---
title: "Créer une stratégie de conformité pour des appareils Android dans Microsoft Intune"
titleSuffix: 
description: "Créez une stratégie de conformité de l’appareil Microsoft Intune pour les appareils Android afin de pouvoir spécifier des exigences qu’un appareil doit respecter pour être conforme."
keywords: 
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e1258fe4-0b5c-4485-8bd1-152090df6345
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 283685629ac1e268a66d82250273a17f9baa5d17
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/08/2018
---
# <a name="how-to-create-a-device-compliance-policy-for-android-devices-in-intune"></a>Guide pratique pour créer une stratégie de conformité pour des appareils Android dans Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Une stratégie de conformité de l’appareil Intune pour Android spécifie les règles et les paramètres que les appareils Android doivent satisfaire pour être considérés comme conformes. Vous pouvez utiliser ces stratégies avec l’accès conditionnel pour autoriser ou bloquer l’accès aux ressources de l’entreprise, et vous pouvez générer des rapports sur les appareils et prendre des mesures en cas de non-conformité. Vous créez des stratégies de conformité de l’appareil pour chaque plateforme dans le portail Intune Azure. Pour en savoir plus sur les stratégies de conformité et sur les prérequis à prendre en compte avant de créer une stratégie, consultez [Bien démarrer avec la conformité des appareils](device-compliance-get-started.md).

## <a name="to-create-a-device-compliance-policy"></a>Pour créer une stratégie de conformité de l’appareil

1. Connectez-vous au [portail Azure](https://portal.azure.com).
2. Choisissez **Tous les services** > **Intune**. Intune se trouve dans la section **Surveillance + Gestion**.
1. Dans le volet **Intune**, choisissez **Conformité de l’appareil**. Sous **Gérer**, choisissez **Stratégies**, puis **Créer une stratégie**.
3. Choisissez **Configurer les paramètres** pour spécifier les paramètres **Sécurité du système**, **Intégrité de l’appareil** et **Propriétés de l’appareil**. Une fois que vous avez terminé, choisissez **Enregistrer**.

<!--- 4. Choose **Actions for noncompliance** to say what actions should happen when a device is determined as noncompliant based on the configured settings in this policy.
5. In the **Actions for noncompliance** pane, choose **Add** to create a new action.  The action parameters pane allows you to specify the action, email recipients that should receive the notification in addition to the user of the device, and the content of the notification that you want to send.
6. The message template option allows you to create several custom emails depending on when the action is set to take. For example, you can create a message for notifications that are sent for the first time and a different message for final warning before access is blocked. The custom messages that you create can be used for all your device compliance policy.
7. Specify the **Grace period** which determines when that action to take place.  For example, you may want to send a notification as soon as the device is evaluated as noncompliant, but allow some time before enforcing the conditional access policy to block access to company resources like SharePoint online.
8. Choose **Add** to finish creating the action.
9. You can create multiple actions and the sequence in which they should occur. Choose **OK** when you are finished creating all the actions.--->

## <a name="to-assign-user-groups"></a>Pour affecter des groupes d’utilisateurs

Pour attribuer une stratégie de conformité à des utilisateurs, choisissez une stratégie que vous avez configurée. Vous trouverez les stratégies existantes dans le volet **Conformité de l’appareil – Stratégies**.

1. Choisissez la stratégie, puis **Affectations**. Cette opération ouvre le volet dans lequel vous pouvez sélectionner des **groupes de sécurité Azure Active Directory** que vous affectez à la stratégie.
2. Choisissez **Groupes sélectionnés** pour ouvrir la page qui affiche les groupes de sécurité Azure AD. Vous y trouvez les groupes de sécurité figurant dans Azure Active Directory.  Vous pouvez sélectionner les groupes d’utilisateurs auxquels vous souhaitez appliquer cette stratégie et choisir **Enregistrer** afin de déployer la stratégie pour les utilisateurs.

Vous avez appliqué la stratégie à des utilisateurs.  La conformité des appareils utilisés par les utilisateurs ciblés par la stratégie de conformité sera évaluée.

<!---##  Compliance policy settings--->

## <a name="device-health-and-security-settings"></a>Paramètres d’intégrité et de sécurité de l’appareil

- **L’appareil ne doit pas être jailbreaké ou rooté** : si vous activez ce paramètre, les appareils jailbreakés ne sont pas détectés comme conformes.
- **Exiger que les appareils interdisent l’installation des applications provenant de sources inconnues (Android 4.0+)** : pour bloquer les appareils qui ont **Sécurité** > **Sources inconnues** activé, activez ce paramètre et définissez-le sur **Oui**.

### <a name="important"></a>Important

Pour les applications en chargement indépendant, le paramètre **Sources inconnues** doit être activé. Appliquez cette stratégie de conformité uniquement si vous n’effectuez aucun chargement indépendant d’applications Android sur les appareils.

- **Exiger que le débogage USB soit désactivé (Android 4.2 ou ultérieur)** : ce paramètre spécifie si la détection de l’option de débogage USB est activée sur l’appareil.
- **Exiger que « Rechercher les menaces de sécurité sur l'appareil » soit activé sur les appareils (Android 4.2-4.4)** : ce paramètre spécifie si la fonctionnalité **Vérifier les applications** est activée sur l’appareil.
- **Niveau minimal du correctif de sécurité Android (Android 6.0 ou ultérieur)** : utilisez ce paramètre pour spécifier le niveau de correctif Android minimal. Les appareils qui ne sont pas au moins à ce niveau de correctif sont non conformes. La date doit être spécifiée dans le format AAAA-MM-JJ.
- **Exiger l’activation de la protection de l’appareil contre les menaces**: utilisez ce paramètre pour sélectionner l’évaluation des risques de la solution Lookout MTP comme une condition de conformité. Choisissez le niveau de menace maximal autorisé parmi les options suivantes :
  - **Aucun (sécurisé)** : c’est le niveau de sécurité le plus haut. L’appareil ne peut présenter aucune menace. Si des menaces d’un autre niveau sont détectées sur l’appareil, celui-ci est évalué comme non conforme.
  - **Faible** : l’appareil est évalué comme conforme uniquement si les menaces détectées sont de niveau faible. La présence de menaces de niveau supérieur rend l’appareil non conforme.
  - **Moyen** : l’appareil est évalué comme conforme si les menaces détectées sont de niveau faible ou moyen. La présence de menaces de niveau élevé rend l’appareil non conforme.
  - **Élevé** : cette option est la moins sécurisée. Essentiellement, elle autorise tous les niveaux de menace. Elle peut s’avérer utile si vous ne recourez à cette solution qu’à des fins de création de rapport.

Pour plus d’informations, consultez [Activer une règle de protection de l’appareil contre les menaces dans la stratégie de conformité](https://docs.microsoft.com/intune-classic/deploy-use/enable-device-threat-protection-rule-in-compliance-policy).

## <a name="system-security-settings"></a>Paramètres de sécurité système

### <a name="password"></a>Mot de passe

- **Exiger un mot de passe pour déverrouiller des appareils mobiles** : définissez cette option sur **Oui** pour obliger les utilisateurs à entrer un mot de passe pour accéder à leur appareil.
- **Longueur minimale du mot de passe** : spécifie le nombre minimal de chiffres ou de caractères devant figurer dans le mot de passe de l’utilisateur.
- **Qualité du mot de passe :** ce paramètre détecte si les critères de mot de passe que vous spécifiez sont configurés sur l’appareil. Activez ce paramètre pour que les utilisateurs satisfassent à certains critères de mot de passe pour les appareils Android. Choisissez parmi :
  - **Sécurité biométrique faible**
  - **Obligatoire**
  - **Au moins numérique**
  - **Au moins alphabétique**
  - **Au moins alphanumérique**
  - **Alphanumérique avec symboles**
- **Minutes d’inactivité avant demande du mot de passe** : spécifiez la durée d’inactivité au terme de laquelle l’utilisateur doit entrer à nouveau son mot de passe.
- **Expiration du mot de passe (jours)** : sélectionnez le nombre de jours avant que le mot de passe de l’utilisateur n’expire et qu’il ne doive en créer un autre.
- **Mémoriser l’historique des mots de passe** : utilisez ce paramètre avec le paramètre **Empêcher la réutilisation des mots de passe précédents** pour empêcher l’utilisateur de créer des mots de passe qui ont déjà été utilisés.
- **Empêcher la réutilisation des mots de passe précédents** : si vous avez sélectionné l’option **Mémoriser l’historique des mots de passe**, spécifiez le nombre de mots de passe précédemment utilisés qui ne peuvent pas être réutilisés.
- **Exiger un mot de passe quand l’appareil quitte un état inactif** : utilisez ce paramètre conjointement avec le paramètre **Minutes d’inactivité avant demande du mot de passe**. L’utilisateur est invité à entrer un mot de passe pour accéder à un appareil qui a été inactif pendant la durée spécifiée par le paramètre **Minutes d’inactivité avant demande du mot de passe**.

### <a name="encryption"></a>Chiffrement

- **Exiger le chiffrement sur l’appareil mobile** : affectez la valeur **Oui** pour exiger que les appareils soient chiffrés pour pouvoir se connecter aux ressources. Les appareils sont chiffrés quand vous choisissez le paramètre **Exiger un mot de passe pour déverrouiller des appareils mobiles**.

## <a name="device-property-settings"></a>Paramètres de propriétés d’appareils

- **Système d’exploitation minimal requis** : quand un appareil ne satisfait pas à la condition de version minimale du système d’exploitation, il est signalé comme non conforme. Un lien avec des informations sur la mise à niveau s’affiche. L’utilisateur peut choisir de mettre à niveau son appareil, après quoi il pourra accéder aux ressources de l’entreprise.
- **Version maximale autorisée du système d’exploitation** : quand un appareil utilise une version du système d’exploitation ultérieure à celle spécifiée dans la règle, l’accès aux ressources de l’entreprise est bloqué et l’utilisateur est invité à contacter son administrateur informatique. Jusqu’à ce qu’il y ait une modification des règles pour autoriser la version du système d’exploitation, cet appareil ne peut pas être utilisé pour accéder aux ressources de l’entreprise.

## <a name="how-noncompliant-settings-work-with-conditional-access-policies"></a>Comment fonctionnent les paramètres non conformes avec les stratégies d’accès conditionnel ?

La table ci-dessous décrit également la façon dont les paramètres non conformes sont gérés quand une stratégie de conformité est utilisée avec une stratégie d’accès conditionnel.

--------------------

|**Paramètre de stratégie**| **Android 4.0 et versions ultérieures, Samsung Knox Standard 4.0 et versions ultérieures** |
| --- | ----|
| **Configuration d’un code confidentiel ou mot de passe** |  En quarantaine |
| **Chiffrement de l’appareil** | En quarantaine |
| **Appareil jailbroken ou rooté** | En quarantaine (pas un paramètre) |
| **profil de messagerie** | Non applicable |
| **Version minimale du système d’exploitation** | En quarantaine |
| **Version maximale du système d’exploitation** |   En quarantaine |
| **Attestation de l’intégrité Windows** | Non applicable |

--------------------------

**Corrigé** : le système d’exploitation de l’appareil applique la conformité. (Par exemple, l’utilisateur est obligé de définir un code confidentiel.)

**En quarantaine** : le système d’exploitation de l’appareil n’applique pas la conformité. (Par exemple, les appareils Android n’obligent pas l’utilisateur à chiffrer l’appareil.) Quand l’appareil n’est pas conforme, les actions suivantes se produisent :

- L’appareil est bloqué si une stratégie d’accès conditionnel s’applique à l’utilisateur.
- Le portail d’entreprise informe l’utilisateur des problèmes de conformité.

<!--- ## Next steps

[How to monitor device compliance](device-compliance-monitor.md)--->
