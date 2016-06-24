---
# required metadata

title: Aider les utilisateurs finaux à comprendre les messages de l’application Portail d’entreprise | Microsoft Intune
description:
keywords:
author: staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 3df993aa-48c5-4799-b68d-c85fe4f7b02c

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Aider les utilisateurs finaux à comprendre les messages de l’application Portail d’entreprise

Les informations suivantes s’appliquent uniquement aux appareils Android versions 6.0 et ultérieures. Lors de l’inscription de l’appareil, les utilisateurs finaux voient deux messages qui s’affichent pendant le processus d’inscription :

- Autoriser l’application Portail d’entreprise à passer et gérer des appels téléphoniques ?
- Autoriser l’application Portail d’entreprise à accéder aux photos, aux fichiers multimédias et aux fichiers de votre appareil ?

Consultez les paragraphes suivants pour plus d’informations sur ces messages et pour connaître les informations que vous pouvez partager avec vos utilisateurs finaux à leur sujet.

## Autoriser l’application Portail d’entreprise à passer et gérer des appels téléphoniques ?

### Texte et emplacement du message
Le texte du message est **Autoriser l’application Portail d’entreprise à passer et gérer des appels téléphoniques ?** et il s’affiche quand les utilisateurs se connectent à l’application Portail d’entreprise pour la première fois pour inscrire leur appareil.

### Signification du message
Le message demande aux utilisateurs d’autoriser l’envoi du numéro IMEI et du numéro de téléphone de leur appareil au service Intune et de les afficher dans la console d’administration dans la page Matériel.

> [!NOTE]
> **L’application Portail d’entreprise ne passe et ne gère jamais d’appels téléphoniques !** Le texte du message est contrôlé par Google et ne peut pas être modifié.

Pour afficher la page **Matériel**, accédez à **Groupes** > **Tous les appareils mobiles** > **Appareils**. Sélectionnez l’appareil de l’utilisateur et accédez à **Afficher les propriétés** > **Matériel**.

### Que se passe-t-il si les utilisateurs autorisent ou refusent l’accès
Si les utilisateurs autorisent l’accès, le numéro IMEI et le numéro de téléphone de l’appareil s’affichent dans la console d’administration de la page Matériel.

Si les utilisateurs refusent l’accès, ils peuvent continuer à utiliser l’application Portail d’entreprise et inscrire leur appareil, mais le numéro IMEI et le numéro de téléphone de l’appareil des utilisateurs sont vides dans la console d’administration de la page Matériel. La deuxième fois que les utilisateurs se connectent à l’application Portail d’entreprise après le refus de l’accès, le message affiche une case **Ne plus me demander** que les utilisateurs peuvent cocher pour que le message ne s’affiche plus.

Si les utilisateurs autorisent, puis refusent par la suite l’accès, le message s’affiche la prochaine fois qu’ils se connectent à l’application Portail d’entreprise après l’inscription.</br></br>Si les utilisateurs décident par la suite d’autoriser l’accès, ils peuvent accéder à **Paramètres** > **Applications** > **Portail d’entreprise** > **Autorisations** > **Téléphone**, puis activer l’autorisation.

### Où diriger vos utilisateurs pour plus d’informations
Étape 5 dans [Inscrire un appareil Android dans Intune](/Intune/EndUser/enroll-your-device-in-intune-android)

## Autoriser l’application Portail d’entreprise à accéder aux photos, aux fichiers multimédias et aux fichiers de votre appareil ?

### Texte et emplacement du message
Le texte du message est **Autoriser l’application Portail d’entreprise à accéder aux photos, aux fichiers multimédias et aux fichiers de votre appareil ?** et il s’affiche quand les utilisateurs appuient sur **Envoyer les données** pour envoyer les journaux de données à leur administrateur informatique.

### Signification du message
Le message demande aux utilisateurs d’autoriser leur appareil à écrire des journaux de données sur la carte SD de l’appareil et à permettre le déplacement de ces journaux à l’aide d’un câble USB.   

> [!NOTE]
> **L’application Portail d’entreprise n’accède jamais aux photos, aux fichiers multimédias ni aux fichiers des utilisateurs !** Le texte du message est contrôlé par Google et ne peut pas être modifié.

### Que se passe-t-il si les utilisateurs autorisent ou refusent l’accès
Si les utilisateurs autorisent l’accès, les journaux sont copiés sur la carte SD.

Si les utilisateurs refusent l’accès, ils peuvent toujours envoyer les journaux de données, mais les journaux ne sont pas copiés sur la carte SD de l’appareil.

La deuxième fois que les utilisateurs se connectent à l’application Portail d’entreprise après le refus de l’accès, le message affiche une case **Ne plus me demander** que les utilisateurs peuvent cocher pour que le message ne s’affiche plus. Si les utilisateurs autorisent, puis refusent par la suite l’accès, le message s’affiche la prochaine fois qu’ils essaient d’envoyer les journaux. Si les utilisateurs décident par la suite d’autoriser l’accès, ils peuvent accéder à **Paramètres** > **Applications** > **Portail d’entreprise** > **Autorisations** > **Stockage**, puis activer l’autorisation.

### Où diriger vos utilisateurs pour plus d’informations
[Envoyer des journaux de données de diagnostic à votre administrateur informatique par e-mail](/Intune/EndUser/send-diagnostic-data-logs-to-your-it-administrator-using-email-android)


### Voir aussi
[Ce qu'il faut dire à vos utilisateurs finaux concernant l'utilisation d'Intune](/intune/deploy-use/what-to-tell-your-end-users-about-using-microsoft-intune.md)


<!--HONumber=Jun16_HO1-->


