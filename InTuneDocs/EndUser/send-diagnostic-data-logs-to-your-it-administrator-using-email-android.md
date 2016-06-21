---
# required metadata

title: Envoyer les journaux de données de diagnostic à votre administrateur informatique par e-mail | Microsoft Intune
description:
keywords:
author: staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 85c868e7-8d63-480c-9770-4e99614a5c94

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: arnab
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Envoyer les journaux de données de diagnostic à votre administrateur informatique par e-mail

Si vous obtenez une erreur sur votre appareil Android pendant que vous utilisez les applications de votre établissement scolaire ou de votre entreprise ou pendant que vous êtes sur l’application du portail d’entreprise, vous pouvez envoyer des journaux de données de diagnostic pour aider votre administrateur informatique à identifier et corriger l’erreur. Pour inclure tous les détails dans les journaux, ce qui facilitera la tâche de l’administrateur informatique chargé d’identifier le problème, activez la journalisation documentée.

Pour activer la journalisation détaillée :

1.  Ouvrez l'application Portail d'entreprise.

2.  Cliquez sur **Menu** &gt; **Paramètres**.

    > [!NOTE] 
    > Le **Menu** peut être un bouton à l’écran ou un bouton physique, selon le type d’appareil Android que vous utilisez.

3.  Sous **Données de diagnostic**, appuyez sur **Envoyer les données**.

    > [!NOTE]
    > **Pour les appareils Android 6.0 ou ultérieur uniquement :** Quand vous appuyez sur **Envoyer des données**, le message **Autoriser l’application Portail d’entreprise à accéder aux photos, aux fichiers multimédias et aux fichiers de votre appareil ?** s’affiche. 

    Ce message est trompeur, car **Microsoft n’accède jamais aux photos, aux fichiers multimédias ou aux fichiers de votre appareil.** Google contrôle le texte du message, par conséquent, Microsoft ne peut pas le modifier.  Quand vous autorisez l’accès, vous autorisez simplement votre appareil à écrire des journaux de données sur la carte SD de l’appareil, ce qui vous permet de déplacer ces journaux à l’aide d’un câble USB.

    Si vous refusez l’accès, le message apparaît la prochaine fois que vous appuyez sur **Envoyer des données**, mais vous pouvez désactiver les futurs messages en cochant la case **Ne plus poser la question**.  Si vous décidez ensuite d’autoriser l’accès, accédez à **Paramètres** &gt; **Applications** &gt; **Portail d’entreprise** &gt; **Autorisations** &gt; **Stockage**, puis activer l’autorisation.

4.  Suivez les invites pour choisir l’application de messagerie à utiliser pour l’envoi des journaux à votre administrateur informatique. L’application crée un e-mail préadressé avec tous les journaux en pièces jointes.


### Voir aussi
[Utilisation de votre appareil Android avec Intune](using-your-android-device-with-intune.md)

<!--HONumber=Jun16_HO1-->


