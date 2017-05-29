## <a name="march-2017"></a>Mars 2017

### <a name="new-capabilities"></a>Nouvelles fonctionnalités

#### <a name="support-for-skycure"></a>Prise en charge de Skycure

Vous pouvez désormais contrôler l’accès des appareils mobiles aux ressources d’entreprise, à l’aide d’un accès conditionnel basé sur une évaluation des risques effectuée par Skycure, une solution de protection contre les menaces mobiles qui s’intègre à Microsoft Intune. Le risque est évalué en fonction des données de télémétrie recueillies par les appareils exécutant Skycure, notamment :

- Défense physique
- Défense du réseau
- Défense des applications
- Défense contre les vulnérabilités

Vous pouvez configurer des stratégies d’accès conditionnel EMS basées sur l’évaluation des risques de Skycure, activée par le biais des stratégies de conformité Intune. Vous pouvez utiliser ces stratégies pour autoriser ou bloquer l’accès des appareils non conformes aux ressources d’entreprise, en fonction des menaces détectées. Pour en savoir plus, voir [Connecteur Skycure Mobile Threat Defense](/intune-classic/deploy-use/skycure-mobile-threat-defense-connector).

#### <a name="new-user-experience-for-the-company-portal-app-for-android---621622--"></a>Nouvelle expérience utilisateur dans l’application Portail d’entreprise pour Android <!--621622-->

L’application Portail d’entreprise pour Android a mis à jour son interface utilisateur afin d’en moderniser l’aspect et d’améliorer l’expérience utilisateur. Les mises à jour notables sont les suivantes :

- Couleurs : les en-têtes de l’onglet Portail d’entreprise sont colorés selon une personnalisation définie par le service informatique.
- Applications : dans l’onglet **Applications**, les boutons **Applications proposées** et **Toutes les applications** sont mis à jour.
- Recherche : dans l’onglet **Applications**, le bouton **Rechercher** est un bouton d’action flottant.
- Navigation dans les applications : la vue **Toutes les applications** affiche une vue comprenant les onglets **Applications proposées**, **Toutes les applications** et **Catégories** pour faciliter la navigation.
- Support : les onglets **Mes appareils** et **Contacter le service informatique** sont mis à jour pour améliorer la lisibilité.

Pour plus d’informations sur ces modifications, consultez [Mises à jour de l’interface utilisateur pour les applications utilisateur final Intune](/intune-classic/whats-new/whats-new-in-intune-app-ui).

#### <a name="non-managed-devices-can-access-assigned-apps---664691--"></a>Les appareils non gérés peuvent accéder aux applications attribuées <!--664691-->

Dans le cadre des modifications conceptuelles du site web du portail d’entreprise, les utilisateurs iOS et Android peuvent installer les applications attribuées indiquées comme « disponibles sans inscription » sur leurs appareils non gérés. À l’aide de leurs informations d’identification Intune, les utilisateurs peuvent se connecter au site web du portail d’entreprise et afficher la liste des applications qui leur sont attribuées. Les packages des applications « disponibles sans inscription » peuvent être téléchargés sur le site web du portail d’entreprise. Les applications dont l’installation nécessite une inscription ne sont pas affectées par cette modification, car les utilisateurs sont invités à inscrire leur appareil s’ils souhaitent installer ces applications.

#### <a name="signing-script-for-windows-10-company-portal---941642--"></a>Script de signature pour le portail d’entreprise Windows 10 <!--941642-->

Si vous avez besoin de télécharger de l’application Portail d’entreprise Windows 10 et d’en charger une version test, vous pouvez à présent utiliser un script qui simplifie le processus de signature d’application pour votre organisation.   Pour télécharger le script et les instructions d’utilisation, consultez [Microsoft Intune Signing Script for Windows 10 Company Portal](https://aka.ms/win10cpscript) (Script de signature Microsoft Intune pour le portail d’entreprise Windows 10) sur la galerie TechNet. Pour plus d’informations sur cette annonce, consultez [Mise à jour de votre application de portail d’entreprise Windows 10](https://blogs.technet.microsoft.com/intunesupport/2017/03/13/updating-your-windows-10-company-portal-app/) sur le blog de l’équipe de support technique Intune.


### <a name="notices"></a>Remarques

#### <a name="support-for-ios-103"></a>Prise en charge d’iOS 10.3

Le déploiement de la version 10.3 d’iOS a débuté le 27 mars 2017 pour les utilisateurs d’iOS. Tous les scénarios MDM et MAM Intune existants sont compatibles avec la dernière version du système d’exploitation Apple. Toutes les fonctionnalités Intune existantes actuellement disponibles pour la gestion des appareils iOS devraient continuer à fonctionner une fois les appareils des utilisateurs migrés vers iOS 10.3.

Actuellement, nous n’avons aucun problème connu à signaler. Si vous rencontrez des problèmes liés à iOS 10.3, n’hésitez pas à contacter [l’équipe de support Intune](/intune-classic/troubleshoot/contact-assisted-phone-support-for-microsoft-intune).

#### <a name="improved-support-for-android-users-based-in-china---720444--"></a>Amélioration du support pour les utilisateurs Android basés en Chine <!--720444-->

En l’absence de Google Play Store en Chine, les appareils Android doivent obtenir les applications sur les places de marché chinoises. L’application Portail d’entreprise prendra en charge ce flux de travail en redirigeant les utilisateurs Android en Chine vers le téléchargement des applications Portail d’entreprise et Outlook à partir des boutiques d’applications locales. Cette approche améliorera l’expérience utilisateur lorsque les stratégies d’accès conditionnel seront activées, à la fois pour la gestion des appareils mobiles et pour la gestion des applications mobiles. Les applications Portail d’entreprise et Outlook pour Android sont disponibles dans les boutiques d’applications chinoises suivantes :

- [Baidu](https://go.microsoft.com/fwlink/?linkid=836946)
- [Xiaomi](https://go.microsoft.com/fwlink/?linkid=836947)
- [Tencent](https://go.microsoft.com/fwlink/?linkid=836949)
- [Huawei](https://go.microsoft.com/fwlink/?linkid=836948)
- [Wandoujia](https://go.microsoft.com/fwlink/?linkid=836950)

#### <a name="best-practice-make-sure-your-company-portal-apps-are-up-to-date---879465--"></a>Meilleures pratiques : vérifiez que vos applications Portail d’entreprise sont à jour <!--879465-->

En décembre 2016, nous avons publié une mise à jour qui a activé l’authentification multifacteur (MFA) sur un groupe d’utilisateurs lorsque ceux-ci inscrivent un appareil iOS, Android, Windows 8.1+ ou Windows Phone 8.1+. Cette fonctionnalité ne peut pas fonctionner sans certaines versions de ligne de base de l’application Portail d’entreprise pour Android (v5.0.3419.0 +) et iOS (v2.1.17+).

Microsoft améliore en permanence Intune en ajoutant de nouvelles fonctions aussi bien à la console qu’aux applications Portail d’entreprise sur toutes les plateformes prises en charge. Par conséquent, Microsoft publie uniquement des correctifs pour les problèmes que nous trouvons dans la version actuelle de l’application Portail d’entreprise. Il est donc recommandé d’utiliser les dernières versions des applications Portail d’entreprise pour bénéficier d’une expérience utilisateur optimale.

>[!Tip]
> Demandez à vos utilisateurs de définir leurs appareils de façon à ce qu’ils mettent à jour automatiquement les applications à partir de l’App Store approprié. Si vous avez partagé l’application Portail d’entreprise Android sur un partage réseau, vous pouvez télécharger la dernière version à partir du [Centre de téléchargement Microsoft](https://www.microsoft.com/download/details.aspx?id=49140).

#### <a name="microsoft-teams-is-now-enabled-for-mam-on-ios-and-android"></a>Microsoft Teams est maintenant activé pour MAM sur iOS et Android

Microsoft a annoncé la disponibilité générale de Microsoft Teams. Les applications Microsoft Teams mises à jour pour iOS et Android sont maintenant activées avec les fonctionnalités de gestion des applications mobiles Intune (MAM). Vous donnez ainsi la possibilité à vos équipes de travailler librement sur les appareils, tout en veillant à ce que les conversations et les données d’entreprise soient protégées en permanence. Pour plus d’informations, consultez l’[annonce Microsoft Teams](https://blogs.technet.microsoft.com/enterprisemobility/2017/03/14/microsoft-teams-is-now-generally-available-and-mam-enabled-on-ios-and-android/) sur le blog Enterprise Mobility and Security.


## <a name="february-2017"></a>Février 2017

### <a name="new-capabilities"></a>Nouvelles fonctionnalités

### <a name="modernizing-the-company-portal-website---753980--"></a>Modernisation du site web du portail d’entreprise <!--753980-->
Le site web du portail d’entreprise prend en charge les applications destinées aux utilisateurs qui n’ont pas d’appareils gérés. Le site web s’aligne sur les autres produits et services Microsoft et utilise un nouveau modèle de couleurs contrastées, des illustrations dynamiques et un « menu hamburger », ![Petite image du menu hamburger désormais ajouté en haut à gauche du site web du portail d’entreprise](/intune-classic/whats-new/whats-new-in-intune-app-ui).

### <a name="notices"></a>Remarques

#### <a name="group-migration-will-not-require-any-updates-to-groups-or-policies-for-ios-devices---898837--"></a>La migration de groupe n’implique pas la mise à jour des groupes ou des stratégies pour les appareils iOS<!--898837-->
Pour chaque groupe d’appareils Intune préattribué par un profil d’inscription des appareils de l’entreprise, un groupe d’appareils dynamique correspondant est créé dans AAD à partir du nom du profil d’inscription des appareils de l’entreprise pendant la migration vers des groupes d’appareils Azure Active Directory. De cette façon, les appareils inscrits sont automatiquement regroupés et reçoivent les mêmes stratégies et applications que le groupe Intune d’origine.

Dès qu’un client entre dans l’étape de regroupement et de ciblage du processus de migration, Intune crée automatiquement un groupe AAD dynamique qui correspond à un groupe Intune ciblé par un profil d’inscription des appareils de l’entreprise. Si l’administrateur Intune supprime le groupe Intune cible, le groupe AAD dynamique correspondant n’est pas supprimé. Les membres du groupe et la requête dynamique disparaissent, mais le groupe lui-même est conservé jusqu’à ce que l’administrateur informatique le supprime dans le portail AAD.

De même, si l’administrateur informatique change le groupe Intune qui est ciblé par un profil d’inscription des appareils de l’entreprise, Intune crée un groupe dynamique qui reflète la nouvelle attribution de profil, mais ne supprime pas le groupe dynamique créé pour l’ancienne attribution.

### <a name="defaulting-to-managing-windows-desktop-devices-through-windows-settings---663050--"></a>Gestion par défaut des appareils de bureau Windows via les paramètres Windows <!--663050-->
Le comportement par défaut pour l’inscription d'ordinateurs de bureau Windows 10 change. Les nouvelles inscriptions se feront via le flux d'inscription d'agent MDM classique plutôt que via l’agent PC. Le site Web du portail d’entreprise fournira aux utilisateurs d'ordinateurs de bureau Windows 10 des instructions d’inscription qui les guideront tout au long du processus d’ajout d’ordinateurs de bureau Windows 10 comme appareils mobiles. Cela n’affectera pas les ordinateurs actuellement inscrits, et votre organisation pourra toujours gérer des ordinateurs de bureau Windows 10 à l’aide de l’agent PC [si vous préférez](/intune-classic/deploy-use/set-up-windows-device-management-with-microsoft-intune).

#### <a name="improving-mobile-app-management-support-for-selective-wipe---581242--"></a>Amélioration de la prise en charge de la gestion des applications mobiles pour la réinitialisation sélective <!--581242-->
Les utilisateurs finaux recevront des instructions supplémentaires sur la façon de récupérer l’accès aux données professionnelles ou scolaires si ces données sont supprimées automatiquement en raison de la stratégie de « Intervalle en mode hors connexion avant la réinitialisation des données d’application ».<!--, or the removal of the Intune Company Portal on Android.-->

#### <a name="company-portal-for-ios-links-open-inside-the-app---665954--"></a>Le portail d’entreprise pour obtenir des liens iOS s'ouvrir au sein de l’application<!--665954-->
Les liens au sein de l’application Portail d’entreprise pour iOS, y compris ceux vers la documentation et les applications, s’ouvriront directement dans l’application Portail d’entreprise à l’aide d’une vue dans l’application de Safari. Cette mise à jour sera disponible séparément à partir de la mise à jour de service de janvier.

#### <a name="new-mdm-server-address-for-windows-devices---893007--"></a>Nouvelle adresse du serveur MDM pour les appareils Windows <!--893007-->
Les utilisateurs de Windows et Windows Phone ne parviennent pas à inscrire un appareil s’ils entrent __manage.microsoft.com__ comme adresse du serveur MDM (s’ils y sont invités). L’adresse du serveur MDM __manage.microsoft.com__ devient __enrollment.manage.microsoft.com__. Demandez à vos utilisateurs d’utiliser __enrollment.manage.microsoft.com__ comme adresse du serveur MDM, s’ils y sont invités lors de l’inscription d’un appareil Windows ou Windows Phone. Aucune modification de votre configuration CNAME n’est nécessaire. Pour plus d’informations sur cette modification, visitez [aka.ms/intuneenrollsvrchange](https://aka.ms/intuneenrollsvrchange).

#### <a name="new-user-experience-for-the-company-portal-app-for-android---621622--"></a>Nouvelle expérience utilisateur dans l’application Portail d’entreprise pour Android <!--621622-->
À compter de mars, l’application Portail d’entreprise pour Android suit les [directives de conception matérielle](https://material.io/guidelines/material-design/introduction.html) pour créer une apparence plus moderne. Cette expérience utilisateur améliorée inclut les éléments suivants :

* __Couleurs__ : La couleur de l’en-tête des onglets peut être assortie à votre palette de couleurs personnalisée.
* __Interface__ : Les boutons Applications proposées et Toutes les applications ont été mis à jour sous l’onglet Applications. Le bouton Rechercher est désormais un bouton d’action flottant.
* __Navigation__ : Le bouton Toutes les applications propose une vue comprenant les onglets Applications proposées, Toutes les applications et Catégories pour faciliter la navigation.
* __Service__ : Les onglets Mes appareils et Contacter le service informatique sont plus lisibles.

Des images « Avant » et « Après » sont disponibles dans la [page des mises à jour de l’interface utilisateur](/intune-classic/whats-new/whats-new-in-intune-app-ui).

### <a name="associate-multiple-management-tools-with-the-windows-store-for-business---926135--"></a>Associer plusieurs outils de gestion à Windows Store pour Entreprises <!--926135-->
Si vous utilisez plusieurs outils de gestion pour déployer des applications Windows Store pour Entreprises, vous ne pouviez associer qu’un seul outil au Windows Store pour Entreprises. Désormais, vous pouvez associer plusieurs outils de gestion au Windows Store, par exemple, Intune et Configuration Manager. Pour plus d’informations, consultez [Gérer les applications que vous avez achetées dans le Windows Store pour Entreprises avec Microsoft Intune](/intune-classic/deploy-use/manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune#associate-your-windows-store-for-business-account-with-intune).

## <a name="whats-new-in-the-public-preview-of-the-intune-admin-experience-on-azure---736542--"></a>Nouveautés de la préversion publique de l’expérience d’administrateur Intune sur Azure <!--736542-->

Début 2017, nous migrerons l’intégralité de notre expérience administrateur vers Azure, permettant ainsi une gestion puissante et intégrée des principaux flux de travail EMS sur une plateforme de services moderne et extensible à l’aide des API Graph.

Les nouveaux locataires de test pourront accéder à la préversion publique de la nouvelle expérience administrateur dans le portail Azure ce mois-ci. Dans un état d’aperçu, les fonctionnalités et la parité avec la console Intune existante seront remises en mode itératif.

L’expérience administrateur dans le portail Azure utilisera la nouvelle fonctionnalité de regroupement et de ciblage précédemment annoncée ; lorsque votre client existant est migré vers la nouvelle expérience de regroupement, vous le serez également afin d’afficher un aperçu de la nouvelle expérience administrateur sur votre client. En attendant, si vous souhaitez tester ou examiner toute nouvelle fonctionnalité avant la migration du client, inscrivez-vous à un nouveau compte d’évaluation Intune ou consultez la [nouvelle documentation](/intune/whats-new).

Vous pouvez découvrir les nouveautés de la préversion Intune dans Azure [ici](/intune/whats-new).

## <a name="january-2017"></a>Janvier 2017

### <a name="new-capabilities"></a>Nouvelles fonctionnalités

#### <a name="in-console-reports-for-mam-without-enrollment---677961--"></a>Rapports dans la console pour MAM sans inscription <!--677961-->
De nouveaux rapports de protection des applications ont été ajoutés pour les appareils inscrits et les appareils qui n’ont pas été inscrits. Vous trouverez plus d'informations sur la façon dont vous pouvez [surveiller les stratégies de gestion des applications mobiles avec Intune ici](/intune-classic/deploy-use/monitor-mobile-app-management-policies-with-microsoft-intune).

#### <a name="android-711-support---694397--"></a>Prise en charge d’Android 7.1.1 <!--694397-->
Intune prend désormais entièrement en charge et gère Android 7.1.1.

#### <a name="resolve-issue-where-ios-devices-are-inactive-or-the-admin-console-cannot-communicate-with-them---unknown--"></a>Résoudre le problème quand les appareils iOS sont inactifs ou que la console d’administration ne peut pas communiquer avec eux <!--unknown-->
Quand les appareils des utilisateurs perdent le contact avec Intune, vous pouvez leur appliquer de nouvelles étapes de dépannage pour leur permettre de récupérer l’accès aux ressources d’entreprise. Consultez [Les appareils sont inactifs ou la console d’administration ne peut pas communiquer avec eux](/intune-classic/troubleshoot/troubleshoot-device-enrollment-in-intune#devices-are-inactive-or-the-admin-console-cannot-communicate-with-them).

### <a name="notices"></a>Remarques

#### <a name="defaulting-to-managing-windows-desktop-devices-through-windows-settings---663050--"></a>Gestion par défaut des appareils de bureau Windows via les paramètres Windows <!--663050-->
Le comportement par défaut pour l’inscription d'ordinateurs de bureau Windows 10 change. Les nouvelles inscriptions se feront via le flux d'inscription d'agent MDM classique plutôt que via l’agent PC.

Le site Web du portail d’entreprise fournira aux utilisateurs d'ordinateurs de bureau Windows 10 des instructions d’inscription qui les guideront tout au long du processus d’ajout d’ordinateurs de bureau Windows 10 comme appareils mobiles. Cela n’affectera pas les ordinateurs actuellement inscrits, et votre organisation pourra toujours gérer des ordinateurs de bureau Windows 10 à l’aide de l’agent PC [si vous préférez](/intune-classic/deploy-use/set-up-windows-device-management-with-microsoft-intune).

#### <a name="improving-mobile-app-management-support-for-selective-wipe---581242--"></a>Amélioration de la prise en charge de la gestion des applications mobiles pour la réinitialisation sélective <!--581242-->
Les utilisateurs finaux recevront des instructions supplémentaires sur la façon de récupérer l’accès aux données professionnelles ou scolaires si ces données sont supprimées automatiquement en raison de la stratégie de « Intervalle en mode hors connexion avant la réinitialisation des données d’application ».<!--, or the removal of the Intune Company Portal on Android.-->

#### <a name="company-portal-for-ios-links-open-inside-the-app---665954--"></a>Le portail d’entreprise pour obtenir des liens iOS s'ouvrir au sein de l’application<!--665954-->
Les liens au sein de l’application Portail d’entreprise pour iOS, y compris ceux vers la documentation et les applications, s’ouvriront directement dans l’application Portail d’entreprise à l’aide d’une vue dans l’application de Safari. Cette mise à jour sera disponible séparément à partir de la mise à jour de service de janvier.

#### <a name="modernizing-the-company-portal-website---753980--"></a>Modernisation du site web du portail d’entreprise <!--753980-->
À compter de février, le site web du portail d’entreprise prend en charge les applications destinées aux utilisateurs qui n’ont pas d’appareils gérés. Le site web s’aligne sur les autres produits et services Microsoft et utilise un nouveau modèle de couleurs contrastées, des illustrations dynamiques et un « menu hamburger », ![Menu hamburger du site web du portail d’entreprise](/intune-classic/whats-new/whats-new-in-intune-app-ui).

#### <a name="new-documentation-for-app-protection-policies---583398--"></a>Nouvelle documentation pour les stratégies de protection des applications <!--583398-->
Nous avons mis à jour notre documentation pour les administrateurs et les développeurs d'applications qui souhaitent activer les stratégies de protection des applications (appelées stratégies MAM) dans leurs applications iOS et Android à l’aide de l'outil de création de package de restrictions d’application Intune ou du SDK d’application Intune.

Les articles suivants ont été mis à jour :

* [Décider comment préparer les applications pour la gestion des applications mobiles avec Microsoft Intune](/intune-classic/deploy-use/decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune)
* [Préparer des applications iOS pour la gestion des applications mobiles avec l’outil de création de package de restrictions d’application Intune](/intune-classic/deploy-use/prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool)
* [Prise en main du Kit de développement logiciel (SDK) d’applications Microsoft Intune](/intune-classic/develop/intune-app-sdk-get-started)
* [Guide du Kit de développement logiciel (SDK) d’applications Intune pour les développeurs iOS](/intune-classic/develop/intune-app-sdk-ios)

Les articles suivants constituent de nouveaux ajouts à la bibliothèque de documents :

* [Plug-in Cordova du SDK d’application Intune](/intune-classic/develop/intune-app-sdk-cordova)
* [Composant Xamarin du SDK d’application Intune](/intune-classic/develop/intune-app-sdk-xamarin)

#### <a name="progress-bar-when-launching-the-company-portal-on-ios---665978--"></a>Barre de progression lors du lancement du portail d’entreprise sur iOS <!--665978-->
Le portail d’entreprise pour iOS introduit une barre de progression sur l’écran de démarrage pour fournir à l’utilisateur des informations sur les processus de chargement qui se produisent. Il y aura un déploiement échelonné de la barre de progression pour remplacer le compteur. Cela signifie que certains de vos utilisateurs verront la nouvelle barre de progression tandis que d’autres verront encore le compteur.

## <a name="december-2016"></a>Décembre 2016

### <a name="public-preview-of-the-new-intune-admin-experience-on-azure---736542--"></a>Préversion publique de la nouvelle expérience d’administrateur Intune sur Azure <!--736542-->
Début 2017, nous migrerons l’intégralité de notre expérience administrateur vers Azure, permettant ainsi une gestion puissante et intégrée des principaux flux de travail EMS sur une plateforme de services moderne et extensible à l’aide des API Graph. Avant la disponibilité générale de ce portail pour tous les clients Intune, nous sommes heureux d’annoncer que nous commencerons le déploiement d’une préversion de cette nouvelle expérience d’administration ce mois-ci pour certains clients.

L’expérience administrateur dans le portail Azure utilisera la nouvelle fonctionnalité de regroupement et de ciblage précédemment annoncée ; lorsque votre client existant est migré vers la nouvelle expérience de regroupement, vous le serez également afin d’afficher un aperçu de la nouvelle expérience administrateur sur votre client. En attendant, découvrez toutes les nouveautés de Microsoft Intune dans le portail Azure dans notre [nouvelle documentation](/intune/what-is-intune).

__Intégration de la gestion des dépenses de télécommunications dans la préversion publique du portail Azure__ <!--747605--> Nous avons commencé à afficher un aperçu de l’intégration de la gestion des dépenses de télécommunications /intune-classic/troubleshoot/how-to-get-support-for-microsoft-intune).

### <a name="new-capabilities"></a>Nouvelles fonctionnalités

__Authentification multifacteur sur toutes les plateformes__ <!--747590--> Vous pouvez appliquer l’authentification multifacteur (MFA) sur un groupe sélectionné d’utilisateurs lorsqu’ils inscrivent un appareil iOS, Android, Windows 8.1+ ou Windows Phone 8.1+ depuis le portail de gestion Azure en configurant l’authentification MFA sur l’application de l’inscription à Microsoft Intune dans Azure Active Directory.

__Capacité à restreindre l’inscription d’appareil mobile__ <!--747596--> Intune ajoute de nouvelles restrictions d’inscription qui contrôlent les plateformes d’appareils mobiles autorisées à être inscrites. Intune sépare les plateformes d’appareils mobiles comme iOS, MacOS, Android, Windows et Windows Mobile.
* La restriction de l’inscription d’appareils mobiles ne limite pas l’inscription des clients de PC.
* Pour iOS uniquement, il existe une option supplémentaire pour bloquer l’inscription des appareils personnels.

Intune marque tous les nouveaux appareils comme personnels, sauf si l’administrateur prend des mesures pour les marquer comme appareils d’entreprise, comme expliqué dans [cet article](/intune-classic/deploy-use/manage-corporate-owned-devices).

### <a name="notices"></a>Remarques

__Déplacement de l’authentification multifacteur pour les inscriptions vers le portail Azure__ <!--VSO 750545--> Auparavant, les administrateurs accédaient à la console Intune ou à la console Configuration Manager (antérieure à la version d’octobre 2016) pour définir l’authentification multifacteur pour les inscriptions Intune. Grâce à cette fonctionnalité mise à jour, vous pouvez désormais vous connecter au [portail Microsoft Azure](https://manage.windowsazure.com) à l’aide de vos informations d’identification Intune et configurer les paramètres de l’authentification multifacteur via Azure AD. En savoir plus sur ce point [ici](https://aka.ms/mfa_ad).

__Application Portail d’entreprise pour Android désormais disponible en Chine__ <!--VSO 658093--> Nous publions l’application Portail d’entreprise pour Android pour le téléchargement en Chine. En l’absence de Google Play Store en Chine, les appareils Android doivent obtenir les applications dans les places de marché des applications chinoises. L’application Portail d’entreprise pour Android sera disponible en téléchargement dans les boutiques suivantes :
* [Baidu](https://go.microsoft.com/fwlink/?linkid=836946)
* [Huawei](https://go.microsoft.com/fwlink/?linkid=836948)
* [Tencent](https://go.microsoft.com/fwlink/?linkid=836949)
* [Wandoujia](https://go.microsoft.com/fwlink/?linkid=836950)
* [Xiaomi](https://go.microsoft.com/fwlink/?linkid=836947)

L’application Portail d’entreprise pour Android utilise Google Play Services pour communiquer avec le service Microsoft Intune. Étant donné que les services Google Play ne sont pas encore disponibles en Chine, le traitement des tâches suivantes peut prendre jusqu’à 8 heures. 

|Console d’administration Intune| Application Portail d’entreprise Intune pour Android |Site web du portail d’entreprise Intune|   
|---|---|---|
|réinitialisation complète| Supprimer un appareil distant| Supprimer l’appareil (local et distant)|
|réinitialisation sélective| Réinitialiser l’appareil| Réinitialiser un appareil|
|Déploiements d’applications nouvelles ou mises à jour| Installer des applications métier disponibles| Réinitialisation du code secret d’un appareil|
|Verrouillage à distance|||
|Réinitialiser le code secret|||

### <a name="deprecations"></a>Dépréciations

__Fin de la prise en charge de Silverlight par Firefox__ <!--VSO TBA--> Mozilla supprime la prise en charge de Silverlight dans la version 52 du [navigateur Firefox](https://www.mozilla.org/firefox), à compter de mars 2017. Ainsi, vous ne pourrez plus vous connecter à la console Intune existante à l’aide de versions de Firefox ultérieures à la version 51. Nous vous recommandons d’utiliser Internet Explorer 10 ou 11 pour accéder à la console d’administration, ou une [version de Firefox antérieure à la version 52](https://ftp.mozilla.org/pub/firefox/releases/). La transition d’Intune vers le portail Azure lui permettra de prendre en charge plusieurs [navigateurs modernes](/azure/azure-preview-portal-supported-browsers-devices) sans dépendance envers Silverlight.

__Suppression des stratégies de boîte aux lettres mobile Exchange Online__ <!--770687--> À compter du mois décembre, les administrateurs ne seront plus en mesure d’afficher ou de configurer les stratégies de boîte aux lettres mobile Exchange Online (EAS) dans la console Intune. Cette modification s’appliquera à tous les clients Intune entre décembre et janvier. La configuration des stratégies existantes restera inchangée. Pour configurer de nouvelles stratégies, utilisez l’environnement de ligne de commande Exchange Management Shell. Obtenez plus d’informations [ici](https://technet.microsoft.com/library/bb123783%28v=exchg.150%29.aspx).

__Les applications Intune AV Player, Image Viewer et PDF Viewer ne sont plus prises en charge sur Android__ <!--747553--> À partir de mi-décembre 2016, les utilisateurs ne seront plus en mesure d’utiliser les applications Intune AV Player, Image Viewer et PDF Viewer. Ces applications ont été remplacées par l’application Azure Information Protection. En savoir plus sur l’application Azure Information Protection [ici](/information-protection/rms-client/mobile-app-faq).

## <a name="november-2016"></a>Novembre 2016

### <a name="new-capabilities"></a>Nouvelles fonctionnalités

__Nouveau portail d’entreprise Microsoft Intune disponible pour les appareils Windows 10__ Microsoft lance une nouvelle [application Portail d’entreprise Microsoft Intune pour les appareils Windows 10](https://www.microsoft.com/store/apps/9wzdncrfj3pz). Cette application, au nouveau format Windows 10 universel, fournira à l’utilisateur une expérience inédite de l’application et une expérience identique sur tous les appareils Windows 10, PC et mobiles, tout en offrant les mêmes fonctionnalités qu’aujourd’hui.

La nouvelle application permettra également aux utilisateurs de tirer parti de fonctionnalités de plateforme supplémentaires telles que l’authentification unique (SSO) et par certificat sur les appareils Windows 10. Elle sera disponible en tant que mise à niveau du portail d’entreprise Windows 8.1 actuel et du portail d’entreprise Windows Phone 8.1 installés à partir du Windows Store. Pour plus d’informations, consultez [aka.ms/intunecp_universalapp](http://aka.ms/intunecp_universalapp).

> [!IMPORTANT]
> __Mise à jour sur Intune et Android for Work__ Vous pouvez déployer des applications Android for Work avec l’action __Obligatoire__, mais vous pouvez uniquement déployer les applications __disponibles__ si vos groupes Intune ont été migrés vers la nouvelle expérience Azure AD pour les groupes.

__Le SDK d’application Intune pour le plug-in Cordova prend maintenant en charge la gestion des applications mobiles (GAM) sans inscription__ Les développeurs d’applications peuvent maintenant utiliser le plug-in Cordova du SDK d’application Intune pour activer la fonctionnalité GAM sans inscription d’appareils dans leurs applications Cordova pour Android et iOS. Vous trouverez le plug-in Cordova du SDK d’application Intune [ici](https://github.com/msintuneappsdk/cordova-plugin-ms-intune-mam).

__Le composant Xamarin du SDK d’application Intune prend maintenant en charge la gestion des applications mobiles (GAM) sans inscription__ Les développeurs d’applications peuvent maintenant utiliser le composant Xamarin du SDK d’application Intune pour activer la fonctionnalité GAM sans inscription d’appareils dans leurs applications Xamarin pour Android et iOS. Vous pouvez trouver le composant Xamarin du SDK d’application Intune [ici](https://github.com/msintuneappsdk/intune-app-sdk-xamarin).

### <a name="notices"></a>Remarques

__Le certificat de signature Symantec n’a plus besoin du portail d’entreprise Windows Phone 8 signé pour le chargement__ Le chargement du certificat de signature Symantec n’a plus besoin de l’application Portail d’entreprise Windows Phone 8 signée. Le certificat peut être chargé séparément.

###<a name="deprecations"></a>Dépréciations

__Prise en charge du portail d’entreprise Windows Phone 8__ La prise en charge du portail d’entreprise Windows Phone 8 est désormais dépréciée. La prise en charge des plateformes Windows Phone 8 et WinRT a été dépréciée en octobre 2016. La prise en charge du portail d’entreprise Windows 8 a également été dépréciée en octobre 2016.

## <a name="october-2016"></a>Octobre 2016

### <a name="conditional-access-for-mobile-application-management"></a>Accès conditionnel à la gestion des applications mobiles
Vous pourrez restreindre l’accès à Exchange Online en autorisant uniquement l’accès à partir d’applications qui prennent en charge les stratégies Intune de gestion des applications mobiles, comme Outlook. [Cette nouvelle fonctionnalité](/intune-classic/deploy-use/allow-policy-managed-apps-access-to-o365) est complémentaire des stratégies Intune de gestion des applications mobiles (GAM), car vous pouvez bloquer l’accès aux clients de messagerie intégrés ou autres applications qui n’ont pas été configurés avec les stratégies Intune GAM. Cela garantit que vos utilisateurs accèdent aux données de votre organisation avec des applications qui peuvent être protégées à l’aide de la GAM Intune. Vous pouvez bien démarrer avec la gestion des applications mobiles Intune à l’aide du portail Azure. dans la nouvelle section Accès conditionnel du panneau « Paramètres ».

### <a name="conditional-access-for-windows-pcs"></a>Accès conditionnel pour les PC Windows
Vous pouvez maintenant créer des stratégies d’accès conditionnel via la console d’administration Intune pour empêcher les PC Windows d’accéder à [Exchange Online](/intune-classic/deploy-use/restrict-access-to-sharepoint-online-with-microsoft-intune). Vous pouvez également créer des stratégies d’accès conditionnel pour bloquer l’accès à des applications de bureau Office et à des applications universelles.

### <a name="android-for-work-support"></a>Support d’Android for Work

> [!IMPORTANT]

> Alors que vous pouvez déployer des applications Android for Work avec l’action __Obligatoire__, vous pouvez uniquement déployer les applications __disponibles__ si vos groupes Intune ont migré vers la nouvelle expérience Azure AD pour les groupes.

Intune fait maintenant partie du programme Android for Work (AfW). Nous allons déployer la prise en charge des fonctionnalités AfW dès ce mois-ci et pendant plusieurs mois. Notez que le déploiement d’AfW disponible tire parti de la nouvelle expérience de regroupement et de ciblage. Les comptes de service Intune récemment approvisionnés pourront utiliser cette fonctionnalité dès qu’ils auront accès à AfW.

[Lisez l’annonce de Microsoft concernant la prise en charge d’Intune dans Android for Work](https://blogs.technet.microsoft.com/enterprisemobility/2016/09/12/microsoft-intune-support-for-android-for-work/).

Les rubriques Intune suivantes sont nouvelles ou sont mises à jour avec des informations relatives à Android for Work :

Pour les informaticiens :
- [Configurer Android for Work](/intune-classic/deploy-use/set-up-android-for-work)
- [Restreindre l’accès à la messagerie Exchange Online et Exchange Online Dedicated (nouvel environnement) avec Intune](/intune-classic/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune)
- [Restreindre l’accès à la messagerie Exchange localement et Exchange Online Dedicated (environnement hérité) avec Intune](/intune-classic/deploy-use/restrict-access-to-exchange-onpremises-with-microsoft-intune)
- [Paramètres de stratégie de conformité Android for Work](/intune-classic/deploy-use/afw-compliance-policy-settings-in-microsoft-intune)
- [Comment déployer des applications Android for Work](/intune-classic/deploy-use/android-for-work-apps)
- [Configurer des applications Android for Work avec des stratégies de configuration des applications mobiles](/intune-classic/deploy-use/afw-app-configuration-policy)
- [Paramètres de stratégie Android for Work](/intune-classic/deploy-use/android-for-work-policy-settings-in-microsoft-intune)

Pour les utilisateurs finaux :
- [Ce qui se passe quand vous créez un profil professionnel](/intune-user-help/what-happens-when-you-create-a-work-profile-android)
- [Créer un profil professionnel et inscrire votre appareil dans Intune](/intune-user-help/create-a-work-profile-and-enroll-your-device-in-intune-android)

### <a name="lookout-integration-to-protect-ios-devices"></a>Intégration de la protection Lookout pour les appareils Android
En octobre, Microsoft intègre la solution de Lockout qui permet de protéger les appareils mobiles Android en détectant les programmes malveillants, les applications à risque et d’autres menaces. La solution de Lookout vous aide à déterminer le niveau de menace et à le configurer. Vous pouvez créer une règle de stratégie de conformité dans Intune pour déterminer la conformité de l’appareil d’après l’évaluation du risque réalisée par Lookout. À l’aide de stratégies d’accès conditionnel, vous pouvez autoriser ou bloquer l’accès aux ressources d’entreprise en fonction de l’état de conformité de l’appareil.

Les utilisateurs d’appareils non conformes seront invités à inscrire leurs appareils. Ils devront également installer l’application Lookout for Work sur leurs appareils, l’activer et corriger les menaces signalées par celles-ci pour accéder aux données d’entreprise. Découvrez comment [configurer et déployer l’application Lookout for Work](/intune-classic/deploy-use/configure-and-deploy-lookout-for-work-apps).
<!--TFS 1319493-->

### <a name="intune-app-wrapping-tool-for-android"></a>Outil de création de package de restrictions d’application Intune pour Android
Vous pouvez configurer vos applications pour utiliser des stratégies de gestion des applications mobiles (GAM) à l’aide de l’outil de création de package de restrictions d’application Intune. La prise en charge des stratégies GAM d’Intune sans nécessiter l’inscription d’appareils est désormais disponible.

### <a name="manage-printing-from-apps-managed-using-mam-policies"></a>Gestion de l’impression à partir d’applications gérées à l’aide de stratégies MAM
Vous pouvez maintenant empêcher l’impression de données d’entreprise à partir d’applications dotées de stratégies MAM. Ce paramètre est disponible sur les appareils du [portail Azure](/intune-classic/deploy-use/android-mam-policy-settings).
<!--TFS 1014328-->

### <a name="support-for-fingerprints-on-android-devices"></a>Prise en charge des empreintes sur les appareils Android
Gestion des applications mobiles Android /intune-classic/deploy-use/android-mam-policy-settings).

### <a name="notices"></a>Remarques

__Compatibilité entre Android Samsung KNOX et Intune__ Certains modèles de téléphone Samsung Galaxy Ace ne peuvent pas être gérés par Intune en tant qu’appareils Samsung KNOX. Lorsque vous inscrivez ces appareils à Intune, ils sont gérés comme des appareils Android standard.

Les numéros de modèle concernés sont les suivants :

* SM-G313HU
* SM-G313HY
* SM-G313M
* SM-G313MY
* SM-G313U

Aucune autre action n’est requise de votre part ou de celle de vos utilisateurs. Pour plus d’informations, consultez le site web [Samsung KNOX](https://www.samsungknox.com).

__L’application Portail d’entreprise pour Windows 8 est dépréciée ; la prise en charge des plateformes Windows Phone 8 et Windows RT est dépréciée__ Depuis octobre 2016, la prise en charge du portail d’entreprise Windows 8 par Microsoft Intune est dépréciée. Microsoft Intune ne prendra également plus en charge les plateformes Windows Phone 8 et Windows RT. Ainsi, vous ne pourrez plus inscrire ni mettre à jour des appareils Windows Phone 8 ou Windows RT.

Néanmoins, vous pourrez continuer à gérer les appareils Windows Phone 8, Windows RT et Windows 8 déjà inscrits. Mettez à jour les appareils Windows Phone 8 et Windows 8 vers Windows Phone 8.1 et Windows 8.1, et utilisez les applications Portail d’entreprise Windows 8.1 et Windows Phone 8.1 correspondantes pour continuer à distribuer des applications sur ces appareils sans interruption.

Dès novembre 2016, la prise en charge du portail d’entreprise Windows Phone 8 ne sera plus assurée.
<!--TFS 1255391-->

### <a name="whats-coming"></a>Nouveautés à venir

__Nouveau portail d’entreprise Microsoft Intune disponible pour les appareils Windows 10__ Microsoft lance un nouveau portail d’entreprise Microsoft Intune pour les appareils Windows 10. Cette application, au nouveau format Windows 10 universel, fournira à l’utilisateur une expérience inédite de l’application et une expérience identique sur tous les appareils Windows 10, PC et mobiles, tout en offrant les mêmes fonctionnalités qu’aujourd’hui.

La nouvelle application permettra également aux utilisateurs de tirer parti de fonctionnalités de plateforme supplémentaires telles que l’authentification unique (SSO) et par certificat sur les appareils Windows 10. Elle sera disponible en tant que mise à niveau du portail d’entreprise Windows 8.1 actuel et du portail d’entreprise Windows Phone 8.1 installés à partir du Windows Store. Pour plus d’informations, consultez [aka.ms/intunecp_universalapp](http://aka.ms/intunecp_universalapp).
<!--TFS 1016502-->

## <a name="september-2016"></a>Septembre 2016
### <a name="new-features-announcements-and-information"></a>Nouvelles fonctionnalités, annonces et informations
* [Accès conditionnel Windows](#windows-conditional-access)
* [Prise en charge d’iOS 10](#ios-10-support)
* [L’outil de création de package de restrictions d’application prend en charge la gestion des applications mobiles (GAM) sans inscription d’appareils pour Android et iOS](#app-wrapping-tool-supports-mam-without-device-enrollment-for-android-and-ios)
* [Début de la transition des groupes Intune vers les groupes Azure Active Directory en septembre](#intune-groups-begin-transitioning-to-azure-active-directory-in-september)
* [Intégration de la protection Lookout pour les appareils Android](#lookout-integration-to-protect-android-devices)
* [Mises à jour du portail d’entreprise pour Android, iOS et Windows](#company-portal-updates)
* [Glossaire Intune](#intune-glossary)
* [Nouveautés à venir](#whats-coming)

### <a name="windows-conditional-access"></a>Accès conditionnel Windows
Vous pouvez maintenant créer des stratégies d’accès conditionnel via la console d’administration Intune pour bloquer l’accès des PC Windows à Exchange Online et à SharePoint Online. Vous pouvez également créer des stratégies d’accès conditionnel pour bloquer l’accès à des applications de bureau Office et à des applications universelles.

### <a name="ios-10-support"></a>Prise en charge d’iOS 10
Les scénarios existants pour la gestion Intune MDM et GAM sont compatibles avec iOS 10. Pour obtenir des conseils, consultez le [blog de l’équipe de support technique Intune](https://blogs.technet.microsoft.com/intunesupport/2016/09/13/support-tip-intune-support-for-ios-10/).

### <a name="app-wrapping-tool-supports-mam-without-device-enrollment-for-android-and-ios"></a>L’outil de création de package de restrictions d’application prend en charge la gestion des applications mobiles (GAM) sans inscription d’appareils pour Android et iOS
Cet outil de ligne de commande permet d’activer la fonctionnalité GAM d’Intune dans les applications métier pour iOS et Android. C’est la façon la plus simple d’incorporer le SDK Intune MAM dans votre application, pour que celle-ci applique les stratégies de gestion des appareils mobiles déployées via Intune. Avec les stratégies de gestion des appareils mobiles, vous pouvez :

1. Chiffrer les données de l’application.
2. Exiger que l’utilisateur entre un code confidentiel au démarrage de l’application.
3. Autoriser l’application à transférer des données uniquement vers d’autres applications gérées.
4. Interdire à l’application de sauvegarder des données sur Android, iTunes et iCloud.
5. Autoriser uniquement les opérations couper, copier et coller vers et depuis d’autres applications gérées.

La préversion publique du dernier outil de création de package de restrictions d’application Intune prend désormais en charge la gestion des applications mobiles (GAM) sans inscription des appareils dans des applications métier internes pour iOS et Android. Cela signifie que vos utilisateurs finaux n’ont pas besoin d’inscrire leurs appareils dans Intune pour utiliser des applications métier avec la fonctionnalité GAM.

Toute personne peut tester la préversion publique du logiciel et lire la documentation d’aide, disponible dans msintuneappsdk sur GitHub :

<p style="margin-left: 40px">http://www.github.com/msintuneappsdk/intune-app-wrapper-ios-preview

<p style="margin-left: 40px">http://www.github.com/msintuneappsdk/intune-app-wrapper-android-preview

Avant d’installer et d’utiliser la préversion de l’outil de création de package de restrictions d’application Microsoft Intune pour Android et iOS, effectuez les opérations suivantes :

* Lisez les termes du contrat de licence Microsoft applicables à la préversion de l’outil de création de package de restrictions d’application Microsoft Intune pour Android et iOS.
* Imprimez et conservez une copie des termes du contrat de licence pour vos archives. En téléchargeant et en utilisant la préversion de l’outil de création de package de restrictions d’application Microsoft Intune pour Android, vous reconnaissez accepter ces termes du contrat de licence. Si vous ne les acceptez pas, n'utilisez pas le logiciel.
<!---TFS 1235607--->

### <a name="intune-groups-begin-transitioning-to-azure-active-directory-in-september"></a>Début de la transition des groupes Intune vers les groupes Azure Active Directory en septembre
Certains nouveaux comptes Intune utiliseront les groupes de sécurité Active Directory Azure au lieu des groupes d’utilisateurs Intune. Vous serez averti que vous utilisez des groupes de sécurité par l’ajout d’un lien vers le Portail de gestion Azure dans la page Groupes du Portail Intune.

### <a name="lookout-integration-to-protect-android-devices"></a>Intégration de la protection Lookout pour les appareils Android
Microsoft intègre la solution de protection contre les menaces mobiles de Lookout, qui permet de protéger les appareils mobiles Android en détectant les programmes malveillants, les applications à risque et autres menaces présents sur les appareils. La solution de Lookout vous aide à déterminer le niveau de menace et à le configurer. Vous pouvez créer une règle de stratégie de conformité dans Intune pour déterminer la conformité de l’appareil d’après l’évaluation du risque réalisée par Lookout. À l’aide de stratégies d’accès conditionnel, vous pouvez autoriser ou bloquer l’accès aux ressources d’entreprise en fonction de l’état de conformité de l’appareil.

Les utilisateurs d’appareils non conformes seront invités à inscrire leurs appareils. Ils devront également installer l’application Lookout for Work sur les appareils Android, activer l’application et corriger les menaces signalées dans l’application Lookout for Work pour pouvoir accéder aux ressources. Pour plus d’informations, consultez [Restrict access based on device, network, and application risk](/intune-classic/deploy-use/device-threat-protection) (Restreindre l’accès en fonction du risque évalué pour l’appareil, le réseau et l’application).


### <a name="company-portal-updates"></a>Mises à jour du Portail d’entreprise

__Android__

<p style="margin-left: 40px">**Ajout de « Notifications » dans le portail d’entreprise pour Android**<br/>
<p style="margin-left: 40px">Une nouvelle icône Notifications a été ajoutée sur la page d’accueil du portail d’entreprise pour Android. Appuyez sur cette icône pour accéder à la page Notifications, ce qui affiche à vos utilisateurs finaux tous les éléments qui nécessitent votre attention dans l’application Portail d’entreprise, comme la non-conformité de l’appareil, la mise à jour de l’inscription et l’activation de l’inscription. L’application Portail d’entreprise iOS bénéficie déjà de cette expérience de notifications. Grâce à cette nouvelle page Notifications, la page Configuration de l’accès à l’entreprise ne s’affichera plus à l’utilisateur chaque fois qu’il lancera ou reprendra le portail d’entreprise tant que l’appareil est déjà inscrit. Si vous créez votre propre aide pour les utilisateurs finaux, vous pouvez mettre à jour votre documentation pour refléter cette modification. Vous trouverez des captures d’écran mises à jour [ici](https://aka.ms/androidcpupdate).  

__iOS__
<p style="margin-left: 40px">**Modifications apportées à la prise en charge de l’application Portail d’entreprise iOS**<br/>
<p style="margin-left: 40px">Tous les utilisateurs de l’application Portail d’entreprise Microsoft Intune pour iOS sont maintenant tenus d’utiliser sa version la plus récente. Les nouveaux utilisateurs peuvent uniquement télécharger la dernière version, et les utilisateurs actuels doivent effectuer une mise à jour vers cette version. La nouvelle version nécessite iOS 8.0 ou version ultérieure. Les appareils qui exécutent des versions antérieures d’iOS ne pourront pas accéder au Portail d’entreprise ni être inscrits si les utilisateurs ne mettent pas à jour ces appareils vers iOS 8.0 ou une version ultérieure, et ne mettent pas à jour l’application Portail d’entreprise vers la nouvelle version. Les appareils inscrits qui exécutent les versions antérieures à iOS 8.0 continueront d’être gérés et répertoriés dans la Console d’administration Intune.
<!---TFS 1283165--->

<p style="margin-left: 40px">**Améliorations apportées à l’accès des utilisateurs finaux iOS à leurs applications**<br/>
<p style="margin-left: 40px">Les modifications suivantes ont été apportées aux vignettes d’applications dans l’application Portail d’entreprise pour iOS. Ces vignettes dirigent les utilisateurs vers différentes vues dans un emplacement unique, à savoir le site web du Portail d’entreprise, pour toutes leurs applications. Les restrictions d’Apple n’autorisent pas l’affichage des applications métier et gérées de l’App Store dans l’application Portail d’entreprise, ce qui oblige les utilisateurs à consulter plusieurs vues pour trouver leurs différentes applications.

<p style="margin-left: 40px">La vignette **Applications d’entreprise** pointait auparavant vers une liste de toutes les applications dans l’onglet TOUT du site web du Portail d’entreprise. Elle a toujours le même comportement, mais son nom a été remplacé par **Toutes les applications**.

<p style="margin-left: 40px">La vignette **Autres applications** pointait auparavant vers une vue, dans l’application Portail d’entreprise, qui répertoriait toutes les applications dont l’affichage dans le Portail d’entreprise était autorisé par Apple. Cette vignette s’appelle maintenant **Applications proposées**. Quand l’utilisateur appuie dessus, il accède à l’onglet SÉLECTION du site web du Portail d’entreprise.

<p style="margin-left: 40px">La vignette **Catégories** pointait auparavant vers une vue, dans l’application Portail d’entreprise, qui répertoriait toutes les catégories d’applications. Son nom n’a pas changé, mais la vignette pointe maintenant vers l’onglet CATÉGORIES du site web du Portail d’entreprise. Vous trouverez des captures d’écran mises à jour [ici](https://gallery.technet.microsoft.com/Improvements-in-how-iOS-d1104186).
  <!---TFS 1317133--->

<p style="margin-left: 40px">**Invitation à l’installation de l’application Managed Browser iOS si un professionnel de l’informatique définit cette obligation pour une application**<br/>
<p style="margin-left: 40px">Si vous avez configuré un clip web pour qu’il s’ouvre uniquement dans le navigateur géré, et que ce navigateur n’est pas installé sur l’appareil, l’application Portail d’entreprise sur l’appareil invitera l’utilisateur à installer le navigateur géré pour permettre l’ouverture du clip web.
  <!---TFS 1228570--->

__Windows__
<p style="margin-left: 40px">**Bouton Commentaires ajouté à l’application Portail d’entreprise Windows Phone 8.1**<br/>
<p style="margin-left: 40px">L’application Portail d’entreprise Windows Phone 8.1 permet aux utilisateurs finaux d’envoyer des commentaires concernant l’application à l’aide d’un nouveau bouton « Envoyer des commentaires ». Pour trouver ce bouton, les utilisateurs appuient sur le menu « points de suspension » situé en bas à droite de l’écran de l’application Portail d’entreprise, puis sélectionnent **Envoyer des commentaires**. Les commentaires, après avoir été regroupés et rendus anonymes, sont utilisés par Microsoft pour améliorer l’expérience utilisateur dans l’application Portail d’entreprise.
<!---TFS 1317806--->

### <a name="intune-glossarybr"></a>Glossaire Intune</br>
Nous avons ajouté une nouvelle rubrique [Glossaire](/intune-classic/understand-explore/intune-glossary) à la bibliothèque pour vous aider à comprendre certains des termes utilisés dans le produit Intune.

## <a name="august-2016"></a>Août 2016
### <a name="app-management"></a>Gestion d'applications

__Applications masquées et affichées pour iOS 9.3__ Pour les appareils exécutant iOS 9.3 ou une version ultérieure, vous pouvez utiliser la liste des applications affichées et masquées dans la stratégie de configuration générale d’iOS pour :
- Spécifier une liste d’applications à masquer aux utilisateurs. Les utilisateurs ne peuvent pas afficher ou lancer ces applications.
- Spécifier une liste d’applications que les utilisateurs peuvent afficher et lancer. Aucune autre application ne peut être affichée ou lancée.

Les applications que vous pouvez spécifier incluent celles que vous avez déployées, ainsi que les applications iOS intégrées telles que Messages et Notes. Pour plus d’informations, consultez [Paramètres de la stratégie iOS dans Microsoft Intune](/intune-classic/deploy-use/ios-policy-settings-in-microsoft-intune).
<!---TFS 1279009 checked--->
__Stratégie des applications autorisées et bloquées pour les appareils dotés de Samsung KNOX__ Vous pouvez désormais configurer une stratégie personnalisée pour les appareils dotés de Samsung KNOX, qui vous permet de créer l’un des éléments suivants :
- Une liste d’applications qui sont bloquées sur l’appareil. Même si elle est installée, une application définie dans la liste bloquée ne peut pas être activée sur l’appareil.
- Une liste d’applications que les utilisateurs de l’appareil sont autorisés à installer à partir de Google Play Store. Aucune autre application ne peut être installée à partir du Store.

Ces paramètres ne peuvent être utilisés que par des appareils qui exécutent Samsung KNOX.
Pour plus d’informations, consultez [Utiliser des stratégies personnalisées pour autoriser et bloquer des applications pour les appareils Samsung KNOX](/intune-classic/deploy-use/custom-policy-to-allow-and-block-samsung-knox-apps).
<!---TFS 1311629 checked --->

__Nouvelles applications compatibles avec les stratégies de gestion des applications mobiles (GAM)__ Application Yammer pour [iOS](/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune), que l’appareil soit inscrit ou pas.

Pour obtenir la liste complète des applications MAM compatibles, consultez le site des [partenaires des applications Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune-partners).
<!--- TFS 1252335 & 1252336 checked--->

__Applications de visionneuse Intune__ Avec la publication de la nouvelle application de partage RMS, nous allons supprimer les applications de visionneuse Intune suivantes à compter du mois d’août 2016 :
- Intune AV Viewer
- Intune PDF Viewer
- Intune Image Viewer pour Android depuis Google Play

Plutôt que d’utiliser l’application de visionneuse Intune, nous vous recommandons d’utiliser la nouvelle [application Rights Management /intune-classic/deploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune#viewing-media-files-with-the-rights-management-sharing-app), qui vous permet de déployer une application au lieu de trois applications différentes pour afficher les fichiers de l’entreprise sur les appareils Android en toute sécurité. Quand l’application de visionneuse Intune ne sera plus prise en charge, elle sera supprimée du Google Store et ne sera plus disponible pour une utilisation ultérieure.

### <a name="device-management"></a>Gestion des appareils
__Prise en charge d’Android 7.0__ Intune assure la prise en charge dès le premier jour du système d’exploitation Android 7.0 pour les appareils mobiles, bientôt disponible.
<!---TFS 1262053--->
### <a name="google-removal-of-remote-passcode-reset-capability-on-android-70-devices"></a>Suppression par Google de la fonctionnalité de réinitialisation à distance du code secret sur les appareils Android 7.0
Google supprime la fonctionnalité permettant aux utilisateurs finaux et aux administrateurs informatiques de réinitialiser à distance le code secret de leurs appareils Android 7.0. Auparavant, les administrateurs informatiques pouvaient réinitialiser à distance le code secret d’un utilisateur, et les utilisateurs finaux pouvaient réinitialiser leur code secret depuis le site web du Portail d’entreprise.



### <a name="company-portal-updates"></a>Mises à jour du Portail d’entreprise
__Site web Portail d’entreprise__
- **Lien des commentaires sur le Portail d’entreprise à l’attention de Microsoft** <br/>
Le site web du portail d’entreprise permet aux utilisateurs finaux d’appuyer sur un nouveau lien « Commentaires », situé en bas de la page, pour envoyer des commentaires à Microsoft concernant leur expérience avec le site. Les commentaires regroupés sont anonymes et permettent à Microsoft d’améliorer le site web du Portail d’entreprise, afin d’optimiser cette expérience.
<!--- TFS 1313657 checked--->

__iOS__
- **Mise à jour de la version minimale de Managed Browser pour iOS 8.0**<br/>
L’application Microsoft Intune Managed Browser pour iOS a été mise à jour pour prendre en charge les appareils exécutant iOS 8.0 ou version ultérieure. Même si les appareils iOS 7.1 peuvent toujours utiliser l’application Managed Browser existante, nous vous recommandons d’inciter vos utilisateurs à procéder à la mise à jour pour iOS 8.0 ou version ultérieure. Ils pourront ainsi accéder aux nouvelles fonctionnalités de Managed Browser et en tirer pleinement parti.  
<!---TFS 1313253 checked--->

### <a name="whats-coming"></a>Nouveautés à venir
__Début de la transition des groupes Intune vers les groupes Azure Active Directory dès septembre 2016__ Intune crée une expérience de gestion de groupe qui utilise les groupes de sécurité Azure Active Directory (AAD) en tant que groupes d’utilisateurs et d’appareils dans Intune. Ces groupes seront utilisés pour la gestion, le déploiement de stratégies et de profils de tous les groupes **lorsque nous introduirons le nouveau portail d’administration Intune basé sur Azure**.

Grâce à cette nouvelle expérience, vous n’aurez plus besoin de dupliquer des groupes entre des services, **ce qui vous permet d’accéder à certaines fonctionnalités de groupes Azure Active Directory Premium (AADP)**, tout en bénéficiant d’une extensibilité lors de l’utilisation de PowerShell et Graph. La gestion des groupes sera également unifiée lors de la gestion de la mobilité d’entreprise.

Pour activer la transition vers les groupes de sécurité, nous allons devoir modifier la **console d’administration actuelle**. **Ces modifications et l’utilisation des groupes de sécurité Azure AD seront consignées dans la documentation d’Intune**.

Les clients qui ne connaissent pas Intune constateront **certaines modifications du groupe de sécurité avant les clients actuels**.

Outre les modifications dans la gestion de groupe, **les fonctionnalités suivantes deviendront obsolètes** :
- Exclusion de membres ou de groupes lors de la création d’un groupe
- Groupes **Utilisateurs non groupés** et **Appareils non groupés**
- **Gérer des groupes** dans le rôle d’administrateur de service
- Alertes personnalisées basées sur le groupe pour les règles de notification
- Glissement des groupes dans les rapports
<!--- TFS 1295329--->

__Ajout de « Notifications » sur le portail d’entreprise pour Android__ En septembre, nous publierons une mise à jour du Portail d’entreprise pour Android, qui présentera la nouvelle icône **Notifications** de la page d’accueil. En appuyant sur cette icône, vous pourrez accéder à la page **Notifications** qui indiquera à votre utilisateur final tous les éléments qui nécessitent son attention particulière dans l’application de portail d’entreprise, tels que la non-conformité d’un appareil, ainsi que les mises à jour ou les activations d’inscriptions. Si vous utilisez également l’application de portail d’entreprise iOS, vous pouvez déjà utiliser ces notifications. Une fois la page **Notifications** en place, si votre appareil est déjà inscrit, vous ne verrez plus la page **Configuration de l’accès à l’entreprise** à chaque fois que vous accédez au portail d’entreprise pour Android ou que vous y revenez. Nous savons que beaucoup d’entre vous ont créé des conseils pour l’utilisateur final et que vous appréciez de recevoir des notifications avancées lorsque vos conseils/captures d’écrans doivent être mis à jour. Mettez à jour votre documentation pour refléter les modifications de l’expérience à venir. Vous trouverez des captures d’écran mises à jour ici : https://aka.ms/androidcpupdate.  

### <a name="service-deprecation"></a>Désapprobation du service

- **Modifications apportées à la prise en charge de l’application Portail d’entreprise iOS**<br/>
En septembre, tous les utilisateurs de l’application Portail d’entreprise Microsoft Intune pour iOS devront utiliser la dernière version. Les nouveaux utilisateurs pourront uniquement télécharger la dernière version et les utilisateurs actuels devront effectuer une mise à jour vers cette version. La dernière version nécessite iOS 8.0 ou version ultérieure. Les appareils qui exécutent d’anciennes versions d’iOS ne pourront pas utiliser le portail d’entreprise ni être inscrits tant qu’ils n’auront pas été mis à jour vers iOS 8.0 ou version ultérieure, et que l’application Portail d’entreprise n’aura pas été mise à jour vers la dernière version. Les appareils inscrits qui exécutent les versions antérieures à iOS 8.0 continueront d’être gérés et répertoriés dans la Console d’administration Intune.  

- **Mise à jour de la version minimale de Managed Browser pour iOS 8.0**<br/>
En août, Intune publiera une mise à jour de l’application Microsoft Intune Managed Browser pour iOS qui prendra uniquement en charge les appareils exécutant iOS version 8.0 ou ultérieure. Même si les appareils iOS 7.1 pourront toujours utiliser l’application Managed Browser, nous vous recommandons d’inciter vos utilisateurs à procéder à la mise à jour pour iOS 8.0 ou ultérieure. Ils pourront ainsi accéder aux nouvelles fonctionnalités de Managed Browser et en tirer pleinement parti.  
<!---TFS 1313253--->

- **Les applications du portail d’entreprise pour Windows 8 et Windows Phone 8 sont dépréciées depuis septembre 2016** <br/>
À compter de septembre 2016, les utilisateurs de l’application Portail d’entreprise Microsoft Intune pour plateformes Windows Phone 8 et Windows 8 ne pourront plus bénéficier du support Microsoft Intune. Mettez à jour vos appareils vers Windows 8.1 et Windows Phone 8.1, et utilisez les applications Portail d’entreprise Windows 8.1 et Windows Phone 8.1 correspondantes pour continuer la distribution des applications sur ces appareils.
<!---TFS 1255391--->
