---
title: "Paramètres de stratégie de conformité pour les appareils Windows"
description: "Cette rubrique décrit les règles et les paramètres que vous pouvez configurer pour une stratégie de conformité des appareils Windows."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f996842c-e9a4-4819-acb4-ee66e8fb35b8
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 67810c51c7a7b2ec1e1ff33c11a27a8757b2bcbd
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/01/2017
---
# <a name="compliance-policy-settings-for-windows-devices-in-microsoft-intune"></a>Paramètres de stratégie de conformité pour les appareils Windows dans Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Les paramètres de stratégie décrits dans cette rubrique s’appliquent aux appareils exécutant le système d’exploitation Windows. Les sections suivantes décrivent les versions de Windows prises en charge :

Si vous recherchez des informations sur d’autres plateformes, sélectionnez l’un des éléments suivants :
> [!div class="op_single_selector"]
- [Paramètres de stratégie de conformité pour les appareils iOS](ios-compliance-policy-settings-in-microsoft-intune.md)
- [Paramètres de stratégie de conformité pour les appareils Android](android-compliance-policy-settings-in-microsoft-intune.md)
- [Paramètres de stratégie de conformité pour Android for Work](afw-compliance-policy-settings-in-microsoft-intune.md)

## <a name="compliance-policy-settings-for-windows-phone-devices"></a>Paramètres de stratégie de conformité pour les appareils Windows Phone
Les paramètres répertoriés dans cette section sont pris en charge par Windows Phone 8.1 et versions ultérieures.

### <a name="system-security-settings"></a>Paramètres de sécurité système
#### <a name="password"></a>Mot de passe
- **Exiger un mot de passe pour déverrouiller des appareils mobiles** : définissez cette option sur **Oui** pour obliger l’utilisateur à entrer un mot de passe pour accéder à son appareil.

- **Autoriser les mots de passe simples** : définissez cette option sur **Oui** pour permettre à l’utilisateur de créer un mot de passe simple comme **1234** ou **1111**.

-  **Longueur minimale du mot de passe** : spécifie le nombre minimal de chiffres ou de caractères devant figurer dans le mot de passe de l’utilisateur.
- **Type de mot de passe requis** : spécifiez si l’utilisateur doit créer un mot de passe **Alphanumérique** ou un mot de passe **Numérique**.

  Pour les appareils qui exécutent Windows et qui sont utilisés avec un compte Microsoft, la stratégie de conformité n’est pas évaluée correctement si l’option Longueur minimale du mot de passe a une valeur supérieure à huit caractères ou si l’option Nombre minimum de jeux de caractères a une valeur supérieure à deux.

- **Nombre minimum de jeux de caractères** : si le paramètre **Type de mot de passe requis** a la valeur **Alphanumérique**, ce paramètre spécifie le nombre minimal de jeux de caractères que le mot de passe doit contenir. Les quatre jeux de caractères sont :
  -   Lettres minuscules
  -   Lettres majuscules
  -   Symboles
  -   Nombres

  Définir un nombre plus élevé pour ce paramètre oblige l’utilisateur à créer un mot de passe plus complexe. Pour les appareils qui exécutent Windows et qui sont utilisés avec un compte Microsoft, la stratégie de conformité n’est pas évaluée correctement si l’option Longueur minimale du mot de passe a une valeur supérieure à huit caractères ou si l’option Nombre minimum de jeux de caractères a une valeur supérieure à deux.

- **Minutes d’inactivité avant demande du mot de passe** : ce paramètre spécifie la durée d’inactivité au terme de laquelle l’utilisateur doit entrer à nouveau son mot de passe.

- **Expiration du mot de passe (jours)** : choisissez le nombre de jours avant que le mot de passe de l’utilisateur n’expire et qu’il ne doive en créer un autre.

- **Mémoriser l’historique des mots de passe** : utilisez ce paramètre conjointement avec le paramètre **Empêcher la réutilisation des mots de passe précédents** pour empêcher l’utilisateur de créer des mots de passe qui ont déjà été utilisés.

- **Empêcher la réutilisation des mots de passe précédents** : si l’option **Mémoriser l’historique des mots de passe** est sélectionnée, spécifiez le nombre de mots de passe précédemment utilisés qui ne peuvent pas être réutilisés.
- **Exiger un mot de passe quand l’appareil quitte un état inactif** : utilisez ce paramètre conjointement avec le paramètre **Minutes d’inactivité avant demande du mot de passe**. L’utilisateur est invité à entrer un mot de passe pour accéder à un appareil qui a été inactif pendant la durée spécifiée par le paramètre **Minutes d’inactivité avant demande du mot de passe**.

  > [!NOTE]
  > Ce paramètre s’applique uniquement aux appareils Windows 10 Mobile.

#### <a name="encryption"></a>Chiffrement
- **Exiger le chiffrement sur l’appareil mobile :** affectez la valeur **Oui** pour exiger que l’appareil soit chiffré pour pouvoir se connecter aux ressources.

### <a name="device-health-settings"></a>Paramètres d’intégrité des appareils
- **Exiger que les appareils soient signalés comme ne posant aucun problème d’intégrité** : vous pouvez définir une règle pour exiger que les appareils **Windows 10 Mobile** soient signalés comme étant sains dans des stratégies de conformité nouvelles ou existantes.  Si ce paramètre est activé, les points de données suivants sont évalués sur les appareils Windows 10 à l’aide du service d’attestation d’intégrité :
  -  **BitLocker est activé** : quand BitLocker est activé, l’appareil peut protéger les données stockées sur le lecteur contre tout accès non autorisé, quand le système est mis hors tension ou en veille prolongée. Le Chiffrement de lecteur BitLocker Windows chiffre toutes les données stockées sur le volume de système d’exploitation Windows. BitLocker utilise le module de plateforme sécurisée (TPM) pour protéger le système d’exploitation Windows et les données utilisateur. BitLocker permet également de vérifier qu’un ordinateur n’a pas été compromis, même s’il est resté allumé sans assistance, s’il est perdu ou s’il a été volé. Si l’ordinateur est équipé d’un module de plateforme sécurisée (TPM) compatible, BitLocker utilise ce module pour verrouiller les clés de chiffrement qui protègent les données. Ainsi, les clés ne sont accessibles qu’une fois que le module de plateforme sécurisée a vérifié l’état de l’ordinateur.
  -  **L’intégrité du code est activée :** l’intégrité du code est une fonctionnalité qui valide l’intégrité d’un fichier de pilote ou d’un fichier système chaque fois qu’il est chargé en mémoire. L’intégrité du code détecte si un fichier système ou un pilote non signé est chargé dans le noyau. Il détecte également si un fichier système a été modifié par des logiciels malveillants exécutés par un compte d’utilisateur doté de privilèges d’administrateur.
  - **Le démarrage sécurisé est activé** : quand le démarrage sécurisé est activé, le système est obligé de démarrer dans un état approuvé par défaut. De plus, quand le démarrage sécurisé est activé, les principaux composants utilisés pour démarrer l’ordinateur doivent avoir des signatures de chiffrement appropriées qui sont approuvées par l’organisation ayant fabriqué l’appareil. Le microprogramme UEFI vérifie cela avant de laisser l’ordinateur démarrer. Si des fichiers ont été falsifiés et que leur signature a été rompue, le système ne démarre pas.

  > [!IMPORTANT]
  > Les appareils Windows ne prennent pas en charge le logiciel tiers **anti-programme malveillant à lancement anticipé** (ELAM) installé dans le cadre de l’attestation de l’intégrité de l’appareil.

  Pour plus d’informations sur le fonctionnement du service HAS, consultez [HealthAttestation CSP](https://msdn.microsoft.com/library/dn934876.aspx).
###  <a name="device-property-settings"></a>Paramètres de propriétés d’appareils
- **Système d’exploitation minimal requis** : quand un appareil ne satisfait pas à la condition de version minimale du système d’exploitation, il est signalé comme non conforme.
    Un lien avec des informations sur la mise à niveau s’affiche. L’utilisateur peut choisir de mettre à niveau son appareil, après quoi il peut accéder aux ressources de l’entreprise.

- **Version maximale autorisée du système d’exploitation** : quand un appareil utilise une version du système d’exploitation ultérieure à celle spécifiée dans la règle, l’accès aux ressources de l’entreprise est bloqué et l’utilisateur est invité à contacter son administrateur informatique. Jusqu’à ce qu’il y ait une modification de la règle pour autoriser la version du système d’exploitation, cet appareil ne peut pas être utilisé pour accéder aux ressources de l’entreprise.


## <a name="compliance-policy-settings-for-windows-pcs"></a>Paramètres de stratégie de conformité pour les PC Windows
Les paramètres répertoriés dans cette section sont pris en charge par les ordinateurs Windows.
### <a name="system-security-settings"></a>Paramètres de sécurité système
#### <a name="password"></a>Mot de passe
- **Longueur minimale du mot de passe** : prise en charge par Windows 8.1.

  Spécifiez le nombre minimal de chiffres ou de caractères devant figurer dans le mot de passe de l’utilisateur.

  Pour les appareils qui exécutent Windows et qui sont utilisés avec un compte Microsoft, la stratégie de conformité n’est pas évaluée correctement si l’option **Longueur minimale du mot de passe** a une valeur supérieure à huit caractères ou si l’option **Nombre minimum de jeux de caractères** a une valeur supérieure à deux caractères.

- **Type de mot de passe requis** : pris en charge sur Windows RT, Windows RT 8.1 et Windows 8.1

  Spécifiez si l’utilisateur doit créer un mot de passe **Alphanumérique** ou un mot de passe **Numérique**.

- **Nombre minimal de jeux de caractères** : pris en charge sur Windows RT, Windows RT 8.1 et Windows 8.1.

  Si le paramètre **Type de mot de passe requis** a la valeur **Alphanumérique**, ce paramètre spécifie le nombre minimal de jeux de caractères que le mot de passe doit contenir. Les quatre jeux de caractères sont :
  -   Lettres minuscules
  -   Lettres majuscules
  -   Symboles
  -   Nombres     

  Définir un nombre plus élevé pour ce paramètre oblige l’utilisateur à créer un mot de passe plus complexe. Pour les appareils qui exécutent Windows et qui sont utilisés avec un compte Microsoft, la stratégie de conformité n’est pas évaluée correctement si l’option **Longueur minimale du mot de passe** a une valeur supérieure à huit caractères ou si l’option **Nombre minimum de jeux de caractères** a une valeur supérieure à deux caractères.

- **Minutes d’inactivité avant demande du mot de passe** : pris en charge sur Windows RT, Windows RT 8.1 et Windows 8.1

  Spécifiez la durée d’inactivité au terme de laquelle l’utilisateur doit entrer à nouveau son mot de passe.

- **Expiration du mot de passe (jours)** : pris en charge sur Windows RT, Windows RT 8.1 et Windows 8.1.

  Choisissez le nombre de jours avant que le mot de passe de l’utilisateur n’expire et qu’il ne doive en créer un autre.

- **Mémoriser l’historique des mots de passe** : pris en charge sur Windows RT et Windows 8.1.

  Utilisez ce paramètre conjointement avec le paramètre **Empêcher la réutilisation des mots de passe précédents** pour empêcher l’utilisateur de créer des mots de passe qui ont déjà été utilisés.

- **Empêcher la réutilisation des mots de passe précédents** : pris en charge sur Windows RT, Windows RT 8.1 et Windows 8.1

  Si l’option **Mémoriser l’historique des mots de passe** est sélectionnée, spécifiez le nombre de mots de passe précédemment utilisés qui ne peuvent pas être réutilisés.

### <a name="device-health-settings"></a>Paramètres d’intégrité des appareils
- **Exiger que les appareils soient signalés comme ne posant aucun problème d’intégrité** : pris en charge sur les appareils Windows 10.
Vous pouvez définir une règle pour exiger que les appareils Windows 10 soient signalés comme étant sains dans des stratégies de conformité nouvelles ou existantes. Si ce paramètre est activé, les points de données suivants sont évalués sur les appareils Windows 10 à l’aide du service d’attestation d’intégrité :
  -  **BitLocker est activé** : quand BitLocker est activé, l’appareil peut protéger les données stockées sur le lecteur contre tout accès non autorisé, quand le système est mis hors tension ou en veille prolongée. Le Chiffrement de lecteur BitLocker Windows chiffre toutes les données stockées sur le volume de système d’exploitation Windows. BitLocker utilise le module de plateforme sécurisée (TPM) pour protéger le système d’exploitation Windows et les données utilisateur. BitLocker permet également de vérifier qu’un ordinateur n’a pas été compromis, même s’il est resté allumé sans assistance, s’il est perdu ou s’il a été volé. Si l’ordinateur est équipé d’un module de plateforme sécurisée (TPM) compatible, BitLocker utilise ce module pour verrouiller les clés de chiffrement qui protègent les données. Ainsi, les clés ne sont accessibles qu’une fois que le module de plateforme sécurisée a vérifié l’état de l’ordinateur.
  -  **L’intégrité du code est activée :** l’intégrité du code est une fonctionnalité qui valide l’intégrité d’un fichier de pilote ou d’un fichier système chaque fois qu’il est chargé en mémoire. L’intégrité du code détecte si un fichier système ou un pilote non signé est chargé dans le noyau. Il détecte également si un fichier système a été modifié par des logiciels malveillants exécutés par un compte d’utilisateur doté de privilèges d’administrateur.
  - **Le démarrage sécurisé est activé** : quand le démarrage sécurisé est activé, le système est obligé de démarrer dans un état approuvé par défaut. De plus, quand le démarrage sécurisé est activé, les principaux composants utilisés pour démarrer l’ordinateur doivent avoir des signatures de chiffrement appropriées qui sont approuvées par l’organisation ayant fabriqué l’appareil. Le microprogramme UEFI vérifie cela avant de laisser l’ordinateur démarrer. Si des fichiers ont été falsifiés et que leur signature a été rompue, le système ne démarre pas.
  - **Logiciel anti-programme malveillant à lancement anticipé** : un logiciel anti-programme malveillant à lancement anticipé protège les ordinateurs de votre réseau quand ils démarrent et avant l’initialisation des pilotes tiers.

  Pour plus d’informations sur le fonctionnement du service HAS, consultez [HealthAttestation CSP](https://msdn.microsoft.com/library/dn934876.aspx).

### <a name="device-property-settings"></a>Paramètres de propriétés d’appareils
- **Système d’exploitation minimal requis** : pris en charge sur Windows 8.1 et Windows 10.

  Indiquez ici le numéro major.minor.build. Le numéro de version doit correspondre à la version que la commande **winver** retourne.

  Si un appareil possède une version antérieure à la version du système d’exploitation spécifiée, il est signalé comme étant incompatible. Un lien avec des informations sur la mise à niveau s’affiche. L’utilisateur peut choisir de mettre à niveau son appareil, après quoi il peut accéder aux ressources de l’entreprise.

- **Version maximale autorisée du système d’exploitation** : pris en charge sur Windows 8.1 et Windows 10.

  Quand un appareil utilise une version du système d’exploitation ultérieure à celle spécifiée dans la règle, accès aux ressources de l’entreprise est bloqué et l’utilisateur est invité à contacter son administrateur. Jusqu’à ce qu’il y ait une modification de la règle pour autoriser la version du système d’exploitation, cet appareil ne peut pas être utilisé pour accéder aux ressources de l’entreprise.

Pour trouver la version du système d’exploitation à utiliser pour les paramètres **Système d’exploitation minimal requis** et **Version maximale autorisée du système d’exploitation**, exécutez la commande **winver** à partir de l’invite de commandes. La commande **winver** retourne la version signalée du système d’exploitation.

- Les PC Windows 8.1 retournent la version **6.3**. Si la règle de la version du système d’exploitation est définie sur Windows 8.1 pour Windows, l’appareil est signalé comme non conforme même si Windows 8.1 est installé dessus.

- Pour les PC Windows exécutant Windows 10, la version doit être **10.0** à laquelle s’ajoute le numéro de la build du système d’exploitation que la commande **winver** retourne. Par exemple, il peut s’agir de 10.0.10586.
> ![Version de la build du système d’exploitation mis en surbrillance dans la boîte de dialogue « À propos de Windows »](./media/ca_win10-os-version.png)
