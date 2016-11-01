---
title: "Paramètres de stratégie de conformité pour les appareils Android | Microsoft Intune"
description: "Cette rubrique décrit les paramètres de stratégie de conformité d’appareil pour les appareils Android."
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 07/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e721c5c7-9678-4f3b-81d4-564da5efd337
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: e24de6814d9e01c64768f425e961a7822f4b27a1
ms.openlocfilehash: 5f02618da6fb3c538ad131fe8abaf35a6be6e177


---


# Paramètres de stratégie de conformité pour les appareils Android dans Microsoft Intune

Les paramètres de stratégie décrits dans cette rubrique s’appliquent aux appareils exécutant Android 4.0 et versions ultérieures ou Samsung KNOX 4.0 et versions ultérieures.

Si vous recherchez des informations sur d’autres plateformes, sélectionnez un des éléments suivants :
> [!div class="op_single_selector"]
- [Paramètres de stratégie de conformité pour les appareils iOS](ios-compliance-policy-settings-in-microsoft-intune.md)
- [Paramètres de stratégie de conformité pour les appareils Windows](windows-compliance-policy-settings-in-microsoft-intune.md)

## Paramètres de sécurité système
### Mot de passe
- **Exiger un mot de passe pour déverrouiller des appareils mobiles** : définissez cette option sur **Oui** pour obliger les utilisateurs à entrer un mot de passe pour accéder à leur appareil.

-  **Longueur minimale du mot de passe** : spécifie le nombre minimal de chiffres ou de caractères devant figurer dans le mot de passe de l’utilisateur.

- **Qualité du mot de passe :** ce paramètre détecte si les critères de mot de passe que vous spécifiez sont configurés sur l’appareil. Activez ce paramètre pour que les utilisateurs satisfassent à certains critères de mot de passe pour les appareils Android. Choisissez parmi :

  -   **Sécurité biométrique faible**
  -   **Obligatoire**
  -   **Au moins numérique**
  -   **Au moins alphabétique**
  -   **Au moins alphanumérique**
  -   **Alphanumérique avec symboles**

- **Minutes d’inactivité avant demande du mot de passe** : spécifiez la durée d’inactivité au terme de laquelle l’utilisateur doit entrer à nouveau son mot de passe.

- **Expiration du mot de passe (jours)** : sélectionnez le nombre de jours avant que le mot de passe de l’utilisateur n’expire et qu’il ne doive en créer un autre.

- **Mémoriser l’historique des mots de passe** : utilisez ce paramètre avec le paramètre **Empêcher la réutilisation des mots de passe précédents** pour empêcher l’utilisateur de créer des mots de passe qui ont déjà été utilisés.

- **Empêcher la réutilisation des mots de passe précédents** : si vous avez sélectionné l’option **Mémoriser l’historique des mots de passe**, spécifiez le nombre de mots de passe précédemment utilisés qui ne peuvent pas être réutilisés.

- **Exiger un mot de passe quand l’appareil quitte un état inactif** : utilisez ce paramètre conjointement avec le paramètre **Minutes d’inactivité avant demande du mot de passe**. L’utilisateur est invité à entrer un mot de passe pour accéder à un appareil qui a été inactif pendant la durée spécifiée par le paramètre **Minutes d’inactivité avant demande du mot de passe**.

### Chiffrement
- **Exiger le chiffrement sur l’appareil mobile** : affectez la valeur **Oui** pour exiger que les appareils soient chiffrés pour pouvoir se connecter aux ressources. Les appareils sont chiffrés quand vous choisissez le paramètre **Exiger un mot de passe pour déverrouiller des appareils mobiles**.

## Paramètres d’intégrité et de sécurité de l’appareil

- **L’appareil ne doit pas être jailbreaké ou rooté** : si vous activez ce paramètre, les appareils jailbreakés ne sont pas détectés comme conformes.
- **Exiger que les appareils interdisent l’installation des applications provenant de sources inconnues (Android 4.0+)** : pour bloquer les appareils qui ont **Sécurité** > **Sources inconnues** activé, activez ce paramètre et définissez-le sur **Oui**.  
>[!IMPORTANT]
>Pour les applications en chargement indépendant, le paramètre **Sources inconnues** doit être activé. Appliquez cette stratégie de conformité uniquement si vous n’effectuez aucun chargement indépendant d’applications Android sur les appareils.

- **Exiger que le débogage USB soit désactivé (Android 4.2 ou ultérieur)** : ce paramètre spécifie si la détection de l’option de débogage USB est activée sur l’appareil.
- **Exiger que « Rechercher les menaces de sécurité sur l'appareil » soit activé sur les appareils (Android 4.2-4.4)** : ce paramètre spécifie si la fonctionnalité **Vérifier les applications** est activée sur l’appareil.
- **Niveau minimal du correctif de sécurité Android (Android 6.0 ou ultérieur)** : utilisez ce paramètre pour spécifier le niveau de correctif Android minimal. Les appareils qui ne sont pas au moins à ce niveau de correctif sont non conformes. La date doit être spécifiée dans le format AAAA-MM-JJ.
- **Exiger l’activation de la protection de l’appareil contre les menaces**: utilisez ce paramètre pour sélectionner l’évaluation des risques de la solution Lookout MTP comme une condition de conformité. Choisissez le niveau de menace maximal autorisé parmi les options suivantes :

  - **Aucun (sécurisé)** : c’est le niveau de sécurité le plus haut. L’appareil ne peut présenter aucune menace. Si des menaces d’un autre niveau sont détectées sur l’appareil, celui-ci est évalué comme non conforme.
  - **Faible** : l’appareil est évalué comme conforme uniquement si les menaces détectées sont de niveau faible. La présence de menaces de niveau supérieur rend l’appareil non conforme.
  - **Moyen** : l’appareil est évalué comme conforme si les menaces détectées sont de niveau faible ou moyen. La présence de menaces de niveau élevé rend l’appareil non conforme.
  - **Élevé** : cette option est la moins sécurisée. Essentiellement, elle autorise tous les niveaux de menace. Elle peut s’avérer utile si vous ne recourez à cette solution qu’à des fins de création de rapport.

  Pour plus d’informations, consultez [Activer une règle de protection de l’appareil contre les menaces dans la stratégie de conformité](enable-device-threat-protection-rule-in-compliance-policy.md).

## Paramètres de propriétés d’appareils
- **Système d’exploitation minimal requis** : quand un appareil ne satisfait pas la condition de version minimale du système d’exploitation, il est signalé comme non conforme.
  Un lien avec des informations sur la mise à niveau s’affiche. L’utilisateur peut choisir de mettre à niveau son appareil, après quoi il pourra accéder aux ressources de l’entreprise.

- **Version maximale autorisée du système d’exploitation** : quand un appareil utilise une version du système d’exploitation ultérieure à celle spécifiée dans la règle, l’accès aux ressources de l’entreprise est bloqué et l’utilisateur est invité à contacter son administrateur informatique. Jusqu’à ce qu’il y ait une modification des règles pour autoriser la version du système d’exploitation, cet appareil ne peut pas être utilisé pour accéder aux ressources de l’entreprise.



<!--HONumber=Oct16_HO3-->


