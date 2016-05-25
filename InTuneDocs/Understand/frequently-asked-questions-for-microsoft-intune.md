---
# required metadata

title: Forum aux questions | Microsoft Intune
description:
keywords:
author: Nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: a8126cca-9ec4-454b-a20b-dc1bb6797327

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Forum aux questions sur Microsoft Intune
Cet article répond à certaines questions fréquemment posées sur Intune. Si la réponse à votre question ne figure pas dans cet article, [écrivez-vous](https://microsoftintune.uservoice.com/).

## Problèmes généraux

-   **Comment savoir quand le service Intune a été mis à jour ?**

    Connectez-vous à votre compte sur manage.microsoft.com. Dans Présentation de l’administration, choisissez **Afficher l’état du service**. L’emplacement de votre client et la planification de maintenance y sont indiqués. Pour en savoir plus sur les mises à jour de service, consultez l’article [Nouveautés](/intune/deploy-use/whats-new-in-microsoft-intune).

-   **Si un utilisateur renomme un appareil à partir de l’application du portail d’entreprise, ce nom sera-t-il modifié dans Intune ou Configuration Manager ?**

    Non, ce changement de nom n’est effectué que pour la commodité de l’utilisateur.

-   **Existe-t-il une fonctionnalité d’assistance à distance dans Intune pour les appareils mobiles ?**

    Non il n’y en a pas. Des applications tierces telles que [Bomgar](http://www.bomgar.com/) et [TeamViewer](https://www.teamviewer.com/) pourraient être utiles.

## Comptes

-   **Si je commence à évaluer Intune et que je crée un client pour la version d’évaluation, puis-je ajouter Office 365 à l’évaluation à l’aide du même client ?**

    Oui. Il vous suffit de vous connecter à l’aide d’un administrateur global de votre abonnement/client Intune existant, tel que *adminglobal@&lt;entreprise&gt;.onmicrosoft.com*.

-   **Si j’attribue l’autorité GPM à Intune pendant la période d’évaluation d’un abonnement, est-ce qu’il sera difficile de passer au service d’une autre entreprise si je change d’avis sur Intune ?**

    Bien qu’il soit difficile d’imaginer que vous ne conserverez pas Intune, le choix de l’autorité GPM n’affecte pas votre capacité à adopter un autre service. Il s’agit en particulier de choisir entre une gestion des appareils mobiles avec Intune ou Intune avec System Center Configuration Manager.

-   **Puis-je utiliser mon nom de domaine Office 365 existant pour mon compte Intune ?**

    Oui, si vous vous connectez avec l’ID d’organisation associé au client et au domaine vérifié Office 365 existants quand vous créez la version d’évaluation Intune ou activez vos licences.

    Intune utilise alors le même domaine/les mêmes utilisateurs/etc. que ceux de votre compte Office 365. Notez que chaque utilisateur Office 365 doit être activé en tant qu’utilisateur Intune, à l’aide d’une licence Intune. Cela doit être effectué par l’administrateur global qui gère le client.

## Inscription

-   **Où mes utilisateurs peuvent-ils trouver la procédure pour inscrire leurs appareils ?**

    Vous pouvez utiliser ou personnaliser les informations fournies dans les [Instructions d’inscription de l’utilisateur final dans Intune pour les administrateurs informatiques](https://gallery.technet.microsoft.com/End-user-Intune-enrollment-55dfd64a).

-   **Comment résoudre les problèmes liés à l’inscription des appareils ?**

    La rubrique [Résoudre les problèmes d’inscription d’appareils dans Intune](/intune/troubleshoot/troubleshoot-device-enrollment-in-intune) montre comment résoudre les problèmes d’inscription les plus courants..

-   **Comment collecter les journaux d’inscription si un utilisateur rencontre un problème d’inscription ?**

    Suivez [ces instructions](http://www.microsoft.com/en-us/download/46391).

## Gestion des appareils mobiles

-   **Gestion des périphériques mobiles – Général**

    -   **Intune peut-il détecter si un appareil est jailbroken ?**

        Oui, pour certains systèmes d’exploitation. Pour plus d’informations sur la façon de gérer les appareils jailbroken, consultez [Créer une stratégie de conformité des appareils](/intune/deploy-use/create-a-device-compliance-policy-in-microsoft-intune.md).

    -   **Puis-je réinitialiser de manière sélective les données d’entreprise d’un appareil ?**

        Oui. Pour plus d’informations sur la réinitialisation sélective, consultez [Protéger vos données à l’aide de la réinitialisation à distance, du verrouillage à distance ou de la réinitialisation du code d’accès](/intune/deploy-use/use-remote-lock-and-passcode-reset-in-microsoft-intune.md).

    -   **Existe-t-il un moyen de bloquer certains sites web sur le navigateur d’appareil mobile par le biais d’Intune ?**

        Non, sur aucun navigateur natif d’une plateforme. Cependant, vous pouvez autoriser ou bloquer des URL une fois que vous avez déployé Intune Managed Browser sur les appareils iOS et Android. Pour plus d’informations, consultez [Gérer l’accès à Internet à l’aide de stratégies Managed Browser](/intune/Deploy-Use/Manage-Internet-access-using-managed-browser-policies-with-Microsoft-Intune.md).

    -   **Pouvons-nous empêcher un utilisateur de désinstaller une application ?**

        En règle générale, non. Toutefois, sur un appareil iOS contrôlé, vous pouvez empêcher un utilisateur de désinstaller une application qui a été distribuée à l’aide de l’outil Apple Configurator. 

    -   **Existe-t-il un moyen de gérer l’utilisation des données mobiles ?**

        Pas directement, mais vous pouvez vérifier que le Wi-Fi est la méthode préférée pour la connexion en envoyant des profils Wi-Fi aux appareils, comme décrit dans [Aider les utilisateurs à se connecter aux réseaux d’entreprise à l’aide de profils Wi-Fi](/intune/Deploy-Use/wi-fi-connections-in-microsoft-intune.md). En outre, certaines plateformes (par exemple, iOS et Android KNOX) permettent de contrôler des paramètres comme la voix et l’itinérance des données.

    -   **Existe-t-il un moyen d’empêcher un utilisateur d’annuler l’inscription d’un appareil ? Que se passe-t-il s’il s’agit d’un appareil appartenant à l’entreprise ?**

        En général, non. Toutefois, en utilisant des paramètres personnalisés Windows Phone vous pouvez empêcher l’inscription des utilisateurs sur Windows Phone 8.1. En outre, pour les appareils iOS contrôlés et inscrits dans le programme d’inscription d’appareils (DEP) d’Apple, vous pouvez empêcher un utilisateur d’annuler l’inscription d’un appareil.

    -   **Puis-je modifier l’autorité GPM choisie ?**

        Vous pouvez changer l’autorité GPM dans certaines situations. Pour ce faire, contactez le Support technique, comme décrit dans [Comment obtenir un support technique pour Microsoft Intune](/intune/Troubleshoot/How-to-get-support-for-Microsoft-Intune.md). Le tableau ci-dessous décrit les modifications possibles. Les changements d’autorité GPM nécessitent la réinscription des appareils.

        ||**À :** Intune!**À :** O365|**À :** Configuration Manager avec Intune|
        |**De :** Intune| | Oui&#42;|Oui|
        |**De :** O365| | Oui&#42;|Oui|
        |**De :** Configuration Manager avec Intune|Oui|Oui| |
        
        &#42;Les autorités de Gestion des appareils mobiles Office 365 et Intune peuvent coexister. Vous n’avez donc pas à réinscrire les appareils mobiles.



-   **Windows**

    -   **Puis-je effectuer un chargement indépendant d’une application du Windows Store ?**

        Les applications disponibles publiquement ne peuvent pas faire l’objet d’un chargement indépendant. Même si vous êtes en mesure de télécharger le package XAP, vous ne pouvez pas le télécharger dans Intune, car il s’agit d’un package XAP public, chiffré et signé avec le certificat de signature de code du développeur. Seules les applications que vous développez et signez avec votre propre certificat de signature de code peuvent faire l’objet d’un chargement indépendant.

    -   **Les applications du Windows Phone Store distribuées par le biais du portail d’entreprise nécessitent-elles que l’utilisateur final possède un compte Microsoft ?**

        Oui, l’utilisateur final ne pourra pas obtenir les applications sans compte Microsoft. Seule exception : les applications métier privées ayant fait l’objet d’un chargement indépendant peuvent être déployées sur un appareil sans compte Microsoft.

    -   **Un compte Microsoft est-il nécessaire sur un Windows Phone 8.1 pour que ce dernier soit géré par Intune ?**

        Non. Toutefois, il est nécessaire pour installer la plupart des applications à partir du magasin public.

        **Pourquoi Windows Phone a-t-il besoin d'un certificat Symantec en matière de gestion ?**
        Windows Phone contrôle la façon dont vous pouvez installer des applications. Tout utilisateur titulaire d'un compte Microsoft peut installer des applications à partir du Windows Phone Store. Par ailleurs, les entreprises peuvent effectuer l'installation ou le chargement indépendant de leurs applications métier développées en interne via un processus spécial décrit dans la documentation de Windows Phone. Quand vous installez des applications métier, les appareils Windows Phone n'approuvent qu'un seul type particulier de certificat émis par Symantec. Vous ne pouvez pas utiliser d'autres certificats générés dans le cadre commercial ou privé. Cela est vrai pour toutes les solutions de gestion d'appareils mobiles, et pas seulement pour Intune.

        Le certificat Symantec crée un jeton d'inscription d'application (jeton AET). Le jeton AET peut être installé sur un appareil quand ce dernier s'inscrit pour la gestion des appareils mobiles. Il peut également être installé hors-bande à partir d'un site web sécurisé ou d'une pièce jointe de message électronique. Les administrateurs doivent signer chaque application métier avec le certificat Symantec, à l'aide des outils fournis dans le [Kit de développement logiciel (SDK) Windows Phone](http://go.microsoft.com/fwlink/?LinkId=268439). Quand des utilisateurs tentent d'installer des applications métier, le système d'exploitation Windows Phone vérifie la signature du jeton AET en la comparant à la signature de l'application. Si les signatures correspondent, l'installation est autorisée à se poursuivre. Si le jeton AET ne peut pas être vérifié, l'installation échoue. Il existe plusieurs raisons pour lesquelles le jeton AET ne peut pas être vérifié :

        -   Le jeton AET n'a jamais été installé sur l'appareil

        -   Le jeton AET a expiré

        -   Le jeton AET n'a pas été créé avec le même certificat Symantec que celui utilisé pour signer l'application

        Windows Phone n'a pas besoin que le jeton AET soit présent durant l'inscription MDM. Toutefois, avant la version de novembre 2014, Intune imposait la présence d'un jeton AET et d'un fichier ssp.xap signé, car il n'y avait aucun autre moyen d'installer le jeton AET et ssp.xap, sauf durant l'inscription.

    **Comment le jeton AET est-il créé pour les utilisateurs Intune ?**
  Quand les administrateurs téléchargent le fichier .pfx pour leur certificat Symantec, Intune crée automatiquement le jeton AET et le déploie sur les appareils Windows Phone inscrits. Il n'est pas nécessaire pour les administrateurs Intune d'utiliser l'outil de génération de jetons AET dans le Kit de développement logiciel (SDK) Windows Phone.

      > [!IMPORTANT]
        > Intune ne prend pas en charge la création manuelle du jeton AET et son déploiement hors-bande.

    **Quels sont les changements qui ont permis de limiter le recours à un certificat Symantec ?**
       Pour la version de novembre 2014, des changements ont été apportés à Intune pour autoriser les scénarios où les entreprises ne disposent pas d'un certificat Symantec.

       -   L'application Portail d'entreprise pour Windows Phone 8.1 peut être installée à partir du Store. Ainsi, il n'est pas nécessaire de la signer avec un certificat Symantec, ni de la valider par rapport à un jeton AET. À la place, l'application est validée dans le cadre du processus de publication du Store.

        -   Les appareils Windows Phone 8.1 peuvent s'inscrire avec ou sans jeton AET. Si un jeton AET est disponible, il est installé la première fois que l'appareil se synchronise à Intune. En l'absence de jeton AET, l'appareil peut toujours être géré par Intune. Les utilisateurs peuvent installer l'application Portail d'entreprise à partir du Store et accéder à la plupart des fonctionnalités de l'application Portail d'entreprise sans avoir besoin d'un certificat Symantec pour signer les applications.

        Il n'y a aucun changement concernant la nécessité de recourir à Symantec pour les appareils Windows Phone 8. Les appareils Windows Phone 8 doivent disposer du fichier ssp.xap signé et du jeton AET durant l'inscription. Sinon, ils ne peuvent pas effectuer l'inscription.

        **Quelles sont les fonctionnalités prises en charge si un appareil Windows Phone 8.1 est inscrit, mais sans certificat Symantec ?**
        Si un appareil Windows Phone 8.1 est inscrit, mais sans certificat Symantec, vous pouvez :

        -   créer des stratégies et effectuer une transmission de type push de ces dernières vers l'appareil ;

        -   configurer les informations de contact du service informatique, qui s'affichent dans l'application Portail d'entreprise ;

        -   créer des liens ciblés vers le Store et les déployer sur l'application Portail d'entreprise ;

        -   créer des liens vers des pages web et les déployer sur l'application Portail d'entreprise ;

        -   créer les conditions générales que les utilisateurs doivent accepter avant de pouvoir accéder à l'application Portail d'entreprise.

        La seule chose que vous ne pouvez pas faire sans certificat Symantec est le déploiement d'applications métier.

        > [!IMPORTANT]
        > L'éditeur de logiciel Intune ne vérifie pas si les applications sont signées quand vous les téléchargez. Si vous déployez des applications non signées, les utilisateurs ne pourront pas les installer.

        **Que peuvent faire les utilisateurs s'ils disposent de l'application Portail d'entreprise, mais pas d'un certificat Symantec ?**
        Les appareils Windows Phone 8.1 n'ont pas besoin d'être inscrits pour que les utilisateurs puissent installer l'application Portail d'entreprise à partir du Store. Si l'appareil n'est pas inscrit, les utilisateurs sont invités à effectuer l'inscription. Toute interaction tactile avec l’invite de l’application Portail d’entreprise mène directement les utilisateurs à **Paramètres / Espace de travail**, où ils peuvent inscrire leurs appareils.

        Même sans inscrire l'appareil, les utilisateurs peuvent effectuer les actions suivantes dans l'application Portail d'entreprise installée à partir du Store :

        -   Accepter ou refuser les conditions générales configurées par l'administrateur. Si les utilisateurs refusent les conditions générales, l'application Portail d'entreprise se ferme.

        -   Afficher les informations de contact du service informatique.

        -   Afficher les appareils inscrits, notamment les appareils iOS, Android et Windows.

        -   Utiliser des liens ciblés vers des applications du Store.

        -   Utiliser des liens web pour ouvrir des pages web.

        Une fois l'appareil inscrit, les utilisateurs peuvent le voir dans la liste **Mes appareils** . Une fois inscrit, l'appareil est soumis aux stratégies Intune déployées. Les appareils doivent être inscrits pour permettre l'obtention du jeton AET et l'installation d'applications métier. Un appareil non inscrit qui tente d'installer une application métier est redirigé vers le processus d'inscription.

        La seule chose que les utilisateurs ne peuvent pas faire si l'entreprise ne dispose pas d'un certificat Symantec est d'installer des applications métier déployées par l'administrateur.

        **Notre société dispose déjà d'un certificat et a effectué l'inscription d'appareils Windows Phone 8.1. Dois-je procéder différemment dans la mesure où l'application Portail d'entreprise est disponible dans le Store ?**
        Le fichier ssp.xap actuel du Centre de téléchargement fonctionne toujours sur les appareils Windows Phone 8.1. Vous pouvez continuer à indiquer aux utilisateurs de s'inscrire et de récupérer l'application Portail d'entreprise durant l'installation.

        **Quels sont les avantages et inconvénients de l'obtention de l'application Portail d'entreprise à partir du Store pour les utilisateurs ?**
        Avantages :

        -   Les utilisateurs obtiennent des liens ciblés et des liens web, même si l'appareil Windows Phone 8.1 n'est pas inscrit.

        -   Quand Microsoft met à jour l'application Portail d'entreprise, l'application de Store se met à jour automatiquement sans que vous soyez obligé de télécharger, de signer et de redéployer le fichier ssp.xap

        -   La documentation pour les utilisateurs Windows Phone 8.1, iOS, Android et Windows est cohérente : « Rendez-vous sur le Store et installez le portail d’entreprise. »

        -   Les utilisateurs voient l'application durant l'installation et obtiennent des instructions d'inscription quand elle s'ouvre.

        Inconvénients :

        -   les utilisateurs voient une case à cocher pour installer un «**hub Entreprise**», mais rien ne les dirige vers l'application Portail d'entreprise dans la liste des applications de l'appareil ;

        -   les utilisateurs ne sont pas obligés d'accepter les conditions générales personnalisées tant qu'ils n'ouvrent pas l'application Portail d'entreprise.

        Dans les cas suivants, vous pouvez continuer à indiquer aux utilisateurs de s'inscrire et d'installer ssp.xap durant l'inscription :

        -   si la société bloque l'accès au Store à partir d'appareils Windows Phone, les utilisateurs doivent installer ssp.xap durant l'inscription ;

        -   si les utilisateurs n'ont pas de comptes Microsoft configurés sur leurs appareils Windows Phone, ils ne peuvent pas installer l'application Portail d'entreprise à partir du Store ;

        -   si la documentation existante pour l'inscription d'appareils Windows Phone indique d'accéder d'abord à Paramètres, Espace de travail, la mise à jour des documents et la redirection des utilisateurs vers le Store peuvent prendre un certain temps.

        **Quelle est la différence entre le fichier ssp.xap du Centre de téléchargement et l'application présente dans le Store ?**

        -   l'application Portail d'entreprise du Store n'a pas besoin d'être signée à l'aide d'un certificat Symantec à installer ;

        -   l'application Portail d'entreprise du Store présente les conditions générales à l'utilisateur, contrairement au fichier ssp.xap du Centre de téléchargement ;

        -   l'application Portail d'entreprise du Store correspond à un fichier .aspx au lieu d'un fichier .xap.

        **Puis-je obtenir le fichier du portail d'entreprise et le distribuer à mes utilisateurs via une transmission de type push, au lieu de rediriger ces derniers vers le Store ?**
        Oui. Vous pouvez télécharger l'application Portail d'entreprise pour les systèmes d'exploitation suivants à partir du Centre de téléchargement :

        -   Windows Phone 8.1 : [http://go.microsoft.com/fwlink/?LinkId=615799](http://go.microsoft.com/fwlink/?LinkId=615799)

        -   Windows Phone 8.0 : [http://go.microsoft.com/fwlink/?LinkId=268440](http://go.microsoft.com/fwlink/?LinkId=268440)

        -   Windows 8.1 : [http://go.microsoft.com/fwlink/?LinkId=615800](http://go.microsoft.com/fwlink/?LinkId=615800)

        **Est-ce que les sociétés peuvent toujours utiliser l'outil de prise en charge de la gestion d'évaluation Windows Intune pour Windows Phone, si elles ne disposent pas d'un certificat Symantec. Par ailleurs, est-ce qu'elles peuvent toujours faire installer l'application Portail d'entreprise par les utilisateurs à partir du Store ?**
        Oui. Si vous devez effectuer une preuve de concept qui inclut l'installation d'applications métier, l'outil de gestion d'évaluation fonctionne avec la version du Store de l'application Portail d'entreprise. Toutefois, dans la mesure où le jeton AET du certificat Symantec n'est plus nécessaire pour inscrire des appareils Windows Phone 8.1, les sociétés peuvent tester l'installation d'applications à l'aide de liens ciblés qui pointent vers les applications du Store.

        L'outil de prise en charge de la gestion d'évaluation Windows Intune pour Windows Phone est réservé uniquement aux abonnements d'évaluation d'Intune.

        > [!IMPORTANT]
        > Utilisez uniquement la fonctionnalité de test de l'outil de gestion d'évaluation. Les appareils inscrits avec le jeton AET à partir de l'outil de gestion d'évaluation doivent annuler leur inscription et se réinscrire si le certificat Symantec de l'outil de gestion d'évaluation n'est plus disponible, ou si la société obtient son propre certificat Symantec pour la signature d'applications.

        **Est-ce que les sociétés peuvent démarrer sans certificat Symantec, puis en ajouter un plus tard, même après l'inscription d'appareils Windows Phone 8.1 ?**
        Oui. Même si des appareils Windows Phone 8.1 sont déjà inscrits, vous pouvez obtenir un certificat Symantec, signer le fichier ssp.xap, puis le télécharger avec le fichier pfx. Intune génère ensuite le jeton AET. Les appareils Windows Phone 8.1 récupèrent le jeton AET à la prochaine synchronisation, selon un délai qui peut aller jusqu'à huit heures. Attendez au moins huit heures avant de déployer des applications métier, une fois que vous avez téléchargé les fichiers xap et pfx.


-   **Android**

    -   **Combien de temps faut-il pour chiffrer un appareil Android ?**

        Cela dépend principalement de la vitesse du processeur de l’appareil et de la quantité de mémoire totale et utilisée. Cela ne dépend pas d’Intune.

-   **iOS**

    -   **Lors du déploiement d’applications iOS avec Intune, si les extensions IPA et le fichier manifeste de l’application ont été téléchargés, l’appareil a-t-il besoin d’un ID Apple spécifié pour poursuivre l’installation ?**

        Non. Quand Intune fournit les bits (extensions IPA téléchargées dans Intune), les applications font l’objet d’un téléchargement indépendant et ne nécessitent pas d’ID Apple.

    -   **Existe-t-il un moyen de permettre l’installation d’applications sur iOS sans autoriser l’accès à l’Apple Store ?**

        Non, mais vous pouvez activer l’App Store et utiliser les listes de blocage et d’autorisation d’applications sur iOS pour surveiller ce que font les utilisateurs. Les applications métier ayant fait l’objet d’un téléchargement indépendant ne nécessitent pas d’accès à l’App Store d’Apple.

    -   **Les applications de l’Apple Store distribuées par le biais du portail d’entreprise nécessitent-elles que l’utilisateur final possède un compte iTunes ?**

        Oui, l’utilisateur final ne pourra pas obtenir les applications sans compte iTunes.

    -   **Puis-je bloquer l’App Store ?**

        Oui vous pouvez, mais vous bloquez aussi toutes les installations et les mises à jour d’applications à partir de l’App Store, pas seulement celles initiées par l’utilisateur final. Cela signifie que les applications publiques de l’App Store que vous déployez à partir d’Intune échoueront également.

## Déploiement d'applications

-   **Comment ajouter une application recommandée ?**

    Dans Intune, elles sont nommées « applications proposées » et sont documentées dans [Déployer des applications dans Microsoft Intune](/Intune/Deploy-Use/deploy-apps-in-microsoft-intune.md).

-   **Puis-je obtenir du stockage cloud supplémentaire pour les applications que je veux déployer ?**

    Oui. Pour en savoir plus, consultez [Déployer des applications](/Intune/Deploy-Use/deploy-apps.md) dans la section *Configuration requise pour le stockage cloud*.

## Sécurité

-   **BitLocker peut-il être appliqué par Intune ?**

    L’agent OMA-DM de Windows 8.1/RT vous permet de lire (get) l’état de chiffrement. Vous ne pouvez pas le définir. Cela est vrai pour Intune et d’autres services de gestion d’appareils mobiles.

-   **Si je chiffre une tablette Windows 8 à l’aide de BitLocker, puis-je appliquer une réinitialisation complète de l’appareil si un utilisateur ne parvient pas à ouvrir une session plusieurs fois consécutives ?**

    Il n’existe aucune option de réinitialisation complète sur les appareils Windows 8.1/RT pour n’importe quel service de gestion de périphériques mobiles, y compris Intune. Intune propose une réinitialisation sélective pour ces appareils. Pour plus d’informations sur la réinitialisation complète ou sélective dans Intune, consultez [Protéger les données et les applications avec Microsoft Intune](/intune/Deploy-Use/protect-apps-and-data-with-microsoft-intune.md).

## Portail d'entreprise

-   **Puis-je personnaliser mon portail d'entreprise ?**

    Oui. Dans la console d’administration Intune, accédez à **Administration&gt;Portail d’entreprise** pour ces paramètres.

## Microsoft Intune avec Configuration Manager

-   **Lorsque j'utilise Configuration Manager avec Intune, où puis-je gérer mes périphériques ?**

    Gérez tous vos périphériques à partir de la console Configuration Manager, même si les périphériques sur lesquels l'agent Intune est installé apparaîtront dans la console Intune. Les périphériques mobiles n'apparaîtront pas dans la console Intune.

-   **Puis-je effectuer une réinitialisation sélective sur des appareils ?**

    Si vous utilisez System Center 2012 R2 Configuration Manager ou version ultérieure avec Intune, vous pouvez effectuer une réinitialisation sélective qui supprime les données de l’entreprise. Pour plus d’informations, consultez [Protéger les données et les applications avec Microsoft Intune](/intune/Deploy-Use/protect-apps-and-data-with-microsoft-intune.md).

-   **Si j’utilise Configuration Manager avec Intune, puis-je continuer à utiliser le portail de gestion Intune ?**

    Vous le pouvez, mais seuls les PC sur lesquels l’agent Intune est installé peuvent être gérés à partir de ce portail. Il existe également d’autres informations utiles dans le portail concernant les alertes sur le service, l’état du service, etc., mais ces paramètres de gestion de périphériques ne s’appliquent pas aux appareils inscrits.



<!--HONumber=May16_HO1-->


