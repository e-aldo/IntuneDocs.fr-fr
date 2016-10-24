---
title: "Restreindre l’accès à SharePoint Online | Microsoft Intune"
description: "Protégez et contrôlez l’accès aux données de l’entreprise sur SharePoint Online avec l’accès conditionnel."
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 07/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b088e5a0-fd4a-4fe7-aa49-cb9c8cfb1585
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: db1d43dd647122e7ba8ebd4e6df48e3c970a3392
ms.openlocfilehash: 76ac4c92d090ef0057bd7c9687b169cd12b901a1


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


**Avant** de configurer une stratégie d’accès conditionnel à SharePoint Online, vous devez :
- Disposer d’un **abonnement SharePoint Online** ; les utilisateurs doivent disposer d’une licence pour SharePoint Online.
- Avoir **un abonnement Enterprise Mobility + Security ou Azure Active Directory Premium**, et les utilisateurs doivent disposer d’une licence EMS ou Azure AD. Pour plus d’informations, consultez la [page de tarification d’Enterprise Mobility](https://www.microsoft.com/en-us/cloud-platform/enterprise-mobility-pricing) ou la [page de tarification d’Azure Active Directory](https://azure.microsoft.com/en-us/pricing/details/active-directory/).


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
- iOS 8.0 et versions ultérieures
- Android 4.0 et versions ultérieures, Samsung Knox Standard 4.0 ou versions ultérieures
- Windows Phone 8.1 et versions ultérieures

Vous pouvez restreindre l’accès à SharePoint Online depuis un navigateur sur les appareils **iOS** et **Android**.  L’accès ne sera autorisé qu’à partir des navigateurs pris en charge sur les appareils compatibles :
* Safari (iOS)
* Chrome (Android)
* Managed Browser (iOS et Android)

**Les navigateurs non pris en charge seront bloqués**.

## Prise en charge des PC
- Windows 8.1 et versions ultérieures (quand ils sont inscrits auprès de Microsoft Intune)
- Windows 7.0, Windows 8.1 ou Windows 10 (quand ils sont joints au domaine)
> [!NOTE]
>Pour utiliser l’accès conditionnel avec des PC Windows 10, vous devez mettre à jour ces PC avec la Mise à jour anniversaire Windows 10.

  - Les PC joints à un domaine doivent être configurés de manière à ce qu’ils [s’inscrivent automatiquement](https://azure.microsoft.com/en-us/documentation/articles/active-directory-conditional-access-automatic-device-registration/) dans Azure Active Directory.
Le service AAD DRS sera activé automatiquement pour les clients Intune et Office 365. Les clients qui ont déjà déployé le service d'inscription d'appareils AD FS ne verront pas les appareils inscrits dans leur annuaire Active Directory local.

  - Si la stratégie est définie de manière à exiger la jonction à un domaine et que le PC n’est pas joint à un domaine, un message invitant l’utilisateur à contacter l’administrateur informatique s’affiche.

  - Si la stratégie définie exige la jonction à un domaine ou la conformité et que le PC ne répond pas aux conditions, un message contenant des instructions sur la façon d’installer l’application du portail d’entreprise et d’inscrire l’appareil s’affiche.
  >[!NOTE]
  >L’accès conditionnel n’est pas pris en charge sur les ordinateurs qui exécutent le client Intune.

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

>[!NOTE]
> Vous pouvez également créer une stratégie d’accès conditionnel dans la console de gestion Azure AD. La console de gestion Azure AD permet de créer des stratégies d’accès conditionnel d’appareils Intune (appelées **stratégies d’accès conditionnel en fonction de l’appareil** dans Azure AD) en plus des autres stratégies d’accès conditionnel, comme l’authentification multifacteur.  Vous pouvez également définir des stratégies d’accès conditionnel pour les applications d’entreprise tierces, comme Salesforce et Box, prises en charge par Azure AD. Pour plus d’informations, consultez [Comment définir la stratégie d’accès conditionnel en fonction de l’appareil Azure Active Directory pour contrôler l’accès aux applications connectées Azure Active Directory](https://azure.microsoft.com/en-us/documentation/articles/active-directory-conditional-access-policy-connected-applications/).


1.  Dans la [Console d’administration Microsoft Intune](https://manage.microsoft.com), choisissez **Stratégie** > **Accès conditionnel** > **Stratégie SharePoint Online**.
![Capture d’écran de la page de stratégie SharePoint Online](../media/mdm-ca-spo-policy-configuration.png)

2.  Sélectionnez **Activer la stratégie d’accès conditionnel pour SharePoint Online**.

3.  Sous **Accès aux applications**, vous pouvez choisir d’appliquer la stratégie d’accès conditionnel à :

    -   **Toutes les plateformes**

        Cette opération exige que tous les appareils utilisés pour accéder à **SharePoint Online** soient inscrits dans Intune et conformes aux stratégies.  Toute application cliente utilisant l’**authentification moderne** est soumise à la stratégie d’accès conditionnel. Si la plateforme n’est actuellement pas prise en charge par Intune, l’accès à **SharePoint Online** est bloqué.

        Si vous sélectionnez l’option **Toutes plateformes**, Azure Active Directory applique cette stratégie à toutes les demandes d’authentification, quelle que soit la plateforme signalée par l’application cliente.  Toutes les plateformes doivent être inscrites et être conformes, sauf dans les cas suivants :
        *   Les appareils Windows doivent être inscrits et conformes et/ou être joints à un domaine avec un annuaire Active Directory local.
        * Plateformes non prises en charge comme Mac.  Toutefois, les applications utilisant l’authentification moderne issues de ces plateformes sont toujours bloquées.

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



<!--HONumber=Oct16_HO1-->


