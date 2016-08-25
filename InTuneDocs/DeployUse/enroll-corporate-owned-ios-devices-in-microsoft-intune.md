---
title: "Inscrire les appareils iOS d’entreprise | Microsoft Intune"
description: "Inscrire des appareils iOS d’entreprise à l’aide du programme d’inscription d’appareils Apple ou d’Apple Configurator"
keywords: 
author: NathBarn
manager: angrobe
ms.date: 07/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2d3ca4ab-f20c-4d56-9413-f8ef19cf0722
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 9b7b8f6e5182e228458f5ea75e804a638f1e2a2b
ms.openlocfilehash: ca05e94e72269c11db24b667f1d113c794cd8b23


---

# Inscrire les appareils iOS d'entreprise dans Microsoft Intune
Microsoft Intune prend en charge l’inscription des appareils iOS qui appartiennent à l’entreprise à l’aide du programme d’inscription d’appareils (DEP, Device Enrollment Program) d’Apple ou de l’outil [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017) à exécuter sur un ordinateur Mac.

**Conditions préalables :** [certificat des services de notification Push Apple](set-up-ios-and-mac-management-with-microsoft-intune.md)

Vous pouvez inscrire les appareils iOS d'entreprise de trois façons :

-   **Apple Configurator** : vous pouvez inscrire des appareils iOS en exportant un profil Corporate Enrollment (Inscription pour l’entreprise), puis en connectant ces appareils mobiles à un Mac exécutant Apple Configurator. Apple Configurator prend en charge deux formes d’inscription :

    - **Inscription Assistant Configuration** : rétablit les paramètres d'usine de l'appareil et le prépare à l'installation par le nouvel utilisateur. Cette méthode oblige l’administrateur à connecter par voie USB l’appareil iOS à un ordinateur Mac qui exécute l’outil [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017) pour préconfigurer l’inscription. Les appareils sont ensuite remis à leurs utilisateurs, qui exécutent le processus de l’Assistant Configuration pour configurer l’appareil avec leurs informations d’identification professionnelles ou scolaires et terminer le processus d’inscription. [Inscrire des appareils iOS avec Apple Configurator et l’Assistant Configuration](ios-setup-assistant-enrollment-in-microsoft-intune.md)

    - **Inscription directe** : crée un fichier compatible avec Apple Configurator, à utiliser durant la préparation de l’appareil. Les paramètres d'usine de l'appareil inscrit ne sont pas rétablis et aucun utilisateur n'y est affilié. Cette méthode oblige l’administrateur à connecter par voie USB l’appareil iOS à un ordinateur Mac qui exécute l’outil [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017) pour inscrire l’appareil. [Inscrire des appareils iOS en utilisant l’inscription directe Apple Configurator](ios-direct-enrollment-in-microsoft-intune.md)

-   **Device Enrollment Program (DEP)** : déploie un profil d’inscription « à distance » sur des appareils achetés par le biais du programme DEP d’Apple. Quand l’utilisateur exécute l’Assistant Configuration sur l’appareil, celui-ci est inscrit dans Intune.  Les appareils inscrits via le programme DEP ne peuvent pas être désinscrits par les utilisateurs. [Inscrire des appareils iOS DEP](ios-device-enrollment-program-in-microsoft-intune.md)

## Utilisation du Portail d’entreprise sur des appareils inscrits via l’outil Apple Configurator ou DEP

Des appareils configurés avec une affinité utilisateur peuvent installer et exécuter l’application Portail d’entreprise pour télécharger des applications et gérer des appareils. Lorsque les utilisateurs reçoivent leurs appareils, ils doivent effectuer un certain nombre d’étapes supplémentaires pour achever l’exécution de l’Assistant Installation et installer l’application Portail d’entreprise.

Comment inscrire des appareils iOS d’entreprise avec l’affinité utilisateur
1. Lorsque les utilisateurs mettent sous tension leur appareil, ils sont invités à achever l’exécution de l’Assistant Installation. Pendant l’installation, les utilisateurs sont invités à fournir leurs informations d’identification. Ils doivent utiliser les informations d’identification (c’est-à-dire, le nom d’utilisateur principal ou UPN) associées à leur abonnement dans Intune.

2. Pendant l’installation, les utilisateurs sont invités à fournir un ID Apple. Un ID Apple doit être fourni pour permettre au périphérique d’installer le portail d’entreprise. Un ID Apple peut également être fourni une fois l’installation terminée, à partir du menu Paramètres d’iOS.

3. Une fois l’installation terminée, l’appareil iOS doit installer l’application Portail d’entreprise à partir de l’App Store.

4. L’utilisateur peut désormais se connecter au portail d’entreprise à l’aide de l’UPN utilisé lors de la configuration du périphérique.

5. Une fois connecté, l’utilisateur est invité à inscrire son périphérique. La première étape consiste à identifier l’appareil. L’application présente la liste des périphériques iOS déjà inscrits par l’entreprise et affectés au compte Intune de l’utilisateur final. Choisissez le périphérique approprié.

  Si ce périphérique n’est pas encore inscrit par l’entreprise, sélectionnez « Nouveau périphérique » pour poursuivre le flux d’inscription standard.

6. Sur l’écran suivant, l’utilisateur doit confirmer le numéro de série du nouveau périphérique. L’utilisateur peut appuyer sur le lien « Confirmez le numéro de série » pour lancer l’application Paramètres afin de vérifier le numéro de série. L’utilisateur doit ensuite entrer les 4 derniers caractères du numéro de série dans l’application Portail d’entreprise.

  Cette étape vérifie que le périphérique est le périphérique d’entreprise inscrit dans Intune. Si le numéro de série du périphérique ne correspond pas, le périphérique sélectionné est incorrect. Revenez à l’écran précédent et sélectionnez un autre périphérique.

7. Une fois le numéro de série vérifié, l’application Portail d’entreprise redirige l’utilisateur vers le site web Portail d’entreprise pour finaliser l’inscription, puis l’invite à retourner à l’application.

8. L’inscription est alors terminée. Vous pouvez désormais utiliser ce périphérique avec l’ensemble complet de fonctionnalités.

### À propos des périphériques gérés d’entreprise sans aucune affinité utilisateur

Les appareils configurés sans aucune affinité utilisateur ne prennent pas en charge le Portail d’entreprise et ne doivent pas installer l’application. Le Portail d’entreprise est conçu pour les utilisateurs détenteurs d’informations d’identification d’entreprise, qui ont besoin d’accéder à des ressources d’entreprise personnalisées (par exemple, au courrier électronique). Les appareils inscrits sans aucune affinité utilisateur ne sont pas destinés à un utilisateur dédié. Un kiosque, un point de vente (PDV) ou un périphérique utilitaire partagé sont des exemples caractéristiques d’utilisation de périphériques inscrits sans aucune affinité utilisateur. Si une affinité utilisateur est requise, vérifiez que l’affinité utilisateur est sélectionnée pour le profil d’inscription de l’appareil avant d’inscrire ce dernier. Pour modifier l’état d’affinité sur un périphérique, vous devez le mettre hors service, puis le réinscrire.



### Voir aussi
[Se préparer à inscrire des appareils dans Microsoft Intune](get-ready-to-enroll-devices-in-microsoft-intune.md)



<!--HONumber=Aug16_HO1-->


