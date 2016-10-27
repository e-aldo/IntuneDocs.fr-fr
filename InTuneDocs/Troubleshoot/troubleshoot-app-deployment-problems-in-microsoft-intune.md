---
title: "Résoudre les problèmes de déploiement d’applications | Microsoft Intune"
description: "Cette rubrique vous aide à résoudre les problèmes de déploiement d’applications dans Microsoft Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 09/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 28ac298e-fb73-4c1c-b3fd-8336639e05e6
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: e95db6d0ccbe350984f11ce08749b700c2f5ad01
ms.openlocfilehash: efc280f0a1143cacc252ee9fc9344064aa211cb2


---

# Résoudre les problèmes de déploiement d’applications dans Microsoft Intune
Si vous rencontrez des problèmes de déploiement et de gestion des applications avec Intune, lisez ce qui suit. Cette rubrique contient certains problèmes courants que vous pouvez rencontrer avec les solutions.

## Codes d'erreur courants du déploiement d'applications

|Code d’erreur|Problème possible|Solution suggérée|
|--------------|--------------------|------------------------|
|0x80073CFF<br /><br />0x80CF201C (erreur du client)|Pour installer cette application, vous devez disposer d'un système compatible avec le chargement de versions tests.|Assurez-vous que le package d’application dispose d’une signature approuvée et qu’il est installé sur un ordinateur appartenant à un domaine sur lequel la stratégie AllowAllTrustedApps est activée ou sur un ordinateur qui a une licence de chargement indépendant Windows sur lequel la stratégie AllowAllTrustedApps est activée.|
|0x80073CF0|Le package n'a pas pu être ouvert.|Causes possibles :<br /><br />-   Le package n’est pas signé.<br />-   Le nom de l’éditeur ne correspond pas au sujet du certificat de signature.<br /><br />Consultez le journal des événements AppxPackagingOM pour plus d'informations.|
|0x80073CF3|Échec de la mise à jour du package, d'une dépendance ou validation de conflit|Causes possibles :<br /><br />-   Le package entrant est en conflit avec un package installé.<br />-   Une dépendance de package spécifiée est introuvable.<br />-   Ce package ne prend pas en charge l’architecture de processeur correcte.<br /><br />Consultez le journal des événements AppXDeployment-Server pour plus d'informations.|
|0x80073CFB|Le package fourni est déjà installé, et la réinstallation du package est bloquée|Cette erreur peut s'afficher si vous installez un package qui n'est pas identique au package déjà installé. Confirmez que la signature numérique fait également partie du package. Lorsqu'un package est reconstruit ou resigné, ce package n'est plus identique au niveau des bits au package déjà installé. Deux options possibles s'offrent à vous pour corriger cette erreur :<br /><br />-   incrémenter le numéro de version de l’application, puis reconstruire et signer à nouveau le package ;<br />-   supprimer l’ancien package pour chaque utilisateur sur le système avant d’installer le nouveau package.|
|0x87D1041C|Installation de l’application réussie mais l’application n’est pas détectée.|- L’application a été déployée correctement par Intune, puis désinstallée par la suite (éventuellement par l’utilisateur final). Demandez à l’utilisateur de réinstaller l’application depuis le portail d’entreprise. Les applications obligatoires sont automatiquement réinstallées au prochain enregistrement de l’appareil.|

## Résolution des problèmes des applications du Windows Store

Les informations de la rubrique [Troubleshooting packaging, deployment, and query of Windows Store apps](https://msdn.microsoft.com/library/windows/desktop/hh973484.aspx) vous aide à résoudre les problèmes courants que vous pouvez rencontrer lors de l’installation d’applications du Windows Store, en utilisant Intune ou par tout autre moyen.

## Résolution des problèmes de déploiement d’applications sur des PC gérés par le client logiciel Intune
Pour vous aider à résoudre les problèmes de déploiement d’applications sur les PC gérés par le client logiciel Intune, vous pouvez consultez les deux fichiers journaux suivants :
- Dossier %ProgramFiles%\Microsoft\OnlineManagement\Logs
- %ProgramFiles%\Microsoft\OnlineManagement\Updates\ReportingEvents.log

En outre, si vous avez besoin d’ouvrir une demande de support pour Intune, il peut être utile d’envoyer ces journaux à Microsoft.


### Étapes suivantes
Si ces informations de dépannage n’ont pas permis de vous aider, contactez le Support Microsoft comme décrit dans [Comment obtenir un support technique pour Microsoft Intune](how-to-get-support-for-microsoft-intune.md).



<!--HONumber=Oct16_HO2-->


