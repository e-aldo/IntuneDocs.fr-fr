---
title: Inscrire des appareils Windows
titleSuffix: Intune Azure preview
description: "Version préliminaire  d’Intune Azure : activez la gestion des appareils mobiles (MDM) pour les appareils Windows."
keywords: 
author: nathbarn
manager: nathbarn
ms.date: 04/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f94dbc2e-a855-487e-af6e-8d08fabe6c3d
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 687be18cedd063b3c2701937f2522e801e51644b
ms.contentlocale: fr-fr
ms.lasthandoff: 05/23/2017


---

# <a name="enroll-windows-devices"></a>Inscrire des appareils Windows

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Cette rubrique aide les administrateurs informatiques à simplifier l’inscription de Windows pour leurs utilisateurs.  Les appareils Windows peuvent être inscrits sans aucune étape supplémentaire, mais vous pouvez faciliter l’inscription pour les utilisateurs.

Les appareils qui exécutent Windows 10 Creators Update et qui sont joints à un domaine Azure Active Directory sont désormais pris en charge par Intune pour la gestion d’utilisateurs multiples. Cela signifie que quand différents utilisateurs standard ouvrent une session sur l’appareil avec leurs informations d’identification Azure AD, ils reçoivent les applications et les stratégies qui ont été affectées à leur nom d’utilisateur. Les utilisateurs ne peuvent actuellement pas utiliser le portail d’entreprise pour les scénarios de libre-service tels que l’installation d’applications.

Deux facteurs déterminent la manière dont vous pouvez simplifier l’inscription des appareils Windows :

- **Utilisez-vous Azure Active Directory Premium ?** <br>[Azure AD Premium](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium) est inclus avec Enterprise Mobility + Security et d’autres plans de licence.
- **Quelles versions des clients Windows allez-vous inscrire ?** <br>Les appareils Windows 10 peuvent s’inscrire automatiquement quand vous ajoutez un compte professionnel ou scolaire. L’inscription des versions antérieures doit s’effectuer à l’aide de l’application Portail d’entreprise.

||**Azure AD Premium**|**Autre AD** |
|----------|---------------|---------------|  
|**Windows 10**|[Inscription automatique](#enable-windows-10-automatic-enrollment) |[Inscription d’utilisateur](#enable-windows-enrollment-without-azure-ad-premium)|
|**Versions précédentes de Windows**|[Inscription d’utilisateur](#enable-windows-enrollment-without-azure-ad-premium)|[Inscription d’utilisateur](#enable-windows-enrollment-without-azure-ad-premium)|

[!INCLUDE[AAD-enrollment](./includes/win10-automatic-enrollment-aad.md)]

## <a name="enable-windows-enrollment-without-azure-ad-premium"></a>Activer l’inscription Windows sans Azure AD Premium
Vous pouvez permettre aux utilisateurs d’inscrire leurs appareils sans passer par l’inscription automatique Azure AD Premium. Une fois que vous affectez des licences, les utilisateurs peuvent s’inscrire après avoir ajouté leur compte professionnel sur leurs appareils personnels ou après avoir connecté leurs appareils d’entreprise à votre compte Azure AD. La création d’un alias DNS (type d’enregistrement CNAME) simplifie l’inscription des appareils pour les utilisateurs. Si vous créez des enregistrements de ressources CNAME DNS, les utilisateurs se connectent et s’inscrivent à Intune sans avoir à entrer le nom du serveur Intune.

**Étape 1 : Créer des enregistrements CNAME** (facultatif)<br>
Créez des enregistrements de ressources CNAME DNS pour le domaine de votre entreprise. Par exemple, si le site web de votre entreprise est contoso.com, vous devez créer un enregistrement CNAME DNS qui redirige EnterpriseEnrollment.contoso.com vers EnterpriseEnrollment-s.manage.microsoft.com.

Bien que la création d’entrées DNS CNAME soit facultative, les enregistrements CNAME facilitent l’inscription pour les utilisateurs. Si aucun enregistrement CNAME d’inscription n’est trouvé, les utilisateurs sont invités à taper le nom du serveur de gestion des appareils mobiles (enrollment.manage.microsoft.com).

|Type|Nom de l'hôte|Pointe vers|TTL|  
|----------|---------------|---------------|---|
|CNAME|enterpriseenrollment.domaine_entreprise.com|EnterpriseEnrollment-s.manage.microsoft.com| 1 heure|

Si vous avez plusieurs suffixes UPN, vous devez créer un enregistrement CNAME pour chaque nom de domaine et pointer chacun d’eux vers EnterpriseEnrollment-s.manage.microsoft.com. Par exemple, si les utilisateurs de Contoso utilisent name@contoso.com, mais aussi name@us.contoso.com et name@eu.constoso.com comme e-mail/UPN, l’administrateur DNS de Contoso doit créer les enregistrements CNAME suivants.

|Type|Nom de l'hôte|Pointe vers|TTL|  
|----------|---------------|---------------|---|
|CNAME|EnterpriseEnrollment.contoso.com|EnterpriseEnrollment-s.manage.microsoft.com|1 heure|
|CNAME|EnterpriseEnrollment.us.contoso.com|EnterpriseEnrollment-s.manage.microsoft.com|1 heure|
|CNAME|EnterpriseEnrollment.eu.contoso.com|EnterpriseEnrollment-s.manage.microsoft.com| 1 heure|

`EnterpriseEnrollment-s.manage.microsoft.com` : prend en charge une redirection vers le service Intune avec reconnaissance du domaine à partir du nom de domaine de l’e-mail.

La propagation des modifications DNS peut prendre jusqu’à 72 heures. Vous ne pouvez pas vérifier la modification DNS dans Intune tant que l’enregistrement DNS ne s’est pas propagé.

**Étape 2 : Vérifier les enregistrements CNAME** (facultatif)<br>
Dans le portail Azure Intune, choisissez **Plus de services** > **Surveillance + gestion** > **Intune**. Dans le panneau Intune, choisissez **Inscrire des appareils** > **Inscription Windows**. Entrez l’URL du domaine vérifié du site web de l’entreprise dans la zone **Spécifiez un nom de domaine vérifié**, puis choisissez **Auto-détection de test**.

## <a name="tell-users-how-to-enroll-windows-devices"></a>Indiquer aux utilisateurs comment inscrire des appareils Windows
Informez vos utilisateurs sur la manière d’inscrire leurs appareils Windows et sur les principes de gestion des appareils. Pour obtenir des instructions d’inscription pour l’utilisateur final, consultez [Inscrire un appareil Windows dans Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-windows). Vous pouvez également diriger les utilisateurs vers la rubrique [Que voit mon administrateur informatique quand j’inscris mon appareil ?](https://docs.microsoft.com/intune-user-help/what-can-your-it-administrator-see-when-you-enroll-your-device-in-intune-windows).

Pour plus d’informations sur les tâches de l’utilisateur final, consultez [Ressources concernant l’expérience utilisateur final avec Microsoft Intune](https://docs.microsoft.com/intune-classic/deploy-use/how-to-educate-your-end-users-about-microsoft-intune).

