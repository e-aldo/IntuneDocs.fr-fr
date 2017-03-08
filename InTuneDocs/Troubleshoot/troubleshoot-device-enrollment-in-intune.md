---
title: "Résoudre les problèmes d’inscription d’appareils | Microsoft Docs"
description: "Suggestions pour résoudre les problèmes liés à l’inscription d’appareils."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/01/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6982ba0e-90ff-4fc4-9594-55797e504b62
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 785e7514c6c6109cfec61a47ae2fc7183c7c2330
ms.openlocfilehash: 91c6a040f8fd3990c8d48087ac7397db8360f666
ms.lasthandoff: 01/25/2017


---

# <a name="troubleshoot-device-enrollment-in-intune"></a>Résoudre les problèmes d’inscription d’appareils dans Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Cette rubrique fournit des suggestions pour résoudre les problèmes liés à l’inscription d’appareils. Si ces informations ne vous permettent pas de remédier à votre problème, consultez [Comment obtenir un support technique pour Microsoft Intune](how-to-get-support-for-microsoft-intune.md) pour accéder à d’autres types d’assistance.


## <a name="initial-troubleshooting-steps"></a>Étapes initiales de dépannage

Avant de commencer le dépannage, vérifiez que vous avez configuré Intune correctement pour activer l’inscription. Vous pouvez consulter ces exigences de configuration dans les rubriques suivantes :

-    [Se préparer à inscrire des appareils dans Microsoft Intune](/intune/deploy-use/prerequisites-for-enrollment)
-    [Configurer la gestion des appareils iOS et Mac](/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune)
-    [Configurer la gestion de Windows 10 Mobile et Windows Phone avec Microsoft Intune](/intune/deploy-use/set-up-windows-phone-management-with-microsoft-intune)
-    [Configurer la gestion des appareils Windows](/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune)


Les utilisateurs d’appareils gérés peuvent recueillir des journaux d’inscription et de diagnostic qui peuvent vous être utiles. Les instructions destinées aux utilisateurs permettant de recueillir les journaux sont fournies dans :

- [Envoyer les erreurs d’inscription Android à votre administrateur informatique](https://docs.microsoft.com/intune/enduser/send-enrollment-errors-to-your-it-admin-android)
- [Envoyer les erreurs iOS à votre administrateur informatique](https://docs.microsoft.com/intune/enduser/send-errors-to-your-it-admin-ios)


## <a name="general-enrollment-issues"></a>Problèmes généraux d’inscription
Ces problèmes peuvent se produire sur toutes les plateformes.

### <a name="device-cap-reached"></a>Plafond d’appareils atteint
**Problème :** un utilisateur reçoit une erreur sur son appareil pendant l’inscription, par exemple une erreur **Portail d’entreprise temporairement indisponible** sur un appareil iOS, et le journal DMPdownloader.log dans Configuration Manager contient l’erreur **DeviceCapReached**.

**Résolution :**

#### <a name="check-number-of-devices-enrolled-and-allowed"></a>Vérifier le nombre d’appareils inscrits et le nombre autorisé

1.  Dans le portail d’administration Intune, vérifiez que l’utilisateur n’a pas dépassé le maximum autorisé de 15 appareils attribués.

2.  Sous **Administration** > **Gestion des appareils mobiles** > **Règles d’inscription** dans la console d’administration Intune, vérifiez que la limite d’inscription d’appareils a la valeur 15.

<!--- Mobile device users can delete devices at the following URL: [https://byodtestservice.azurewebsites.net/](https://byodtestservice.azurewebsites.net/). --->

Les administrateurs peuvent supprimer des appareils dans le portail Azure Active Directory.

#### <a name="to-delete-devices-in-the-azure-active-directory-portal"></a>Pour supprimer des appareils dans le portail Azure Active Directory

1.  Accédez à [http://aka.ms/accessaad](http://aka.ms/accessaad) ou choisissez **Administration** &gt; **Azure AD** dans [https://portal.office.com](https://portal.office.com).

2.  Connectez-vous avec l’ID de votre organisation en utilisant le lien sur le côté gauche de la page.

3.  Créez un abonnement Azure si vous n’en avez pas. Choisissez le lien d’abonnement **Enregistrer votre abonnement Azure Active Directory gratuit**. Vous ne devriez pas avoir besoin de carte de crédit ni d’effectuer un paiement si vous disposez d’un compte payant.

4.  Sélectionnez **Active Directory** , puis le nom de votre organisation.

5.  Sélectionnez l’onglet **Utilisateurs** .

6.  Sélectionnez l’utilisateur dont vous voulez supprimer les appareils.

7.  Choisissez **Appareils**.

8.  Supprimez les appareils appropriés, par exemple, ceux qui ne sont plus utilisés ou qui n’ont pas de définitions précises.

> [!NOTE]

> Pour éviter d’atteindre le plafond d’inscription d’appareils, vous pouvez utiliser le compte de gestionnaire d’inscription d’appareil, comme décrit dans [Inscrire des appareils d’entreprise avec le gestionnaire d’inscription d’appareil dans Microsoft Intune](/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune).
>
> Un compte d’utilisateur ajouté au compte des gestionnaires d’inscription d’appareil ne peut pas effectuer d’inscription si la stratégie d’accès conditionnel est appliquée à cette connexion d’utilisateur spécifique.

### <a name="company-portal-temporarily-unavailable"></a>Portail d’entreprise temporairement indisponible
**Problème :** Les utilisateurs reçoivent l’erreur **Portail d’entreprise temporairement indisponible** sur leur appareil.

**Résolution :**

1.  Supprimez l’application Portail d’entreprise Intune de l’appareil.

2.  Sur l’appareil, ouvrez le navigateur, accédez à [https://portal.manage.microsoft.com](https://portal.manage.microsoft.com), puis essayez de connecter un utilisateur.

3.  Si la connexion échoue, essayez avec un autre réseau.

4.  En cas d’échec, vérifiez que les informations d’identification de l’utilisateur ont bien été synchronisées avec Azure Active Directory.

5.  Si la connexion aboutit, l’appareil iOS vous invite à installer l’application Portail d’entreprise Intune et à procéder à l’inscription. Sur un appareil Android, vous devez d’abord installer manuellement l’application Portail d’entreprise Intune avant de retenter l’inscription.

### <a name="mdm-authority-not-defined"></a>Autorité MDM non définie
**Problème :** Un utilisateur reçoit l’erreur **Autorité MDM non définie**.

**Résolution :**

1.  Vérifiez que l’autorité MDM a été correctement définie pour le type de service Intune que vous utilisez, autrement dit pour Intune, Office 365 ou System Center Configuration Manager avec Intune. Pour Intune, l’autorité MDM est définie dans **Administration** &gt; **Gestion des appareils mobiles**. Pour Configuration Manager avec Intune, vous la définissez pendant que vous configurez le connecteur Intune. Dans Office 365, il s’agit du paramètre **Appareils mobiles**.

    > [!NOTE]
    > Une fois que vous avez défini l’autorité MDM, vous ne pouvez la modifier qu’en contactant le support technique, comme indiqué dans [Comment obtenir un support technique pour Microsoft Intune](how-to-get-support-for-microsoft-intune.md).

2.  Vérifiez que les informations d’identification de l’utilisateur ont bien été synchronisées avec Azure Active Directory en vous assurant que le nom d’utilisateur principal (UPN) correspond aux informations Active Directory dans le portail Office 365.
    Si l’UPN ne correspond pas aux informations Active Directory :

    1.  Désactivez DirSync sur le serveur local.

    2.  Supprimez l’utilisateur en question de la liste d’utilisateurs du **Portail de compte Intune** .

    3.  Patientez environ une heure avant que le service Azure supprime les données incorrectes.

    4.  Réactivez DirSync et vérifiez que l’utilisateur est à présent correctement synchronisé.

3.  Dans le cas où vous utilisez System Center Configuration Manager avec Intune, vérifiez que l’utilisateur dispose d’un ID d’utilisateur Cloud valide :

    1.  Ouvrez SQL Management Studio.

    2.  Connectez-vous à la base de données appropriée.

    3.  Ouvrez le dossier de bases de données, recherchez et ouvrez le dossier **CM_DBName**, DBName représentant le nom de la base de données client.

    4.  Dans la partie supérieure, choisissez **Nouvelle requête** et exécutez les requêtes suivantes :

        -   Pour afficher tous les utilisateurs : `select * from [CM_ DBName].[dbo].[User_DISC]`

        -   Pour afficher des utilisateurs spécifiques, utilisez la requête suivante, où %testuser1% représente username@domain.com pour l’utilisateur que vous recherchez : `select * from [CM_ DBName].[dbo].[User_DISC] where User_Principal_Name0 like '%testuser1%'`

        Après avoir écrit la requête, choisissez **!Execute**.
        Une fois que les résultats ont été retournés, recherchez l’ID d’utilisateur cloud.  Si vous n’en trouvez pas, c’est que l’utilisateur n’a pas de licence Intune.

### <a name="unable-to-create-policy-or-enroll-devices-if-the-company-name-contains-special-characters"></a>Impossible de créer une stratégie ou d’inscrire des appareils si le nom de l’entreprise contient des caractères spéciaux
**Problème :** Vous ne pouvez pas créer des stratégies, ni inscrire des appareils.

**Résolution :** Dans le [Centre d’administration Office 365](https://portal.office.com/), supprimez les caractères spéciaux du nom de l’entreprise et enregistrez les informations de l’entreprise.

### <a name="unable-to-log-in-or-enroll-devices-when-you-have-multiple-verified-domains"></a>Impossible de se connecter ou d’inscrire des appareils lorsque vous avez plusieurs domaines vérifiés
**Problème :** Quand vous ajoutez un deuxième domaine vérifié à votre ADFS, les utilisateurs avec le suffixe de nom principal d’utilisateur (UPN) du deuxième domaine peuvent ne pas pouvoir se connecter aux portails ou inscrire des appareils.


**Solution :** Les clients Microsoft Office 365 qui utilisent l’authentification unique (SSO) par le biais des services AD FS 2.0 et qui disposent de plusieurs domaines de niveau supérieur pour les suffixes UPN des utilisateurs au sein de leur entreprise (par exemple, @contoso.com ou @fabrikam.com)) doivent déployer une instance distincte du service FS (Federation Service) AD FS 2.0 pour chaque suffixe. Il existe désormais un [correctif cumulatif pour ADFS 2.0](http://support.microsoft.com/kb/2607496) qui fonctionne conjointement avec le commutateur **SupportMultipleDomain** pour permettre au serveur ADFS de prendre en charge ce scénario sans nécessiter d’autres serveurs ADFS 2.0. Pour plus d’informations, consultez [ce blog](https://blogs.technet.microsoft.com/abizerh/2013/02/05/supportmultipledomain-switch-when-managing-sso-to-office-365/).


## <a name="android-issues"></a>Problèmes Android
### <a name="devices-fail-to-check-in-with-the-intune-service-and-display-as-unhealthy-in-the-intune-admin-console"></a>Les appareils ne parviennent pas à se connecter au service Intune et affichent le message « Défectueux » dans la console d’administration Intune
**Problème :** Certains appareils Samsung exécutant des versions Android 4.4.x et 5.x peuvent interrompre la connexion au service Intune. Si les appareils ne sont pas connectés :

- Ils ne peuvent pas recevoir la stratégie, les applications et les commandes à distance du service Intune.
- Ils affichent un état de gestion **Défectueux** dans la console Administrateur.
- Les utilisateurs qui sont protégés par des stratégies d’accès conditionnel peuvent perdre l’accès aux ressources d’entreprise.

Samsung a confirmé que le logiciel Samsung Smart Manager, fourni sur certains appareils Samsung, peut désactiver le portail d’entreprise Intune et ses composants. Lorsque le portail d’entreprise est désactivé, il ne peut pas s’exécuter en arrière-plan et par conséquent, il ne peut pas contacter le service Intune.

**Résolution #1 :**

Demandez à vos utilisateurs de démarrer manuellement l’application Portail d’entreprise. Une fois l’application redémarrée, l’appareil se connecte au service Intune.

> [!IMPORTANT]
> L’ouverture manuelle de l’application Portail d’entreprise est une solution temporaire, car Samsung Smart Manager peut la désactiver de nouveau.

**Résolution #2 :**

Demandez à vos utilisateurs de tenter la mise à niveau vers Android 6.0. Le problème de désactivation ne se produit pas sur les appareils Android 6.0. Pour vérifier si une mise à jour est disponible, les utilisateurs peuvent accéder à **Paramètres** > **À propos de l’appareil** > **Télécharger manuellement des mises à jour**, et suivre les invites sur l’appareil.

**Résolution #3 :**

Si la résolution #2 ne fonctionne pas, indiquez à vos utilisateurs de suivre ces étapes afin que Smart Manager exclue l’application Portail d’entreprise :

1. Lancez l’application Smart Manager sur l’appareil.

  ![Sélectionner l’icône Smart Manager sur l’appareil](./media/smart-manager-app-icon.png)

2. Choisissez la vignette **Batterie**.

  ![Sélectionner la vignette Batterie](./media/smart-manager-battery-tile.png)

3. Sous **Économie d’énergie de l’application** ou **Optimisation de l’application**, sélectionnez **Détail**.

  ![Sélectionner Détail sous Économie d’énergie de l’application ou Optimisation de l’application](./media/smart-manager-app-power-saving-detail.png)

4. Choisissez **Portail d’entreprise** dans la liste des applications.

  ![Sélectionner Portail d’entreprise dans la liste des applications](./media/smart-manager-company-portal.png)

5. Choisissez **Désactivé**.

  ![Sélectionner Désactivé dans la boîte de dialogue Optimisation de l’application](./media/smart-manager-app-optimization-turned-off.png)

6. Sous **Économie d’énergie de l’application** ou **Optimisation de l’application**, vérifiez que le portail d’entreprise est désactivé.

  ![Vérifier que le portail d’entreprise est désactivé](./media/smart-manager-verify-comp-portal-turned-off.png)


### <a name="profile-installation-failed"></a>Échec de l’installation du profil
**Problème :** Un utilisateur reçoit l’erreur **Échec de l’installation du profil** sur un appareil Android.

**Résolution :**

1.  Vérifiez que l’utilisateur a reçu une licence appropriée pour la version du service Intune que vous utilisez.

2.  Vérifiez que l’appareil n’est pas déjà inscrit auprès d’un autre fournisseur GPM ou qu’il ne dispose pas déjà d’un profil de gestion.

3.  Vérifiez que Chrome pour Android est le navigateur par défaut et que les cookies sont activés.

### <a name="android-certificate-issues"></a>Problèmes touchant les certificats Android

**Problème** : Les utilisateurs reçoivent le message suivant sur leur appareil : *Vous ne pouvez pas vous connecter, car il manque un certificat obligatoire à votre appareil.*

**Résolution 1 **:

Demandez à vos utilisateurs de suivre les instructions fournies dans [Un certificat obligatoire est manquant sur votre appareil](/intune/enduser/your-device-is-missing-a-required-certificate-android#your-device-is-missing-a-certificate-required-by-your-it-administrator). Si après cela l’erreur persiste, essayez la Résolution 2.

**Résolution 2** :

Si l’erreur de certificat manquant s’affiche toujours une fois que les utilisateurs ont entré leurs informations d’identification d’entreprise et qu’ils ont été redirigés vers l’expérience de connexion fédérée, il est possible qu’un certificat intermédiaire soit manquant sur votre serveur AD FS (Active Directory Federation Services).

L’erreur de certificat se produit car les appareils Android nécessitent l’inclusion de certificats intermédiaires dans un message [hello de serveur SSL](https://technet.microsoft.com/library/cc783349.aspx), mais actuellement une installation de serveur AD FS ou de serveur Proxy AD FS par défaut envoie uniquement le certificat SSL du service AD FS dans la réponse hello de serveur SSL à une demande hello de client SSL.

Pour résoudre ce problème, importez les certificats dans les certificats personnels de l’ordinateur sur les proxys ou le serveur AD FS en procédant comme suit :

1.    Sur les serveurs ADFS et proxy, lancez la console de gestion des certificats pour l’ordinateur local en cliquant avec le bouton droit sur le bouton **Démarrer**, en choisissant **Exécuter** et en tapant **certlm.msc**.
2.    Développez **Personnel** et sélectionnez **Certificats**.
3.    Recherchez le certificat pour votre communication avec le service AD FS (un certificat signé publiquement) et double-cliquez dessus pour afficher ses propriétés.
4.    Sélectionnez l’onglet **Chemin d’accès de certification** pour afficher les certificats parents du certificat.
5.    Sur chaque certificat parent, sélectionnez **Afficher le certificat**.
6.    Sélectionnez l’onglet **Détails** et choisissez **Copier dans un fichier**.
7.    Suivez les invites de l’Assistant pour exporter ou enregistrer la clé publique du certificat à l’emplacement de fichier souhaité.
8.    Importez les certificats parents qui ont été exportés à l’étape 3 dans Ordinateur local\Personnel\Certificats en double-cliquant sur **Certificats**, en sélectionnant **Toutes les tâches** > **Importer**, puis en suivant les invites de l’Assistant pour importer les certificats.
9.    Redémarrez les serveurs AD FS.
10.    Répétez les étapes ci-dessus sur tous les serveurs proxy et AD FS.
L’utilisateur doit maintenant être en mesure de se connecter au site Portail d’entreprise sur l’appareil Android.

**Pour vérifier que le certificat a été installé correctement** :

Les étapes suivantes décrivent l’une des nombreuses méthodes et outils permettant de vérifier que le certificat a été installé correctement.

1. Accédez à l’[outil gratuit Digicert](ttps://www.digicert.com/help/).
2. Entrez le nom de domaine complet de votre serveur AD FS (par exemple, sts.contoso.com), puis sélectionnez **CHECK SERVER**.

Si le certificat de serveur est installé correctement, toutes les coches s’affichent dans les résultats. Si le problème ci-dessus se produit, un X rouge apparaît dans les sections « Certificate Name Matches » et « SSL Certificate is correctly Installed » du rapport.


## <a name="ios-issues"></a>Problèmes iOS

### <a name="devices-are-inactive-or-the-admin-console-cannot-communicate-with-them"></a>Les appareils sont inactifs ou la console d’administration ne peut pas communiquer avec eux
**Problème :** Les appareils iOS ne sont pas enregistrés auprès du service Intune. Les appareils doivent être régulièrement enregistrés auprès du service pour conserver l’accès aux ressources d’entreprise protégées. Si les appareils ne sont pas enregistrés :

- Ils ne peuvent pas recevoir la stratégie, les applications et les commandes à distance du service Intune.
- Ils affichent un état de gestion **Défectueux** dans la console Administrateur.
- Les utilisateurs qui sont protégés par des stratégies d’accès conditionnel peuvent perdre l’accès aux ressources d’entreprise.

**Solution :** Partagez les solutions suivantes avec les utilisateurs finaux pour les aider à récupérer l’accès aux ressources d’entreprise.

Quand les utilisateurs démarrent l’application Portail d’entreprise iOS, celle-ci peut leur indiquer si leur appareil a perdu le contact avec Intune. Si elle détecte une absence de contact, elle essaie automatiquement de se synchroniser avec Intune pour se reconnecter et les utilisateurs voient la notification en ligne **Tentative de synchronisation...** .

  ![Notification Tentative de synchronisation](./media/ios_cp_app_trying_to_sync_notification.png)

Si la synchronisation est réussie, la notification en ligne **Synchronisation réussie** s’affiche dans l’application Portail d’entreprise iOS, indiquant que votre appareil est dans un état d’intégrité correct.

  ![Notification Synchronisation réussie](./media/ios_cp_app_sync_successful_notification.png)

Si la synchronisation échoue, la notification en ligne **Synchronisation impossible** s’affiche dans l’application Portail d’entreprise iOS.

  ![Notification Synchronisation impossible](./media/ios_cp_app_unable_to_sync_notification.png)

Pour résoudre le problème, les utilisateurs doivent sélectionner le bouton **Configurer** qui apparaît à droite de la notification **Synchronisation impossible**. Le bouton Configurer dirige les utilisateurs vers l’écran de flux de configuration de l’accès à l’entreprise, où ils peuvent suivre les invites pour inscrire leur appareil.

  ![Écran de configuration de l’accès à l’entreprise](./media/ios_cp_app_company_access_setup.png)

Une fois inscrits, les appareils retrouvent un état d’intégrité correct et récupèrent l’accès aux ressources d’entreprise.

### <a name="profile-installation-failed"></a>Échec de l’installation du profil
**Problème :** Un utilisateur reçoit l’erreur **Échec de l’installation du profil** sur un appareil iOS.

### <a name="troubleshooting-steps-for-failed-profile-installation"></a>Procédure de dépannage en cas d’échec de l’installation d’un profil

1.  Vérifiez que l’utilisateur a reçu une licence appropriée pour la version du service Intune que vous utilisez.

2.  Vérifiez que l’appareil n’est pas déjà inscrit auprès d’un autre fournisseur GPM ou qu’il ne dispose pas déjà d’un profil de gestion.

3.  Accédez à [https://portal.manage.microsoft.com](https://portal.manage.microsoft.com) et essayez d’installer le profil quand vous y êtes invité.

4.  Vérifiez que Safari pour iOS est le navigateur par défaut et que les cookies sont activés.

### <a name="enrolled-ios-device-doesnt-appear-in-console-when-using-system-center-configuration-manager-with-intune"></a>L’appareil iOS inscrit n’apparaît pas dans la console lors de l’utilisation de System Center Configuration Manager avec Intune
**Problème :** l’utilisateur inscrit l’appareil iOS, mais celui-ci n’apparaît pas dans la console d’administration de Configuration Manager. L’appareil n’indique pas qu’il a été inscrit. Causes possibles :

- Le connecteur Microsoft Intune sur votre site Configuration Manager ne communique pas avec le service Intune.
- Le composant Data Discovery Manager (ddm) ou le composant State Manager (statmgr) ne traite pas les messages du service Intune.
- Vous avez peut-être téléchargé le certificat de gestion des appareils mobiles à partir d’un compte et vous l’avez utilisé dans un autre compte.


**Résolution :** Passez en revue les fichiers journaux suivants pour détecter les erreurs possibles :

- dmpdownloader.log
- ddm.log
- statmgr.log

Des exemples seront bientôt ajoutés concernant les éléments à rechercher dans ces fichiers journaux.


## <a name="issues-when-using-system-center-configuration-manager-with-intune"></a>Problèmes quand vous utilisez System Center Configuration Manager avec Intune
### <a name="mobile-devices-disappear"></a>Les appareils mobiles disparaissent
**Problème :** Après avoir inscrit un appareil mobile dans Configuration Manager, il disparaît du regroupement d’appareils mobiles, mais l’appareil a toujours son profil de gestion et est répertorié dans la passerelle CSS.

**Résolution :** Cela peut être dû au fait qu’un processus personnalisé supprime les appareils non joints à un domaine ou que l’utilisateur a retiré l’appareil de l’abonnement. Pour identifier le processus ou le compte d’utilisateur qui a supprimé l’appareil de la console Configuration Manager, procédez comme suit.

#### <a name="check-how-device-was-removed"></a>Vérifier comment l’appareil a été supprimé

1.  Dans la console d’administration Configuration Manager, sélectionnez **Analyse** &gt; **État du système** &gt; **Requêtes sur les messages d’état**.

2.  Cliquez avec le bouton droit sur **Ressources du membre pour un regroupement supprimées manuellement**, puis sélectionnez **Afficher les messages**.

3.  Choisissez une heure/date appropriée ou les 12 dernières heures.

4.  Recherchez l’appareil en question et vérifiez comment l’appareil a été supprimé. L’exemple ci-dessous indique que le compte SCCMInstall a supprimé l’appareil via une application inconnue.

    ![Capture d’écran du diagnostic de suppression d’appareil](./media/CM_With_Intune_Unknown_App_Deleted_Device.jpg)

5.  Vérifiez que Configuration Manager n’a pas de tâche, de script ou tout autre processus planifié qui pourrait vider automatiquement les appareils mobiles hors domaine ou associés.




### <a name="other-ios-enrollment-errors"></a>Autres erreurs d’inscription iOS
Une liste des erreurs d’inscription iOS est fournie dans la documentation de l’utilisateur de l’appareil, dans [Des erreurs se produisent pendant l’inscription de votre appareil dans Intune](/intune/enduser/using-your-iOS-or-macOS-device-with-intune).

## <a name="pc--issues"></a>Problèmes liés aux PC

### <a name="the-machine-is-already-enrolled---error-hr-0x8007064c"></a>L’ordinateur est déjà inscrit - Erreur hr 0x8007064c
**Problème :** L’inscription échoue avec l’erreur **L’ordinateur est déjà inscrit**. Le journal d’inscription affiche l’erreur **hr 0x8007064c**.

Cela peut être dû au fait que l’ordinateur avait déjà été inscrit précédemment ou qu’il a l’image clonée d’un ordinateur qui avait été inscrit. Le certificat de compte du compte précédent est toujours présent sur l’ordinateur.



**Résolution :**

1. Dans le menu **Démarrer**, tapez **Exécuter** -> **MMC**.
1. Choisissez **Fichier** > **Ajouter/supprimer des composants logiciels enfichables**.
1. Double-cliquez sur **Certificats**, choisissez **Compte ordinateur** > **Suivant**, puis sélectionnez **Ordinateur local**.
1. Double-cliquez sur **Certificats (ordinateur local)**, puis choisissez **Personnel / certificats**.
1. Recherchez le certificat Intune émis par Sc_Online_Issuing et supprimez-le, le cas échéant.
1. Supprimez la clé de Registre **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\OnlineManagement regkey** si elle existe, ainsi que toutes les sous-clés.
1. Tentez la réinscription.
1. Si le PC ne peut toujours pas être inscrit, recherchez la clé **KEY_CLASSES_ROOT\Installer\Products\6985F0077D3EEB44AB6849B5D7913E95** et supprimez-la, si elle existe.
1. Tentez la réinscription.

    > [!IMPORTANT]
    > Cette section, méthode ou tâche contient des étapes qui vous indiquent comment modifier le registre. Toutefois, des problèmes importants peuvent survenir si vous modifiez le registre de façon incorrecte. Par conséquent, assurez-vous de suivre les étapes avec précaution. Pour plus de protection, sauvegardez le registre avant de le modifier. Vous pourrez ainsi restaurer le Registre en cas de problème.
    > Pour plus d’informations sur la procédure de sauvegarde et de restauration du registre, consultez [Procédure de sauvegarde et de restauration du registre dans Windows](https://support.microsoft.com/en-us/kb/322756)

## <a name="general-enrollment-error-codes"></a>Codes généraux des erreurs d’inscription

|Code d’erreur|Problème possible|Solution suggérée|
|--------------|--------------------|----------------------------------------|
|0x80CF0437 |L'horloge de l'ordinateur client n'est pas réglée sur l'heure correcte.|Assurez-vous que l'horloge et le fuseau horaire de l'ordinateur client sont correctement réglés.|
|0x80240438, 0x80CF0438, 0x80CF402C|Impossible de se connecter au service Intune. Vérifiez les paramètres de proxy du client.|Vérifiez que la configuration du proxy sur l’ordinateur client est prise en charge par Intune et que l’ordinateur client dispose d’un accès à Internet.|
|0x80240438, 0x80CF0438|Les paramètres de proxy dans Internet Explorer et le système local ne sont pas configurés.|Impossible de se connecter au service Intune. Vérifiez les paramètres de proxy du client et assurez-vous que la configuration proxy sur l’ordinateur client est prise en charge par Intune et que l’ordinateur client a accès à Internet.|
|0x80043001, 0x80CF3001, 0x80043004, 0x80CF3004|Le package d'inscription n'est plus à jour.|Téléchargez et installez le package de logiciel client le plus récent à partir de l’espace de travail Administration.|
|0x80043002, 0x80CF3002|Le compte est en mode de maintenance.|Vous ne pouvez pas inscrire de nouveaux ordinateurs clients lorsque le compte est en mode de maintenance. Pour afficher les paramètres de votre compte, connectez-vous à ce dernier.|
|0x80043003, 0x80CF3003|Le compte a été supprimé.|Vérifiez que votre compte et votre abonnement à Intune sont toujours actifs. Pour afficher les paramètres de votre compte, connectez-vous à ce dernier.|
|0x80043005, 0x80CF3005|L'ordinateur client a été mis hors service.|Patientez quelques heures, supprimez les anciennes versions du logiciel client de l'ordinateur et essayez de le réinstaller.|
|0x80043006, 0x80CF3006|Le nombre maximal de sièges autorisés pour le compte a été atteint.|Votre entreprise doit acheter des sièges supplémentaires pour que vous puissiez inscrire davantage d'ordinateurs clients dans le service.|
|0x80043007, 0x80CF3007|Impossible de trouver le fichier de certificat dans le même dossier que le programme d'installation.|Extrayez tous les fichiers avant de commencer l'installation. Ne renommez pas et ne déplacez pas les fichiers extraits : tous les fichiers doivent se trouver dans le même dossier sans quoi l'installation échouera.|
|0x8024D015, 0x00240005, 0x80070BC2, 0x80070BC9, 0x80CFD015|Le logiciel ne peut pas être installé, car un redémarrage de l'ordinateur client est en attente.|Redémarrez l'ordinateur, puis réessayez d'installer le logiciel client.|
|0x80070032|Une ou plusieurs conditions requises pour l'installation du logiciel client n'ont pas été remplies au niveau de l'ordinateur.|Assurez-vous que toutes les mises à jour nécessaires sont installées sur l'ordinateur client, puis réessayez d'installer le logiciel client.|
|0x80043008, 0x80CF3008|Échec du démarrage du service des mises à jour de gestion Microsoft Online.|Contactez le support Microsoft comme décrit dans [Comment obtenir un support technique pour Microsoft Intune](how-to-get-support-for-microsoft-intune.md).|
|0x80043009, 0x80CF3009|L'ordinateur client est déjà inscrit dans le service.|Vous devez mettre hors service l'ordinateur client avant de le réinscrire dans le service.|
|0x8004300B, 0x80CF300B|Impossible d'exécuter le package d'installation du logiciel client car la version de Windows en cours d'exécution sur le client n'est pas prise en charge.|Intune ne prend pas en charge la version de Windows en cours d’exécution sur l’ordinateur client.|
|0xAB2|Windows Installer n'a pas pu accéder à l'exécution VBScript d'une action personnalisée.|Cette erreur est générée par une action personnalisée basée sur des DLL (Dynamic-Link Libraries). Pour résoudre les problèmes liés aux DLL, vous pouvez avoir besoin d’utiliser les outils décrits dans [Microsoft Support KB198038: Useful Tools for Package and Deployment Issues](https://support.microsoft.com/en-us/kb/198038) (KB198038 du support technique Microsoft : Outils utiles en cas de problèmes de package et de déploiement).|
|0x80cf0440|La connexion au point de terminaison de service s'est terminée.|Le compte d’évaluation ou payant est suspendu. Créez un nouveau compte d’évaluation ou payant et recommencez l’inscription.|




### <a name="next-steps"></a>Étapes suivantes
Si ces informations de dépannage n’ont pas permis de vous aider, contactez le support Microsoft comme décrit dans [Comment obtenir un support technique pour Microsoft Intune](how-to-get-support-for-microsoft-intune.md).

