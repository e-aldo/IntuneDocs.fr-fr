---
title: "Inscription en bloc de Windows 10 | Microsoft Docs"
titleSuffix: Intune Azure preview
description: "Créer un package d’inscription en bloc pour Microsoft Intune"
keywords: 
author: NathBarn
ms.author: NathBarn
manager: angrobe
ms.date: 03/18/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1f39c02a-8d8a-4911-b4e1-e8d014dbce95
ms.reviewer: damionw
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: f8d1ff7a9a8bd804d4fe40f8aec7e7d0bf998e35
ms.contentlocale: fr-fr
ms.lasthandoff: 05/23/2017

---
# <a name="bulk-enrollment-for-windows-devices"></a>Inscription en bloc des appareils Windows

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

En tant qu’administrateur, vous pouvez joindre un grand nombre de nouveaux appareils Windows à Azure Active Directory et à Intune. Pour inscrire des appareils en bloc pour votre client Azure AD, vous devez créer un package d’approvisionnement avec l’application Windows Configuration Designer (WCD). En appliquant le package d’approvisionnement aux appareils d’entreprise, vous pouvez joindre les appareils à votre client Azure AD et les inscrire pour une gestion dans Intune. Une fois le package appliqué, vos utilisateurs Azure AD peuvent immédiatement s’y connecter.

Les utilisateurs d’Azure AD agissent sur ces appareils en tant qu’utilisateurs standard ; ils reçoivent les stratégies Intune qui leur sont affectées ainsi que les applications dont ils ont besoin. Les scénarios de libre-service et de portail d’entreprise ne sont pas pris en charge pour le moment.

## <a name="prerequisites-for-windows-devices-bulk-enrollment"></a>Configuration requise pour l’inscription en bloc des appareils Windows

L’inscription en bloc des appareils Windows requiert les éléments suivants :

- Appareils exécutant Windows 10 Creator ou version ultérieure
- [Inscription automatique de Windows](https://docs.microsoft.com/intune-classic/deploy-use/set-up-windows-device-management-with-microsoft-intune#enable-windows-10-automatic-enrollment)

## <a name="create-a-provisioning-package"></a>Créer un package d’approvisionnement

1. Téléchargez l’application [Windows Configuration Designer (WCD)](https://www.microsoft.com/store/apps/9nblggh4tx22) à partir du Windows Store.
![Illustration montrant les captures d’écran de l’application Windows Configuration Designer du Windows Store avec une description](media/bulk-enroll-store.png)

2. Ouvrez l’application **Windows Configuration Designer** et sélectionnez **Provision desktop devices** (Approvisionner des appareils de bureau).
![Capture d’écran montrant l’option Provision desktop devices (Approvisionner des appareils de bureau) sélectionnée dans l’application Windows Configuration Designer](media/bulk-enroll-select.png)

3. Vous accédez à une fenêtre **Nouveau projet** dans laquelle vous pouvez spécifier les éléments suivants :
  - **Nom** : nom de votre projet
  - **Dossier de projet** : dossier dans lequel vous allez enregistrer votre projet
  - **Description** : description facultative du projet ![Capture d’écran indiquant où spécifier le nom, le dossier du projet et la description dans l’application Windows Configuration Designer](media/bulk-enroll-name.png)

4.    Entrez un nom unique pour vos appareils. Les noms peuvent inclure un numéro de série (%%SERIAL%%) ou un jeu de caractères aléatoires. Si vous le souhaitez, vous pouvez également entrer une clé de produit si vous mettez à niveau l’édition de Windows, configurer l’appareil pour une utilisation partagée et supprimer le logiciel préinstallé.
![Capture d’écran indiquant où spécifier le nom, le dossier du projet et la description dans l’application Windows Configuration Designer](media/bulk-enroll-device.png)

5.    Si vous le souhaitez, vous pouvez configurer les périphériques réseau Wi-Fi auxquels se connecter lors de leur premier démarrage.  Si cela n’est pas configuré, une connexion de réseau câblé est requise lors du premier démarrage de l’appareil.
![Capture d’écran indiquant l’activation du Wi-Fi, y compris les options SSID réseau et le type de réseau, dans l’application Windows Configuration Designer](media/bulk-enroll-network.png)

6.    Sélectionnez **Enroll in Azure AD** (S’inscrire dans Azure AD), entrez une date dans le champ **Bulk Token Expiry** (Expiration du jeton en bloc), puis sélectionnez **Get Bulk Token** (Obtenir le jeton en bloc).
![Capture d’écran indiquant où spécifier le nom, le dossier du projet et la description dans l’application Windows Configuration Designer](media/bulk-enroll-account.png)

7. Indiquez vos informations d’identification Azure AD pour obtenir un jeton en bloc.
![Capture d’écran indiquant où spécifier le nom, le dossier du projet et la description dans l’application Windows Configuration Designer](media/bulk-enroll-cred.png)

8.    Cliquez sur **Suivant** une fois le **jeton en bloc** obtenu.

9. Si vous le souhaitez, vous pouvez **ajouter des applications** et **ajouter des certificats**. Ces applications et certificats sont approvisionnés sur le périphérique.

10. Si vous le souhaitez, vous pouvez protéger votre package d’approvisionnement par un mot de passe.  Cliquez sur **Créer**.
![Capture d’écran indiquant où spécifier le nom, le dossier du projet et la description dans l’application Windows Configuration Designer](media/bulk-enroll-create.png)

## <a name="provision-devices"></a>Approvisionner des appareils

1. Accédez au package d’approvisionnement à l’emplacement spécifié dans le **dossier de projet** indiqué dans l’application.

2. Choisissez comment vous allez appliquer le package d’approvisionnement à l’appareil.  Un package d’approvisionnement peut être appliqué à un appareil de plusieurs manières :
 - Copiez le package d’approvisionnement sur une clé USB, insérez la clé USB dans l’appareil que vous voulez inscrire en bloc, puis appliquez-le lors de l’installation initiale
 - Copiez le package d’approvisionnement dans un dossier réseau et insérez-le dans l’appareil que vous voulez inscrire en bloc après l’installation initiale

 Pour obtenir des instructions détaillées sur l’application d’un package d’approvisionnement, consultez la rubrique [Apply a provisioning package](https://technet.microsoft.com/itpro/windows/configure/provisioning-apply-package) (Appliquer un package d’approvisionnement).

3. Après avoir appliqué le package, l’appareil redémarrera automatiquement dans 1 minute.
 ![Capture d’écran indiquant où spécifier le nom, le dossier du projet et la description dans l’application Windows Configuration Designer](media/bulk-enroll-add.png)

4. Lorsque l’appareil redémarre, il se connecte à Azure Active Directory et s’inscrit dans Microsoft Intune.

## <a name="troubleshooting-windows-bulk-enrollment"></a>Résolution des problèmes d’inscription en bloc sous Windows

L’approvisionnement est destiné aux nouveaux appareils Windows. Les échecs d’approvisionnement peuvent nécessiter une réinitialisation de l’appareil ou une récupération de l’appareil à partir d’une image de démarrage. Voici quelques raisons qui peuvent expliquer un échec de l’approvisionnement :

- Un package d’approvisionnement qui tente de rejoindre un domaine Active Directory ou un client Azure Active Directory qui ne crée pas de compte local peut rendre l’appareil inaccessible si le processus de jonction de domaine échoue en raison d’un manque de connectivité réseau.
- Les scripts exécutés par le package d’approvisionnement sont exécutés dans le contexte système et peuvent apporter des modifications arbitraires au système de fichiers et aux configurations de l’appareil. Un script malveillant ou incorrect peut faire basculer l’appareil dans un état dont il ne pourra récupérer que par une réinitialisation de l’image ou par une restauration des paramètres d’usine de l’appareil.

