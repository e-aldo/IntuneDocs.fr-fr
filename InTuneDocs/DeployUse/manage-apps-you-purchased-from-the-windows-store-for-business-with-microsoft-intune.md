---
# required metadata

title: Gérer les applications que vous avez achetées dans le Windows Store pour Entreprises | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 8e38d47d-0c5e-40ce-b379-29d3657f5c28

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Gérer les applications que vous avez achetées dans le Windows Store pour Entreprises avec Microsoft Intune
[Windows Store pour Entreprises](https://www.microsoft.com/business-store) propose un lieu dans lequel vous pouvez trouver et acheter des applications pour votre organisation, individuellement ou par lots. En connectant le magasin à Microsoft Intune, vous pouvez gérer les applications achetées par lots depuis la console Intune, par exemple :
* Vous pouvez synchroniser la liste des applications que vous avez achetées dans le magasin avec Intune.
* Les applications qui sont synchronisées apparaissent dans la console d’administration Intune et vous pouvez les déployer comme toute autre application
* Vous pouvez suivre le nombre de licences disponibles, et la quantité utilisée dans la console d’administration Intune
* Intune bloque le déploiement et l’installation des applications s’il n’y a pas suffisamment de licences disponibles

## Avant de commencer
Passez en revue les informations suivantes avant de commencer la synchronisation et le déploiement des applications depuis Windows Store pour Entreprises :
* Vous devez configurer Intune comme autorité de gestion des appareils mobiles pour votre organisation. Pour plus d’informations, consultez [Se préparer à inscrire des appareils dans Microsoft Intune](get-ready-to-enroll-devices-in-microsoft-intune.md)
* Vous devez disposer d’un compte sur Windows Store Entreprises
* Une fois que vous avez associé un compte Windows Business Store avec Intune, vous ne pouvez pas basculer sur un autre compte ultérieurement.
* Les applications achetées depuis le magasin ne peuvent pas être manuellement ajoutées ou supprimées d’Intune. Elles peuvent uniquement être synchronisées avec Windows Store pour Entreprises.
* Intune synchronise uniquement les applications sous licence en ligne que vous avez achetées auprès de Windows Store pour Entreprises.
* Les appareils doivent être joints à un domaine Active Directory ou à un espace de travail pour pouvoir utiliser cette fonctionnalité.
* Les appareils inscrits doivent utiliser la version 1511 de Windows 10.

## Associer votre compte Windows Store pour Entreprises à Intune
Avant d’activer la synchronisation dans la console Intune, vous devez configurer votre compte de magasin pour utiliser Intune comme outil de gestion :
1. Veillez à vous connecter à Business Store avec le même compte de locataire que pour Intune.
2. Dans Business Store, choisissez **Paramètres** > **Outils de gestion**.
3. Sur la page Outils de gestion, choisissez **Ajouter un outil de gestion**, puis choisissez Microsoft Intune.

Vous pouvez maintenant continuer et configurer la synchronisation dans la console Intune.

## Configuration de la synchronisation

1. Dans la [console d’administration Microsoft Intune](https://manage.microsoft.com), cliquez sur **Administration**.
2. Dans l’espace de travail **Administration**, développez **Gestion des appareils mobiles**, puis cliquez sur **Store Pro**.
3. Sur la page **Windows Store pour Entreprises**, procédez comme suit :
* Si vous ne l’avez pas déjà fait, cliquez sur le lien pour vous inscrire pour Windows Store pour Entreprises
* Une fois l’inscription effectuée, cliquez sur **Configurer la synchronisation**
4. Dans la boîte de dialogue **Configurer la synchronisation des applications du Windows Store Pro**, sélectionnez **Activer la synchronisation du Windows Store Pro**.
5. Dans la liste déroulante **Langue**, choisissez la langue dans laquelle les applications de Windows Store pour Entreprises s’afficheront dans la console Intune. Quelle que soit la langue dans laquelle elles sont affichées, elles seront installées dans la langue de l’utilisateur final lorsqu’elles sont disponibles.
6. Cliquez sur **OK**.

## Synchroniser les applications

1. Sur la page **Windows Store pour Entreprises**, cliquez sur **Synchroniser maintenant** pour synchroniser les applications que vous avez achetées dans le magasin avec Intune.
2. Dans l’espace de travail **Applications**, cliquez sur **Logiciels gérés** > **Logiciels sous licence** pour afficher les applications disponibles et vérifier que vos applications achetées ont bien été importées.
Les applications de ce nœud s’affichent avec le nombre total de licences que vous possédez, ainsi que le nombre de licences disponibles.

## Déployer des applications

Vous déployez des applications à partir du magasin de la même façon que vous déploieriez toute autre application Intune. Pour plus d’informations, consultez [Déployer des applications dans Microsoft Intune](deploy-apps-in-microsoft-intune.md).
Lorsque vous déployez une application Windows Store pour Entreprises, une licence est utilisée par chaque utilisateur qui installe l’application. Si vous utilisez toutes les licences disponibles pour une application déployée, vous ne pourrez plus déployer d’autres copies et devrez prendre une des mesures suivantes :
* Désinstaller l’application de certains appareils
* Réduire la portée du déploiement actuel pour cibler uniquement les utilisateurs pour lesquels vous avez suffisamment de licences
* Acheter plus de copies de l’application dans Windows Store pour Entreprises


### Voir aussi
[Ajouter des applications pour des appareils mobiles dans Microsoft Intune](add-apps-for-mobile-devices-in-microsoft-intune.md)




<!--HONumber=Jun16_HO1-->


