---
title: "Inscrire des appareils iOS avec Apple Configurator et l’inscription directe"
titleSuffix: Intune Azure preview
description: "Version préliminaire d’Intune Azure : découvrez comment utiliser Apple Configurator pour inscrire des appareils iOS d’entreprise à l’aide de l’inscription directe."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e6c0a430-1851-4108-812a-87e0fc2623b5
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: b464a07e701797d39b7f9f50d1854a9a2682ac8e
ms.openlocfilehash: 3208e964f2676ebcc1e54e29f039c4965c20238f
ms.lasthandoff: 03/01/2017


---

# <a name="enroll-ios-devices-with-apple-configurator-and-direct-enrollment"></a>Inscrire des appareils iOS avec Apple Configurator et l’inscription directe 

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Intune prend en charge l’inscription d’appareils iOS d’entreprise à l’aide d’[Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) s’exécutant sur un ordinateur Mac. Ce processus ne réinitialise pas l’appareil aux paramètres d’usine et l’inscrit avec une stratégie prédéfinie. Cette méthode est destinée aux appareils n’ayant **aucune affinité utilisateur** et implique de connecter l’appareil iOS à un ordinateur Mac via une connexion USB pour configurer l’inscription d’entreprise.

>[!NOTE]
>Cette méthode d’inscription ne peut pas être utilisée avec celle du [gestionnaire d’inscription d’appareil](enroll-devices-using-device-enrollment-manager.md).

Quand vous inscrivez directement des appareils iOS, vous pouvez inscrire un appareil sans obtenir son numéro de série. Vous pouvez également nommer l’appareil à des fins d’identification avant qu’Intune capture son nom lors de l’inscription. L’application Portail d’entreprise n’est pas prise en charge pour les appareils inscrits directement. Cette aide suppose que vous utilisez Apple Configurator 2.0 sur un ordinateur Mac.

Les autres méthodes d’inscription d’appareils iOS sont décrites dans [Choisir comment inscrire des appareils iOS dans Intune](choose-ios-enrollment-method.md).


## <a name="prerequisites"></a>Conditions préalables

Avant de configurer l’inscription des appareils iOS, effectuez les préparatifs suivants :

- [Configurer des domaines](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-2)
- [Configurer l’autorité MDM](set-mdm-authority.md)
- [Créer des groupes](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-5)
- [Configurer le portail d’entreprise](/intune-azure/manage-apps/company-portal-app)
- Attribuer des licences utilisateur dans le [portail Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Obtenir un certificat Push MDM Apple](get-an-apple-mdm-push-certificate.md)
- Assurez-vous d’avoir un accès physique aux appareils iOS
- Obtenez les numéros de série des appareils (consultez [Comment obtenir un numéro de série iOS](https://support.apple.com//HT204308))
- Disposer de câbles de connexion USB
- Vérifiez que vous disposez d’un ordinateur Mac avec [Apple Configurator 2.0](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) installé

## <a name="create-an-apple-configurator-profile-for-devices"></a>Créer un profil Apple Configurator pour les appareils

Un profil d'inscription d'appareil définit les paramètres appliqués à un groupe d'appareils. Les étapes suivantes montrent comment créer un profil d’inscription d’appareil pour les appareils iOS inscrits à l’aide d’Apple Configurator.

1. Dans le portail Azure, choisissez **Plus de services** > **Surveillance + gestion** > **Intune**.

2. Dans le panneau Intune, choisissez **Inscrire des appareils**, puis choisissez **Inscription Apple**.

3. Sous **Gérer les paramètres d’inscription Apple Configurator**, sélectionnez **Profils AC**.

4. Dans le panneau **Profils d’inscription Apple Configurator**, sélectionnez **Créer**.

5. Dans le panneau **Créer un profil d’inscription**, entrez un nom et une description pour le profil.

6. Pour **Affinité utilisateur** choisissez **Inscrire sans affinité utilisateur** pour vous assurer que l’appareil n’est pas associé à un utilisateur. Utilisez cette affiliation pour les appareils qui effectuent des tâches sans accéder aux données de l'utilisateur local. Les applications qui nécessitent l’affiliation d’un utilisateur (y compris l’application Portail d’entreprise utilisée pour l’installation des applications métier) ne fonctionneront pas.

7. Sélectionnez **Créer** pour enregistrer le profil.

## <a name="export-the-profile-as-mobileconfig-to-ios-devices"></a>Exporter le profil en tant que fichier .mobileconfig sur les appareils iOS

1. Dans le panneau **Exporter le profil**, téléchargez le profil d’inscription dans [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) pour l’envoyer directement comme profil de gestion sur un appareil iOS connecté. Cette méthode n’effectue pas une réinitialisation des paramètres d’usine de l’appareil.

2. Préparez l’appareil avec Apple Configurator à l’aide de la procédure suivante.

   a. Sur un ordinateur Mac, ouvrez Apple Configurator 2.0.

   b. Connectez l’appareil iOS à l’ordinateur Mac avec un câble USB. Fermez Photos, iTunes et toutes les autres applications qui s’ouvrent quand l’appareil est détecté.

   c. Dans Apple Configurator, choisissez l’appareil iOS connecté, puis cliquez sur le bouton **Ajouter**. Les options qui peuvent être ajoutées à l’appareil s’affichent dans la liste déroulante. Choisissez **Profils**.

   d. Utilisez le sélecteur de fichiers pour sélectionner le fichier .mobileconfig que vous avez exporté à partir d’Intune, puis choisissez **Ajouter**. Le profil est ajouté à l’appareil. Si l’appareil est Non supervisé, l’installation nécessite d’être acceptée sur l’appareil.

3. Utilisez la procédure suivante pour installer le profil sur l’appareil iOS. L’appareil doit avoir terminé l’Assistant Configuration et être prêt à l’emploi. Si l’inscription entraîne des déploiements d’applications, un ID Apple doit être configuré sur l’appareil, car les déploiements d’applications nécessitent de s’être connecté à l’APP Store avec un ID Apple.

   a. Déverrouillez l’appareil iOS.

   b. Dans la boîte de dialogue **Install profile** (Installer le profil) de **Management profile** (Gestion du profil), choisissez **Install** (Installer).

   c. Spécifiez le code d’accès d’appareil ou l’Apple ID, si nécessaire.

   d. Acceptez l’avertissement (**Warning**), puis choisissez **Install** (Installer).

   e. Acceptez l’avertissement distant (**Remote Warning**), puis choisissez **Trust** (Approuver).

   f. Quand la boîte de dialogue **Profile Installed** (Profil installé) confirme que le profil est installé, cliquez sur **Done** (Terminé).

4. Sur l’appareil iOS, ouvrez **Settings** (Réglages) et accédez à **General (Général)** > **Device Management (Gestion des appareils)** > **Management Profile (Profil de gestion)**. Assurez-vous que l’installation du profil est répertoriée, puis vérifiez les restrictions de stratégie iOS et les applications installées. L’affichage des applications et des restrictions de stratégie sur l’appareil peut prendre jusqu’à dix minutes.

5. Distribuez des appareils. L’appareil iOS est maintenant inscrit et géré dans Intune.

