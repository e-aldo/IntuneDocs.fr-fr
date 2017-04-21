---
title: "Créer une conception Intune | Microsoft Docs"
description: "Cet article vous permet de créer une conception dans le cadre de la conception et de l&quot;implémentation d&quot;un cloud Microsoft Intune uniquement."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a8e38e29-f5e3-4a71-a170-d3b1a06e37c6
ms.reviewer: jeffbu, cgerth
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: ab6d9b6b296fb4e1fb0aaa9496fede28976728dc
ms.openlocfilehash: ce51e92f9643ddc77e84e6b4c65825d397a37ddc
ms.lasthandoff: 04/14/2017


---

# <a name="create-an-intune-design"></a>Créer une conception Intune

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

La section du guide doit être utilisée en parallèle avec d’autres rubriques de la section 2. Cette conception sera basée sur les informations que vous collectez et les décisions que vous prendrez, complétant ainsi les sections précédentes de ce guide. Dans cette section traitant de la conception, nous allons nous concentrer sur la version autonome d’Intune, qui est un service cloud Microsoft.

Bien qu’il existe des conditions minimales concernant l’infrastructure en local, travaillez toujours sur un plan de conception pour vous assurer de disposer de la solution de gestion d’appareils mobiles adéquate qui répond à vos objectifs et exigences.

En outre, il est courant d’apporter des modifications de conception lors des phases d’implémentation et de test. Veillez à documenter ces modifications en les justifiant à mesure qu’elles se produisent. Nous allons aborder les domaines suivants :

-   L'environnement actuel

-   Options de déploiement Intune

-   Conditions d’identité requises pour les dépendances externes

-   Considérations relatives aux plateformes d'appareils

-   Conditions requises pour la remise  

Examinons chacun de ces domaines plus en détail. 

## <a name="record-your-environment"></a>Enregistrer votre environnement

La première étape avant de pouvoir créer votre conception consiste à enregistrer votre environnement actuel. L’environnement actuel peut influencer les décisions en matière de conception et doit être documenté et référencé lorsque que vous prenez d’autres décisions de conception Intune. Voici quelques exemples d’enregistrement de l’environnement actuel :

-   **Identifier dans le cloud**

    -   Utilisez-vous DirSync ou Azure Active Directory (AAD) Connect ?

    -   Votre environnement est-il fédéré ?

    -   L'authentification multifacteur est-elle activée ?

-   **Environnement de courrier électronique**

    -   Utilisez-vous Exchange ? En local ou dans le cloud ?

    -   Êtes-vous au milieu d’un projet de migration Exchange vers le cloud ?

-   **Solution de gestion des appareils mobiles actuelle**

    -   Utilisez-vous d'autres solutions de gestion des appareils mobiles ?

    -   Quelles solutions de gestion des appareils mobiles utilisez-vous pour l'entreprise et les scénarios d'utilisation BYOD ?

    -   Quelles fonctionnalités utilisez-vous (paramètres d'appareils, configurations Wi-Fi, etc.) ?

    -   Quelles sont les plateformes d'appareils prises en charge ?

    -   Quels groupes et combien d’utilisateurs exploitent la solution de gestion des appareils mobiles ?

-   **Solution de certificat**

    -   Avez-vous implémenté une solution de certificat ?

    -   Quel type de certificats utilisez-vous ?

-   **Systems Management**

    -   Comment gérez-vous votre environnement PC et serveur ?

    -   Utilisez-vous Microsoft System Center Configuration Manager ? Utilisez-vous une plate-forme de gestion système tierce ?

-   **Solution VPN**

    -   Quelle est votre solution VPN ?

    -   Est-elle utilisée pour des scénarios d'utilisation en entreprise et BYOD ?

Veillez à noter tous les projets ou tous les autres plans mis en place susceptibles de modifier votre environnement lors de l’enregistrement de l’environnement de gestion des appareils mobiles actuel. Voici un exemple de méthode d'enregistrement de l’environnement actuel qui peut se révéler utile lors de la création de votre conception Intune :

| **Zone de la solution** | **Environnement actuel** | **Commentaires** |
|:---:|:---:|:---:|
| **Identité** | Azure AD, Azure AD Connect, non fédéré, sans authentification multifacteur | Projet en place pour activer l’authentification multifacteur avant la fin de l’année |                 
| **Environnement de courrier électronique** | Exchange sur site, Exchange en ligne | En cours de migration d'Exchange sur site vers Exchange en ligne. 75 % de boîtes aux lettres migrés. Les 25 % restants seront migrés avant le début du projet pilote Intune. |                
| **SharePoint** | SharePoint sur site | Aucun plan pour migrer vers SharePoint en ligne |  
| **Gestion des appareils mobiles actuelle** | Exchange ActiveSync |  |
| **Solution de certificat** | Microsoft Server 2012 R2, services de certificats AD | Utiliser uniquement une PKI pour les serveurs de sites Web |
| **System Management** | System Center Configuration Manager CB 1606 | Souhaiterait étudier une solution Intune hybride |
| **Solution VPN** | Cisco AnyConnect |  |

## <a name="choose-an-intune-deployment-option"></a>Choisissez une option de déploiement Intune

Intune propose deux options de déploiement : autonome et hybride. Vous devrez choisir celle qui répond aux besoins de votre entreprise. Autonome fait référence au service Intune en cours d’exécution dans le cloud, hybride fait référence à l’intégration d’Intune avec System Center Configuration Manager.

- En savoir plus sur [choisir entre Microsoft Intune en mode autonome et la gestion des appareils mobiles hybride avec System Center Configuration Manager](https://docs.microsoft.com/sccm/mdm/understand/choose-between-standalone-intune-and-hybrid-mobile-device-management)

## <a name="intune-tenant-location"></a>Emplacement du client Intune

Si votre organisation est présente dans plusieurs pays, tenez compte de l'emplacement de votre client lors de l’abonnement au service. Le pays est défini lorsque vous souscrivez un abonnement Intune pour la première fois. Voici les régions du monde concernées :

-   Amérique du Nord

-   Europe, Moyen-Orient et Afrique

-   Asie et Pacifique

>[!IMPORTANT]
> Il n’est pas possible de modifier l’emplacement du pays/client ultérieurement.

## <a name="external-dependencies"></a>Dépendances externes

Les dépendances externes sont des services et des produits distincts d'Intune, mais elles constituent une condition requise pour Intune ou peuvent s'intégrer à Intune. Il est important d’identifier les conditions requises de toutes les dépendances externes et comment elles seront configurées. Vous trouverez ci-dessous quelques exemples de dépendances externes courantes.

-   Fournisseur

-   Groupes d’utilisateurs et d’appareils

-   PKI

Examinons plus en détail les dépendances externes courantes ci-dessous

### <a name="identity"></a>Fournisseur

L’identité est la façon dont nous identifions les utilisateurs qui appartiennent à votre organisation et inscrivent un appareil. Intune nécessite Azure Active Directory (Azure AD) comme fournisseur d’identité d'utilisateur. Si vous utilisez déjà ce service, vous pourrez tirer parti de votre identité déjà présente dans le cloud. En outre, Azure AD Connect est l’outil recommandé pour synchroniser les identités de vos utilisateurs locaux avec les services de cloud Microsoft. Si votre organisation utilise déjà Office 365, il est important qu'Intune utilise le même environnement Azure Active Directory.

Vous trouverez ci-dessous plus d’informations sur les spécifications d’identité d'Intune.

-   En savoir plus sur les [conditions requises pour les identités](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-overview#design-considerations-overview).

-   En savoir plus sur les [conditions requises pour la synchronisation d’annuaires](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-directory-sync-requirements).

-   En savoir plus sur [les conditions requises pour l’authentification multifacteur](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-multifactor-auth-requirements).

### <a name="user-and-device-groups"></a>Groupes d’utilisateurs et d’appareils

Les groupes d’utilisateurs et d'appareils déterminent la cible d’un déploiement. Cela peut inclure la cible d'un déploiement des stratégies, des applications et des profils. Le cloud Intune prend uniquement en charge des groupes d’utilisateurs et d’appareils : vous devez donc choisir les groupes d’utilisateurs et d’appareils qui seront nécessaires. Il est recommandé de créer tous les groupes dans Active Directory en local, puis de les synchroniser avec Azure Active Directory. Vous trouverez ci-dessous plus d’informations sur la planification et la création de groupes d'utilisateurs et d'appareils.

-   En savoir plus sur la [planification de vos groupes d’utilisateurs et d'appareils](https://docs.microsoft.com/intune/deploy-use/plan-your-user-and-device-groups).

-   En savoir plus la [création de groupes d’utilisateurs et d'appareils](https://docs.microsoft.com/intune/deploy-use/use-groups-to-manage-users-and-devices-with-microsoft-intune).

### <a name="public-key-infrastructure-pki"></a>Infrastructure à clé publique (PKI)

L'infrastructure à clé publique fournit des certificats aux appareils ou utilisateurs afin qu'ils puissent s’authentifier en toute sécurité auprès d’un service. Intune prend en charge une infrastructure PKI Microsoft. Les certificats d'utilisateur et d'appareil peuvent être transmis à un appareil mobile afin de répondre aux exigences de l’authentification basée sur un certificat. Avant d’implémenter des certificats, vous devez déterminer si les certificats sont nécessaires, si l’infrastructure du réseau peut prendre en charge l’authentification basée sur un certificat, et si des certificats sont actuellement utilisés dans l’environnement existant.

Si vous comptez utiliser des certificats avec des profils VPN, Wi-Fi ou de courrier électronique avec Intune, veillez à mettre en place une [infrastructure PKI](https://docs.microsoft.com/intune/deploy-use/secure-resource-access-with-certificate-profiles) prise en charge, prête à créer et à déployer des profils de certificat.

En outre, si des certificats SCEP seront transmis, vous devez choisir le serveur qui hébergera la fonctionnalité Service d’inscription de périphériques réseau (NDES), et comment la communication s'effectuera.

Pour plus d’informations sur la configuration des certificats dans Intune :

-   [Configurer l’infrastructure de certificats pour SCEP](https://docs.microsoft.com/intune/deploy-use/configure-certificate-infrastructure-for-scep).

-   [Configurer l’infrastructure de certificat pour PFX](https://docs.microsoft.com/intune/deploy-use/configure-certificate-infrastructure-for-pfx).

-   [Configurer les profils de certificats Intune](https://docs.microsoft.com/intune/deploy-use/configure-intune-certificate-profiles).

-   [Comment configurer les stratégies d’accès aux ressources](https://docs.microsoft.com/intune/deploy-use/enable-access-to-company-resources-with-microsoft-intune).

## <a name="device-platform-considerations"></a>Considérations relatives aux plateformes d'appareils

Vous devrez également examiner plus en détail vos appareils afin de bien comprendre leur utilisation.

-   Déterminer les plateformes d'appareils prises en charge

-   Appareils

-   Propriété des appareils

-   Inscription en bloc

Examinons ces domaines plus en détail.

### <a name="determine-supported-device-platforms"></a>Déterminer les plateformes d'appareils prises en charge

Vous devez identifier les appareils qui seront utilisés dans l’environnement et vérifier s'ils sont pris en charge ou non par Intune lors de la création de votre conception. Intune prend en charge les plateformes iOS, Android et Windows.

-   En savoir plus sur les [appareils pris en charge par Intune](https://docs.microsoft.com/intune/get-started/supported-mobile-devices-and-computers).

### <a name="devices"></a>Appareils

Intune gère les appareils mobiles pour sécuriser les données d’entreprise et permettre aux utilisateurs de travailler depuis plusieurs endroits. Comme Intune prend en charge plusieurs plateformes d'appareils, il est recommandé de documenter les appareils et les plateformes de système d’exploitation pris en charge dans la conception de votre organisation. Cette règle s'appliquera également aux appareils et plateformes créés dans la section (exigences du scénario d’utilisation).

Il est également recommandé d'identifier les versions pour référencer la liste lors de la vérification des fonctionnalités de l’appareil par plate-forme de système d’exploitation et version. Voici un exemple :

| **Plate-forme d'appareil** | **Versions du système d'exploitation** |
|:---:|:---:|
| iOS - iPhone | 9.0+ |                
| iOS - iPad | 8.0+ |               
| Android – Samsung Knox Standard | 4.0+ |
| Tablette Windows 10 | 10+ |

### <a name="device-ownership"></a>Propriété des appareils

Intune prend en charge à la fois la propriété d'entreprise et BYOD. Un appareil est considéré comme appartenant à l'entreprise s'il est inscrit par un gestionnaire d’inscription des appareils ou par un programme d'inscription des appareils. Par exemple, un appareil peut être inscrit via Apple DEP, marqué comme appartenant à l'entreprise et placé dans un groupe d'appareils auquel s'appliquent des stratégies d’entreprise et des applications ciblées.

Reportez-vous à la [Section 3 : déterminer les exigences du scénario d’utilisation](section-3-determine-use-case-requirements.md) pour plus d'informations sur les scénarios d'utilisation d'entreprise et BYOD.

### <a name="bulk-enrollment"></a>Inscription en bloc

Il existe plusieurs options disponibles pour l’inscription d’un appareil dans Intune afin de compléter l’inscription libre-service via le portail d’entreprise. Une inscription en bloc peut être effectuée de différentes manières selon la plateforme. Si une inscription en bloc sera nécessaire, déterminez d'abord la méthode d’inscription en bloc et incorporez-la dans votre conception. Vous trouverez ci-dessous plus d'informations sur les différentes méthodes d’inscription en bloc.

-   En savoir plus l'[inscription en bloc](https://docs.microsoft.com/intune/deploy-use/enroll-devices-in-microsoft-intune).

## <a name="feature-requirements"></a>Exigences concernant les fonctionnalités

Dans les sections suivantes, nous allons examiner les fonctionnalités et capacités qui répondent aux besoins de votre scénario d’utilisation :

-   Politiques de conditions générales

-   Stratégies de configuration

-   Profils de ressources

-   Applications

-   Stratégie de conformité

-   Accès conditionnel

Examinons chacun de ces domaines plus en détail.

### <a name="terms-and-conditions-policies"></a>Politiques de conditions générales

Des conditions générales peuvent expliquer les stratégies ou les conditions qu’un utilisateur final doit accepter avant l’inscription. Intune permet d’ajouter et de déployer plusieurs stratégies de conditions générales pour des groupes d’utilisateurs. Vous devez déterminer si des conditions générales sont nécessaires. Dans ce cas, vous devez désigner une personne chargée de fournir ces informations au sein de l’organisation.

-   En savoir plus [comment créer des stratégies de conditions générales](https://docs.microsoft.com/intune/deploy-use/terms-and-condition-policy-settings-in-microsoft-intune) dans Intune. Voici un exemple montrant comment documenter la stratégie de conditions générales.

| **Nom des conditions générales** | **Scénario d'utilisation** | **Groupe ciblé** |
|:---:|:---:|:---:|
| Conditions générales d'entreprise | Entreprise | Utilisateurs d’entreprise |                 
| Conditions générales BYOD | BYOD | Utilisateurs BYOD |                

### <a name="configuration-policies"></a>Stratégies de configuration

Stratégies de configuration utilisées pour gérer les paramètres de sécurité et les fonctionnalités sur un appareil. Lorsque vous concevez vos stratégies de configuration, consultez la section Exigences du scénario d’utilisation pour déterminer les exigences des appareils Intune. Documentez les réglages (et comment ils doivent être configurés) ainsi que les groupes d'utilisateurs ou d'appareils qui seront ciblés.

Vous devez créer au moins une stratégie de configuration par plate-forme. Vous pouvez créer plusieurs stratégies de configuration par plate-forme si nécessaire. Voici un exemple de conception de quatre stratégies de configuration pour différentes plateformes et scénarios d'utilisation.

| **Nom de la stratégie** | **Plate-forme d'appareil** | **Paramètres** | **Groupe cible** |   
|:---:|:---:|:---:|:---:|
| Entreprise - iOS | iOS | Code PIN nécessaire, longueur : 6, restreindre la sauvegarde sur le cloud | Appareils d'entreprise |                                                           
| Entreprise - Android | Android | Code PIN nécessaire, longueur : 6, restreindre la sauvegarde sur le cloud | Appareils d'entreprise |                                                           
| BYOD – iOS  | iOS | Code PIN nécessaire, longueur : 4 | Appareils BYOD |
| BYOD – Android  | Android | Code PIN nécessaire, longueur : 4 | Appareils BYOD |

### <a name="profiles"></a>Profils

Les profils sont utilisés pour aider l’utilisateur final à se connecter aux données d’entreprise. Intune prend en charge plusieurs types de profils. Consultez les scénarios d’utilisation et les exigences pour déterminer quand les [profils](https://docs.microsoft.com/intune/deploy-use/enable-access-to-company-resources-with-microsoft-intune) seront configurés. Tous les profils d'appareils sont classés par type de plate-forme et doivent être inclus dans la documentation de conception.

-   Profils de certificat

-   Profil Wi-Fi

-   Profil VPN

-   Profil de messagerie

Examinons chaque type de profil plus en détail.

##### <a name="certificate-profiles"></a>Profils de certificat

Les profils de certificat permettent à Intune de transmettre un certificat à un utilisateur ou à un appareil. Intune prend en charge les profils suivants :

-   Protocole SCEP (Simple Certificate Enrollment Protocol)

-   Certificat racine approuvé

-   Certificat PFX.

Il est recommandé de documenter quel groupe d'utilisateurs a besoin d’un certificat, le nombre de profils de certificat qui seront nécessaires et les groupes d’utilisateurs sur lesquels ils seront déployés.

>[!NOTE]
> N’oubliez pas que le certificat racine approuvé est requis pour le certificat SCEP. Assurez-vous par conséquent que tous les utilisateurs ciblés pour le certificat SCEP reçoivent également un certificat racine approuvé. Si des certificats SCEP sont nécessaires, concevez et documentez les modèles de certificat SCEP qui seront nécessaires.

Voici un exemple montrant comment documenter les certificats lors de la conception :

| **Type** | **Nom du profil** | **Plate-forme d'appareil** | **Scénarios d'utilisation** |   
|:---:|:---:|:---:|:---:|
| Autorité de certification racine | Autorité de certification racine d’entreprise | Android, iOS, Windows mobile | Entreprise, BYOD  |                                                           
| SCEP | Certificat d'utilisateur | Android, iOS, Windows mobile | Entreprise, BYOD |                                                           

##### <a name="wi-fi-profile"></a>Profil Wi-Fi

Les profils Wi-Fi permettent de connecter automatiquement un appareil mobile à un réseau sans fil. Intune prend en charge le déploiement de profils Wi-Fi sur toutes les plateformes prises en charge.

-   En savoir plus sur [comment Intune prend en charge les profils Wi-Fi.](https://docs.microsoft.com/intune/deploy-use/wi-fi-connections-in-microsoft-intune)

Voici un exemple de conception pour un profil Wi-Fi :

| **Type** | **Nom du profil** | **Plate-forme d'appareil** | **Scénarios d'utilisation** |   
|:---:|:---:|:---:|:---:|
| Wi-Fi | Profil Wi-Fi Asie | Android | Entreprise, BYOD - région Asie|                                                           
| Wi-Fi | Profil Wi-Fi Amérique du Nord | Android, iOS, Windows 10 Mobile | Entreprise, BYOD - région Amérique du Nord |                                                           

##### <a name="vpn-profile"></a>Profil VPN

Les profils VPN permettent aux utilisateurs d’accéder en toute sécurité à votre réseau à partir d’emplacements distants. Intune prend en charge les profils VPN à partir de connexions VPN mobiles natives et de fournisseurs tiers.

-   En savoir plus sur les [profils VPN et les fournisseurs pris en charge par Intune](https://docs.microsoft.com/intune/deploy-use/vpn-connections-in-microsoft-intune).

Voici un exemple de documentation de la conception d’un profil VPN.

| **Type** | **Nom du profil** | **Plate-forme d'appareil** | **Scénarios d'utilisation** |   
|:---:|:---:|:---:|:---:|
| VPN | Profil VPN Cisco AnyConnect | Android, iOS, Windows 10 Mobile | Entreprise, BYOD - Amérique du Nord et Allemagne|                                                           
| VPN | Pulse Secure | Android | Entreprise, BYOD - région Asie |                                                           

##### <a name="email-profile"></a>Profil de messagerie

Les profils de messagerie permettent de configurer automatiquement un client de messagerie à l'aide des informations de connexion et la configuration de la messagerie. Intune prend en charge les profils de messagerie sur certains appareils.

-   En savoir plus sur [profils de messagerie](https://docs.microsoft.com/intune/deploy-use/configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune) et quelles plateformes sont prises en charge.

Voici un exemple de documentation de la conception de profils de messagerie :

| **Type** | **Nom du profil** | **Plate-forme d'appareil** | **Scénarios d'utilisation** |   
|:---:|:---:|:---:|:---:|
| Profil de messagerie | Profil de messagerie iOS | iOS | Entreprise – BYOD travailleur de l'information |                                                           
| Profil de messagerie | Profil de messagerie Android Knox | Android Knox | BYOD |

### <a name="apps"></a>Applications

Intune prend en charge plusieurs types de distribution d’applications à des utilisateurs ou appareils. Le type d’application remis peut-être des applications logicielles d'installation, des applications d'un magasin d’applications public, des liens externes ou des applications iOS gérées. En plus des déploiements d’applications individuels, les applications achetés en volume peuvent être gérées et déployées via les programmes d’achats en volume pour iOS et Windows. Vous trouverez ci-dessous plus d’informations sur la manière dont Intune prend en charge les applications et les programmes d’achats en volume.

-   En savoir plus sur les [types d’applications](https://docs.microsoft.com/intune/deploy-use/enroll-devices-in-microsoft-intune)

-   En savoir plus sur le [programme d'achats en volume iOS pour les entreprises (VPP](https://docs.microsoft.com/intune/deploy-use/manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune)).

-   En savoir plus sur [Windows Store pour Entreprises](https://docs.microsoft.com/intune/deploy-use/manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune).

#### <a name="app-type-requirements"></a>Exigences de type d’application

Comme les applications peuvent être déployées sur des utilisateurs et des appareils, il est recommandé de déterminer les applications qui seront gérées par Intune. Lorsque vous en dressez la liste, essayez de répondre aux questions suivantes :

-   Les applications nécessitent-elle une intégration à des services cloud ?

-   Les applications sont-elles toutes accessibles aux utilisateurs BYOD ?

-   Quelles sont les options de déploiement disponibles pour ces applications ?

-   Votre entreprise doit-elle fournir un accès à des données applications SaaS Software as a service (SaaS) à ses partenaires ?

-   Les applications nécessitent-elle un accès à Internet à partir des appareils de l'utilisateur ?

-   Les applications sont-elles disponibles publiquement dans un magasin d’applications, ou s'agit-il d'applications métier personnalisées ?


>[!TIP]
> Découvrez les [différents types d’applications pris en charge par Intune](https://docs.microsoft.com/intune/deploy-use/add-apps).

#### <a name="app-protection-policies"></a>Stratégies de protection des applications

Les stratégies de protection des applications limitent les perte de données en définissant la manière dont l’application gère les données d’entreprise. Intune prend en charge les stratégies de protection des applications pour toute application créée pour fonctionner avec la gestion des applications mobiles. Lorsque vous créez la stratégie de protection des applications, vous devez déterminer quelles restrictions vous voulez appliquer aux données d’entreprise dans une application donnée. Il est recommandé d’examiner la façon dont les [stratégies de protection des applications](https://docs.microsoft.com/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) fonctionnent. Voici un exemple montrant comment documenter les applications existantes et quelle protection est nécessaire.

| **Application** | **Fonction** | **Plateformes** | **Scénario d'utilisation** | **Stratégie de protection d'application** |
|:---:|:---:|:---:|:---:|:---:|
| Outlook Mobile  | Disponible | iOS | Entreprise - Cadres | Ne peut pas être jailbreaké, chiffrement des fichiers |                                                         
| Word | Disponible | iOS, Android - Samsung Knox, non-Knox, Windows 10 Mobile | Entreprise, BYOD | Ne peut pas être jailbreaké, chiffrement des fichiers |                                                         

#### <a name="compliance-policies"></a>Stratégies de conformité

Les stratégies de conformité déterminent si un appareil est conforme à certaines exigences. Intune utilise des stratégies de conformité pour déterminer si un appareil est considéré conforme ou non conforme. L’état de conformité peut ensuite servir à restreindre l’accès aux ressources d’entreprise. Si un accès conditionnel est requis, il est recommandé de concevoir une [stratégie de conformité d'appareil](https://docs.microsoft.com/intune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune). Reportez-vous à la configuration requise et aux cas d’utilisation pour déterminer le nombre de stratégies de conformité d'appareils nécessaires et les groupes d’utilisateurs ciblés. En outre, vous devez déterminer la durée pendant laquelle un appareil peut rester déconnecté sans s'identifier avant d'être considéré non conforme.

Voici un exemple de conception d’une stratégie de conformité :

| **Nom de la stratégie** | **Plate-forme d'appareil** | **Paramètres** | **Groupe cible** |   
|:---:|:---:|:---:|:---:|
| Stratégie de conformité | iOS, Android - Samsung Knox, non-Knox, Windows 10 Mobile | Code PIN - requis, ne peut pas être jailbreaké | Entreprise, BYOD |

#### <a name="conditional-access-policies"></a>Stratégies d'accès conditionnel

L'accès conditionnel est utilisé pour autoriser uniquement les appareils compatibles à accéder aux ressources de l’entreprise. Intune fonctionne avec la totalité d'Enterprise Mobility + Security (EMS) pour contrôler l’accès aux ressources de l’entreprise. Vous devez déterminer si l’accès conditionnel est requis, et ce qui doit être sécurisé.

-   En savoir plus sur l'[accès conditionnel](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune).

Pour l'accès en ligne, déterminez les plateformes et les groupes d’utilisateurs ciblés par les stratégies d’accès conditionnel.

En outre, vous devez déterminer si vous devez installer/configurer le connecteur service à service Intune pour Exchange Online ou Exchange sur site.

Découvrez comment installer et configurer les connecteurs service à service Intune :

-   [Exchange Online](https://docs.microsoft.com/intune/deploy-use/intune-service-to-service-exchange-connector)

-   [Exchange sur site](https://docs.microsoft.com/intune/deploy-use/intune-on-premises-exchange-connector)

Voici un exemple montrant comment documenter des stratégies d’accès conditionnel :

| **Service** | **Plateformes pour l'authentification moderne** | **Authentification de base** | **Scénarios d'utilisation** |   
|:---:|:---:|:---:|:---:|
| Exchange Online | iOS, Android | Bloquer les appareils non conformes sur les plateformes prises en charge par Microsoft Docs | Entreprise, BYOD |
| SharePoint Online | iOS, Android |  | Entreprise, BYOD |

## <a name="next-section"></a>Section suivante

La section suivante fournit des conseils sur le [processus d’implémentation Intune](section-8-onboarding-process.md).

