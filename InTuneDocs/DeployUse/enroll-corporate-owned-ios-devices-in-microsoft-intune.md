---
# required metadata

title: Inscrire les appareils iOS d’entreprise dans Microsoft Intune | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 2d3ca4ab-f20c-4d56-9413-f8ef19cf0722

# optional metadata

ROBOTS: noindex,nofollow
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Inscrire les appareils iOS d'entreprise dans Microsoft Intune
Microsoft Intune prend en charge l’inscription des appareils iOS qui appartiennent à l’entreprise à l’aide du programme d’inscription d’appareils (DEP, Device Enrollment Program) d’Apple ou de l’outil [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017) à exécuter sur un ordinateur Mac.

Vous pouvez inscrire les appareils iOS d'entreprise de trois façons :

-   **Inscription Assistant Configuration** : rétablit les paramètres d'usine de l'appareil et le prépare à l'installation par le nouvel utilisateur. Cette méthode oblige l’administrateur à connecter par voie USB l’appareil iOS à un ordinateur Mac qui exécute Apple Configurator pour préconfigurer l’inscription. Les appareils sont ensuite remis à leurs utilisateurs, qui exécutent le processus de l’Assistant Configuration pour configurer l’appareil avec leurs informations d’identification professionnelles ou scolaires et terminer le processus d’inscription. [Inscrire des appareils iOS avec Apple Configurator et l’Assistant Configuration](ios-setup-assistant-enrollment-in-microsoft-intune.md)

-   **Inscription directe** : crée un fichier compatible avec Apple Configurator, à utiliser durant la préparation de l’appareil. Les paramètres d'usine de l'appareil inscrit ne sont pas rétablis et aucun utilisateur n'y est affilié. Cette méthode oblige l’administrateur à connecter par voie USB l’appareil iOS à un ordinateur Mac qui exécute Apple Configurator pour inscrire l’appareil. [Inscrire des appareils iOS en utilisant l’inscription directe Apple Configurator](ios-direct-enrollment-in-microsoft-intune.md)

-   **Device Enrollment Program (DEP)** : déploie un profil d’inscription « à distance » sur des appareils achetés par le biais du programme DEP d’Apple. Quand l’utilisateur exécute l’Assistant Configuration sur l’appareil, celui-ci est inscrit dans Intune.  Les appareils inscrits via le programme DEP ne peuvent pas être désinscrits par les utilisateurs. [Inscrire des appareils iOS DEP](ios-device-enrollment-program-in-microsoft-intune.md)




### Voir aussi
[Se préparer à inscrire des appareils dans Microsoft Intune](get-ready-to-enroll-devices-in-microsoft-intune.md)


<!--HONumber=May16_HO1-->


