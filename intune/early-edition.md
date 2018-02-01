---
title: "Édition préliminaire"
description: 
keywords: 
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 01/24/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: d4bcabc4d1af4554a3e3bea875be45f9376b4ef7
ms.sourcegitcommit: b982f9d50da4f958fb0c48c56ba46c8ef71500c4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2018
---
# <a name="the-early-edition-for-microsoft-intune---february-2018"></a>Édition préliminaire de Microsoft Intune - Février 2018

**L’édition préliminaire** fournit la liste des fonctionnalités qui seront intégrées dans les prochaines versions de Microsoft Intune. Ces informations sont fournies de manière limitée et sont susceptibles de changer. Ne partagez pas ces informations en dehors de votre entreprise. Certaines fonctionnalités répertoriées ici risquent de ne pas être prêtes d’ici la date limite et d’être repoussées à une version ultérieure. D’autres fonctionnalités sont en cours de test dans un pilote (version d’évaluation) pour s’assurer qu'elles sont prêtes à l'emploi. Joignez votre contact de groupe de produits Microsoft si vous avez des questions ou rencontrez des problèmes.

Cette page est mise à jour périodiquement. Consultez-la régulièrement pour savoir si des mises à jour supplémentaires sont disponibles.

> [!Note]
>Les modifications suivantes sont en cours de développement pour Intune. Pour plus d’informations sur les nouvelles fonctionnalités hybrides, consultez notre page [Nouveautés hybrides](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

<!--
## What's coming to Intune in the Azure portal  
## What's coming to Intune apps
## Notices
-->

## <a name="intune-in-the-azure-portal"></a>Intune dans le portail Azure


<!-- 1802 start -->


### <a name="app-protection-policies-----679615---"></a>Stratégies de protection des applications  <!-- 679615 -->
Les stratégies Intune App Protection permettent de créer des stratégies globales, par défaut, afin d’activer rapidement la protection pour tous les utilisateurs dans l’ensemble du locataire.

### <a name="intune-support-for-multiple-apple-dep--apple-school-manager-accounts----747685---"></a>Prise en charge d’Intune pour plusieurs comptes DEP / Apple School Manager <!-- 747685 -->

Intune prendra en charge l’inscription des appareils jusqu'à la limite de 100 comptes dans le cadre du Programme d’inscription des appareils (DEP) ou Apple School Manager. Chaque jeton téléchargé peut être géré séparément pour les profils d’inscription et les appareils. Un profil d’inscription différent peut être affecté automatiquement pour chaque jeton DEP/School Manager téléchargé. Si plusieurs jetons School Manager sont téléchargés, un seul jeton peut être partagé avec Microsoft School Data Sync à la fois.

Après la migration, les API Graph en version bêta et les scripts publiés pour la gestion DEP Apple ou ASM via Graph ne fonctionneront plus. De nouvelles versions bêta des API Graph sont en cours de développement et seront publiées après la migration.

### <a name="windows-defender-health-status-and-threat-status-reports---854704---"></a>Rapports sur l’état des menaces et l’état d’intégrité de Windows Defender<!--854704 -->

Il est essentiel de comprendre l’état et l’intégrité de Windows Defender pour gérer des PC Windows.  Intune ajoute de nouveaux rapports et de nouvelles actions à l’état et l’intégrité de l’agent Windows Defender. À l’aide d’un rapport de cumul d’état dans la charge de travail Conformité de l’appareil, vous serez en mesure de voir les appareils qui nécessitent les actions suivantes :

- mise à jour des signatures
- redémarrage
- intervention manuelle
- analyse complète
- autres états de l’agent nécessitant une intervention

Dans certains cas, des actions de correction à distance peuvent être entreprises, telles que le déclenchement d’une mise à jour des signatures.  Le rapport indique également le nombre de PC signalés comme **sans problème**.

Un rapport détaillé pour chaque catégorie d’état liste les PC individuels nécessitant une attention particulière, ou ceux qui sont signalés comme **sans problème**.

### <a name="protocol-exceptions-for-applications---1035509-eeready--"></a>Exceptions de protocoles pour les applications<!--1035509 eeready-->

Vous serez en mesure de créer des exceptions à la stratégie de transfert de données de gestion des applications mobiles (MAM) Intune pour ouvrir des applications non gérées spécifiques. De telles applications doivent être approuvées par le service informatique. À part les exceptions que vous créez, le transfert de données sera toujours limité aux applications qui sont gérées par Intune quand votre stratégie de transfert de données est définie sur **les applications gérées uniquement**. Vous pouvez créer les restrictions à l’aide de protocoles (iOS) ou de packages (Android).

Par exemple, vous pouvez ajouter le package Webex en tant qu’exception à la stratégie de transfert de données MAM. Cela permet d’ouvrir les liens Webex dans un e-mail Outlook géré directement dans l’application Webex. Le transfert de données sera toujours limité dans d’autres applications non gérées.

### <a name="customize-your-company-portal-themes-with-hex-codes---1049561-eeready--"></a>Personnaliser vos thèmes de portail d’entreprise avec des codes hexadécimaux<!--1049561 eeready-->

Vous serez en mesure de personnaliser la couleur de thème dans les applications Portail d’entreprise à l’aide de codes hexadécimaux. Quand vous entrez votre code hexadécimal, Intune détermine la couleur du texte qui fournit le plus haut niveau de contraste entre la couleur du texte et la couleur d’arrière-plan selon les [normes WCAG 2.0](http://www.w3.org/TR/WCAG20). Vous pouvez afficher un aperçu de la couleur du texte et du logo de votre société par rapport à la couleur dans **Applications mobiles** > **Portail d’entreprise**. 

### <a name="select-device-categories-by-using-the-access-work-or-school-settings----1058963---"></a>Sélectionnez les catégories d’appareils en utilisant les paramètres Accès scolaire ou professionnel <!-- 1058963 --> 
Si vous avez activé le [mappage de groupe d’appareils](https://docs.microsoft.com/en-us/intune/device-group-mapping), les utilisateurs de Windows 10 seront invités à sélectionner une catégorie d’appareils après l’inscription via le bouton **Se connecter** situé dans **Paramètres**  >  **Comptes** > **Accès scolaire ou professionnel** ou au cours de l'expérience OOBE (out-of-box experience).

### <a name="new-windows-defender-credential-guard-settings-added-to-endpoint-protection-settings---1102252---"></a>Nouveaux paramètres Windows Defender Credential Guard ajoutés aux paramètres Endpoint Protection <!--1102252 --> 

De nouveaux paramètres [Windows Defender Credential Guard](https://docs.microsoft.com/windows/access-protection/credential-guard/credential-guard] vont être ajoutés à **Configuration de l’appareil** > **Profils** > **Endpoint Protection**. Les paramètres suivants seront ajoutés : 

- Niveau de sécurité de plateforme : spécifiez si le niveau de sécurité de plateforme est activé lors du prochain redémarrage. La sécurité basée sur la virtualisation nécessite un démarrage sécurisé. La sécurité basée sur la virtualisation peut éventuellement être activée avec l’utilisation de protections d’accès direct à la mémoire (DMA). Les protections DMA nécessitent une prise en charge matérielle et ne seront activées que sur des appareils configurés correctement.
- Sécurité basée sur la virtualisation : spécifiez si la sécurité basée sur la virtualisation est activée lors du prochain redémarrage. 
- Windows Defender Credential Guard : activez Credential Guard avec la sécurité basée sur la virtualisation pour protéger les informations d’identification au prochain redémarrage quand le niveau de sécurité de plateforme avec un démarrage sécurisé et la sécurité basée sur la virtualisation sont tous deux activés. Les options disponibles sont notamment **Désactivé**, **Activé avec le verrouillage UEFI**, **Activé sans verrouillage** et **Non configuré**. 
  - L’option « Désactivé » désactive Credential Guard à distance s’il a été préalablement activé avec l’option « Activé sans verrouillage ».

  - L’option « Activé avec le verrouillage UEFI » garantit que Credential Guard ne peut pas être désactivé avec une clé de Registre ni en utilisant une stratégie de groupe. Pour désactiver Credential Guard après avoir utilisé ce paramètre, vous devez définir la stratégie de groupe sur « Désactivé » et supprimer la fonction de sécurité de chaque ordinateur, avec un utilisateur présent physiquement, afin d’effacer la configuration incluse dans UEFI. Tant que la configuration UEFI persiste, Credential Guard est activé.

  - L’option « Activé sans verrouillage » permet de désactiver Credential Guard à distance à l’aide d’une stratégie de groupe. Les appareils utilisant ce paramètre doivent exécuter au moins Windows 10 (version 1511).

  - L’option « Non configuré » laisse le paramètre de stratégie non défini. La stratégie de groupe n’écrit pas le paramètre de stratégie dans le Registre et il n’a donc pas d’impact sur les ordinateurs ou les utilisateurs. Si un paramètre existe dans le Registre, il n’est pas modifié.

### <a name="synchronize-and-deploy-sparsely-bundled-windows-store-for-business-apps---1222672---"></a>Synchroniser et déployer des applications du Windows Store pour Entreprises faiblement regroupées <!--1222672 -->
Les applications en mode hors connexion achetées auprès du Windows Store pour Entreprises seront synchronisées avec le portail Intune. Vous pouvez alors déployer ces applications sur des groupes d’utilisateurs ou d’appareils. Les applications en mode hors connexion sont installées par Intune et non par le Store.

### <a name="reset-passwords-for-android-o-devices----1238299---"></a>Réinitialiser les mots de passe pour les appareils Android O <!-- 1238299 -->
Vous serez en mesure de réinitialiser les mots de passe pour les appareils Android O inscrits. Quand vous envoyez une demande « Réinitialiser le mot de passe » à un appareil Android O, il définit un nouveau mot de passe de déverrouillage d’appareil ou une vérification de profil géré pour l’utilisateur actuel. Le mot de passe ou la vérification est envoyé selon si l’appareil a un propriétaire de profil ou un propriétaire d’appareil, et entre immédiatement en vigueur.

### <a name="local-device-security-option-settings----1251887---"></a>Paramètres d’option de sécurité d’appareil local <!-- 1251887 -->
Vous pourrez activer les paramètres de sécurité sur les appareils Windows 10 avec les nouveaux paramètres d’option de sécurité d’appareil local. Recherchez ces paramètres dans la catégorie Endpoint Protection quand vous créez une stratégie de configuration d’appareil Windows 10.

### <a name="new-printer-settings-for-education-profiles----1308900---"></a>Nouveaux paramètres d’imprimante pour les profils Éducation <!-- 1308900 -->

Pour les profils Éducation, de nouveaux paramètres seront disponibles sous la catégorie **Imprimantes** : **Imprimantes**, **Imprimante par défaut**, **Ajouter de nouvelles imprimantes**. 

### <a name="new-privacy-settings-for-device-restrictions---1308926---"></a>Nouveaux paramètres de confidentialité pour les restrictions de l’appareil <!--1308926 -->

Deux nouveaux paramètres de confidentialité seront disponibles pour les appareils :

- **Publier les activités de l’utilisateur** : affectez la valeur **Bloquer** pour empêcher les expériences partagées et la découverte des ressources récemment utilisées dans le sélecteur de tâches.

- **Activités locales uniquement** : affectez la valeur **Bloquer** pour empêcher les expériences partagées et la découverte des ressources récemment utilisées dans le sélecteur de tâches en fonction uniquement de l’activité locale.

### <a name="macos-company-portal-support-for-enrollments-that-use-the-device-enrollment-manager----1352411---"></a>Prise en charge du portail d’entreprise macOS pour les inscriptions qui utilisent le gestionnaire d’inscription d’appareil <!-- 1352411 -->

Les utilisateurs seront en mesure d’utiliser le gestionnaire d’inscription d’appareil lors de l’inscription auprès du portail d’entreprise macOS.

#### <a name="new-settings-for-the-edge-browser---1469166---"></a>Nouveaux paramètres pour le navigateur Edge <!--1469166 -->

Deux nouveaux paramètres seront disponibles pour les appareils avec le navigateur Edge : **Chemin vers le fichier de favoris** et **Modifications des favoris**. 

### <a name="windows-information-protection-wip-encrypted-data-in-windows-search-results----1469193---"></a>Données chiffrées Windows Information Protection (WIP) dans les résultats de la recherche Windows <!-- 1469193 -->

Un nouveau paramètre dans la stratégie Protection des informations Windows (WIP) vous permettra de choisir d’inclure les données chiffrées par WIP dans les résultats de la recherche Windows.

### <a name="line-of-business-lob-app-support-for-macos----1473977---"></a>Prise en charge des applications métier pour macOS <!-- 1473977 -->
Intune fournit la possibilité d’installer des applications métier macOS. Les applications métier sont des applications dans lesquelles vous fournissez le fichier d’installation et utilisez Intune pour installer l’application sur l’appareil. Dans le cadre de la prise en charge des applications métier macOS, vous devez utiliser l’outil de création de package de restrictions d’application Microsoft Intune pour macOS afin de prétraiter les applications métier macOS.

### <a name="configure-resource-account-settings-for-surface-hubs----1475674---"></a>Configurer les paramètres de compte de ressource pour les appareils Surface Hub <!-- 1475674 -->

Vous serez en mesure de configurer à distance les paramètres de compte de ressource pour les appareils Surface Hub.

Le compte de ressource est utilisé par un appareil Surface Hub pour l’authentification sur Skype/Exchange afin de prendre part à une réunion. Vous pouvez créer un compte de ressource unique afin que l’appareil Surface Hub puisse s’afficher dans la réunion en tant que salle de conférence, par exemple un compte de ressource tel que **Salle de conférence B41/6233**.

> [!NOTE]
> - Si vous laissez les champs vides, vous allez remplacer les attributs précédemment configurés sur l’appareil.
>
> - Les propriétés de compte de ressource peuvent changer dynamiquement sur l’appareil Surface Hub, par exemple si la rotation de mot de passe est activée. Par conséquent, il est possible que les valeurs dans la console Azure prennent un certain temps avant de refléter la réalité sur l’appareil. 
>
>   Pour comprendre ce qui est actuellement configuré sur l’appareil Surface Hub, les informations de compte de ressource peuvent être incluses dans l’inventaire matériel (qui dispose déjà d’un intervalle de 7 jours) ou en tant que propriétés en lecture seule. Pour améliorer la précision une fois que l’action à distance a eu lieu, vous pouvez obtenir l’état des paramètres immédiatement après l’exécution de l’action pour mettre à jour les paramètres/le compte sur l’appareil Surface Hub.

### <a name="ios-app-provisioning-configuration----1581650---"></a>Configuration du provisionnement des applications iOS <!-- 1581650 -->
Vous serez en mesure d’assigner des profils de provisionnement des applications iOS pour empêcher vos applications d’arriver à expiration en incluant ou excluant des groupes de sécurité.

### <a name="new-windows-defender-exploit-guard-settings----631893---"></a>Nouveaux paramètres Windows Defender Exploit Guard <!-- 631893 -->

Six nouveaux paramètres de **réduction de la surface d’attaque** et fonctionnalités développées **d’accès contrôlé aux dossiers : Protection des dossiers** seront disponibles. Ces paramètres se trouvent dans : Configuration de l’appareil\Profils\
Créez profil\Endpoint Protection\Windows Defender Exploit Guard.

#### <a name="attack-surface-reduction"></a>Règles de réduction de la surface d’attaque

|Nom du paramètre  |Options du paramètre  |Description  |
|---------|---------|---------|
|Protection avancée contre les ransomware|Activé, Auditer, Non configuré|Utiliser une protection agressive contre les ransomware.|
|Marquer le vol des informations d’identification du sous-système de l’autorité de sécurité locale Windows|Activé, Auditer, Non configuré|Marquer le vol des informations d’identification du sous-système de l’autorité de sécurité locale Windows (lsass.exe).|
|Création de processus à partir des commandes PSExec et WMI|Bloquer, Auditer, Non configuré|Bloquer les créations de processus issues des commandes PSExec et WMI.|
|Processus non approuvés et non signés exécutés à partir d’USB|Bloquer, Auditer, Non configuré|Bloquer les processus non approuvés et non signés exécutés à partir d’USB.|
|Fichiers exécutables qui ne répondent pas à des critères de prédominance, d’âge ou de liste approuvée|Bloquer, Auditer, Non configuré|Bloquer l’exécution des fichiers exécutables sauf s’ils répondent à des critères de prédominance, d’âge ou de liste approuvée.|

#### <a name="controlled-folder-access"></a>Accès contrôlé aux dossiers

|Nom du paramètre  |Options du paramètre  |Description  |
|---------|---------|---------|
|Protection des dossiers (déjà implémenté)|Non configuré, Activer, Auditer uniquement (déjà implémentées)<br><br> **Nouveau**<br>Bloquer la modification du disque, Auditer la modification du disque|
Protéger les fichiers et les dossiers contre les modifications non autorisées par des applications hostiles.<br><br>**Activer** : Empêcher les applications non approuvées de modifier ou supprimer des fichiers dans des dossiers protégés et d’écrire dans des secteurs de disque.<br><br>
**Bloquer la modification du disque uniquement** :<br>Empêcher les applications non approuvées d’écrire dans des secteurs de disque. Les applications non approuvées peuvent toujours modifier ou supprimer des fichiers dans des dossiers protégés.

### <a name="new-windows-defender-application-guard-settings----1631890---"></a>Nouveaux paramètres Windows Defender Application Guard <!-- 1631890 -->

- **Activer l’accélération graphique**

Les administrateurs pourront activer un processeur graphique virtuel pour Windows Defender Application Guard. Ce paramètre permet à l’UC de décharger l’affichage graphique sur l’unité de traitement graphique virtuelle. Cela peut améliorer les performances quand vous utilisez des sites web qui consomment beaucoup de graphiques ou regardez une vidéo au sein du conteneur.

- **SaveFilestoHost**

Les administrateurs pourront activer les fichiers à transférer de Microsoft Edge en cours d’exécution dans le conteneur au système de fichiers hôte. L’activation de ce paramètre permet aux utilisateurs de télécharger des fichiers à partir de Microsoft Edge dans le conteneur sur le système de fichiers hôte.

### <a name="see-enrollment-restrictions-per-user----1634444---"></a>Afficher les restrictions d’inscription par utilisateur <!-- 1634444 -->
Dans le panneau de résolution des problèmes, vous serez en mesure d’afficher les restrictions d’inscription qui sont en vigueur pour chaque utilisateur.

### <a name="configuring-a-self-updating-mobile-msi-app----1740840---"></a>Configuration d’une application MSI mobile avec mise à jour automatique <!-- 1740840 -->
Vous serez en mesure de configurer une application MSI mobile avec mise à jour automatique connue pour ignorer le processus de vérification de version. Cette fonctionnalité est utile pour éviter d’introduire une condition de concurrence. Par exemple, cela peut se produire quand l’application est mise à jour automatiquement par le développeur de l’application et aussi par Intune. Les deux pourraient essayer d’appliquer une version de l’application sur le client Windows et déclencher ainsi un conflit.

### <a name="additions-to-system-security-settings-for-windows-10-and-later-compliance-policies---1704133---"></a>Ajouts aux paramètres de sécurité du système pour les stratégies de conformité Windows 10 et versions ultérieures <!--1704133 -->

Des ajouts aux paramètres de conformité Windows 10 seront disponibles, dont le pare-feu obligatoire et l’antivirus Windows Defender.

### <a name="including-and-excluding-app-assignment-based-on-groups-for-android-enterprise----1813081---"></a>Inclusion et exclusion d’affectations d’applications en fonction de groupes pour Android Enterprise <!-- 1813081 -->
Lors des affectations d’applications et après avoir sélectionné un type d’affectation, Android Enterprise (anciennement Android for Work) prend en charge la fonctionnalité d’exclusion.


### <a name="related-sets-of-app-licenses-supported-in-intune----1864117---"></a>Jeux liés de licences d’application pris en charge dans Intune <!-- 1864117 -->
Intune dans le portail Azure prend en charge les jeux liés de licences d’application comme élément d’application unique dans l’interface utilisateur. En outre, toutes les applications sous licence en mode hors connexion synchronisées à partir de Microsoft Store pour Entreprises seront consolidées dans une entrée d’application unique et les détails du déploiement des packages individuels seront migrés sur l’entrée unique. Pour afficher les jeux liés de licences d’application dans le portail Azure, sélectionnez **Licences d’application** dans le panneau **Applications mobiles**.

<!-- the following are present prior to 1802 -->

### <a name="new-option-for-user-authentication-for-apple-bulk-enrollment----747625---"></a>Nouvelle option pour l’authentification utilisateur dans le cadre de l’inscription en bloc Apple <!-- 747625 -->
Intune vous donnera la possibilité d’authentifier les appareils à l’aide de l’application Portail d’entreprise pour les méthodes d’inscription suivantes :

- Programme d'inscription d'appareils Apple
- Apple School Manager
- Inscription à Apple Configurator

Lorsque vous utilisez l’option Portail d’entreprise, l’authentification multifacteur Azure Active Directory peut être appliquée sans bloquer ces méthodes d’inscription.

Lorsque vous utilisez l’option Portail d’entreprise, Intune ignore l’authentification utilisateur dans l’Assistant Réglages iOS pour l’inscription d’affinité utilisateur. Cela signifie que l’appareil est initialement inscrit comme appareil sans utilisateur et, par conséquent, vous ne recevrez pas les configurations ou stratégies des groupes d’utilisateurs. Il recevra uniquement les configurations et les stratégies des groupes d’appareils. Toutefois, Intune installera automatiquement l’application Portail d’entreprise sur l’appareil. Le premier utilisateur à lancer l’application Portail d’entreprise et à s’y connecter sera associé à l’appareil dans Intune. À ce stade, l’utilisateur recevra les configurations et les stratégies de ses groupes d’utilisateurs. L’association de l’utilisateur ne peut pas être modifiée sans réinscription.

### <a name="intune-support-for-multiple-apple-dep--apple-school-manager-accounts----747685---"></a>Prise en charge d’Intune pour plusieurs comptes DEP / Apple School Manager <!-- 747685 -->
Intune prendra en charge l’inscription des appareils jusqu'à la limite de 100 comptes dans le cadre du Programme d’inscription des appareils (DEP) ou Apple School Manager. Chaque jeton téléchargé peut être géré séparément pour les profils d’inscription et les appareils. Un profil d’inscription différent peut être affecté automatiquement pour chaque jeton DEP/School Manager téléchargé. Si plusieurs jetons School Manager sont téléchargés, un seul jeton peut être partagé avec Microsoft School Data Sync à la fois.

Après la migration, les API Graph en version bêta et les scripts publiés pour la gestion DEP Apple ou ASM via Graph ne fonctionneront plus. De nouvelles versions bêta des API Graph sont en cours de développement et seront publiées après la migration.

### <a name="select-device-categories-by-using-the-access-work-or-school-settings----1058963---"></a>Sélectionnez les catégories d’appareils en utilisant les paramètres Accès scolaire ou professionnel <!-- 1058963 -->
Si vous avez activé le [mappage de groupe d’appareils](https://docs.microsoft.com/en-us/intune/device-group-mapping), les utilisateurs de Windows 10 seront invités à sélectionner une catégorie d’appareils après l’inscription via le bouton **Se connecter** situé dans **Paramètres**  >  **Comptes** > **Accès scolaire ou professionnel** ou au cours de l'expérience OOBE (out-of-box experience).

### <a name="targeting-compliance-policies-to-devices-in-device-groups---1307012---"></a>Ciblage des stratégies de conformité pour les appareils dans des groupes d’appareils <!--1307012 -->

Vous pourrez cibler des stratégies de conformité pour les utilisateurs dans des groupes d’utilisateurs. Vous pourrez cibler des stratégies de conformité pour les appareils dans des groupes d’appareils.

### <a name="including-and-excluding-app-assignment-based-on-groups----1406920---"></a>Inclusion et exclusion d’affectations d’applications en fonction de groupes <!-- 1406920 -->

Lors de l’affectation d’une application et après avoir sélectionné un type d’affectation, vous pourrez sélectionner les groupes à inclure ainsi que les groupes à exclure.

### <a name="remote-erase-command-support----1438084---"></a>Prise en charge de la commande d’effacement à distance <!-- 1438084 -->

Les administrateurs pourront déclencher une commande d’effacement à distance.

> [!IMPORTANT]
> La commande d’effacement ne peut pas être annulée et doit être utilisée avec précaution.

La commande d’effacement supprime toutes les données, y compris le système d’exploitation, d’un appareil. Elle entraîne aussi la suppression de l'appareil de la gestion Intune. Aucun avertissement n’est envoyé à l’utilisateur, et l’effacement se produit dès l’envoi de la commande.

Vous pourrez configurer un code PIN de récupération à 6 chiffres. Ce code PIN peut servir à déverrouiller l’appareil effacé avant de lancer la réinstallation du système d’exploitation. Une fois que l’effacement a démarré, le code PIN apparaît dans une barre d’état sur le panneau de présentation de l’appareil dans Intune. Le code PIN restera affiché tant que l’effacement est en cours. Une fois l’effacement terminé, l’appareil disparaît totalement de la gestion Intune. Veillez à enregistrer le code PIN de récupération afin que toute personne qui restaure l’appareil puisse l’utiliser.

### <a name="windows-information-protection-wip-encrypted-data-in-windows-search-results----1469193---"></a>Données chiffrées Windows Information Protection (WIP) dans les résultats de la recherche Windows <!-- 1469193 -->

Un nouveau paramètre dans la stratégie Protection des informations Windows (WIP) vous permettra de choisir d’inclure les données chiffrées par WIP dans les résultats de la recherche Windows.

### <a name="website-learning-mode----1631908---"></a>Mode d’apprentissage de site web (Website Learning Mode) <!-- 1631908 -->

Intune proposera une extension du mode d’apprentissage de la Protection des informations Windows (WIP). Outre l’affichage des informations sur les applications compatibles avec WIP, vous pourrez consulter un résumé des appareils qui partagent des données de travail avec des sites web. Ces informations vous permettront d’identifier les sites web à ajouter aux stratégies WIP des utilisateurs et des groupes.

### <a name="updates-to-compliance-emails---1637547---"></a>Mises à jour des e-mails de conformité <!--1637547 -->

Lorsqu’un e-mail est envoyé pour signaler un appareil non conforme, d’autres d’informations sur cet appareil non conforme seront incluses. L’article suivant sera mis à jour pour indiquer ce point : [Automatiser des actions en cas de non-conformité](#actions-for-noncompliance).

###  <a name="alerts-for-expired-tokens-and-tokens-that-will-soon-expire----1639263---"></a>Alertes pour les jetons expirés et les jetons qui arrivent à expiration <!-- 1639263 -->
La page de présentation affichera des alertes pour les jetons expirés et ceux qui arrivent à expiration. Lorsque vous cliquez sur une alerte pour un jeton unique, vous accéderez à la page des détails de ce jeton.  Si vous cliquez sur une alerte comportant plusieurs jetons, vous accéderez à une liste de tous les jetons avec leur état. Les administrateurs doivent renouveler leurs jetons avant la date d’expiration.

### <a name="remote-printing-over-a-secure-network----1709994----"></a>Impression à distance sur un réseau sécurisé <!-- 1709994  -->
Les solutions d’impression mobiles sans fil PrinterOn permettront aux utilisateurs d’imprimer à distance depuis n’importe où et à tout moment via un réseau sécurisé. PrinterOn s’intégrera au Kit SDK APP d’Intune à la fois pour iOS et Android. Vous pourrez cibler les stratégies de protection d’application pour cette application via le panneau des **stratégies de protection d’application** d’Intune, dans la console d’administration. Les utilisateurs finaux pourront télécharger l’application « PrinterOn for Microsoft » via le Google Play Store ou iTunes afin de l’utiliser dans leur écosystème Intune.

### <a name="approve-the-company-portal-app-for-android-for-work---1797090---"></a>Approuver l’application Portail d’entreprise pour Android for Work <!--1797090 -->
Si votre organisation utilise Android for Work, vous devrez approuver manuellement l’application Portail d’entreprise pour Android afin qu’elle continue à recevoir les mises à jour automatiques du magasin Google Play managé.

### <a name="faceid-on-ios-devices----1807377---"></a>FaceID sur les appareils iOS <!-- 1807377 -->
Les stratégies de protection des applications Intune prennent désormais en charge un paramètre qui gère FaceID sur les appareils iOS. Ce paramètre est destiné aux appareils qui prennent en charge la fonctionnalité FaceID (uniquement l’iPhone X pour l’instant). Ce paramètre est indépendant des contrôles TouchID actuellement pris en charge. Les organisations ont la possibilité de choisir FaceID comme code PIN valide en remplacement des commandes TouchID.

### <a name="microsoft-graph-api-for-intune---general-availability-----1833289---"></a>API Graph Microsoft pour Intune - disponibilité générale <!-- 1833289 -->
Les API Intune dans Microsoft Graph fourniront un accès par programme aux données et méthodes pour automatiser les actions d’administration du service Intune.  Avec la **disponibilité générale** de ces API, clients, partenaires et développeurs pourront utiliser les API pour intégrer des solutions internes ou commerciales liées à ou nécessitant la prise en charge d’Intune ou d’autres services Microsoft disponibles via Microsoft Graph.

<!-- the following are present prior to 1801 -->

### <a name="app-protection-policies-----679615---"></a>Stratégies de protection des applications  <!-- 679615 -->
Les stratégies Intune App Protection permettent de créer des stratégies globales, par défaut, afin d’activer rapidement la protection pour tous les utilisateurs dans l’ensemble du locataire.

### <a name="revoking-ios-volume-purchase-program-apps-----820863---"></a>Révocation des applications du Programme d’achat en volume iOS  <!-- 820863 -->
Pour un appareil donné disposant d’une ou de plusieurs applications de Programme d’achat en volume (VPP) iOS, vous pourrez révoquer la licence d’application basée sur l’appareil associé. La révocation d’une licence d’application ne désinstalle pas l’application VPP de l’appareil. Pour désinstaller une application VPP, vous devez remplacer l’action d’attribution par **Désinstaller**. Pour plus d’informations, consultez [Guide pratique pour gérer les applications iOS achetées par le biais d’un programme d’achat en volume avec Microsoft Intune](vpp-apps-ios.md).

### <a name="revoke-licenses-for-an-ios-volume-purchasing-program-token----820870---"></a>Révoquer des licences pour un jeton Programme d’achat en volume iOS <!-- 820870 -->
Vous pourrez révoquer la licence de toutes les applications de Programme d’achat en volume (VPP) iOS pour un jeton VPP donné.

### <a name="new-ios-device-action------1244701---"></a>Nouvelle action sur appareil iOS   <!-- 1244701 -->
Vous pouvez arrêter les appareils supervisés iOS 10.3. Cette action arrête immédiatement l’appareil sans avertir l’utilisateur final. L’action **Arrêter (supervisé uniquement)** se trouve dans les propriétés de l’appareil lorsque vous sélectionnez un appareil dans la charge de travail **Appareil**.

### <a name="intune-provides-the-account-move-operation-----1573558-1579830---"></a>Intune propose l’opération Déplacer le compte <!-- 1573558, 1579830 -->
L’opération **Déplacer le compte** migre un locataire à partir d’une échelle d’unité Azure (ASU) vers une autre. L’opération **Déplacer le compte** peut être utilisée dans les scénarios initiés par le client, lorsque vous faites la demande de cette opération auprès de l’équipe de support d’Intune, et elle peut être utilisée dans un scénario géré par Microsoft lorsque Microsoft doit apporter des réglages au service dans le serveur principal. Au cours de l’opération **Déplacer le compte**, les locataires sont en mode lecture seule. Durant la période où les locataires sont en lecture seule, les opérations de service comme l’inscription, le changement de nom des appareils, la mise à jour de l’état de conformité, échoueront.



<!-- the following are present prior to 1712 -->
### <a name="assign-office-365-mobile-apps-to-ios-and-android-devices-using-built-in-app-type----1332318---"></a>Affecter des applications mobiles Office 365 aux appareils iOS et Android à l’aide du type d’application intégré <!-- 1332318 -->
Le type d’application **Intégré** facilitera la création d’applications Office 365 et leur affectation aux appareils iOS et Android gérés. Ces applications incluent les applications Office 365 telles que Word, Excel, PowerPoint et OneDrive. Vous pouvez affecter des applications spécifiques au type d’application et modifier la configuration des informations des applications.

### <a name="assignment-conflict-resolution-has-changed-for-ios-store-apps----1480316---"></a>La résolution des conflits d’affectation a changé pour les applications de l’App Store iOS <!-- 1480316 -->
Les utilisateurs finaux pourront constater une évolution de la disponibilité des applications de l’App Store iOS. Actuellement, une application qui a été attribuée à deux groupes et présentant un conflit entre **Obligatoire et disponible** et **Non applicable** se résout en **Obligatoire et disponible**. Avec ce changement, une application qui rencontre ce conflit se résout en **Non applicable**.

Ce changement met fin à la confusion liée à l’attribution d’une application à plusieurs groupes avec des intentions d’application différentes.

Si vous souhaitez que votre application soit disponible dans le portail des travailleurs de l’information et dans le portail d’entreprise avant la publication de service de novembre, vous avez deux options :

1. Supprimer l’affectation **Non applicable** pour votre groupe.
2. Créer un groupe qui n’inclut pas de membres auxquels est affectée l’intention **Obligatoire et disponible** et assigner ce groupe en tant que **Non applicable**.

Pour plus d’informations, consultez [Guide pratique pour attribuer des applications à des groupes avec Microsoft Intune](apps-deploy.md).

> [!Note]
> Après la publication, vous ne pouvez plus afficher ou modifier les affectations d’applications MDM avec la console Intune classique. Toutefois, vous pouvez utiliser la console Azure ou l’API Graph Intune pour effectuer vos affectations d’applications.

### <a name="configure-an-ios-app-pin----1586774---"></a>Configurer un code PIN d’application iOS <!-- 1586774 -->
Vous pourrez bientôt exiger un code PIN pour des applications iOS ciblées. Vous pouvez configurer l’exigence du code PIN et sa date d’expiration en jours par le biais du portail Azure. Le cas échéant, l’utilisateur devra définir et utiliser un nouveau code PIN avant d’accéder à une application iOS. Seules les applications iOS pour lesquelles la protection d’application est activée avec le SDK d’application Intune prendront en charge cette fonctionnalité.

### <a name="user-experience-update-for-the-company-portal-app-for-ios---1412866--"></a>Mise à jour de l’expérience utilisateur dans l’application Portail d’entreprise pour iOS <!--1412866-->

Nous publierons une mise à jour importante de l’expérience utilisateur dans l’application Portail d’entreprise pour iOS. La mise à jour présentera une toute nouvelle apparence, plus moderne, avec une amélioration de l’accessibilité et de l’utilisation. Toutes les fonctionnalités actuelles de l’application Portail d’entreprise pour iOS seront conservées.

Nous vous offrons une préversion de l’application Portail d’entreprise pour iOS mise à jour via le programme Apple TestFlight pour que vous l’utilisiez et nous fassiez part de vos commentaires. Inscrivez-vous à l’adresse https://aka.ms/intune_ios_cp_testflight pour accéder à TestFlight. 

![images d’annonce de la nouvelle application Portail d’entreprise pour iOS](./media/ios-cp-app-redesign-1801-teaser.png)

<!-- the following are present prior to 1711 -->

### <a name="azure-active-directory-web-sites-can-require-the-intune-managed-browser-app-and-support-single-sign-on-for-the-managed-browser-public-preview----710595---"></a>Les sites web Azure Active Directory peuvent nécessiter l’application Intune Managed Browser et la prise en charge de l’authentification unique pour Managed Browser (Préversion publique) <!-- 710595 -->   
Avec Azure Active Directory (Azure AD), vous pouvez restreindre l’accès aux sites web sur des appareils mobiles à l’application Intune Managed Browser. Dans Managed Browser, les données de site web restent sécurisées et séparées des données personnelles de l’utilisateur final. Par ailleurs, Managed Browser prend en charge les fonctionnalités d’authentification unique pour les sites protégés par Azure AD. Si vous vous connectez à Managed Browser ou que vous utilisez Managed Browser sur un appareil avec une autre application gérée par Intune, Managed Browser peut accéder aux sites d’entreprise protégés par Azure AD sans que l’utilisateur ne doive entrer ses informations d’identification. Cette fonctionnalité s’applique aux sites comme Outlook Web Access (OWA) et SharePoint Online, ainsi qu’à d’autres sites d’entreprise tels que les ressources intranet accessibles par le proxy de l’application Azure.

<!-- the following are present prior to 1711 -->

### <a name="redirecting-macos-users-to-our-new-company-portal-app---1380728--"></a>Redirection des utilisateurs macOS vers notre nouvelle application Portail d’entreprise<!--1380728-->   
Lorsqu’un utilisateur final se connecte au site web du portail d’entreprise pour inscrire son appareil macOS, il est invité à télécharger la nouvelle application Portail d’entreprise pour macOS pour effectuer la procédure. Ce comportement se produit pour les appareils macOS avec OS X El Capitan 10.11 ou ultérieur. 


<!-- the following are present prior to 1709 -->

### <a name="intune-managed-browser-support-for-ios-and-android----1374196---"></a>Prise en charge d’Intune Managed Browser pour iOS et Android <!-- 1374196 -->
À compter d’octobre 2017, l’application Intune Managed Browser sur l’application Android prendra en charge seulement les appareils exécutant Android 4.4 et ultérieur. L’application Intune Managed Browser sur iOS prendra en charge seulement les appareils exécutant iOS 9.0 et ultérieur. Les versions antérieures d’Android et d’iOS pourront encore utiliser Managed Browser, mais elles ne pourront pas installer les nouvelles versions de l’application et n’auront peut-être pas accès à toutes les fonctionnalités. Nous vous encourageons à mettre à jour le système d’exploitation de ces appareils avec une version prise en charge.

### <a name="improved-error-message-for-when-a-user-reaches-the-maximum-number-of-devices-allowed-to-enroll----1270370---"></a>Message d’erreur amélioré quand un utilisateur atteint le nombre maximal d’appareils autorisés à inscrire <!-- 1270370 -->
Au lieu d’un message d’erreur générique, les utilisateurs finaux d’appareils Android reçoivent un message d’erreur convivial offrant une possibilité d’action : « Vous avez inscrit le nombre maximal d’appareils autorisés par votre administrateur informatique. Supprimez un appareil inscrit ou demandez de l’aide à votre administrateur informatique ».



## <a name="notices"></a>Remarques

Il n’existe aucun avis actif pour l’instant.



### <a name="see-also"></a>Voir aussi
Voir [Nouveautés de Microsoft Intune](whats-new.md) pour en savoir plus sur les derniers développements.


