---
title: Changer votre autorité MDM pour Configuration Manager (MDM hybride)
description: Découvrez comment changer l’autorité MDM d’une version autonome d’Intune pour Configuration Manager (MDM hybride).
keywords: ''
author: dougeby
manager: dougeby
ms.date: 10/04/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f1b4bce3-7932-4a0d-aa92-6dacc7060f42
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: dc73befb46f1f159d9a8c023bb5604517b9f73f4
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31028059"
---
# <a name="change-the-mdm-authority"></a>Changer l’autorité MDM
À compter de Configuration Manager version 1610, vous pouvez changer votre autorité MDM sans avoir à contacter le Support Microsoft, et sans devoir désinscrire puis réinscrire vos appareils gérés existants. Cette rubrique décrit la procédure pour changer un locataire Microsoft Intune existant configuré à partir d’Intune et avec **Microsoft Intune** (version autonome) comme autorité MDM pour **Configuration Manager** (MDM hybride), sans devoir désinscrire puis réinscrire vos appareils gérés existants.

> [!Note]    
> Si vous voulez changer un locataire Microsoft Intune existant configuré à partir de la console Configuration Manager (hybride) et avec l’autorité MDM définie sur **Configuration Manager** (hybride) pour une version autonome de **Microsoft Intune**, consultez [Changer l’autorité MDM de Configuration Manager (MDM hybride) pour Intune (version autonome)](https://docs.microsoft.com/sccm/mdm/deploy-use/change-mdm-authority). 


## <a name="key-considerations"></a>Principales considérations
Après le passage à la nouvelle autorité MDM, une période de transition (jusqu'à huit heures) peut survenir avant que l’appareil n’effectue l’archivage et ne se synchronise avec le service. Vous devez configurer les paramètres de la nouvelle autorité MDM (hybride) pour garantir que les appareils inscrits continueront d’être gérés et protégés après le changement. 
- Les appareils doivent se connecter au service après le changement afin que les paramètres de la nouvelle autorité MDM (version autonome d’Intune) remplacent les paramètres existants sur l’appareil.
- Une fois le changement d’autorité MDM effectué, certains des paramètres de base (comme les profils) de l’autorité MDM précédente (version autonome d’Intune) restent sur l’appareil pendant sept jours ou jusqu’à ce que l’appareil se connecte au service pour la première fois. Il est recommandé de configurer dès que possible les applications et les paramètres (stratégies, profils, applications, etc.) de la nouvelle autorité MDM (hybride), et de déployer le paramètre sur les groupes d’utilisateurs contenant des utilisateurs qui ont des appareils inscrits existants. Dès qu’un appareil se connecte au service après le changement d’autorité MDM, il reçoit les nouveaux paramètres de la nouvelle autorité MDM, évitant ainsi toute interruption dans la gestion et la protection.
- Quand les mêmes catégories d’appareils existent à la fois dans Intune et dans Configuration Manager, les affectations de catégorie aux appareils ne sont pas effectuées après le passage à la nouvelle autorité MDM. Pour continuer à utiliser les catégories d’appareils, les appareils migrés doivent être ajoutés manuellement aux collections appropriées une fois que l’autorité MDM est changée et que les appareils s’affichent dans la console Configuration Manager.
- Les appareils qui n’ont pas d’utilisateurs associés (en général, lorsque vous utilisez le Programme d’inscription des appareils iOS ou des scénarios d’inscription en bloc) ne sont pas migrés vers la nouvelle autorité MDM. Pour ces appareils, vous devez contacter le support afin d’obtenir de l’aide pour déplacer ces appareils vers la nouvelle autorité MDM.

## <a name="prepare-to-change-the-mdm-authority-to-configuration-manager-hybrid"></a>Se préparer à utiliser Configuration Manager (hybride) comme autorité MDM
Passez en revue les informations suivantes pour préparer le passage à l’autorité MDM :
- Vous devez disposer de Configuration Manager 1610 ou version ultérieure pour pouvoir changer d’autorité MDM.
- Après le passage à la nouvelle autorité MDM, la connexion d’un appareil au service peut prendre jusqu’à huit heures.
- Créez un regroupement d’utilisateurs Configuration Manager contenant tous les utilisateurs actuellement gérés par Intune autonome, à utiliser quand vous configurez l’abonnement Intune dans la console Configuration Manager. Ceci permet de garantir que l’utilisateur et ses appareils disposent d’une licence Configuration Manager et qu’ils sont gérés dans l’environnement hybride après le changement d’autorité MDM.
- Assurez-vous que l’utilisateur administrateur informatique figure également dans ce regroupement.  
- Avant le changement, l’autorité MDM apparaît sous la forme **Définir sur Microsoft Intune** (autonome) dans la console d’administration Intune.
- L’autorité MDM devrait s’afficher sous la forme **Définir sur Microsoft Intune** (locataire autonome) dans la console d’administration Microsoft Intune avant le changement d’autorité MDM.
    > [!NOTE]    
    > Si votre autorité MDM apparaît sous la forme **Géré par Intune et Office 365**, vos appareils MDM gérés par Office 365 ne sont plus gérés quand vous utilisez **Configuration Manager** (hybride) comme autorité MDM. Nous vous recommandons d’attribuer à ces utilisateurs une licence Intune ou Enterprise Mobility Suite avant de changer d’autorité MDM.   

- Dans la [console d’administration Microsoft Intune](http://manage.microsoft.com), supprimez le rôle Gestionnaire d’inscription d’appareil. Pour plus d’informations, consultez [Supprimer un gestionnaire d'inscription d'appareil d'Intune](/intune-classic/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune#delete-a-device-enrollment-manager-from-intune).
- Désactivez tous les mappages de groupes d’appareils configurés. Pour plus d’informations, consultez [Catégoriser les appareils avec un mappage de groupes d’appareils dans Microsoft Intune](/intune-classic/deploy-use/categorize-devices-with-device-group-mapping-in-microsoft-intune).
- Le changement d’autorité MDM ne devrait avoir aucun impact significatif sur les utilisateurs finaux. Toutefois, vous pouvez en informer ces utilisateurs pour s’assurer que leurs appareils sont sous tension et qu’ils se connectent au service peu après le changement. Cela permet de connecter et d’inscrire autant d’appareils que possible auprès du service aussitôt la nouvelle autorité sélectionnée.
- Si vous utilisez Intune autonome pour gérer des appareils iOS avant le changement d’autorité MDM, vous devez veiller à ce que le même certificat du service de notification push d'Apple (APNs) précédemment utilisé dans Intune soit renouvelé et utilisé pour réinstaller le locataire dans Configuration Manager (hybride).    

    > [!IMPORTANT]  
    > Si un autre certificat APNs est utilisé pour la version hybride, l’inscription de TOUS les appareils iOS précédemment inscrits est annulée et vous devez les réinscrire. Avant de changer d’autorité MDM, assurez-vous que vous savez exactement quel certificat APNs a été utilisé pour gérer les appareils iOS dans Intune. Recherchez le même certificat affiché dans le portail Apple Push Certificates (https://identity.apple.com)) et vérifiez que l’utilisateur dont l’ID Apple a été utilisé pour créer le certificat d’origine est identifié et disponible pour renouveler le même certificat APNs dans le cadre du changement d’autorité MDM.  

## <a name="change-the-mdm-authority-to-configuration-manager"></a>Utiliser Configuration Manager comme autorité MDM
Le processus pour utiliser Configuration Manager (hybride) comme autorité MDM comprend les étapes principales suivantes :  
- Dans la console Configuration Manager, ajoutez l’abonnement Microsoft Intune.
- Configurez le certificat APNs Apple en utilisant le même certificat APNs que vous avez renouvelé.
- Dans la console Configuration Manager, configurez et déployez les nouveaux réglages et les nouvelles applications à partir de la nouvelle autorité MDM (hybride).
- La prochaine fois qu’ils se connecteront au service, les appareils se synchronisent et reçoivent les nouveaux paramètres à partir de la nouvelle autorité MDM.

#### <a name="to-change-the-mdm-authority-to-configuration-manager"></a>Pour utiliser Configuration Manager comme autorité MDM
1. Dans la console Configuration Manager, accédez à **Administration** &gt; **Vue d’ensemble** &gt; **Services Cloud** &gt; **Abonnement Microsoft Intune**, puis choisissez d’ajouter un abonnement Intune.
2. Connectez-vous au locataire Intune que vous avez utilisé lors de la première définition de l’autorité MDM dans Intune, puis cliquez sur **Suivant**.
3. Sélectionnez **Utiliser Configuration Manager comme autorité MDM**, puis cliquez sur **suivant**.
4. Sélectionnez le regroupement d’utilisateurs contenant tous les utilisateurs qui continuent d’être gérés par la nouvelle autorité MDM hybride.
5. Cliquez sur **Suivant** pour terminer l'Assistant. La nouvelle autorité MDM est désormais **Configuration Manager**.
6. Connectez-vous à la [console d’administration Microsoft Intune](http://manage.microsoft.com) en utilisant le même locataire Intune et vérifiez que l’autorité MDM a été changée en **Définir sur Configuration Manager**.


## <a name="enable-ios-enrollment"></a>Activer l'inscription iOS
Si vous utilisez des appareils iOS, vous devez configurer le certificat APNs dans Configuration Manager.

#### <a name="to-enable-ios-enrollment-and-configure-the-apns-certificate"></a>Pour activer l’inscription iOS et configurer le certificat APNs

1. **Télécharger une demande de signature de certificat**

   1. Dans la console Configuration Manager, accédez à **Administration** &gt; **Services cloud** &gt; **Abonnements Microsoft Intune**, puis sélectionnez **Créer une demande de certificat APNs** pour ouvrir la boîte de dialogue **Effectuer une demande de signature de certificat APNs**.  
   2. Cliquez sur**Parcourir** pour accéder à l'emplacement auquel vous souhaitez enregistrer le fichier du nouveau certificat de demande de signature (.csr). Enregistrez localement le fichier de demande de signature de certificat (.csr).  
   3. Cliquez sur **Télécharger**. Le nouveau fichier .csr Microsoft Intune se télécharge et il est enregistré par Configuration Manager.   

      > [!IMPORTANT]
      > Vous devez télécharger une nouvelle demande de signature de certificat. N’utilisez pas un fichier existant car dans ce cas, l’opération échoue.  

2. Accédez au [portail Apple Push Certificates](http://go.microsoft.com/fwlink/?LinkId=269844), connectez-vous avec le **même** ID Apple utilisé précédemment pour créer et renouveler le certificat APNs dans Intune autonome.

   ![Page de connexion au portail Apple Push Certificates](../media/mdm-change-apns-portal.png)

3. Sélectionnez le certificat APNs que vous avez utilisé dans Intune autonome, puis cliquez sur **Renouveler**.

    ![Boîte de dialogue de renouvellement du certificat APNs](../media/mdm-change-renew-apns.png)

4. Sélectionnez le fichier de la demande de signature du certificat APNs (.csr) que vous avez téléchargé localement, puis cliquez sur **Charger**.

    ![Page de connexion au portail Apple Push Certificates](../media/mdm-change-renew-apns-upload.png)
 
5. Sélectionnez les mêmes certificats APNs, puis cliquez sur **Télécharger**. Téléchargez le certificat APNs (.pem) et enregistrez le fichier localement.  

    ![Page de connexion au portail Apple Push Certificates](../media/mdm-change-renew-apns-download.png)

6. Chargez le certificat APNs renouvelé sur le locataire hybride en utilisant le même ID Apple qu’auparavant.

    1.  Dans la console Configuration Manager, accédez à **Administration** &gt; **Services cloud** &gt; **Abonnement Microsoft Intune**, puis choisissez **Configurer des plateformes** &gt; **iOS**.  
    2.  Dans la boîte de dialogue **Propriétés des abonnements Microsoft Intune**, sélectionnez l’onglet **Certificat APNs** puis cochez la case **Activer l'inscription iOS et Mac OS X (MDM)**.  
    3.  Cliquez sur **Parcourir**et accédez au fichier (.cer) du certificat APNs téléchargé à partir d’Apple. Configuration Manager affiche les informations du certificat APNs. Cliquez sur **OK** pour enregistrer le certificat APNs sur Intune.  

        ![Page des propriétés des abonnements Intune - iOS](../media/mdm-change-subscription-properties-ios.png)

## <a name="enable-android-enrollment"></a>Activer l’inscription Android
1. Dans la console Configuration Manager, accédez à **Administration** &gt; **Services cloud** &gt; **Abonnement Microsoft Intune**, puis choisissez **Configurer des plateformes** &gt; **Android**.  
2. Sélectionnez **Activer l’inscription Android** et cliquez sur **OK**.

### <a name="enable-windows-enrollment"></a>Activer l’inscription Windows
1. Dans la console Configuration Manager, accédez à **Administration** &gt; **Services cloud** &gt; **Abonnement Microsoft Intune**, puis choisissez **Configurer des plateformes** &gt; **Windows**.  
2. Sélectionnez **Activer l’inscription Windows** et cliquez sur **OK**.

### <a name="enable-windows-phone-enrollment"></a>Activer l’inscription Windows Phone
1. Dans la console Configuration Manager, accédez à **Administration** &gt; **Services cloud** &gt; **Abonnement Microsoft Intune**, puis choisissez **Configurer des plateformes** &gt; **Windows Phone**.  
2. Sélectionnez la plateforme que vous souhaitez activer, puis cliquez sur **OK**.


## <a name="next-steps"></a>Étapes suivantes
Une fois le changement d’autorité MDM effectué, passez en revue les étapes suivantes :
- Quand le service Intune détecte que l’autorité MDM d’un locataire a changé, il envoie un message de notification à tous les appareils inscrits pour qu’ils s’enregistrent et se synchronisent avec le service (ces opérations sont effectuées en dehors de l’enregistrement régulier planifié). Par conséquent, une fois que l’autorité MDM du locataire est passée de la version autonome d’Intune à hybride, tous les appareils sous tension et en ligne se connecteront au service, recevront la nouvelle autorité MDM et seront désormais gérés par la version hybride. Il n’y a aucune interruption au niveau de la gestion et de la protection de ces appareils.
- Même si les appareils sont sous tension et en ligne pendant (ou juste après) le changement d’autorité MDM, un délai de huit heures maximum s’écoulera (selon l’heure du prochain enregistrement régulier planifié) avant que les appareils soient inscrits auprès du service sous la nouvelle autorité MDM.    

  > [!IMPORTANT]    
  > Entre le moment où vous changez l’autorité MDM et celui où le certificat APNs renouvelé est chargé dans la nouvelle autorité, les inscriptions de nouveaux appareils et l’enregistrement d’appareils iOS échouent. Par conséquent, il est important de passer en revue et de charger le certificat APNs dans la nouvelle autorité dès que possible après le changement d’autorité MDM.

- Les utilisateurs peuvent rapidement basculer vers la nouvelle autorité MDM en lançant manuellement un enregistrement de l’appareil vers le service. Les utilisateurs peuvent facilement effectuer cette opération à l’aide de l’application du portail d’entreprise, en lançant une vérification de conformité d’appareil.
- Pour confirmer que tout fonctionne correctement une fois les appareils enregistrés et synchronisés avec le service après le changement d’autorité MDM, recherchez les appareils dans la console Configuration Manager. Les appareils précédemment gérés par Intune apparaissent désormais en tant qu’appareils gérés dans la console Configuration Manager.    
- Il existe une période temporaire pendant laquelle un appareil est hors ligne lors du changement d’autorité MDM et lorsque cet appareil s’enregistre auprès du service. Pour que l’appareil reste protégé et opérationnel pendant cet intervalle, les profils suivants y sont conservés pendant sept jours maximum (ou jusqu’à ce que l’appareil se connecte à la nouvelle autorité MDM et reçoive les nouveaux paramètres qui remplacent les paramètres existants) :
    - Profil de messagerie
    - Profil VPN
    - Profil de certificat
    - Profil Wi-Fi
    - Profils de configuration
- Après la sélection de la nouvelle autorité MDM, une semaine peut être nécessaire avant que les données de conformité s’affichent correctement dans la console d’administration Microsoft Intune. Cependant, les états de conformité dans Azure Active Directory et sur l’appareil restent corrects et l’appareil est ainsi toujours protégé.
- Vérifiez que les nouveaux paramètres destinés à remplacer les paramètres existants portent le même nom que les précédents pour s’assurer que les anciens paramètres sont remplacés. Sinon, les appareils risquent de contenir des stratégies et des profils redondants.    

  > [!TIP]    
  > Il est recommandé de créer tous les paramètres de gestion et toutes les configurations, ainsi que les déploiements, peu de temps après le changement d’autorité MDM. Ceci permet de garantir que les appareils sont protégés et activement gérés pendant la période temporaire.

-  Après avoir modifié l’autorité MDM, procédez comme suit pour confirmer que les nouveaux appareils sont inscrits correctement auprès de la nouvelle autorité :   
    - Inscrire un nouvel appareil
    - Assurez-vous que l’appareil qui vient d’être inscrit s’affiche dans la console Configuration Manager.
    - Effectuez une action, par exemple un verrouillage à distance, à partir de la console d’administration sur l’appareil. Si elle réussit, l’appareil est géré par la nouvelle autorité MDM.
- Si vous rencontrez des problèmes avec des appareils spécifiques, vous pouvez annuler l’inscription puis réinscrire ces appareils pour les connecter à la nouvelle autorité et les gérer dès que possible.