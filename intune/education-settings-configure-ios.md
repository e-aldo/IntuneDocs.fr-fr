---
title: "Paramètres Intune pour l’application iOS Classroom"
titlesuffix: Azure portal
description: "Découvrez les paramètres Intune qui vous permettent de contrôler les paramètres pour l’application Classroom sur les appareils iOS."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 06/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1381a5ce-c743-40e9-8a10-4c218085bb5f
ms.reviewer: derriw
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1ea9c38fc7d2dd82171d4018cfe1048c8f139386
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/09/2017
---
# <a name="how-to-configure-intune-settings-for-the-ios-classroom-app"></a>Guide pratique pour configurer des paramètres Intune pour l’application iOS Classroom

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <a name="introduction"></a>Introduction
[Classroom](https://itunes.apple.com/app/id1085319084) est une application qui permet aux enseignants d’orienter l’apprentissage et de contrôler les appareils des étudiants dans la salle de classe. Par exemple, à l’aide de l’application,un enseignant peut :

- ouvrir des applications sur les appareils des étudiants ;
- verrouiller et déverrouiller l’écran de l’iPad ;
- afficher l’écran de l’iPad d’un étudiant ;
- diriger les iPad des étudiants vers un signet ou le chapitre d’un livre ;
- afficher l’écran de l’iPad d’un étudiant sur Apple TV.

Utilisez le profil d’appareil **Éducation** iOS d’Intune et les informations de cette rubrique pour vous aider à configurer l’application Classroom et les appareils sur lesquels vous l’utilisez.

## <a name="before-you-start"></a>Avant de commencer

Tenez compte des éléments suivants avant de commencer à configurer ces paramètres :

- Les iPad des enseignants et étudiants doivent être inscrits dans Intune
- Vérifiez que vous avez installé l’application [Apple Classroom](https://itunes.apple.com/us/app/classroom/id1085319084?mt=8) sur l’appareil de l’enseignant. Vous pouvez installer l’application manuellement ou utiliser la [gestion des applications Intune](app-management.md).
- Vous devez configurer des certificats pour authentifier les connexions entre les appareils des enseignants et étudiants (consultez l’étape 2)
- Les iPad des enseignants et étudiants doivent être situés sur le même réseau Wi-Fi, et Bluetooth doit également être activé
- L’application Classroom fonctionne sur des iPad supervisés exécutant iOS 9.3 ou version ultérieure
- Dans cette version, Intune prend en charge la gestion d’un scénario 1:1 où chaque étudiant a son propre iPad dédié


## <a name="step-1---import-your-school-data-into-azure-active-directory"></a>Étape 1 : Importer vos données scolaires dans Azure Active Directory

Utilisez SDS (School Data Sync) de Microsoft pour importer des dossiers scolaires d’un système SIS (Student Information System) existant vers Azure AD (Azure Active Directory).
SDS synchronise les informations de votre SIS et les stocke dans Azure AD. Azure AD est un système de gestion Microsoft qui vous permet d’organiser les utilisateurs et les appareils. Vous pouvez ensuite utiliser ces données pour vous aider à gérer les étudiants et cours. [En savoir plus sur le déploiement de SDS](https://support.office.com/article/Overview-of-School-Data-Sync-and-Classroom-f3d1147b-4ade-4905-8518-508e729f2e91).

### <a name="how-to-import-data-using-sds"></a>Comment importer des données à l’aide de SDS ?

Vous pouvez importer des informations dans SDS en appliquant l’une des méthodes suivantes :

- [Fichiers CSV](https://support.office.com/article/Follow-these-steps-71d5fe4a-aa51-4f35-9b53-348898a390a1) : exportez et compilez manuellement des fichiers de valeurs séparées par des virgules (.csv)
- [API PowerSchool](https://support.office.com/article/Follow-these-steps-851b5edc-558f-43a9-9122-b2d63458cb8f) : fournisseur SIS qui simplifie la synchronisation avec Azure AD
- [API Clever](https://support.office.com/article/Follow-these-steps-f3d92fde-3ad0-48f3-80a1-1ad0ac4a3fae) : solution de gestion des identités qui synchronise directement avec Azure AD
- [OneRoster](https://support.office.com/article/Follow-these-steps-f43cbb2a-b502-497d-a8b1-783dc05a57ab) : format CSV que vous pouvez exporter et convertir pour la synchronisation avec Azure AD

### <a name="find-out-more"></a>En savoir plus

- [En savoir plus sur l’expérience complète de la synchronisation des données scolaires locales avec Azure AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)
- [En savoir plus sur School Data Sync de Microsoft](https://sds.microsoft.com/)
- [En savoir plus sur les licences dans Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal)

## <a name="step-2---create-and-assign-an-ios-education-profile-in-intune"></a>Étape 2 : Créer et affecter un profil Éducation iOS dans Intune

### <a name="configure-general-settings"></a>Configurer les paramètres généraux

1. Connectez-vous au portail Azure.
2. Choisissez **Plus de services** > **Surveillance + Gestion** > **Intune**.
3.  Dans le panneau **Intune**, choisissez **Configurer des appareils**.
4.  Dans le panneau **Configuration de l’appareil**, choisissez **Gérer** > **Profils**.
5.  Dans le panneau des profils, sélectionnez **Créer un profil**.
6.  Dans le panneau **Créer un profil**, entrez un **Nom** et une **Description** pour le profil Éducation iOS.
7.  Dans la liste déroulante **Plateforme**, choisissez **iOS**.
8.  Dans la liste déroulante **Type de profil**, choisissez **Education**.
9.  Choisissez **Paramètres** > **Configurer**.


Vous avez ensuite besoin de certificats pour établir une relation d’approbation entre les iPad des enseignants et étudiants. Les certificats sont utilisés pour authentifier de manière fluide et silencieuse les connexions entre les appareils sans avoir à entrer les noms d’utilisateur et mots de passe.

>[!IMPORTANT]
>Les certificats des enseignants et étudiants que vous utilisez doivent être émis par différentes autorités de certification. Vous devez créer deux autorités de certification subordonnées connectées à votre infrastructure de certificats existante : une pour les enseignants et une pour les étudiants.

Les profils Éducation iOS prennent en charge uniquement les certificats PFX. Les certificats SCEP ne sont pas pris en charge.

Les certificats que vous créez doivent prendre en charge l’authentification du serveur en plus de l’authentification de l’utilisateur.

### <a name="configure-teacher-certificates"></a>Configurer des certificats d’enseignant

Dans le panneau **Éducation**, choisissez **Certificats d’enseignant**.

#### <a name="configure-teacher-root-certificate"></a>Configurer le certificat racine de l’enseignant

Sous **Certificat racine d’enseignant**, cliquez sur le bouton Parcourir pour sélectionner le certificat racine de l’enseignant avec l’extension .cer (DER ou codé en Base64), ou .P7B (avec ou sans la chaîne complète).

#### <a name="configure-teacher-pkcs12-certificate"></a>Configurer le certificat PKCS#12 de l’enseignant

Sous **Certificat PKCS#12 d’enseignant**, configurez les valeurs suivantes :

- **Format du nom de l’objet** : Intune ajoute automatiquement **organisateur** comme préfixe au nom commun du certificat pour le certificat de l’enseignant, et **membre** pour le certificat de l’étudiant.
- **Autorité de certification** : autorité de certification d’entreprise qui s’exécute sur une édition Entreprise de Windows Server 2008 R2 ou version ultérieure. Une autorité de certification autonome n'est pas prise en charge. 
- **Nom de l’autorité de certification** : entrez le nom de votre autorité de certification.
- **Nom du modèle de certificat** : entrez le nom d’un modèle de certificat qui a été ajouté à une autorité de certification émettrice. 
- **Seuil de renouvellement (%)** : spécifiez le pourcentage de durée de vie restante du certificat avant que l’appareil ne demande le renouvellement du certificat.
- **Période de validité du certificat** : spécifiez la quantité de temps restant avant l’expiration du certificat.
Vous pouvez spécifier une valeur inférieure à la période de validité du modèle de certificat spécifié, mais pas une valeur supérieure. Par exemple, si la période de validité du certificat dans le modèle de certificat est de 2 ans, vous pouvez spécifier une valeur de 1 an mais pas une valeur de 5 ans. La valeur doit également être inférieure à la période de validité restante du certificat de l’autorité de certification émettrice.

Quand vous avez terminé la configuration des certificats, choisissez **OK**.

### <a name="configure-student-certificates"></a>Configurer des certificats d’étudiant

1.  Dans le panneau **Éducation**, choisissez **Certificats d’étudiant**.
2.  Dans le panneau **Certificats d’étudiant**, dans la liste **Type de certificat d’appareil étudiant**, choisissez **1:1**.

#### <a name="configure-student-root-certificate"></a>Configurer le certificat racine de l’étudiant

Sous **Certificat racine d’étudiant**, cliquez sur le bouton Parcourir pour sélectionner le certificat racine de l’étudiant avec l’extension .cer (DER ou codé en Base64), ou .P7B (avec ou sans la chaîne complète).

#### <a name="configure-student-pkcs12-certificate"></a>Configurer le certificat PKCS#12 de l’étudiant

Sous **Certificat PKCS#12 d’étudiant**, configurez les valeurs suivantes :

- **Format du nom de l’objet** : Intune ajoute automatiquement **organisateur** comme préfixe au nom commun du certificat pour le certificat de l’enseignant, et **membre** pour le certificat de l’étudiant.
- **Autorité de certification** : autorité de certification d’entreprise qui s’exécute sur une édition Entreprise de Windows Server 2008 R2 ou version ultérieure. Une autorité de certification autonome n'est pas prise en charge. 
- **Nom de l’autorité de certification** : entrez le nom de votre autorité de certification.
- **Nom du modèle de certificat** : entrez le nom d’un modèle de certificat qui a été ajouté à une autorité de certification émettrice. 
- **Seuil de renouvellement (%)** : spécifiez le pourcentage de durée de vie restante du certificat avant que l’appareil ne demande le renouvellement du certificat.
- **Période de validité du certificat** : spécifiez la quantité de temps restant avant l’expiration du certificat.
Vous pouvez spécifier une valeur inférieure à la période de validité du modèle de certificat spécifié, mais pas une valeur supérieure. Par exemple, si la période de validité du certificat dans le modèle de certificat est de 2 ans, vous pouvez spécifier une valeur de 1 an mais pas une valeur de 5 ans. La valeur doit également être inférieure à la période de validité restante du certificat de l’autorité de certification émettrice.

Quand vous avez terminé la configuration des certificats, choisissez **OK**.

## <a name="finish-up"></a>Terminer

1.  Dans le panneau **Éducation**, choisissez OK.
2.  Dans le panneau **Créer un profil**, choisissez **Créer**.
    
Le profil est créé et s’affiche dans le panneau de la liste des profils.

Affectez le profil aux appareils des étudiants dans les groupes de salle de classe qui ont été créés quand vous avez synchronisé vos données scolaires avec Azure AD (consultez [Guide pratique pour attribuer des profils d’appareil](device-profile-assign.md).

## <a name="next-steps"></a>Étapes suivantes

Maintenant, quand un enseignant utilise l’application Classroom, il a un contrôle total sur les appareils des étudiants.

Pour plus d’informations sur l’application Classroom, consultez [Aide En classe](https://help.apple.com/classroom/ipad/2.0/) sur le site web Apple.

Si vous souhaitez configurer des appareils iPad partagés pour les étudiants, consultez [Guide pratique pour configurer les paramètres d’éducation Intune pour les appareils iPad partagés](education-settings-configure-ios-shared.md).
