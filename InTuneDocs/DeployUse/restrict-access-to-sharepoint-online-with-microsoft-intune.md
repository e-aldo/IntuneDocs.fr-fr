---
# required metadata

title: Restreindre l’accès à SharePoint Online | Microsoft Intune
description:
keywords:
author: karthikaraman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: b088e5a0-fd4a-4fe7-aa49-cb9c8cfb1585

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: chrisgre
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Restreindre l’accès à SharePoint Online avec Microsoft Intune
Utilisez l’accès conditionnel [!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)] pour contrôler l’accès aux fichiers situés sur SharePoint Online.
L’accès conditionnel comprend deux composants :
- La stratégie de conformité des appareils que l’appareil doit respecter pour être considéré comme conforme.
- La stratégie d’accès conditionnel dans laquelle vous spécifiez les conditions que l’appareil doit remplir pour accéder au service.
Pour en savoir plus sur le fonctionnement de l’accès conditionnel, lisez la rubrique [Restreindre l’accès à la messagerie et aux services O365](restrict-access-to-email-and-o365-services-with-microsoft-intune.md).

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

## Prise en charge des appareils mobiles
- iOS 7.1 et versions ultérieures
- Android 4.0 et versions ultérieures, Samsung Knox Standard 4.0 ou versions ultérieures
- Windows Phone 8.1 et versions ultérieures

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

> [!NOTE]Tandis que les stratégies de conformité sont déployées dans des groupes [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)], les stratégies d’accès conditionnel sont destinées aux groupes de sécurité Azure Active Directory.

Pour plus d’informations sur la configuration de la stratégie de conformité, consultez [Create a  compliance policy](create-a-device-compliance-policy-in-microsoft-intune.md) (Créer une stratégie de conformité).

> [!IMPORTANT] Si vous n’avez pas déployé de stratégie de conformité, les appareils sont considérés comme conformes.

Quand vous êtes prêt, passez à l' **Étape 3**.

### Étape 3 : configurer la stratégie SharePoint Online
Ensuite, configurez la stratégie de manière à restreindre l'accès à SharePoint Online aux appareils gérés et conformes. Cette stratégie sera stockée dans Azure Active Directory.

#### <a name="bkmk_spopolicy"></a>

1.  Dans la [Console d’administration Microsoft Intune](https://manage.microsoft.com), cliquez sur **Stratégie** > **Accès conditionnel** > **Stratégie SharePoint Online**.
![Capture d’écran de la page de stratégie SharePoint Online](../media/IntuneSASharePointOnlineCAPolicy.png)

2.  Sélectionnez **Activer la stratégie d’accès conditionnel pour SharePoint Online**.

3.  Sous **Accès aux applications**, vous pouvez choisir d’appliquer la stratégie d’accès conditionnel à :

    -   **Toutes les plateformes**

        Cette opération exige que tous les appareils utilisés pour accéder à **SharePoint Online** soient inscrits dans Intune et conformes aux stratégies.  Toute application cliente utilisant l’**authentification moderne** est soumise à la stratégie d’accès conditionnel. Si la plateforme n’est actuellement pas prise en charge par Intune, l’accès à **SharePoint Online** est bloqué.
        >[!TIP]
        >Vous ne verrez peut-être pas cette option si vous n’utilisez pas l’accès conditionnel pour PC.  Utilisez les **Plateformes spécifiques** à la place. L’accès conditionnel pour PC n’est actuellement pas disponible pour tous les clients Intune.   Vous trouverez plus d’informations sur les problèmes connus et sur l’accès à cette fonctionnalité sur le [site Microsoft Connect](http://go.microsoft.com/fwlink/?LinkId=761472).

    -   **des plateformes spécifiques**

         La stratégie d’accès conditionnel s’applique à toutes les applications clientes qui utilisent l’authentification moderne sur les plateformes que vous spécifiez.

     Pour les PC Windows, le PC doit être joint à un domaine ou inscrit auprès d’[!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] et être conforme. Vous pouvez définir les conditions suivantes :

     -   **Les appareils doivent être joints à un domaine ou conformes.** Choisissez cette option si vous voulez que les PC soient joints à un domaine ou conformes aux stratégies définies dans [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]. Si le PC ne remplit pas l’une des conditions requises, l’utilisateur est invité à inscrire l’appareil auprès de [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].

     -   **Les appareils doivent être joints à un domaine.** Choisissez cette option pour spécifier que les PC doivent être joints à un domaine pour accéder à Exchange Online. Si le PC n’est pas joint à un domaine, l’accès à la messagerie électronique est bloqué et l’utilisateur est invité à contacter l’administrateur informatique.

     -   **Les appareils doivent être conformes** Choisissez cette option pour spécifier que les PC doivent être inscrits auprès d’[!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] et être conforme. Si le PC n'est pas inscrit, un message contenant des instructions sur la procédure d'inscription à suivre s'affiche.

4.  Sous **Groupes ciblés**, cliquez sur **Modifier** pour sélectionner les groupes de sécurité Active Directory auxquels la stratégie sera appliquée. Vous pouvez cibler cette stratégie sur tous les utilisateurs ou seulement sur des groupes d’utilisateurs sélectionnés.

5.  Sous **Groupes exemptés**, vous pouvez éventuellement cliquez sur **Modifier** pour sélectionner les groupes de sécurité Azure Active Directory exempts de cette stratégie.

6.  Une fois terminé, cliquez sur **Enregistrer**.

La stratégie d'accès conditionnel prend effet immédiatement. Il est donc inutile de la déployer.

### Étape 4 : analyser les stratégies d’accès conditionnel et de conformité
Dans l’espace de travail **Groupes**, vous pouvez afficher l’état de vos appareils.

Sélectionnez un groupe d'appareils mobiles quelconque, puis sous l'onglet **Appareils** , sélectionnez l'un des **Filtres**suivants :

-   **Appareils non enregistrés avec AAD** : l'accès à SharePoint Online est bloqué pour ces appareils.

-   **Appareils non conformes** : l'accès à SharePoint Online est bloqué pour ces appareils.

-   **Appareils enregistrés avec AAD et conformes** : ces appareils peuvent accéder à SharePoint Online.

### Voir aussi
[Restreindre l’accès aux services de messagerie et O365 avec Microsoft Intune](restrict-access-to-email-and-o365-services-with-microsoft-intune.md)


<!--HONumber=Jun16_HO2-->


