---
title: "Évaluer la gestion des appareils mobiles dans Microsoft Intune | Documents Microsoft"
description: "Évaluez la gestion des appareils mobiles dans votre version d’évaluation gratuite Intune."
keywords: 
author: lindavr
ms.author: lindavr
manager: angrobe
ms.date: 11/29/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 47806f69-303d-41d9-9b0e-9b9445ea24ac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: eeb85a28ea6f99a0123ec5df3b0d476a678b85cb
ms.openlocfilehash: 4133c64d283682f0be37cd6ac69164ef872a5026


---

# <a name="evaluate-mobile-device-management-in-microsoft-intune"></a>Évaluer la gestion des appareils mobiles dans Microsoft Intune
Ce guide d’évaluation vous montre comment fonctionne la gestion des appareils mobiles dans Intune. Vous allez :
- Inscrire un appareil pour qu’il soit géré par Intune.
- Créer des groupes pour organiser les utilisateurs et les appareils.
- Créer des stratégies de gestion des appareils et les déployer sur des groupes.
- Publier une application que les utilisateurs installeront sur leurs appareils inscrits.
<!--- - Monitor the device? View a report of compliant devices?--->
<!--- - Remove the device from management--->

## <a name="assumptions"></a>Hypothèses
Ce guide part du principe que vous utilisez la version d’évaluation uniquement à des fins d’évaluation et que vous envisagez de démarrer avec un environnement propre quand vous allez vous abonner.

Pour vous permettre de démarrer facilement avec la version d’évaluation, nous configurons un environnement très simple qui utilise uniquement Intune et qui sera supposément votre autorité de gestion des appareils mobiles. Toutefois, tout au long du guide, nous vous indiquerons du contenu technique plus approfondi si vous souhaitez en savoir plus sur certains points.

Dans la version d’évaluation, vous pouvez effectuer les mêmes opérations que dans une version d’abonnement ; la seule différence est que vous êtes limité à 100 comptes d’utilisateur dans la version d’évaluation.

## <a name="whats-not-covered"></a>Sujets non abordés
|Si vous êtes intéressé par |Lisez |
|------------------------|----------|
|Gestion des appareils mobiles dans un environnement autre qu’un environnement de test | [Bien démarrer](https://docs.microsoft.com/en-us/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune) |
|Gestion des appareils mobiles avec Intune et System Center Configuration Manager | [Gestion des appareils mobiles hybride](https://docs.microsoft.com/en-us/sccm/mdm/understand/hybrid-mobile-device-management) |

Comme les guides ci-dessus vous aident à configurer Intune dans les environnements de production, ils sont plus volumineux et comptent plus de points de décision à considérer que dans le guide d’évaluation.

Pour vous familiariser rapidement avec Intune, nous vous conseillons de commencer par le guide d’évaluation, puis de passer aux autres guides.

## <a name="prerequisites-for-this-evaluation"></a>Conditions préalables pour cette évaluation
- Internet Explorer 10 ou version ultérieure
- Un appareil que vous utiliserez pour tester la façon dont les utilisateurs Intune inscrivent et gèrent leurs appareils dans le portail d’entreprise. Nous utilisons un iPad et un téléphone Android dans ce guide.
- Pour gérer l’iPad ou un autre appareil iOS, vous aurez besoin d’un [certificat APNs](https://docs.microsoft.com/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune).
- Un [abonnement d’évaluation Intune](sign-up-for-30-day-trial-microsoft-intune.md)

## <a name="set-your-mdm-authority"></a>Définir votre autorité de gestion des appareils mobiles
La première étape à effectuer pour gérer des appareils mobiles avec Intune consiste à définir votre **autorité de gestion des appareils mobiles**.

Si vous utilisez Intune autonome, comme supposé dans cette version d’évaluation, ou si vous utilisez Intune dans le cadre d’un abonnement EMS (Enterprise Mobility + Security), vous devez définir Intune comme votre autorité de gestion des appareils mobiles. Autrement dit, vous désignez Intune comme le service que vous utilisez pour gérer les appareils mobiles de votre organisation.

Les clients qui souhaitent utiliser Intune avec System Center Configuration Manager pour gérer les appareils mobiles doivent décider s’il faut utiliser Intune ou Configuration Manager comme leur autorité de gestion des appareils mobiles. Il s’agit d’une décision importante à prendre dans un environnement de production, car il est actuellement très difficile de modifier ce paramètre une fois que vous l’avez défini, mais cela dépasse le cadre de ce guide d’évaluation. Pour en savoir plus sur les implications de la définition d’Intune ou de Configuration Manager comme autorité de gestion des appareils mobiles, consultez [Choisir entre Intune autonome et une gestion des appareils mobiles hybride](https://docs.microsoft.com/en-us/sccm/mdm/understand/choose-between-standalone-intune-and-hybrid-mobile-device-management).

Nous allons définir Intune comme autorité de gestion des appareils mobiles pour la version d’évaluation ; cela n’affectera pas votre environnement de production, sauf si vous décidez d’utiliser votre version d’évaluation pour votre environnement de production.

1. Dans la [console d’administration Intune](https://manage.microsoft.com/), cliquez sur **Admin** &gt; **Gestion des appareils mobiles**.
2. Dans la liste **Tâches**, choisissez **Définir l’autorité de gestion des appareils mobiles**. La boîte de dialogue **Définir l'autorité MDM** s'ouvre. <!---screen shot--->
3. Intune vous invite à confirmer que vous souhaitez définir Intune comme autorité MDM. Cochez la case, puis choisissez **Oui** pour utiliser Intune pour gérer les appareils mobiles.

## <a name="enroll-your-test-devices-into-intune"></a>Inscrire vos appareils de test dans Intune

Dans le cadre de ce guide, nous allons inscrire un téléphone Android et un iPad Apple, mais aussi fournir des liens pour [en savoir plus sur l’inscription d’appareils dans Intune](#Learn-more-about-device-enrollment) à la fin de cette section.
### <a name="android"></a>Android
Installez l’application **Portail d’entreprise Intune** de Microsoft Corporation disponible sur [Google Play](http://go.microsoft.com/fwlink/p/?LinkId=386612) et connectez-vous avec les [informations d’identification de l’utilisateur](sign-up-for-30-day-trial-microsoft-intune.md#add-users) Intune que vous avez créées lors de votre inscription à l’évaluation gratuite.

### <a name="ios"></a>iOS
Avant que les utilisateurs ne puissent inscrire leurs appareils iOS, vous devez configurer Intune pour gérer ces appareils.

1. **Obtenir une demande de signature de certificat**<br/>
Connectez-vous à Intune avec votre compte d’administrateur et accédez à **Administration** > **Gestion des appareils mobiles** > **iOS et Mac OS X** > **Télécharger un certificat APNs**, puis cliquez sur **Télécharger la demande de certificat APNs**. Enregistrez localement le fichier de demande de signature de certificat (.csr). Le fichier .csr est utilisé pour demander un certificat de relation d'approbation à partir du portail Apple Push Certificates. <!--- screen shot--->
2.  **Obtenir un certificat du service Apple Push Notification**<BR/>
Accédez au [portail Apple Push Certificates](https://idmsa.apple.com/IDMSWebAuth/login?appIdKey=3fbfc9ad8dfedeb78be1d37f6458e72adc3160d1ad5b323a9e5c5eb2f8e7e3e2&rv=2) et connectez-vous avec votre ID Apple d’entreprise pour créer le certificat APNs à l’aide du fichier .csr. Après avoir choisi **Upload on Apple’s Push Certificate Portal** (Télécharger sur le portail Apple Push Certificate), vous recevrez un fichier .json qui ne peut pas être utilisé pour APNs. Terminez le téléchargement, revenez au portail Apple Push Certificate pour obtenir des certificats pour serveurs tiers, puis choisissez **Télécharger**.

 Téléchargez le certificat APNs (.pem) et enregistrez le fichier localement. Cet ID Apple doit être utilisé ultérieurement pour renouveler votre certificat APNs.
3.  **Ajouter le certificat APNs à Intune**<BR/>
Dans la console d’administration Microsoft Intune, accédez à **Administration** > **Gestion des appareils mobiles** > **iOS et Mac OS X** > **Télécharger un certificat APNs**, puis choisissez **Télécharger le certificat APNs**. Accédez au fichier de certificat (.pem), choisissez **Ouvrir**, puis entrez votre ID Apple. Avec le certificat APNs. Intune peut inscrire et gérer des appareils iOS en envoyant la stratégie aux appareils mobiles inscrits.
4.  **Indiquez à vos utilisateurs comment inscrire leurs appareils de manière à ce qu’ils puissent accéder aux ressources de l’entreprise.**<br/>
Pour obtenir des instructions sur l’inscription des utilisateurs finaux, consultez [Inscrire un appareil iOS dans Intune](https://docs.microsoft.com/en-us/Intune/enduser/enroll-your-device-in-intune-ios) et [Inscrire votre appareil Mac OS X dans Intune](https://docs.microsoft.com/en-us/Intune/enduser/enroll-your-device-in-intune-mac-os-x). Le processus d’inscription indique aux utilisateurs ce qu’ils peuvent attendre, et ce que les administrateurs informatiques peuvent voir ou ne peuvent pas voir sur leurs appareils.


### <a name="learn-more-about-device-enrollment"></a>En savoir plus sur l’inscription d’appareils

Intune prend en charge les plateformes d’appareils suivantes :

[!INCLUDE[mdm-supported-devices](../includes/mdm-supported-devices.md)]

La configuration requise pour activer la gestion des appareils varie selon les plateformes que vous souhaitez gérer.
- Les appareils mobiles **Android** permettent aux utilisateurs de [s’inscrire à l’aide de l’application Portail d’entreprise](/intune/deploy-use/set-up-android-management-with-microsoft-intune) disponible sur Google Play. Aucune configuration supplémentaire n'est nécessaire dans Intune.
- [Configuration requise pour l’installation d’**iOS et de Mac OS X**](/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune)
- [Configuration requise pour l’installation de **Windows Phone**](/intune/deploy-use/set-up-windows-phone-management-with-microsoft-intune).

<!--- ## Verify enrollment--->
<!--- START HERE

### iOS and Mac OS X
Install the **Microsoft Intune Company Portal** app from Microsoft Corporation available in the App Store and sign in with Intune user credentials added above. View **Enrolled devices** to add your device.



### Windows Phone 8.1
Users install the **Company Portal** app from Microsoft Corporation, available in the Windows Phone store, and sign in with the Intune user credentials added above.  View **Enrolled devices** to add your device.

## Install the previously deployed app
Open the Company Portal on the mobile device, choose **Apps**, and then install **Microsoft Skype**.--->



## <a name="next-steps"></a>Étapes suivantes
[Créer des groupes pour organiser les utilisateurs et les appareils](get-started-with-a-30-day-trial-of-microsoft-intune-step-3.md)



<!--HONumber=Jan17_HO1-->


