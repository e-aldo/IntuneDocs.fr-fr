---
# required metadata

title: Nouveautés | Microsoft Intune
description:
keywords:
author: Lindavr
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Nouveautés de Microsoft Intune

## Avril 2016
Toutes ces fonctionnalités sont également prises en charge pour les clients hybrides (Configuration Manager intégré à Intune).
### Gestion d'applications
- **Conformité MAM de l’utilisateur.**
Vous pouvez désormais afficher l’[état](monitor-mobile-app-management-policies-with-Microsoft-Intune.md) de vos stratégies de gestion d’applications pour n'importe quel utilisateur dans votre client Azure Active Directory (AAD). Les opérations à effectuer sont les suivantes :
   - Appareils
   - Applications sur l’appareil

   Valeurs d'état :

   **Activé** : indique que la stratégie a été déployée pour l'utilisateur, que l’application a été utilisée dans un contexte professionnel et qu’elle a reçu avec succès la stratégie.

    **Non activé :** indique que la stratégie a été déployée pour l’utilisateur, mais que l’application n’a pas été utilisée au moins une fois dans un contexte professionnel depuis.


- **Contrôles MAM pour empêcher la synchronisation des contacts Outlook (Android).**
Un nouveau paramètre est disponible pour la [gestion des applications mobiles](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) sans inscription de l'appareil. Ce paramètre vous permet d’empêcher une application de synchroniser les contacts avec le carnet d'adresses natif sur les appareils Android. Si ce paramètre est activé, les applications ciblées ne pourront plus enregistrer les contacts dans le carnet d'adresses natif. Si ce paramètre est désactivé, les applications ciblées pourront enregistrer les contacts dans le carnet d'adresses natif. Lorsque vous [réinitialisez de façon sélective un appareil ou une application](wipe-managed-company-app-data-with-Microsoft-Intune.md), les contacts déjà enregistrés dans le carnet d'adresses natif seront supprimés. Ce nouveau paramètre est initialement pris en charge par l'application Outlook sur les appareils Android.

### Gestion des appareils
- **Identification de numéros de téléphone pour les appareils appartenant à l'entreprise.** Les téléphones classés comme « appartenant à l’entreprise » sont identifiés avec leur numéro de téléphone complet, par exemple, lorsque vous exécutez un rapport d’inventaire des appareils mobiles. Les numéros de téléphone de type « BYOD » continuent d’être masqués avec **** ; seuls les 4 derniers chiffres s’affichent.


### Mises à jour de Portail d'entreprise
**Application Portail d’entreprise Android**
Les utilisateurs qui n'ont pas inscrit leur appareil dans Intune et qui n'ont pas le bon certificat installé ne pourront pas se connecter à l'application Portail d'entreprise Android. Le message suivant s'affiche : « Vous ne pouvez pas vous connecter, car il manque un certificat obligatoire à votre appareil.. » Le message inclut un lien « Comment résoudre ce problème » permettant aux utilisateurs d’obtenir des instructions pour installer le certificat. Pour connaître les étapes que les utilisateurs finaux doivent suivre pour résoudre ce problème, consultez [Il manque un certificat obligatoire à votre appareil](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_cert_missing).

**Application Portail d’entreprise iOS**
Une prise en charge a été ajoutée pour l'action Tirer pour actualiser permettant d’actualiser le contenu sur l'écran d'accueil, notamment les applications répertoriées, les appareils répertoriés et les informations sur les contacts informatiques. L'action Tirer pour actualiser ne vérifie pas les informations de conformité ou de stratégie, opération qui peut être effectuée en sélectionnant la vignette correspondant à votre appareil puis en appuyant sur le bouton **Sync**.

**Application Portail d’entreprise Windows 10 Mobile et Windows Phone 8.1**
Lorsque les utilisateurs finaux installent des applications métier, ils bénéficient d’une expérience d’installation améliorée. Si l'installation de l'application prend beaucoup de temps, les utilisateurs peuvent synchroniser manuellement leur appareil pour forcer la reprise du processus de synchronisation. Pour consulter les instructions de l'utilisateur final, voir [Synchroniser votre appareil manuellement pour accélérer l’installation des applications](https://technet.microsoft.com/library/mt427782.aspx#BKMK_win10m_wp81_sync_manually).

**Site web Portail d’entreprise**
Lorsque les utilisateurs Windows 10 Mobile et Windows Phone 8.1 installent des applications métier, les nouveaux états suivants apparaissent et leur fournissent plus de détails sur l'état de leur installation :

* **En attente de la synchronisation de l’appareil** : l'utilisateur a appuyé sur « Installer » et l'appareil tente à présent de se synchroniser avec l'infrastructure Intune. La synchronisation est nécessaire pour pouvoir finaliser l'installation. Le message « En attente de la synchronisation de l’appareil » contient également un lien sur lequel les utilisateurs peuvent cliquer pour obtenir des [instructions](https://technet.microsoft.com/library/mt590895.aspx#BKMK_iwp_sync_manually) sur la synchronisation manuelle de leur appareil avec Intune si le processus de synchronisation prend beaucoup de temps ou se bloque.
* **Téléchargement** : la demande de téléchargement de l'utilisateur est en cours de traitement et l’appareil télécharge et installe l'application.

Avant l'ajout de ces états, les utilisateurs étaient désorientés lorsque l’installation de l'application prenait beaucoup de temps car seul l’état « Installation » s’affichait à l'écran, parfois pendant des heures. Grâce à l’ajout de ces nouveaux états, au lieu d'appeler le support technique, les utilisateurs peuvent désormais appuyer sur le lien « En attente de la synchronisation de l’appareil » et suivre les instructions pour forcer la reprise du processus de synchronisation.

### Nouveautés à venir

**Modifications apportées aux comptes de gestionnaires d'inscription d’appareils.** Pour améliorer les performances et la mise à l’échelle, Intune n'affiche plus tous les appareils Gestionnaires d’inscription d’appareil (DEM) dans le volet Mes appareils de l'application Portail d'entreprise. Seul l’appareil local qui exécute l'application est affiché et uniquement s'il est inscrit via l'application Portail d'entreprise. L'utilisateur DEM peut effectuer des actions sur l’appareil local, mais la gestion à distance d’autres appareils inscrits ne peut être effectuée à partir de la console d'administration Intune.  En outre, Intune désapprouvera l’utilisation de comptes DEM avec le Programme d'inscription d'appareils Apple ou l'outil Apple Configurator. Ces deux méthodes d'inscription prennent déjà en charge l'inscription sans utilisateur pour les appareils iOS partagés.  Utilisez uniquement les comptes DEM lors l'inscription sans utilisateur d’appareils partagés n'est pas disponible.

Restez informé des développements à venir pour Intune avec la [Feuille de route de la plateforme cloud](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune).


## Versions précédentes d’Intune
Les dernières améliorations apportées à Intune au cours des six derniers mois sont répertoriées dans l’article [Versions précédentes d’Intune](previous-intune-releases.md).



### Voir aussi
* [Blog Microsoft Intune](http://go.microsoft.com/fwlink/?LinkID=273882)


<!--HONumber=May16_HO1-->


