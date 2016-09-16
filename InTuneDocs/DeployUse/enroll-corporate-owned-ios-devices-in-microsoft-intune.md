---
title: "Inscrire les appareils iOS d’entreprise | Microsoft Intune"
description: "Inscrire des appareils iOS d’entreprise à l’aide du programme d’inscription des appareils Apple ou d’Apple Configurator"
keywords: 
author: NathBarn
manager: angrobe
ms.date: 09/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2d3ca4ab-f20c-4d56-9413-f8ef19cf0722
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: bee93334e7b868ef6c827fba9efc3318c8419527
ms.openlocfilehash: b295ee11d566fbfbe84513c045f3a76dfd51cda4


---

# Inscrire les appareils iOS d'entreprise dans Microsoft Intune
Microsoft Intune prend en charge l’inscription des appareils iOS qui appartiennent à l’entreprise par le biais du programme d’inscription des appareils (DEP, Device Enrollment Program) d’Apple ou de l’outil [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017) à exécuter sur un ordinateur Mac.

**Conditions préalables :** un [certificat des services de notification Push Apple](set-up-ios-and-mac-management-with-microsoft-intune.md) est obligatoire.

Vous pouvez inscrire les appareils iOS d’entreprise de trois façons : en utilisant Apple Configurator, le programme d’inscription des appareils ou le Portail d’entreprise.

## Utiliser Apple Configurator

Vous pouvez inscrire des appareils iOS en exportant un profil d’inscription de l’entreprise, puis en connectant ces appareils mobiles à un Mac exécutant Apple Configurator. Apple Configurator prend en charge deux formes d’inscription :

- **Inscription Assistant Configuration** : rétablit les paramètres d’usine de l’appareil et le prépare à l’installation par le nouvel utilisateur. Cette méthode oblige l’administrateur à connecter l’appareil iOS par voie USB à un ordinateur Mac qui exécute l’outil [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017) pour préconfigurer l’inscription. Les appareils sont alors remis à leurs utilisateurs, qui exécutent la procédure de l’Assistant Configuration. Cette procédure configure l’appareil avec leurs informations d’identification professionnelles ou scolaires et termine le processus d’inscription. Pour plus d’informations, consultez [Inscrire des appareils iOS avec Apple Configurator et l’Assistant Configuration](ios-setup-assistant-enrollment-in-microsoft-intune.md).

- **Inscription directe** : crée un fichier compatible avec Apple Configurator, à utiliser durant la préparation de l’appareil. Les paramètres d’usine de l’appareil inscrit ne sont pas rétablis et aucun utilisateur n’y est affilié. Cette méthode oblige l’administrateur à connecter l’appareil iOS par voie USB à un ordinateur Mac qui exécute l’outil [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017) pour inscrire l’appareil. Pour plus d’informations, consultez [Inscrire des appareils iOS en utilisant l’inscription directe Apple Configurator](ios-direct-enrollment-in-microsoft-intune.md).

## Programme d’inscription des appareils (DEP)
Le programme DEP déploie un profil d’inscription selon le procédé OTA (Over The Air) sur les appareils achetés par son biais. Quand un utilisateur exécute l’Assistant Configuration sur l’appareil, celui-ci est inscrit dans Intune.  Les appareils inscrits via le programme DEP ne peuvent pas être désinscrits par les utilisateurs. Pour plus d’informations, consultez [Inscrire des appareils iOS DEP](ios-device-enrollment-program-in-microsoft-intune.md).

## Utiliser le Portail d’entreprise sur des appareils inscrits via l’outil Apple Configurator ou DEP

Les appareils qui sont configurés avec une affinité utilisateur peuvent installer et exécuter l’application Portail d’entreprise pour télécharger des applications et gérer des appareils. Une fois que les utilisateurs reçoivent leurs appareils, ils doivent effectuer un certain nombre d’étapes supplémentaires pour terminer l’exécution de l’Assistant Installation et installer l’application Portail d’entreprise.

Une affinité utilisateur est nécessaire pour prendre en charge les éléments suivants :
  - Applications de gestion des applications mobiles (GAM)
  - Accès conditionnel aux données de messagerie et de l’entreprise
  - Application Portail d’entreprise

**Comment les utilisateurs inscrivent des appareils iOS d’entreprise avec l’affinité utilisateur**
1. Quand les utilisateurs allument leur appareil, ils sont invités à terminer l’exécution de l’Assistant Installation. Pendant l’installation, les utilisateurs sont invités à fournir leurs informations d’identification. Ils doivent utiliser les informations d’identification (c’est-à-dire, le nom d’utilisateur principal ou UPN) associées à leur abonnement dans Intune.

2. Pendant l’installation, les utilisateurs sont invités à fournir un ID Apple. Ils doivent fournir un identifiant Apple pour permettre à l’appareil d’installer le portail d’entreprise. Ils peuvent également fournir l’identifiant à partir du menu des paramètres iOS après l’installation.

3. Une fois l’installation terminée, l’appareil iOS doit installer l’application Portail d’entreprise à partir de l’App Store.

4. L’utilisateur peut désormais se connecter au portail d’entreprise à l’aide de l’UPN qu’il a utilisé pendant la configuration de l’appareil.

5. Une fois connecté, l’utilisateur est invité à inscrire son appareil. La première étape consiste à identifier l’appareil. L’application présente la liste des appareils iOS déjà inscrits par l’entreprise et affectés au compte Intune de l’utilisateur. Il doit choisir l’appareil approprié.

  Si cet appareil n’est pas encore inscrit par l’entreprise, il doit choisir **nouvel appareil** pour poursuivre la procédure d’inscription standard.

6. Dans l’écran suivant, l’utilisateur doit confirmer le numéro de série du nouvel appareil. L’utilisateur peut appuyer sur le lien **Confirmez le numéro de série** pour lancer l’application Paramètres afin de vérifier le numéro de série. L’utilisateur doit ensuite entrer les quatre derniers caractères du numéro de série dans l’application Portail d’entreprise.

  Cette étape vérifie que l’appareil est l’appareil d’entreprise inscrit dans Intune. Si le numéro de série de l’appareil ne correspond pas, l’appareil sélectionné est incorrect. L’utilisateur doit revenir à l’écran précédent et sélectionner un autre appareil.

7. Une fois le numéro de série vérifié, l’application Portail d’entreprise redirige l’utilisateur vers le site web Portail d’entreprise pour finaliser l’inscription. Ensuite, le site web invite l’utilisateur à retourner à l’application.

8. L’inscription est alors terminée. L’utilisateur peut désormais utiliser cet appareil avec l’ensemble complet de fonctionnalités.

### À propos des appareils gérés d’entreprise sans aucune affinité utilisateur

Les appareils configurés sans aucune affinité utilisateur ne prennent pas en charge le Portail d’entreprise et ne doivent pas être dotés de l’application. Le Portail d’entreprise est conçu pour les utilisateurs détenteurs d’informations d’identification d’entreprise, qui ont besoin d’accéder à des ressources d’entreprise personnalisées (par exemple à l’e-mail). Les appareils inscrits sans aucune affinité utilisateur ne sont pas destinés à un utilisateur dédié. Une borne, un point de vente (PDV) ou un appareil à usage partagé sont des exemples typiques d’utilisation d’appareils inscrits sans aucune affinité utilisateur.

Si une affinité utilisateur est obligatoire, vérifiez que l’option **Affinité utilisateur** est sélectionnée pour le profil d’inscription de l’appareil avant d’inscrire ce dernier. Pour modifier l’état d’affinité d’un appareil, vous devez le mettre hors service et le réinscrire.



### Voir aussi
[Se préparer à inscrire des appareils dans Microsoft Intune](get-ready-to-enroll-devices-in-microsoft-intune.md)



<!--HONumber=Sep16_HO3-->


