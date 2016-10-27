---
title: "Conditions préalables à l’inscription d’appareils mobiles | Microsoft Intune"
description: "Configurez les conditions préalables à la gestion d’appareils mobiles, puis préparez-vous à inscrire différents systèmes d’exploitation."
keywords: 
author: NathBarn
manager: angrobe
ms.date: 07/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 44fd4af0-f9b0-493a-b590-7825139d9d40
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 77c8df8f1886786a2e772429d93b034798b22a66
ms.openlocfilehash: 8c500a5bfd59f801d1177a681fa9d55d1aa1ee0e


---

# Conditions préalables à la gestion d’appareils mobiles dans Intune
Vous pouvez permettre aux employés d’inscrire leurs appareils mobiles auprès d’Intune en appliquant la procédure suivante. Ces mêmes étapes sont nécessaires pour gérer les appareils d’entreprise.

|Étapes|Détails|  
|-----------|-------------|  
|**Étape 1 :** [Dépendances de l’inscription des appareils](#step-1-device-enrollment-dependencies)|Vérifiez que votre nom de domaine personnalisé est configuré et que la communication réseau est prête.|  
|**Étape 2 :** [Définir l’autorité de gestion des appareils mobiles](#step-2-set-mobile-device-management-authority)|L’autorité de gestion des appareils mobiles définit le service affecté à vos appareils.|
|**Étape 3 :** [Configurer le portail d’entreprise Intune](#step-3-configure-the-intune-company-portal)|Configurer les paramètres utilisateur pour l’application Portail d’entreprise|  
|**Étape 4 :** [Affecter des licences utilisateur Intune](#step-4-assign-intune-user-licenses)|Affecter des licences Intune aux utilisateurs pour qu’ils puissent inscrire des appareils|
|**Étape 5 :** [Configurer la gestion des appareils](#step-5-set-up-device-management)|Activez les paramètres spécifiques à la plateforme pour la gestion d’iOS et de Windows. Les appareils Android ne nécessitent pas de configuration supplémentaire.|

Vous recherchez Intune avec Configuration Manager ?
> [!div class="button"]
[Consultez les documents SCCM >](https://docs.microsoft.com/sccm/mdm/deploy-use/setup-hybrid-mdm)

## Étape 1 : Dépendances de l’inscription des appareils

Avant d’activer l’inscription d’appareils mobiles, vérifiez que vous avez bien effectué les tâches suivantes :
- [Passer en revue les URL et les ports du réseau](../get-started/network-infrastructure-requirements-for-microsoft-intune)
- [Ajouter et vérifier votre nom de domaine](../get-started/domain-names-for-microsoft-intune)

## Étape 2 : Définir l’autorité de gestion des appareils mobiles (MDM)
L’autorité MDM définit le service de gestion habilité à gérer un ensemble d’appareils. Les options en matière d’autorité de gestion des appareils mobiles incluent Intune en version autonome et Configuration Manager avec Intune. Si vous définissez Configuration Manager comme autorité de gestion, aucun autre service ne peut être utilisé pour la gestion des appareils mobiles.

>[!IMPORTANT]
> Réfléchissez bien avant de décider de gérer les appareils mobiles à l’aide d’Intune uniquement (service en ligne) ou à l’aide de System Center Configuration Manager avec Intune (solution logicielle locale avec service en ligne). Une fois qu’elle est définie, l’autorité de gestion des appareils mobiles n’est pas modifiable.



1.  Dans la [console d’administration Microsoft Intune](http://manage.microsoft.com), choisissez **Administration** &gt; **Gestion des appareils mobiles**.

2.  Dans la liste **Tâches** , cliquez sur **Définir l'autorité de gestion des appareils mobiles**. La boîte de dialogue **Définir l'autorité MDM** s'ouvre.

    ![Boîte de dialogue Définir l’autorité MDM](../media/intune-mdm-authority.png)

3.  Intune vous invite à confirmer que vous souhaitez définir Intune comme autorité MDM. Cochez la case, puis choisissez **Oui** pour utiliser Microsoft Intune pour gérer les appareils mobiles.

## Étape 3 : Configurer le portail d’entreprise Intune

Le portail d’entreprise Intune permet aux utilisateurs d’accéder aux données de l’entreprise et d’effectuer des tâches courantes, notamment l’inscription d’appareils, l’installation d’applications et d’accéder à des informations d’assistance fournies par le département informatique.

> [!TIP]
> Quand vous personnalisez le Portail d’entreprise, les configurations s’appliquent au site web du Portail d’entreprise et aux applications du Portail d’entreprise.

La personnalisation du Portail d’entreprise permet de fournir une expérience familière et utile à vos utilisateurs finaux. Pour ce faire, connectez-vous à la [console d’administration Microsoft Intune](https://manage.microsoft.com) comme administrateur du service ou client, choisissez **Administration** &gt; **Portail d’entreprise** et configurez les paramètres du portail d’entreprise.

![admin-console-admin-workspace-comp-portal-settings](../media/cp_sa_cpsetup.PNG)

### Informations de contact et déclaration de confidentialité de l'entreprise

Le nom de l’entreprise s’affiche comme titre du Portail d’entreprise. Les informations de contact et les détails sont présentés aux utilisateurs dans l’écran Contacter le service informatique du Portail d’entreprise. La déclaration de confidentialité s’affiche lorsqu’un utilisateur clique sur le lien correspondant.

|Nom du champ|Longueur maximale|Plus d'informations|
    |----------|------------------------|----------------|
    |Nom de la société|40|Ce nom s’affiche comme titre du Portail d’entreprise. **Remarque** : Seuls des caractères alphanumériques peuvent être utilisés. Ce champ n’accepte pas les caractères spéciaux.|
    |Nom du contact du service informatique|40|Ce nom s’affiche dans la page **Contacter le service informatique**.|
    |Numéro de téléphone du service informatique|20|Ce numéro s’affiche dans la page **Contacter le service informatique**.|
    |Adresse de messagerie du service informatique|40|Cette adresse s’affiche dans la page **Contacter le service informatique**. Vous devez entrer une adresse de messagerie valide au format **alias@nomdedomaine.com**.|
    |Informations supplémentaires|120|Ces informations s'affichent sur la page **Contacter l’administrateur**.|
    |URL de la déclaration de confidentialité de l'entreprise|79|Vous pouvez spécifier la déclaration de confidentialité de votre entreprise qui s’affiche lorsque les utilisateurs cliquent sur les liens de confidentialité à partir du Portail d’entreprise. Vous devez entrer une URL valide au format https://www.contoso.com.|

### Contacts du support
Les utilisateurs peuvent voir le lien du site web de support dans le Portail d’entreprise et l’utiliser pour accéder au support en ligne.

|Nom du champ|Longueur maximale|Plus d'informations|
    |----------|------------------------|----------------|
    |URL du site Web de support technique|150|Si vous avez un site web de support technique auquel vous aimeriez que les utilisateurs accèdent, spécifiez cette URL ici. L’URL doit être au format https://www.contoso.com. Si vous ne spécifiez aucune URL, rien ne s’affiche pour le site web de support technique dans la page **Contacter le service informatique** du Portail d’entreprise.|
    |Nom du site web|40|Il s'agit du nom convivial qui s'affiche pour l'URL permettant d'accéder au site Web de support technique. Si vous spécifiez l’URL d’un site web de support technique sans aucun nom convivial, **Accéder au site web du service informatique** apparaît dans la page **Contacter le service informatique** du Portail d’entreprise.|


### Personnalisation de l’image de la société

Vous pouvez personnaliser votre Portail d’entreprise avec le logo et le nom de votre entreprise, un thème chromatique et un arrière-plan.

|Nom du champ|Plus d'informations|
    |----------|----------------|
    |Couleur de thème|Sélectionnez une couleur de thème à appliquer au Portail d’entreprise.|
    |Inclure le logo de l'entreprise|Lorsque vous activez cette option, vous pouvez télécharger le logo de votre entreprise pour qu’il apparaisse sur le Portail de celle-ci. Vous pouvez télécharger deux logos : un qui s’affiche quand l’arrière-plan du Portail d’entreprise est blanc, et un autre qui s’affiche quand l’arrière-plan du Portail d’entreprise utilise la couleur de thème que vous avez sélectionnée. Chaque logo doit être un fichier .png ou .jpg et avoir une résolution maximale de 400 x 100 pixels et une taille inférieure ou égale à 750 Ko.|
    |Choisir un arrière-plan pour l’application Portail d’entreprise|Ce paramètre affecte seulement l’arrière-plan de l’application Portail d’entreprise.|


Après avoir enregistré vos modifications, vous pouvez utiliser les liens proposés au bas de la page **Portail d’entreprise** de la console d’administration pour afficher le site web du Portail d’entreprise. Ces liens ne peuvent pas être modifiés. Lorsqu’un utilisateur se connecte, ces liens présentent vos abonnements dans le Portail d’entreprise.

## Étape 4 : Affecter des licences utilisateur Intune

Utilisez le **portail de gestion Office 365** pour ajouter manuellement des utilisateurs basés sur le cloud et attribuer des licences aux comptes d’utilisateur basés sur le cloud et aux comptes synchronisés à partir de votre annuaire Active Directory local vers Azure AD. Vous pouvez [synchroniser des utilisateurs locaux avec Azure AD](../get-started/domain-names-for-microsoft-intune#to-synchronize-on-premises-users-with-azure-ad.md).

1.  Connectez-vous au [portail de gestion Office 365](https://portal.office.com/Admin/Default.aspx) à l’aide de vos informations d’identification d’administrateur client.

2.  Sélectionnez le compte d’utilisateur auquel vous souhaitez attribuer une licence utilisateur Intune et cochez la case **Microsoft Intune** dans les propriétés du compte utilisateur.

3.  Le compte d’utilisateur est alors ajouté au groupe d’utilisateurs Microsoft Intune qui autorise l’utilisateur à utiliser le service et à inscrire ses appareils pour les gérer.

### Pour synchroniser des utilisateurs locaux avec Azure AD

1. [Ajoutez le suffixe UPN](https://technet.microsoft.com/en-us/library/cc772007.aspx) de votre domaine personnalisé dans votre annuaire Active Directory local.
2. Définissez le nouveau suffixe UPN pour les utilisateurs locaux que vous voulez importer.
3. Exécutez la [synchronisation Azure AD Connect](https://azure.microsoft.com/en-us/documentation/articles/active-directory-aadconnect/) pour intégrer vos utilisateurs locaux à Azure AD.
4. Une fois les informations sur le compte d’utilisateur correctement synchronisées, vous pouvez attribuer des licences Microsoft Intune à l’aide du [portail de gestion Office 365](https://portal.office.com/Admin/Default.aspx).

## Étape 5 : Configurer la gestion des appareils
Après avoir configuré l’autorité de gestion des appareils mobiles, vous devez configurer la gestion des appareils pour les systèmes d’exploitation que votre organisation souhaite prendre en charge. Les étapes requises pour configurer la gestion des appareils varient selon le système d’exploitation. Par exemple, le système d’exploitation Android ne vous demande d’effectuer aucune opération dans la console d’administration Intune. En revanche, iOS et Windows nécessitent une relation d’approbation entre les appareils et Intune pour autoriser la gestion.

Configurez la gestion pour les plateformes suivantes :
- [Android](set-up-android-management-with-microsoft-intune.md)
- [iOS et Mac](set-up-ios-and-mac-management-with-microsoft-intune.md)
- [PC et ordinateurs portables Windows](set-up-windows-device-management-with-microsoft-intune.md)
- [Windows 10 Mobile et Windows Phone](set-up-windows-phone-management-with-microsoft-intune.md)

Vous pouvez également effectuer les opérations suivantes :
 - Utilisez le [compte de gestionnaire d’inscription d’appareil](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md) pour inscrire de nombreux appareils.
 - [Indiquez les appareils d’entreprise avec des numéros IMEI](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md) pour mieux inscrire les appareils et cibler la stratégie.



<!--HONumber=Oct16_HO2-->


