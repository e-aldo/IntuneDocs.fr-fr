---
title: "Protéger les données et les applications | Microsoft Intune"
description: 
keywords: 
author: karthikaraman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5c46e188-87eb-4ce2-b184-24809e8bf783
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ded7bd6c971a9448ad6e6492ebc5e42dfcb5d76e
ms.openlocfilehash: 9445b4b171eb2102d73cf0e866e85b535274eee2


---

# Protéger les données et les applications avec Microsoft Intune


Intune protège les données d’entreprise à travers plusieurs couches de technologie.
  Dans la couche d’identité, un accès conditionnel protège l’accès aux services en autorisant uniquement l’accès à partir d’appareils conformes et gérés.  Dans la couche d’application client, la gestion des applications mobiles (GAM) protège contre la perte de données en empêchant le déplacement de données vers des applications ou des emplacements de stockage non protégés et en effaçant les données lorsqu’un appareil est perdu ou volé.  Ces deux couches de protection doivent être utilisées ensemble afin de sécuriser les données tout en préservant la productivité de votre personnel mobile.

Une première étape importante pour la protection des données de l’entreprise consiste à implémenter un accès conditionnel en s’assurant que les appareils utilisés pour accéder à ces données utilisent des protections de sécurité (mot de passe fort, chiffrement) et ne sont pas jailbreakés. Microsoft Intune vous permet de définir les conditions auxquelles les appareils doivent se conformer pour être autorisés à accéder à la messagerie et aux données de l’entreprise.

L[’accès conditionnel](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) est déterminé par deux types de stratégies que vous pouvez définir dans Intune :
- [Les stratégies de conformité](introduction-to-device-compliance-policies-in-microsoft-intune.md) déterminent la conformité d’un appareil. Elles évaluent les paramètres et les conditions telles que :
  - Code confidentiel et mot de passe : vous pouvez créer des règles exigeant un mot de passe pour déverrouiller un appareil et définir les exigences de complexité du mot de passe ainsi que d’autres paramètres associés.
  - Chiffrement : vous pouvez restreindre l’accès aux appareils chiffrés.
  - Appareil non jailbreaké ou rooté : Intune peut déterminer si un appareil inscrit est jailbreaké et vous pouvez définir une stratégie pour bloquer l’accès à ces appareils.
- [Les stratégies d’accès conditionnel](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) sont configurées pour un service particulier comme Exchange Online ou SharePoint Online. Pour chaque service, vous pouvez définir les groupes d’utilisateurs auxquels ces stratégies doivent s’appliquer. Par exemple, vous pouvez faire en sorte que tous les employés du service financier ne puissent accéder à la messagerie professionnelle qu’à partir d’appareil inscrits et conformes.

La sécurisation de l’accès aux ressources de l’entreprise n’est que la première étape de protection des données de l’entreprise. Vous devez également être en mesure de protéger les données une fois qu’un appareil y a accédé. Les données peuvent être copiées, déplacées, enregistrées dans un emplacement différent ou partagées. Intune résout ce problème en vous offrant la possibilité de limiter le déplacement des données grâce à un ensemble de règles du type :
- Bloquer les copier-coller ou empêcher le transfert de données en dehors du contexte professionnel.
- Empêcher la sauvegarde dans un stockage cloud personnel, bloquer la fonctionnalité Enregistrer sous.
- Sécuriser l’accès aux applications en demandant un code confidentiel/code secret ou des informations d’identification d’entreprise.
- Ouvrir tous les liens web dans Intune Managed Browser.

Ces règles sont appelées [stratégies de gestion des applications mobiles (GAM)](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md).  Les stratégies de GAM peuvent être appliquées à des applications qui s’exécutent sur des appareils gérés ou non par vous.  Vous pouvez protéger vos données d’entreprise à l’aide de stratégies de GAM sur les appareils inscrits dans Intune, inscrits et gérés par un système de GPM tiers ou encore non gérés par vous, par exemple les appareils des employés.

Pour associer une application à une stratégie de GAM, l’application doit intégrer le Kit de développement logiciel (SDK) Microsoft Intune App ou utiliser App Wrapping Tool.

Certaines applications, par exemple les applications Microsoft Office, intègrent le SDK App. Vous trouverez la liste complète des applications prises en charge dans la [Galerie d’applications mobiles Microsoft Intune](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx) sur la page de d’applications partenaires de Microsoft Intune. Sélectionnez une application pour afficher les scénarios pris en charge, connaître les plateformes et savoir si elle prend en charge les identités multiples.

Vous pouvez également [activer les stratégies de GAM sur vos applications métier personnalisées](decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune.md).

En plus de restreindre le déplacement des données si un appareil est perdu ou volé ou que l’utilisateur ne travaille plus avec votre entreprise, vous pouvez [effacer de façon sélective des données de la société](wipe-managed-company-app-data-with-microsoft-intune.md) et laisser uniquement les données personnelles.



<!--HONumber=Jun16_HO4-->


