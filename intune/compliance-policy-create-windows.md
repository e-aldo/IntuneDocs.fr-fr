---
title: "Guide pratique pour créer une stratégie de conformité pour Windows"
titleSuffix: Intune on Azure
description: "Apprenez à créer une stratégie de conformité pour les appareils Windows."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 13fc7783-d4de-47d0-b1b8-4c8710a9e6ab
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 91f0a71ed7b924746425822ce10190a8ec7a7a40
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/01/2017
---
# <a name="how-to-create-a-device-compliance-policy-for-windows-devices-in-intune"></a>Guide pratique pour créer une stratégie de conformité pour des appareils Windows dans Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Des stratégies de conformité sont créées pour chaque plateforme.  Vous pouvez créer une stratégie de conformité dans le portail Azure. Pour en savoir plus sur ce qu'est la stratégie de conformité, consultez la rubrique [Qu'est-ce-que la compatibilité des appareils ?](device-compliance.md). Pour en savoir plus sur les conditions préalables à prendre en compte avant de créer une stratégie, consultez la rubrique [Bien démarrer avec la conformité des appareils](device-compliance-get-started.md).

La table ci-dessous décrit également la façon dont les paramètres non conformes sont gérés quand une stratégie de conformité est utilisée avec une stratégie d’accès conditionnel.

---------------------------

| **Paramètre de stratégie** | **Windows 8.1 et versions ultérieures** | **Windows Phone 8.1 et versions ultérieures** |
|----| ----| --- |
| **Configuration d’un code confidentiel ou mot de passe** | Corrigé | Corrigé |   
| **Chiffrement de l’appareil** | Non applicable | Corrigé |   
| **Appareil jailbroken ou rooté** | Non applicable | Non applicable |  
| **Profil de messagerie** | Non applicable | Non applicable |   
| **Version minimale du système d’exploitation** | En quarantaine | En quarantaine |   
| **Version maximale du système d’exploitation** | En quarantaine | En quarantaine |   
| **Attestation de l’intégrité Windows** | En quarantaine : Windows 10 et Windows 10 Mobile|Non applicable : Windows 8.1 |

-------------------------------

**Corrigé** : le système d’exploitation de l’appareil applique la conformité. (Par exemple, l’utilisateur est obligé de définir un code PIN.)+

**En quarantaine** : le système d’exploitation de l’appareil n’applique pas la conformité. (Par exemple, les appareils Android n’obligent pas l’utilisateur à chiffrer l’appareil.) Quand l’appareil n’est pas conforme, les actions suivantes se produisent :+

- L’appareil est bloqué si une stratégie d’accès conditionnel s’applique à l’utilisateur.
- Le portail d’entreprise informe l’utilisateur des problèmes de conformité.

## <a name="create-a-compliance-policy-in-the-azure-portal"></a>Création d'une stratégie de conformité dans le portail Azure

1. Dans le panneau **Intune**, choisissez **Définir la conformité des appareils**. Sous **Gérer**, choisissez **Toutes les stratégies de conformité d'appareil**, puis **Créer**.
2. Tapez un nom et une description, puis sélectionnez la plateforme à laquelle vous souhaitez appliquer cette stratégie.
3. Choisissez **Critères de conformité** pour ouvrir le panneau des exigences de conformité.  Vous pouvez spécifier les paramètres **Sécurité**, **Intégrité de l'appareil** et la **propriété de l'appareil** ici. Lorsque vous avez terminé, choisissez **Ok**.

<!--- 4. Choose **Actions for noncompliance** to say what actions should happen when a device is determined as noncompliant with this policy.
5. In the **Actions for noncompliance** blade, choose **Add** to create a new action.  The action parameters blade allows you to specify the action, email recipients that should receive the notification in addition to the user of the device, and the content of the notification that you want to send.
6. The message template option allows you to create several custom emails depending on when the action is set to take. For example, you can create a message for notifications that are sent for the first time and a different message for final warning before access is blocked. The custom messages that you create can be used for all your device compliance policy.
7. Specify the **Grace period** which determines when that action to take place.  For example, you may want to send a notification as soon as the device is evaluated as noncompliant, but allow some time before enforcing the conditional access policy to block access to company resources like SharePoint online.
8. Choose **Add** to finish creating the action.
9. You can create multiple actions and the sequence in which they should occur. Choose **Ok** when you are finished creating all the actions.--->

## <a name="assign-user-groups"></a>Affectation de groupes d’utilisateurs

Pour attribuer une stratégie de conformité à des utilisateurs, choisissez une stratégie que vous avez configurée. Vous trouverez les stratégies existantes dans le panneau **Stratégie de conformité**.

1. Choisissez la stratégie que vous souhaitez attribuer aux utilisateurs, puis **Affectations**. Cette opération ouvre le panneau dans lequel vous pouvez sélectionner des **groupes de sécurité Azure Active Directory** que vous attribuez à la stratégie.
2. Choisissez **Sélectionner des groupes** pour ouvrir le panneau qui affiche les groupes de sécurité Azure AD.  Si vous choisissez **Sélectionner**, la stratégie est déployée pour les utilisateurs.

Vous avez appliqué la stratégie à des utilisateurs.  La conformité des appareils utilisés par les utilisateurs ciblés par la stratégie de conformité sera évaluée.

<!---## Compliance policy settings--->

## <a name="system-security-settings"></a>Paramètres de sécurité système

### <a name="password"></a>Mot de passe

- **Exiger un mot de passe pour déverrouiller des appareils mobiles :** définissez cette option sur **Oui** pour obliger les utilisateurs à entrer un mot de passe pour accéder à leur appareil.
- **Autoriser les mots de passe simples :** définissez cette option sur **Oui** pour permettre aux utilisateurs de créer des mots de passe simples tels que « **1234** » ou « **1111** ».
- **Longueur minimale du mot de passe** : spécifie le nombre minimal de chiffres ou de caractères devant figurer dans le mot de passe de l’utilisateur.
- **Type de mot de passe requis :** spécifiez si les utilisateurs doivent créer un mot de passe de type **Alphanumérique** ou **Numérique**.

Pour les appareils qui exécutent Windows et qui sont utilisés avec un compte Microsoft, la stratégie de conformité n’est pas évaluée correctement si l’option Longueur minimale du mot de passe a une valeur supérieure à huit caractères ou si l’option Nombre minimum de jeux de caractères a une valeur supérieure à deux.

- **Nombre minimum de jeux de caractères :** si le paramètre **Type de mot de passe requis** a la valeur **Alphanumérique**, ce paramètre spécifie le nombre minimal de jeux de caractères que le mot de passe doit contenir. Les quatre jeux de caractères sont :
  - Lettres minuscules
  - Lettres majuscules
  - Symboles
  - Nombres

Le fait de définir un nombre plus élevé pour ce paramètre oblige les utilisateurs à créer des mots de passe plus complexes. Pour les appareils qui exécutent Windows et qui sont utilisés avec un compte Microsoft, la stratégie de conformité n’est pas évaluée correctement si l’option Longueur minimale du mot de passe a une valeur supérieure à huit caractères ou si l’option Nombre minimum de jeux de caractères a une valeur supérieure à deux.

- **Minutes d’inactivité avant demande du mot de passe** : spécifie la durée d’inactivité au terme de laquelle l’utilisateur doit entrer à nouveau son mot de passe.
- **Expiration du mot de passe (jours)** : sélectionnez le nombre de jours avant que le mot de passe de l’utilisateur n’expire et qu’il ne doive en créer un autre.
- **Mémoriser l’historique des mots de passe** : utilisez ce paramètre conjointement avec le paramètre **Empêcher la réutilisation des mots de passe précédents** pour empêcher l’utilisateur de créer des mots de passe qui ont déjà été utilisés.
- **Empêcher la réutilisation des mots de passe précédents :** si l’option **Mémoriser l’historique des mots de passe** est sélectionnée, spécifiez le nombre de mots de passe précédemment utilisés qui ne peuvent pas être réutilisés.
- **Exiger un mot de passe quand l'appareil quitte un état inactif :** ce paramètre doit être utilisé conjointement avec le paramètre **Minutes d’inactivité avant demande du mot de passe**. Les utilisateurs finaux sont invités à entrer un mot de passe pour accéder à un appareil qui a été inactif pendant la durée spécifiée par le paramètre **Minutes d’inactivité avant demande du mot de passe**.

**Ce paramètre s’applique uniquement aux appareils Windows 10 Mobile.**

### <a name="encryption"></a>Chiffrement

- **Exiger le chiffrement sur l’appareil mobile :** affectez la valeur **Oui** pour exiger que l’appareil soit chiffré pour pouvoir se connecter aux ressources.



## <a name="device-health-settings"></a>Paramètres d’intégrité des appareils

- **Exiger que les appareils soient signalés comme ne posant aucun problème d’intégrité :** vous pouvez définir une règle pour exiger que les appareils **Windows 10 Mobile** soient signalés comme étant sains dans des stratégies de conformité nouvelles ou existantes. Si ce paramètre est activé, les points de données suivants sont évalués sur les appareils Windows 10 à l’aide du service d’attestation de l’intégrité (HAS, Health Attestation Service) :
  - **BitLocker est activé :** quand BitLocker est activé, l’appareil peut protéger les données stockées sur le lecteur contre tout accès non autorisé, quand le système est mis hors tension ou en veille prolongée. Le Chiffrement de lecteur BitLocker Windows chiffre toutes les données stockées sur le volume de système d’exploitation Windows. BitLocker utilise le module de plateforme sécurisée pour protéger le système d’exploitation Windows et les données de l’utilisateur. Il aide à s’assurer qu’un ordinateur n’a pas été falsifié, même en cas de perte ou de vol ou s’il a été laissé sans surveillance. Si l’ordinateur est équipé d’un module de plateforme sécurisée compatible, BitLocker utilise ce module pour verrouiller les clés de chiffrement qui protègent les données. Ainsi, les clés ne sont accessibles qu’une fois que le module de plateforme sécurisée a vérifié l’état de l’ordinateur
  - **L’intégrité du code est activée :** l’intégrité du code est une fonctionnalité qui valide l’intégrité d’un fichier de pilote ou d’un fichier système chaque fois qu’il est chargé en mémoire. Elle détecte si un fichier système ou un fichier de pilote non signé est chargé dans le noyau, ou si un fichier système a été modifié par un logiciel malveillant exécuté par un compte d’utilisateur avec des privilèges d’administrateur.
  - **Le démarrage sécurisé est activé** : quand le démarrage sécurisé est activé, le système est obligé de démarrer dans un état usine approuvé. De plus, quand le démarrage sécurisé est activé, les principaux composants utilisés pour démarrer l’ordinateur doivent avoir des signatures de chiffrement appropriées qui sont approuvées par l’organisation ayant fabriqué l’appareil. Le microprogramme UEFI vérifie cela avant de laisser l’ordinateur démarrer. Si des fichiers ont été falsifiés et que leur signature a été rompue, le système ne démarre pas.

Pour plus d’informations sur le fonctionnement du service HAS, consultez [HealthAttestation CSP](https://msdn.microsoft.com/library/dn934876.aspx).

## <a name="device-property-settings"></a>Paramètres de propriétés d’appareils

- **Système d’exploitation minimal requis :** quand un appareil ne satisfait pas la condition de version minimale du système d’exploitation, il est signalé comme non conforme. Un lien avec des informations sur la mise à niveau s’affiche. L’utilisateur final peut choisir de mettre à niveau son appareil, après quoi il pourra accéder aux ressources de l’entreprise.
- **Version maximale autorisée du système d’exploitation :** quand un appareil utilise une version du système d’exploitation ultérieure à celle spécifiée dans la règle, l’accès aux ressources de l’entreprise est bloqué et l’utilisateur est invité à contacter son administrateur informatique. Jusqu’à ce qu’il y ait une modification de la règle pour autoriser la version du système d’exploitation, cet appareil ne peut pas être utilisé pour accéder aux ressources de l’entreprise.

<!---## Compliance policy settings for Windows PCs--->

## <a name="system-security-settings"></a>Paramètres de sécurité système

### <a name="password"></a>Mot de passe

- **Longueur minimale du mot de passe :** prise en charge par Windows 8.1.

Spécifiez le nombre minimal de chiffres ou de caractères devant figurer dans le mot de passe de l'utilisateur.

Pour les appareils qui exécutent Windows et qui sont utilisés avec un compte Microsoft, la stratégie de conformité n’est pas évaluée correctement si l’option **Longueur minimale du mot de passe** a une valeur supérieure à 8 caractères ou si l’option **Nombre minimum de jeux de caractères** a une valeur supérieure à deux caractères.

- **Type de mot de passe requis** : pris en charge sur Windows RT, Windows RT 8.1 et Windows 8.1

Spécifiez si les utilisateurs doivent créer un mot de passe de type **Alphanumérique** ou **Numérique**.

- **Nombre minimal de jeux de caractères** : pris en charge sur Windows RT, Windows RT 8.1 et Windows 8.1. Si le paramètre **Type de mot de passe requis** a la valeur **Alphanumérique**, ce paramètre spécifie le nombre minimal de jeux de caractères que le mot de passe doit contenir. Les quatre jeux de caractères sont :
  - Lettres minuscules
  - Lettres majuscules
  - Symboles
  - Nombres : le fait de définir un nombre plus élevé pour ce paramètre oblige les utilisateurs à créer des mots de passe plus complexes.

Pour les appareils qui exécutent Windows et qui sont utilisés avec un compte Microsoft, la stratégie de conformité n’est pas évaluée correctement si l’option **Longueur minimale du mot de passe** a une valeur supérieure à 8 caractères ou si l’option **Nombre minimum de jeux de caractères** a une valeur supérieure à 2 caractères.

- **Minutes d'inactivité avant demande du mot de passe :** pris en charge sur Windows RT, Windows RT 8.1 et Windows 8.1

Spécifiez la durée d'inactivité au terme de laquelle l'utilisateur doit entrer à nouveau son mot de passe.

- **Expiration du mot de passe (jours)** : pris en charge sur Windows RT, Windows RT 8.1 et Windows 8.1.

Sélectionnez le nombre de jours avant que le mot de passe de l'utilisateur n'expire et qu'il ne doive en créer un autre.

- **Mémoriser l'historique des mots de passe :** pris en charge sur Windows RT, Windows RT et Windows 8.1.

Utilisez ce paramètre conjointement avec le paramètre **Empêcher la réutilisation des mots de passe précédents** pour empêcher l’utilisateur de créer des mots de passe qui ont déjà été utilisés.

- **Empêcher la réutilisation des mots de passe précédents :** pris en charge sur Windows RT, Windows RT 8.1 et Windows 8.1

Si l’option **Mémoriser l’historique des mots de passe** est sélectionnée, spécifiez le nombre de mots de passe précédemment utilisés qui ne peuvent pas être réutilisés.


## <a name="device-health-settings"></a>Paramètres d’intégrité des appareils

- **Exiger que les appareils soient signalés comme ne posant aucun problème d’intégrité :** pris en charge sur les appareils Windows 10. Vous pouvez définir une règle pour exiger que les appareils Windows 10 soient signalés comme étant sains dans des stratégies de conformité nouvelles ou existantes. Si ce paramètre est activé, les points de données suivants sont évalués sur les appareils Windows 10 à l’aide du service d’attestation de l’intégrité (HAS, Health Attestation Service) :
  - **BitLocker est activé :** quand BitLocker est activé, l’appareil peut protéger les données stockées sur le lecteur contre tout accès non autorisé, quand le système est mis hors tension ou en veille prolongée. Le Chiffrement de lecteur BitLocker Windows chiffre toutes les données stockées sur le volume de système d’exploitation Windows. BitLocker utilise le module de plateforme sécurisée pour protéger le système d’exploitation Windows et les données de l’utilisateur. Il aide à s’assurer qu’un ordinateur n’a pas été falsifié, même en cas de perte ou de vol ou s’il a été laissé sans surveillance. Si l’ordinateur est équipé d’un module de plateforme sécurisée compatible, BitLocker utilise ce module pour verrouiller les clés de chiffrement qui protègent les données. Ainsi, les clés ne sont accessibles qu’une fois que le module de plateforme sécurisée a vérifié l’état de l’ordinateur
  - **L’intégrité du code est activée :** l’intégrité du code est une fonctionnalité qui valide l’intégrité d’un fichier de pilote ou d’un fichier système chaque fois qu’il est chargé en mémoire. Elle détecte si un fichier système ou un fichier de pilote non signé est chargé dans le noyau, ou si un fichier système a été modifié par un logiciel malveillant exécuté par un compte d’utilisateur avec des privilèges d’administrateur.
  - **Le démarrage sécurisé est activé** : quand le démarrage sécurisé est activé, le système est obligé de démarrer dans un état usine approuvé. De plus, quand le démarrage sécurisé est activé, les principaux composants utilisés pour démarrer l’ordinateur doivent avoir des signatures de chiffrement appropriées qui sont approuvées par l’organisation ayant fabriqué l’appareil. Le microprogramme UEFI vérifie cela avant de laisser l’ordinateur démarrer. Si des fichiers ont été falsifiés et que leur signature a été rompue, le système ne démarre pas.
  - **Logiciel anti-programme malveillant à lancement anticipé :** un logiciel anti-programme malveillant à lancement anticipé protège les ordinateurs de votre réseau quand ils démarrent et avant l’initialisation des pilotes tiers.

Pour plus d’informations sur le fonctionnement du service HAS, consultez [HealthAttestation CSP](https://msdn.microsoft.com/library/dn934876.aspx).

## <a name="device-property-settings"></a>Paramètres de propriétés d’appareils

- **Système d'exploitation minimal requis :** pris en charge sur Windows 8.1 et Windows 10.

Indiquez ici le numéro major.minor.build. Le numéro de version doit correspondre à la version retournée par la commande ```winver```.

Si un appareil possède une version antérieure à la version du système d'exploitation spécifiée, il est signalé comme étant non conforme. Un lien avec des informations sur la mise à niveau s’affiche. L’utilisateur final peut choisir de mettre à niveau son appareil, après quoi il pourra accéder aux ressources de l’entreprise.

- **Version maximale autorisée du système d’exploitation :** pris en charge sur Windows 8.1 et Windows 10.

Quand un appareil utilise une version du système d’exploitation ultérieure à celle spécifiée dans la règle, accès aux ressources de l’entreprise est bloqué et l’utilisateur est invité à contacter son administrateur. Jusqu’à ce qu’il y ait une modification de la règle pour autoriser la version du système d’exploitation, cet appareil ne peut pas être utilisé pour accéder aux ressources de l’entreprise.

Pour rechercher la version du système d’exploitation à utiliser pour les paramètres **Système d’exploitation minimal requis** et **Version maximale autorisée du système d’exploitation**, exécutez la commande **winver** à partir de l’invite de commandes. La commande winver retourne la version signalée du système d’exploitation.+

- Les PC Windows 8.1 retournent la version **3**. Si la règle de la version du système d’exploitation est définie sur Windows 8.1 pour Windows, l’appareil est signalé comme non conforme même si Windows 8.1 est installé dessus.
- Pour les PC Windows exécutant Windows 10, la version doit être définie comme étant &quot;10.0&quot; + le numéro de version du système d’exploitation retourné par la commande winver.

<!--- ## Next steps

[How to monitor device compliance](device-compliance-monitor.md)--->
