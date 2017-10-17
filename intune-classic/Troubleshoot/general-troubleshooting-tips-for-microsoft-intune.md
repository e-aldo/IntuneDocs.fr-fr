---
title: "Conseils généraux de dépannage"
description: "Cette rubrique contient des ressources générales pour vous aider à résoudre les problèmes touchant Intune."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 12/08/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c86a4e4a-6b9f-4835-a3d3-61a3f5f4c1ec
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: tscott
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 7085429b8e3e9e7dff3b56e681fb425c6551d722
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/10/2017
---
# <a name="general-troubleshooting-tips-for-microsoft-intune"></a>Conseils généraux de dépannage pour Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Après avoir déployé Microsoft Intune, vous rencontrerez peut-être quelques problèmes liés à la configuration ou aux appareils clients. Utilisez les ressources suivantes pour vous aider à découvrir l’origine du problème afin de le résoudre.

> [!NOTE]
> Pour créer une demande de support technique ou examiner une demande existante, [visitez le centre d’administration Office 365](https://portal.office.com/admin/default.aspx). Pour plus d’informations sur les options de support technique, consultez [Comment obtenir un support technique pour Microsoft Intune](how-to-get-support-for-microsoft-intune.md).

## <a name="define-the-problem"></a>Définir le problème

-   Quel est le comportement ?

-   Qui rencontre ce comportement, et sur quelles plateformes et quels appareils ?

-   L’appareil fonctionnait-il correctement auparavant ?

-   Quelles modifications avez-vous apportées à la configuration d’Intune ou de l’appareil ?

-   D’autres modifications ont-elles été apportées à l’environnement dans lequel vous travaillez, hormis des modifications de configuration ?

-   Ce problème se produit-il souvent ? Est-il sporadique ou régulier ?

-   Se pourrait-il que l’utilisateur rencontre un problème d’authentification ? Si c’est une éventualité, vérifiez si l’utilisateur peut se connecter à d’autres services qui utilisent Azure Active Directory. Vérifiez également si l’utilisateur peut se connecter à partir d’un autre appareil.

-   Avez-vous vérifié l’état du service ? Vous pouvez surveiller l’état du service Intune dans le [portail de gestion Office 365](https://portal.office.com/Admin/Default.aspx). Choisissez **État du service** dans le volet gauche.

## <a name="collect-available-data"></a>Collecter les données disponibles

-   Les ressources suivantes expliquent comment collecter les journaux de l’appareil :
  - [Envoyer les journaux de données de diagnostic Android à votre administrateur informatique en utilisant un câble USB](/intune-user-help/send-diagnostic-data-logs-to-your-it-administrator-using-a-usb-cable-android)
  - [Envoyer les journaux de données de diagnostic Android à votre administrateur informatique par e-mail](/intune-user-help/send-diagnostic-data-logs-to-your-it-administrator-using-email-android)
  - [Envoyer les erreurs d’inscription Android à votre administrateur informatique](/intune-user-help/send-enrollment-errors-to-your-it-administrator-android)
  - [Envoyer les erreurs d’inscription iOS à votre administrateur informatique](/intune-user-help/send-errors-to-your-it-admin-ios)

-   Avec les données de la console d’administration (par exemple, pour les problèmes d’implémentation de stratégie), examinez la stratégie concernée et son état, comme décrit dans [Utiliser des groupes pour gérer les utilisateurs et les appareils avec Microsoft Intune](/intune-classic/deploy-use/use-groups-to-manage-users-and-devices-with-microsoft-intune).

## <a name="research-the-solution"></a>Rechercher la solution

-   Recherchez une solution sur le web. Par exemple, si vous recevez l’erreur 0x80073CF0, recherchez **technet intune 0x80073cf0** sur le web pour accéder à l’article [Résoudre les problèmes de déploiement d’applications dans Microsoft Intune](troubleshoot-app-deployment-problems-in-microsoft-intune.md). Cet article propose des suggestions pour résoudre ce problème.

-   Recherchez une réponse sur le [forum Intune TechNet](https://social.technet.microsoft.com/Forums/en-US/home?forum=microsoftintuneprod).  Si ce problème n’a pas encore été traité, soumettez la question aux utilisateurs de la communauté pour obtenir des suggestions.

-   Ouvrez une demande de support technique. Le Support technique Intune pourra mieux vous aider à résoudre votre problème une fois que vous l’aurez clairement défini et que vous aurez recueilli les données disponibles.

    Pour créer une demande de support technique, [visitez le Centre d’administration Office 365](https://portal.office.com/admin/default.aspx). Pour plus d’informations sur les options de support technique, consultez [Comment obtenir un support technique pour Microsoft Intune](how-to-get-support-for-microsoft-intune.md).

## <a name="find-community-resources"></a>Rechercher des ressources de la communauté
Vous trouverez d’autres informations utiles dans ces ressources de communauté :

-   Le [Guide de survie Microsoft Intune](http://social.technet.microsoft.com/wiki/contents/articles/23431.microsoft-intune-survival-guide.aspx) contient des liens vers de nombreuses ressources qui peuvent vous aider à configurer, gérer et dépanner Intune.

-   [Blog Intune](http://blogs.technet.com/b/windowsintune/)

-   [Suivez Intune sur Twitter](https://twitter.com/MSIntune)

-   [Forums Intune](https://social.technet.microsoft.com/Forums/home?category=microsoftintune&filter=alltypes&sort=lastpostdesc)

### <a name="next-steps"></a>Étapes suivantes
Les rubriques suivantes proposent une aide à la résolution de problèmes spécifiques. Si ces informations ne vous aident pas, contactez le support technique de Microsoft comme décrit dans [Comment obtenir un support technique pour Microsoft Intune](how-to-get-support-for-microsoft-intune.md).

[Résoudre les problèmes de protection de point de terminaison dans Microsoft Intune](troubleshoot-endpoint-protection-in-microsoft-intune.md)

[Résoudre les problèmes d’accès aux ressources d’entreprise avec Microsoft Intune](troubleshoot-company-resource-access-problems-with-microsoft-intune.md)

[Résoudre les problèmes de déploiement d’applications dans Microsoft Intune](troubleshoot-app-deployment-problems-in-microsoft-intune.md)

[Résoudre les problèmes d’inscription d’appareils dans Intune](troubleshoot-device-enrollment-in-intune.md)

[Résoudre les problèmes de stratégie dans Microsoft Intune](troubleshoot-policies-in-microsoft-intune.md)

[Résoudre les problèmes d’installation du client dans Microsoft Intune](troubleshoot-client-setup-in-microsoft-intune.md)

[Résoudre les problèmes de mise à jour logicielle dans Microsoft Intune](troubleshoot-software-updates-in-microsoft-intune.md)
