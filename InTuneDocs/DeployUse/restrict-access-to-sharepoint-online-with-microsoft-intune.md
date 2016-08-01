---
title: "Restreindre l’accès à SharePoint Online | Microsoft Intune"
description: "Protégez et contrôlez l’accès aux données de l’entreprise sur SharePoint Online avec l’accès conditionnel."
keywords: 
author: karthikaraman
manager: arob98
ms.date: 07/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b088e5a0-fd4a-4fe7-aa49-cb9c8cfb1585
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 2038ed6219a94dc4285891d71ce00fd51310f3e3
ms.openlocfilehash: 54f5e95fc8992ee3a68fd7063bff7cdb90c308bb


---

# Restreindre l’accès à SharePoint Online avec Microsoft Intune
Utilisez l’accès conditionnel [!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)] pour contrôler l’accès aux fichiers situés sur SharePoint Online.
L’accès conditionnel comprend deux composants :
- La stratégie de conformité des appareils que l’appareil doit respecter pour être considéré comme conforme.
- La stratégie d’accès conditionnel dans laquelle vous spécifiez les conditions que l’appareil doit remplir pour accéder au service.
Pour en savoir plus sur le fonctionnement de l’accès conditionnel, lisez la rubrique [Restreindre l’accès aux services de messagerie, O365 et autres ](restrict-access-to-email-and-o365-services-with-microsoft-intune.md).

La conformité et les stratégies d’accès conditionnel sont déployées pour l’utilisateur. La conformité avec les stratégies de chaque appareil que l’utilisateur utilise pour accéder aux services est contrôlée.

Quand un utilisateur tente de se connecter à un fichier à l’aide d’une application prise en charge, par exemple OneDrive, sur son appareil, l’évaluation suivante se produit :

![Diagramme illustrant les points de décision qui déterminent si un appareil est autorisé ou non à accéder à SharePoint ](../media/ConditionalAccess8-6.png)

>[!IMPORTANT]
>L’accès conditionnel des PC et des appareils Windows 10 Mobile avec des applications utilisant l’authentification moderne n’est actuellement pas disponible pour tous les clients Intune. Si vous utilisez déjà ces fonctionnalités, vous n’avez pas d’action particulière à effectuer. Vous pouvez continuer à les utiliser.

>Si vous n’avez pas créé de stratégies d’accès conditionnel pour PC ou appareils Windows 10 Mobile avec des applications utilisant l’authentification moderne et que vous souhaitez le faire, vous devez soumettre une demande.  Vous trouverez plus d’informations sur les problèmes connus et sur l’accès à cette fonctionnalité sur le [site Connect](http://go.microsoft.com/fwlink/?LinkId=761472).

**Avant** de configurer une stratégie d’accès conditionnel à SharePoint Online, vous devez :
- Disposer d’un **abonnement SharePoint Online** ; les utilisateurs doivent disposer d’une licence pour SharePoint Online.
- Disposer d’un abonnement à **Enterprise Mobility Suite** ou **Azure Active Directory Premium**.

  Pour se connecter aux fichiers requis, l’appareil doit :
-   Être **inscrit** auprès d’[!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] ou être un PC joint à un domaine.

-   **Inscrire l’appareil** dans Azure Active Directory (cela se produit automatiquement quand l’appareil est inscrit auprès de [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]).


-   Être conforme à toutes les stratégies de conformité [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] déployées.

L'état de l'appareil est stocké dans Azure Active Directory, qui autorise ou bloque l'accès aux fichiers en fonction des conditions spécifiées.

Si une condition n'est pas remplie, l'utilisateur reçoit l'un des messages suivants quand il tente de se connecter :

-   Si l’appareil n’est pas inscrit auprès d’[!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] ou qu’il n’est pas inscrit dans Azure Active Directory, l’utilisateur reçoit un message contenant des instructions pour installer l’application du portail d’entreprise et inscrire l’appareil.

-   Si l’appareil n’est pas conforme, l’utilisateur reçoit un message le dirigeant vers le site web du portail d’entreprise [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] dans lequel il peut trouver des informations sur le problème et des solutions pour y remédier.

**L’accès conditionnel est appliqué sur tous les sites SharePoint et le partage externe est bloqué**

>[!NOTE]
>Si vous activez l’accès conditionnel pour SharePoint Online, nous vous recommandons de désactiver le domaine dans la liste comme décrit dans la rubrique [Remove-SPOTenantSyncClientRestriction](https://technet.microsoft.com/en-us/library/dn917451.aspx).  
## Prise en charge des appareils mobiles
- iOS 7.1 et versions ultérieures
- Android 4.0 et versions ultérieures, Samsung Knox Standard 4.0 ou versions ultérieures
- Windows Phone 8.1 et versions ultérieures

Vous pouvez restreindre l’accès à SharePoint Online depuis un navigateur sur les appareils **iOS** et **Android**.  L’accès ne sera autorisé qu’à partir des navigateurs pris en charge sur les appareils compatibles :
* Safari (iOS)
* Chrome (Android)
* Managed Browser (iOS et Android)

**Les navigateurs non pris en charge seront bloqués**.

## Prise en charge des PC
- Windows 8.1 et versions ultérieures (quand ils sont inscrits auprès de Microsoft Intune)
- Windows 7.0 ou Windows 8.1 (quand ils sont joints au domaine)

  - Les PC joints à un domaine doivent être configurés de manière à ce qu’ils [s’inscrivent automatiquement](https://azure.microsoft.com/en-us/documentation/articles/active-directory-conditional-access-automatic-device-registration/) dans Azure Active Directory.
Le service AAD DRS sera activé automatiquement pour les clients Intune et Office 365. Les clients qui ont déjà déployé le service d'inscription d'appareils AD FS ne verront pas les appareils inscrits dans leur annuaire Active Directory local.

  - Si la stratégie est définie de manière à exiger la jonction à un domaine et que le PC n’est pas joint à un domaine, un message invitant l’utilisateur à contacter l’administrateur informatique s’affiche.

  - Si la stratégie définie exige la jonction à un domaine ou la conformité et que le PC ne répond pas aux conditions, un message contenant des instructions sur la façon d’installer l’application du portail d’entreprise et d’inscrire l’appareil s’affiche.
-    [L’authentification moderne Office 365 doit être activée](https://support.office.com/en-US/article/Using-Office-365-modern-authentication-with-Office-clients-776c0036-66fd-41cb-8928-5495c0f9168a) et toutes les mises à jour Office les plus récentes doivent être installées.

    L’authentification moderne permet aux clients Windows Office 2013 d’utiliser une connexion basée sur la bibliothèque ADAL (Active Directory Authentication Library) et permet de bénéficier d’une sécurité accrue, comme l’**authentification multifacteur** et l’**authentification basée sur certificat**.


## Configurer l’accès conditionnel à SharePoint Online

### Étape 1 : configurer les groupes de sécurité Active Directory
Avant de commencer, configurez les groupes de sécurité Azure Active Directory pour la stratégie d'accès conditionnel. Vous pouvez configurer ces groupes dans le **Centre d'administration Office 365**ou dans le **Portail de compte Intune**. Ces groupes seront utilisés pour cibler ou exempter les utilisateurs de la stratégie. Quand un utilisateur est ciblé par une stratégie, chaque appareil qu'il utilise doit être conforme à cette stratégie pour qu'il puisse accéder aux ressources.

Vous pouvez spécifier deux types de groupes dans une stratégie SharePoint Online :

-   **Groupes ciblés** : contient les groupes d’utilisateurs auxquels s’applique la stratégie.

-   **Groupes exemptés** : contient les groupes d’utilisateurs exempts de la stratégie.

Si un utilisateur se trouve dans les deux groupes, il est exempt de la stratégie.

### Étape 2 : configurer et déployer une stratégie de conformité
Si ce n’est pas encore fait, créez une stratégie de conformité et déployez-la sur tous les utilisateurs qui seront ciblés par la stratégie d’accès conditionnel SharePoint Online.

> [!NOTE]
> Tandis que les stratégies de conformité sont déployées sur les groupes [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)], les stratégies d’accès conditionnel sont destinées aux groupes de sécurité Azure Active Directory.

Pour plus d’informations sur la configuration de la stratégie de conformité, consultez [Create a  compliance policy](create-a-device-compliance-policy-in-microsoft-intune.md) (Créer une stratégie de conformité).

> [!IMPORTANT]
> Si vous n’avez pas déployé de stratégie de conformité, les appareils seront traités comme étant conformes.

Quand vous êtes prêt, passez à l' **Étape 3**.

### Étape 3 : configurer la stratégie SharePoint Online
Ensuite, configurez la stratégie de manière à restreindre l'accès à SharePoint Online aux appareils gérés et conformes. Cette stratégie sera stockée dans Azure Active Directory.

#### <a name="bkmk_spopolicy"></a>

1.  Dans la [Console d’administration Microsoft Intune](https://manage.microsoft.com), choisissez **Stratégie** > **Accès conditionnel** > **Stratégie SharePoint Online**.
![Capture d’écran de la page de stratégie SharePoint Online](../media/mdm-ca-spo-policy-configuration.png)

2.  Sélectionnez **Activer la stratégie d’accès conditionnel pour SharePoint Online**.

3.  Sous **Accès aux applications**, vous pouvez choisir d’appliquer la stratégie d’accès conditionnel à :

    -   **Toutes les plateformes**

        Cette opération exige que tous les appareils utilisés pour accéder à **SharePoint Online** soient inscrits dans Intune et conformes aux stratégies.  Toute application cliente utilisant l’**authentification moderne** est soumise à la stratégie d’accès conditionnel. Si la plateforme n’est actuellement pas prise en charge par Intune, l’accès à **SharePoint Online** est bloqué.

        Si vous sélectionnez l’option **Toutes plateformes**, Azure Active Directory applique cette stratégie à toutes les demandes d’authentification, quelle que soit la plateforme signalée par l’application cliente.  Toutes les plateformes doivent être inscrites et être conformes, sauf dans les cas suivants :
        *   Les appareils Windows doivent être inscrits et conformes et/ou être joints à un domaine avec un annuaire Active Directory local.
        * Plateformes non prises en charge comme Mac.  Toutefois, les applications utilisant l’authentification moderne issues de ces plateformes sont toujours bloquées.
        >[!TIP]
        >Vous ne verrez peut-être pas cette option si vous n’utilisez pas l’accès conditionnel pour PC.  Utilisez les **Plateformes spécifiques** à la place. L’accès conditionnel pour PC n’est actuellement pas disponible pour tous les clients Intune.   Vous trouverez plus d’informations sur les problèmes connus et sur l’accès à cette fonctionnalité sur le [site Microsoft Connect](http://go.microsoft.com/fwlink/?LinkId=761472).

    -   **des plateformes spécifiques**

         La stratégie d’accès conditionnel s’applique à toutes les applications clientes qui utilisent l’authentification moderne sur les plateformes que vous spécifiez.

     Pour les PC Windows, le PC doit être joint à un domaine ou inscrit auprès d’[!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] et être conforme. Vous pouvez définir les conditions suivantes :

     -   **Les appareils doivent être joints à un domaine ou conformes.** Choisissez cette option si vous voulez que les PC soient joints à un domaine ou conformes aux stratégies définies dans [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]. Si le PC ne remplit pas l’une des conditions requises, l’utilisateur est invité à inscrire l’appareil auprès de [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].

     -   **Les appareils doivent être joints à un domaine.** Choisissez cette option pour spécifier que les PC doivent être joints à un domaine pour accéder à Exchange Online. Si le PC n’est pas joint à un domaine, l’accès à la messagerie électronique est bloqué et l’utilisateur est invité à contacter l’administrateur informatique.

     -   **Les appareils doivent être conformes** Choisissez cette option pour spécifier que les PC doivent être inscrits auprès d’[!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] et être conforme. Si le PC n'est pas inscrit, un message contenant des instructions sur la procédure d'inscription à suivre s'affiche.

4.   Sous **Accès du navigateur à SharePoint et à OneDrive Entreprise**, vous pouvez choisir d’autoriser l’accès à Exchange Online uniquement par le biais des navigateurs pris en charge : Safari (iOS) et Chrome (Android). L’accès à partir d’autres navigateurs est bloqué.  Les restrictions de plateforme que vous avez sélectionnées pour Accès aux applications pour OneDrive s’appliquent également ici.

  Sur les appareils **Android**, les utilisateurs doivent activer l’accès au navigateur.  Pour ce faire, l’utilisateur final doit activer l’option « Activer l’accès du navigateur » sur l’appareil inscrit comme suit :
  1.    Lancer l’**application Portail d’entreprise**.
  2.    Accéder à la page **Paramètres** à partir des trois points (...) ou du bouton de menu matériel.
  3.    Appuyer sur le bouton **Activer l’accès du navigateur**.
  4.  Dans le navigateur Chrome, se déconnecter d’Office 365 et redémarrer Chrome.

  Sur les plateformes **iOS et Android**, pour identifier l’appareil qui est utilisé pour accéder au service, Azure Active Directory émet un certificat TLS (Transport Layer Security) à destination de l’appareil.  L’appareil affiche le certificat avec une invite demandant à l’utilisateur final de sélectionner le certificat, comme indiqué dans les captures d’écran ci-dessous. L’utilisateur final doit sélectionner ce certificat pour continuer à utiliser le navigateur.

  **iOS**

  ![Capture d’écran de l’invite de certificat sur un iPad](../media/mdm-browser-ca-ios-cert-prompt.png)

  **Android**

  ![Capture d’écran de l’invite de certificat sur un appareil Android](../media/mdm-browser-ca-android-cert-prompt.png)
5.  Sous **Groupes ciblés**, choisissez **Modifier** pour sélectionner les groupes de sécurité Azure Active Directory auxquels la stratégie sera appliquée. Vous pouvez cibler cette stratégie sur tous les utilisateurs ou seulement sur des groupes d’utilisateurs sélectionnés.

6.  Sous **Groupes exemptés**, vous pouvez éventuellement choisir **Modifier** pour sélectionner les groupes de sécurité Azure Active Directory exempts de cette stratégie.

6.  Une fois terminé, choisissez **Enregistrer**.

La stratégie d'accès conditionnel prend effet immédiatement. Il est donc inutile de la déployer.

### Étape 4 : analyser les stratégies d’accès conditionnel et de conformité
Dans l’espace de travail **Groupes**, vous pouvez afficher l’état de vos appareils.

Sélectionnez un groupe d'appareils mobiles quelconque, puis sous l'onglet **Appareils** , sélectionnez l'un des **Filtres**suivants :

-   **Appareils non enregistrés avec AAD** : l'accès à SharePoint Online est bloqué pour ces appareils.

-   **Appareils non conformes** : l'accès à SharePoint Online est bloqué pour ces appareils.

-   **Appareils enregistrés avec AAD et conformes** : ces appareils peuvent accéder à SharePoint Online.

### Voir aussi
[Restreindre l’accès aux services de messagerie et O365 avec Microsoft Intune](restrict-access-to-email-and-o365-services-with-microsoft-intune.md)



<!--HONumber=Jul16_HO4-->


