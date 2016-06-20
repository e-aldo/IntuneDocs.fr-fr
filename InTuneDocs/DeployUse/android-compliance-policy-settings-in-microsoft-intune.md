---
# required metadata

title: Paramètres de stratégie de conformité pour les appareils Android | Microsoft Intune
description:
keywords:
author: karthikaraman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: e721c5c7-9678-4f3b-81d4-564da5efd337

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: chrisgre
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Paramètres de stratégie de conformité pour les appareils Android dans Microsoft Intune

Les paramètres de stratégie décrits dans cette rubrique s’appliquent aux appareils exécutant Android 4.0 et versions ultérieures ou Samsung KNOX 4.0 et versions ultérieures.

Si vous recherchez des informations sur d’autres plateformes, sélectionnez l’un des éléments suivants :
> [!div class="op_single_selector"]
- [Paramètres de stratégie de conformité pour les appareils iOS](ios-compliance-policy-settings-in-microsoft-intune.md)
- [Paramètres de stratégie de conformité pour les appareils Windows](windows-compliance-policy-settings-in-microsoft-intune.md)

## Paramètres de sécurité système
### Mot de passe
- **Exiger un mot de passe pour déverrouiller des appareils mobiles :** définissez cette option sur **Oui** pour obliger les utilisateurs à entrer un mot de passe pour accéder à leur appareil.

-  **Longueur minimale du mot de passe** : spécifie le nombre minimal de chiffres ou de caractères devant figurer dans le mot de passe de l’utilisateur.

- **Qualité du mot de passe :** activez ce paramètre pour configurer des exigences de mot de passe pour les appareils Android. Choisissez parmi :
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

### Chiffrement
- **Exiger le chiffrement sur l’appareil mobile :** affectez la valeur **Oui** pour exiger que les appareils soient chiffrés pour pouvoir se connecter aux ressources. Les appareils sont chiffrés quand vous configurez le paramètre **Exiger un mot de passe pour déverrouiller des appareils mobiles**.

## Paramètres d’intégrité des appareils

- **L’appareil ne doit pas être jailbroken ou rooté :** si vous activez ce paramètre, les appareils jailbroken ne sont pas détectés comme conformes.

## Paramètres de propriétés d’appareils
- **Système d’exploitation minimal requis :** quand un appareil ne satisfait pas la condition de version minimale du système d’exploitation, il est signalé comme non conforme.
  Un lien avec des informations sur la mise à niveau s’affiche. L’utilisateur final peut choisir de mettre à niveau son appareil, après quoi il pourra accéder aux ressources de l’entreprise.

- **Version maximale autorisée du système d’exploitation :** quand un appareil utilise une version du système d’exploitation ultérieure à celle spécifiée dans la règle, l’accès aux ressources de l’entreprise est bloqué et l’utilisateur est invité à contacter son administrateur informatique. Jusqu’à ce qu’il y ait une modification de la règle pour autoriser la version du système d’exploitation, cet appareil ne peut pas être utilisé pour accéder aux ressources de l’entreprise.


<!--HONumber=Jun16_HO2-->


