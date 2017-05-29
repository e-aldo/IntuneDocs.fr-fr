---
title: "Résolution de problèmes d’accès conditionnel | Microsoft Docs"
description: "Cette rubrique décrit les actions à entreprendre quand vos utilisateurs ne parviennent pas à accéder à des ressources par le biais de l’accès conditionnel Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 10/24/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 433fc32c-ca9c-4bad-9616-852c72faf996
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 19635b4dda7f4f04690ad165bad6608cad7ac84f
ms.contentlocale: fr-fr
ms.lasthandoff: 05/23/2017


---

# <a name="troubleshoot-conditional-access"></a>Résoudre les problèmes d’accès conditionnel

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

En général, l’utilisateur tente d’accéder à ses e-mails ou à SharePoint et reçoit une invitation à s’inscrire. Cette invitation le conduit au portail d’entreprise.

Cette rubrique décrit les actions à entreprendre quand vos utilisateurs ne parviennent pas à accéder à des ressources par le biais de l’accès conditionnel Intune.


## <a name="the-basics-for-success-in-conditional-access"></a>Ce qu’il faut savoir pour réussir l’accès conditionnel

Pour que l’accès conditionnel fonctionne, les conditions suivantes doivent être remplies :

-    L’appareil doit être géré par Intune.
-    L’appareil doit être inscrit auprès d’Azure Active Directory (AAD). Normalement, cette opération s’effectue automatiquement pendant l’inscription.
-    L’appareil doit être conforme à vos stratégies de conformité Intune, pour l’appareil et pour l’utilisateur de l’appareil.  Si aucune stratégie de conformité n’existe, l’inscription Intune est suffisante.
-    Exchange ActiveSync doit être activé sur l’appareil si l’utilisateur récupère ses e-mails par l’intermédiaire du client d’e-mail natif de l’appareil, plutôt que par l’intermédiaire d’Outlook.     Ceci se produit automatiquement pour les appareils iOS, Windows Phone et Android/KNOX standard.
-    Votre connecteur Exchange Intune doit être configuré correctement. Pour plus d’informations, consultez [Dépannage du connecteur Exchange dans Microsoft Intune](troubleshoot-exchange-connector.md).

Ces conditions sont visibles sur chaque appareil dans le portail de gestion Azure et dans le rapport d’inventaire des appareils.

## <a name="enrollment-issues"></a>Problèmes d’inscription

 -  L’appareil n’est pas inscrit. L’inscription résoudra le problème.
 -  L’utilisateur a inscrit l’appareil, mais la jonction au lieu de travail a échoué. L’utilisateur doit mettre à jour l’inscription à partir du portail d’entreprise.

## <a name="compliance-issues"></a>Problèmes de conformité

 -  L’appareil n’est pas conforme à la stratégie Intune. Les critères de chiffrement et de mot de passe font partie des problèmes courants. L’utilisateur est redirigé vers le portail d’entreprise, où il peut configurer son appareil pour qu’il soit conforme.
 -  L’inscription des informations de conformité d’un appareil peut demander un certain temps. Attendez quelques minutes et réessayez.
 -  Pour les appareils iOS :
     -   Un profil d’e-mail existant créé par l’utilisateur bloque le déploiement d’un profil créé par un administrateur Intune. Il s’agit d’un problème courant parce que les utilisateurs iOS créent généralement un profil de messagerie, puis s’inscrivent. Le portail d’entreprise informe les utilisateurs qu’ils ne sont pas conformes en raison de leur profil de messagerie configuré manuellement et les invite à supprimer ce profil. Les utilisateurs doivent supprimer leur profil de messagerie pour que le profil Intune puisse être déployé. Pour éviter ce problème, demandez à vos utilisateurs de s’inscrire sans installer de profil de messagerie et d’autoriser Intune à déployer le profil.
     -     Un appareil iOS peut rester bloqué dans un état de vérification de conformité, ce qui empêche l’utilisateur de lancer une autre vérification. Le redémarrage du portail d’entreprise peut résoudre ce problème. L’état de conformité reflètera alors l’état de l’appareil dans Intune. Une fois que toutes les données sont collectées sur un appareil, la synchronisation de la vérification de la conformité est rapide, moins d’une demi-seconde en moyenne.

        En général, les appareils restent dans cet état parce qu’ils rencontrent des problèmes de connexion au service ou parce que la synchronisation prend beaucoup de temps.  Si le problème persiste sur différentes configurations réseau (téléphonie mobile, Wi-Fi, VPN), après redémarrage de l’appareil et après avoir vérifié que le fournisseur de services partagés est à jour sur l’appareil, contactez le support Microsoft comme décrit dans [Guide pratique pour obtenir un support technique pour Microsoft Intune](how-to-get-support-for-microsoft-intune.md).

 - Pour les appareils Android :
     - Certains appareils Android peuvent paraître chiffrés, alors que l’application de portail d’entreprise reconnaît ces appareils comme non chiffrés. 
    
        -    Pour ces appareils, l’utilisateur doit définir un code secret de démarrage sécurisé. L’utilisateur reçoit une notification d’appareil de l’application de portail d’entreprise lui demandant de définir un code secret de démarrage pour l’appareil. Après avoir appuyé sur la notification d’appareil et confirmé votre code confidentiel ou mot de passe existant, choisissez l’option **Exiger un code confidentiel pour démarrer l’appareil** dans l’écran **Démarrage sécurisé**. Ensuite, appuyez sur le bouton **Vérifier la conformité** pour l’appareil dans l’application de portail d’entreprise. L’appareil doit maintenant être détecté comme chiffré.
    
        -     Certains fabricants d’appareils chiffrent leurs appareils à l’aide d’un code confidentiel par défaut à la place du code confidentiel secret défini par l’utilisateur. Intune considère le chiffrement au moyen du code confidentiel par défaut comme non sécurisé. En effet, cette méthode de chiffrement peut mettre en danger les données figurant sur l’appareil face à des utilisateurs mal intentionnés en mesure d’accéder physiquement à l’appareil. Si tel est le problème, envisagez d’utiliser les [stratégies de protection des applications](/intune-classic/deploy-use/azure-portal-for-microsoft-intune-mam-policies).

## <a name="policy-issues"></a>Problèmes de stratégie

Quand vous créez une stratégie de conformité et que vous la liez à une stratégie de messagerie, les deux stratégies doivent être déployées sur le même utilisateur. Par conséquent, soyez vigilant quand vous planifiez quelles stratégies sont déployées sur quels groupes. Les utilisateurs auxquels une seule stratégie est appliquée découvriront probablement que leurs appareils ne sont pas conformes.


## <a name="exchange-activesync-issues"></a>Problèmes Exchange ActiveSync

### <a name="compliant-android-device-gets-quarantine-notice"></a>L’appareil Android compatible reçoit un avis de mise en quarantaine
- Un appareil Android inscrit et conforme peut quand même recevoir une notification de mise en quarantaine quand vous tentez d’accéder à des ressources d’entreprise. Avant de cliquer sur le lien indiquant **Commencer**, l’utilisateur doit vérifier que le portail d’entreprise n’était pas ouvert quand il a tenté d’accéder aux ressources. Les utilisateurs doivent fermer le portail d’entreprise, réessayer d’accéder aux ressources, puis cliquer sur le lien **Commencer**.

### <a name="retired-device-continues-to-have-access"></a>Un appareil mis hors service continue d’avoir un accès.
- Avec Exchange Online, un appareil mis hors service peut continuer à avoir accès aux ressources pendant plusieurs heures après sa mise hors service. En effet, Exchange met en cache les droits d’accès pendant 6 heures. Envisagez d’autres moyens de protéger les données sur les appareils mis hors service dans ce scénario.

### <a name="device-is-compliant-and-registered-with-aad-but-still-blocked"></a>Un appareil est conforme et inscrit sur AAD, mais reste bloqué
- Parfois, l’approvisionnement de l’ID d’Exchange ActiveSync (EASID) sur AAD est retardé. La limitation constitue une cause courante de ce problème. Par conséquent, attendez quelques minutes et réessayez.

### <a name="device-blocked"></a>Appareil bloqué

Un appareil peut être bloqué au niveau de l’accès conditionnel sans recevoir d’e-mail d’activation.

- Existe-t-il une règle Exchange par défaut qui met en quarantaine ou bloque les appareils ? Si une règle par défaut bloque ou met en quarantaine les appareils, ces derniers ne peuvent pas recevoir le message d’activation du connecteur Exchange. Ceci est volontaire.
- Le compte de notification est-il correctement configuré comme décrit dans la configuration de base ?
- L’appareil apparaît-il dans la console d’administration Intune comme appareil Exchange ActiveSync ? Si ce n’est pas le cas, la découverte des appareils est certainement défaillante, probablement en raison d’un problème de synchronisation du connecteur Exchange. Consultez Appareil Exchange ActiveSync non découvert à partir d’Exchange.
- Examinez les journaux du connecteur Exchange pour l’activité sendemail et recherchez les éventuelles erreurs. Un exemple de la commande à rechercher est SendEmail à partir du compte de notification jusqu’à useremail.
- Avant que le connecteur Exchange bloque l’appareil, il envoie l’e-mail d’activation. Si l’appareil est hors connexion, il peut ne pas recevoir l’e-mail d’activation. Vérifiez si le client d’e-mail de l’appareil récupère les e-mails avec Push au lieu de Poll, car cela pourrait également expliquer que l’utilisateur ne reçoit pas l’e-mail. Basculez sur Poll et regardez si l’appareil reçoit l’e-mail.

## <a name="non-compliant-device-not-blocked"></a>Appareil non conforme non bloqué

Si vous constatez qu’un appareil continue à avoir un accès alors qu’il n’est pas conforme, procédez comme suit.

- Vérifiez vos groupes cibles et d’exclusion. Si un utilisateur n’est pas dans le bon groupe cible ou est dans le groupe d’exclusions, il n’est pas bloqué. Seuls les appareils des utilisateurs d’un groupe cible sont vérifiés pour la conformité.
- Assurez-vous que l’appareil est en cours de découverte. Le connecteur Exchange pointe-t-il sur la sécurité d’accès du code Exchange 2010 quand l’utilisateur est sur un serveur Exchange 2013 ? Dans ce cas, si la règle d’Exchange par défaut est Autoriser, même si l’utilisateur est dans le groupe cible, Intune ne peut pas savoir si l’appareil est connecté à Exchange.
- Vérifiez l’état Existence/accès de l’appareil dans Exchange :
    - Utilisez cette applet de commande PowerShell pour obtenir la liste de tous les appareils mobiles d’une boîte aux lettres : "Get-ActiveSyncDeviceStatistics -mailbox mbx'. Si l’appareil n’est pas dans la liste, cela signifie qu’il n’accède pas à Exchange.
    - S’il est dans la liste, utilisez l’applet de commande Get-CASmailbox -identity:’upn’ | fl pour obtenir des informations détaillées sur son état d’accès que vous fournirez au support Microsoft.

## <a name="before-you-open-a-support-ticket"></a>Avant d’ouvrir un ticket de support
Si ces procédures de dépannage ne résolvent pas votre problème, le support Microsoft vous demandera peut-être de fournir des informations comme les journaux de la boîte aux lettres OWA ou les journaux du connecteur Exchange.

### <a name="collecting-owa-mailbox-logs"></a>Collecte des journaux de boîte aux lettres OWA

1. Connectez-vous par le biais d’OWA et choisissez le symbole Paramètres (engrenage) en regard de votre nom en haut à droite.
2. Choisissez **Options**.
3. Choisissez **Téléphone** (ou bien **Appareils mobiles**) dans la colonne sur le côté gauche.
4. Dans le menu affiché en haut, choisissez **Appareils mobiles**.
5. Choisissez votre appareil dans la liste, puis **Démarrer l’enregistrement dans le journal**.
6. Quand vous y êtes invité, choisissez **Oui** dans la boîte de dialogue contextuelle.
7. Exécutez l’action qui a provoqué le problème pour pouvoir le reproduire.
8. Patientez 1 à 2 minutes, puis revenez à la liste téléphonique dans OWA. Vérifiez que votre téléphone est sélectionné dans la liste, puis dans le menu supérieur, choisissez **Récupérer le journal**.
9. Vous devriez maintenant recevoir un e-mail de vous-même avec une pièce jointe. Quand vous ouvrez un ticket de support, fournissez le contenu de l’e-mail au support technique Microsoft.

### <a name="exchange-connector-logs"></a>Journaux du connecteur Exchange

#### <a name="general-log-information"></a>Informations générales sur les journaux
Pour afficher les journaux du connecteur Exchange, utilisez [Server Trace Viewer Tool](server trace viewer tool (https://msdn.microsoft.com/library/ms732023(v=vs.110).aspx'). Pour utiliser cet outil, vous devez télécharger le SDK de Windows Server.

>[!NOTE]
>Les journaux sont dans C:\ProgramData\Microsoft\Windows Intune Exchange Connector\Logs. Ils sont contenus dans une série de 30 fichiers journaux qui vont de *Connector0.log* à *Connector29.log*. Les journaux se remplacent les uns les autres dès que 10 Mo de données ont été accumulées dans un journal. Une fois que les journaux arrivent à Connector29, ils reviennent à Connector0 en remplaçant les fichiers journaux précédents.

#### <a name="locating-sync-logs"></a>Localisation des journaux de synchronisation

-    Localisez une synchronisation complète dans les journaux en recherchant **synchronisation complète**. Le début d’une synchronisation complète est marqué par ce texte :

    « Traitement de la commande : obtention de la liste des appareils mobiles sans filtre de temps (synchronisation complète) pour <number> utilisateurs »

    La fin du journal pour une synchronisation complète ressemble à ceci :

    Obtention de la liste des appareils mobiles sans filtre de temps (synchronisation complète) pour 4 utilisateurs réussie. Détails : Résultat de la commande d’inventaire - Appareils synchronisés : 0 ID de commande : commandIDGUID' Intégrité Exchange : 'Server health 'Nom : 'PowerShellExchangeServer: <Name=nomdemonserveurmail>' État : Connected','

-    Localisez une synchronisation (différentielle) rapide dans les journaux en recherchant **synchronisation rapide**.

##### <a name="exceptions-in-get-next-command"></a>Exceptions dans la commande Get next
Recherchez les exceptions de la **commande get next** dans les journaux du connecteur Exchange et fournissez-les au support Microsoft.

#### <a name="verbose-logging"></a>Journalisation détaillée

Pour activer la journalisation détaillée :

1.    Ouvrez le fichier de configuration de suivi du connecteur Exchange. Le fichier est situé dans : %ProgramData%\Microsoft\Windows Intune Exchange Connector\TracingConfiguration.xml.
2.    Recherchez TraceSourceLine avec la clé suivante : OnPremisesExchangeConnectorService
3.    Remplacez la valeur du nœud **SourceLevel** **Warning ActivityTracing** (par défaut) par **Verbose ActivityTracing**, comme indiqué ci-dessous.

    <TraceSourceLine>
          <Key xsi:type="xsd:string">OnPremisesExchangeConnectorService</Key>
          <Value xsi:type="TraceSource">
            <SourceLevel>All</SourceLevel>
            <Listeners>
              <Listener>
                <ListenerType>CircularTraceListener</ListenerType>
                <SourceLevel>Verbose ActivityTracing</SourceLevel>
                <FileSizeQuotaInBytes>10000000</FileSizeQuotaInBytes>
                <FileName>Microsoft\Windows Intune Exchange Connector\Logs\Connector.svclog</FileName>
                <FileQuota>30</FileQuota>
              </Listener>
            </Listeners>
          </Value>
    </TraceSourceLine>



### <a name="next-steps"></a>Étapes suivantes
Si ces informations de dépannage n’ont pas permis de vous aider, contactez le support Microsoft comme décrit dans [Comment obtenir un support technique pour Microsoft Intune](how-to-get-support-for-microsoft-intune.md).

