---
# required metadata

title: Votre ordinateur est déjà inscrit | Microsoft Intune
description:
keywords:
author: staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 8d3a40f5-99e9-48dc-9706-f7a3a23e5704

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Votre ordinateur est déjà inscrit
Cette page s'affiche car vous avez exécuté le programme d'installation du logiciel client Intune. Toutefois, le logiciel est déjà installé sur votre ordinateur et le programme d'installation ne peut pas continuer.

La raison peut être la suivante :

-   Le logiciel client a été installé précédemment et le programme d'installation a été à nouveau exécuté.

-   Le programme d'installation a été exécuté sur l'ordinateur après qu'un administrateur informatique a mis hors service votre appareil depuis Intune. Une fois votre appareil mis hors service, cela peut prendre plusieurs heures pour que le logiciel client soit supprimé de votre ordinateur.

-   Le programme d'installation a détecté un échec d'installation ou de suppression récent du logiciel client.

## Éléments installés par le programme d'installation sur votre ordinateur
Le programme d'installation installe le client Intune. Une fois l'installation terminée, le logiciel client continue de s'exécuter en arrière-plan pour configurer l'utilisation de votre ordinateur avec Intune. Ce processus peut prendre du temps et inclut les opérations suivantes :

-   Inscription de votre ordinateur auprès d’Intune

-   Envoi d'un inventaire du matériel et des logiciels installés de l'ordinateur

-   Configuration de la stratégie Intune, avec installation d'Endpoint Protection (si configuré)

-   Installation d’Intune Center

Une fois Intune Center installé, vous pouvez l'utiliser pour accéder au portail d'entreprise sur lequel vous pouvez établir un lien entre votre ordinateur et votre compte professionnel.

## Microsoft Intune Center
Intune Center s'installe en tant qu'application sur votre ordinateur une fois que le logiciel client est correctement installé sur l'ordinateur, puis inscrit votre ordinateur auprès d’Intune. Vous pouvez utiliser Intune Center pour :

-   **Obtenir des applications à partir du portail d'entreprise** : recherchez et installez les applications déployées par votre administrateur informatique. Lors de la première connexion au portail d'entreprise sur un ordinateur nouvellement inscrit, vous avez la possibilité d'établir un lien entre votre compte professionnel et cet ordinateur.

-   **Vérifier les mises à jour logicielles** : recherchez les mises à jour logicielles déployées par votre administrateur Intune.

-   **Démarrer une analyse Endpoint Protection de votre ordinateur** : vous pouvez lancer une analyse pour détecter les logiciels malveillants éventuellement installés sur votre ordinateur.

-   **Demander une assistance à distance** : cette option est disponible uniquement quand l'assistance à distance est prise en charge par le système d'exploitation de vos ordinateurs.

## Confirmer que le logiciel client est installé ou a été supprimé
**Vérifier que le client est installé :**
L'installation du client Intune est terminée quand les applications suivantes sont disponibles sur l'ordinateur :

-   **Intune Center**

-   **Intune Endpoint Protection** (si Endpoint Protection est activé par votre administrateur informatique)

Si vous savez utiliser le Gestionnaire des tâches, vous pouvez rechercher le service client Intune, qui doit être en cours d'exécution :

-   **OmcSvc**

**Vérifier que le client a été supprimé :**
Une fois que le client Intune est désinstallé d'un ordinateur, les applications qui ont été installées pendant l'installation du client sont supprimées, notamment Intune Center.

Le service client Intune **OmcSvc** supprimé.

## Comment supprimer le logiciel client de l'ordinateur
Par défaut, plusieurs heures après la mise hors service de votre ordinateur par votre administrateur informatique à partir de la console d'administration Intune, le logiciel client Intune est désinstallé.

Pour désinstaller manuellement le logiciel client Intune d'un ordinateur, vous pouvez utiliser les étapes suivantes pour forcer sa désinstallation :

1.  Sur l'ordinateur, ouvrez une invite de commandes en mode administrateur.

2.  Accédez au dossier **%programfiles%\Microsoft\OnlineManagement\Common**

3.  Exécutez la commande suivante : **ProvisioningUtil.exe /UninstallAgents /MicrosoftIntune**

La suppression du logiciel client est ainsi planifiée.



<!--HONumber=May16_HO1-->


