---
title: Exiger l’authentification multifacteur pour l’inscription d’appareils dans Intune
titlesuffix: Microsoft Intune
description: Découvrez comment exiger l’authentification multifacteur dans Azure AD pour l’inscription d’appareils dans Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 01/10/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 94280c73-c05c-4e72-b0dd-a7cb997782f9
ROBOTS: ''
ms.custom: intune-azure
ms.openlocfilehash: 5b2c2bb6e76bd6b2da7ee7c12282c0ff22d7d3e3
ms.sourcegitcommit: 2162ed46d939b4a9b85fa4e7e9943f2fb5948f1e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/20/2018
ms.locfileid: "31617207"
---
# <a name="require-multi-factor-authentication-for-intune-device-enrollments"></a>Exiger l’authentification multifacteur pour l’inscription d’appareils dans Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Intune peut utiliser l’authentification multifacteur (MFA) Azure Active Directory (AD) pour l’inscription d’appareils afin de sécuriser vos ressources d’entreprise.

Elle nécessite au moins deux des méthodes de vérification suivantes :

- Quelque chose que vous connaissez (généralement un mot de passe ou code PIN).
- Quelque chose que vous possédez (un appareil de confiance difficilement copiable, comme un téléphone).
- Quelque chose qui vous représente (biométrie, comme une empreinte digitale).

L’authentification multifacteur est prise en charge sur les appareils iOS, Android, Windows 8.1 ou ultérieur, Windows Phone 8.1 ou Windows 10 Mobile ou ultérieur.

Quand vous activez MFA, les utilisateurs finaux doivent fournir deux formes d’informations d’identification pour inscrire un appareil.

## <a name="configure-intune-to-require-multi-factor-authentication-at-device-enrollment"></a>Configurer Intune pour exiger une authentification multifacteur lors de l’inscription des appareils

Pour exiger l’authentification multifacteur à l’inscription d’un appareil, procédez comme suit :

>[!Important]
>Vous devez avoir un abonnement Azure Active Directory Premium P1 ou supérieur affecté à vos utilisateurs pour implémenter cette stratégie.

>[!Important]
>Ne configurez pas les **règles d’accès basées sur les appareils** pour l’inscription à Microsoft Intune.

1. Connectez-vous à votre [portail Microsoft Azure](https://portal.azure.com) avec vos informations d’identification.
2. Dans le portail, choisissez **Azure Active Directory**.
2. Dans **Azure Active Directory**, choisissez **Gérer** > **Applications d’entreprise**.
3. Dans **Applications d’entreprise**, choisissez **Gérer** > **Toutes les applications**. Vous voyez une liste de toutes les applications Azure que vous gérez.
3. Dans la liste, choisissez **Inscription à Microsoft Intune**.
4. Dans **Inscription à Microsoft Intune**, choisissez **Sécurité** > **Accès conditionnel**.
5. Choisissez **Nouvelle stratégie**.
6. Dans **Nouvelle** stratégie, tapez un nom descriptif pour la stratégie.
7. Dans la section **Affectations**, choisissez **Utilisateurs et groupes**.
8. Dans **Utilisateurs et groupes**, choisissez les utilisateurs ou les groupes qui doivent recevoir cette stratégie, puis choisissez **OK**.
9. Dans la section **Affectations**, choisissez **Applications cloud**.
10. Sous l’onglet **Inclure** des **Applications cloud**, choisissez **Sélectionner les applications**, puis **Sélectionner** > **Inscription à Microsoft Intune**, puis choisissez **OK**.
11. Dans la section **Affectations**, choisissez **Conditions**.
12. Dans **Conditions**, vous n’avez pas besoin de configurer de paramètres pour MFA.
13. Dans la section **Contrôles d’accès**, choisissez **Accorder**.
14. Dans **Accorder**, choisissez **Accorder l’accès**, puis sélectionnez **Exiger l’authentification multifacteur**.
    Ne sélectionnez pas **Exiger que l’appareil soit marqué comme conforme**, car la conformité d’un appareil ne peut pas être évaluée tant que celui-ci n’est pas inscrit.
15. Choisissez **Sélectionner**.
16. Dans **Nouvelle stratégie**, choisissez **Activer la stratégie** > **Activée**, puis choisissez **Créer**.



## <a name="next-steps"></a>Étapes suivantes

Quand les utilisateurs finaux inscrivent leur appareil, ils doivent maintenant s’authentifier avec une deuxième forme d’identification, comme un code PIN, un téléphone ou des données biométriques.
