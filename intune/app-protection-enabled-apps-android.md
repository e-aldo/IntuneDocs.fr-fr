---
title: "Applications Android avec stratégies de protection des applications"
titlesuffix: Azure portal
description: "Cet article décrit ce qui se produit lorsque votre application Android est gérée par des stratégies de protection d’application."
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a6816285-8e43-4dc8-bca0-e80ec5ef01e6
ms.reviewer: andcerat
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ac70c8ce3bbc8338339e7becb8b28d594bb2fbf6
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/09/2017
---
# <a name="what-to-expect-when-your-android-app-is-managed-by-app-protection-policies"></a>Ce qui se passe quand votre application Android est gérée par des stratégies de protection d'application 

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Cet article décrit l’expérience utilisateur relative aux applications avec des stratégies de protection d’application. Les stratégies de protection d'application ne sont appliquées que quand les applications sont utilisées dans le contexte professionnel, par exemple dans le cadre de l’accès aux applications à l’aide de votre compte professionnel ou de l’accès aux fichiers stockés à l’emplacement OneDrive Entreprise de votre société.
##  <a name="accessing-apps"></a>Accès aux applications

L’application Portail d’entreprise est obligatoire pour toutes les applications associées aux stratégies de protection d’application sur les appareils Android.

Pour les appareils qui ne sont pas inscrits dans Intune, l’application Portail d’entreprise doit être installée sur l’appareil. Toutefois, l’utilisateur n’a pas besoin de lancer l’application Portail d’entreprise ou de s’y connecter pour utiliser les applications gérées par les stratégies de protection d'application.
L’application Portail d’entreprise étant un moyen pour Intune de partager des données à un emplacement sécurisé, elle est donc indispensable même si l’appareil n’est pas inscrit dans Intune.


##  <a name="using-apps-with-multi-identity-support"></a>Utilisation d’applications avec prise en charge de plusieurs identités

Les stratégies de protection d'application n’étant appliquées que dans le cadre de l’utilisation professionnelle de l’application, le comportement de celle-ci peut différer selon qu’elle est utilisée dans un contexte professionnel ou personnel.

Pour les applications qui prennent en charge plusieurs identités, Intune n’applique les stratégies de protection d'application que quand l’utilisateur final utilise l’application dans le contexte professionnel.  Par exemple, l’utilisateur final reçoit une invite de code confidentiel quand il accède aux données professionnelles.  Pour l’**application Outlook**, l’utilisateur final est invité à entrer un code confidentiel au lancement de l’application. Pour l’**application OneDrive**, cela se produit quand l’utilisateur final tape le compte professionnel.  Pour Microsoft **Word**, **PowerPoint* et **Excel**, cela se produit quand l’utilisateur final accède à des documents stockés à l’emplacement OneDrive Entreprise de votre société.
##  <a name="managing-user-accounts-on-the-device"></a>Gestion des comptes d’utilisateur sur l’appareil

Intune prend en charge le déploiement de stratégies de protection d'application vers un seul compte d’utilisateur par appareil.

* Il est possible que le deuxième utilisateur soit bloqué sur l’appareil, mais cela dépend de l’application utilisée. Toutefois, dans tous les cas, seul le premier utilisateur sujet aux stratégies de protection d'application est affecté par la stratégie.

  * **Microsoft Word**, **Excel** et **PowerPoint** ne bloquent pas un deuxième compte d’utilisateur, mais celui-ci n’est pas affecté par les stratégies de protection d'application.

  * Pour les **applications OneDrive et Outlook**, vous ne pouvez utiliser qu’un seul compte professionnel.  L’ajout de plusieurs comptes professionnels est bloqué sur ces applications.  Toutefois, vous pouvez supprimer un utilisateur et en ajouter un autre sur l’appareil.


* Si un appareil a plusieurs comptes d’utilisateur existants avant le déploiement des stratégies, le premier compte vers lequel les stratégies de protection d'application sont déployées est géré par les stratégies de protection d'application Intune.


Lisez l’exemple de scénario ci-dessous pour mieux comprendre le comportement quand il existe plusieurs comptes d’utilisateur.

L’utilisateur A travaille pour deux sociétés : **Société X** et **Société Y**. L’utilisateur A a un compte professionnel pour chaque société, et tous deux utilisent Intune pour déployer des stratégies de protection d'application. **Société X** déploie des stratégies de protection d'application **avant** **Société Y**. Le compte associé à **Société X** est soumis à la stratégie de protection d’application, contrairement au compte associé à Société Y. Si vous souhaitez que le compte d’utilisateur associé à Société Y soit géré par les stratégies de protection d’application, vous devez supprimer le compte d’utilisateur associé à Société X.
### <a name="adding-a-second-account"></a>Ajout d’un deuxième compte
####  <a name="android"></a>Android
Sur un appareil Android, un message de blocage peut s’afficher avec des instructions permettant de supprimer le compte existant et d’en ajouter un nouveau.  Pour supprimer le compte existant, accédez à **Paramètres &gt;Général &gt; Gestionnaire d’applications &gt;Portail d’entreprise et sélectionnez « Effacer les données »**.

![Capture d’écran du message d’erreur et des instructions pour supprimer le compte](./media/android-switch-user.png)

##  <a name="viewing-media-files-with-the-azure-information-protection-app-previously-known-as-rights-management-sharing-app"></a>Affichage des fichiers multimédias avec l’application Azure Information Protection (anciennement Rights Management)
Pour afficher les fichiers image, AV et PDF d’entreprise sur des appareils Android, utilisez l’[application Azure Information Protection](https://play.google.com/store/apps/details?id=com.microsoft.ipviewer).

Vous pouvez télécharger cette application à partir de la boutique Google Play.  

Les types de fichiers suivants sont pris en charge :

* **Audio :** AAC-LC, HE-AACv1 (AAC+), HE-AACv2 (AAC+ amélioré), AAC-ELD (AAC avec délai court amélioré), AMR-NB, AMR-WB, FLAC, MP3, MIDI, Ogg Vorbis, PCM/WAVE.
* **Vidéo :** H.263, H.264 AVC, MPEG-4 SP, VP8.
* **Image :** jpg, pjpg, png, ppng, bmp, pbmp, gif, pgif, jpeg, pjpeg.
* **Documents :** PDF, PPDF

------------
|**pfile**|**text**|
|----|----|
|Pfile est un format « wrapper » générique pour les fichiers protégés qui encapsulent du contenu chiffré ainsi que des licences Azure Information Protection, et qui permet de protéger n’importe quel type de fichier.|Les fichiers texte, notamment XML, CSV, etc., peuvent être ouverts pour être affichés dans l’application même quand ils sont protégés. Types de fichiers : txt, ptxt, csv, pcsv, log, plog, xml, pxml.|
---------------
## <a name="next-steps"></a>Étapes suivantes
[Ce qui se passe quand votre application iOS est gérée par des stratégies de protection d'application](app-protection-enabled-apps-ios.md)

### <a name="see-also"></a>Voir aussi
[Créer et déployer des stratégies de protection d’application à l’aide de Microsoft Intune](app-protection-policies.md)
