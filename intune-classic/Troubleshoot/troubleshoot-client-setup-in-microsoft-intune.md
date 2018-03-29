---
title: Résoudre les problèmes de configuration du client
description: Résolvez les problèmes de configuration de client courants.
keywords: ''
author: nathbarn
ms.author: nathbarn
manager: dougeby
ms.date: 02/22/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: e46d292b-1d16-46db-a87f-d53eefa4d22a
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: tscott
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: f9cb68fcac7abc895f51cf2c8758c2cf59b32759
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/22/2018
---
# <a name="troubleshoot-client-setup-in-microsoft-intune"></a>Résolution des problèmes d’installation du client dans Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Utilisez les informations suivantes pour vous aider à résoudre les problèmes courants de configuration du client. Si ces informations ne vous permettent pas de remédier à votre problème, consultez [Comment obtenir un support technique pour Microsoft Intune](how-to-get-support-for-microsoft-intune.md) pour accéder à d’autres types d’assistance.

## <a name="client-installation-fails"></a>Échec de l’installation du client

-   Si aucune alerte de déploiement du logiciel client pour l’ordinateur n’est affichée dans la [console d’administration Microsoft Intune](https://manage.microsoft.com/), vérifiez la connectivité Internet et la configuration du proxy de l’ordinateur, puis vérifiez que ce dernier peut communiquer avec l’URL du service, [https://manage.microsoft.com](https://manage.microsoft.com/). Ensuite, réessayez d'installer le logiciel client.

-   Vous pouvez envoyer un message électronique à une sélection de destinataires quand une alerte relative à l'échec du déploiement du logiciel client se produit en configurant une règle de notification dans l'espace de travail **Admin**. Pour plus d’informations, consultez [Recevoir des alertes Microsoft Intune](/intune-classic/deploy-use/get-notified-by-alerts).

-   Intune affiche l’alerte critique **Échec de déploiement du logiciel client** si le déploiement du logiciel client échoue. Elle s’affiche dans la page **Vue d’ensemble du système** et les pages **Alertes** de la [ console d’administration Microsoft Intune](https://manage.microsoft.com/). Voici comment vérifier les alertes :

1.  Dans la [console d’administration Microsoft Intune](https://manage.microsoft.com/), choisissez **Alertes** &gt; **Vue d’ensemble**.

2.  Dans la page **Vue d'ensemble des alertes**, vous pouvez vérifier les informations suivantes :

    -   Les trois alertes principales, qui peuvent être triées par date, catégorie ou gravité

    -   Le nombre total d'alertes actives

3.  Choisissez **Toutes les alertes** pour afficher les informations suivantes dans la page **Alertes**. Les alertes critiques sont affichées en premier :

    -   **Nom** : nom du type d'alerte qui a généré l'alerte.

    -   **Source** : lien vers la source de l'alerte.  Si le seuil d'affichage du type d'alerte est défini sur **Tout**, ce lien affichera un seul appareil concerné.  Si le seuil d'affichage du type d'alerte est défini sur une valeur, ce lien affichera la liste de tous les appareils concernés par cette alerte.

    -   **Dernière modification** : indique l'heure de la dernière modification de l'alerte. Si une alerte est fermée, la date et l'heure de sa fermeture sont affichées.

    -   **Gravité** : indique la gravité de l'alerte

## <a name="computer-enrollment-package-doesnt-download"></a>Le package d’inscription de l’ordinateur ne se télécharge pas
**Problème :** lors de la tentative d’inscription d’un ordinateur, vous rencontrez les problèmes suivants :
-  Le package d’inscription ne parvient pas à se télécharger
-  La boîte de dialogue de téléchargement s’affiche mais arrive à expiration

**Résolution :** dans le navigateur que vous utilisez pour le téléchargement, au moment où le téléchargement a lieu, vérifiez que les téléchargements sont activés et que les fichiers chiffrés peuvent être enregistrés sur votre disque local.

## <a name="client-installation-hangs-with-error-code-0x80040154"></a>L’installation du client se bloque avec le code d’erreur 0x80040154
**Problème :**

-  L’installation du client pendant l’inscription se bloque

-  Impossible d’inscrire l’appareil

-  Erreur 0x80040154 dans WindowsUpdate.log

Cela peut être dû à l’absence de mises à jour logicielles critiques sur le PC.

**Résolution :** Vérifiez que votre stratégie de mise à jour logicielle permet d’installer les mises à jour critiques, comme décrit dans [Maintenir des PC Windows à jour avec les mises à jour logicielles dans Microsoft Intune](/intune-classic/deploy-use/keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune)


## <a name="microsoft-intune-policy-related-errors-in-policyplatformlog"></a>Erreurs liées aux stratégies Microsoft Intune dans policyplatform.log
Pour les appareils Windows non soumis à la gestion des appareils mobiles, les erreurs de stratégie dans le fichier policyplatform.log peuvent être dues à des paramètres définis sur des valeurs autres que les valeurs par défaut dans le Contrôle de compte d’utilisateur Windows sur l’appareil. Certains paramètres de Contrôle de compte d’utilisateur autres que les paramètres par défaut peuvent affecter les installations du client Microsoft Intune et l’exécution des stratégies.

### <a name="to-resolve-uac-issues"></a>Pour résoudre les problèmes liés au Contrôle de compte d’utilisateur

1.  Mettez hors service l’ordinateur, comme décrit dans [Mettre hors service des données et des appareils en cas de gestion Microsoft Intune](/intune-classic/deploy-use/retire-devices-from-microsoft-intune-management).

2.  Attendez 20 minutes que le logiciel client soit supprimé.

    > [!NOTE]
    > N’essayez pas de supprimer le client à partir de Programmes et fonctionnalités.

3.  Dans le menu Démarrer, tapez **UAC** pour ouvrir les paramètres de Contrôle de compte d’utilisateur.

4.  Déplacez le curseur de notification sur le paramètre par défaut.

## <a name="what-to-do-if-the-client-will-not-uninstall-from-the-microsoft-intune-administrator-console"></a>Que faire si le client ne se désinstalle pas de la console d'administration Microsoft Intune ?

### <a name="to-remove-the-client-software-by-using-the-microsoft-intune-command-line-tool"></a>Pour supprimer le logiciel client à l'aide de l'outil de ligne de commande de Microsoft Intune

1.  Ouvrez une invite de commande en mode administrateur.

2.  Accédez au dossier *%programfiles%\Microsoft\OnlineManagement\Common*.

3.  Exécutez la commande suivante : ``ProvisioningUtil.exe /UninstallAgents /MicrosoftIntune``

## <a name="client-installation-error-codes"></a>Codes d'erreur d'installation du logiciel client
Le tableau suivant décrit les codes d'erreur indiqués dans l'espace de travail **Alertes** en cas d'échec de l'installation du logiciel client. Il inclut des suggestions pour résoudre le problème identifié par chaque code d'erreur.

|Code d'erreur|Problème possible|Solution suggérée|
|--------------|--------------------|------------------------|
|**0x80CF0437**|L'horloge de l'ordinateur client n'est pas réglée sur l'heure correcte.|Assurez-vous que l'horloge et le fuseau horaire de l'ordinateur client sont correctement réglés.|
|**0x80240438**, **0x80CF0438**, **0x80CF401B**|Impossible de se connecter au service Intune. Vérifiez les paramètres de proxy du client.|Vérifiez que la configuration du proxy sur l’ordinateur client est prise en charge par Intune et que l’ordinateur client dispose d’un accès à Internet. Pour plus d’informations sur les configurations de proxy prises en charge, consultez la page [Contribuer à la sécurisation des PC Windows avec Endpoint Protection pour Microsoft Intune](/intune-classic/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune).|
|**0x80CF402C**|Impossible de se connecter au service Intune. Vérifiez la connexion réseau.|Vérifiez que l'ordinateur dispose d'une connectivité réseau. Assurez-vous que le câble réseau est connecté ou que le réseau sans fil est activé.|
|**0x80240438, 0x80CF0438**|Les paramètres de proxy dans Internet Explorer et le système local ne sont pas configurés.|Vérifiez les paramètres de proxy du client et assurez-vous que la configuration proxy sur l’ordinateur client est prise en charge par Intune et que l’ordinateur client a accès à Internet. Pour plus d’informations sur les configurations de proxy prises en charge, consultez la page [Contribuer à la sécurisation des PC Windows avec Endpoint Protection pour Microsoft Intune](/intune-classic/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune).|
|**0x80043001**|Le package d'inscription n'est plus à jour.|Téléchargez et installez le package logiciel client le plus récent à partir de l'espace de travail **Admin**. Pour obtenir des instructions, consultez la rubrique [Installer le client de PC Windows avec Microsoft Intune](/intune-classic/deploy-use/install-the-windows-pc-client-with-microsoft-intune).|
|**0x80043004**|L'abonnement n'existe pas ou est désactivé.|Vérifiez que votre compte et votre abonnement à Intune sont toujours actifs. Pour afficher les paramètres de votre compte, connectez-vous à votre compte dans le [Centre d’administration Office 365](http://go.microsoft.com/fwlink/?LinkId=698854%20).|
|**0x80043002**|Le compte est en mode de maintenance.|Vous ne pouvez pas inscrire de nouveaux ordinateurs clients lorsque le compte est en mode de maintenance. Pour afficher les paramètres de votre compte, connectez-vous à votre compte dans le [Centre d’administration Office 365](http://go.microsoft.com/fwlink/?LinkId=698854%20).|
|**0x80043003**|Le compte a été supprimé.|Vérifiez que votre compte et votre abonnement à Intune sont toujours actifs. Pour afficher les paramètres de votre compte, connectez-vous à ce dernier.|
|**0x80043005**|L'ordinateur client est hors service.|Patientez quelques heures, supprimez les anciennes versions du logiciel client de l'ordinateur et essayez de le réinstaller. Pour obtenir des instructions, consultez **Que faire si le client ne se désinstalle pas de la console d’administration Microsoft Intune ?** plus haut.|
|**0x80043006**|Le nombre maximal de sièges autorisés pour le compte est atteint.|Votre entreprise doit acheter des sièges supplémentaires pour que vous puissiez inscrire davantage d'ordinateurs clients dans le service.|
|**0x80043007**|Impossible de trouver le fichier de certificat dans le même dossier que le programme d'installation.|Extrayez tous les fichiers avant de commencer l'installation. Ne renommez pas et ne déplacez pas les fichiers extraits : tous les fichiers doivent se trouver dans le même dossier sans quoi l'installation échouera. Pour plus d’informations, consultez [Installer le client de PC Windows avec Microsoft Intune](/intune-classic/deploy-use/install-the-windows-pc-client-with-microsoft-intune).|
|**0x8024D015**, **0x00240005**, **0x80070BC2**, **0x80070BC9**, **0x80CFD015**|Le logiciel ne peut pas être installé, car un redémarrage de l'ordinateur client est en attente.|Redémarrez l'ordinateur, puis réessayez d'installer le logiciel client.|
|**0x80070032**|Une ou plusieurs conditions requises pour l'installation du logiciel client n'ont pas été remplies au niveau de l'ordinateur.|Assurez-vous que toutes les mises à jour nécessaires sont installées sur l'ordinateur client, puis réessayez d'installer le logiciel client. Pour plus d’informations sur la configuration requise pour installer le logiciel client, consultez [Configuration requise de l’infrastructure réseau pour Microsoft Intune](/intune-classic/get-started/network-infrastructure-requirements-for-microsoft-intune).|
|**0x80043008**|Impossible de démarrer le service des mises à jour de Microsoft Online Management.|Contactez le support technique comme décrit dans [Comment obtenir un support technique pour Microsoft Intune](how-to-get-support-for-microsoft-intune.md).|
|**0x80043009**|L'ordinateur client est déjà inscrit dans le service.|Vous devez mettre hors service l'ordinateur client avant de le réinscrire dans le service. Pour obtenir des instructions, consultez [Mettre hors service des appareils en cas de gestion Microsoft Intune](/intune-classic/deploy-use/retire-devices-from-microsoft-intune-management).|
|**0x8004300A**|(Phase 21) Une erreur s’est produite lors du déploiement du package d’inscription sur l’objet de stratégie de groupe à installer pour l’étendue de l’utilisateur et non pour l’étendue de l’ordinateur. |Vérifiez que l’objet de stratégie de groupe est correctement ciblé via la technologie GPSI pour l’étendue de l’ordinateur. Pour consulter les publications de forum à ce sujet, consultez ce [Forum TechNet](https://social.technet.microsoft.com/Forums/en-US/bb9fa71c-c132-4954-abb0-70be8acbd925/failed-to-install-windows-intune?forum=microsoftintuneprod).|
|**0x8004300B**|Impossible d'exécuter le package d'installation du logiciel client car la version de Windows en cours d'exécution sur le client n'est pas prise en charge.|Intune ne prend pas en charge la version de Windows en cours d’exécution sur l’ordinateur client. Pour obtenir la liste des systèmes d’exploitation pris en charge, consultez [Configuration requise de l’infrastructure réseau pour Microsoft Intune](/intune-classic/get-started/network-infrastructure-requirements-for-microsoft-intune).|
|**0xAB2**|Windows Installer n'a pas pu accéder à l'exécution VBScript d'une action personnalisée.|Cette erreur est générée par une action personnalisée basée sur des DLL (Dynamic-Link Libraries). Pour résoudre les problèmes liés aux DLL, vous pouvez avoir besoin d’utiliser les outils décrits dans [Microsoft Support KB198038: Useful Tools for Package and Deployment Issues](http://go.microsoft.com/fwlink/?LinkID=234255) (KB198038 du support technique Microsoft : Outils utiles en cas de problèmes de package et de déploiement).|
|**0x8004300f**|Le logiciel ne peut pas être installé, car le client System Center Configuration Manager est déjà installé.|Supprimez le client Configuration Manager, puis relancez l'installation du logiciel client.|
|**0x80043010**|Le logiciel ne peut pas être installé car le client Open Mobile Alliance Device Management (OMADM) est déjà installé.|Désinscrivez le client OMADM, puis recommencez l'installation du logiciel client.|
Si les problèmes d’installation persistent, contactez le Support technique comme décrit dans [Comment obtenir un support technique pour Microsoft Intune](how-to-get-support-for-microsoft-intune.md). Munissez-vous du journal d’inscription de l’ordinateur client (situé dans %*programfiles*%\Microsoft\OnlineManagement\Logs\Enrollment.log et %*userprofile*%\AppData\Local\Microsoft\OnlineManagement\Logs\Enrollement.log) et du journal de Windows Update (%*windir*%\windowsupdate.log) pour les communiquer aux ingénieurs du support.

## <a name="what-to-do-if-endpoint-protection-is-not-uninstalled-when-you-uninstall-the-client"></a>Que faire si Endpoint Protection n’est pas désinstallé quand vous désinstallez le client

Parfois, vous pouvez quitter l’agent de protection des hôtes (Endpoint Protection) après avoir exécuté les commandes ci-dessus. Si cela se produit, exécutez cette commande à partir d’une invite de commandes avec élévation de privilèges :

    ```
    "C:\Program Files\Managed Defender\Setup.exe" /x /q /s
    ```


### <a name="next-steps"></a>Étapes suivantes
Si ces informations de dépannage n’ont pas permis de vous aider, contactez le support Microsoft comme décrit dans [Comment obtenir un support technique pour Microsoft Intune](how-to-get-support-for-microsoft-intune.md).
