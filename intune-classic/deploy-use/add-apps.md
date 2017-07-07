---
title: Ajouter des applications
description: "Avant de commencer à déployer des applications avec Intune, vous devez vous familiariser avec les concepts présentés dans cette rubrique."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2b770f4f-6d36-41e4-b535-514b46e29aaa
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 18272f21799253128cfe0ad6aa66e108b24a0b50
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/01/2017
---
# <a name="add-apps-with-microsoft-intune"></a>Ajouter des applications avec Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Avant de commencer à déployer des applications avec Microsoft Intune, vous devez vous familiariser avec les concepts présentés dans cette rubrique. Ces concepts vous permettent de comprendre quelles applications vous pouvez déployer sur quelle plateforme. Ils vous permettent aussi de comprendre les conditions préalables qui doivent être mises en place avant de déployer les applications.

## <a name="app-types-that-you-can-deploy"></a>Types d’application que vous pouvez déployer

### <a name="software-installer"></a>Programme d’installation de logiciel

|Type d’application|Détails|
|----------------|-------|
|**Windows Installer (&#42;.exe, &#42;.msi)**|Ce type d’application doit prendre en charge une installation sans assistance et sans entrée utilisateur. La documentation de votre application doit inclure les options de ligne de commande appropriées pour installer l’application sans assistance (par exemple, **/q**). Vous trouverez une liste des options de ligne de commande courantes dans [Commutateurs de ligne de commande pour l’outil Microsoft Windows Installer](https://support.microsoft.com/kb/227091).<br><br>Tous les fichiers et dossiers supplémentaires qu’exige le programme d’installation de l’application doivent être disponibles à l’emplacement que vous spécifiez pour les fichiers d’installation de l’application.<br><br>Dans la plupart des cas, les fichiers Windows Installer (.msi) et les fichiers du correctif Windows Installer (.msp) n’ont pas besoin d’Intune pour installer des arguments de ligne de commande. Consultez la documentation de votre application.<br><br>Si des arguments de ligne de commande sont requis, vous devez les entrer sous la forme de paires Nom=Valeur (telles que TRANSFORMS=custom_transform.mst).<br><br>Ce type d’application s’applique uniquement aux ordinateurs qui exécutent le client logiciel Intune.|
|**Package d’application pour Android (&#42;.apk)**|Pour déployer des applications Android, vous devez disposer d’un package .apk valide.|
|**Package d’application pour iOS (&#42;.ipa)**|Pour déployer des applications iOS, vous devez disposer d’un package .ipa valide.<br><br>Le package .ipa doit être signé par Apple et la date d’expiration dans le profil de configuration doit être valide. Intune peut distribuer des applications iOS de certificat d’entreprise.<br><br>Toutes les applications de certificat du développeur Apple ne sont pas prises en charge.<br><br>Votre entreprise doit être inscrite au programme iOS Developer Enterprise Program.<br><br>Assurez-vous que le pare-feu de votre organisation autorise l’accès aux sites web de configuration et de certification iOS.<br><br>Vous n’avez pas besoin de déployer un fichier manifeste (.plist) avec l’application.|
|**Package d’application Windows Phone (&#42;.xap, .appx, .appxbundle)**|Pour déployer des applications, vous aurez besoin d’un certificat de signature de code mobile d’entreprise. Pour plus d’informations, consultez [Configurer la gestion de Windows Phone avec Microsoft Intune](set-up-windows-device-management-with-microsoft-intune.md).|
|**Package d’application Windows (.appx, .appxbundle)**|Pour déployer des applications, vous aurez besoin d’un certificat de signature de code mobile d’entreprise. Pour plus d’informations, consultez [Configurer la gestion des appareils Windows avec Microsoft Intune](set-up-windows-device-management-with-microsoft-intune.md).|
|**Windows Installer par le biais de la gestion des appareils mobiles (&#42;.msi)**|Vous utilisez cette application pour créer et déployer des applications Windows Installer sur des PC inscrits qui exécutent Windows 10. Ces PC sont gérés via la gestion des appareils mobiles (MDM).<br /><br />Vous ne pouvez charger qu’un seul fichier avec l’extension .msi.<br><br>Le code de produit et la version de produit du fichier sont utilisés pour la détection d’applications.<br><br>Le comportement de redémarrage par défaut de l’application sera utilisé. Intune ne contrôle pas ceci.<br><br>Les packages MSI par utilisateur sont installés pour un utilisateur unique.<br><br>Les packages MSI par ordinateur sont installés pour tous les utilisateurs de l’appareil.<br><br>Les packages MSI en mode double sont actuellement installés pour tous les utilisateurs de l’appareil uniquement.<br><br>Les mises à jour d’application sont prises en charge quand les codes de produit MSI de toutes les versions sont identiques.<br>
Tous les types d’application de programme d’installation de logiciel sont téléchargés vers votre espace de stockage cloud.

### <a name="external-link"></a>**Lien externe**
Utilisez un lien externe quand vous avez :
- Une URL qui permet aux utilisateurs de télécharger une application à partir d’un App Store.
- Un lien vers une application web qui s’exécute à partir du navigateur web.

Les applications basées sur les liens externes ne sont pas stockées dans votre espace de stockage cloud Intune.
### <a name="managed-ios-app-from-the-app-store"></a>**Application iOS gérée à partir de l’App Store**
Vous pouvez utiliser des applications iOS gérées pour gérer et déployer des applications iOS gratuites à partir de l’App Store. Vous pouvez aussi utiliser des applications iOS gérées pour associer des [stratégies de gestion d’applications mobiles](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md) aux [applications compatibles](https://www.microsoft.com/server-cloud/products/microsoft-intune/partners.aspx), puis consulter leur état dans la console Administrateur.<br /><br />Les applications iOS gérées ne sont pas stockées dans votre espace de stockage cloud Intune.

> [!TIP]
> Les options pour les appareils mobiles ne sont pas disponibles tant que vous n’avez pas [défini l’autorité MDM](prerequisites-for-enrollment.md) sur Intune.

## <a name="intune-software-publisher"></a>Éditeur de logiciel Intune
L’Éditeur de logiciel Microsoft Intune démarre quand vous ajoutez ou modifiez des applications à partir de la console Administrateur Intune. Dans l’éditeur, sélectionnez et configurez un type de programme d’installation de logiciel qui :

- Charge des applications (programmes pour les ordinateurs ou applications pour les appareils mobiles) à stocker dans le stockage cloud Intune.
- Dispose d’un lien vers un magasin en ligne ou une application web.

Avant de commencer à utiliser l'éditeur de logiciel, vous devez installer la version complète de [Microsoft .NET Framework 4.0](https://www.microsoft.com/download/details.aspx?id=17851). Après l’installation, il peut être nécessaire de redémarrer votre ordinateur pour que l’éditeur de logiciel s’ouvre correctement.

## <a name="cloud-storage-space"></a>Espace de stockage cloud
Toutes les applications que vous créez en utilisant le type d’installation de programme d’installation de logiciel (par exemple, une application métier) sont empaquetées et chargées dans le stockage cloud Microsoft Intune. Un abonnement d’essai à Intune inclut 2 Go de stockage cloud, utilisé pour stocker les applications gérées et les mises à jour. Votre abonnement complet inclut 20 Go d’espace de stockage.

Vous pouvez voir combien d’espace vous utilisez dans le nœud **Utilisation du stockage** de l’espace de travail **Administration**. Vous pouvez utiliser la méthode de paiement d’origine pour acheter du stockage supplémentaire pour Intune.  Si vous avez payé par facture ou carte de crédit, visitez le [portail Gestion des abonnements](https://portal.office.com/adminportal/home?switchtomodern=true#/subscriptions).  Dans le cas contraire, contactez votre partenaire ou vendeur.

La configuration requise pour l’espace de stockage cloud est la suivante :

-   Tous les fichiers d’installation de l’application doivent être dans le même dossier.
-   La taille maximale de chaque fichier que vous chargez s’élève à 2 Go.


## <a name="support-for-universal-windows-platform-uwp-apps"></a>Prise en charge des applications de plateforme Windows universelle (UWP)
Les PC Windows 10 n’ont pas besoin d’une clé de chargement indépendant (sideloading) pour installer des applications métier. Cependant, la clé de Registre **HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Appx\AllowAllTrustedApps** doit avoir la valeur **1** pour activer le chargement indépendant.

Si cette clé de Registre n’est pas configurée, Intune lui attribue automatiquement la valeur **1** la première fois que vous déployez une application sur l’appareil. Si vous avez défini cette valeur sur **0**, Intune ne peut pas modifier automatiquement la valeur et le déploiement des applications métier échoue.

Les applications métier de la plateforme Windows universelle doivent être signées avec un certificat de code de signature approuvé sur chaque appareil sur lequel l’application est déployée. Vous pouvez utiliser un certificat d’une infrastructure à clé publique (PKI) interne ou un certificat racine public tiers installé sur l’appareil.

Sur les appareils Windows 10 Mobile, vous pouvez utiliser un certificat de code de signature non-Symantec pour signer les applications **.appx** universelles. Pour les applications **.appx**, mais aussi les packages **.appx** générés pour Windows Phone 8.1 que vous voulez installer sur des appareils Windows 10 Mobile, vous devez utiliser un certificat de signature de code Symantec.

### <a name="dependencies-for-uwp-apps"></a>Dépendances pour les applications UWP

Quand vous ajoutez un package appxbundle Windows 10 Universel pour Intune, vous devez également vérifier que toutes les dépendances de l’application sont chargées.
Pour ce faire, vérifiez que le dossier **Dependencies** créé lors de la génération de l’application se trouve dans le même dossier que le fichier .appxbundle.
Ainsi, quand vous chargerez l’application sur Intune, tous les fichiers contenus dans le dossier **Dependencies** seront également chargés. En voici une illustration dans la capture d’écran suivante :


![Comment sélectionner des dépendances appxbundle UWP Windows 10](./media/w10-dependencies.png)


## <a name="next-steps"></a>Étapes suivantes

Vous devez ajouter les applications à la console Intune avant de les déployer. Vous pouvez ajouter des applications pour des [appareils inscrits](add-apps-for-mobile-devices-in-microsoft-intune.md) ou pour des [PC Windows que vous gérez avec le logiciel client Intune](add-apps-for-windows-pcs-in-microsoft-intune.md).
