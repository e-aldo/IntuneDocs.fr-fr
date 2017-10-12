---
title: "Qu’est-ce que l’inscription des appareils Microsoft Intune ?"
titlesuffix: Azure portal
description: "En savoir plus sur l’inscription pour les appareils iOS, Android et Windows."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 10/03/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6f67fcd2-5682-4f9c-8d74-d4ab69dc978c
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: bef73c81d285a6d320cd92b055ff2b5592a55af4
ms.sourcegitcommit: 001577b700f634da2fec0b44af2a378150d1f7ac
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/04/2017
---
# <a name="what-is-device-enrollment"></a>Qu’est-ce que l’inscription d’appareils ?
[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Cette rubrique décrit l’inscription et répertorie différentes façons d’inscrire des appareils mobiles dans la gestion Intune.

Vous inscrivez des appareils dans Intune afin de pouvoir gérer ces appareils. Nous appelons cette fonctionnalité « gestion des appareils mobiles (MDM) » dans la documentation Intune . Lorsque les appareils sont inscrits dans Intune, ils se voient remettre un certificat MDM, que les appareils utilisent ensuite pour communiquer avec le service Intune.

La façon dont vous inscrivez vos appareils dépend du type d’appareil, de son propriétaire et du niveau de gestion souhaité. L’inscription BYOD (« Bring your own device ») permet aux utilisateurs d’inscrire leurs téléphones, tablettes ou PC personnels. Vous pouvez gérer l’inscription des appareils d’entreprise (COD) de plusieurs façons : inscription automatique, appareils partagés ou inscription pré-autorisée.

Si vous utilisez Exchange ActiveSync (soit localement, soit hébergé dans le cloud), vous pouvez choisir la gestion Intune simple sans inscription (plus d’informations prochainement). Vous pouvez gérer les PC Windows en tant qu’appareils mobiles, ce qui est la méthode recommandée décrite ci-après.


## <a name="overview-of-device-enrollment-methods"></a>Présentation des méthodes d’inscription des appareils

Le tableau suivant offre une vue d’ensemble des méthodes d’inscription Intune avec leurs fonctions et spécifications décrites ci-dessous.

**Légende**

- **Réinitialisation requise** - Les appareils sont réinitialisés aux paramètres d’usine lors de l’inscription.
- **Affinité utilisateur** : associe les appareils à des utilisateurs. Pour plus d’informations, consultez [Affinité utilisateur](device-enrollment-program-enroll-ios.md).
- **Verrouillé** - Empêche les utilisateurs de désinscrire des appareils.

**Méthodes d’inscription iOS**

| **Méthode** |  **Réinitialisation requise** |    **Affinité utilisateur**   |   **Verrouillé** | **Détails** |
|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#byod)** | Non|    Oui |   Non | [Plus d’informations](./apple-mdm-push-certificate-get.md)|
|**[GESTIONNAIRE D’INSCRIPTION D’APPAREIL](#dem)**|   Non |Non |Non  | [Plus d’informations](./device-enrollment-program-enroll-ios.md)|
|**[DEP](#dep)**|   Oui |   Facultatif |  Facultatif|[Plus d’informations](./device-enrollment-program-enroll-ios.md)|
|**[USB-SA](#usb-sa)**| Oui |   Facultatif |  Non| [Plus d’informations](./apple-configurator-setup-assistant-enroll-ios.md)|
|**[USB-Direct](#usb-direct)**| Non |    Non  | Non|[Plus d’informations](./apple-configurator-direct-enroll-ios.md)|

**Méthodes d’inscription de Windows**

| **Méthode** |  **Réinitialisation requise** |    **Affinité utilisateur**   |   **Verrouillé** | **Détails**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#byod)** | Non |   Oui |   Non | [Plus d’informations](windows-enroll.md)|
|**[GESTIONNAIRE D’INSCRIPTION D’APPAREIL](#dem)**|   Non |Non |Non  |[Plus d’informations](device-enrollment-manager-enroll.md)|
|**Inscription automatique** | Non |Oui |Non | [Plus d’informations](./windows-enroll.md#enable-windows-10-automatic-enrollment)|
|**Inscription en bloc** |Non |Non |Non | [Plus d’informations](./windows-bulk-enroll.md) |

**Méthodes d’inscription d’Android**

| **Méthode** |  **Réinitialisation requise** |    **Affinité utilisateur**   |   **Verrouillé** | **Détails**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#byod)** | Non|    Oui |   Non | [Plus d’informations](./android-enroll.md)|
|**[GESTIONNAIRE D’INSCRIPTION D’APPAREIL](#dem)**|   Non |Non |Non  |[Plus d’informations](./device-enrollment-program-enroll-ios.md)|
|**Android for Work**| Non | Oui | Non| [Plus d’informations](./android-enroll.md#enable-enrollment-of-android-for-work-devices) |


## <a name="byod"></a>BYOD
Les utilisateurs d’appareils personnels installent et exécutent l’application Portail d’entreprise pour inscrire leurs propres appareils. Ce programme permet aux utilisateurs d’accéder aux ressources de l’entreprise, comme la messagerie électronique.

## <a name="corporate-owned-devices"></a>Appareils d’entreprise
Voici des scénarios d’inscription d’appareils d’entreprise (COD). Vous pouvez inscrire les appareils iOS directement par le biais des outils fournis par Apple. Tous les types d’appareils peuvent être inscrits par un administrateur ou un gestionnaire à l’aide du Gestionnaire d’inscription d’appareil. Les appareils dotés d’un numéro IMEI peuvent également être identifiés et référencés comme appartenant à l’entreprise pour activer des scénarios COD.

### <a name="dem"></a>Gestionnaire d’inscription d’appareil
Le gestionnaire d’inscription d’appareil est un compte d’utilisateur spécial permettant d’inscrire et de gérer plusieurs appareils d’entreprise. Les responsables peuvent installer le Portail d’entreprise et inscrire de nombreux appareils sans utilisateur. En savoir plus sur le [gestionnaire d’inscription d’appareil](./device-enrollment-manager-enroll.md).

### <a name="dep"></a>DEP
Le programme d’inscription d’appareils Apple (ou DEP) vous permet de créer et déployer une stratégie « à distance » sur des appareils iOS achetés et gérés avec DEP. L’appareil est inscrit quand l’utilisateur le démarre pour la première fois et exécute l’Assistant d’installation iOS. Cette méthode prend en charge le mode iOS supervisé, qui permet la configuration d’un appareil avec les fonctionnalités suivantes :

- Verrouillage d’application (Mode Application unique) 
- Proxy HTTP global 
- Ignorer le verrouillage d’activation 
- Mode Application unique autonome 
- Filtrage de contenu web 
- Définition de l’écran d’arrière-plan et de verrouillage 
- Envoi (push) d’application en mode silencieux 
- VPN AlwaysOn 
- Autoriser l’installation d’applications gérées exclusivement 
- iBookstore 
- iMessages 
- Centre de jeux 
- AirDrop 
- AirPlay 
- Appairage d’hôtes 
- Synchronisation cloud 
- Recherche Spotlight 
- Handoff 
- Effacer l’appareil 
- Interface utilisateur - Restrictions 
- Installation de profils de configuration par l’interface utilisateur 
- Actualités 
- Raccourcis clavier 
- Modifications du code secret 
- Changements du nom de l’appareil 
- Changements de papier peint 
- Téléchargements automatiques d’applications 
- Changements apportés à l’approbation d’applications d’entreprise 
- Apple Music 
- Mail Drop 
- Appairage avec Apple Watch 

> [!NOTE]
> Apple a confirmé que certains paramètres passeront en mode supervisé uniquement en 2018. Nous recommandons de prendre ceci en considération lors de l’utilisation de ces paramètres, au lieu d’attendre qu’Apple les migre en mode supervisé uniquement :
> - Installation d’applications
> - Suppression d’applications
> - FaceTime
> - Safari
> - iTunes
> - Contenu explicite
> - Documents et données iCloud
> - Jeux multijoueur
> - Ajouter des amis du centre de jeux

Pour en savoir plus sur l’inscription DEP iOS :

- [Choisir comment inscrire des appareils iOS](ios-enroll.md)
- [Inscrire des appareils iOS à l’aide du programme d’inscription d’appareils](device-enrollment-program-enroll-ios.md)

### <a name="usb-sa"></a>USB-SA
Les administrateurs utilisent Apple Configurator, via un port USB, pour préparer manuellement chaque appareil d’entreprise à l’inscription à l’aide de l’Assistant Configuration. Ils créent un profil d’inscription et l’exportent vers Apple Configurator. Lorsque les utilisateurs reçoivent leurs appareils, ils sont invités à exécuter l’Assistant Configuration pour inscrire leurs appareils. Cette méthode prend en charge le mode **iOS supervisé**, qui active les fonctionnalités suivantes :
  - Inscription verrouillée
  - Mode plein écran et autres configurations et restrictions avancées

Découvrez l’inscription d’Apple Configurator iOS avec l’Assistant Configuration :

- [Choisir la méthode d’inscription des appareils iOS](enrollment-method-choose-ios.md)
- [Inscrire des appareils iOS avec Configurator et l’Assistant Configuration](apple-configurator-setup-assistant-enroll-ios.md)

### <a name="usb-direct"></a>USB-Direct
Pour les inscriptions directes, l’administrateur doit inscrire manuellement chaque appareil en créant une stratégie d’inscription et en l’exportant vers Apple Configurator. Les appareils d’entreprise connectés par USB sont inscrits directement et aucune réinitialisation aux paramètres d’usine n’est nécessaire. Les appareils sont gérés comme des appareils sans utilisateur. Ils ne sont pas verrouillés ni supervisés et ne peuvent pas prendre en charge l’accès conditionnel, la détection de jailbreak ou la gestion des applications mobiles.

Pour en savoir plus sur l’inscription d’appareils iOS, consultez :

- [Choisir la méthode d’inscription des appareils iOS](enrollment-method-choose-ios.md)
- [Inscrire des appareils iOS avec Apple Configurator et l’inscription directe](apple-configurator-direct-enroll-ios.md)

## <a name="mobile-device-management-with-exchange-activesync-and-intune"></a>Gestion des appareils mobiles à l’aide d’Exchange ActiveSync et d’Intune
Les appareils mobiles qui ne sont pas inscrits mais qui se connectent à Exchange ActiveSync (EAS) peuvent être gérés par Intune à l’aide de la stratégie de gestion des appareils mobiles EAS. Intune utilise un connecteur Exchange pour communiquer avec EAS, localement ou hébergé dans le cloud. Plus d’informations seront bientôt disponibles.

## <a name="mobile-device-cleanup-after-mdm-certificate-expiration"></a>Nettoyage de l’appareil mobile après expiration du certificat MDM

Le certificat MDM est renouvelé automatiquement lorsque les appareils mobiles communiquent avec le service Intune. Si des appareils mobiles sont réinitialisés ou ne parviennent pas à communiquer avec le service Intune pendant un certain temps, le certificat MDM n’est pas renouvelé. L’appareil est supprimé du portail Azure 180 jours après l’expiration du certificat MDM.
