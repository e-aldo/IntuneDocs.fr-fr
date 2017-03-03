---
title: Inscrire des appareils Windows
titleSuffix: Intune Azure preview
description: "Version préliminaire  d’Intune Azure : activez la gestion des appareils mobiles (MDM) pour les appareils Windows."
keywords: 
author: staciebarker
manager: stabar
ms.date: 02/15/17
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f94dbc2e-a855-487e-af6e-8d08fabe6c3d
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: 7262093700dab3a7befd5b82ac9f8ee3dde22dcf


---

# <a name="enroll-windows-devices"></a>Inscrire des appareils Windows 

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Pour configurer l’inscription pour les appareils Windows, utilisez l’une des méthodes suivantes :

- [**Inscription automatique de Windows 10 et Windows 10 Mobile avec Azure Active Directory Premium**](#set-up-windows-10-and-windows-10-mobile-automatic-enrollment-with-azure-active-directory-premium)
 -  Cette méthode s’applique uniquement aux appareils Windows 10 et Windows 10 Mobile.
 -  Vous devez disposer d’Azure Active Directory Premium pour utiliser cette méthode. Sinon, utilisez la méthode d’inscription pour Windows 8.1 et Windows Phone 8.1.
 -  Si vous choisissez de ne pas activer l’inscription automatique, utilisez la méthode d’inscription pour Windows 8.1 et Windows Phone 8.1.

- [**Inscription Windows 8.1 et Windows Phone 8.1 en configurant l’enregistrement CNAME**](#set-up-windows-81-and-windows-phone-81-enrollment-by-configuring-cname)
 - Vous devez utiliser cette méthode pour inscrire des appareils Windows 8.1 et Windows Phone 8.1.


## <a name="prerequisites"></a>Conditions préalables

Si certaines des conditions préalables suivantes ne sont pas encore dans la version préliminaire d’Intune Azure, vous devrez les exécuter à partir de la console d’administration Intune classique.

- [Configurer un nom de domaine personnalisé](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-2)
- [Définir l’autorité de gestion des appareils mobiles](set-mdm-authority.md) sur **Microsoft Intune**
- [Configurer l’application Portail d’entreprise](/intune-azure/manage-apps/company-portal-app.md)
- Affecter des licences aux utilisateurs

[!INCLUDE[AAD-enrollment](../includes/win10-automatic-enrollment-aad.md)]

## <a name="set-up-windows-81-and-windows-phone-81-enrollment-by-configuring-cname"></a>Configurer l’inscription Windows 8.1 et Windows Phone 8.1 en configurant l’enregistrement CNAME

Vous pouvez permettre aux utilisateurs d’installer et d’inscrire leurs appareils à l’aide du Portail d’entreprise Intune. Si vous créez des enregistrements de ressources CNAME DNS, les utilisateurs se connectent et s’inscrivent à Intune sans entrer un nom de serveur.

1. **Créer des enregistrements CNAME** (facultatif)<br>
 Créez des enregistrements de ressources **CNAME** DNS pour le domaine de votre entreprise. Par exemple, si le site web de votre entreprise est contoso.com, vous devez créer un enregistrement CNAME DNS qui redirige EnterpriseEnrollment.contoso.com vers EnterpriseEnrollment-s.manage.microsoft.com.

    Bien que la création d’entrées DNS CNAME soit facultative, les enregistrements CNAME facilitent l’inscription pour les utilisateurs. Si aucun enregistrement CNAME d’inscription n’est trouvé, les utilisateurs sont invités à taper le nom du serveur de gestion des appareils mobiles (enrollment.manage.microsoft.com).

    S'il existe plusieurs domaines vérifiés, créez un enregistrement CNAME pour chaque domaine. Ces enregistrements doivent contenir les informations suivantes :

    Les enregistrements de ressources CNAME doivent avoir les informations suivantes :

  |TYPE|Nom d'hôte|Pointe vers|TTL|
  |--------|-------------|-------------|-------|
  |CNAME|enterpriseenrollment.domaine_entreprise.com|EnterpriseEnrollment-s.manage.microsoft.com |1 heure|
  |CNAME|EnterpriseRegistration.domaine_entreprise.com|EnterpriseRegistration.windows.net|1 heure|

  `EnterpriseEnrollment-s.manage.microsoft.com` : prend en charge une redirection vers le service Intune avec reconnaissance du domaine à partir du nom de domaine de l’e-mail.

  `EnterpriseRegistration.windows.net` : prend en charge les appareils Windows 8.1 et Windows 10 Mobile qui s’inscrivent auprès d’Azure Active Directory avec leur compte professionnel ou scolaire.

  Si votre entreprise utilise plusieurs domaines pour les informations d’identification de l’utilisateur, créez des enregistrements CNAME pour chaque domaine.

  Par exemple, si le site web de votre entreprise est contoso.com, vous devez créer un enregistrement CNAME dans DNS qui redirige EnterpriseEnrollment.contoso.com vers EnterpriseEnrollment-s.manage.microsoft.com. La propagation des modifications DNS peut prendre jusqu’à 72 heures. Vous ne pouvez pas vérifier la modification DNS dans Intune tant que l’enregistrement DNS ne s’est pas propagé.

2.  **Vérifier un enregistrement CNAME**<br>Dans la [console d’administration Microsoft Intune](http://manage.microsoft.com), choisissez **Administration** &gt; **Gestion des appareils mobiles** &gt; **Windows Phone**. Entrez l’URL du domaine vérifié du site web de l’entreprise dans la zone **Spécifiez un nom de domaine vérifié**, puis choisissez **Auto-détection de test**.

3.  **Étapes facultatives**<br>L’étape **Ajouter des clés de déploiement (sideloading)** n’est pas nécessaire pour Windows 10. <br>L’étape **Télécharger un certificat de signature de code** est uniquement nécessaire si vous voulez distribuer des applications métier non disponibles depuis le Windows Store à des appareils.

4.  **Informez vos utilisateurs sur la manière d’inscrire leurs appareils et sur les principes de gestion des appareils.**

    Pour obtenir des instructions d’inscription pour l’utilisateur final, consultez [Inscrire un appareil Windows dans Intune](https://docs.microsoft.com/en-us/intune/enduser/enroll-your-device-in-intune-windows). Vous pouvez également diriger les utilisateurs vers la rubrique [Que voit mon administrateur informatique quand j’inscris mon appareil ?](https://docs.microsoft.com/intune/enduser/what-can-your-it-administrator-see-when-you-enroll-your-device-in-intune-windows).

    Pour plus d’informations sur les tâches de l’utilisateur final, consultez [Ressources concernant l’expérience utilisateur final avec Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/what-to-tell-your-end-users-about-using-microsoft-intune).

Aucun travail supplémentaire n’est requis sauf si vous déployez le Portail d’entreprise sur les appareils.  Les étapes 2 et 3 dans la console d’administration peuvent être ignorées en toute sécurité.



<!--HONumber=Feb17_HO3-->


