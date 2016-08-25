---
title: "Conseils généraux de dépannage | Microsoft Intune"
description: "Cette rubrique contient des ressources générales pour vous aider à résoudre les problèmes touchant Intune."
keywords: 
author: nbigman
manager: angrobe
ms.date: 07/21/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c86a4e4a-6b9f-4835-a3d3-61a3f5f4c1ec
ms.reviewer: tscott
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 9915b275101e287498217c4f35e1c0e56d2425c2
ms.openlocfilehash: d321930262a9bcf9542c757fdf0b945d0419930c


---

# Conseils généraux de dépannage pour Microsoft Intune
Après avoir déployé Microsoft Intune, il se peut que vous rencontriez quelques problèmes liés à la configuration ou aux clients. Les ressources ci-dessous peuvent vous aider à identifier la cause du problème.

> [!NOTE]
> Pour créer une demande de support technique ou examiner une demande existante, [visitez le centre d’administration Office 365](https://portal.office.com/admin/default.aspx). Pour plus d’informations sur les options de support technique, consultez [Comment obtenir un support technique pour Microsoft Intune](how-to-get-support-for-microsoft-intune.md).
## Définir le problème

-   Quel est le comportement ?

-   Qui rencontre ce comportement, et sur quelles plateformes et quels appareils ?

-   L’appareil fonctionnait-il correctement auparavant ?

-   Quelles modifications avez-vous apportées à la configuration d’Intune ou de l’appareil ?

-   Essayez de savoir si d’autres modifications ont été apportées à l’environnement dans lequel vous travaillez, hormis des modifications de configuration.

-   Ce problème se produit-il souvent ? Est-il sporadique ou régulier ?

-   Se pourrait-il que l’utilisateur rencontre un problème d’authentification ? Si c’est une éventualité, vérifiez si l’utilisateur peut se connecter à d’autres services qui utilisent Azure Active Directory. Vérifiez également si l’utilisateur peut se connecter à partir d’un autre appareil.

-   Avez-vous vérifié l’état du service ? Vous pouvez surveiller l’état du service Intune dans le [portail de gestion Office 365](https://portal.office.com/Admin/Default.aspx). Choisissez **État du service** dans le volet gauche.

## Collecter les données disponibles

-   Journaux des appareils. Découvrez comment collecter les journaux de l’appareil dans :
  - [Envoyer les journaux de données de diagnostic Android à votre administrateur informatique par câble USB](/intune/enduser/send-diagnostic-data-logs-to-your-it-administrator-using-a-usb-cable-android)
  - [Envoyer les journaux de données de diagnostic Android à votre administrateur informatique par e-mail](/intune/enduser/send-diagnostic-data-logs-to-your-it-administrator-using-email-android)
  - [Envoyer les erreurs d’inscription Android à votre administrateur informatique](/intune/enduser/send-enrollment-errors-to-your-it-administrator-android)
  - [Envoyer les erreurs d’inscription iOS à votre administrateur informatique](/intune/enduser/send-errors-to-your-it-admin-ios)

-   Données de la console d’administration. Par exemple, pour les problèmes d’implémentation de stratégie, vous devez examiner la stratégie concernée et son état, comme décrit dans [Utiliser des groupes pour gérer les utilisateurs et les appareils avec Microsoft Intune](/intune/deploy-use/use-groups-to-manage-users-and-devices-with-microsoft-intune).

## Rechercher la solution

-   Recherchez une solution sur le web. Par exemple, si vous recevez l’erreur 0x80073CF0, vous pouvez rechercher **technet intune 0x80073cf0** sur le web pour accéder à l’article [Résoudre les problèmes de déploiement d’applications dans Microsoft Intune](troubleshoot-app-deployment-problems-in-microsoft-intune.md), qui contient des suggestions pour résoudre ce problème.

-   Vous pouvez rechercher une réponse dans le [forum Intune TechNet](https://social.technet.microsoft.com/Forums/en-US/home?forum=microsoftintuneprod).  Si ce problème n’a pas encore été traité, soumettez la question aux utilisateurs de la communauté pour obtenir des suggestions.

-   Vous pouvez ouvrir une demande de support technique. Le Support technique Intune pourra mieux vous aider à résoudre votre problème si vous l’avez clairement défini et que vous avez recueilli les données disponibles.

    Pour créer une demande de support technique, [visitez le Centre d’administration Office 365](https://portal.office.com/admin/default.aspx). Pour plus d’informations sur les options de support technique, consultez [Comment obtenir un support technique pour Microsoft Intune](how-to-get-support-for-microsoft-intune.md).

## Ressources de la communauté
Vous trouverez d’autres informations utiles dans ces ressources de communauté :

-   Le [Guide de survie Microsoft Intune](http://social.technet.microsoft.com/wiki/contents/articles/23431.microsoft-intune-survival-guide.aspx) contient des liens vers de nombreuses ressources qui peuvent vous aider à configurer, gérer et dépanner Intune.

-   [Le blog Intune](http://blogs.technet.com/b/windowsintune/)

-   [Suivez Intune sur Twitter](https://twitter.com/MSIntune)

-   [Les forums Intune](https://social.technet.microsoft.com/Forums/home?category=microsoftintune&filter=alltypes&sort=lastpostdesc)

### Étapes suivantes
Les rubriques répertoriées ci-dessous proposent une aide à la résolution de problèmes spécifiques. Si ces informations ne vous aident pas, contactez le support technique de Microsoft comme décrit dans [Comment obtenir un support technique pour Microsoft Intune](how-to-get-support-for-microsoft-intune.md).

[Troubleshoot Endpoint Protection in Microsoft Intune](troubleshoot-endpoint-protection-in-microsoft-intune.md)

[Résoudre les problèmes d’accès aux ressources d’entreprise avec Microsoft Intune](troubleshoot-company-resource-access-problems-with-microsoft-intune.md)

[Résoudre les problèmes de déploiement d’applications dans Microsoft Intune](troubleshoot-app-deployment-problems-in-microsoft-intune.md)

[Résoudre les problèmes d’inscription d’appareils dans Intune](troubleshoot-device-enrollment-in-intune.md)

[Résoudre les problèmes de stratégie dans Microsoft Intune](troubleshoot-policies-in-microsoft-intune.md)

[Résolution des problèmes d’installation du client dans Microsoft Intune](troubleshoot-client-setup-in-microsoft-intune.md)

[Résoudre les problèmes de mise à jour logicielle dans Microsoft Intune](troubleshoot-software-updates-in-microsoft-intune.md)



<!--HONumber=Jul16_HO4-->


