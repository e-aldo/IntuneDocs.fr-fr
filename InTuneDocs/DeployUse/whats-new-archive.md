---
title: "Archive des nouveautés | Microsoft Intune"
description: 
keywords: 
author: Lindavr
manager: angrobe
ms.date: 07/18/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ed2db991-4729-49a7-a1e6-be2ffa0d03d1
ROBOTS: noindex,nofollow
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 300df17fd5844589a1e81552d2d590aee5615897
ms.openlocfilehash: 458ee268d0c6a8fa6cbe6cc23ad07f0e45eff3e5


---
## Décembre 2015
### Modifications et mises à jour du portail d’entreprise Microsoft
Les modifications suivantes ont été apportées au portail d’entreprise dans cette version.

**Application Portail d’entreprise Android**

Les modifications suivantes ont été apportées pour se conformer aux nouvelles exigences de Google. Sur les appareils Android 6.0 et versions ultérieures, deux nouveaux messages sont présentés aux utilisateurs :
* Autoriser l’application Portail d’entreprise à passer et gérer des appels téléphoniques ?
* Autoriser l’application Portail d’entreprise à accéder aux photos, aux fichiers multimédias et aux fichiers de votre appareil ?

Pour plus d’informations sur ces deux messages, consultez les tableaux suivants.



Texte du message  |Autoriser l’application Portail d’entreprise à passer et gérer des appels téléphoniques ?  
---------|---------
Signification du message     |  Permet d’envoyer le numéro IMEI et le numéro de téléphone de l’appareil de l’utilisateur au service Intune et de les afficher dans la console d’administration sur la page Matériel.   </br></br>**REMARQUE : L’application Portail d’entreprise ne passe et ne gère jamais d’appels téléphoniques !** Le texte du message est contrôlé par Google et ne peut pas être modifié. </br></br>Pour afficher la page **Matériel**, accédez à **Groupes** > **Tous les appareils mobiles** > **Appareils**. Sélectionnez l’appareil de l’utilisateur et accédez à **Afficher les propriétés** > **Matériel**.    
Où et quand le message s’affiche  | Le message s’affiche quand les utilisateurs se connectent à l’application Portail d’entreprise pour la première fois pour inscrire leur appareil.|         
Ce qui se passe si les utilisateurs autorisent l’accès  |  Le numéro IMEI et le numéro de téléphone de l’appareil s’affichent dans la console d’administration de la page Matériel. |         
Ce qui se passe si les utilisateurs refusent l’accès     | Ils peuvent continuer à utiliser l’application Portail d’entreprise et inscrire leur appareil, mais le numéro IMEI et le numéro de téléphone de l’appareil de l’utilisateur sont vides dans la console d’administration de la page Matériel.       </br></br> La deuxième fois que les utilisateurs se connectent à l’application Portail d’entreprise après le refus de l’accès, le message affiche une case **Ne plus me demander** que les utilisateurs peuvent cocher pour que le message ne s’affiche plus.</br></br>Si les utilisateurs autorisent, puis refusent par la suite l’accès, le message s’affiche la prochaine fois qu’ils se connectent à l’application Portail d’entreprise après l’inscription.</br></br>Si les utilisateurs décident par la suite d’autoriser l’accès, ils peuvent accéder à **Paramètres** > **Applications** > **Portail d’entreprise** > **Autorisations** > **Téléphone**, puis activer l’autorisation.
Plus d'informations     |  Pour vos utilisateurs : [Se connecter à l’application Portail d’entreprise](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_signin_cp)  </br></br>Pour les professionnels de l’informatique : Les informations présentes dans ce tableau figurent également dans [Description des messages de l’application Portail d’entreprise pour vos utilisateurs](https://technet.microsoft.com/library/dn948527.aspx#BKMK_help_users_understd_msgs)   

Texte du message  |Autoriser l’application Portail d’entreprise à accéder aux photos, aux fichiers multimédias et aux fichiers de votre appareil ?  
---------|---------
Signification du message     |  Permet à l’appareil d’écrire des journaux de données sur la carte SD, et donc de déplacer les journaux à l’aide d’un câble USB.   </br></br>**REMARQUE : L’application Portail d’entreprise n’accède jamais aux photos, aux fichiers multimédias ou aux fichiers des utilisateurs.** Le texte du message est contrôlé par Google et ne peut pas être modifié.     
Où et quand le message s’affiche  | Le message s’affiche quand les utilisateurs appuient sur **Envoyer les données** pour envoyer les journaux de données à leur administrateur informatique.|         
Ce qui se passe si les utilisateurs autorisent l’accès  |  Les journaux sont copiés sur la carte SD. |         
Ce qui se passe si les utilisateurs refusent l’accès     | Ils peuvent toujours envoyer les journaux de données, mais les journaux ne sont pas copiés sur la carte SD de l’appareil.       </br></br> La deuxième fois que les utilisateurs se connectent à l’application Portail d’entreprise après le refus de l’accès, le message affiche une case **Ne plus me demander** que les utilisateurs peuvent cocher pour que le message ne s’affiche plus.</br></br>Si les utilisateurs autorisent, puis refusent par la suite l’accès, le message s’affiche la prochaine fois qu’ils essaient d’envoyer les journaux.</br></br>Si les utilisateurs décident par la suite d’autoriser l’accès, ils peuvent accéder à **Paramètres** > **Applications** > **Portail d’entreprise** > **Autorisations** > **Stockage**, puis activer l’autorisation.
Plus d'informations     |  Pour vos utilisateurs : [Envoyer des journaux de données de diagnostic à votre administrateur informatique par e-mail](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_send_diag_logs)  </br></br>Pour les professionnels de l’informatique : Les informations présentes dans ce tableau figurent également dans [Description des messages de l’application Portail d’entreprise pour vos utilisateurs](https://technet.microsoft.com/library/dn948527.aspx#BKMK_help_users_understd_msgs)   


**Application Portail d’entreprise iOS**
* Les utilisateurs peuvent désormais utiliser Microsoft Outlook ou d’autres applications de messagerie pour envoyer les journaux de diagnostic à l’administrateur informatique. Avant, seule l’application native pouvait être utilisée.
* La prise en charge a été améliorée pour le programme d’inscription d’appareil (DEP) d’Apple et les appareils inscrits de l’entreprise. Pour plus d’informations, consultez [Vous êtes invité à identifier votre appareil quand vous essayez de l’inscrire](https://technet.microsoft.com/library/mt598622.aspx#BKMK_ios_id_your_device).
* Dans la liste des appareils inscrits de l’utilisateur, une coche verte s’affiche désormais en regard de l’appareil que l’utilisateur est en train d’utiliser. Avant l’ajout de cette coche, les utilisateurs ne pouvaient pas savoir quel appareil inscrit ils utilisaient.

**Application Portail d’entreprise Windows**

Microsoft recueille automatiquement des données anonymes sur les performances et l'utilisation du portail d'entreprise pour améliorer les produits et services Microsoft. Les utilisateurs finaux peuvent désactiver la collecte de données à l'aide du paramètre Données d'utilisation sur leur appareil, mais les administrateurs n'ont aucun contrôle sur la collecte de données et ne peuvent pas changer la sélection de l'utilisateur final pour ce paramètre.



## Novembre 2015
### Gestion d'applications
Intune prend en charge les stratégies de gestion des applications mobiles (MAM) qui aident à empêcher la divulgation des données d’entreprise aux applications ou services consommateurs. Auparavant, ces stratégies s’appliquaient uniquement aux applications mobiles exécutées sur des appareils qui étaient également inscrits pour la gestion des appareils mobiles dans Intune.

Avec la mise à jour de ce mois-ci, Intune étend ses fonctionnalités MAM à de nouvelles classes d’appareils. En plus des appareils inscrits dans Intune, vous pouvez appliquer les stratégies MAM :
* Aux appareils gérés par toute autre solution de gestion des appareils mobiles.
* Aux appareils qui ne sont inscrits dans aucun système de gestion des appareils mobiles (généralement des appareils BYOD).

Vous trouverez plus d’informations sur ces nouvelles fonctionnalités MAM dans les billets de blog suivants :
* [Enhancing managed mobile productivity](http://blogs.technet.com/b/microsoftintune/archive/2015/11/17/enhancing-managed-mobile-productivity.aspx)
* [Announcing new Microsoft Enterprise Mobility capabilities](http://blogs.technet.com/b/microsoftintune/archive/2015/11/17/enhancing-managed-mobile-productivity.aspx)

Voici quelques points importants et informations supplémentaires sur les fonctionnalités MAM d’Intune :
* Les données d’entreprise sont isolées des données des clients dans les applications compatibles avec Intune, notamment les applications Office Mobile, les applications tierces qui ont adopté le SDK Intune ou les applications métier encapsulées par Intune.
* Les données d’entreprise peuvent être partagées (**Couper/Copier/Coller**) entre les applications d’entreprise, tout en empêchant leur partage dans des applications personnelles. Pour plus d’informations, consultez [Comment les stratégies de gestion des applications mobiles protègent les données d’application](https://technet.microsoft.com/library/mt627825.aspx) . Cet exemple de scénario, [Utiliser l’application Microsoft Word pour des tâches personnelles et professionnelles](https://technet.microsoft.com/library/mt627827.aspx), montre comment empêcher le partage des données d’entreprise dans des applications personnelles.
* Stratégies de prévention de perte des données clés, telles que les codes confidentiels propres aux applications, les contrôles Enregistrer sous et le partage des données managées entre les applications. Pour obtenir une liste de toutes les stratégies, consultez [Créer et déployer des stratégies de gestion des applications mobiles à l’aide de Microsoft Intune](https://technet.microsoft.com/library/mt627829.aspx).
* Les applications Word, Excel, PowerPoint, Outlook, OneNote et OneDrive Entreprise offrent toutes ces nouvelles fonctionnalités et peuvent être gérées avec ou sans l’inscription d’appareils. Les fonctionnalités de protection contre la perte de données sont intégrées de manière native aux applications Office standard dans l’Apple Store ou le Google Play Store, et ne nécessitent pas de création de package de restrictions d’application ni de chargement indépendant.
* Pour plus d’informations, consultez [Prise en main des stratégies de gestion des applications mobiles dans le portail Azure](https://technet.microsoft.com/library/mt627830.aspx). Pour découvrir comment configurer et déployer des stratégies de gestion des applications mobiles, consultez [Créer et déployer des stratégies de gestion des applications mobiles à l’aide de Microsoft Intune](https://technet.microsoft.com/library/mt627829.aspx).
* Quand les utilisateurs s’authentifient auprès de l’application avec leurs informations d’identification d’entreprise, les fonctionnalités de protection contre la perte de données sont configurées automatiquement. La rubrique [Expérience utilisateur pour les applications associées aux stratégies de gestion des applications mobiles Microsoft Intune](https://technet.microsoft.com/library/mt627827.aspx) contient des exemples de scénarios pour l’accès à OneDrive sur des appareils iOS et Android.
* Fonctionne sur les appareils iOS et Android.

La liste des [Applications Microsoft utilisables avec les stratégies de gestion des applications mobiles de Microsoft Intune](https://technet.microsoft.com/library/dn708489.aspx) a été mise à jour et contient les dernières applications.

### Gestion des appareils
 **Gestion des appareils Mac OS X** Vous pouvez maintenant inscrire et gérer des appareils Mac OS X avec Intune. Vous pouvez effectuer les opérations suivantes avec vos appareils Mac OS X :
* Inscrire des appareils pour qu’ils soient gérés par Intune. Consultez [Configurer la gestion iOS et MAC avec Microsoft Intune](https://technet.microsoft.com/library/dn408185.aspx).
* Contrôler les paramètres des appareils avec une stratégie de configuration générale. Consultez [Paramètres de la stratégie de configuration Mac OS X dans Microsoft Intune](https://technet.microsoft.com/library/mt627823.aspx).
* Déployer des paramètres Mac OS X que vous avez créés avec l’outil Apple Configurator. Consultez [Paramètres de la stratégie personnalisée Mac OS X dans Microsoft Intune](https://technet.microsoft.com/library/mt627820.aspx).
* Recueillir l’inventaire matériel et logiciel à partir d’appareils Mac OS X. Consultez [Comprendre vos appareils grâce à l’inventaire de Microsoft Intune](https://technet.microsoft.com/library/jj733634.aspx).
* Exécuter de nouveaux rapports qui affichent des détails sur les appareils Mac OS X que vous gérez. Consultez [Présentation des opérations Microsoft Intune à l’aide de rapports](https://technet.microsoft.com/library/dn646977.aspx).

**Nouveaux paramètres de navigateur Edge pour les appareils Windows 10** De nouveaux paramètres ont été ajoutés à la stratégie de configuration générale de Windows 10 pour vous permettre de gérer les paramètres et les fonctionnalités du navigateur Microsoft Edge. Consultez [Paramètres de la stratégie de configuration Windows 10 dans Microsoft Intune](https://technet.microsoft.com/library/mt404697.aspx).

**Profils de messagerie** Une nouvelle stratégie de profils de messagerie a été ajoutée pour les appareils Windows 10 Desktop et Windows 10 Mobile. Consultez [Gérer des paramètres et des fonctionnalités sur vos appareils avec des stratégies Microsoft Intune](https://technet.microsoft.com/library/dn646984.aspx).

**Nouveaux paramètres de stratégie de conformité** Les nouveaux paramètres de stratégie système et de sécurité suivants ont été ajoutés à la liste des stratégies de conformité :
* Pour être sûr que les dernières mises à jour sont installées sur les appareils Windows 8.1 ou version ultérieure qui accèdent aux ressources de votre entreprise, vous devez utiliser le paramètre **Exiger les mises à jour automatiques**. Vous pouvez également spécifier le type de mise à jour à installer automatiquement : soit toutes les mises à jour marquées comme importantes, soit toutes les mises à jour marquées comme importantes ou recommandées. Pour obtenir la liste complète des paramètres de stratégie de conformité, consultez [Gérer les stratégies de conformité d’appareils pour Microsoft Intune](https://technet.microsoft.com/library/dn705843.aspx).
* Le nouveau paramètre **Exiger un mot de passe quand l’appareil quitte un état inactif**, combiné avec le paramètre existant **Minutes d’inactivité avant demande du mot de passe**, vous permet de créer un paramètre de conformité qui oblige l’utilisateur final à entrer un mot de passe pour utiliser un appareil qui est inactif depuis un certain temps.

**Nouvelles options de stratégie d’accès conditionnel** Vous pouvez appliquer des stratégies d’accès conditionnel à **tous les utilisateurs** dans des stratégies d’accès conditionnel nouvelles ou existantes. Tous les utilisateurs disposant d’une licence pour Intune et Office 365 devront inscrire leurs appareils, et si la plateforme de l’appareil n’est pas prise en charge par Intune, l’accès est bloqué pour les applications clientes à l’aide de la [connexion basée sur l’authentification Active Directory (authentification moderne)](https://blogs.office.com/2014/11/12/office-2013-updated-authentication-enabling-multi-factor-authentication-saml-identity-providers/).

Vous pouvez également spécifier que la stratégie d’accès conditionnel s’applique à **toutes les plateformes**.  Toute application cliente utilisant la [connexion basée sur l’authentification Active Directory (authentification moderne)](https://blogs.office.com/2014/11/12/office-2013-updated-authentication-enabling-multi-factor-authentication-saml-identity-providers/) est soumise à la stratégie d’accès conditionnel, et si la plateforme n’est pas prise en charge par Intune, elle est bloquée.

### Modifications et mises à jour du portail d’entreprise Microsoft
Les modifications suivantes ont été apportées aux applications de portail d'entreprise dans cette version :

* **Android**: un écran d’accueil a été ajouté à l’application Portail d’entreprise Android pour aider les utilisateurs à comprendre la fonction de cette application. Cet écran vise à réduire les téléchargements de l’application par les utilisateurs dont les entreprises ne sont pas abonnées à Intune.

* **iOS** : Intune prend désormais en charge l’inscription des appareils Mac OS X à l’aide du [site web Portail d’entreprise](https://portal.manage.microsoft.com). Pour obtenir des instructions, consultez [Inscrire votre appareil Mac OS X dans Intune](https://technet.microsoft.com/library/mt598622.aspx).

* **Site web Portail d’entreprise**: les utilisateurs qui ont inscrit leur appareil dans Intune peuvent désormais réinitialiser leur code d’accès à l’aide de l’option **Réinitialiser le code d’accès** sur le site web du portail d’entreprise. Auparavant, seuls les administrateurs informatiques pouvaient réinitialiser les codes d’accès des utilisateurs. L’option Réinitialiser le code d’accès n’est pas prise en charge sur les appareils Windows 8.1 ni Windows RT. Elle s’affiche uniquement quand les appareils sont inscrits dans la gestion des appareils mobiles (MDM) ou MDM avec Exchange ActiveSync. Pour obtenir des instructions utilisateur, consultez [Réinitialiser votre code d’accès](https://technet.microsoft.com/library/mt590895.aspx).

### Modifications apportées à la gestion des licences par les administrateurs généraux
En octobre, nous avons indiqué que les administrateurs généraux (également appelés Administrateurs de clients) pouvaient continuer à effectuer des tâches d’administration quotidiennes sans licence distincte Intune ou Enterprise Mobility Suite (EMS). Toutefois, si les administrateurs généraux souhaitent utiliser le service, par exemple pour inscrire leur propre appareil ou un appareil d’entreprise, ou pour utiliser le portail d’entreprise Intune, ils doivent avoir une licence Intune ou EMS comme tout autre utilisateur. Voici quelques détails supplémentaires.
* Le portail d’entreprise Intune permet aux utilisateurs finaux :
    * D’inscrire leur appareil.
    * D’afficher l’état de leur appareil.
    * De télécharger des logiciels qu’un administrateur général a déployés dans l’organisation.
    * D’accéder à des liens publiés par l’administrateur général pour savoir comment contacter le service informatique.

    [En savoir plus sur le portail d’entreprise](https://technet.microsoft.com/library/dn646966.aspx#BKMK_CompanyPortal) et sur les différentes [façons de personnaliser le portail d’entreprise](https://technet.microsoft.com/library/dn646983.aspx#BKMK_ConfigureCompanyPortal).
* La personne qui s’inscrit pour acheter Intune ou EMS pour le compte d’une société devient automatiquement le premier administrateur général dans son locataire. Cet automne, Intune a commencé à affecter automatiquement une licence Intune ou EMS à ce premier administrateur général dans le cadre de la transition vers le [portail Office 365](http://portal.office.com/) et de la suppression du [portail des comptes Intune](http://account.manage.microsoft.com/). Les administrateurs généraux supplémentaires ajoutés peuvent continuer à effectuer des tâches d’administration quotidienne sans licence Intune ou EMS distincte. Si l’administrateur général agit comme un utilisateur final et veut inscrire son propre appareil (ou un appareil d’entreprise) ou télécharger des logiciels à partir du portail d’entreprise, il doit avoir une licence, comme tout autre utilisateur.
* Cette modification va prendre effet en janvier 2016.
* Cette modification ne doit pas affecter la capacité des partenaires Microsoft à administrer le service pour le compte de leurs clients. En revanche, les utilisateurs finaux devront avoir une licence Intune ou EMS pour pouvoir inscrire un appareil et accéder au portail d’entreprise ou télécharger un logiciel à partir du portail.

Si vous avez des questions sur cette modification, n’hésitez pas à contacter votre équipe de support technique Intune :
* [Canaux de support Microsoft Intune](https://technet.microsoft.com/library/jj839713.aspx)
* [Support de la communauté](https://social.technet.microsoft.com/Forums/en-US/home?forum=microsoftintuneprod)

Si vous avez des commentaires d’ordre général sur Microsoft Intune, notamment si vous voulez soumettre une demande de modification de conception (DCR, Design Change Request) ou un bogue, accédez à [Intune User Voice](https://microsoftintune.uservoice.com/).


### Nouveautés de la documentation d’Intune -- Novembre 2015
**Nouveau contenu**
* [Paramètres de la stratégie de configuration Mac OS X dans Microsoft Intune](https://technet.microsoft.com/library/mt627823.aspx) : explique comment contrôler les paramètres et les fonctionnalités des appareils Mac OS X.
* [Paramètres de la stratégie personnalisée Mac OS X dans Microsoft Intune](https://technet.microsoft.com/library/mt627820.aspx) : explique comment déployer les paramètres des appareils Mac OS X que vous avez créés à l’aide de l’outil Apple Configurator.
* [Configurer des stratégies d’application de prévention contre les pertes de données avec Microsoft Intune](https://technet.microsoft.com/library/mt627825.aspx) : contient des informations sur les scénarios pris en charge par les stratégies de gestion des applications mobiles et sur la façon dont les stratégies protègent les données.
* [Prise en main des stratégies de gestion des applications mobiles dans le portail Azure](https://technet.microsoft.com/library/mt627830.aspx) : explique ce que vous devez connaître pour commencer à utiliser le portail Azure en version préliminaire pour les stratégies de gestion des applications mobiles.
* [Créer et déployer des stratégies de gestion des applications mobiles à l’aide de Microsoft Intune](https://technet.microsoft.com/library/mt627829.aspx) : contient une procédure pas à pas illustrant comment créer des stratégies de gestion des applications mobiles dans le portail Azure en version préliminaire.
* [Analyser les stratégies de gestion des applications mobiles à l’aide de Microsoft Intune](https://technet.microsoft.com/library/mt627824.aspx): explique comment surveiller vos stratégies de gestion des applications mobiles à l’aide du portail Azure en version préliminaire.
* [Stratégies de gestion des applications mobiles Microsoft Intune et iOS Open In](https://technet.microsoft.com/library/mt627821.aspx): explique le fonctionnement des stratégies de gestion des applications mobiles avec la fonctionnalité iOS Open In.
* [Expérience utilisateur pour les applications associées aux stratégies de gestion des applications mobiles Microsoft Intune](https://technet.microsoft.com/library/mt627827.aspx) : décrit l’expérience utilisateur en cas d’utilisation d’applications associées à une stratégie de gestion des applications mobiles.
* [Réinitialiser les données d’applications d’entreprise managées avec Microsoft Intune](https://technet.microsoft.com/library/mt627826.aspx) : explique comment supprimer des données d’application d’entreprise.

**Contenu mis à jour**
* [Paramètres de la stratégie de configuration Windows 10 dans Microsoft Intune](https://technet.microsoft.com/library/mt404697.aspx) : ajout de nouveaux paramètres de navigateur Edge.
* [Configurer la gestion iOS et MAC avec Microsoft Intune](http://technet.microsoft.com/library/dn408185.aspx) : ajout d’informations expliquant comment inscrire des appareils Mac OS X.
* [Comprendre vos appareils grâce à l’inventaire de Microsoft Intune](https://technet.microsoft.com/library/jj733634.aspx) : ajout d’informations sur l’inventaire collecté à partir d’appareils Mac OS X. La rubrique a aussi été mise à jour avec les dernières informations pour toutes les plateformes.
* [Présentation des opérations Microsoft Intune à l’aide de rapports](https://technet.microsoft.com/library/dn646977.aspx) : ajout d’informations sur les deux nouveaux rapports qui permettent d’afficher des informations sur vos appareils Mac OS X gérés.
* [Gérer les stratégies de conformité d’appareils pour Microsoft Intune](https://technet.microsoft.com/library/dn705843.aspx): ajout d’informations sur les nouvelles stratégies de conformité relatives aux exigences en matière de mises à jour automatiques et de mots de passe quand un appareil sort d’un état d’inactivité.
* [Gérer l’accès à la messagerie avec Microsoft Intune](https://technet.microsoft.com/library/dn705841.aspx) : ajout d’informations sur la possibilité d’appliquer une stratégie d’accès conditionnel à toutes les plateformes et tous les utilisateurs.
* [Gérer l’accès à SharePoint Online avec Microsoft Intune](https://technet.microsoft.com/library/dn705844.aspx) : ajout d’informations sur la possibilité d’appliquer une stratégie d’accès conditionnel à toutes les plateformes et tous les utilisateurs.

## Octobre 2015

### Mises à jour de l’accès conditionnel pour Exchange sur site
**Vous pouvez désormais accorder l’accès à la messagerie Exchange Active Sync aux appareils conformes inscrits dans Intune quand la règle Exchange globale est définie sur « Bloquer » ou « Quarantaine ».** Jusqu’à présent, pour autoriser l’accès à la messagerie sur les appareils inscrits et conformes, vous deviez définir la règle Exchange globale par défaut sur **Autoriser**.

Avec cette mise à jour du service, ce paramètre n’est plus obligatoire pour l’accès conditionnel. Si votre environnement Exchange exige que votre règle globale par défaut soit définie sur **Bloquer/Quarantaine**, cochez simplement la case **Remplacement de la règle par défaut** dans la page de stratégie d’accès conditionnel d’Exchange sur site. La rubrique [Gérer l’accès à la messagerie avec Microsoft Intune](https://technet.microsoft.com/library/dn705841.aspx) contient davantage de détails sur les règles et les notifications qui en résultent pour les utilisateurs finaux.

**Nouvelle expérience de mise en quarantaine en un seul clic** : nous avons simplifié l’expérience de messagerie de mise en quarantaine pour permettre une inscription en un seul clic. Grâce à la mise à jour de ce service, il suffit aux utilisateurs finaux de cliquer sur un lien dans le message électronique de mise en quarantaine pour finaliser l’inscription dans l’application Portail d’entreprise.
### Mises à jour relatives à la gestion des applications et des appareils mobiles
**Android** Toutes les fonctionnalités de gestion d’Intune prennent désormais en charge Android 6.0 (Marshmallow), comme l’explique ce billet de blog : [Microsoft Intune Provides Day 0 Support for Android Marshmallow](http://blogs.technet.com/b/microsoftintune/archive/2015/10/09/microsoft-intune-to-provide-day-0-support-for-android-marshmallow.aspx)

**iOS** Vous ne pouvez plus créer de déploiements d’applications à destination d’appareils iOS exécutant une version antérieure à iOS 7.1. Les déploiements d’applications existants à destination d’appareils exécutant une version antérieure à iOS 7.1 continueront de fonctionner et d’être gérés par Intune.

**Windows 10** Intune prend désormais en charge le déploiement d’applications Windows 10 universelles à l’aide du type de programmation d’installation de logiciel **Package d’application Windows**. Pour plus d’informations et pour connaître les conditions requises, consultez [Get Started with app deployment in Microsoft Intune](http://technet.microsoft.com/en-US/library/dn646955.aspx) (Prise en main du déploiement d’applications dans Microsoft Intune).


### Modifications et mises à jour des applications Portail d'entreprise de Microsoft
Les modifications suivantes ont été apportées aux applications Portail d’entreprise dans cette version : **iOS** De nouveaux boutons ont été ajoutés à l’application Portail d’entreprise pour permettre aux utilisateurs d’envoyer plus facilement les journaux de diagnostic à leurs administrateurs informatiques :

|Nom du bouton|Emplacement|
|------------|---------------|
|Rapport|Messages d’alerte d’erreur|
|Envoyer un rapport de diagnostic|Écran « À propos de » de l’application Portail d’entreprise|



## Septembre 2015
### Mises à jour relatives à la gestion des applications et des appareils mobiles
**Toutes les fonctionnalités de gestion iOS d’Intune prennent désormais en charge iOS 9** Pour plus d’informations sur les fonctionnalités de gestion d’iOS 9, consultez [ce billet de blog](http://blogs.technet.com/b/microsoftintune/archive/2015/09/09/day-zero-support-for-ios-9-with-intune.aspx).

**Nouvelle stratégie de configuration des applications mobiles pour iOS** La nouvelle stratégie de configuration des applications mobiles vous permet de fournir automatiquement les paramètres dont peut avoir besoin une application iOS au moment de son exécution. Par exemple, vous pouvez fournir un port réseau ou un nom d’utilisateur. Pour plus d’informations, consultez [Configurer des applications avec des stratégies de configuration des applications mobiles dans Microsoft Intune](https://technet.microsoft.com/library/mt481447.aspx).

**Une gestion des applications simplifiée pour les utilisateurs d’iOS 9**
 Dans cette version, vous pouvez intégrer les applications déjà déployées à la gestion Intune pour les utilisateurs d’iOS 9. Pour les versions antérieures d’iOS, quand vous déployez une application alors qu’une version non gérée de l’application est déjà installée sur un appareil, vous devez quand même demander à l’utilisateur de désinstaller l’application manuellement pour qu’Intune puisse installer l’application gérée.

 À compter de cette version d’Intune, vous pouvez inviter les utilisateurs d’appareils iOS 9 à autoriser Intune à contrôler la gestion de l’application et à appliquer des stratégies de gestion des applications mobiles pertinentes.

 **Gestion Windows 10** La nouvelle [stratégie de configuration générale de Windows 10](https://technet.microsoft.com/library/mt404697.aspx) vous permet de configurer les paramètres de mot de passe, d’appareil, de navigateur et autres pour les appareils inscrits qui exécutent Windows 10 et Windows 10 Mobile.

 **Créer et déployer des applications sur les appareils Windows 10 inscrits** Un nouveau type de programme d’installation de logiciel, Windows Installer via MDM (&#42;.msi), vous permet de créer et de déployer des applications Windows Installer sur des appareils inscrits qui exécutent Windows 10. Pour plus d’informations, consultez [Prendre en main le déploiement d’applications dans Microsoft Intune](https://technet.microsoft.com/library/dn646955.aspx).

### Modifications et mises à jour des applications Portail d'entreprise de Microsoft
Les modifications suivantes ont été apportées aux applications de portail d'entreprise dans cette version :

**iOS**
* Microsoft recueille automatiquement des données anonymes sur les performances et l'utilisation du portail d'entreprise pour améliorer les produits et services Microsoft. Les utilisateurs finaux peuvent désactiver la collecte de données à l'aide du paramètre Données d'utilisation sur leur appareil, mais les administrateurs n'ont aucun contrôle sur la collecte de données et ne peuvent pas changer la sélection de l'utilisateur final pour ce paramètre.
* Prise en charge de la résolution plein écran sur iPhone 6 et 6 Plus
* Correction de bogues pour améliorer la sécurité

### Nouveautés de la documentation Intune -- Septembre 2015
**Nouvelles rubriques**

|Nom|Détails|
|----|--------|
|[Paramètres de la stratégie de configuration Windows 10 dans Microsoft Intune](https://technet.microsoft.com/library/mt404697.aspx)|Nouvelle stratégie de configuration qui permet de gérer les paramètres et les fonctionnalités des appareils qui exécutent Windows 10 et Windows 10 Mobile.
| [Configurer des applications avec des stratégies de configuration des applications mobiles dans Microsoft Intune](https://technet.microsoft.com/library/mt481447.aspx)|Nouveau type de stratégie qui permet de fournir automatiquement des paramètres qui peuvent être nécessaires quand l’utilisateur exécute une application iOS. |

**Rubriques mises à jour**

|Nom|Détails|
|----|-------|
|[Utiliser des stratégies pour gérer les ordinateurs et appareils mobiles avec Microsoft Intune](https://technet.microsoft.com/library/dn743712.aspx)|Documentation mise à jour pour inclure les informations les plus récentes pour vous aider à comprendre et créer les stratégies.|

## Août 2015
### Mises à jour relatives à la gestion des applications et des appareils mobiles
* Les**conditions générales** qui régissent l'inscription et l'accès des entreprises à Intune sont [désormais gérées à l'aide de stratégies](https://technet.microsoft.com/library/mt405893.aspx). Vous pouvez cibler différents jeux de conditions générales pour répondre à des exigences spécifiques de groupes d'utilisateurs. Par exemple, vous pouvez déployer des conditions générales dans différentes langues en fonction de la zone géographique des groupes d'utilisateurs. Vous pouvez aussi [modifier vos conditions générales](https://technet.microsoft.com/library/mt405893.aspx#BKMK_TCVers) et spécifier une incrémentation des numéros de version, en demandant aux utilisateurs d'accepter les nouvelles conditions générales avant de pouvoir utiliser le portail d'entreprise.
* **Un certain nombre de stratégies Intune ont été renommées** pour améliorer la cohérence générale du produit et pour les trouver plus facilement. Pour obtenir la liste de toutes les stratégies Intune disponibles, consultez [Utiliser des stratégies pour gérer les ordinateurs et les appareils mobiles avec Microsoft Intune](https://technet.microsoft.com/library/dn743712.aspx).
* Les **profils de certificat PKCS #12 (.PFX)** sont disponibles pour Android 4.0 ou version ultérieure et Windows 10 (Desktop et Mobile) et versions ultérieures. L'utilisation de profils de certificat .PFX ne nécessite pas de serveur NDES. Découvrez comment utiliser des profils de certificat .PFX dans [Activer l’accès aux ressources d’entreprise en utilisant des profils de certificat avec Microsoft Intune](http://technet.microsoft.com/library/dn818904.aspx).
* **Les paramètres des limites réseau de l’entreprise pour Windows 10 Desktop et Mobile** permettent de bénéficier de paramètres VPN granulaires, comme décrit dans [Aider les utilisateurs à se connecter à leur travail à l’aide de profils VPN avec Microsoft Intune](https://technet.microsoft.com/library/dn818905.aspx)
* **L’application OneDrive pour Android prend désormais en charge les identités multiples**. Cette mise à jour ainsi que d'autres mises à jour relatives aux stratégies de gestion des applications mobiles sont décrites dans la [liste des applications Microsoft que vous pouvez gérer](https://technet.microsoft.com/library/dn708489.aspx).
* **Contournement du verrou d'activation iOS**. Si les appareils iOS appartenant à l'entreprise sont protégés par le verrou d'activation, vous devez entrer l'ID Apple et le mot de passe de l'utilisateur pour pouvoir effacer ou réactiver l'appareil. Cela peut présenter un défi quand les utilisateurs quittent l'entreprise et rendent un appareil appartenant à l'entreprise sans désactiver le verrou d'activation. Pour résoudre ce problème, vous pouvez utiliser le [contournement du verrou d’activation Intune](https://technet.microsoft.com/library/mt414176.aspx)

### Accès conditionnel pour les PC
Vous pouvez désormais configurer des stratégies d'accès conditionnel pour les PC. Ces stratégies permettent aux applications de bureau Office d'accéder à Exchange Online et aux services SharePoint Online.
Pour activer la stratégie d'accès conditionnel pour les PCs, il faut que le PC soit joint au domaine ou soit compatible.
* Consultez la section **Prise en main** dans [Gérer l’accès à la messagerie et à SharePoint avec Microsoft Intune](http://technet.microsoft.com/library/dn818907).aspx) pour obtenir la liste complète des conditions requises pour activer l’accès conditionnel pour les PC.
* Pour connaître les options que vous pouvez configurer pour activer l’accès conditionnel à la messagerie électronique, consultez la rubrique [Gérer l’accès à la messagerie avec Microsoft Intune](https://technet.microsoft.com/library/dn705841.aspx).
* Pour connaître les options que vous pouvez définir pour activer l’accès conditionnel à SharePoint Online, consultez [Gérer l’accès à SharePoint Online avec Microsoft Intune](https://technet.microsoft.com/library/dn705844.aspx).

### Modifications et mises à jour des applications Portail d'entreprise de Microsoft
Les modifications suivantes ont été apportées aux applications de portail d'entreprise dans cette version :

**Android**

Une fois connectés, les utilisateurs verront désormais s'afficher des instructions pour inscrire les appareils s'ils n'ont pas encore inscrit le leur.

### Nouveautés dans la documentation Intune -- Août 2015
**Nouvelles rubriques**

|Titre|Détails|
|-----|-------|
|[Aider à protéger les appareils iOS avec le contournement du verrou d'activation pour Microsoft Intune](https://technet.microsoft.com/library/mt414176.aspx)|Découvrez comment contourner le verrou d'activation iOS avec Intune quand un utilisateur quitte l'entreprise et qu'il restitue un appareil verrouillé.|

**Rubriques mises à jour**

|Titre|Détails|
|-----|-------|
|[Applications Microsoft utilisables avec les stratégies de gestion des applications mobiles de Microsoft Intune](https://technet.microsoft.com/library/dn708489.aspx)|Mise à jour des informations concernant les applications que vous pouvez gérer à l'aide de stratégies de gestion d'applications mobiles.
|[Utiliser des stratégies pour gérer les ordinateurs et appareils mobiles avec Microsoft Intune](http://technet.microsoft.com/library/dn743712.aspx)|Mise à jour mentionnant les dernières stratégies ajoutées à Intune.|
<!---
## July 2015
July updates for Intune are limited to behind-the-scenes enhancements that allow us to continue providing you with a high-quality service experience. New features are not included in this service update.

### Intune Onboarding benefit
Microsoft offers the Intune Onboarding benefit for eligible plans. The Onboarding benefit lets you work remotely with Microsoft specialists to get your Intune environment ready for use. For more information, see [Microsoft Intune Onboarding benefit description](https://technet.microsoft.com/library/mt228266.aspx)
### Changes and updates to Microsoft Company Portal apps
The following changes have been made to the company portal apps in this release.

**Android**

Microsoft automatically collects anonymous data about the performance and use of the company portal to improve Microsoft products and services. End users can turn off data collection by using the Usage Data setting on their device, but administrators have no control over the data collection and cannot change the end user’s selection for this setting.--->



<!--HONumber=Jul16_HO4-->


