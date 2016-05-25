---
# required metadata

title: Nouveautés à venir | Microsoft Intune
description:
keywords:
author: Lindavr
manager: jeffgilb
ms.date: 05/03/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Nouveautés à venir de Microsoft Intune
Ces informations sont fournies de manière très limitée dans le cadre d’un accord de confidentialité et sont susceptibles de changer. Certaines fonctionnalités répertoriées ici risquent de ne pas être prêtes d’ici la date limite et d’être repoussées à une version ultérieure. D’autres fonctionnalités sont en cours de test dans un pilote (version d’évaluation) pour s’assurer qu'elles sont prêtes à l'emploi. Veuillez contacter votre responsable Intune ou votre chef de projet si vous avez des questions ou rencontrez des problèmes.

Cette page est mise à jour périodiquement. Vérifiez régulièrement les mises à jour Nouveautés à venir.

Les modifications suivantes sont en cours de développement pour Intune. Toutes ces fonctionnalités seront également prises en charge pour les déploiements de clients hybrides (Configuration Manager avec Intune). Pour plus d'informations sur les nouvelles fonctionnalités hybrides, consultez notre [page hybride Nouveautés](https://technet.microsoft.com/en-US/library/mt718155(TechNet.10).aspx).

## Intégration du centre des messages
Dans le cadre de la migration d’Intune vers le [portail de gestion Office 365](https://portal.office.com/), nous allons commencer par tirer parti du centre de messages pour communiquer les nouvelles fonctionnalités et autres notifications.  En outre, en installant l'application mobile d’administration Office 365, vous pouvez recevoir des notifications sur votre téléphone mobile et transférer facilement des messages à des utilisateurs ou à un alias de distribution.<br>  
Nous allons commencer en utilisant le centre de messages avec la version de mai, qui vous avertira lorsque des mises à jour seront terminées et inclura des informations sur les nouvelles fonctionnalités Intune.  Consultez dès aujourd’hui le centre des messages en vous connectant au [portail de gestion Office 365](https://portal.office.com/) et en choisissant l’option **CENTRE DES MESSAGES** dans le volet de navigation gauche.
<!---TFS 1242782--->


## Gestion d'applications
- **Accès conditionnel pour le navigateur.** Vous ne pourrez pas définir une stratégie d'accès conditionnel pour Exchange Online et SharePoint Online afin que ces applications soient uniquement accessibles aux appareils iOS et Android gérés et compatibles. Les utilisateurs finaux qui essaient de se connecter à des sites Outlook Web Access (OWA) et SharePoint avec des appareils iOS et Android seront invités à inscrire leurs appareils avec Intune, et à résoudre les problèmes d'incompatibilité avant de pouvoir finaliser la connexion.
<!---TFS 1175844--->

- **SDK MAM : prise en charge de la configuration de longueur de code confidentiel.** Vous pourrez spécifier la longueur du code confidentiel des applications MAM comme s’il s’agissait du code confidentiel d’un appareil. Cette opération obligera les utilisateurs finaux à respecter les nouvelles restrictions que vous définissez. Ils verront un écran légèrement différent pour prendre en compte la saisie d’un code confidentiel plus long.
<!--- TFS 1104753--->

- **Contrôles MAM pour empêcher la synchronisation des contacts Outlook (iOS).** Un nouveau paramètre est disponible pour la gestion des applications mobiles sans inscription de l'appareil. Ce paramètre permet à l'administrateur Intune d’empêcher une application de synchroniser les contacts avec le carnet d'adresses natif sur les appareils iOS. Si ce paramètre est activé, l'application ne pourra plus enregistrer les contacts dans le carnet d'adresses natif. Si ce paramètre est désactivé, l'application pourra enregistrer les contacts dans le carnet d'adresses natif. Lorsqu'un administrateur Intune réinitialise de façon sélective un appareil, tous les contacts déjà enregistrés dans le carnet d'adresses natif seront supprimés. Ce nouveau paramètre est désormais pris en charge par l'application Outlook sur les appareils iOS.
<!---TFS item 1276166--->

- **Skype Entreprise pour Android.** Les administrateurs Intune peuvent maintenant cibler Skype Entreprise avec MAM sans stratégie d'inscription.  Une fois les utilisateurs connectés, les stratégies auxquelles seront appliquées.
<!--- TFS item 1248444 --->

- **Skype Entreprise pour iOS.** Les administrateurs Intune peuvent maintenant cibler Skype Entreprise avec MAM sans stratégie d'inscription.  Une fois les utilisateurs connectés, les stratégies auxquelles seront appliquées.
<!--- TFS item 1248443 --->

### Prise en charge de Xamarin
Le Kit de développement logiciel (SDK) de l'application Microsoft Intune prend désormais en charge les applications Xamarin dans ces scénarios :

- Écriture de nouvelles applications ou modification des applications métier existantes à l'aide du kit de développement logiciel (SDK) Intune. Vous pouvez obtenir le plug-in sur la page [Microsoft Intune Github](https://github.com/msintuneappsdk).
- Ajout de la prise en charge MAM aux applications métier existantes à l'aide de l'outil de création de package de restrictions d'application Intune

Pour faciliter le choix de la méthode à utiliser, consultez [Décider comment préparer les applications pour la gestion des applications mobiles avec Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune).
<!--- TFS 1061478 & TFS 1152340--->


## Gestion des appareils
- **Sessions d'assistance à distance pour les PC Windows.** L’intégration de TeamViewer Windows pour les PC gérés par agent vous permet d'établir des sessions d'assistance à distance avec des ordinateurs Windows gérés par agent dans le cadre du support technique de l'utilisateur final. Cela inclut Windows 7, 8, 8.1 et Windows 10.
<!--- TFS 1284856--->


<!--- TFS item 1274326 --->

## Contrôle d'accès
* **Skype Entreprise Online prend en charge l'accès conditionnel.** Les administrateurs Intune pourront définir une stratégie d'accès conditionnel pour Skype Entreprise Online afin que cette application soit uniquement accessible aux appareils iOS et Android gérés et compatibles. Les utilisateurs finaux qui essaient de se connecter à l’application mobile Skype Entreprise sur un appareil iOS et Android seront invités à s'inscrire auprès d’Intune et à résoudre les éventuels problèmes d'incompatibilité avant de finaliser la connexion.
<!---TFS item 1254499--->

## Portail d'entreprise
* **Une bannière d'identification de l’appareil fournit davantage d'informations aux utilisateurs finaux.** Les utilisateurs finaux pourront ainsi facilement identifier l’appareil qu'ils ont sélectionné lorsqu'ils utilisent le site Web du portail d'entreprise. Si un appareil incorrect est sélectionné, ils pourront sélectionner l’appareil approprié en cliquant sur le lien « Tap here » dans la bannière de la page d'accueil.
<!--- TFS 1231157--->

* **Packages d'applications Windows directement accessibles depuis le portail d'entreprise** : les utilisateurs de PC sous Windows 8, Windows 8.1 et Windows RT peuvent désormais installer des packages d'applications Windows (avec l'extension .aspx) directement depuis le site Web du portail d'entreprise. Auparavant, les administrateurs Intune devaient effectuer le déploiement, ou les utilisateurs devaient installer l'application Portail d'entreprise sur leurs appareils pour installer des applications.
<!--- TFS item 1082481 --->

* **Les utilisateurs peuvent verrouiller à distance leurs appareils depuis le portail d'entreprise** Une nouvelle option de verrouillage à distance a été ajoutée au site Web du portail d'entreprise pour permettre aux utilisateurs finaux de verrouiller à distance leurs appareils depuis le portail si leur appareil est égaré ou volé. Le tableau suivant répertorie les plates-formes prises en charge pour le verrouillage à distance avec Intune et Intune avec Configuration Manager.
<!--- TFS item 1195661 --->

|Plate-forme  |Détails de la prise en charge|
|---------|---------|
|iOS | Pris en charge|
|Android | Pris en charge|
|Windows Phone 8.1 | Pris en charge|
|Windows 10 Mobile | Pris en charge uniquement si le téléphone dispose d’un code secret|
|PC (Windows 8.0 et versions antérieures) | Non prise en charge|
|PC (Windows 8.1) | Non prise en charge|
|Windows Phone 8.0 | Non pris en charge|
|Windows 10 Desktop | Non pris en charge|

## Désapprobation du service
* **Ciblage de groupe personnalisé de suppression des règles de notification.** À partir de juin 2016, vous ne pourrez plus utiliser l'Assistant Créer règle de notification pour cibler des groupes créés par l'utilisateur avec des règles de notification.

    Actuellement, pour cibler un groupe créé par l'utilisateur depuis la console d'administration Microsoft Intune, vous sélectionnez **Admin** > **Règles de notification** > **Créer une règle**. À l'étape 2 de l'Assistant Créer règle de notification, vous devez sélectionner les groupes d’appareils que la règle ciblera. Cette étape, **Sélection de groupes d’appareils**, est déconseillée à partir de la console Intune.

    L’étape **Sélection de groupes d’appareils** ne sera plus prise en charge après la version Intune 1606 de juin. Toutefois, cette option continuera de s’afficher jusqu'en août 2016. Après août, nous commencerons à migrer progressivement nos clients vers la nouvelle version sur une période de deux mois. D’ici octobre 2016, tous les clients existants devraient avoir passé à la nouvelle version. Après la migration vers la nouvelle version, vous ne verrez plus s’afficher l'option permettant de cibler un groupe spécifique avec les règles de notification.
<!---   TFS 1278864--->







### Voir aussi
Consultez [Nouveautés de Microsoft Intune](whats-new-in-microsoft-intune.md) pour plus de détails sur les derniers développements.


<!--HONumber=May16_HO1-->


