---
title: "Accéder à la messagerie d’entreprise en utilisant des profils de messagerie | Microsoft Intune"
description: "Vous pouvez utiliser des paramètres de profil de messagerie pour configurer les paramètres d’accès à la messagerie électronique pour des clients de messagerie spécifiques sur les appareils mobiles."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 11/10/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 10f0cd61-e514-4e44-b13e-aeb85a8e53ae
ms.reviewer: karanda
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: f0c5920f7cc46e40bf4d1795a68ba1d67840fcfa
ms.openlocfilehash: 6ac7034ba0713c7b6bdd28c7b53b99c247d3aeb3


---

# <a name="configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune"></a>Configurer l’accès à la messagerie d’entreprise à l’aide de profils de messagerie avec Microsoft Intune

[!INCLUDE[wit_nextref](../includes/afw_rollout_disclaimer.md)]

De nombreuses plateformes mobiles incluent un client de messagerie natif fourni avec le système d’exploitation. Certains de ces clients peuvent être configurés à l’aide de profils de messagerie, comme décrit dans cette rubrique.

Vous pouvez utiliser des paramètres de profil de messagerie pour configurer les paramètres d’accès à la messagerie pour des clients de messagerie spécifiques sur les appareils mobiles. Sur les plateformes prises en charge, les clients de messagerie natifs peuvent être configurés par Microsoft Intune pour permettre aux utilisateurs d’accéder à leur messagerie d’entreprise sur les appareils personnels sans aucune configuration supplémentaire.

Si vous avez besoin d’une protection supplémentaire contre la perte de données, utilisez l’[accès conditionnel](restrict-access-to-email-and-o365-services-with-microsoft-intune.md), qui contrôle l’accès à la boîte aux lettres de l’utilisateur pour n’importe quel client de messagerie, notamment les clients de messagerie natifs.

Les administrateurs informatiques ou les utilisateurs peuvent choisir d’installer d’autres clients de messagerie (par exemple Microsoft Outlook pour Android ou iOS). Ces clients de messagerie peuvent ne pas prendre en charge les profils de messagerie, et ne sont pas configurables à l’aide des profils de messagerie Intune.  

Vous pouvez utiliser des profils de messagerie pour configurer le client de messagerie natif sur les types d’appareils suivants :
-   Windows Phone 8.1 et versions ultérieures
-   Windows 10 (pour le bureau), Windows 10 Mobile et versions ultérieures
-   iOS 8.0 et versions ultérieures
-   Samsung KNOX Standard (4.0 et versions ultérieures)
-   Android for Work

>[!NOTE]
>Intune fournit deux profils de messagerie Android for Work, un pour chacune des applications de messagerie Gmail et Nine Work. Ces applications sont disponibles dans le Google Play Store et prennent en charge les connexions à Exchange. Pour activer la connectivité d’e-mail, déployez une de ces applications de messagerie sur les appareils de vos utilisateurs, puis créez et déployez le profil approprié.

Outre la configuration d’un compte de messagerie sur l’appareil, vous pouvez configurer le volume d’e-mails à synchroniser et, en fonction du type d’appareil, les types de contenu à synchroniser.

>[!NOTE]
>
>Si l’utilisateur a installé un profil de messagerie avant de configurer un profil via Intune, le résultat du déploiement du profil de messagerie Intune dépend de la plateforme d’appareil :

>**iOS** : Un profil de messagerie existant en double est détecté en fonction de l’adresse e-mail et du nom d’hôte. Le profil de messagerie en double créé par l’utilisateur bloque le déploiement d’un profil créé par un administrateur Intune. Il s’agit d’un problème courant, car les utilisateurs iOS créent généralement un profil de messagerie, puis s’inscrivent. Le portail d’entreprise signale à l’utilisateur qu’il n’est pas conforme à cause de son profil de messagerie configuré manuellement, et invite l’utilisateur à supprimer ce profil. L’utilisateur doit supprimer son profil de messagerie pour que le profil Intune puisse être configuré. Pour éviter ce problème, demandez à vos utilisateurs de s’inscrire avant d’installer le profil de messagerie et d’autoriser Intune à configurer le profil.

>**Windows** : Un profil de messagerie existant en double est détecté en fonction de l’adresse e-mail et du nom d’hôte. Intune remplace le profil de messagerie existant créé par l’utilisateur.

>**Samsung KNOX** : Un profil de messagerie existant en double est détecté en fonction de l’adresse e-mail, et est remplacé par le profil Intune. Si l’utilisateur configure ce compte, il est remplacé à nouveau par le profil Intune. Notez que cela peut entraîner une certaine confusion pour l’utilisateur.

>Étant donné que Samsung KNOX n’utilise pas le nom d’hôte pour identifier le profil, nous vous recommandons de ne pas créer plusieurs profils de messagerie à utiliser à la même adresse e-mail sur des hôtes différents, car ils se remplaceront l’un l’autre.

>**Android for Work** : le profil Intune est appliqué uniquement à des applications de messagerie spécifiques du profil professionnel de l’appareil et n’affecte pas la configuration de messagerie sur le profil utilisateur de l’appareil.


## <a name="secure-email-profiles"></a>Profils de messagerie sécurisés
Vous pouvez sécuriser les profils de messagerie à l’aide d’un certificat ou d’un mot de passe.

### <a name="certificates"></a>Certificats
Quand vous créez le profil de messagerie, vous choisissez un profil de certificat que vous avez créé précédemment dans Intune. Il s’agit du certificat d’identité, qui est utilisé pour l’authentification par rapport à un profil de certificat approuvé (ou un certificat racine) pour établir le fait que l’utilisateur est autorisé à se connecter. Le certificat approuvé est déployé sur l’ordinateur qui authentifie la connexion de messagerie, en général le serveur de messagerie natif.

Pour plus d’informations sur la création et l’utilisation des profils de certificat dans Intune, consultez [Sécuriser l’accès aux ressources avec des profils de certificat](secure-resource-access-with-certificate-profiles.md)).

### <a name="user-name-and-password"></a>Nom d'utilisateur et mot de passe
L’utilisateur s’authentifie auprès du serveur de messagerie natif en fournissant son nom d’utilisateur et son mot de passe.

Comme le mot de passe n’est pas contenu dans le profil de messagerie, l’utilisateur doit le fournir quand il se connecte à sa messagerie.

### <a name="create-an-email-profile"></a>Créer un profil de messagerie

1.  Dans la [console d’administration Microsoft Intune](https://manage.microsoft.com), choisissez **Stratégie** &gt; **Ajouter une stratégie**.

2.  Configurez l’un des types de stratégies suivants :

    -   **Profil de messagerie pour Samsung KNOX Standard (4.0 et versions ultérieures)**

    -   **Profil d’e-mail (iOS 8.0 et ultérieur)**

    -   **Profil d’e-mail (Windows Phone 8.1 et ultérieur)**

    -   **Profil de messagerie (Windows 10 Desktop et Mobile, et ultérieur)**

    -   **Profil d’e-mail (Android for Work - Gmail)**

    -   **Profil d’e-mail (Android for Work - Nine Work)**

    Vous pouvez uniquement créer et déployer une stratégie de profil de messagerie personnalisée. Les paramètres recommandés ne sont pas disponibles.

3.  Utilisez le tableau suivant pour vous aider à configurer les paramètres de profil de messagerie :

|Nom du paramètre | Plus d'informations|
| ----------- | --------------- |
    |**Nom**|Nom unique du profil de messagerie.|
    |**Description**|Description qui vous aide à identifier ce profil.|
    |**Hôte**|Nom d’hôte du serveur de votre société qui héberge votre service de messagerie natif.|
    |**Nom du compte**|Nom complet du compte de messagerie, tel qu’il apparaîtra aux utilisateurs sur leurs appareils.|
    |**Nom d’utilisateur**|Il s’agit de l’attribut dans Active Directory (AD) ou Azure AD, qui doit être utilisé pour générer le nom d’utilisateur de ce profil de messagerie. Sélectionnez l’adresse SMTP principale, comme *user1@contoso.com* ou le nom d’utilisateur principal, comme *user1* ou *user1@contoso.com*.|
    |**Adresse de messagerie**|Façon dont l’adresse de messagerie de l’utilisateur est générée sur chaque appareil. Sélectionnez **Adresse SMTP principale** pour utiliser l’adresse SMTP principale pour vous connecter à Exchange ou **Nom principal de l’utilisateur** pour utiliser le nom principal complet comme adresse de messagerie.|
    |**Méthode d’authentification** (Android for Work, Samsung KNOX et iOS)|Sélectionnez **Nom d’utilisateur et mot de passe** ou **Certificats** comme méthode d’authentification utilisée par le profil de messagerie.|
    |**Sélectionner un certificat client pour l’authentification client (certificat d’identité)** (Android for Work, Samsung KNOX et iOS)|Sélectionnez le certificat SCEP client que vous avez créé précédemment qui servira à authentifier la connexion Exchange. Pour plus d’informations sur la façon de créer des profils de certificat dans Intune, consultez [Sécuriser l’accès aux ressources avec des profils de certificat](secure-resource-access-with-certificate-profiles.md). Cette option est visible uniquement quand la méthode d'authentification est **Certificats**.|
    |**Utiliser S/MIME** (Samsung KNOX et iOS)|Envoyez des messages électroniques en utilisant le chiffrement S/MIME.|
    |**Certificat de signature** (Samsung KNOX et iOS)|Sélectionnez le certificat de signature qui sera utilisé pour signer le courrier électronique sortant. Cette option est visible uniquement quand vous sélectionnez **Utiliser S/MIME**.|
    |**Nombre de jours de courrier électronique à synchroniser**|Nombre de jours d’e-mails à synchroniser, ou sélectionnez **Illimité** pour synchroniser tous les e-mails disponibles.|
    |**Planification de la synchronisation** (Android for Work, Samsung KNOX, Windows Phone 8 et versions ultérieures, Windows 10)|Sélectionnez la planification selon laquelle les appareils vont synchroniser les données du serveur Exchange. Vous pouvez également sélectionner **À mesure que les messages arrivent** pour synchroniser les données dès qu’elles arrivent ou **Manuel** pour que ce soit l’utilisateur de l’appareil qui lance la synchronisation.|
    |**Utiliser SSL**|Utilisez la communication SSL (Secure Sockets Layer) pour envoyer et recevoir des e-mails, et communiquer avec le serveur Exchange. Pour les appareils qui exécutent Samsung KNOX 4.0 ou version ultérieure, vous devez exporter votre certificat SSL Exchange Server et le déployer comme profil de certificat approuvé par Android dans Intune. Intune ne prend pas en charge l’accès à ce certificat s’il est installé sur le serveur Exchange par d’autres moyens.|
    |**Type de contenu à synchroniser** (toutes les plateformes sauf Android for Work Gmail)|Sélectionnez les types de contenu à synchroniser avec des appareils.|
    |**Autoriser l’envoi de courrier électronique à partir d’applications tierces** (iOS uniquement)|Autoriser l’utilisateur à sélectionner ce profil en tant que compte par défaut pour l’envoi d’e-mails et autoriser les applications tierces à ouvrir les e-mails dans l’application de messagerie native, par exemple pour y joindre des fichiers.|

> [!IMPORTANT]
>
> Si vous avez déployé un profil de messagerie et que vous souhaitez ensuite modifier les valeurs **Hôte** ou **Adresse de messagerie**, vous devez supprimer le profil de messagerie existant et en créer un avec les valeurs requises.

4.  Quand vous avez terminé, cliquez sur **Enregistrer la stratégie**.

La nouvelle stratégie s'affiche sous le nœud **Stratégies de configuration** de l'espace de travail **Stratégie** .

## <a name="deploy-the-policy"></a>Déploiement de la stratégie

1.  Dans l’espace de travail **Stratégie**, sélectionnez la stratégie à déployer, puis choisissez **Gérer le déploiement**.

2.  Dans la boîte de dialogue **Gérer le déploiement** :

    -   **Pour déployer la stratégie** : sélectionnez un ou plusieurs groupes sur lesquels déployer la stratégie, puis choisissez **Ajouter** &gt; **OK**.

    -   **Pour fermer la boîte de dialogue sans la déployer**, choisissez **Annuler**.

Un récapitulatif de l'état et des alertes identifient, dans la page **Vue d'ensemble** de l'espace de travail **Stratégie** , les problèmes liés à la stratégie qui nécessitent votre attention. En outre, le Tableau de bord contient un récapitulatif de l'état.

> [!NOTE]
> - Pour Android for Work, vérifiez que vous déployez également les applications Gmail ou Nine Work en plus du profil de messagerie approprié.
> - Si vous souhaitez supprimer un profil de messagerie d'un appareil, modifiez le déploiement et supprimez les groupes dont l'appareil est membre.



<!--HONumber=Nov16_HO3-->


