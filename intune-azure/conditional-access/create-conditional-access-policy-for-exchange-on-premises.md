---
title: "Créer et affecter une stratégie d’accès conditionnel Exchange sur site"
titleSuffix: Intune Azure preview
description: "Préversion d’Intune Azure : guide de configuration de l’accès conditionnel Exchange sur site et Exchange Online Dedicated hérité dans Intune"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 04/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 127dafcb-3f30-4745-a561-f62c9f095907
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: c8715f96f532ee6bacda231e1147d03226ecbb48
ms.openlocfilehash: 2a011bf390bb55d685f580cfc782b21ff0c2ebd5
ms.lasthandoff: 04/26/2017


---

# <a name="how-to-create-and-assign-a-conditional-access-policy-for-exchange-on-premises-and-legacy-exchange-online-dedicated-in-microsoft-intune-azure-preview"></a>Guide de création et d’affectation d’une stratégie d’accès conditionnel pour Exchange sur site et Exchange Online Dedicated hérité dans la préversion de Microsoft Intune Azure

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Cette rubrique vous guide tout au long du processus de configuration de l’accès conditionnel pour Exchange sur site basé sur la compatibilité des appareils.

Si vous disposez d’un environnement Exchange Online Dedicated et que vous ne savez pas s’il s’agit de la nouvelle configuration ou d’une configuration héritée, contactez votre responsable de compte. Pour contrôler l’accès à la messagerie Exchange sur site ou Exchange Online Dedicated (environnement hérité), configurez l’accès conditionnel à Exchange sur site dans Intune.

## <a name="before-you-begin"></a>Avant de commencer

Avant de configurer l’accès conditionnel, vérifiez les éléments suivants :

- Votre version d’Exchange doit être **Exchange 2010 SP1 ou une version ultérieure**. Le groupe de serveurs d’accès au client (CAS) du serveur Exchange est pris en charge.

- Vous devez utiliser le [connecteur Exchange Active Sync sur site](https://docs.microsoft.com/intune-azure/conditional-access/install-intune-on-premises-exchange-connector) qui connecte Intune à Exchange sur site.

    >[!IMPORTANT]
    >Le connecteur Exchange local est propre à votre client Intune et ne peut pas être utilisé avec un autre client. Vous devez également vous assurer que le connecteur Exchange de votre client est installé **sur un seul ordinateur**.

- Vous pouvez installer le connecteur sur n’importe quel ordinateur, tant que celui-ci peut communiquer avec le serveur Exchange.

- Le connecteur prend en charge l’**Environnement CAS Exchange**. Techniquement, vous pouvez installer directement le connecteur sur le serveur CAS Exchange si vous le souhaitez, mais cette opération est déconseillée car elle augmente la charge sur le serveur. Quand vous configurez le connecteur, vous devez faire en sorte qu’il communique avec l’un des serveurs CAS Exchange.

- Vous devez configurer **Exchange ActiveSync** avec l’authentification par certificat ou la saisie des informations d’identification de l’utilisateur.

- Une fois les stratégies d’accès conditionnel configurées et ciblées sur un utilisateur, l’**appareil** dont l’utilisateur se sert pour se connecter à sa messagerie doit :
    - Être **inscrit** auprès d’Intune ou avoir un PC joint à un domaine.
    - Être **inscrit dans Azure Active Directory**. En outre, l’ID Exchange ActiveSync du client doit être inscrit auprès d’Azure Active Directory.
<br></br>
- Le service AAD DRS sera activé automatiquement pour les clients Intune et Office 365. Les clients qui ont déjà déployé le service d'inscription d'appareils AD FS ne verront pas les appareils inscrits dans leur annuaire Active Directory local. **Cela ne s’applique pas aux PC Windows ni aux appareils Windows Phone**.

- **Conforme** aux stratégies de conformité d’appareil déployées sur cet appareil.

- Si l'appareil ne répond pas aux paramètres d’accès conditionnel, l’utilisateur reçoit l’un des messages suivants quand il tente de se connecter :
    - Si l’appareil n’est pas inscrit auprès d’Intune ou qu’il n’est pas inscrit dans Azure Active Directory, l’utilisateur reçoit un message contenant des instructions pour installer l’application Portail d’entreprise, inscrire l’appareil et activer la messagerie. Ce processus associe également l’ID Exchange ActiveSync de l’appareil à l’enregistrement de l’appareil dans Azure Active Directory.
    - Si l’appareil n’est pas conforme, l’utilisateur reçoit un message le dirigeant vers le site web ou l’application Portail d’entreprise Intune, où il peut trouver des informations sur le problème et des solutions pour y remédier.

### <a name="support-for-mobile-devices"></a>Prise en charge des appareils mobiles

- Windows Phone 8.1 et versions ultérieures
- Application de messagerie native sur iOS.
- Clients de messagerie EAS, comme Gmail sur Android 4 ou ultérieur.
- Clients de messagerie EAS sur les **appareils Android for Work :** seules les applications **Gmail** et **Nine Work** dans le **profil professionnel** sont prises en charge sur les appareils Android for Work. Pour que l’accès conditionnel fonctionne avec Android for Work, vous devez déployer un profil de messagerie pour l’application Gmail ou Nine Work et également déployer ces applications comme installation obligatoire.

> [!NOTE]
> L’application Microsoft Outlook pour Android et iOS n’est pas prise en charge. Le déploiement d’Android for Work pour les clients Intune a commencé et va durer quelques mois.

### <a name="support-for-pcs"></a>Prise en charge des PC

L'application native **Courrier** sur Windows 8.1 et les versions ultérieures (en cas d’inscription auprès d'Intune)


## <a name="configure-exchange-on-premises-access"></a>Configuration de l'accès à Exchange sur site

1. Accédez au [portail Azure](https://portal.azure.com/) et connectez-vous avec vos informations d’identification Intune.

2. Une fois correctement connecté, le **tableau de bord Azure** apparaît.

3. Choisissez **Autres services** dans le menu de gauche, puis tapez **Intune** dans le filtre de zone de texte.

4. Choisissez **Intune**, vous voyez le **tableau de bord Intune**.

5.  Choisissez **Accès conditionnel**, puis

6. Le panneau **Local** affiche l’état de la stratégie d’accès conditionnel et les appareils qui en sont affectés.

7. Sous **Gérer**, choisissez **Accès à Exchange sur site**.

8. Dans le panneau **Accès à Exchange sur site**, choisissez **Oui** pour activer le contrôle d’accès Exchange sur site.

      > [!NOTE]
      > Si vous n’avez pas configuré le connecteur Exchange Active Sync sur site, cette option est désactivée.  Vous devez tout d’abord installer et configurer ce connecteur avant d’activer l’accès conditionnel pour Exchange sur site. Pour plus de détails, consultez la rubrique [Installer le connecteur Exchange local de Microsoft Intune](install-intune-on-premises-exchange-connector.md)

9. Sous **Affectation**, choisissez **Groupes inclus**.  Utilisez le groupe d’utilisateurs de sécurité auquel appliquer l'accès conditionnel. Dans ce cas, les utilisateurs doivent inscrire leurs appareils auprès d'Intune et se conformer aux profils de conformité.

10. Si vous voulez exclure des groupes d’utilisateurs spécifiques, vous pouvez le faire en choisissant **Groupes exclus** et en sélectionnant un groupe d’utilisateurs exempté de l’inscription de l'appareil et de la conformité.

11. Sous **Paramètres**, choisissez **Notifications utilisateur** pour modifier l'e-mail par défaut. Ce message est envoyé aux utilisateurs si leur appareil n’est pas conforme alors qu'ils souhaitent accéder à Exchange sur site. Le modèle de message utilise le langage de balisage.  Vous verrez également un aperçu du message en cours de frappe.
    > [!TIP]
    > Pour en savoir plus sur le langage de balisage, consultez cet [article](https://en.wikipedia.org/wiki/Markup_language) Wikipedia.

12. Dans le panneau des **paramètres d’accès Exchange Active Sync avancés**, définissez la règle globale par défaut pour l’accès à partir d'appareils qui ne sont pas gérés par Intune et pour les règles de niveau plate-forme comme décrit dans les deux prochaines étapes.

13. Si vous avez un appareil qui n'est pas affecté par l'accès conditionnel ou d'autres règles, vous pouvez choisir de l'autoriser l'accès à Exchange ou le bloquer.
  - Lorsque vous définissez cette option pour autoriser l’accès, tous les appareils sont en mesure d’accéder immédiatement à Exchange sur site.  Les appareils qui appartiennent aux utilisateurs dans les **Groupes inclus** sont bloqués s’ils sont évalués par la suite comme non conforme aux stratégies de conformité ou ne sont pas inscrits auprès d'Intune.
  - Lorsque vous définissez cette option pour bloquer l’accès, l'accès initial des appareils à Exchange sur site est immédiatement bloqué.  Les appareils qui appartiennent à des utilisateurs des **Groupes inclus** reçoivent un accès une fois que ces appareils sont inscrits auprès d'Intune et déterminés comme conformes. Les appareils Android qui n’exécutent pas Samsung KNOX standard seront toujours bloqués, car ils ne prennent pas en charge ce paramètre.
<br></br>
14. Sous **Exceptions de la plateforme d'appareils**, choisissez **Ajouter** pour spécifier les plateformes. Si le paramètre **Accès aux appareils non gérés** est défini sur **Bloqué**, les appareils qui sont inscrits et conformes seront autorisés, même s’il existe une exception de plateforme qui bloque. Choisissez **OK** pour enregistrer les paramètres.

15. Dans le panneau **Local**, cliquez sur **Enregistrer** pour enregistrer la stratégie d’accès conditionnel.

## <a name="create-azure-ad-conditional-access-policies-in-intune-azure-preview"></a>Création de stratégies d’accès conditionnel Azure AD dans la version préliminaire d’Intune Azure

À compter d’Intune version 1704, les administrateurs peuvent créer des stratégies d’accès conditionnel Azure AD depuis la version préliminaire d’Intune Azure, ce qui leur offre plus de commodité, car il n’est plus nécessaire de basculer entre les charges de travail Azure et Intune.

> [!IMPORTANT]
> Vous devez disposer d’une licence Azure AD Premium pour créer des stratégies d’accès conditionnel Azure AD à partir du portail de la version préliminaire d’Intune Azure.

### <a name="to-create-azure-ad-conditional-access-policy"></a>Pour créer une stratégie d’accès conditionnel Azure AD

1. Dans le **tableau de bord Intune**, choisissez **Accès conditionnel**.

2. Dans le **Tableau de bord d’accès conditionnel**, sélectionnez **Accès conditionnel dans Azure Active Directory**.

3. Choisissez **Nouvelle stratégie** pour créer votre nouvelle stratégie d’accès conditionnel Azure AD.

    ![Stratégies d’accès conditionnel Azure AD](../media/Azure-AD-CA-Intune.png)

## <a name="see-also"></a>Voir aussi

[Accès conditionnel dans Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access)
