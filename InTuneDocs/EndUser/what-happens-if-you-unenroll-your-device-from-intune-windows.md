---
# required metadata

title: Que se passe-t-il quand vous désinscrivez votre appareil d’Intune ? | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 47e03edb-0c57-4e25-8e89-4a1069267b8c

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: priyar
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Que se passe-t-il quand vous désinscrivez votre appareil d’Intune ?

Lorsque vous désinstallez l'application Portail d'entreprise de votre appareil, votre appareil est également désinscrit d’Intune. Pour plus d’informations sur ce processus, utilisez le lien répertorié dans la section ci-dessus « Dans cet article » correspondant au type d’appareil que vous utilisez.

- [Windows 10 Mobile, 8.1, Windows 8, Windows 7, Vista](#windows-10-mobile--8-1,-windows-8,-windows-7,-vista)
- [Windows 10, Windows 8.1 ou Windows Phone 8](#windows-10--windows-8-1-or-windows-phone-8)
- [Windows RT exécutant Windows 8.1 ou Windows RT](#windows-rt-running-windows-8-1-or-windows-rt)


## Windows 10, Windows 8.1, Windows 8, Windows 7, Vista

-   Votre appareil n’apparaît plus dans le portail d’entreprise, et vous ne pouvez plus installer des applications à partir du portail d’entreprise.

-   Si vous avez installé le logiciel client Intune, il est supprimé de votre ordinateur.

-   Le logiciel Intune Endpoint Protection est supprimé de votre ordinateur. Si votre ordinateur dispose d'un autre logiciel antivirus et qu'il est désactivé, ce logiciel peut être réactivé après la suppression d’Intune Endpoint Protection. Vous devez vérifier votre ordinateur après l'avoir supprimé du portail d'entreprise.

    > [!IMPORTANT] Si l’autre logiciel de protection antivirus n’est pas réactivé ou si aucun autre logiciel antivirus n’est installé, votre ordinateur peut être vulnérable aux virus et aux logiciels malveillants.

-   Tous les paramètres qui ont été modifiés sur votre appareil quand vous l’avez ajouté, par exemple la désactivation de l’appareil photo, ne s’appliquent plus.

-   Votre ordinateur ne recevra plus les mises à jour automatiques ou mises à jour de logiciels antivirus à partir du service Intune. Toutefois, selon la façon dont il est configuré, votre ordinateur peut continuer à recevoir des mises à jour des services Windows Server Update.

En outre, pour Windows 8.1 :

-   Vous ne pouvez plus utiliser les applications et les données d'entreprise sur votre périphérique.

-   Certaines applications de messagerie, telles que Windows Mail, ne pourront plus accéder à la messagerie d'entreprise stockée sur votre appareil.

-   Vous ne pourrez peut-être plus vous connecter au réseau de votre entreprise via le Wi-Fi ou un réseau privé virtuel.

-   Il se peut que vous n'ayez plus accès à certaines ressources de l'entreprise, telles que les partages de fichiers ou les sites Web internes.

## Windows 10 Mobile, Windows Phone 8.1 ou Windows Phone 8

-   L’application Portail d’entreprise est désinstallée de votre appareil, ce qui signifie que votre appareil n’apparaît plus dans le portail d’entreprise. Vous ne pourrez pas installer des applications à partir de l’application Portail d’entreprise ou du site web du portail d’entreprise.

-   Vous ne pouvez plus utiliser les applications et les données d'entreprise sur votre périphérique.

-   Tous les paramètres qui ont été modifiés sur votre appareil lorsque vous l'avez ajouté, par exemple la désactivation de l'appareil photo ou l'exigence d'une certaine longueur de mot de passe, ne s'appliquent plus.

    > [!IMPORTANT]
    > Seules les stratégies de cryptage continuent de s'appliquer. Si votre stratégie d’entreprise nécessitait le chiffrement de votre appareil Windows Phone, la seule façon de le déchiffrer est de le réinitialiser en utilisant son menu **Paramètres**.

## Windows RT exécutant Windows 8.1 ou Windows RT

-   L’application Portail d’entreprise est désinstallée de votre appareil, ce qui signifie que votre appareil n’apparaît plus dans le portail d’entreprise. Vous ne pourrez pas installer des applications à partir du portail d’entreprise.

-   Vous ne pouvez plus utiliser les applications et les données d'entreprise sur votre périphérique.

-   Tous les paramètres qui ont été modifiés sur votre appareil lorsque vous l'avez ajouté, par exemple la désactivation de l'appareil photo ou l'exigence d'une certaine longueur de mot de passe, ne s'appliquent plus.

-   Vous ne pourrez peut-être plus vous connecter au réseau de votre entreprise via le Wi-Fi ou un réseau privé virtuel.

-   Il se peut que vous n'ayez plus accès à certaines ressources de l'entreprise, telles que les partages de fichiers ou les sites Web internes.

-   Certaines applications de messagerie, telles que Windows Mail, ne pourront plus accéder à la messagerie d'entreprise stockée sur votre appareil.

Lorsque vous supprimez votre appareil Windows RT, voici ce qui se produit :

-   L’application Portail d’entreprise est désinstallée de votre appareil, ce qui signifie que votre appareil n’apparaît plus dans le portail d’entreprise. Vous ne pourrez pas installer des applications à partir du portail d’entreprise.

-   Vous ne pouvez plus utiliser les applications et les données d'entreprise sur votre périphérique.

-   Tous les paramètres qui ont été modifiés sur votre appareil lorsque vous l'avez ajouté, par exemple la désactivation de l'appareil photo ou l'exigence d'une certaine longueur de mot de passe, ne s'appliquent plus.

Si vous avez des questions ou si vous ne trouvez pas les coordonnées de votre administrateur informatique, regardez si elles ne sont pas indiquées dans le [site web Portail d’entreprise](http://portal.manage.microsoft.com).

### Voir aussi
[Utilisation de votre appareil Windows avec Intune](using-your-windows-device-with-intune.md)

<!--HONumber=Jun16_HO1-->


