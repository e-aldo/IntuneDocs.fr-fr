---
title: Créer une stratégie de conformité des appareils macOS dans Microsoft Intune - Azure | Microsoft Docs
description: Créez ou configurez une stratégie de conformité des appareils Microsoft Intune pour permettre aux appareils macOS d’utiliser la protection de l’intégrité du système, définissez la version minimale et maximale du système d’exploitation, choisissez les exigences relatives aux mots de passe et chiffrez le stockage de données.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/16/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: a797c68ca43a6173a4bac70e914d3f763ce5e6d0
ms.sourcegitcommit: 2773f388f50654366197a95a6838306f70fc18b8
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/18/2018
---
# <a name="add-a-device-compliance-policy-for-macos-devices-with-intune"></a>Ajouter une stratégie de conformité des appareils pour les appareils macOS avec Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Une stratégie de conformité des appareils macOS avec Intune détermine les règles et les paramètres que les appareils macOS doivent respecter pour être conformes. Quand vous utilisez des stratégies de conformité de l’appareil avec l’accès conditionnel, vous pouvez autoriser ou bloquer l’accès aux ressources d’entreprise. Vous pouvez également obtenir des rapports sur les appareils et prendre des mesures en cas de non-conformité. Des stratégies de conformité de l’appareil pour chaque plateforme peuvent être créées dans le portail Intune Azure. Pour en savoir plus sur les stratégies de conformité et sur les prérequis, consultez [Bien démarrer avec la conformité des appareils](device-compliance-get-started.md).

Le tableau suivant décrit la gestion des paramètres non conformes quand une stratégie de conformité est utilisée avec une stratégie d’accès conditionnel :

---------------------------

| Paramètre de stratégie | macOS 10.11 et ultérieur |
| --- | --- |
| **Configuration d’un code confidentiel ou mot de passe** | Corrigé |   
| **Chiffrement de l’appareil** | Corrigé (en définissant le code confidentiel) |
| **Profil de messagerie** | En quarantaine |
|**Version minimale du système d’exploitation** | En quarantaine |
| **Version maximale du système d’exploitation** | En quarantaine |

---------------------------

**Corrigé** : le système d’exploitation de l’appareil applique la conformité. Par exemple, l’utilisateur est obligé de définir un code PIN.

**En quarantaine** : le système d’exploitation de l’appareil n’applique pas la conformité. (Par exemple, les appareils Android n’obligent pas l’utilisateur à chiffrer l’appareil.) Quand l’appareil n’est pas conforme, les actions suivantes se produisent :

- L’appareil est bloqué si une stratégie d’accès conditionnel s’applique à l’utilisateur.
- Le portail d’entreprise informe l’utilisateur des problèmes de conformité.

## <a name="create-a-device-compliance-policy"></a>Créer une stratégie de conformité des appareils

[!INCLUDE [new-device-compliance-policy](./includes/new-device-compliance-policy.md)]
5. Pour l’option **Plateforme**, sélectionnez **macOS**. Choisissez **Paramètres Configurer**, puis entrez les paramètres nécessaires pour les options **Intégrité de l’appareil**, **Propriétés de l’appareil** et **Sécurité du système**. Une fois que vous avez fini, sélectionnez **OK**, puis **Créer**.

## <a name="device-health"></a>Intégrité de l’appareil

- **Exiger la protection de l’intégrité du système** : vous pouvez **exiger** que la [Protection de l’intégrité du système](https://support.apple.com/HT204899) soit activée sur les appareils macOS.

## <a name="device-properties"></a>Propriétés des appareils

- **Version minimale du système d’exploitation** : quand un appareil ne répond pas aux exigences minimales relatives à la version du système d’exploitation, il est signalé comme non conforme. Un lien avec des informations sur la mise à niveau apparaît. L’utilisateur final peut choisir de mettre à niveau son appareil pour pouvoir accéder aux ressources de l’entreprise.
- **Version maximale du système d’exploitation** : quand un appareil utilise une version du système d’exploitation postérieure à la version spécifiée dans la règle, l’accès aux ressources de l’entreprise est bloqué. L’utilisateur est invité à contacter son administrateur informatique. Tant que la règle autorisant la version du système d’exploitation reste inchangée, cet appareil ne peut pas accéder aux ressources de l’entreprise.

## <a name="system-security-settings"></a>Paramètres de sécurité système

### <a name="password"></a>Mot de passe

- **Exiger un mot de passe pour déverrouiller les appareils mobiles** : permet d’**obliger** les utilisateurs à entrer un mot de passe pour pouvoir accéder à leur appareil.
- **Mots de passe simples** : choisissez **Bloquer** pour que les utilisateurs ne puissent pas créer de mots de passe simples, par exemple **1234** ou **1111**. Choisissez **Non configuré** pour permettre aux utilisateurs de créer des mots de passe tels que **1234** ou **1111**.
- **Longueur minimale du mot de passe** : entrez le nombre minimal de chiffres ou de caractères du mot de passe.
- **Type de mot de passe** : choisissez si un mot de passe doit comporter uniquement des caractères **numériques**, ou s’il doit comporter un mélange de chiffres et d’autres caractères (**alphanumériques**).
- **Nombre de caractères non alphanumériques dans le mot de passe** : entrez le nombre minimal de caractères spéciaux (&, #, %, !, etc.) à inclure dans le mot de passe.

    Si vous définissez un nombre plus élevé, l’utilisateur doit créer un mot de passe plus complexe.

- **Nombre maximal de minutes d’inactivité avant demande du mot de passe** : entrez la durée d’inactivité après laquelle l’utilisateur doit rentrer son mot de passe.
- **Expiration du mot de passe (jours)**  : sélectionnez le nombre de jours avant l’expiration du mot de passe de l’utilisateur et l’obligation d’en créer un autre.
- **Nombre de mots de passe précédents avant d’autoriser leur réutilisation** : entrez le nombre d’anciens mots de passe qui ne peuvent pas être réutilisés.

    > [!IMPORTANT]
    > Quand les exigences de mot de passe sont changées sur un appareil macOS, elles n’entrent pas en vigueur tant que l’utilisateur ne change pas son mot de passe. Par exemple, si vous fixez la longueur minimale du mot de passe à huit chiffres et si l’appareil macOS a un mot de passe de six chiffres, il reste conforme jusqu’à ce que l’utilisateur mette à jour son mot de passe.

### <a name="encryption"></a>Chiffrement

- **Chiffrement du stockage de données sur l’appareil** : choisissez **Exiger** pour chiffrer le stockage des données sur vos appareils.

## <a name="assign-user-groups"></a>Affectation de groupes d’utilisateurs

1. Choisissez une stratégie que vous avez configurée. Les stratégies existantes se trouvent dans **Conformité de l’appareil** > **Stratégies**.
2. Choisissez la stratégie, puis **Affectations**. Vous pouvez inclure ou exclure des groupes de sécurité Azure AD (Azure Active Directory).
3. Choisissez **Groupes sélectionnés** pour voir vos groupes de sécurité Azure AD. Sélectionnez les groupes d’utilisateurs auxquels vous souhaitez appliquer cette stratégie, puis choisissez **Enregistrer** pour déployer la stratégie auprès des utilisateurs.

> [!TIP]
> Par défaut, les appareils vérifient la conformité toutes les huit heures. Toutefois, les utilisateurs peuvent forcer ce processus via l’application Portail d’entreprise Intune.

Vous avez appliqué la stratégie à des utilisateurs. La conformité des appareils utilisés par les utilisateurs ciblés par la stratégie est évaluée.

## <a name="next-steps"></a>Étapes suivantes
[Automatiser l’envoi d’un e-mail et ajouter des actions pour les appareils non conformes](actions-for-noncompliance.md)  
[Surveiller les stratégies de conformité d’appareils Intune](compliance-policy-monitor.md)