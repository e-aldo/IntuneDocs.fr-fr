---
title: "Utilisations courantes d’Intune | Microsoft Intune"
description: "Répertorie six des tâches les plus courantes pour lesquelles Intune vous aide."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 09/06/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1f37d4ff-b5a7-4a89-8884-a6184908b09c
ms.reviewer: robstackmsft
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: a4f7a503417938eabb4334757dcf12a63f082fd3
ms.openlocfilehash: 71e06c6d792440e8fedff0078881a10b0ce0d862


---

# Utilisations courantes d’Intune

Avant de vous plonger dans des tâches d’implémentation, il est important d’aligner les parties prenantes de la mobilité d’entreprise avec vos objectifs professionnels.  Ceci est important que vous débutiez dans la mobilité d’entreprise ou que vous effectuiez une migration à partir d’un autre produit.  Les besoins en matière de mobilité d’entreprise évoluent de manière dynamique, et l’approche de Microsoft pour répondre à ces besoins peut parfois différer des autres solutions disponibles sur le marché.  La meilleure façon de s’aligner avec les objectifs professionnels consiste à exprimer ce que vous souhaitez accomplir en termes des scénarios que vous souhaitez activer pour vos employés, partenaires et service informatique.  Voici quelques courtes introductions au six scénarios les plus courants qui s’appuient sur Intune, accompagnées de liens vers d’autres informations sur la façon de planifier et de déployer chacun d’eux.

>[!NOTE]
>Vous souhaitez savoir comment Microsoft IT utilise Intune pour permettre aux employés de Microsoft d’accéder aux ressources d’entreprise sur leurs appareils mobiles tout en garantissant la protection des données d’entreprise ? [Lisez cette étude de cas technique](https://www.microsoft.com/itshowcase/Article/Content/588) pour découvrir en détail comment Microsoft IT utilise Intune et d’autres services pour gérer les identités, appareils, applications et données.  

>[!IMPORTANT]
>S’assurer que les appareils mobiles sont à jour<br>
>Suite aux récentes attaques des programmes malveillants « Trident » sur les appareils iOS, nous avons publié un nouveau billet de blog, [S’assurer que les appareils mobiles sont à jour avec Microsoft Intune](https://blogs.technet.microsoft.com/enterprisemobility/2016/08/26/ensuring-mobile-devices-are-up-to-date-using-microsoft-intune/), pour vous permettre de découvrir comment Intune peut vous aider à garder des appareils sécurisés et à jour.

## Sécurisation de votre messagerie et de vos données locales pour qu’elles soient accessibles en toute sécurité par les appareils mobiles
La plupart des stratégies de mobilité d’entreprise commencent par un plan pour permettre aux employés munis d’appareils mobiles d’accéder de manière sécurisé à la messagerie électronique par le biais d’internet. De nombreuses organisations hébergent encore des données et des serveurs d’applications locaux, tels que Microsoft Exchange, sur leur réseau d’entreprise. Intune et Microsoft Enterprise Mobility + Security (EMS) fournissent une [solution d’accès conditionnel](/intune/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune) intégrée unique pour Exchange Server qui garantit qu’aucune application mobile ne peut accéder à l’e-mail tant que l’appareil n’a pas été inscrit avec Intune, tout ceci sans déployer un autre ordinateur passerelle à la périphérie de votre réseau d’entreprise.

Outre la messagerie électronique, Intune prend en charge l’activation de l’accès aux applications mobiles qui nécessitent un accès sécurisé aux données locales, comme un serveur d’applications métier.  Des [certificats gérés par Intune](/intune/deploy-use/secure-resource-access-with-certificate-profiles) sont généralement utilisés pour le contrôle d’accès, combinés à une passerelle VPN standard ou à un proxy dans le périmètre (tel que le Proxy d’application Microsoft Azure AD).  Dans ce cas, la seule façon d’accéder aux données d’entreprise consiste à inscrire l’appareil pour la gestion.  Une fois l’inscription effectuée, le système de gestion s’assure que les appareils qui accèdent aux données d’entreprise sont conformes à vos stratégies.  Vous pouvez également utiliser [l’Outil de création de package de restrictions d’application et le Kit App SDK](/intune/deploy-use/decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune) Intune pour contenir les données accessibles de votre application métier et que celle-ci ne puisse pas passer de données d’entreprise à des applications ou des services de particuliers.

<!-- Learn more about how to plan and deploy Intune to help secure on-premises email and data. -->

## Sécurisation de votre messagerie et de vos données Office 365 pour qu’elles soient accessibles en toute sécurité par les appareils mobiles
La protection des données d’entreprise dans Office 365 (messagerie, documents, messages instantanés, contacts) ne pourrait pas être plus facile pour vous ou plus transparente pour vos utilisateurs. Intune et Microsoft Enterprise Mobility + Security fournissent une solution d’accès conditionnel intégrée unique qui garantit qu’aucun utilisateur, appareil ou application ne peut accéder aux données Office 365 s’ils ne répondent pas aux exigences de conformité de votre entreprise (exécution de l’[authentification multifacteur](/intune/deploy-use/protect-windows-devices-with-multi-factor-authentication), inscription avec Intune, utilisation d’une application gérée, version de système d’exploitation prise en charge, code confidentiel d’appareil, profil utilisateur à faible risque, etc.). Les applications mobiles Office disponibles dans leurs magasins d’applications respectifs sont prêtes à l’emploi avec des stratégies de relation contenant-contenu de données que vous pouvez configurer par le biais d’Intune, ce qui vous permet d’empêcher le partage des données avec des applications (par exemple une application de messagerie native) et des emplacements de stockage (comme Dropbox) qui ne sont pas gérés par votre service informatique.  Toutes ces fonctionnalités sont intégrées à Office 365 et EMS.  Vous n’avez aucune infrastructure supplémentaire à déployer.

Une pratique de déploiement Office 365 courante consiste à exiger l’inscription des appareils si des configurations d’applications/certificats/Wi-Fi/VPN d’entreprise doivent être configurées dessus, ce qui est souvent le cas pour les appareils d’entreprise.  Toutefois, si l’utilisateur doit simplement accéder aux e-mails et aux documents d’entreprise, ce qui est souvent le cas pour les appareils personnels, il doit utiliser les applications mobiles Office (auxquelles vous avez [appliqué des règles de relation contenant-contenu de données](/intune/deploy-use/protect-apps-and-data-with-microsoft-intune)) et ignorer entièrement l’inscription de l’appareil.  Dans les deux cas, les données Office 365 seront sécurisées par des stratégies que vous aurez définies.

<!-- Learn more about how to plan and deploy Intune to help secure Office 365 email and data. -->

## Offrir un programme BYOD (Apportez votre propre appareil) à tous les employés
BYOD continue de croître en popularité comme approche visant à réduire les dépenses en matériel ou à augmenter les choix de productivité mobile pour les employés. De nos jours, presque tout le monde a un téléphone personnel. Pourquoi en mettre un autre dans leur poche ? Le défi principal a toujours été de convaincre les employés d’inscrire leur appareil personnel pour la gestion, car ils s’inquiètent de ce que leur service informatique pourra voir et faire avec leur appareil.  

Quand l’inscription d’appareil n’est pas une option viable, Intune propose une autre approche BYOD consistant simplement à [gérer les applications qui contiennent des données d’entreprise](/intune/deploy-use/protect-apps-and-data-with-microsoft-intune).  Intune protège les données d’entreprise même si l’application en question accède à la fois à des données personnelles et des données d’entreprise, comme c’est le cas pour les applications mobiles Office.  En tant qu’administrateur, vous pouvez exiger des utilisateurs qu’ils accèdent à Office 365 à partir des applications mobiles Office et configurer les applications avec des stratégies de protection des données (chiffrement, protection par code confidentiel, et ainsi de suite).  Ces stratégies évitent la fuite de données vers des applications et des emplacements de stockage non gérés, que ce soit à l’intérieur ou en dehors de ces applications.  Par exemple, les stratégies empêcheront un utilisateur de copier du texte à partir d’un profil de messagerie d’entreprise vers un profil de messagerie privé même si ces deux profils sont configurés dans Outlook Mobile.  Vous pouvez déployer des configurations similaires pour d’autres services et applications dont vos utilisateurs BYOD ont besoin.

<!-- Learn more about how to plan and deploy Intune to support BYOD.-->

## Délivrer des téléphones d’entreprise aux travailleurs de l’information
De nos jours, la plupart des travailleurs de l’information sont mobiles. La productivité sur les appareils mobiles est donc un impératif de compétitivité.  Ces employés doivent pouvoir accéder de manière transparente à toutes les applications et données d’entreprise, à tout moment, où qu’ils se trouvent.  Vous devez garantir la sécurité des données d’entreprise et limiter les coûts d’administration.  

Intune propose des [solutions de configuration et de gestion en bloc ](/intune/deploy-use/manage-corporate-owned-devices)qui sont intégrées aux principales plateformes de gestion d’appareils d’entreprise disponibles aujourd’hui sur le marché, notamment le Programme DEP Apple et la plateforme de sécurité mobile Samsung KNOX.  La création centralisée de configurations d’appareils avec Intune peut faire de la mise en service des appareils d’entreprise une tâche hautement automatisée.  

Imaginez : vous remettez à un employé un iPhone dans son emballage d’origine. L’employé le met sous tension et suit un flux d’installation propre à l’entreprise qui lui impose de s’authentifier. L’iPhone est configuré en toute transparence avec des [stratégies de sécurité](/intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies) (chiffrement de disque dur, code confidentiel d’appareil, etc), des [profils d’e-mail/Wi-Fi/VPN/certificat](/intune/deploy-use/enable-access-to-company-resources-with-microsoft-intune) et un groupe d’[applications](/intune/deploy-use/add-apps) de référence. Ensuite, l’employé lance l’application Portail d’entreprise Intune pour accéder aux applications d’entreprise facultatives mises à sa disposition.

<!-- Learn more about how to plan and deploy Intune to support corporate owned devices. -->

## Délivrer des tablettes partagées à utilisation limitée à vos employés
Les employés utilisent de plus en plus les technologies mobiles.  Par exemple, les tablettes partagées sont désormais courantes parmi les employés de magasins de vente au détail.  Qu’elles servent à traiter une vente ou à vérifier instantanément le stock, les tablettes aident à créer de riches interactions avec les clients.  Dans ce cas, la simplicité de l’expérience utilisateur est essentielle.  Pour cette raison, les tablettes sont généralement délivrées aux employés dans un mode d’utilisation limitée (par exemple, l’employé ne peut interagir qu’avec une application métier).  Avec Intune, vous pouvez centraliser la configuration, la sécurisation et la gestion de ces tablettes [iOS](/intune/deploy-use/ios-policy-settings-in-microsoft-intune#general-configuration-policy-settings) et [Android](/intune/deploy-use/android-policy-settings-in-microsoft-intune#general-configuration-policy) partagées qui peuvent être configurées pour s’exécuter dans ce mode d’utilisation limitée.

<!-- Learn more about how to plan and deploy Intune to support shared tablets. -->

## Permettre à vos employés d’accéder en toute sécurité à Office 365 à partir d’une borne publique non gérée
Vos employés doivent parfois utiliser des appareils, applications ou navigateurs que vous ne pouvez pas gérer, tels que des ordinateurs publics disponibles lors de salons commerciaux et dans des hôtels. Devez-vous autoriser vos employés à accéder aux e-mails de l’entreprise à partir de ces ordinateurs ? Avec Intune et Microsoft Enterprise Mobility + Security, <!--you have choices. The--> la réponse ne peut être que « non » en [limitant l’accès aux e-mails aux appareils qui sont gérés par votre organisation](/intune/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune).  <!-- Alternatively, you can choose to allow limited access to these untrusted computers by requiring multi-factor authentication and only allowing browser access (Outlook Web Access) in a mode where files cannot be downloaded (e.g. email attachments).-->  Ainsi, vos employés fortement authentifiés ne risqueront pas de laisser accidentellement des données d’entreprise sur l’ordinateur non approuvé.

<!-- Learn more about how to plan and deploy Intune to support kiosks. -->



<!--HONumber=Oct16_HO4-->


