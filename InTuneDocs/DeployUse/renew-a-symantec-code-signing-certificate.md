---
title: "Renouveler un certificat de signature de code d’entreprise Symantec à utiliser avec Microsoft Intune | Microsoft Intune"
description: 
keywords: 
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c4813044-a925-4273-b0ec-e992fd55850a
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 779127bfd39145010f0d9b6609286aaf4dedfdc8
ms.openlocfilehash: 566a226c19825990c6a34bffbbd9d1cd6a242ddb


---

# Renouveler un certificat de signature du code d’entreprise Symantec pour les appareils Windows

Le certificat Symantec utilisé pour gérer certains appareils mobiles Windows et Windows Phone doit être renouvelé régulièrement. Pour les appareils Windows Phone 8.0, une application Portail d'entreprise signée et le certificat de signature de code sont nécessaires pour l'inscription d'un appareil. Par la suite, les appareils Windows Phone peuvent utiliser l'application de portail d'entreprise téléchargée à partir du magasin. Un certificat de signature de code est aussi requis pour le déploiement d'applications métier.

## Comment renouveler le certificat de signature du code d'entreprise Symantec

1.  Recherchez un e-mail de renouvellement envoyé par Symantec 14 jours environ avant l'expiration du certificat. Ce courrier électronique contient les instructions de Symantec sur le renouvellement du certificat de votre entreprise.

    Pour plus d’informations sur les certificats Symantec, visitez [www.symantec.com](http://www.symantec.com) ou appelez le 1-877-438-8776 ou le 1-650-426-3400.

2.  Accédez au site web (par exemple, [https://products.websecurity.symantec.com/orders/enrollment/microsoftCert.do](https://products.websecurity.symantec.com/orders/enrollment/microsoftCert.do)) et connectez-vous à l'aide de l'identifiant d'éditeur Symantec et de l'adresse e-mail associée au certificat. Pensez à utiliser le même ordinateur pour démarrer le renouvellement que vous allez utiliser pour télécharger le certificat.

3.  Une fois le renouvellement approuvé et payé, téléchargez-le.

## Comment installer le certificat mis à jour pour Windows Phone 8.0

1.  Téléchargez et signez l'application Portail d'entreprise Windows Phone la plus récente à l'adresse suivante : [http://www.microsoft.com/en-us/download/details.aspx?id=36060](http://www.microsoft.com/en-us/download/details.aspx?id=36060).

2.  Ouvrez la console d’administration Intune ([https://admin.manage.microsoft.com](https://admin.manage.microsoft.com)) et accédez à **Admin**, **Gestion des appareils mobiles** &gt; **Windows Phone**, puis cliquez sur **Télécharger l’application signée**.

3.  Téléchargez le portail d'entreprise nouvellement signé. Vous avez besoin du fichier SSP.xap qui vient d'être signé et du nouveau fichier .PFX que vous avez reçu de Symantec, ou du jeton d'inscription d'application qui a été créé avec ce nouveau fichier .PFX.

4.  Une fois le téléchargement terminé, supprimez l'ancienne version du portail d'entreprise dans l'espace de travail **Logiciel** de la console de gestion d'Intune.

5.  Signez toutes les applications métier d'entreprise en utilisant le même certificat, puis téléchargez et remplacez les applications existantes.

Le fichier SSP.xap signé est actuellement le seul moyen de fournir le certificat de signature de code mis à jour. Pour prendre en charge les applications métier signées, vous devez signer et charger une application Portail d'entreprise, même si vos utilisateurs installent l'application Portail d'entreprise à partir de la boutique d'applications.

## Comment installer le certificat mis à jour pour Windows Phone 8.1 et versions ultérieures

1.  Téléchargez et signez l'application Portail d'entreprise Windows Phone la plus récente à partir du Centre de téléchargement à l'adresse suivante : [http://www.microsoft.com/en-us/download/details.aspx?id=36060](http://www.microsoft.com/en-us/download/details.aspx?id=36060).

2.  Ouvrez la [console d’administration Intune](https://admin.manage.microsoft.com) (https://admin.manage.microsoft.com) et accédez à **Admin** &gt; **Gestion des appareils mobiles** &gt; **Windows Phone**, puis cliquez sur **Télécharger l’application signée**.

3.  Téléchargez le portail d'entreprise nouvellement signé. Vous avez besoin du fichier SSP.xap qui vient d'être signé et du nouveau fichier .PFX que vous avez reçu de Symantec, ou du jeton d'inscription d'application qui a été créé avec ce nouveau fichier .PFX.

4.  Une fois le chargement terminé, supprimez l'ancienne version de l'application Portail d'entreprise dans l'espace de travail **Logiciel**  .

5.  Signez toutes les applications métier nouvelles et mises à jour de l'entreprise à l'aide du nouveau certificat. Les applications existantes ne doivent être ni resignées ni redéployées.


### Voir aussi
[Configurer la gestion de Windows Phone 8.0](set-up-windows-phone-8.0-management-with-microsoft-intune.md)
[Configurer la gestion de Windows Phone](set-up-windows-phone-management-with-microsoft-intune.md)



<!--HONumber=Jun16_HO4-->


