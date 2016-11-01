---
title: "Applications Android avec les stratégies de gestion des applications mobiles | Microsoft Intune"
description: "Cette rubrique décrit ce qui se passe lorsque votre application est gérée par les stratégies de gestion des applications mobiles."
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 10/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 53c8e2ad-f627-425b-9adc-39ca69dbb460
ms.reviewer: andcerat
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 389daf0ed39fa2cd4b2e5d6e52cbd6809a568c9e
ms.openlocfilehash: 546b909737b4ea34bd747880fe8ed2d366c6b18a


---

# Ce qui se passe quand votre application Android est gérée par des stratégies GAM
Cette rubrique décrit l’expérience de l’utilisateur des applications avec des stratégies GAM. Les stratégies de gestion des applications mobiles (GAM) ne sont appliquées que quand les applications sont utilisées dans le contexte professionnel, par exemple dans le cadre de l’accès aux applications à l’aide de votre compte professionnel ou de l’accès aux fichiers stockés à l’emplacement OneDrive Entreprise de votre société.
##  Accès aux applications

L’application Portail d’entreprise est obligatoire pour toutes les applications associées aux stratégies GAM sur les appareils Android.

Pour les appareils qui ne sont pas inscrits dans Intune, l’application Portail d’entreprise doit être installée sur l’appareil. Toutefois, l’utilisateur n’a pas besoin de lancer l’application Portail d’entreprise ou de s’y connecter pour utiliser les applications gérées par les stratégies GAM.
L’application Portail d’entreprise étant un moyen pour Intune de partager des données à un emplacement sécurisé, elle est donc indispensable même si l’appareil n’est pas inscrit dans Intune.


##  Utilisation d’applications avec prise en charge de plusieurs identités

Les stratégies GAM n’étant appliquées que dans le cadre de l’utilisation professionnelle de l’application, le comportement de celle-ci peut différer selon qu’elle est utilisée dans un contexte professionnel ou personnel.

Pour les applications qui prennent en charge plusieurs identités, Intune n’applique les stratégies GAM que quand l’utilisateur final utilise l’application dans le contexte professionnel.  Par exemple, l’utilisateur final reçoit une invite de code confidentiel quand il accède aux données professionnelles.  Pour l’**application Outlook**, l’utilisateur final est invité à entrer un code confidentiel au lancement de l’application. Pour l’**application OneDrive**, cela se produit quand l’utilisateur final tape le compte professionnel.  Pour Microsoft **Word**, **PowerPoint* et **Excel**, cela se produit quand l’utilisateur final accède à des documents stockés à l’emplacement OneDrive Entreprise de votre société.
##  Gestion des comptes d’utilisateur sur l’appareil

Intune prend en charge le déploiement de stratégies GAM vers un seul compte d’utilisateur par appareil.

* Il est possible que le deuxième utilisateur soit bloqué sur l’appareil, mais cela dépend de l’application utilisée. Toutefois, dans tous les cas, seul le premier utilisateur sujet aux stratégies GAM est affecté par la stratégie.

  * **Microsoft Word**, **Excel** et **PowerPoint** ne bloquent pas un deuxième compte d’utilisateur, mais celui-ci n’est pas affecté par les stratégies GAM.

  * Pour les **applications OneDrive et Outlook**, vous ne pouvez utiliser qu’un seul compte professionnel.  L’ajout de plusieurs comptes professionnels est bloqué sur ces applications.  Toutefois, vous pouvez supprimer un utilisateur et en ajouter un autre sur l’appareil.


* Si un appareil a plusieurs comptes d’utilisateur existants avant le déploiement des stratégies, le premier compte vers lequel les stratégies GAM sont déployées est géré par les stratégies GAM Intune.


Lisez l’exemple de scénario ci-dessous pour mieux comprendre le comportement quand il existe plusieurs comptes d’utilisateur.

L’utilisateur A travaille pour deux sociétés : **Société X** et **Société Y**. L’utilisateur A a un compte professionnel pour chaque société, et tous deux utilisent Intune pour déployer des stratégies GAM. **Société X** déploie des stratégies GAM **avant** **Société Y**. Le compte associé à **Société X** est soumis à la stratégie GAM, contrairement au compte associé à Société Y. Si vous souhaitez que le compte d’utilisateur associé à Société Y soit géré par les stratégies GAM, vous devez supprimer le compte d’utilisateur associé à Société X.
### Ajout d’un deuxième compte
####  Android
Sur un appareil Android, un message de blocage peut s’afficher avec des instructions permettant de supprimer le compte existant et d’en ajouter un nouveau.  Pour supprimer le compte existant, accédez à **Paramètres &gt;Général &gt; Gestionnaire d’applications &gt;Portail d’entreprise et sélectionnez « Effacer les données »**.

![Capture d’écran du message d’erreur et des instructions pour supprimer le compte](../media/AppManagement/Android_SwitchUser.png)

##  Affichage des fichiers multimédias avec l’application Azure Information Protection (anciennement Rights Management)
Pour afficher les fichiers image, AV et PDF d’entreprise sur des appareils Android, utilisez l’[application Azure Information Protection](https://play.google.com/store/apps/details?id=com.microsoft.ipviewer).

Vous pouvez télécharger cette application à partir de la boutique Google Play.  

Les types de fichiers suivants sont pris en charge :

* **Audio :** AAC-LC, HE-AACv1 (AAC+), HE-AACv2 (AAC+ amélioré), AAC-ELD (AAC avec délai court amélioré), AMR-NB, AMR-WB, FLAC, MP3, MIDI, Ogg Vorbis, PCM/WAVE.
* **Vidéo :** H.263, H.264 AVC, MPEG-4 SP, VP8.
* **Image :** jpg, pjpg, png, ppng, bmp, pbmp, gif, pgif, jpeg, pjpeg.
* **Documents :** PDF, PPDF

------------
|**pfile**|**texte**|
|----|----|
|Pfile est un format « wrapper » générique pour les fichiers protégés qui encapsulent du contenu chiffré ainsi que des licences Azure Information Protection, et qui permet de protéger n’importe quel type de fichier.|Les fichiers texte, notamment XML, CSV, etc., peuvent être ouverts pour être affichés dans l’application même quand ils sont protégés. Types de fichiers : txt, ptxt, csv, pcsv, log, plog, xml, pxml.|
---------------
## Étapes suivantes
[Ce qui se passe quand votre application iOS est gérée par des stratégies GAM](user-experience-for-mam-enabled-ios-apps-with-microsoft-intune.md)

### Voir aussi
[Créer et déployer des stratégies de gestion des applications mobiles à l’aide de Microsoft Intune](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Oct16_HO3-->


