---
title: "Paramètres de stratégie de conformité pour Android for Work | Microsoft Intune"
description: "Cette rubrique décrit les paramètres de stratégie de conformité d’appareil pour les appareils Android compatibles avec Android for Work."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 11/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e721c5c7-9678-4f3b-81d4-564da5efd337
ms.reviewer: chrisbal
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 87e37cd8334ddb9331c0662b691545cd0ab0553a
ms.openlocfilehash: 050da562fb03bbc32c4a7c293b6faad4f87ab78e


---


# <a name="compliance-policy-settings-for-android-for-work-devices-in-microsoft-intune"></a>Paramètres de stratégie de conformité pour les appareils Android for Work dans Microsoft Intune

[!INCLUDE[wit_nextref](../includes/afw_rollout_disclaimer.md)]

Les paramètres de stratégie décrits dans cette rubrique s’appliquent aux appareils Android for Work.

Si vous recherchez des informations sur d’autres plateformes, sélectionnez un des éléments suivants :
> [!div class="op_single_selector"]
- [Paramètre de stratégie de conformité pour Android](android-compliance-policy-settings-in-microsoft-intune.md)
- [Paramètres de stratégie de conformité pour les appareils iOS](ios-compliance-policy-settings-in-microsoft-intune.md)
- [Paramètres de stratégie de conformité pour les appareils Windows](windows-compliance-policy-settings-in-microsoft-intune.md)

## <a name="system-security-settings"></a>Paramètres de sécurité système
### <a name="password"></a>Mot de passe
- **Exiger un mot de passe pour déverrouiller des appareils mobiles :** définissez cette option sur **Oui** pour obliger les utilisateurs à entrer un mot de passe pour accéder à leur appareil.

-  **Longueur minimale du mot de passe** : spécifie le nombre minimal de chiffres ou de caractères devant figurer dans le mot de passe de l’utilisateur.

- **Qualité du mot de passe :** ce paramètre détecte si les critères de mot de passe que vous spécifiez sont configurés sur l’appareil. Activez ce paramètre pour que les utilisateurs configurent certains critères de mot de passe pour les appareils Android. Choisissez parmi :
  -   **Sécurité biométrique faible**
  - **Obligatoire**
  -   **Au moins numérique**
  -   **Au moins alphabétique**
  -   **Au moins alphanumérique**
  -   **Alphanumérique avec symboles**

- **Minutes d’inactivité avant demande du mot de passe** spécifie la durée d’inactivité au terme de laquelle l’utilisateur doit entrer à nouveau son mot de passe.

- **Expiration du mot de passe (jours) :** sélectionnez le nombre de jours avant que le mot de passe de l'utilisateur n'expire et qu'il ne doive en créer un autre.

- **Mémoriser l’historique des mots de passe** : utilisez ce paramètre conjointement avec le paramètre **Empêcher la réutilisation des mots de passe précédents** pour empêcher l’utilisateur de créer des mots de passe qui ont déjà été utilisés.

- **Empêcher la réutilisation des mots de passe précédents :** si l’option **Mémoriser l’historique des mots de passe** est sélectionnée, spécifiez le nombre de mots de passe précédemment utilisés qui ne peuvent pas être réutilisés.

- **Exiger un mot de passe quand l'appareil quitte un état inactif :** ce paramètre doit être utilisé conjointement avec le paramètre **Minutes d’inactivité avant demande du mot de passe**. Les utilisateurs finaux sont invités à entrer un mot de passe pour accéder à un appareil qui a été inactif pendant la durée spécifiée par le paramètre **Minutes d’inactivité avant demande du mot de passe**.

### <a name="encryption"></a>Chiffrement
- **Exiger le chiffrement sur l’appareil mobile :** vous n’êtes pas obligé de configurer ce paramètre dans la mesure où les appareils Android for Work appliquent le chiffrement.

## <a name="device-health-and-security-settings"></a>Paramètres d’intégrité et de sécurité de l’appareil

- **L’appareil ne doit pas être jailbreaké ou rooté :** si vous activez ce paramètre, les appareils jailbreakés ne sont pas détectés comme conformes.
- **Exiger que les appareils interdisent l’installation des applications provenant de sources inconnues :** vous n’êtes pas obligé de configurer ce paramètre, car les appareils Android for Work limitent systématiquement l’installation à partir de sources inconnues. .  

- **Exiger que le débogage USB soit désactivé** : vous n’êtes pas obligé de configurer ce paramètre, car le débogage USB est déjà désactivé sur les appareils Android for Work.

- **Niveau minimal du correctif de sécurité Android** : utilisez ce paramètre pour spécifier le niveau de correctif Android minimal.  Les appareils qui ne sont pas au moins à ce niveau de correctif sont non conformes. La date doit être spécifiée au format suivant : AAAA-MM-JJ.
- **Exiger l’activation de la protection de l’appareil contre les menaces**: utilisez ce paramètre pour sélectionner l’évaluation des risques de la solution Lookout MTP comme une condition de conformité. Choisissez le niveau de menace maximal autorisé parmi les options suivantes :

  - **Aucun (sécurisé)** : c’est le niveau de sécurité le plus haut. L’appareil ne peut présenter aucune menace. Si des menaces d’un autre niveau sont détectées sur l’appareil, celui-ci est évalué comme non conforme.
  - **Faible** : l’appareil est évalué comme conforme uniquement si les menaces détectées sont de niveau faible. La présence de menaces de niveau supérieur rend l’appareil non conforme.
  - **Moyen** : l’appareil est évalué comme conforme si les menaces détectées sont de niveau faible ou moyen. La présence de menaces de niveau élevé rend l’appareil non conforme.
  - **Élevé** : cette option est la moins sécurisée. Les menaces de tout niveau sont fondamentalement autorisées. Cette option peut être utile uniquement si vous utilisez cette solution pour créer des rapports.

  Pour plus d’informations, consultez [Activer une règle de protection de l’appareil contre les menaces dans la stratégie de conformité](enable-device-threat-protection-rule-in-compliance-policy.md).

## <a name="device-property-settings"></a>Paramètres de propriétés d’appareils
- **Système d’exploitation minimal requis :** quand un appareil ne satisfait pas la condition de version minimale du système d’exploitation, il est signalé comme non conforme.
  Un lien avec des informations sur la mise à niveau s’affiche. L’utilisateur final peut choisir de mettre à niveau son appareil, après quoi il pourra accéder aux ressources de l’entreprise.

- **Version maximale autorisée du système d’exploitation :** quand un appareil utilise une version du système d’exploitation ultérieure à celle spécifiée dans la règle, l’accès aux ressources de l’entreprise est bloqué et l’utilisateur est invité à contacter son administrateur informatique. Jusqu’à ce qu’il y ait une modification de la règle pour autoriser la version du système d’exploitation, cet appareil ne peut pas être utilisé pour accéder aux ressources de l’entreprise.



<!--HONumber=Dec16_HO2-->


