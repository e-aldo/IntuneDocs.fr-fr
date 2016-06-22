---
# required metadata

title: Fonctionnalités de gestion des appareils mobiles | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: f23b3ee7-78da-4e53-9fc2-78e58401bcf9

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---
# Fonctionnalités Microsoft Intune de gestion des appareils mobiles

Microsoft Intune vous permet de gérer une gamme d’appareils en les *inscrivant* auprès du service. Les utilisateurs peuvent ensuite utiliser un *portail d’entreprise* pour effectuer différentes opérations telles que l’inscription de leur appareil, la recherche et l’installation d’applications, la vérification de la conformité de leur appareil aux stratégies d’entreprise et la prise de contact avec le service d’assistance informatique.
Cette rubrique fournit une liste complète des fonctionnalités liées à l’inscription d’appareils.

La gestion, l'inventaire, le déploiement d'applications, l'approvisionnement et la mise hors service sont gérés par le biais de la console d'administration Intune. Les utilisateurs ont accès au portail d'entreprise qui leur permet d'installer des applications, d'inscrire et de supprimer des appareils, et de contacter le service informatique ou le support technique.



## Configuration et sécurité des appareils

|Fonctionnalité|Détails|Plus d'informations|
|--------------|-----------|--------------------|
|Stratégies de configuration<br><br>Stratégies personnalisées|Les stratégies de configuration des appareils mobiles vous permettent de gérer de nombreux paramètres et fonctionnalités sur les appareils mobiles de votre organisation. Par exemple, vous pouvez exiger un mot de passe, restreindre le nombre de tentatives de connexion ayant échoué, limiter le nombre de minutes avant le verrouillage de l’écran, définir une date d’expiration du mot de passe et empêcher la réutilisation de mots de passe précédemment utilisés. Vous pouvez également contrôler l’utilisation de fonctionnalités matérielles et logicielles telles que l’appareil photo ou le navigateur web<br><br>Utilisez des stratégies personnalisées quand les stratégies de configuration ne contiennent pas le paramètre dont vous avez besoin. Pour les appareils iOS, vous pouvez importer les paramètres que vous avez exportés à l'aide de l'outil Apple Configurator. Pour d'autres appareils, vous pouvez utiliser des paramètres OMA-URI pour configurer les paramètres et fonctionnalités sur l'appareil.|[Gérer des paramètres et des fonctionnalités sur vos appareils avec des stratégies Microsoft Intune](/intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies)<br />|
|Réinitialisation à distance, verrouillage à distance et réinitialisation du code d'accès|Supprimez les données sensibles quand un appareil est perdu ou volé. Par exemple, vous pouvez verrouiller l'appareil à distance, restaurer ses paramètres d'usine ou effacer uniquement les données d'entreprise.<br>Vous pouvez réinitialiser les codes secrets si les utilisateurs ne peuvent plus accéder à leur appareil, verrouiller des appareils perdus ou volés ou supprimer les données d'appareils perdus ou volés.|[Protégez vos appareils avec le verrouillage à distance et la réinitialisation du mot de passe](/intune/deploy-use/use-remote-lock-and-passcode-reset-in-microsoft-intune) et [Retirer des appareils de la gestion Intune](/intune/deploy-use/retire-devices-from-microsoft-intune-management)|
|Mode plein écran|Permet de verrouiller certaines fonctionnalités des appareils mobiles comme la capture d'écran et le bouton d'alimentation. Vous permet également de limiter les appareils à l'exécution d'une seule application que vous spécifiez.|[Paramètres de la stratégie de configuration iOS dans Microsoft Intune](/intune/deploy-use/ios-policy-settings-in-microsoft-intune)|

## Gestion d'applications

|Fonctionnalité|Détails|Plus d'informations|
|--------------|-----------|--------------------|
|Déploiement et gestion d'applications|Fournit une gamme d'outils pour vous aider à gérer les applications mobiles tout au long de leur cycle de vie, notamment le déploiement d'applications à partir de fichiers d'installation ou de magasins d'applications, l'analyse détaillée de l'état des applications et la suppression d'applications.|[Déploiement d’applications dans Microsoft Intune](/intune/deploy-use/deploy-apps)|
|Applications conformes et non conformes|Vous permet de spécifier des listes d'applications conformes (que les utilisateurs sont autorisés à installer) et non conformes (que les utilisateurs ne doivent pas installer).|[Paramètres de la stratégie d’iOS dans Microsoft Intune](/intune/deploy-use/ios-policy-settings-in-microsoft-intune)|
|Gestion des applications mobiles|Configurez des restrictions pour les applications à l’aide de la gestion des applications mobiles pour les appareils que vous gérez avec Intune et également pour les appareils qui ne sont pas gérés par Intune. Une telle stratégie vous permet de renforcer la sécurité de vos données d'entreprise en limitant les opérations de copie et collage, de sauvegarde externe des données et de transfert des données entre les applications notamment.|[Configurer et déployer des stratégies de gestion des applications mobiles dans la console Microsoft Intune](/intune/deploy-use/configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console)<br><br>[Créer et déployer des stratégies de gestion des applications mobiles à l’aide de Microsoft Intune](/intune/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune)<br /><br />[Préparer des applications iOS pour la gestion des applications mobiles avec l'outil de création de package de restrictions d'application Microsoft Intune](/intune/deploy-use/prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool)<br /><br />[Préparer des applications Android pour la gestion des applications mobiles avec l'outil de création de package de restrictions d'application Microsoft Intune](/intune/deploy-use/prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool)|
|Configuration des applications mobiles|Utilisez des stratégies de configuration des applications mobiles pour fournir les paramètres pour des applications iOS pouvant être nécessaires lors de l’exécution d’une application. Par exemple, une application peut nécessiter que l’utilisateur spécifie un numéro de port ou des informations de connexion. Cela peut simplifier la configuration de l’application et réduire le nombre d’appels au support technique.|[Configurer des applications iOS avec des stratégies de configuration des applications mobiles dans Microsoft Intune](/intune/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune)|
|Managed Browser|Après avoir déployé Managed Browser sur vos utilisateurs, vous pouvez configurer une stratégie Managed Browser pour contrôler les sites web qu'ils peuvent visiter. En outre, vous pouvez également appliquer des stratégies de gestion des applications mobiles à Managed Browser.|[Gérer l'accès à Internet à l'aide de stratégies Managed Browser avec Microsoft Intune](/intune/deploy-use/manage-internet-access-using-managed-browser-policies)|
|Microsoft Passport|Intune vous permet d’intégrer Microsoft Passport for Work et de disposer ainsi d’une autre méthode de connexion pour Windows 10 utilisant Active Directory ou un compte Azure Active Directory pour remplacer un mot de passe, une carte à puce ou une carte à puce virtuelle.|[Contrôler les paramètres de Microsoft Passport sur les appareils avec Microsoft Intune](/intune/deploy-use/control-microsoft-passport-settings-on-devices-with-microsoft-intune)|

## Accès aux ressources d'entreprise

|Fonctionnalité|Détails|Plus d'informations|
|--------------|-----------|--------------------|
|Profils de certificat|Créez et déployez des profils de certificat approuvés et des certificats SCEP (Simple Certificate Enrollment Protocol) qui peuvent être utilisés pour sécuriser et authentifier des profils Wi-Fi, VPN et de messagerie.|[Sécuriser l’accès aux ressources avec des profils de certificat dans Microsoft Intune](/intune/deploy-use/secure-resource-access-with-certificate-profiles)|
|Profils Wi-Fi|Déployez les paramètres de réseau sans fil sur vos utilisateurs. En déployant ces paramètres, vous réduisez l'effort que doit fournir l'utilisateur final pour se connecter au réseau d'entreprise.|[Connexions Wi-Fi dans Microsoft Intune](/intune/deploy-use/wi-fi-connections-in-microsoft-intune)|
|Profils de messagerie|Créez et déployez des paramètres de messagerie pour les appareils. L'utilisateur peut ainsi accéder à sa messagerie professionnelle sur son appareil personnel sans aucune autre configuration de sa part.|[Configurer l’accès à la messagerie d’entreprise à l’aide de profils de messagerie avec Microsoft Intune](/intune/deploy-use/configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune)|
|Profils VPN|Déployez des paramètres VPN pour les utilisateurs et les appareils de votre organisation. En déployant ces paramètres, vous réduisez l'effort que doit fournir l'utilisateur final pour se connecter aux ressources du réseau d'entreprise.|[Connexions VPN dans Microsoft Intune](/intune/deploy-use/vpn-connections-in-microsoft-intune)|
|Stratégies d'accès conditionnel|Gérer l'accès à la messagerie Microsoft Exchange et à SharePoint Online sur des appareils qui ne sont pas gérés par Intune.|[Restreindre l’accès à la messagerie et à SharePoint avec Microsoft Intune](/intune/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune)|

## Inventaire et rapports

|Fonctionnalité|Détails|Plus d'informations|
|--------------|-----------|--------------------|
|Inventaire et rapports|Trouvez des informations sur les appareils que vous gérez et les logiciels qu'ils utilisent.|[Comprendre vos appareils grâce à l’inventaire de Microsoft Intune](./deploy-use/understand-your-devices-with-inventory-in-microsoft-intune)|


### Voir aussi
[Fonctionnalités de gestion des PC Windows dans Microsoft Intune](./windows-pc-management-capabilities-in-microsoft-intune.md)


<!--HONumber=Jun16_HO1-->


