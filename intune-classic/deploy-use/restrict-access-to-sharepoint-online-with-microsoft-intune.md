---
title: Protéger SharePoint Online
description: Protégez et contrôlez l’accès aux données de l’entreprise sur SharePoint Online en utilisant l’accès conditionnel.
keywords: ''
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 01/03/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: b088e5a0-fd4a-4fe7-aa49-cb9c8cfb1585
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 2b7285c272efac8eab406393b0b896795fa5d8ed
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31027974"
---
# <a name="protect-access-to-sharepoint-online-with-microsoft-intune"></a>Protéger l’accès à SharePoint Online avec Microsoft Intune

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Utilisez l’accès conditionnel Microsoft Intune pour contrôler l’accès aux fichiers situés sur SharePoint Online.
L’accès conditionnel comprend deux composants :
- Une stratégie de conformité des appareils que l’appareil doit respecter pour être considéré comme conforme.
- Une stratégie d’accès conditionnel dans laquelle vous spécifiez les conditions que l’appareil doit remplir pour accéder au service.
Pour en savoir plus sur le fonctionnement de l’accès conditionnel, lisez la rubrique [Protéger l’accès à la messagerie, à Office 365 et à d’autres services](restrict-access-to-email-and-o365-services-with-microsoft-intune.md).

Vous déployez les stratégies de conformité et d’accès conditionnel sur les utilisateurs. La conformité avec les stratégies de chaque appareil qu’un utilisateur utilise pour accéder aux services est contrôlée.

Quand un utilisateur tente de se connecter à un fichier à l’aide d’une application prise en charge, par exemple OneDrive, sur son appareil, l’évaluation suivante se produit :

![Diagramme illustrant les points de décision qui déterminent si un appareil est autorisé ou non à accéder à SharePoint](../media/ConditionalAccess8-6.png)


**Avant** de configurer une stratégie d’accès conditionnel à SharePoint Online, vous devez :
- Disposer d’un **abonnement SharePoint Online** ; les utilisateurs doivent disposer d’une licence pour SharePoint Online.
- Avoir un **abonnement Enterprise Mobility + Security (EMS)** ou un **abonnement Azure Active Directory (Azure AD)  Premium**, et les utilisateurs doivent disposer d’une licence EMS ou Azure AD. Pour plus d’informations, consultez la [page de tarification d’Enterprise Mobility](https://www.microsoft.com/cloud-platform/enterprise-mobility-pricing) ou la [page de tarification d’Azure Active Directory](https://azure.microsoft.com/pricing/details/active-directory/).


  Pour se connecter aux fichiers obligatoires, un appareil doit être :
-   **Inscrit** auprès d’Intune ou d’un PC joint à un domaine.

-   **Inscrit** dans Azure Active Directory (cela se produit automatiquement quand l’appareil est inscrit auprès d’Intune).


-   **Conforme** à toutes les stratégies de conformité Intune déployées.

L’état de l’appareil est stocké dans Azure Active Directory, qui autorise ou bloque l’accès aux fichiers en fonction des conditions spécifiées.

Si une condition n’est pas remplie, l’utilisateur reçoit l’un des messages suivants quand il tente de se connecter :

-   Si l’appareil n’est pas inscrit auprès d’Intune ni dans Azure Active Directory, l’utilisateur reçoit un message contenant des instructions pour installer l’application Portail d’entreprise et inscrire l’appareil.

-   Si l’appareil n’est pas conforme, l’utilisateur reçoit un message le dirigeant vers le site web du portail d’entreprise Intune, où il peut trouver des informations sur le problème et des solutions pour y remédier.

**L’accès conditionnel ne s’applique pas au partage externe**. Pour découvrir comment empêcher le partage externe dans votre locataire ou collection de sites, consultez [Gérer le partage externe pour votre environnement SharePoint Online](https://support.office.com/article/Manage-external-sharing-for-your-SharePoint-Online-environment-C8A462EB-0723-4B0B-8D0A-70FEAFE4BE85).

>[!NOTE]
>Si vous activez l’accès conditionnel pour SharePoint Online, nous vous recommandons de désactiver le domaine dans la liste, comme décrit dans la rubrique [Remove-SPOTenantSyncClientRestriction](https://technet.microsoft.com/library/dn917451.aspx).  

## <a name="support-for-mobile-devices"></a>Prise en charge des appareils mobiles
Les éléments suivants sont pris en charge :
- iOS 8.0 et versions ultérieures
- Android 4.0 et versions ultérieures, Samsung Knox Standard 4.0 ou versions ultérieures
- Windows Phone 8.1 et versions ultérieures

Vous pouvez protéger l’accès à SharePoint Online quand les appareils **iOS** et **Android** y accèdent à partir d’un navigateur. L’accès est autorisé uniquement à partir des navigateurs pris en charge sur les appareils conformes :
* Safari (iOS)
* Chrome (Android)
* Intune Managed Browser (iOS et Android versions 5.0 et ultérieures)

**Les navigateurs non pris en charge sont bloqués**.

## <a name="support-for-pcs"></a>Prise en charge des PC
Les éléments suivants sont pris en charge :
- Windows 8.1 et versions ultérieures (quand les PC sont inscrits auprès de Microsoft Intune)
- Windows 7.0, Windows 8.1 ou Windows 10 (quand les PC sont joints au domaine)
  > [!NOTE]
  >Pour utiliser l’accès conditionnel avec des PC Windows 10, vous devez mettre à jour ces PC avec la Mise à jour anniversaire Windows 10.

  - Vous devez configurer les PC joints à un domaine pour qu’ils [s’inscrivent automatiquement](https://azure.microsoft.com/documentation/articles/active-directory-conditional-access-automatic-device-registration/) dans Azure Active Directory. Le service d’inscription Azure Active Directory pour appareils sera activé automatiquement pour les clients Intune et Office 365. Les clients qui ont déjà déployé le service d’inscription d’appareils AD FS ne verront pas les appareils inscrits dans l’annuaire Active Directory local.

  - Si la stratégie est définie pour exiger l’appartenance à un domaine et que le PC n’est pas joint à un domaine, un message invitant l’utilisateur à contacter l’administrateur informatique s’affiche.

  - Si la stratégie définie exige l’appartenance à un domaine ou la conformité et que le PC ne remplit aucune de ces conditions, un message contenant des instructions sur la façon d’installer l’application Portail d’entreprise et d’inscrire l’appareil s’affiche.
    >[!NOTE]
    >L’accès conditionnel n’est pas pris en charge sur les PC qui exécutent le client Intune.

[L’authentification moderne Office 365 doit être activée](https://support.office.com/article/Using-Office-365-modern-authentication-with-Office-clients-776c0036-66fd-41cb-8928-5495c0f9168a) et toutes les mises à jour Office les plus récentes doivent être installées.

L’authentification moderne permet aux clients Windows Office 2013 d’utiliser une connexion basée sur la bibliothèque ADAL (Active Directory Authentication Library) et permet de bénéficier d’une sécurité accrue, comme l’**authentification multifacteur** et l’**authentification basée sur certificat**.


## <a name="configure-conditional-access-for-sharepoint-online"></a>Configurer l’accès conditionnel à SharePoint Online

### <a name="step-1-configure-active-directory-security-groups"></a>Étape 1 : configurer les groupes de sécurité Active Directory
Avant de commencer, configurez les groupes de sécurité Azure Active Directory pour la stratégie d'accès conditionnel. Vous pouvez configurer ces groupes dans le **Centre d’administration Office 365**ou dans le **Portail de compte Intune**. Vous utilisez ces groupes pour cibler les utilisateurs avec la stratégie ou les exempter de la stratégie. Quand un utilisateur est ciblé par une stratégie, chaque appareil qu’il utilise doit être conforme à cette stratégie pour qu’il puisse accéder aux ressources.

Vous pouvez spécifier deux types de groupes dans une stratégie SharePoint Online :

-   **Groupes ciblés** : contient les groupes d’utilisateurs auxquels la stratégie s’applique.

-   **Groupes exemptés** : contient les groupes d’utilisateurs exempts de la stratégie.

Si un utilisateur se trouve dans les deux groupes, il est exempt de la stratégie.

### <a name="step-2-configure-and-deploy-a-compliance-policy"></a>Étape 2 : configurer et déployer une stratégie de conformité
Si ce n’est pas encore fait, créez une stratégie de conformité et déployez-la sur tous les utilisateurs ciblés par la stratégie d’accès conditionnel SharePoint Online.

> [!NOTE]
> Tandis que les stratégies de conformité sont déployées sur les groupes Intune, les stratégies d’accès conditionnel sont destinées aux groupes de sécurité Azure Active Directory.

Pour plus d’informations sur la façon de configurer la stratégie de conformité, consultez [Créer une stratégie de conformité](create-a-device-compliance-policy-in-microsoft-intune.md).

> [!IMPORTANT]
> Si vous n’avez pas déployé de stratégie de conformité, les appareils sont traités comme étant conformes.

Quand vous êtes prêt, passez à l’**Étape 3**.

### <a name="step-3-configure-the-sharepoint-online-policy"></a>Étape 3 : configurer la stratégie SharePoint Online
Ensuite, configurez la stratégie de manière à restreindre l'accès à SharePoint Online aux appareils gérés et conformes. Cette stratégie est stockée dans Azure Active Directory.

#### <a name="bkmk_spopolicy"></a>

>[!NOTE]
> Vous pouvez également créer une stratégie d’accès conditionnel pour des appareils Intune dans la console de gestion Azure AD (la stratégie est appelée **stratégie d’accès conditionnel basée sur les appareils** dans Azure AD). En outre, vous pouvez créer d’autres stratégies d’accès conditionnel telles que l’authentification multifacteur. Vous pouvez aussi définir des stratégies d’accès conditionnel pour des applications d’entreprise tierces prises en charge par Azure AD, comme Salesforce et Box. Pour plus d’informations, consultez [Comment définir la stratégie d’accès conditionnel en fonction de l’appareil Azure Active Directory pour contrôler l’accès aux applications connectées Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-conditional-access-policy-connected-applications/).


1. Dans la [Console d’administration Microsoft Intune](https://manage.microsoft.com), choisissez **Stratégie** > **Accès conditionnel** > **Stratégie SharePoint Online**.
   ![Capture d’écran de la page de stratégie SharePoint Online](../media/mdm-ca-spo-policy-configuration.png)

2. Sélectionnez **Activer la stratégie d’accès conditionnel pour SharePoint Online**.

3. Sous **Accès aux applications**, vous pouvez choisir d’appliquer la stratégie d’accès conditionnel à :

   - **Toutes les plateformes**

     Cette opération exige que tous les appareils utilisés pour accéder à **SharePoint Online** soient inscrits dans Intune et conformes aux stratégies. Toute application cliente qui utilise l’**authentification moderne** est soumise à la stratégie d’accès conditionnel. Si la plateforme n’est pas prise en charge actuellement par Intune, l’accès à **SharePoint Online** est bloqué.

     Si vous sélectionnez l’option **Toutes plateformes**, Azure Active Directory applique cette stratégie à toutes les demandes d’authentification, quelle que soit la plateforme signalée par l’application cliente. Toutes les plateformes doivent être inscrites et être conformes, sauf dans les cas suivants :
     *   Les appareils Windows doivent être inscrits et conformes et/ou être joints à un domaine avec un annuaire Active Directory local.
     * Plateformes non prises en charge comme Mac. Toutefois, les applications utilisant l’authentification moderne issues de ces plateformes sont toujours bloquées.

   - **Plateformes spécifiques**

      La stratégie d’accès conditionnel s’applique à toutes les applications clientes qui utilisent l’authentification moderne sur les plateformes que vous spécifiez.

     Pour les PC Windows, ceux-ci doivent être joints à un domaine ou inscrits auprès d’Intune et être conformes. Vous pouvez définir les conditions suivantes :

     -   **Les appareils doivent être joints à un domaine ou conformes.** Choisissez cette option pour exiger que les PC soient joints à un domaine ou conformes aux stratégies définies dans Intune. Si un PC ne remplit pas l’une de ces conditions, l’utilisateur est invité à inscrire l’appareil auprès d’Intune.

     -   **Les appareils doivent être conformes** Choisissez cette option pour exiger que les PC soient inscrits auprès d’Intune et conformes. Si un PC n’est pas inscrit, un message contenant des instructions sur la procédure d’inscription à suivre s’affiche.

4. Sous **Accès du navigateur à SharePoint et à OneDrive Entreprise**, vous pouvez choisir d’autoriser l’accès à Exchange Online uniquement par le biais des navigateurs pris en charge : Safari (iOS) et Chrome (Android). L’accès à partir d’autres navigateurs est bloqué. Les restrictions de plateforme que vous avez sélectionnées pour Accès aux applications pour OneDrive s’appliquent également ici.

   Sur les appareils **Android**, les utilisateurs doivent activer l’accès du navigateur. Pour ce faire, l’utilisateur doit choisir l’option **Activer l’accès du navigateur** sur l’appareil inscrit comme suit :
   1.    Ouvrez l’application **Portail d’entreprise**.
   2.    Accédez à la page **Paramètres** à partir des trois points (...) ou du bouton de menu matériel.
   3.    Appuyer sur le bouton **Activer l’accès du navigateur**.
   4.    Dans le navigateur Chrome, se déconnecter d’Office 365 et redémarrer Chrome.

   Sur les plateformes **iOS** et **Android**, pour identifier l’appareil qui est utilisé pour accéder au service, Azure Active Directory délivre un certificat TLS (Transport Layer Security) à l’appareil. L’appareil affiche le certificat avec une invite demandant à l’utilisateur de sélectionner le certificat, comme indiqué dans les captures d’écran suivantes. L’utilisateur doit sélectionner ce certificat pour pouvoir utiliser le navigateur.

   **iOS**

   ![Capture d’écran de l’invite de certificat sur un iPad](../media/mdm-browser-ca-ios-cert-prompt.png)

   **Android**

   ![Capture d’écran de l’invite de certificat sur un appareil Android](../media/mdm-browser-ca-android-cert-prompt.png)
5. Sous **Groupes ciblés**, choisissez **Modifier** pour sélectionner les groupes de sécurité Azure Active Directory auxquels la stratégie s’applique. Vous pouvez cibler cette stratégie sur tous les utilisateurs ou seulement sur un groupe d’utilisateurs donné.

6. Sous **Groupes exemptés**, vous pouvez éventuellement choisir **Modifier** pour sélectionner les groupes de sécurité Azure Active Directory exempts de cette stratégie.

7. Quand vous avez terminé, choisissez **Enregistrer**.

La stratégie d’accès conditionnel prend effet immédiatement. Il est donc inutile de la déployer.

### <a name="step-4-monitor-the-compliance-and-conditional-access-policies"></a>Étape 4 : analyser les stratégies d’accès conditionnel et de conformité
Dans l’espace de travail **Groupes**, vous pouvez afficher l’état de vos appareils.

Sélectionnez un groupe d’appareils mobiles. Ensuite, sous l’onglet **Appareils**, choisissez l’un des **Filtres** suivants :

-   **Appareils non enregistrés avec AAD**. Ces appareils ne peuvent pas accéder à SharePoint Online.

-   **Appareils non conformes**. Ces appareils ne peuvent pas accéder à SharePoint Online.

-   **Appareils enregistrés avec AAD et conformes**. Ces appareils peuvent accéder à SharePoint Online.

### <a name="see-also"></a>Voir aussi
[Protéger l’accès à la messagerie et aux services O365 avec Microsoft Intune](restrict-access-to-email-and-o365-services-with-microsoft-intune.md)
