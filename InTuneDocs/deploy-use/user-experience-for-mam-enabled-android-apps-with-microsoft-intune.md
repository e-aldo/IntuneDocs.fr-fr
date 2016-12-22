---
title: "Applications Android avec les stratégies de gestion des applications mobiles | Microsoft Intune"
description: "Cette rubrique décrit ce qui se passe lorsque votre application est gérée par les stratégies de gestion des applications mobiles."
keywords: 
author: NathBarn
ms.author: nathbarn
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
ms.sourcegitcommit: 87e37cd8334ddb9331c0662b691545cd0ab0553a
ms.openlocfilehash: 945c9f48846fc37358c44b83990feed1f3694966


---

# <a name="what-to-expect-when-your-android-app-is-managed-by-mam-policies"></a>Ce qui se passe quand votre application Android est gérée par des stratégies GAM
Cette rubrique décrit l’expérience de l’utilisateur des applications avec des stratégies GAM (gestion des applications mobiles). Les stratégies GAM ne sont appliquées que quand les applications sont utilisées dans un contexte professionnel, par exemple quand l’utilisateur accède à des applications à l’aide d’un compte professionnel ou accède à des fichiers stockés à l’emplacement OneDrive Entreprise d’une société.
##  <a name="access-apps"></a>Accéder aux applications

L’application Portail d’entreprise est obligatoire pour toutes les applications associées aux stratégies GAM sur les appareils Android.

Pour les appareils qui ne sont pas inscrits dans Intune, l’application Portail d’entreprise doit être installée sur l’appareil. Toutefois, l’utilisateur n’a pas besoin de lancer l’application Portail d’entreprise ou de s’y connecter pour utiliser les applications gérées par les stratégies GAM.

L’application Portail d’entreprise est un moyen pour Intune de partager des données dans un emplacement sécurisé. Ainsi, l’application Portail d’entreprise est obligatoire pour toutes les applications qui sont associés à des stratégies GAM, même si l’appareil n’est pas inscrit dans Intune.


##  <a name="use-apps-with-multi-identity-support"></a>Utiliser des applications avec prise en charge de plusieurs identités

Les stratégies GAM sont appliquées uniquement dans le contexte professionnel. Ainsi, l’application peut se comporter différemment selon qu’il s’agit d’un contexte professionnel ou personnel.

Par exemple, l’utilisateur reçoit une invite de code confidentiel quand il accède à des données professionnelles. Pour l’**application Outlook**, l’utilisateur est invité à entrer un code confidentiel quand il lance l’application. Pour l’**application OneDrive**, l’utilisateur est invité à entrer le code confidentiel quand il entre son compte professionnel. Pour Microsoft **Word**, **PowerPoint** et **Excel**, l’utilisateur est invité à entrer le code confidentiel quand il accède à des documents stockés à l’emplacement OneDrive Entreprise de la société.

##  <a name="manage-user-accounts-on-the-device"></a>Gérer les comptes d’utilisateur sur l’appareil

Intune prend en charge le déploiement de stratégies GAM sur un seul compte d’utilisateur par appareil.

* Il est possible que le deuxième utilisateur soit bloqué sur l’appareil, mais cela dépend de l’application utilisée. Toutefois, dans tous les cas, seul le premier utilisateur sujet aux stratégies GAM est affecté par la stratégie.

  * **Microsoft Word**, **Excel** et **PowerPoint** ne bloquent pas un deuxième compte d’utilisateur, mais celui-ci n’est pas affecté par les stratégies GAM.

  * Pour les applications **OneDrive** et **Outlook**, vous ne pouvez utiliser qu’un seul compte professionnel.  Vous ne pouvez pas ajouter plusieurs comptes professionnels pour ces applications.  Toutefois, vous pouvez supprimer un utilisateur et en ajouter un autre sur l’appareil.


* Si un appareil a plusieurs comptes d’utilisateur existants avant le déploiement des stratégies, le premier compte sur lequel les stratégies GAM sont déployées est géré par les stratégies GAM Intune.


Lisez l’exemple de scénario suivant pour mieux comprendre le comportement quand il existe plusieurs comptes d’utilisateur.

L’utilisateur A travaille pour deux sociétés : **Société X** et **Société Y**. L’utilisateur A a un compte professionnel pour chaque société, et tous deux utilisent Intune pour déployer des stratégies GAM. **Société X** déploie des stratégies GAM **avant** **Société Y**. Le compte associé à **Société X** est soumis à la stratégie GAM, contrairement au compte associé à Société Y. Si vous souhaitez que le compte d’utilisateur associé à Société Y soit géré par les stratégies GAM, vous devez supprimer le compte d’utilisateur associé à Société X.
### <a name="add-a-second-account"></a>Ajouter un deuxième compte
####  <a name="android"></a>Android
Sur un appareil Android, un message de blocage peut s’afficher avec des instructions permettant de supprimer le compte existant et d’en ajouter un nouveau.  Pour supprimer le compte existant, accédez à **Paramètres &gt;Général &gt; Gestionnaire d’applications &gt;Portail d’entreprise**. Ensuite, choisissez **Effacer les données**.

![Capture d’écran du message d’erreur et des instructions pour supprimer le compte](../media/AppManagement/Android_SwitchUser.png)

##  <a name="view-media-files-with-the-azure-information-protection-app"></a>Afficher des fichiers multimédias avec l’application Azure Information Protection
Pour afficher les fichiers image, AV et PDF d’entreprise sur des appareils Android, utilisez l’[application Azure Information Protection](https://play.google.com/store/apps/details?id=com.microsoft.ipviewer) (anciennement « application de partage Microsoft Rights Management »).

Vous pouvez télécharger cette application à partir de Google Play Store.  

Les types de fichiers suivants sont pris en charge :

* **Audio :** AAC-LC, HE-AACv1 (AAC+), HE-AACv2 (AAC+ amélioré), AAC-ELD (AAC avec délai court amélioré), AMR-NB, AMR-WB, FLAC, MP3, MIDI, Ogg Vorbis, PCM/WAVE
* **Vidéo :** H.263, H.264 AVC, MPEG-4 SP, VP8
* **Image :** .jpg, .pjpg, .png, .ppng, .bmp, .pbmp, .gif, .pgif, .jpeg, .pjpeg
* **Documents :** PDF, PPDF


|**pfile**|**text**|
|----|----|
|Pfile est un format « wrapper » générique pour les fichiers protégés qui encapsulent du contenu chiffré ainsi que des licences Azure Information Protection. Il peut être utilisé pour protéger tout type de fichier.|Les fichiers texte, notamment XML, CSV, et ainsi de suite, peuvent être ouverts pour être affichés dans l’application même quand ils sont protégés. Types de fichiers : .txt, .ptxt, .csv, .pcsv, .log, .plog, .xml, .pxml.|

## <a name="next-steps"></a>Étapes suivantes
[Ce qui se passe quand votre application iOS est gérée par des stratégies GAM](user-experience-for-mam-enabled-ios-apps-with-microsoft-intune.md)

### <a name="see-also"></a>Voir aussi
[Créer et déployer des stratégies de gestion des applications mobiles à l’aide de Microsoft Intune](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Dec16_HO2-->


