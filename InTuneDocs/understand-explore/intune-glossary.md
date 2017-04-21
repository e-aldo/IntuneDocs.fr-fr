---
title: Glossaire Intune | Microsoft Docs
description: En savoir plus sur la terminologie de Microsoft Intune
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 11/17/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 86d00901-fac7-4471-aac2-f1d13a4879b6
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: ab6d9b6b296fb4e1fb0aaa9496fede28976728dc
ms.openlocfilehash: 9e084cce8e34b0de2dce7c6b8503d5b5089c930e
ms.lasthandoff: 04/14/2017


---

# <a name="microsoft-intune-glossary"></a>Glossaire Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

## <a name="a"></a>Objet

|||
|-|-|
|SDK d’application|Le [SDK d’application Microsoft Intune](/intune/develop/intune-app-sdk) vous permet d’ajouter des fonctionnalités à vos applications développées en interne, qui leur permettent d’être gérées par des stratégies de gestion des applications mobiles Intune.|
|Outil de création de package de restrictions d’application|[Application de ligne de commande](/intune/deploy-use/decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune) qui crée un wrapper autour d’une application métier, ce qui permet ensuite à l’application d’être gérée par une stratégie de gestion des applications mobiles Intune.|
|Installation disponible|Quand vous déployez une application avec cette action, elle apparaît sur le portail d’entreprise et les utilisateurs peuvent [l’installer à la demande](/intune/deploy-use/deploy-apps).|
|Portail Azure|Nouvelle console pour Intune, qui sera bientôt introduite. Pour le moment, vous pouvez utiliser le portail Azure pour créer des [stratégies GAM Intune ](/intune/deploy-use/azure-portal-for-microsoft-intune-mam-policies) pour les appareils.|

## <a name="b"></a>B
|||
|-|-|
|BYOD|[Apportez votre propre appareil (Bring Your Own Device)](/intune/get-started/choose-how-to-enroll-devices1). Les utilisateurs peuvent installer sur leur appareil l’application Portail d’entreprise Intune, puis inscrire leur appareil pour pouvoir accéder aux ressources d’entreprise comme la messagerie, les applications d’entreprise, les données d’entreprise et le support.|

## <a name="c"></a>C
|||
|-|-|
|Profil de certificat|Vous utilisez ce type de stratégie pour [sécuriser l’accès aux ressources d’entreprise](/intune/deploy-use/secure-resource-access-with-certificate-profiles) avec des certificats quand vous utilisez des profils Wi-Fi, E-mail ou VPN.|
|Espace de stockage cloud|Emplacement où les applications, ou les données sur les applications que vous créez, [sont stockées](/intune/deploy-use/add-apps#cloud-storage-space).|
|COD|Les [appareils d’entreprise](/intune/get-started/choose-how-to-enroll-devices1) peuvent être inscrits de différentes façons, selon les besoins de l’entreprise et les types d’appareils gérés.|
|Portail d'entreprise|Application ou site web qui permet aux utilisateurs [d’accéder aux données et applications de l’entreprise](/intune/get-started/microsoft-intune-company-portal).|
|Stratégie de conformité|Vérifiez que les appareils utilisés pour accéder aux applications et aux données de l’entreprise [sont conformes à certaines règles](/intune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune), comme utiliser un code confidentiel pour accéder à l’appareil et chiffrer les données qui y sont stockées.|
|Applications conformes et non conformes|Dans le cadre d’une [stratégie de configuration générale](/intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies), ces paramètres vous permettent de définir une liste des applications que les utilisateurs peuvent ou non exécuter. Intune vous informe ensuite via des rapports qu’une application non conforme a été installée ou exécutée. Pour certaines plateformes, Intune peut également bloquer l’installation d’une application non conforme.|
|Accès conditionnel|[Permet d’accéder à la messagerie d’entreprise, à Office 365 et à d’autres services](/intune/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune) seulement depuis des appareils qui sont conformes à des règles que vous définissez.|
|Stratégie personnalisée|Vous [utilisez ces stratégies](/intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies) quand une stratégie de configuration générale ne contient pas un paramètre prédéfini répondant à vos besoins. Vous serez peut-être en mesure d’utiliser une stratégie personnalisée pour créer un paramètre par d’autres moyens, comme Apple Configurator ou OMA-URI.|

## <a name="d"></a>D
|||
|-|-|
|Déploiement|Fait d’envoyer une application ou une stratégie à un appareil ou à un utilisateur que vous gérez.|
|Action de déploiement|Choix que vous faites quand vous [déployez une application](/intune/deploy-use/deploy-apps-in-microsoft-intune). Vous pouvez choisir de rendre l’installation de l’application obligatoire ou facultative, ou vous pouvez désinstaller l’application.|
|Gestionnaire d'inscription d'appareils|Les organisations peuvent utiliser Intune pour gérer un grand nombre d'appareils mobiles avec un seul compte d’utilisateur. Le compte du [gestionnaire d’inscription d’appareils](/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune) est un compte Intune spécial qui peut inscrire jusqu’à 1 000 appareils.|
|Mappage de groupe d’appareils|Vous aide à [ajouter automatiquement des appareils à des groupes](/intune/deploy-use/categorize-devices-with-device-group-mapping-in-microsoft-intune) en fonction d’une catégorie d’appareils (comme « Personnel » ou « Ventes ») que vous ou l’utilisateur final pouvez affecter à l’appareil.|

## <a name="e"></a>E
|||
|-|-|
|Profil de messagerie|Cette stratégie peut être utilisée pour configurer les [paramètres d’accès à la messagerie](/intune/deploy-use/configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune) pour des clients de messagerie spécifiques sur des appareils mobiles, en minimisant la configuration que l’utilisateur final doit effectuer.|
|EMS|Microsoft Enterprise Mobility + Security (anciennement Enterprise Mobility Suite) conserve les données de votre entreprise protégées tout en permettant à vos utilisateurs d’[accéder aux applications et au contenu dont ils ont besoin](https://www.microsoft.com/cloud-platform/enterprise-mobility).|
|Utilisateur final|[Utilisateurs d’appareils comme des téléphones et des PC](/intune/deploy-use/how-to-educate-your-end-users-about-microsoft-intune) gérés à l’aide d’Intune.|
|Inscription|Microsoft Intune utilise l’[inscription](/intune/deploy-use/enroll-devices-in-microsoft-intune) pour intégrer des appareils dans la gestion et pour autoriser l’accès à des ressources.|

## <a name="f"></a>F
|||
|-|-|
|FastTrack|[Service Microsoft](https://technet.microsoft.com/library/mt228265.aspx) pour les utilisateurs Intune avec 150 licences dans un forfait éligible. Avec ce service, des spécialistes Microsoft travaillent avec vous pour vous rendre opérationnel avec Intune.|

## <a name="g"></a>G
|||
|-|-|
|Groupes|Les groupes vous permettent de [regrouper logiquement des utilisateurs ou des appareils](/intune/deploy-use/use-groups-to-manage-users-and-devices-with-microsoft-intune). Par exemple, vous pouvez créer un groupe avec tous les PC Windows. Vous pouvez ensuite déployer des applications et une stratégie sur ces groupes.|

## <a name="h"></a>H
|||
|-|-|
|Hybride|Configuration où vous pouvez gérer des appareils inscrits avec Intune [via la console System Center Configuration Manager](/intune/get-started/integration-with-cloud-services).|

## <a name="i"></a>I
|||
|-|-|
|Console d'administration Intune|Console actuelle que vous utilisez pour la plupart des opérations de gestion Intune.|
|Client logiciel Intune|Autre moyen de [gérer des PC Windows](/intune/deploy-use/manage-windows-pcs-with-microsoft-intune). Consultez [Choisir comment gérer des appareils](/intune/get-started/choose-how-to-manage-devices) pour déterminer la méthode à utiliser.|
|Éditeur de logiciel Intune|Outil que vous utilisez pour [définir les applications que vous voulez déployer et les télécharger dans votre espace de stockage cloud](/intune/deploy-use/add-apps).|
|Inventaire|Utilisé pour afficher le [matériel et les logiciels installés](/intune/deploy-use/understand-your-devices-with-inventory-in-microsoft-intune) sur les appareils que vous gérez.|

## <a name="k"></a>K
|||
|-|-|
|Mode plein écran|Configuré dans le cadre d’une [stratégie de configuration générale](/intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies), ce mode vous permet de verrouiller des appareils. Par exemple, vous pouvez configurer un appareil destiné à la vente au détail pour y autoriser l’exécution d’une seule application.|

## <a name="m"></a>M
|||
|-|-|
|Managed Browser|[Application de navigation web](/intune/deploy-use/manage-internet-access-using-managed-browser-policies)que vous pouvez déployer dans votre organisation à l’aide de Microsoft Intune. Une stratégie Managed Browser configure une liste verte ou une liste rouge, qui restreint les sites web auxquels les utilisateurs de Managed Browser ont accès.|
|Gestion des applications mobiles|La [gestion des applications mobiles (GAM)](/intune/deploy-use/overview-of-app-lifecycle-in-microsoft-intune) vous permet de publier, envoyer des notifications Push, configurer, sécuriser, surveiller et mettre à jour des applications mobiles pour vos utilisateurs.
|Gestion des appareils mobiles|La [gestion des appareils mobiles (MDM)](/intune/deploy-use/overview-of-device-lifecycle-in-microsoft-intune) vous permet d’inscrire des appareils dans Intune pour approvisionner, configurer, surveiller et effectuer des actions sur ces appareils.
|Autorité MDM|L’[autorité de gestion d’appareils mobiles](/intune/deploy-use/get-ready-to-enroll-devices-in-microsoft-intune) définit le service de gestion habilité à gérer un ensemble d’appareils. Les options en matière d’autorité de gestion des appareils mobiles incluent Intune en version autonome et Configuration Manager avec Intune.|
|Stratégie d’approvisionnement des applications mobiles|Stratégie iOS qui permet de garantir que les [profils de configuration](/intune/deploy-use/ios-mobile-app-provisioning-profiles) pour les applications iOS que vous n’expirent pas.|
|Stratégies de configuration des applications mobiles|Stratégie iOS qui est utilisée pour [fournir des paramètres aux applications iOS compatibles](/intune/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune) quand elles sont exécutées, par exemple un nom de société ou l’adresse d’un serveur.|

## <a name="o"></a>O
|||
|-|-|
|OMA-DM|Open Mobile Alliance Device Management. Protocole de gestion d’appareils qui est un standard de l’industrie et qui est utilisé par de nombreux fabricants de matériel pour permettre le contrôle des fonctionnalités des appareils mobiles et des PC.|
|OMA-URI|Open Mobile Alliance Uniform Resource Identifier. Identifie les paramètres d’appareils individuels qui sont conformes à la norme OMA-DM. Plusieurs de ces paramètres peuvent être utilisés dans des [stratégies personnalisées Intune](/intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies) quand aucun paramètre prédéfini ne répond à vos besoins.|

## <a name="p"></a>P
|||
|-|-|
|Stratégie|[Ensemble d’informations](/intune/deploy-use/microsoft-intune-policy-reference) envoyé depuis Intune à un appareil. Par exemple, vous pouvez déployer des paramètres de sécurité ou des informations de conformité des appareils sur l’appareil.|
|Réinitialiser le code secret|Fonctionnalité Intune qui vous permet de forcer l’utilisateur final à [réinitialiser le code secret](/intune/deploy-use/use-remote-lock-and-passcode-reset-in-microsoft-intune) sur des appareils pris en charge.|

## <a name="r"></a>R
|||
|-|-|
|Verrouillage à distance|Fonctionnalité Intune qui vous permet de [verrouiller des appareils pris en charge](/intune/deploy-use/use-remote-lock-and-passcode-reset-in-microsoft-intune), même si vous n’êtes pas en possession de l’appareil.|
|Les rapports|Intune offre un ensemble de [rapports prédéfinis](/intune/deploy-use/understand-microsoft-intune-operations-by-using-reports) qui fournissent des informations sur les appareils que vous gérez.|
|Installation requise|Quand vous déployez une application avec cette action, elle est installée sur l’appareil sans [aucune intervention de l’utilisateur](/intune/deploy-use/deploy-apps) (bien que pour certaines plateformes, l’utilisateur final doive accepter l’installation).|
|Configuration requise|[Opération de déploiement d’application](/intune/deploy-use/add-apps) qui vous permet de sélectionner les conditions qui doivent être remplies sur un appareil avant que l’application soit installée. Par exemple, vous pouvez spécifier la version du système d’exploitation iOS qui doit être installée avant que l’application soit installée.|

## <a name="s"></a>S
|||
|-|-|
|Réinitialisation sélective|Une [réinitialisation sélective](/intune/deploy-use/use-remote-wipe-to-help-protect-data-using-microsoft-intune) supprime seulement les données d’entreprise, notamment les données de gestion des applications mobiles (GAM) (le cas échéant), les paramètres et les profils de messagerie sur un appareil. La réinitialisation sélective conserve les données personnelles de l’utilisateur sur l’appareil.|
|Abonnement|L’accord que vous acceptez qui vous permet d’accéder à un client Intune.|

## <a name="t"></a>T
|||
|-|-|
|TeamViewer|Une application de tiers qui fonctionne avec Intune pour fournir [des fonctionnalités d’assistance à distance](/intune/deploy-use/common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client#request-and-provide-remote-assistance-for-windows-pcs) pour les PC Windows gérés avec le client logiciel Intune.|
|Client|Une seule instance du service Intune auquel vous pouvez accéder à l’aide d’un abonnement.|
|Conditions générales|Type de stratégie que vous déployez sur les utilisateurs et qui contient des informations que les utilisateurs doivent [lire et accepter](/intune/deploy-use/terms-and-condition-policy-settings-in-microsoft-intune) avant de pouvoir utiliser le portail d’entreprise pour s’inscrire et accéder à leur travail.|

## <a name="v"></a>V
|||
|-|-|
|Applications achetées en volume|Certains magasins d’applications vous permettent d’acheter plusieurs licences pour une application que vous voulez utiliser dans votre entreprise. Intune vous aide à gérer les applications que vous avez [achetées via un programme de ce type](/intune/deploy-use/manage-volume-purchased-apps-in-microsoft-intune), en important les informations de licence à partir de l’App Store, en effectuant le suivi du nombre de licences que vous avez utilisées, et en vous empêchant d’installer un nombre de copies de l’application supérieur au nombre dont vous êtes propriétaire.|
|Profil VPN|Stratégie qui déploie des [paramètres VPN](/intune/deploy-use/vpn-connections-in-microsoft-intune) sur les appareils que vous gérez, qui réduit la configuration que les utilisateurs finaux doivent effectuer.|

## <a name="w"></a>W
|||
|-|-|
|Profil Wi-Fi|Stratégie qui déploie des [paramètres de réseau sans fil](/intune/deploy-use/wi-fi-connections-in-microsoft-intune) sur les appareils pour permettre aux utilisateurs de se connecter à votre réseau d’entreprise sans avoir à connaître ou à configurer des paramètres.

