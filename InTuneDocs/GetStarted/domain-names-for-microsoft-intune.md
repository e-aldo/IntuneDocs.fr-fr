---
# required metadata

title: Noms de domaine pour Microsoft Intune | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: c3c136f0-330d-432a-a91f-16f7dd097e55

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---



# Noms de domaine pour Microsoft Intune

Avant de configurer Microsoft Intune, consultez cette rubrique et les autres exigences recensées dans [Informations à connaître avant de commencer à utiliser Microsoft Intune](what-to-know-before-you-start-microsoft-intune.md).

Quand votre organisation s’inscrit à un service cloud Microsoft comme Intune, vous recevez un nom de domaine initial qui ressemble à celui-ci : **contoso.onmicrosoft.com**. Dans cet exemple, **contoso** est le nom de domaine que vous avez choisi lors de votre inscription et **onmicrosoft.com** est le suffixe attribué aux comptes que vous ajoutez à votre abonnement. Une fois l'inscription terminée, vous ne pouvez pas modifier ce nom de domaine. Toutefois, en tant qu'administrateur général, vous pouvez ajouter vos propres noms de domaine personnalisés pour que votre organisation les utilise avec le service ou supprimer des domaines ajoutés précédemment.

Par défaut, quand vous utilisez le domaine onmicrosoft, chaque utilisateur que vous importez reçoit le suffixe **onmicrosoft.com** pour son nom d’utilisateur principal (UPN).

Pour utiliser un nom de domaine que vous possédez au lieu de celui qui vous a été attribué à l’inscription, vous pouvez ajouter ce nom de domaine à Azure Active Directory. Une fois que vous avez ajouté le domaine et qu'il a été vérifié qu'il vous appartient, vous pouvez créer des comptes et des groupes qui incluent le nom de domaine en modifiant des enregistrements de ressource DNS auprès de votre fournisseur d'hébergement DNS. Pour simplifier la gestion des comptes d’utilisateur quand vous envisagez d’utiliser un domaine personnalisé, configurer un nom de domaine personnalisé pour votre abonnement avant de commencer à synchroniser des utilisateurs à partir de votre instance Active Directory locale.

La configuration des noms de domaine et des enregistrements de ressources DNS pour Intune est la même que pour d’autres clients Azure Active Directory. Pour obtenir des instructions, consultez [Ajout de votre nom de domaine personnalisé à Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-add-domain/).

### Voir aussi
[Informations à connaître avant de commencer à utiliser Microsoft Intune](what-to-know-before-you-start-microsoft-intune.md)


<!--HONumber=May16_HO1-->


