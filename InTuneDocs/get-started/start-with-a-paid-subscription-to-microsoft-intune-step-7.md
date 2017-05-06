---
title: "Personnaliser le Portail d’entreprise | Microsoft Docs"
description: "Le portail d’entreprise Intune permet aux utilisateurs d’effectuer des tâches courantes comme inscrire des appareils, installer des applications et trouver des informations concernant le service informatique."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/14/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: eb4a9f01-f857-4563-ab6f-5d0d7dfa659d
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 8b2bd3ecba0b597bc742ea08872ffe8fc58155cf
ms.openlocfilehash: 3794981387e73176152c212854a97b4333023f5d
ms.lasthandoff: 04/24/2017


---

# <a name="customize-the-company-portal"></a>Personnaliser le portail d'entreprise

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Cette rubrique explique aux administrateurs comment personnaliser l’application Portail d’entreprise Intune et le site web du portail d’entreprise.

Le portail d’entreprise Intune permet aux utilisateurs d’accéder aux données de l’entreprise et d’effectuer des tâches courantes, notamment l’inscription d’appareils, l’installation d’applications et d’accéder à des informations d’assistance fournies par le département informatique.

Le Portail d’entreprise Intune permet aux utilisateurs d’accéder aux données et applications de l’entreprise. Le Portail d’entreprise est disponible sous deux formes :

-   **L’application Portail d’entreprise** : disponible sur les appareils que vous gérez avec Intune. En savoir plus sur les applications Portail d’entreprise pour [Android](/Intune/EndUser/using-your-android-device-with-intune), [iOS](/Intune/EndUser/using-your-iOS-or-macOS-device-with-intune) et [Windows](/Intune/EndUser/using-your-windows-device-with-intune).


- **Le site web du portail d’entreprise** : site web permettant aux utilisateurs finaux d’effectuer la plupart des tâches à partir de l’application Portail d’entreprise. L’URL du portail d’entreprise Intune est [https://portal.manage.microsoft.com](https://portal.manage.microsoft.com). Pour en savoir plus sur ce site web, consultez [Utiliser le site web du portail d’entreprise Intune](/Intune/EndUser/using-the-intune-company-portal-website).

> [!TIP]
> Quand vous personnalisez le Portail d’entreprise, les configurations s’appliquent au site web du Portail d’entreprise et aux applications du Portail d’entreprise.

Certaines des tâches que les utilisateurs peuvent effectuer dans le Portail d’entreprise sont les suivantes :

-   Inscrire des appareils
-   Afficher l'état de leurs appareils
-   Réinitialiser leur appareil
-   Réinitialiser leur mot de passe
-   Verrouiller leur appareil à distance
-   télécharger les logiciels déployés par votre organisation ;
-   Contacter le service informatique pour obtenir de l’aide

## <a name="customize-company-portal-settings"></a>Personnaliser les paramètres du portail d’entreprise
La personnalisation du Portail d’entreprise permet de fournir une expérience familière et utile à vos utilisateurs finaux. Connectez-vous à la [console d’administration Microsoft Intune](https://manage.microsoft.com) comme administrateur du service ou client, choisissez **Administration** &gt; **Portail d’entreprise** et configurez les paramètres du portail d’entreprise.

![admin-console-admin-workspace-comp-portal-settings](./media/companyportal.png)

## <a name="company-contact-information-and-privacy-statement"></a>Informations de contact et déclaration de confidentialité de l'entreprise
Le nom de l’entreprise s’affiche comme titre du Portail d’entreprise. Les informations de contact et les détails sont présentés aux utilisateurs dans l’écran Contacter le service informatique du Portail d’entreprise. La déclaration de confidentialité s’affiche lorsqu’un utilisateur clique sur le lien correspondant.

|Nom du champ|Longueur maximale|Plus d'informations|
    |----------|------------------------|----------------|
    |Nom de la société|40|Ce nom s’affiche comme titre du Portail d’entreprise.|
    |Nom du contact du service informatique|40|Ce nom s’affiche dans la page **Contacter le service informatique**.|
    |Numéro de téléphone du service informatique|20|Ce numéro s’affiche dans la page **Contacter le service informatique**.|
    |Adresse de messagerie du service informatique|40|Cette adresse s’affiche dans la page **Contacter le service informatique**. Vous devez entrer une adresse e-mail valide au format **alias@domainname.com**.|
    |Informations supplémentaires|120|S’affiche dans la page **Contacter le service informatique**.|
    |URL de la déclaration de confidentialité de l'entreprise|79|Vous pouvez spécifier la déclaration de confidentialité de votre entreprise qui s’affiche lorsque les utilisateurs cliquent sur les liens de confidentialité à partir du Portail d’entreprise. Vous devez entrer une URL valide au format https://www.contoso.com.|

## <a name="support-contacts"></a>Contacts du support
Les utilisateurs peuvent voir le lien du site web de support dans le Portail d’entreprise et l’utiliser pour accéder au support en ligne.

|Nom du champ|Longueur maximale|Plus d'informations|
    |----------|------------------------|----------------|
    |URL du site Web de support technique|150|Si vous avez un site web de support technique auquel vous aimeriez que les utilisateurs accèdent, spécifiez cette URL ici. L’URL doit être au format https://www.contoso.com. Si vous ne spécifiez aucune URL, rien ne s’affiche pour le site web de support technique dans la page **Contacter le service informatique** du Portail d’entreprise.|
    |Nom du site web|40|Il s'agit du nom convivial qui s'affiche pour l'URL permettant d'accéder au site Web de support technique. Si vous spécifiez l’URL d’un site web de support technique sans aucun nom convivial, **Accéder au site web du service informatique** apparaît dans la page **Contacter le service informatique** du Portail d’entreprise.|

## <a name="company-branding-customization"></a>Personnalisation de l’image de la société
Vous pouvez personnaliser votre Portail d’entreprise avec le logo et le nom de votre société, un thème chromatique et un arrière-plan.

|Nom du champ|Plus d'informations|
    |----------|----------------|
    |Couleur de thème|Sélectionnez une couleur de thème à appliquer au Portail d’entreprise.|
    |Inclure le logo de l'entreprise|Lorsque vous activez cette option, vous pouvez télécharger le logo de votre entreprise pour qu’il apparaisse sur le Portail de celle-ci. Vous pouvez télécharger deux logos : un qui s’affiche quand l’arrière-plan du Portail d’entreprise est blanc, et un autre qui s’affiche quand l’arrière-plan du Portail d’entreprise utilise la couleur de thème que vous avez sélectionnée. Chaque logo doit être un fichier de type .png ou .jpg, et avoir une résolution maximale de 400 x 100 pixels et une taille inférieure ou égale à 750 Ko.|
    |Choisir un arrière-plan pour l'application Portail d'entreprise [!INCLUDE[win8_client_2](../includes/win8_client_2_md.md)]|Ce paramètre affecte l’arrière-plan de l’application Portail d’entreprise [!INCLUDE[win8_client_2](../includes/win8_client_2_md.md)] uniquement.|


Après avoir enregistré vos modifications, vous pouvez utiliser les liens proposés au bas de la page **Portail d’entreprise** de la console d’administration pour afficher le site web du Portail d’entreprise. Ces liens ne peuvent pas être modifiés. Lorsqu’un utilisateur se connecte, ces liens présentent vos abonnements dans le Portail d’entreprise.

>[!div class="step-by-step"]

>[&larr;**Créer des applications et des stratégies**](.\start-with-a-paid-subscription-to-microsoft-intune-step-6.md)[       **Inscrire des appareils**&rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-8.md)  

