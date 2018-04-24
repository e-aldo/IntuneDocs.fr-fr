---
title: Conditions préalables pour l’inscription des appareils mobiles
description: Configurez les conditions préalables à la gestion d’appareils mobiles, puis préparez-vous à inscrire différents systèmes d’exploitation.
keywords: ''
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 05/31/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 44fd4af0-f9b0-493a-b590-7825139d9d40
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 57dfc1bf2765de6c2e02352caca58f3859742fd6
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2018
---
# <a name="prerequisites-for-mobile-device-management-in-intune"></a>Conditions préalables à la gestion d’appareils mobiles dans Intune

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Vous pouvez permettre aux employés d’inscrire leurs appareils mobiles auprès d’Intune en appliquant la procédure suivante. Ces mêmes étapes sont nécessaires pour gérer les appareils d’entreprise.

|Étapes|Détails|  
|-----------|-------------|  
|**Étape 1 :** [Activer les connexions](#step-1-enable-connections)|Vérifiez que votre nom de domaine personnalisé est configuré et que la communication réseau est prête.|  
|**Étape 2 :** [Définir l’autorité MDM](#step-2-set-mdm-authority)|L’autorité de gestion des appareils mobiles définit le service affecté à vos appareils.|
|**Étape 3 :** [Créer des groupes](#step-3-create-groups)|Configurer les paramètres utilisateur pour l’application Portail d’entreprise|  
|**Étape 4 :** [Configurer le portail d’entreprise](#step-4-configure-company-portal)|Configurer les paramètres utilisateur pour l’application Portail d’entreprise|  
|**Étape 5 :** [Affecter des licences utilisateur](#step-5-assign-user-licenses)|Affecter des licences Intune aux utilisateurs pour qu’ils puissent inscrire des appareils|
|**Étape 6 :** [Activer l’inscription](#step-6-enable-enrollment)|Activez les paramètres spécifiques à la plateforme pour la gestion d’iOS et de Windows. Les appareils Android ne nécessitent pas de configuration supplémentaire.|
|**Étape 7 :** [Étapes suivantes](#step-7-next-steps)|Activez les paramètres spécifiques à la plateforme pour la gestion d’iOS et de Windows. Les appareils Android ne nécessitent pas de configuration supplémentaire.|

Vous recherchez Intune avec Configuration Manager ?
> [!div class="button"]
> [Consultez les documents SCCM >](https://docs.microsoft.com/sccm/mdm/deploy-use/setup-hybrid-mdm)

## <a name="step-1-enable-connections"></a>Étape 1 : Activer les connexions

Avant d’activer l’inscription d’appareils mobiles, vérifiez que vous avez bien effectué les tâches suivantes :
- [Passer en revue les URL et les ports du réseau](/intune/network-bandwidth-use)
- [Ajouter et vérifier votre nom de domaine](/intune/custom-domain-name-configure)

## <a name="step-2-set-mdm-authority"></a>Étape 2 : Définir l’autorité MDM
L’autorité MDM définit le service de gestion habilité à gérer un ensemble d’appareils. Les options en matière d’autorité de gestion des appareils mobiles incluent Intune en version autonome et Configuration Manager avec Intune. Si vous définissez Configuration Manager comme autorité de gestion, aucun autre service ne peut être utilisé pour la gestion des appareils mobiles.

>[!IMPORTANT]
> Dans Configuration Manager version 1610 ou ultérieure et Microsoft Intune version 1705, vous pouvez modifier l’autorité de GPM sans avoir à contacter le Support Microsoft où à désinscrire et réinscrire vos appareils déjà gérés. Pour plus d’informations, consultez la page [Que faire si vous choisissez le mauvais paramètre d’autorité de GPM](/intune-classic/deploy-use/prerequisites-for-enrollment#what-to-do-if-you-choose-the-wrong-mdm-authority-setting).

1.  Dans la [console d’administration Microsoft Intune](https://manage.microsoft.com), choisissez **Administration** &gt; **Gestion des appareils mobiles**.

2.  Dans la liste **Tâches** , cliquez sur **Définir l'autorité de gestion des appareils mobiles**. La boîte de dialogue **Définir l'autorité MDM** s'ouvre.

    ![Boîte de dialogue Définir l’autorité MDM](../media/intune-mdm-authority.png)

3.  Intune vous invite à confirmer que vous souhaitez définir Intune comme autorité MDM. Cochez la case, puis choisissez **Oui** pour utiliser Microsoft Intune pour gérer les appareils mobiles.

## <a name="step-3-create-groups"></a>Étape 3 : Créer des groupes

Vous pouvez créer des groupes d’utilisateurs et d’appareils pour simplifier la gestion et améliorer le ciblage des stratégies, des ressources d’entreprise et des applications déployées. [Découvrez comment créer des groupes](use-groups-to-manage-users-and-devices-with-microsoft-intune.md#create-groups).

## <a name="step-4-configure-company-portal"></a>Étape 4 : Configurer le portail d’entreprise

Le portail d’entreprise Intune permet aux utilisateurs d’accéder aux données de l’entreprise et d’effectuer des tâches courantes, notamment l’inscription d’appareils, l’installation d’applications et d’accéder à des informations d’assistance fournies par le département informatique.

> [!TIP]
> Quand vous personnalisez le Portail d’entreprise, les configurations s’appliquent au site web du Portail d’entreprise et aux applications du Portail d’entreprise.

La personnalisation du Portail d’entreprise permet de fournir une expérience familière et utile à vos utilisateurs finaux. Pour ce faire, connectez-vous à la [console d’administration Microsoft Intune](https://manage.microsoft.com) comme administrateur du service ou client, choisissez **Administration** &gt; **Portail d’entreprise** et configurez les paramètres du portail d’entreprise.

![admin-console-admin-workspace-comp-portal-settings](../media/cp_sa_cpsetup.PNG)

### <a name="company-contact-information-and-privacy-statement"></a>Informations de contact et déclaration de confidentialité de l'entreprise

Le nom de l’entreprise s’affiche comme titre du Portail d’entreprise. Les informations de contact et les détails sont présentés aux utilisateurs dans l’écran Contacter le service informatique du Portail d’entreprise. La déclaration de confidentialité s’affiche lorsqu’un utilisateur clique sur le lien correspondant.


|          Nom du champ           | Longueur maximale |                                                                                       Autres informations                                                                                        |
|-------------------------------|------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|         Nom de la société          |     40     |                Ce nom s’affiche comme titre du Portail d’entreprise. <strong>Remarque</strong> : Seuls des caractères alphanumériques peuvent être utilisés. Ce champ n’accepte pas les caractères spéciaux.                |
|  Nom du contact du service informatique   |     40     |                                                                Ce nom s’affiche dans la page <strong>Contacter le service informatique</strong>.                                                                |
|  Numéro de téléphone du service informatique   |     20     |                                                           Ce numéro s’affiche dans la page <strong>Contacter le service informatique</strong>.                                                           |
|  Adresse de messagerie du service informatique  |     40     |             Cette adresse s’affiche dans la page <strong>Contacter le service informatique</strong>. Vous devez entrer une adresse e-mail valide au format <strong>alias@domainname.com</strong>.              |
|    Informations complémentaires     |    120     |                                                            Ces informations s'affichent sur la page <strong>Contacter l’administrateur</strong>.                                                             |
| URL de la déclaration de confidentialité de l'entreprise |     79     | Vous pouvez spécifier la déclaration de confidentialité de votre entreprise qui s’affiche lorsque les utilisateurs cliquent sur les liens de confidentialité à partir du Portail d’entreprise. Vous devez entrer une URL valide au format https://www.contoso.com. |

### <a name="support-contacts"></a>Contacts du support
Les utilisateurs peuvent voir le lien du site web de support dans le Portail d’entreprise et l’utiliser pour accéder au support en ligne.

|Nom du champ|Longueur maximale|Autres informations|
    |----------|------------------------|----------------|
    |URL du site Web de support technique|150|Si vous avez un site web de support technique auquel vous aimeriez que les utilisateurs accèdent, spécifiez cette URL ici. Elle doit être au format https://www.contoso.com. Si vous ne spécifiez aucune URL, rien ne s’affiche pour le site web de support technique dans la page **Contacter le service informatique** du Portail d’entreprise.|
    |Nom du site web|40|Il s'agit du nom convivial qui s'affiche pour l'URL permettant d'accéder au site Web de support technique. Si vous spécifiez l’URL d’un site web de support technique sans aucun nom convivial, **Accéder au site web du service informatique** apparaît dans la page **Contacter le service informatique** du Portail d’entreprise.|


### <a name="company-branding-customization"></a>Personnalisation de l’image de la société

Vous pouvez personnaliser votre Portail d’entreprise avec le logo et le nom de votre entreprise, un thème chromatique et un arrière-plan.

|Nom du champ|Autres informations|
    |----------|----------------|
    |Couleur de thème|Sélectionnez une couleur de thème à appliquer au Portail d’entreprise.|
    |Inclure le logo de l'entreprise|Lorsque vous activez cette option, vous pouvez télécharger le logo de votre entreprise pour qu’il apparaisse sur le Portail de celle-ci. Vous pouvez télécharger deux logos : un qui s’affiche quand l’arrière-plan du Portail d’entreprise est blanc, et un autre qui s’affiche quand l’arrière-plan du Portail d’entreprise utilise la couleur de thème que vous avez sélectionnée. Chaque logo doit être un fichier .png ou .jpg et avoir une résolution maximale de 400 x 100 pixels et une taille inférieure ou égale à 750 Ko.|
    |Choisir un arrière-plan pour l’application Portail d’entreprise|Ce paramètre affecte seulement l’arrière-plan de l’application Portail d’entreprise.|


Après avoir enregistré vos modifications, vous pouvez utiliser les liens proposés au bas de la page **Portail d’entreprise** de la console d’administration pour afficher le site web du Portail d’entreprise. Ces liens ne peuvent pas être modifiés. Lorsqu’un utilisateur se connecte, ces liens présentent vos abonnements dans le Portail d’entreprise.

## <a name="step-5-assign-user-licenses"></a>Étape 5 : Affecter des licences utilisateur

Utilisez le **portail de gestion Office 365** pour ajouter manuellement des utilisateurs basés sur le cloud et attribuer des licences aux comptes d’utilisateur basés sur le cloud et aux comptes synchronisés à partir de votre annuaire Active Directory local vers Azure AD. Vous pouvez [synchroniser des utilisateurs locaux avec Azure AD](/intune/users-permissions-add#how-to-sync-on-premises-users-with-azure-ad).

1.  Connectez-vous au [portail de gestion Office 365](https://portal.office.com/Admin/Default.aspx) à l’aide de vos informations d’identification d’administrateur client.

2.  Sélectionnez le compte d’utilisateur auquel vous souhaitez attribuer une licence utilisateur Intune et cochez la case **Microsoft Intune** dans les propriétés du compte utilisateur.

3.  Le compte d’utilisateur est alors ajouté au groupe d’utilisateurs Microsoft Intune qui autorise l’utilisateur à utiliser le service et à inscrire ses appareils pour les gérer.

### <a name="to-synchronize-on-premises-users-with-azure-ad"></a>Pour synchroniser des utilisateurs locaux avec Azure AD

1. [Ajoutez le suffixe UPN](https://technet.microsoft.com/library/cc772007.aspx) de votre domaine personnalisé dans votre annuaire Active Directory local.
2. Définissez le nouveau suffixe UPN pour les utilisateurs locaux que vous voulez importer.
3. Exécutez la [synchronisation Azure AD Connect](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect/) pour intégrer vos utilisateurs locaux à Azure AD.
4. Une fois les informations sur le compte d’utilisateur correctement synchronisées, vous pouvez attribuer des licences Microsoft Intune à l’aide du [portail de gestion Office 365](https://portal.office.com/Admin/Default.aspx).

## <a name="step-6-enable-enrollment"></a>Étape 6 : Activer l’inscription
Après avoir configuré l’autorité de gestion des appareils mobiles, vous devez configurer la gestion des appareils pour les systèmes d’exploitation que votre organisation souhaite prendre en charge. Les étapes requises pour configurer la gestion des appareils varient selon le système d’exploitation. Par exemple, le système d’exploitation Android ne vous demande d’effectuer aucune opération dans la console d’administration Intune. En revanche, iOS et Windows nécessitent une relation d’approbation entre les appareils et Intune pour autoriser la gestion.

Configurez la gestion pour les plateformes suivantes :
- [iOS et Mac](set-up-ios-and-mac-management-with-microsoft-intune.md)
- [Android](set-up-android-management-with-microsoft-intune.md)
- [Android for Work](set-up-android-for-work.md)
- [Windows 10 Mobile et Windows Phone](set-up-windows-device-management-with-microsoft-intune.md)
- [PC et ordinateurs portables Windows](manage-windows-pcs-with-microsoft-intune.md) (Logiciel client Intune)

Vous pouvez également activer l’[inscription d’appareils d’entreprise](manage-corporate-owned-devices.md).

## <a name="step-7-next-steps"></a>Étape 7 : Étapes suivantes

L’inscription étant activée, vous devez configurer la gestion en fonction des besoins de votre entreprise. Voici certaines options de gestion :

- [Déployer des stratégies qui gèrent des paramètres et des fonctionnalités sur les appareils](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)
- [Activer l’accès aux ressources d’entreprise telles que l’e-mail, le Wi-Fi et VPN](enable-access-to-company-resources-with-microsoft-intune.md)
- [Ajouter des applications](add-apps.md) et [déployer une application](deploy-apps.md) sur des appareils gérés
- [Créer des stratégies de conformité des appareils](introduction-to-device-compliance-policies-in-microsoft-intune.md) et [restreindre l’accès en fonction de la conformité](restrict-access-to-email-and-o365-services-with-microsoft-intune.md)

## <a name="what-to-do-if-you-choose-the-wrong-mdm-authority-setting"></a>Que faire si vous choisissez le mauvais paramètre d’autorité MDM

Si vous pensez avoir choisi le mauvais paramètre d’autorité de GPM et que vous devez le changer, les options suivantes s’offrent à vous.

### <a name="change-the-mdm-authority-yourself"></a>Modifier l’autorité de GPM vous-même
À compter de Configuration Manager version 1610 et de Microsoft Intune version 1705, vous pouvez modifier l’autorité de GPM pour passer de Microsoft Intune à Configuration Manager (hybride) et vice versa sans avoir à contacter le Support Microsoft ou à désinscrire et réinscrire vos appareils déjà gérés. Pour plus d’informations, consultez la page [Modifier l’autorité de GPM]( /sccm/mdm/deploy-use/change-mdm-authority).

### <a name="contact-microsoft-support"></a>Contacter le support Microsoft
Si Configuration Manager est antérieur à la version 1610, vous devez contacter le Support Microsoft. Vous ne pouvez pas changer vous-même ce paramètre. Avant de contacter le Support Microsoft, consultez les informations suivantes, que le Support Microsoft vous demandera de lui indiquer pour effectuer le changement.

Il existe trois façons possibles de réinitialiser votre autorité MDM. Dans votre demande de support, vous devez choisir celle qui s’applique à votre situation. Si le scénario que vous rencontrez n’est pas listé, poursuivrez avec le Support Microsoft.

Le Support Microsoft vous demandera de confirmer les informations suivantes :

- ID de client : domaine utilisé pour vous connecter au service (par exemple, intune.onmicrosoft.com)
- L’autorité MDM que vous souhaitez définir
- Confirmation des étapes relatives aux prérequis que vous avez effectuées, comme indiqué ci-dessous

En cas de coexistence, vous devez vérifier les deux listes de contrôle Intune et Office 365.

#### <a name="reset-mdm-authority-from-intune-to-configuration-manager"></a>Réinitialiser l’autorité MDM à partir de Configuration Manager

Effectuez les étapes suivantes avant de contacter le Support Microsoft pour réinitialiser votre autorité MDM.

- Mettez hors service tous les appareils à partir de la console d’administration Intune. N’essayez pas de mettre hors service un appareil à partir de l’appareil lui-même. 
- Supprimez le connecteur de service à service (sous **Administration** > **Gestion des appareils mobiles** > **Microsoft Exchange**), ou désactivez le connecteur Exchange si vous l’avez configuré.
- Supprimez le rôle Gestionnaire d’inscription d’appareil à partir d’**Administrateur** > **Gestionnaire d’inscription d’appareil**.
- Désactivez le mappage de groupe d’appareils dans **Administrateur** > **Gestion des appareils mobiles** > **Mappage de groupe d’appareils**.
- Supprimez les clés de chargement indépendant (sideloading) à partir d’**Administrateur** > **Gestion des appareils mobiles** > **Windows** > **Clés de chargement indépendant**.
- Supprimez le certificat APN iOS dans la page **Administrateur** > **Gestion des appareils mobiles** > **iOS**.
- Supprimez le jeton DEP iOS dans la page **Administrateur** > **Gestion des appareils mobiles** > **iOS**.
- Supprimez toutes les stratégies destinées aux appareils MDM sous **Stratégie** > **Stratégies de configuration**.
- Supprimez toutes les applications publiées destinées aux appareils MDM dans **Applications** > **Logiciels gérés**.

#### <a name="reset-mdm-authority-from-configuration-manager-to-intune"></a>Réinitialiser l’autorité MDM sur Intune à la place de Configuration Manager

Effectuez les étapes suivantes avant de contacter le Support Microsoft pour réinitialiser votre autorité MDM.

- Mettez hors service tous les appareils (qui sont gérés comme des appareils mobiles) à partir de la console Configuration Manager. N’essayez pas de mettre hors service un appareil à partir de l’appareil lui-même. 
- Supprimez tous les utilisateurs du groupe d’utilisateurs Intune. Faites pointer l’abonnement Intune sur un regroupement d’utilisateurs vide, ou supprimez tous les utilisateurs du regroupement ciblé.  Vérifiez dans le fichier CloudUserSync.log que les utilisateurs sont supprimés. 
- Décochez la plateforme iOS pour vider le certificat APNs.
- Supprimez toutes les applications publiées destinées aux appareils MDM.
- Supprimez toutes les stratégies destinées aux appareils MDM.
- Supprimez le connecteur Windows Intune à partir de la console Configuration Manager (applicable uniquement à R2 SP1 ou versions antérieures).
Supprimez l’abonnement Intune en double-cliquant sur l’abonnement, puis en sélectionnant **Supprimer**.
- Redémarrez le service SMS Executive.
- Fournissez-nous des exemples d’utilisateurs pour nous permettre de vérifier, une fois le processus terminé, que les licences Configuration Manager ont été supprimées.

#### <a name="reset-mdm-authority-from-office-365-to-configuration-manager"></a>Réinitialiser l’autorité MDM sur Configuration Manager à la place d’Office 365

1. Accédez à [https://protection.office.com](https://protection.office.com).
2. Sélectionnez l’onglet **Stratégies de sécurité**, puis **Gestion des appareils**.
3. Mettez hors service tous les appareils en choisissant **Réinitialisation sélective**. N’essayez pas de mettre hors service un appareil à partir de l’appareil lui-même. Si la réinitialisation sélective est désactivée, aucune action supplémentaire n’est nécessaire.
4. Sélectionnez l’onglet **Stratégies de sécurité**, puis **Stratégies de sécurité des appareils**.
5. Sélectionnez **Supprimer** pour toutes les stratégies existantes. Si les stratégies sont en état d’attente, aucune action supplémentaire n’est nécessaire.

>[!NOTE]
>Le certificat APNs iOS ne peut pas être supprimé et reste attaché au compte.

#### <a name="next-steps-for-mdm-authority-resets"></a>Étapes suivantes pour les réinitialisations d’autorité MDM

Une fois que le Support Microsoft vérifie les éléments de la liste de contrôle applicable, la réinitialisation de l’autorité MDM peut prendre jusqu’à trois jours ouvrés, mais elle s’effectue généralement en une journée.

>[!IMPORTANT]
>N’essayez pas de configurer votre abonnement tant que le Support Microsoft n’a pas confirmé que la réinitialisation est terminée. Une configuration prématurée peut entraîner des dysfonctionnements et/ou affecter votre possibilité d’utiliser le service Intune.
