---
title: "Il manque un certificat obligatoire à votre appareil | Microsoft Intune"
description: 
keywords: 
author: staciebarker
manager: angrobe
ms.date: 7/7/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9081b1d8-50e8-4bc2-ba37-766421364213
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: arnab
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: d3a2daebdb781ce99aa103e7717ffa1b0297cb3a
ms.openlocfilehash: e10de556babc49d4e2f1ebf6ba9c766291d58efd


---


# Un certificat obligatoire est manquant sur votre appareil


## Un certificat qui est généralement installé sur votre téléphone est absent de votre appareil
Si votre appareil Android n’est pas inscrit dans Intune et qu’il manque un certificat qui devrait être installé sur votre téléphone, vous ne pouvez pas vous connecter à l’application Portail d’entreprise Android. Quand vous essayez de vous connecter, le message suivant s’affiche :

![screenshot-error-message-about-missing-certificate](./media/andr-cert_install-1-cert_missing.png)

Pour résoudre ce problème et obtenir le certificat obligatoire :

1.  Dans un navigateur, accédez à cette [page du certificat Digicert](https://www.digicert.com/digicert-root-certificates.htm).

2.  Recherchez et téléchargez le certificat Baltimore CyberTrust Root (https://www.digicert.com/CACerts/BaltimoreCyberTrustRoot.crt).

3.  Faites glisser à partir du haut pour ouvrir vos notifications, puis appuyez sur **BaltimoreCyberTrustRoot.crt** dans la liste des notifications.

4.  Dans la boîte de dialogue **Name the certificate** (Nommer le certificat), acceptez le nom du certificat par défaut.

5. Vérifiez que **Credential Use** (Utilisation des informations d’identification) a la valeur **Used for VPN and apps** (Utilisé pour le VPN et les applications), puis appuyez sur **OK**.

    ![screenshot-certificate-name-dialog-showing-baltimore-certificate-name](./media/andr-cert_install-2-add_cert_name.png)

6. Fermez le navigateur web et l’application Portail d’entreprise.

7. Rouvrez l’application Portail d’entreprise. Vous devriez pouvoir vous connecter à l’application Portail d’entreprise. Si vous avez besoin d’aide, contactez votre administrateur informatique.

## Le certificat requis par votre administrateur est absent de votre appareil
Si votre appareil Android n’est pas inscrit dans Intune et qu’il manque un certificat requis par votre administrateur, vous ne pouvez pas vous connecter à l’application Portail d’entreprise Android. Quand vous essayez de vous connecter, le message suivant s’affiche :

![screenshot-error-message-about-missing-certificate](./media/andr-cert_install-1-cert_missing.png)

>[!NOTE]
> Si vous avez déjà vu un message « Certificat manquant » et suivi les étapes de [Un certificat qui est généralement installé sur votre téléphone est absent de votre appareil](#your-device-is-missing-a-certificate-that-usually-comes-installed-on-your-phone), cela ne pose pas de problème. Il s’agit d’un autre message, concernant un autre certificat. Vous pouvez donc continuer et suivre les étapes de cette section pour obtenir le certificat manquant.

Pour résoudre ce problème et obtenir le certificat requis, il existe deux étapes à suivre :

- Identifier le certificat manquant en le recherchant sur votre ordinateur professionnel ou scolaire.
- Utiliser votre appareil pour télécharger le certificat manquant à partir d’Internet.

### Identifier le certificat manquant en le recherchant sur votre ordinateur professionnel ou scolaire

1. Ouvrez Internet Explorer sur votre PC. Si vous n’avez pas de PC, contactez votre administrateur. Pour obtenir les coordonnées de votre administrateur, consultez le site web [Portail d’entreprise](http://portal.manage.microsoft.com) de votre entreprise.

2. Accédez au site web [Portail d’entreprise](http://portal.manage.microsoft.com), puis connectez-vous à l’aide de vos informations d’identification professionnelles ou scolaires.

3. À l’extrême droite de la barre d’adresse du navigateur, cliquez sur le symbole qui ressemble à un verrou, comme indiqué ci-dessous. Si vous ne voyez pas le symbole de verrou, arrêtez, puis contactez votre administrateur. Le verrou signifie que vous êtes connecté en toute sécurité, donc ne continuez pas tant que vous ne voyez pas ce symbole.

    ![screenshot-internet-explorer-address-bar-padlock-symbol](./media/andr-missing-cert-ie-padlock-symbol.png)

4. Cliquez sur **Afficher les certificats**.

    ![screenshot-internet-explorer-view-certificates-button-on-website-identification-dialog](./media/andr-missg-cert-ie-view-cert-button.png)

5. Dans la boîte de dialogue **Certificat**, cliquez sur l’onglet **Chemin d’accès de certification**, puis identifiez le certificat que vous devez obtenir à partir d’Internet. Le nom de ce certificat est affiché au même endroit que celui mis en surbrillance dans la capture d’écran ci-dessus.

### Télécharger et installer le certificat manquant sur votre appareil mobile Android

1. À l’aide d’un moteur de recherche tel que Bing ou Google, recherchez le nom du certificat manquant que vous avez identifié dans la section précédente. Le nom du certificat peut se terminer par différentes extensions, telles que « .crt » ou « .pem », etc.

2. Téléchargez le certificat racine à partir du site web.

3. Une fois le certificat téléchargé, faites défiler l’écran de votre appareil de bas en haut pour accéder à vos notifications, puis cliquez sur le nom du certificat dans la liste des notifications.

4. Dans la boîte de dialogue **Name the certificate** (Nommer le certificat) indiquée ci-dessous, acceptez le nom du certificat par défaut.

5. Vérifiez que **Credential Use** (Utilisation des informations d’identification) a la valeur **Used for VPN and apps** (Utilisé pour le VPN et les applications), puis appuyez sur **OK**.

    ![screenshot-certificate-name-dialog-showing-certificate-name](./media/andr-missing-cert-cert-name.png)

6. Fermez l’application Portail d’entreprise.

7. Rouvrez l’application Portail d’entreprise. Vous devriez pouvoir vous connecter à l’application Portail d’entreprise. Si vous avez besoin d’aide, contactez votre administrateur informatique.

Si un message « Certificat manquant » semblable à celui indiqué ci-dessus s’affiche alors que vous avez déjà suivi la procédure précédente, cela signifie généralement qu’il manque un autre certificat et vous devez demander à votre administrateur de vous aider à l’installer. Contactez votre administrateur et transmettez-lui ce [lien](/intune/troubleshoot/troubleshoot-device-enrollment-in-intune#android-certificate-issues) qui mène vers la procédure de résolution du problème.

### Voir aussi
[Utilisation de votre appareil Windows avec Intune](using-your-windows-device-with-intune.md)



<!--HONumber=Aug16_HO4-->


