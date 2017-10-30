---
title: "Paramètres Endpoint Protection Intune pour Windows 10"
titlesuffix: Azure portal
description: "Découvrez les paramètres Intune que vous pouvez utiliser pour contrôler les paramètres Endpoint Protection tels que BitLocker sur les appareils Windows 10."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 08/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3af7c91b-8292-4c7e-8d25-8834fcf3517a
ms.reviewer: ilwu
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 66d13a5a5d4b74cc70696239514875fe0092a164
ms.sourcegitcommit: 4742390f29f84e553e674ea31c88318bda6ab059
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/18/2017
---
# <a name="endpoint-protection-settings-for-windows-10-and-later-in-microsoft-intune"></a>Paramètres Endpoint Protection pour Windows 10 et versions ultérieures dans Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Le profil Endpoint Protection vous permet de contrôler les fonctionnalités de sécurité sur les appareils Windows 10, telles que BitLocker et Windows Defender.

Utilisez les informations de cette rubrique pour découvrir comment créer des profils Endpoint Protection.

> [!Note]
> Ces paramètres ne sont pas pris en charge dans les éditions Famille et Professionnel de Windows 10.

## <a name="create-an-endpoint-protection-profile"></a>Créer un profil Endpoint Protection

1. Connectez-vous au portail Azure.
2. Choisissez **Autres services** > **Surveillance + Gestion** > **Intune**.
3. Dans le panneau **Intune**, choisissez **Configuration de l’appareil**.
2. Dans le panneau **Configuration de l’appareil**, choisissez **Gérer** > **Profils**.
3. Dans le panneau des profils, sélectionnez **Créer un profil**.
4. Dans le panneau **Créer un profil**, entrez un **nom** et une **description** pour le profil de fonctionnalités de l’appareil.
5. Dans la liste déroulante **Plateforme**, sélectionnez **Windows 10 et versions ultérieures**.
6. Dans la liste déroulante **Type de profil**, choisissez **Endpoint Protection**.
7. Dans le panneau **Chiffrement Windows**, configurez les paramètres souhaités. Utilisez les détails de cette rubrique pour vous aider à comprendre le rôle de chaque paramètre. Quand vous avez terminé, cliquez sur **OK**.
8. Revenez au panneau **Créer un profil** et choisissez **Créer**.

Le profil est créé et s’affiche dans le panneau de la liste des profils.

## <a name="windows-defender-smartscreen-settings"></a>Paramètres Windows Defender SmartScreen

- **SmartScreen pour les applications et fichiers** : activez Windows SmartScreen pour l’exécution de fichiers et d’applications.
- **Exécution des fichiers non vérifiée** : empêche l’utilisateur final d’exécuter des fichiers qui n’ont pas été vérifiés par Windows SmartScreen.

## <a name="windows-encryption-settings"></a>Paramètres de chiffrement Windows

### <a name="windows-settings"></a>Paramètres Windows

- **Exiger le chiffrement des appareils (Desktop uniquement)** : si ce paramètre est activé, les utilisateurs sont invités à activer le chiffrement de l’appareil. Ils sont aussi invités à confirmer que le chiffrement d’un autre fournisseur n’a pas été activé. Si le chiffrement Windows est activé alors qu’une autre méthode de chiffrement est active, l’appareil peut devenir instable.
- **Exiger le chiffrement de la carte de stockage (Mobile uniquement)** : activez ce paramètre pour chiffrer toutes les cartes de stockage amovibles utilisées par l’appareil.


### <a name="bitlocker-base-settings"></a>Paramètres de base BitLocker

- **Configurer les méthodes de chiffrement** : activez ce paramètre pour configurer des algorithmes de chiffrement pour le système d’exploitation, les données et les lecteurs amovibles.
    - **Chiffrement pour les lecteurs du système d’exploitation** : choisissez la méthode de chiffrement pour les lecteurs de système d’exploitation. Nous vous recommandons d’utiliser l’algorithme AES-XTS.
    - **Chiffrement pour les lecteurs de données fixes** : choisissez la méthode de chiffrement pour les lecteurs de données fixes (intégrés). Nous vous recommandons d’utiliser l’algorithme AES-XTS.
    - **Chiffrement pour les lecteurs de données amovibles** : choisissez la méthode de chiffrement pour les lecteurs de données amovibles. Si le lecteur amovible est utilisé avec des appareils qui n’exécutent pas Windows 10, nous vous recommandons d’utiliser l’algorithme AES-CBC.


### <a name="bitlocker-os-drive-settings"></a>Paramètres de lecteur du système d’exploitation BitLocker

- **Exiger une authentification supplémentaire au démarrage** -
    - **BitLocker avec puce TPM non compatible** -
    - **Démarrage de TPM** : configurez si la puce TPM est autorisée, non autorisée ou obligatoire.
    - **Code PIN de démarrage de TPM** : configurez si l’utilisation d’un code PIN de démarrage avec la puce TPM est autorisée, non autorisée ou obligatoire.
    - **Clé de démarrage de TPM** : configurez si l’utilisation d’une clé de démarrage avec la puce TPM est autorisée, non autorisée ou obligatoire.
    - **Clé et code PIN de démarrage de TPM** : configurez si l’utilisation d’une clé de démarrage et d’un code PIN avec la puce TPM est autorisée, non autorisée ou obligatoire.
- **Longueur minimale du code PIN** : activez ce paramètre pour configurer une longueur minimale pour le code PIN de démarrage de TPM.
    - **Nombre minimal de caractères** : entrez le nombre de caractères obligatoires pour le code PIN de démarrage (**4**-**20**).
- **Activer la récupération du lecteur du système d’exploitation** : activez ce paramètre pour contrôler comment les lecteurs du système d’exploitation protégés par BitLocker sont récupérés quand les informations de démarrage nécessaires ne sont pas disponibles.
    - **Agent de récupération de données basé sur les certificats** : activez ce paramètre si vous souhaitez que les agents de récupération de données puissent être utilisés avec les lecteurs du système d’exploitation protégés par BitLocker.
    - **Création d’un mot de passe de récupération par l’utilisateur** : configurez si les utilisateurs sont autorisés, non autorisés ou contraints à générer un mot de passe de récupération de 48 chiffres.
    - **Création d’une clé de récupération par l’utilisateur** : configurez si les utilisateurs sont autorisés, non autorisés ou contraints à générer une clé de récupération de 256 bits.
    - **Masquer les options de récupération dans l’Assistant Installation de BitLocker** : activez ce paramètre pour empêcher les utilisateurs de voir ou de changer les options de récupération quand ils activent BitLocker.
    - **Enregistrer les informations de récupération BitLocker dans AD DS** : active le stockage des informations de récupération BitLocker dans Active Directory.
    - **Configurer le stockage des informations de récupération BitLocker dans AD DS** : configurez les parties des informations de récupération de BitLocker qui sont stockées dans Active Directory. Choisissez parmi :
        - **Sauvegarder les mots de passe et les jeux de clés de récupération**
        - **Sauvegarder les mots de passe de récupération uniquement**
    - **Exiger le stockage des informations de récupération dans AD DS avant l’activation de BitLocker** : activez ce paramètre pour empêcher les utilisateurs d’activer BitLocker, sauf si l’appareil est joint au domaine et que les informations de récupération BitLocker sont correctement stockées dans Active Directory.
- **Activer le message et l’URL de récupération préalables au démarrage** : activez ce paramètre pour configurer le message et l’URL qui s’affichent sur l’écran de récupération de clé préalable au démarrage.
    - **Message de récupération préalable au démarrage** : configurez la façon dont le message de récupération préalable au démarrage est présenté aux utilisateurs. Choisissez parmi :
        - **Utiliser le message et l’URL de récupération par défaut**
        - **Utiliser un message et une URL de récupération vides**
        - **Utiliser le message de récupération personnalisé**
        - **Utiliser l’URL de récupération personnalisée**


### <a name="bitlocker-fixed-data-drive-settings"></a>Paramètres BitLocker des lecteurs de données fixes

- **Refuser l’accès en écriture à un lecteur de données fixe non protégé par BitLocker** : si ce paramètre est activé, la protection BitLocker doit être activée sur tous les lecteurs de données fixes, ou intégrés, pour qu’ils soient accessibles en écriture.
- **Activer la récupération des lecteurs fixes** : activez ce paramètre pour contrôler comment les lecteurs fixes protégés par BitLocker sont récupérés quand les informations de démarrage nécessaires ne sont pas disponibles.
    - **Agent de récupération de données** : activez ce paramètre si vous souhaitez que les agents de récupération de données soient utilisés avec les lecteurs fixes protégés par BitLocker.
    - **Création d’un mot de passe de récupération par l’utilisateur** : configurez si les utilisateurs sont autorisés, non autorisés ou contraints à générer un mot de passe de récupération de 48 chiffres.  
    - **Création d’une clé de récupération par l’utilisateur** : configurez si les utilisateurs sont autorisés, non autorisés ou contraints à générer une clé de récupération de 256 bits.
    - **Masquer les options de récupération dans l’Assistant Installation de BitLocker** : activez ce paramètre pour empêcher les utilisateurs de voir ou de changer les options de récupération quand ils activent BitLocker.
    - **Enregistrer les informations de récupération BitLocker dans AD DS** : active le stockage des informations de récupération BitLocker dans Active Directory.
    - **Configurer le stockage des informations de récupération BitLocker dans AD DS** : configurez les parties des informations de récupération de BitLocker qui sont stockées dans Active Directory. Choisissez parmi :
        - **Sauvegarder les mots de passe et les jeux de clés de récupération**
        - **Sauvegarder les mots de passe de récupération uniquement**
    - **Exiger le stockage des informations de récupération dans AD DS avant l’activation de BitLocker** : activez ce paramètre pour empêcher les utilisateurs d’activer BitLocker, sauf si l’appareil est joint au domaine et que les informations de récupération BitLocker ont été correctement stockées dans Active Directory.


### <a name="bitlocker-removable-data-drive-settings"></a>Paramètres BitLocker des lecteurs de données amovibles

- **Refuser l’accès en écriture à un lecteur de données amovible non protégé par BitLocker** : spécifiez si le chiffrement BitLocker est obligatoire pour les lecteurs de stockage amovibles.
    - **Bloquer l’accès en écriture aux appareils configurés dans une autre organisation** : spécifiez si les lecteurs de données amovibles qui appartiennent à une autre organisation sont accessibles en écriture.



## <a name="next-steps"></a>Étapes suivantes

Si vous souhaitez continuer et attribuer ce profil à des groupes, consultez [Guide pratique pour attribuer des profils d’appareils](device-profile-assign.md).
