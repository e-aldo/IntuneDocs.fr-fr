---
title: "Nouveautés | Microsoft Docs"
description: "Découvrir les nouveautés de la version de Microsoft Intune de ce mois-ci et des versions précédentes"
keywords: 
author: mtillman
ms.author: mtillman
manager: angrobe
ms.date: 03/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
ms.reviewer: priyar
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: c473a1f05b0a7b0ce5205598b2b9a9b86bfe6c1d
ms.openlocfilehash: bddd8c0dc74835f74a71af1d900d43d84aab894c
ms.lasthandoff: 03/29/2017


---
# <a name="whats-new-in-microsoft-intune---march-2017"></a>Nouveautés de Microsoft Intune - Mars 2017
Découvrez les nouveautés de la version de Microsoft Intune de ce mois-ci. Vous pouvez également découvrir les modifications à venir que vous devez planifier, ainsi que des informations sur les versions précédentes.

> [!Note]
> Toutes ces fonctionnalités seront finalement prises en charge pour les déploiements de clients hybrides (Configuration Manager avec Intune). Pour plus d’informations sur les nouvelles fonctionnalités hybrides, consultez notre page [Nouveautés hybrides](https://docs.microsoft.com/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

## <a name="new-capabilities"></a>Nouvelles fonctionnalités

### <a name="support-for-skycure"></a>Prise en charge de Skycure

Vous pouvez désormais contrôler l’accès des appareils mobiles aux ressources d’entreprise, à l’aide d’un accès conditionnel basé sur une évaluation des risques effectuée par Skycure, une solution de protection contre les menaces mobiles qui s’intègre à Microsoft Intune. Le risque est évalué en fonction des données de télémétrie recueillies par les appareils exécutant Skycure, notamment :

- Défense physique
- Défense du réseau
- Défense des applications
- Défense contre les vulnérabilités

Vous pouvez configurer des stratégies d’accès conditionnel EMS basées sur l’évaluation des risques de Skycure, activée par le biais des stratégies de conformité Intune. Vous pouvez utiliser ces stratégies pour autoriser ou bloquer l’accès des appareils non conformes aux ressources d’entreprise, en fonction des menaces détectées. Pour en savoir plus, voir [Connecteur Skycure Mobile Threat Defense](/intune/deploy-use/skycure-mobile-threat-defense-connector).

### <a name="new-user-experience-for-the-company-portal-app-for-android---621622--"></a>Nouvelle expérience utilisateur dans l’application Portail d’entreprise pour Android <!--621622-->

L’application Portail d’entreprise pour Android a mis à jour son interface utilisateur afin d’en moderniser l’aspect et d’améliorer l’expérience utilisateur. Les mises à jour notables sont les suivantes :

- Couleurs : les en-têtes de l’onglet Portail d’entreprise sont colorés selon une personnalisation définie par le service informatique.
- Applications : dans l’onglet **Applications**, les boutons **Applications proposées** et **Toutes les applications** sont mis à jour.
- Recherche : dans l’onglet **Applications**, le bouton **Rechercher** est un bouton d’action flottant.
- Navigation dans les applications : la vue **Toutes les applications** affiche une vue comprenant les onglets **Applications proposées**, **Toutes les applications** et **Catégories** pour faciliter la navigation.
- Support : les onglets **Mes appareils** et **Contacter le service informatique** sont mis à jour pour améliorer la lisibilité.

Pour plus d’informations sur ces modifications, consultez [Mises à jour de l’interface utilisateur pour les applications utilisateur final Intune](whats-new-in-intune-app-ui.md).

### <a name="non-managed-devices-can-access-assigned-apps---664691--"></a>Les appareils non gérés peuvent accéder aux applications attribuées <!--664691-->

Dans le cadre des modifications conceptuelles du site web du portail d’entreprise, les utilisateurs iOS et Android peuvent installer les applications attribuées indiquées comme « disponibles sans inscription » sur leurs appareils non gérés. À l’aide de leurs informations d’identification Intune, les utilisateurs peuvent se connecter au site web du portail d’entreprise et afficher la liste des applications qui leur sont attribuées. Les packages des applications « disponibles sans inscription » peuvent être téléchargés sur le site web du portail d’entreprise. Les applications dont l’installation nécessite une inscription ne sont pas affectées par cette modification, car les utilisateurs sont invités à inscrire leur appareil s’ils souhaitent installer ces applications.

### <a name="signing-script-for-windows-10-company-portal---941642--"></a>Script de signature pour le portail d’entreprise Windows 10 <!--941642-->

Si vous avez besoin de télécharger de l’application Portail d’entreprise Windows 10 et d’en charger une version test, vous pouvez à présent utiliser un script qui simplifie le processus de signature d’application pour votre organisation.   Pour télécharger le script et les instructions d’utilisation, consultez [Microsoft Intune Signing Script for Windows 10 Company Portal](https://aka.ms/win10cpscript) (Script de signature Microsoft Intune pour le portail d’entreprise Windows 10) sur la galerie TechNet. Pour plus d’informations sur cette annonce, consultez [Mise à jour de votre application de portail d’entreprise Windows 10](https://blogs.technet.microsoft.com/intunesupport/2017/03/13/updating-your-windows-10-company-portal-app/) sur le blog de l’équipe de support technique Intune.


## <a name="notices"></a>Remarques

### <a name="support-for-ios-103"></a>Prise en charge d’iOS 10.3

Le déploiement de la version 10.3 d’iOS a débuté le 27 mars 2017 pour les utilisateurs d’iOS. Tous les scénarios de GPM et GAM Intune existants sont compatibles avec la dernière version du système d’exploitation Apple. Toutes les fonctionnalités Intune existantes actuellement disponibles pour la gestion des appareils iOS devraient continuer à fonctionner une fois les appareils des utilisateurs migrés vers iOS 10.3.

Actuellement, nous n’avons aucun problème connu à signaler. Si vous rencontrez des problèmes liés à iOS 10.3, n’hésitez pas à contacter [l’équipe de support Intune](/intune/troubleshoot/contact-assisted-phone-support-for-microsoft-intune).

### <a name="improved-support-for-android-users-based-in-china---720444--"></a>Amélioration du support pour les utilisateurs Android basés en Chine <!--720444-->

En l’absence de Google Play Store en Chine, les appareils Android doivent obtenir les applications sur les places de marché chinoises. L’application Portail d’entreprise prendra en charge ce flux de travail en redirigeant les utilisateurs Android en Chine vers le téléchargement des applications Portail d’entreprise et Outlook à partir des boutiques d’applications locales. Cette approche améliorera l’expérience utilisateur lorsque les stratégies d’accès conditionnel seront activées, à la fois pour la gestion des appareils mobiles et pour la gestion des applications mobiles. Les applications Portail d’entreprise et Outlook pour Android sont disponibles dans les boutiques d’applications chinoises suivantes :

- [Baidu](https://go.microsoft.com/fwlink/?linkid=836946)
- [Xiaomi](https://go.microsoft.com/fwlink/?linkid=836947)
- [Tencent](https://go.microsoft.com/fwlink/?linkid=836949)
- [Huawei](https://go.microsoft.com/fwlink/?linkid=836948)
- [Wandoujia](https://go.microsoft.com/fwlink/?linkid=836950)

### <a name="best-practice-make-sure-your-company-portal-apps-are-up-to-date---879465--"></a>Meilleures pratiques : vérifiez que vos applications Portail d’entreprise sont à jour <!--879465-->

En décembre 2016, nous avons publié une mise à jour qui a activé l’authentification multifacteur (MFA) sur un groupe d’utilisateurs lorsque ceux-ci inscrivent un appareil iOS, Android, Windows 8.1+ ou Windows Phone 8.1+. Cette fonctionnalité ne peut pas fonctionner sans certaines versions de ligne de base de l’application Portail d’entreprise pour Android (v5.0.3419.0 +) et iOS (v2.1.17+).

Microsoft améliore en permanence Intune en ajoutant de nouvelles fonctions aussi bien à la console qu’aux applications Portail d’entreprise sur toutes les plateformes prises en charge. Par conséquent, Microsoft publie uniquement des correctifs pour les problèmes que nous trouvons dans la version actuelle de l’application Portail d’entreprise. Il est donc recommandé d’utiliser les dernières versions des applications Portail d’entreprise pour bénéficier d’une expérience utilisateur optimale.

>[!Tip]
> Demandez à vos utilisateurs de définir leurs appareils de façon à ce qu’ils mettent à jour automatiquement les applications à partir de l’App Store approprié. Si vous avez partagé l’application Portail d’entreprise Android sur un partage réseau, vous pouvez télécharger la dernière version à partir du [Centre de téléchargement Microsoft](https://www.microsoft.com/download/details.aspx?id=49140).

### <a name="microsoft-teams-is-now-enabled-for-mam-on-ios-and-android"></a>Microsoft Teams est maintenant activé pour MAM sur iOS et Android

Microsoft a annoncé la disponibilité générale de Microsoft Teams. Les applications Microsoft Teams mises à jour pour iOS et Android sont maintenant activées avec les fonctionnalités de gestion des applications mobiles Intune (MAM). Vous donnez ainsi la possibilité à vos équipes de travailler librement sur les appareils, tout en veillant à ce que les conversations et les données d’entreprise soient protégées en permanence. Pour plus d’informations, consultez l’[annonce Microsoft Teams](https://blogs.technet.microsoft.com/enterprisemobility/2017/03/14/microsoft-teams-is-now-generally-available-and-mam-enabled-on-ios-and-android/) sur le blog Enterprise Mobility and Security.


## <a name="whats-new-in-the-public-preview-of-the-intune-admin-experience-on-azure---736542--"></a>Nouveautés de la préversion publique de l’expérience d’administrateur Intune sur Azure <!--736542-->

Début 2017, nous migrerons l’intégralité de notre expérience administrateur vers Azure, permettant ainsi une gestion puissante et intégrée des principaux flux de travail EMS sur une plateforme de services moderne et extensible à l’aide des API Graph.

Les nouveaux locataires de test pourront accéder à la préversion publique de la nouvelle expérience administrateur dans le portail Azure ce mois-ci. Dans un état d’aperçu, les fonctionnalités et la parité avec la console Intune existante seront remises en mode itératif.

L’expérience administrateur dans le portail Azure utilisera la nouvelle fonctionnalité de regroupement et de ciblage précédemment annoncée ; lorsque votre client existant est migré vers la nouvelle expérience de regroupement, vous le serez également afin d’afficher un aperçu de la nouvelle expérience administrateur sur votre client. En attendant, si vous souhaitez tester ou examiner toute nouvelle fonctionnalité avant la migration du client, inscrivez-vous à un nouveau compte d’évaluation Intune ou consultez la [nouvelle documentation](/intune-azure/introduction/whats-new).

> [!Note]
> En ce qui concerne la préversion du portail Azure, nous déployons actuellement les mises à jour pour ce mois. Toutefois, il se peut que les modifications ne soient pas disponibles immédiatement selon la façon dont le service Intune est mis à jour.  Plusieurs composants du service doivent être actualisés de façon séquentielle avant que les nouvelles fonctionnalités du portail soient disponibles. Recherchez les modifications dans la préversion du portail Azure qui seront publiées à une date ultérieure ce mois-ci. Pour obtenir la liste complète des modifications, consultez [Nouveautés de la préversion de Microsoft Intune](/intune-azure/introduction/whats-new).

### <a name="administration-roles-being-replaced-in-azure-portal"></a>Rôles d’administration remplacés dans le portail Azure

Les rôles d’administration de la gestion des applications mobiles (GAM), à savoir Contributeur, Propriétaire et Lecture seule, qui sont utilisés dans le portail Intune classique, sont remplacés par un nouvel ensemble complet de contrôles d’administration basés sur des rôles (RBAC) dans le portail Intune Azure. Une fois la migration effectuée vers le portail Azure, vous devez associer vos administrateurs à ces nouveaux rôles d’administration. Pour en savoir plus sur les contrôles RBAC et les nouveaux rôles, voir [Rôles Intune (RBAC) pour Microsoft Intune](/intune-azure/access-control/role-based-access-control).


## <a name="whats-coming"></a>Nouveautés à venir

### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Mises à jour requises par Apple pour Application Transport Security <!--748318-->

La société Apple a annoncé qu’à compter du printemps 2017, elle appliquera des exigences de sécurité spécifiques pour Application Transport Security (ATS). ATS est utilisé pour renforcer la sécurité de toutes les communications d’application via le protocole HTTPS. Cette modification a une incidence sur les clients Intune qui utilisent les applications de portail d’entreprise iOS. Pour plus d’informations, consultez notre [blog de support Intune](https://aka.ms/compportalats).

### <a name="see-also"></a>Voir aussi
* [Blog Microsoft Intune](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Feuille de route de la plateforme cloud](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Nouveautés de la préversion Azure](https://docs.microsoft.com/intune-azure/introduction/whats-new)
* [Nouveautés de l’interface utilisateur du portail d’entreprise](https://docs.microsoft.com/intune/whats-new/whats-new-in-company-portal-ui)
* [Archive des nouveautés](whats-new-archive.md)

