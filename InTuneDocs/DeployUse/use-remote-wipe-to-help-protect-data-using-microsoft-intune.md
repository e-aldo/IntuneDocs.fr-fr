---
# required metadata

title: Utiliser la réinitialisation à distance pour protéger les données | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 8519e411-3d48-44eb-9b41-3e4fd6a93112

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Protégez vos données avec la réinitialisation complète ou sélective à l’aide de Microsoft Intune
Comme avec les appareils, à un moment donné, vous voulez ou devez [mettre hors service des applications](retire-apps-using-microsoft-intune.md) que vous avez déployées pour des ordinateurs et des appareils mobiles, car elles ne sont plus nécessaires. Vous souhaitez peut-être aussi supprimer les données d’entreprise sur l’appareil. Pour ce faire, Intune propose des fonctionnalités de réinitialisation sélective et de réinitialisation complète. Comme les appareils mobiles peuvent stocker des données d’entreprise sensibles et donner accès à de nombreuses ressources d’entreprise, vous pouvez émettre une commande de réinitialisation d’appareil à distance à partir d’Intune pour réinitialiser un appareil perdu ou volé. Les utilisateurs peuvent émettre aussi une commande de réinitialisation d’appareil à distance à partir d’Intune sur les appareils privés inscrits dans Intune.

  > [!NOTE]
  > Cette rubrique concerne uniquement la réinitialisation d’appareils gérés par Intune. Vous pouvez aussi utiliser [le portail Azure en version préliminaire](https://portal.azure.com) pour [réinitialiser les données d’entreprise des applications](wipe-managed-company-app-data-with-microsoft-intune.md)

## réinitialisation complète


**Une réinitialisation complète** rétablit les paramètres d’usine d’un appareil et supprime l’ensemble des données et des paramètres de l’entreprise et de l’utilisateur. L’appareil est supprimé d’Intune. La réinitialisation complète est utile pour réinitialiser un appareil avant de le transmettre à un nouvel utilisateur ou dans les cas où l’appareil a été perdu ou volé.  Faites attention lors de la sélection de la réinitialisation complète.

## Les données sur l’appareil ne peuvent pas être récupérées

réinitialisation sélective La **réinitialisation sélective** supprime les données d’entreprise, notamment les données de gestion des applications mobiles (MAM) le cas échéant, les paramètres et les profils de messagerie sur un appareil. La réinitialisation sélective conserve les données personnelles de l’utilisateur sur l’appareil. L’appareil est supprimé d’Intune.

**Les tableaux suivants décrivent par plateforme la nature des données supprimées et l’effet de cette opération sur les données qui restent sur l’appareil après une réinitialisation sélective.**

|iOS|Type de données|
|-------------|-------|
|iOS|Applications d’entreprise et données associées installées par Intune. Les applications sont désinstallées.<br /><br />Les données des applications de l'entreprise sont supprimées. Les données d'application des applications Microsoft qui utilisent la gestion des applications mobiles sont supprimées.|
|L'application n'est pas supprimée.|Paramètres|
|Les configurations qui ont été définies par la stratégie Intune ne sont plus appliquées et les utilisateurs peuvent modifier les paramètres.|Paramètres de profil Wi-Fi et VPN|
|Supprimé|Paramètres de profil de certificat|
|Certificats supprimés et révoqués.|Agent de gestion|
|Le profil de gestion est supprimé.|Courrier électronique|
|Les profils de messagerie approvisionnés via Intune sont supprimés. Les e-mails mis en cache sur l’appareil le sont également.|Disjonction d'Azure Active Directory (AAD)|
|Enregistrement AAD supprimé | Contacts  Les contacts synchronisés avec le carnet d’adresses natif directement à partir de l’application sont supprimés. <br /> <br />Les contacts synchronisés à partir du carnet d’adresses natif vers une autre source externe ne peuvent pas être réinitialisés.

**Actuellement, seule l’application Outlook est prise en charge.**

|Android|Type de données|Android|
|-------------|-----------|------------------------|
|Android Samsung KNOX|Liens web|Supprimé.|
|Supprimé|Applications Google Play non gérées|Les applications et les données sont toujours installées.|
|Les applications et les données sont toujours installées.|Applications métier non gérées|Les applications et les données sont toujours installées. Les applications sont désinstallées et les données locales propres aux applications sont supprimées en conséquence.|
|Aucune donnée extérieure à l’application (carte SD, etc.) n’est supprimée.|Applications Google Play gérées Les données d’application sont supprimées. L’application n’est pas supprimée.|Les données protégées par chiffrement MAM en dehors de l’application (carte SD, etc.) restent chiffrées mais ne sont pas supprimées. Les données d’application sont supprimées. L’application n’est pas supprimée.|
|Les données protégées par chiffrement MAM en dehors de l’application (carte SD, etc.) restent chiffrées mais ne sont pas supprimées.|Applications métier gérées Les données d’application sont supprimées. L’application n’est pas supprimée.|Les données protégées par chiffrement MAM en dehors de l’application (carte SD, etc.) restent chiffrées mais ne sont pas supprimées. Les données d’application sont supprimées. L’application n’est pas supprimée.|
|Les données protégées par chiffrement MAM en dehors de l’application (carte SD, etc.) restent chiffrées mais ne sont pas supprimées.|Paramètres|Les configurations qui ont été définies par la stratégie Intune ne sont plus appliquées et les utilisateurs peuvent modifier les paramètres.|
|Les configurations qui ont été définies par la stratégie Intune ne sont plus appliquées et les utilisateurs peuvent modifier les paramètres.|Paramètres de profil Wi-Fi et VPN|Supprimé|
|Supprimé|Paramètres de profil de certificat|Certificats révoqués, mais pas supprimés.|
|Certificats supprimés et révoqués.|Agent de gestion|Le privilège d'administrateur d'appareil est révoqué.|
|Le privilège d'administrateur d'appareil est révoqué.|E-mail|Les messages reçus par l’application Microsoft Outlook pour l’application Android sont supprimés.|
|Les profils de messagerie approvisionnés via Intune sont supprimés. Les e-mails mis en cache sur l’appareil le sont également.|Disjonction d'Azure Active Directory (AAD)|Enregistrement AAD supprimé|
|Enregistrement AAD supprimé | Contacts  Les contacts synchronisés avec le carnet d’adresses natif directement à partir de l’application sont supprimés. <br /> <br />Les contacts synchronisés à partir du carnet d’adresses natif vers une autre source externe ne peuvent pas être réinitialisés.|Actuellement, seule l’application Outlook est prise en charge.  Les contacts synchronisés avec le carnet d’adresses natif directement à partir de l’application sont supprimés. <br /> <br />Les contacts synchronisés à partir du carnet d’adresses natif vers une autre source externe ne peuvent pas être réinitialisés.

**Actuellement, seule l’application Outlook est prise en charge.**

|Windows|Type de données|Windows 8.1 (MDM) et Windows RT 8.1|Windows RT|Windows Phone 8 et Windows Phone 8.1|
|-------------|----------------------------------------------------------------|--------------|-----------------------------------------|--------|
|Windows 10|Applications d’entreprise et données associées installées par Intune.|Les fichiers protégés par le système EFS voient leur clé révoquée et l'utilisateur n'est pas en mesure d'ouvrir ces fichiers.|Ne supprime pas les applications de la société. Les applications installées à l'origine via le portail d'entreprise sont désinstallées.|Les données des applications de l'entreprise sont supprimées.|
|Les applications sont désinstallées et les clés de chargement de version test sont supprimées.|Paramètres|Les configurations qui ont été définies par la stratégie Intune ne sont plus appliquées et les utilisateurs peuvent modifier les paramètres.|Les configurations qui ont été définies par la stratégie Intune ne sont plus appliquées et les utilisateurs peuvent modifier les paramètres.|Les configurations qui ont été définies par la stratégie Intune ne sont plus appliquées et les utilisateurs peuvent modifier les paramètres.|
|Les configurations qui ont été définies par la stratégie Intune ne sont plus appliquées et les utilisateurs peuvent modifier les paramètres.|Paramètres de profil Wi-Fi et VPN|Supprimé|Supprimé|Non pris en charge|
|Supprimé|Paramètres de profil de certificat|Certificats supprimés et révoqués.|Certificats supprimés et révoqués.|Non pris en charge|
|Certificats supprimés et révoqués.|E-mail|Supprime la messagerie électronique compatible avec EFS, qui inclut l'application de messagerie électronique pour la messagerie et les pièces jointes Windows.|Non prise en charge|Les profils de messagerie approvisionnés via Intune sont supprimés. Les e-mails mis en cache sur l’appareil le sont également. Supprime la messagerie électronique compatible avec EFS, qui inclut l'application de messagerie électronique pour la messagerie et les pièces jointes Windows.|
|Supprime les comptes de messagerie approvisionnés par Intune.|Disjonction d'Azure Active Directory (AAD)|Non|Non|Enregistrement AAD supprimé Non applicable.|

### Windows 10 ne prend pas en charge la réinitialisation sélective pour appareils joints à Azure Active Directory

1.  Réinitialiser à distance un appareil à partir de la console d’administration Intune Sélectionnez les appareils à réinitialiser.

    -   **Vous les trouverez par utilisateur ou par appareil.**

        1.  Par utilisateur :

        2.  Dans la [console d’administration Intune](https://manage.microsoft.com/), cliquez sur **Groupes** &gt; **Tous les utilisateurs** Cliquez sur le nom de l’utilisateur dont vous souhaitez réinitialiser l’appareil mobile.

        3.  Cliquez sur **Afficher les propriétés** Dans la page des **propriétés** de l’utilisateur, sélectionnez **Appareils**, puis le nom de l’appareil mobile à réinitialiser.

    -   **Utilisez Ctrl + clic pour sélectionner plusieurs appareils.**

        1.  Par appareil :

      ![Dans la [console d’administration Intune](https://manage.microsoft.com/), sélectionnez **Groupes** &gt; **Tous les appareils mobiles**](../media/dev-sa-wipe.png)

        2.  Démarrage d’une mise hors service ou d’une réinitialisation Sélectionnez **Appareils**, puis le nom de l’appareil mobile à réinitialiser.

2.  Utilisez Ctrl + clic pour sélectionner plusieurs appareils.

3.  Cliquez sur **Mettre hors service/Réinitialiser**

    -   Un message s'affiche vous invitant à confirmer si vous voulez mettre l'appareil hors service ou non.

    -   Pour effectuer une **Réinitialisation sélective** qui supprime uniquement les applications et les données d’entreprise, cliquez sur **Oui** Pour effectuer une **Réinitialisation complète** qui efface toutes les applications et les données, puis rétablit les paramètres d’usine de l’appareil, sélectionnez **Réinitialiser l’appareil avant la mise hors service**. Cette action s'applique à toutes les plateformes sauf Windows 8.1.

Vous ne pouvez pas récupérer les données supprimées par une réinitialisation complète

## La propagation d'une réinitialisation sur tous les types d'appareil prend moins de 15 minutes.
Réinitialiser le contenu EFS (Encryption File System) La réinitialisation sélective du contenu EFS est prise en charge par Windows 8.1 et Windows RT 8.1.

-   Les éléments suivants s'appliquent à une réinitialisation sélective du contenu EFS : Seules les applications et les données qui sont protégées par EFS et qui utilisent le même domaine Internet que le compte Intune sont réinitialisées de manière sélective.

-   Pour plus d’informations, consultez la page relative à la [réinitialisation sélective de Windows pour la gestion des données d’appareil](http://technet.microsoft.com/library/dn486874.aspx)

-   Si des modifications sont apportées au domaine associé à EFS, il peut falloir jusqu'à 48 heures avant que les applications et les données qui utilisent le nouveau domaine soient réinitialisées de manière sélective.

Chaque domaine inscrit dans Intune est réinitialisé.

-   Les données et les applications qui sont actuellement prises en charge par la réinitialisation sélective EFS sont :

-   Application de messagerie pour Windows

-   Dossiers de travail Fichiers et dossiers chiffrés par EFS.

-   Pour plus d’informations, consultez [Meilleures pratiques pour le chiffrement des systèmes de fichiers](http://support.microsoft.com/kb/223316)  Si votre organisation gère son identité dans Active Directory, elle doit utiliser l'outil de synchronisation d'annuaires (DirSync) pour synchroniser les informations dans AAD pour que la réinitialisation sélective EFS fonctionne correctement.

## Pour plus d’informations sur DirSync, consultez [Scénario de synchronisation d’annuaires](http://technet.microsoft.com/library/dn441212.aspx) dans la documentation Azure Active Directory.
Analyser les actions de mise hors service, de réinitialisation et de suppression

1.  Pour obtenir un rapport sur les appareils qui ont été mis hors service, réinitialisés ou supprimés, ainsi que sur les personnes qui ont effectué ces opérations :

2.  Dans la [console d’administration Intune](https://manage.microsoft.com/), cliquez sur **Rapports** &gt; **Rapports d’historique de l’appareil**


### Indiquez une date de début et de fin pour le rapport, puis cliquez sur **Afficher le rapport**
[Voir aussi](retire-devices-from-microsoft-intune-management.md)

[Mettre des appareils hors service](http://technet.microsoft.com/library/dn486874.aspx)


<!--HONumber=May16_HO2-->


