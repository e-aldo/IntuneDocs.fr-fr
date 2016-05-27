---
# required metadata

title: Personnaliser le Portail d’entreprise | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: eb4a9f01-f857-4563-ab6f-5d0d7dfa659d

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Personnaliser le portail d'entreprise
Le [!INCLUDE[wit_iwportal_1](../includes/wit_iwportal_1_md.md)] est l'emplacement où les utilisateurs peuvent accéder aux données de l'entreprise et effectuer des tâches courantes, notamment l'inscription d'appareils, l'installation d'applications et accéder à des informations d'assistance fournies par le département informatique.

> [!TIP]
> Quand vous personnalisez le Portail d’entreprise, les configurations s’appliquent au site web du Portail d’entreprise et aux applications du Portail d’entreprise.

La personnalisation du Portail d’entreprise permet de fournir une expérience familière et utile à vos utilisateurs finaux. Pour ce faire, connectez-vous à la [console d’administration Microsoft Intune](https://manage.microsoft.com) en tant qu’administrateur du service ou que client, choisissez **Administrateur** &gt; **Portail d’entreprise** et configurez les paramètres du Portail d’entreprise.

![admin-console-admin-workspace-comp-portal-settings](./media/companyportal.png)

## Informations de contact et déclaration de confidentialité de l'entreprise
Le nom de l’entreprise s’affiche comme titre du Portail d’entreprise. Les informations de contact et les détails sont présentés aux utilisateurs dans l’écran Contacter le service informatique du Portail d’entreprise. La déclaration de confidentialité s’affiche lorsqu’un utilisateur clique sur le lien correspondant.

|Nom du champ|Longueur maximale|Plus d'informations|
    |----------|------------------------|----------------|
    |Nom de la société|40|Ce nom s’affiche comme titre du Portail d’entreprise.|
    |Nom du contact du service informatique|40|Ce nom s’affiche dans la page **Contacter le service informatique**.|
    |Numéro de téléphone du service informatique|20|Ce numéro s’affiche dans la page **Contacter le service informatique**.|
    |Adresse de messagerie du service informatique|40|Cette adresse s’affiche dans la page **Contacter le service informatique**. Vous devez entrer une adresse de messagerie valide au format **alias@nomdedomaine.com**.|
    |Informations supplémentaires|120|S’affiche dans la page **Contacter le service informatique**.|
    |URL de la déclaration de confidentialité de l'entreprise|79|Vous pouvez spécifier la déclaration de confidentialité de votre entreprise qui s’affiche lorsque les utilisateurs cliquent sur les liens de confidentialité à partir du Portail d’entreprise. Vous devez entrer une URL valide au format https://www.contoso.com.|

## Contacts du support
Les utilisateurs peuvent voir le lien du site web de support dans le Portail d’entreprise et l’utiliser pour accéder au support en ligne.

|Nom du champ|Longueur maximale|Plus d'informations|
    |----------|------------------------|----------------|
    |URL du site Web de support technique|150|Si vous avez un site web de support technique auquel vous aimeriez que les utilisateurs accèdent, spécifiez cette URL ici. L’URL doit être au format https://www.contoso.com. Si vous ne spécifiez aucune URL, rien ne s’affiche pour le site web de support technique dans la page **Contacter le service informatique** du Portail d’entreprise.|
    |Nom du site web|40|Il s'agit du nom convivial qui s'affiche pour l'URL permettant d'accéder au site Web de support technique. Si vous spécifiez l’URL d’un site web de support technique sans aucun nom convivial, **Accéder au site web du service informatique** apparaît dans la page **Contacter le service informatique** du Portail d’entreprise.|

## Personnalisation de l’image de la société
Vous pouvez personnaliser votre Portail d’entreprise avec le logo et le nom de votre société, un thème chromatique et un arrière-plan.

|Nom du champ|Plus d'informations|
    |----------|----------------|
    |Couleur de thème|Sélectionnez une couleur de thème à appliquer au Portail d’entreprise.|
    |Inclure le logo de l'entreprise|Lorsque vous activez cette option, vous pouvez télécharger le logo de votre entreprise pour qu’il apparaisse sur le Portail de celle-ci. Vous pouvez télécharger deux logos : un qui s’affiche quand l’arrière-plan du Portail d’entreprise est blanc, et un autre qui s’affiche quand l’arrière-plan du Portail d’entreprise utilise la couleur de thème que vous avez sélectionnée. Chaque logo doit être un fichier de type .png ou .jpg, et avoir une résolution maximale de 400 x 100 pixels et une taille inférieure ou égale à 750 Ko .|
    |Choisir un arrière-plan pour l'application Portail d'entreprise [!INCLUDE[win8_client_2](../includes/win8_client_2_md.md)]|Ce paramètre affecte l’arrière-plan de l’application Portail d’entreprise [!INCLUDE[win8_client_2](../includes/win8_client_2_md.md)] uniquement.|


Après avoir enregistré vos modifications, vous pouvez utiliser les liens proposés au bas de la page **Portail d’entreprise** de la console d’administration pour afficher le site web du Portail d’entreprise. Ces liens ne peuvent pas être modifiés. Lorsqu’un utilisateur se connecte, ces liens présentent vos abonnements dans le Portail d’entreprise.

### Étapes suivantes
Félicitations ! Vous venez d’effectuer l’étape 7 du *guide de démarrage rapide Intune*.
>[!div class="step-by-step"]

>[&larr; **Créer des applications et des stratégies**](.\start-with-a-paid-subscription-to-microsoft-intune-step-6.md)       [**Inscrire des appareils** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-8.md)  


<!--HONumber=May16_HO1-->


