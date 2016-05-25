---
# required metadata

title: Paramètres de stratégie de conformité pour les appareils iOS | Microsoft Intune
description:
keywords:
author: karthikaraman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 4a59d24f-ed58-49b1-b874-b2d4aea3ec76

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Paramètres de stratégie de conformité pour les appareils iOS

Les paramètres de stratégie décrits dans cette rubrique s’appliquent aux appareils exécutant iOS 6 et ultérieur.

Si vous recherchez des informations sur d’autres plateformes, sélectionnez un des éléments suivants :
> [!div class="op_single_selector"]
- [Paramètres de stratégie de conformité pour les appareils Android](android-compliance-policy-settings-in-microsoft-intune.md)
- [Paramètres de stratégie de conformité pour les appareils Windows](windows-compliance-policy-settings-in-microsoft-intune.md)

## Paramètres de sécurité système
### Mot de passe
- **Exiger un mot de passe pour déverrouiller des appareils mobiles :** définissez ceci sur **Oui** pour obliger les utilisateurs à entrer un mot de passe pour
  pouvoir accéder à leur appareil. Les appareils iOS utilisant un mot de passe sont chiffrés.

- **Autoriser les mots de passe simples :** définissez ceci
   sur **Oui** pour permettre aux utilisateurs de créer des mots de passe simples,
   comme « **1234** » ou « **1111** ».

-  **Longueur minimale du mot de passe :**
  Spécifiez le nombre minimal de chiffres ou de caractères
  que le mot de passe de l’utilisateur doit contenir.
- **Type de mot de passe requis :** spécifiez si les utilisateurs doivent créer
un mot de passe **alphanumérique** ou **numérique**.

- **Nombre minimum de jeux de caractères :** si vous définissez **Type de mot de passe requis** sur
**Alphanumériques**, utilisez ce paramètre pour spécifier le nombre minimal de
jeux de caractères que le mot de passe doit contenir. Les quatre jeux de caractères sont :
  -   Lettres minuscules
  -   Lettres majuscules
  -   Symboles
  -   Nombres

  Le fait de définir un nombre plus élevé pour ce paramètre oblige les utilisateurs à créer des mots de passe plus complexes.

  Pour les appareils iOS, ce paramètre indique le nombre de caractères spéciaux (par exemple **!****#**, **&amp;**) qui doivent être inclus dans le mot de passe.
- **Minutes d’inactivité avant demande du mot de passe :** spécifiez la durée d’inactivité au terme de laquelle l’utilisateur doit entrer à nouveau son mot de passe.

- **Expiration du mot de passe (jours) :** choisissez le nombre de jours avant que le mot de passe de l’utilisateur expire
et qu’il doive en créer un autre.

- **Mémoriser l’historique des mots de passe :** utilisez ce paramètre conjointement avec le paramètre **Empêcher la réutilisation des mots de passe précédents** pour empêcher l’utilisateur de
créer des mots de passe qui ont déjà été utilisés.

- **Empêcher la réutilisation des mots de passe précédents :** si **Mémoriser l’historique des mots de passe** est sélectionné, spécifiez le
nombre de mots de passe précédemment utilisés qui ne peuvent pas être réutilisés.

- **Exiger un mot de passe quand l’appareil quitte un état inactif :**
Ce paramètre doit être utilisé conjointement avec le paramètre **Minutes d’inactivité avant demande du mot de passe**. Les utilisateurs finaux sont invités à entrer un mot de passe pour accéder à un appareil qui a été inactif pendant la durée spécifiée par
le paramètre **Minutes d’inactivité avant demande du mot de passe**.

### Profil de messagerie
- **Le compte de messagerie doit être géré par Intune :** quand cette option est définie sur **Oui**, l’appareil doit utiliser la messagerie non conforme qui y est déployée. L’appareil est considéré comme non conforme dans les situations suivantes :
  - Le profil de messagerie doit également être déployé sur le même groupe d’utilisateurs en tant que groupe d’utilisateurs ciblé par la stratégie de conformité, sinon les appareils des utilisateurs seront considérés comme non conformes.
  - L’appareil est considéré comme non conforme si l’utilisateur a déjà configuré sur l’appareil un compte de messagerie qui correspond au profil de messagerie Intune déployé sur l’appareil. Intune ne peut pas remplacer le profil configuré par l’utilisateur et ne peut donc
  pas le gérer. Pour assurer la conformité, l’utilisateur doit supprimer les
  paramètres de messagerie existants : Intune peut alors installer le
  profil de messagerie géré.


- **Sélectionnez le profil de messagerie géré par Intune :**
     Si le paramètre **Le compte de messagerie doit être géré par Intune** est sélectionné,
     choisissez **Sélectionner** pour spécifier le profil de messagerie Intune. Le profil de messagerie doit être présent sur l'appareil.

     Pour plus d’informations sur les profils de messagerie, consultez [Configurer l’accès
     à la messagerie d’entreprise en utilisant des profils de messagerie avec Microsoft Intune](configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune.md).

## Paramètres d’intégrité des appareils

- **L’appareil ne doit pas être jailbroken ou rooté :** si vous activez ce paramètre,
les appareils jailbroken ne sont pas considérés comme étant conformes.

##  Propriétés des appareils
- **Système d’exploitation minimal requis :** quand un appareil n’a pas la version minimale requise
du système d’exploitation, il est considéré comme étant non conforme.
Un lien avec des informations sur la mise à niveau s’affiche. L’utilisateur final peut choisir de mettre à niveau son appareil. Une fois cette opération effectuée, il peut normalement accéder aux ressources de l’entreprise.

- **Version maximale autorisée du système d’exploitation :** quand un appareil utilise une
version du système d’exploitation ultérieure à celle spécifiée dans la règle, l’accès aux ressources de l’entreprise est bloqué et l’utilisateur est invité à contacter son administrateur informatique. Jusqu’à ce qu’il y ait une modification de la règle pour autoriser la version du système d’exploitation, cet appareil ne peut pas être utilisé pour accéder aux ressources de l’entreprise.


<!--HONumber=May16_HO1-->


