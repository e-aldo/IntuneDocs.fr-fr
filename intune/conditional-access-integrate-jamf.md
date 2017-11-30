---
title: "Intégrer Jamf Pro à Intune pour des raisons de conformité"
titlesuffix: Azure portal
description: "Utilisez la conformité pour sécuriser les appareils gérés par Jamf."
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 11/14/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4b6dcbcc-4661-4463-9a36-698d673502c6
ms.reviewer: elocholi
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6b37ffd23f8cf8764ba457b0803dfc308cf1c071
ms.sourcegitcommit: 82088d297eef629e3da6011681ead442ae7e25f7
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/15/2017
---
# <a name="integrate-jamf-pro-with-intune-for-compliance"></a>Intégrer Jamf Pro à Intune pour des raisons de conformité

|S’applique à : Intune dans le portail Azure |
|--|
|Vous recherchez de la documentation sur Intune dans le portail Classic ? [Cliquez ici](/intune/introduction-intune?toc=/intune-classic/toc.json).|
| |

|Actuellement en préversion privée|
|--|
|Les fonctionnalités décrites dans cette rubrique ne sont accessibles qu’aux clients qui utilisent la préversion privée. Ce message sera supprimé une fois qu’elle sera commercialisée pour tous les clients.|
| |

Si votre organisation utilise [Jamf Pro](https://www.jamf.com) pour gérer les Mac des utilisateurs finaux, vous pouvez vous servir des stratégies de conformité Microsoft Intune et de l’accès conditionnel Azure Active Directory pour faire en sorte que les appareils de votre organisation soient conformes.

## <a name="prerequisites"></a>Prérequis

Vous aurez besoin des éléments suivants pour configurer l’accès conditionnel avec Jamf Pro :

- l’accès à la préversion privée d’Intune pour l’accès conditionnel macOS ;
- Jamf Pro 10.1.0 (ou une version ultérieure) ;
- [l’application Portail d’entreprise pour macOS](https://aka.ms/macoscompanyportal) ;
- des appareils macOS équipés d’OS X 10.11 Yosemite (ou une version ultérieure).

## <a name="connecting-intune-to-jamf-pro"></a>Connecter Intune à Jamf Pro

Vous pouvez connecter Intune à Jamf Pro en :

1. Créant une application dans Visual Studio.
2. Autorisant l’intégration d’Intune à Jamf Pro.
3. Configurant l’accès conditionnel dans Jamf Pro.

## <a name="create-a-new-application-in-azure-active-directory"></a>Créer une application dans Azure Active Directory

1. Ouvrez **Azure Active Directory** > **Inscription d’une application**.
2. Cliquez sur **+ Inscription d’une nouvelle application**.
3. Entrez un **nom d’affichage**, par exemple, **Accès conditionnel Jamf**.
4. Sélectionnez **Application web / API**.
5. Spécifiez **l’URL de connexion** de Jamf Pro.
6. Cliquez sur **Créer une application**.
7. Enregistrez **l’ID d’application** ainsi créé, puis ouvrez **Tous les paramètres** > **Clés** pour créer une nouvelle clé d’application. Enregistrez la clé d’application.

  > [!NOTE]
  > La clé d’application ne s’affiche qu’une seule fois pendant ce processus. Veillez à l’enregistrer dans un endroit où vous pourrez facilement la récupérer.

8. Accédez à **Tous les paramètres** > **Accès à l’API** > **Autorisations requises** et supprimez toutes les autorisations.

  > [!NOTE]
  > Ajoutez une nouvelle autorisation requise. L’application ne peut fonctionner correctement qu’avec l’unique autorisation requise.

9.  Sélectionnez **API Microsoft Intune** et cliquez sur **Sélectionner**.
10. Sélectionnez **Envoyer les attributs des appareils à Microsoft Intune** et cliquez sur **Sélectionner**.
11. Cliquez sur le bouton **Accorder des autorisations** après avoir enregistré les autorisations requises de l’application.

  > [!NOTE]
  > Si la clé d’application arrive à expiration, il vous faudra créer une nouvelle clé d’application dans Microsoft Azure, puis mettre à jour les données d’accès conditionnel dans Jamf Pro. Azure vous autorise à avoir à la fois l’ancienne et la nouvelle clés actives afin d’éviter toute interruption de service.

## <a name="enable-intune-to-integrate-with-jamf-pro"></a>Autoriser l’intégration d’Intune à Jamf Pro

1. Sur le Portail Microsoft Azure, ouvrez **Microsoft Intune** > **Conformité des appareils** > **Connecteur de conformité de Jamf**.
2. Activez le connecteur de conformité de Jamf en collant l’ID d’application dans le champ **ID d’application Jamf Azure Active Directory**.
3. Cliquez sur **Enregistrer**.

## <a name="configure-conditional-access-in-jamf-pro"></a>Configurer l’accès conditionnel dans Jamf Pro

1. Dans Jamf Pro, accédez à **Gestion globale** > **Accès conditionnel**. Cliquez sur le bouton **Modifier** de l’onglet **Microsoft**.
2. Cochez la case **Activer l’accès conditionnel avec Microsoft**.
3. Saisissez les informations requises sur votre client Azure, notamment **Emplacement**, **Nom de domaine**, **ID d’application** et **Clé d’application** (tous deux enregistrés lors des étapes précédentes).
4. Cliquez sur **Enregistrer**. Jamf Pro testera vos paramètres et vérifiera que tout fonctionne.

## <a name="information-shared-from-jamf-pro-to-intune"></a>Informations partagées par Jamf Pro avec Intune

Jamf Pro capture des données d’inventaire sur les appareils macOS gérés. Jamf Pro fournit les informations suivantes à Intune :

* ID d’appareil Azure AD
* État de l’inventaire Jamf (état de l’inventaire d’un ordinateur enregistré auprès de Jamf Pro au cours des dernières 24 heures)
* Version de système d'exploitation
* ID d’utilisateur Azure AD
* Chiffré (FileVault 2)
* État de l’opérateur de contrôle d’appels
* Mot de passe : nombre minimal de jeux de caractères
* Expiration du mot de passe (jours)
* Type de mot de passe : simple, alphanumérique ou inconnu
* Empêcher la connexion automatique
* Longueur de mot de passe requise
* Mot de passe : nombre de mots de passe précédents pour empêcher la réutilisation
* Protection de l’intégrité du système
* Dernière heure d’enregistrement
* Type d’architecture
* Emplacements de mémoire RAM disponibles
* Capacité de la batterie
* ROM de démarrage
* Vitesse du bus
* Taille de cache
* Nom du périphérique
* Jonction de domaine
* ID Jamf
* Adresse MAC
* Make
* Modèle
* Identificateur du modèle
* Vitesse de la carte réseau
* Nombre de cœurs
* Nombre de processeurs
* Système d’exploitation
* Plate-forme
* vitesse du processeur
* Type de processeur
* Adresse MAC secondaire
* Numéro de série
* Version SMC
* RAM totale
* UDID
* Adresse e-mail de l’utilisateur

## <a name="next-steps"></a>Étapes suivantes

- [Appliquer des stratégies de conformité aux appareils gérés par Jamf](conditional-access-assign-jamf.md)
