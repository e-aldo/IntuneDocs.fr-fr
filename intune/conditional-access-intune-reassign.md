---
title: "Migrez les stratégies d’accès conditionnel à partir du portail classique Intune vers le nouveau portail Azure."
titleSuffix: Intune on Azure
description: "Migrez les stratégies d’accès conditionnel à partir du portail classique Intune vers le nouveau portail Azure."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 301159ad-5f7e-4fcc-86c7-f72a71701ff4
ms.reviewer: chrisgree
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 2450a878424d8c992a43e8028ba59b7136e1d530
ms.sourcegitcommit: fd5b7aa26446d2fa92c21638cb29371e43fe169f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/06/2017
---
# <a name="reassign-conditional-access-policies-from-intune-classic-portal-to-the-new-azure-portal"></a>Réaffecter les stratégies d’accès conditionnel à partir du portail classique Intune vers le nouveau portail Azure

Avec le nouveau portail Azure, l’accès conditionnel prend en charge plusieurs stratégies par application ainsi que davantage de possibilités de personnalisation.

## <a name="before-you-begin"></a>Avant de commencer

Si vous êtes prêt à passer au nouveau portail Azure, vous pouvez suivre les étapes ci-dessous pour réaffecter les stratégies d’accès conditionnel précédemment créées dans le portail classique Intune :

- Regroupez les stratégies d’accès conditionnel déjà créées dans le portail classique Intune afin de savoir quels paramètres vous devez réaffecter ultérieurement.

- Suivez les étapes décrites dans cette rubrique pour recréer ces stratégies dans le nouveau portail Azure.

- Désactivez les stratégies conditionnelles dans la console classique Intune une fois que vous avez vérifié que les nouvelles stratégies fonctionnent comme prévu dans le nouveau portail Azure.
<br /><br />
    - **Avant de désactiver** les stratégies d’accès conditionnel dans le portail classique Intune, planifiez le déplacement des utilisateurs vers la nouvelle stratégie. Il existe deux approches :
<br /><br />
        - **Utiliser le même groupe d’inclusions pour appliquer les stratégies créées dans le nouveau portail Azure et créer un groupe d’exemptions à utiliser avec les stratégies appliquées par le portail classique Intune**.
            - Déplacez progressivement certains utilisateurs dans le groupe d’exemptions indiqué dans le portail classique.  Cela empêche l’application des stratégies ciblées par le portail classique Intune. Les stratégies créées et ciblées vers le même groupe d’utilisateurs dans le nouveau portail Azure sont appliquées en plus de celles appliquées dans le portail classique Intune. 
<br /><br />
        - **Créer un groupe pour cibler les stratégies d’accès conditionnel dans le nouveau portail Azure**. Si vous choisissez cette approche, vous devez effectuer les opérations suivantes :
            - Supprimez progressivement des utilisateurs des groupes de sécurité qui sont la cible des stratégies d’accès conditionnel dans le portail classique Intune.
            - Une fois que vous avez confirmé que la nouvelle stratégie fonctionne pour ces utilisateurs, vous pouvez désactiver la stratégie dans le portail classique Intune. 
<br /><br />
- Si vous avez des paramètres de stratégie d’accès conditionnel configurés pour utiliser EAS (Exchange Active Sync) dans le portail classique Intune, consultez les [instructions de cette rubrique](#to-reassign-intune-device-based-conditional-access-policies-for-eas-clients) pour **réaffecter les paramètres de stratégie d’accès conditionnel EAS dans le nouveau portail Azure**.

### <a name="to-verify-your-device-based-conditional-access-policies-in-the-intune-classic-portal"></a>Pour vérifier vos stratégies d’accès conditionnel basé sur l’appareil dans le portail classique Intune

1.  Accédez au [portail classique Intune](https://manage.microsoft.com) et connectez-vous à l’aide de vos informations d’identification.

2.  Choisissez **Stratégie** dans le menu de gauche.

3.  Choisissez **Accès conditionnel**, puis sélectionnez le service cloud Microsoft (Exchange Online, SharePoint Online, etc.) pour lequel vous avez créé une stratégie d’accès conditionnel.

4.  Notez les paramètres d’accès conditionnel et utilisez ces notes comme référence pour créer les mêmes stratégies d’accès conditionnel dans le nouveau portail Azure.

### <a name="app-and-device-based-conditional-access-policies-working-together"></a>Utilisation conjointe de stratégies d’accès conditionnel basé sur l’application et sur l’appareil

Le panneau **Intune App Protection** dans le nouveau portail Azure permet aux administrateurs de définir des règles conditionnelles basées sur l’application afin que seules les applications qui prennent en charge les stratégies de protection des applications Intune soient autorisées à accéder aux ressources d’entreprise. Vous pouvez choisir de chevaucher ces stratégies d’accès conditionnel basé sur l’application avec des stratégies d’accès conditionnel basé sur l’appareil. Vous pouvez ensuite combiner les stratégies conditionnelles basées sur l’application et l’appareil (AND logique) ou fournir une option (OR logique). Si vos exigences de stratégie d’accès conditionnel sont :

- Exiger un appareil conforme **ET** utiliser l’application approuvée.
    - Vous devez définir votre stratégie d’accès conditionnel à l’aide du [panneau d’accès conditionnel Azure AD](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) et du [panneau Intune App Protection](https://portal.azure.com/#blade/Microsoft_Intune/SummaryBlade/0).
<br /><br />
- Exiger un appareil conforme **OU** utiliser l’application approuvée.
    - Vous devez définir votre stratégie d’accès conditionnel à l’aide du [portail classique Intune](https://manage.microsoft.com) et du [panneau Intune App Protection](https://portal.azure.com/#blade/Microsoft_Intune/SummaryBlade/0).

> [!TIP] 
> Cette rubrique fournit des captures d’écran comparant l’expérience de l’utilisateur dans le portail classique Intune et le nouveau portail Azure.

## <a name="to-re-assign-intune-device-based-conditional-access-policies"></a>Pour réaffecter des stratégies d’accès conditionnel basé sur l’appareil Intune

1. Accédez à [Accès conditionnel dans le nouveau portail Azure](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) et connectez-vous avec vos informations d’identification.

2. Choisissez **Nouvelle stratégie**.

3. Spécifiez un nom pour la stratégie.

4. Choisissez **Utilisateurs et groupes** sous la section **Affectations** pour cibler la nouvelle stratégie d’accès conditionnel.
    
    ![Comparaison de l’interface utilisateur des groupes d’utilisateurs entre le portail classique Intune et le nouveau portail Azure](./media/reassign-ca-1.png)

    > [!IMPORTANT] 
    > Si tous les utilisateurs sont sélectionnés dans le portail classique Intune, incluez Tous les utilisateurs. La même règle s’applique pour les groupes : si des groupes sont sélectionnés, vous devez choisir **Sélectionner des utilisateurs et des groupes** pour inclure ces groupes. Si vous avez également choisi l’option **Groupes exempts** dans le portail classique Intune, vous devez exclure ces groupes sélectionnés dans le nouveau portail Azure.

5. Après avoir choisi votre groupe, cliquez sur **Sélectionner**, puis sur **Terminé**.

6. Choisissez **Applications cloud** sous la section **Affectations**.

7. Dans le panneau **Applications cloud**, choisissez **Sélectionner les applications**.

8. Choisissez l’application à laquelle vous voulez appliquer la nouvelle stratégie d’accès conditionnel et cliquez sur **Sélectionner**.

9. Cliquez sur **Terminé**.

    ![Comparaison de l’interface utilisateur des applications cloud entre le portail classique Intune et le nouveau portail Azure](./media/reassign-ca-3.png)

    > [!TIP] 
    > Si vous avez plusieurs applications avec la même stratégie, vous pouvez envisager de les regrouper dans une seule stratégie dans le nouveau portail Azure.

10. Choisissez **Conditions** sous la section **Affectations**.

11. Dans le panneau **Conditions**, choisissez **Plateformes d’appareils**, puis les plateformes d’appareils applicables.

12. Une fois les plateformes d’appareils choisies, cliquez sur **Terminé** à deux reprises.

    ![Comparaison de l’interface utilisateur des plateformes d’appareils entre le portail classique Intune et le nouveau portail Azure](./media/reassign-ca-4.png)

    > [!TIP] 
    > Si vous avez choisi des plateformes individuelles dans le portail classique Intune, choisissez les plateformes individuelles dans le nouveau portail Azure.

    > [!NOTE] 
    > Vous pouvez spécifier les options de jonction de domaine ou de conformité pour Windows ultérieurement.

13. Choisissez **Conditions** sous la section **Affectations**.

14. Dans le panneau **Conditions**, choisissez **Applications clientes**, puis l’application cliente applicable.

15. Une fois l’application cliente choisie, cliquez sur **Terminé** à deux reprises.

    ![Comparaison de l’interface utilisateur des applications clientes entre le portail classique Intune et le nouveau portail Azure](./media/reassign-ca-6.png)

16. Si vous avez choisi les paramètres du navigateur dans le portail classique Intune, sélectionnez à la fois **Navigateur** et **Applications mobiles et clients de bureau** dans le nouveau portail Azure. Si vous n’avez pas choisi les paramètres du navigateur dans le portail classique Intune, choisissez uniquement **Applications mobiles et clients de bureau**. 

17. Choisissez **Accorder** sous la section **Contrôles d’accès**.

18. Choisissez **Exiger que l’appareil soit marqué comme conforme** sous **Accorder les contrôles d’accès**, puis cliquez sur **Sélectionner**.

19. Si vous avez une stratégie pour exiger des appareils Windows joints au domaine et que vous autorisez également des appareils Windows conformes et inscrits auprès d’Intune, choisissez **Exiger un appareil joint au domaine** et **Exiger que l’appareil soit marqué comme conforme** avec **Demander un des contrôles sélectionnés**.

20. Si vous n’autorisez pas les appareils Windows conformes et inscrits auprès d’Intune, exemptez la stratégie Windows de la stratégie actuelle, puis créez une stratégie distincte avec **Windows** comme valeur de **Plateformes d’appareils**, incluez les autres conditions comme définies ci-dessus et choisissez **Exiger un appareil joint au domaine** sous **Accorder les contrôles d’accès**.

21. Activez la bascule **Activer la stratégie** dans le panneau de la stratégie d’accès conditionnel **Nouveau**, puis cliquez sur **Créer**.

    ![Comparaison de l’interface utilisateur de l’activation de la stratégie d’accès conditionnel entre le portail classique Intune et le nouveau portail Azure](./media/reassign-ca-11.png)

## <a name="to-reassign-intune-device-based-conditional-access-policies-for-eas-clients"></a>Pour réaffecter des stratégies d’accès conditionnel basé sur l’appareil Intune pour les clients EAS

Si vous avez configuré les paramètres EAS (Exchange Active Sync) dans le cadre d’une stratégie Exchange Online dans le portail classique Intune, vous devez créer une deuxième stratégie d’accès conditionnel dans le nouveau portail Azure.

1. Accédez à [Accès conditionnel dans le nouveau portail Azure](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) et connectez-vous avec vos informations d’identification.

2. Choisissez **Nouvelle stratégie**.

3. Spécifiez un nom pour la stratégie.

4. Choisissez **Utilisateurs et groupes** sous la section **Affectations** pour cibler la nouvelle stratégie d’accès conditionnel.

    ![Comparaison de l’interface utilisateur des groupes d’utilisateurs entre le portail classique Intune et le nouveau portail Azure](./media/reassign-ca-12.png)

    > [!IMPORTANT] 
    > Si tous les utilisateurs sont sélectionnés dans le portail classique Intune, incluez Tous les utilisateurs. La même règle s’applique pour les groupes : si des groupes sont sélectionnés, vous devez choisir **Sélectionner des utilisateurs et des groupes** pour inclure ces groupes. Si vous avez également choisi l’option **Groupes exempts** dans le portail classique Intune, vous devez exclure ces groupes sélectionnés dans le nouveau portail Azure.

5. Après avoir choisi votre groupe, cliquez sur **Sélectionner**, puis sur **Terminé**.

6. Choisissez **Applications cloud** sous la section **Affectations**.

7. Dans le panneau **Applications cloud**, cliquez sur **Applications sélectionnées**, choisissez **Exchange Online**, cliquez sur **Sélectionner**, puis sur **Terminé**.

    ![Comparaison de l’interface utilisateur des applications cloud entre le portail classique Intune et le nouveau portail Azure](./media/reassign-ca-14.png)

    > [!IMPORTANT] 
    > Les stratégies d’accès conditionnel pour les clients EAS ne peuvent inclure aucune autre application cloud.

8. Dans le panneau **Conditions**, choisissez **Applications clientes**, puis l’application cliente applicable. Si vous avez choisi de bloquer les clients qui ne sont pas pris en charge par Intune, utilisez l’option **Appliquer la stratégie uniquement aux plateformes prises en charge**.

    ![Comparaison de l’interface utilisateur des applications clientes entre le portail classique Intune et le nouveau portail Azure](./media/reassign-ca-15.png)

9. Une fois l’application cliente choisie, cliquez sur **Terminé** à deux reprises.

10. Choisissez **Accorder** sous la section **Contrôles d’accès**.

11. Choisissez **Exiger que l’appareil soit marqué comme conforme** sous **Accorder les contrôles d’accès**, puis cliquez sur **Sélectionner**.

    ![Comparaison de l’interface utilisateur de l’accord de l’accès entre le portail classique Intune et le nouveau portail Azure](./media/reassign-ca-16.png)

12. Activez la bascule **Activer la stratégie** dans le panneau de la stratégie d’accès conditionnel **Nouveau**, puis cliquez sur **Créer**.

    ![Comparaison de l’interface utilisateur de l’activation de la stratégie d’accès conditionnel entre le portail classique Intune et le nouveau portail Azure](./media/reassign-ca-17.png)

## <a name="disable-conditional-access-policies-in-the-intune-classic-portal"></a>Désactiver les stratégies d’accès conditionnel dans le portail classique Intune
### <a name="before-you-start"></a>Avant de commencer

Une fois que vous avez réaffecté vos stratégies d’accès conditionnel dans le nouveau portail Azure, il est important de désactiver progressivement les stratégies d’accès conditionnel créées précédemment dans le portail classique Intune. Vous devrez peut-être aussi utiliser le même groupe de sécurité pour appliquer les stratégies d’accès conditionnel créées dans le nouveau portail Azure

- Consultez la section [Avant de commencer](#before-you-begin) au début de cette rubrique avant de désactiver vos stratégies d’accès conditionnel dans le portail classique Intune.

### <a name="to-disable-the-conditional-access-policies"></a>Pour désactiver les stratégies d’accès conditionnel

1.  Accédez au [portail classique Intune](https://manage.microsoft.com) et connectez-vous à l’aide de vos informations d’identification.

2.  Choisissez **Stratégie** dans le menu de gauche.

3.  Choisissez **Accès conditionnel**, puis sélectionnez le service cloud Microsoft (Exchange Online, SharePoint Online, etc.) pour lequel vous avez créé une stratégie d’accès conditionnel.

4.  Décochez l’option **Activer la stratégie d’accès conditionnel**, puis cliquez sur **Enregistrer**.

    ![Désactiver les stratégies d’accès conditionnel dans le portail classique Intune](./media/reassign-ca-18.png)

## <a name="see-also"></a>Voir aussi

- [Utilisations courantes de l’accès conditionnel avec Intune](conditional-access-intune-common-ways-use.md)
- [Accès conditionnel basé sur l’application avec Intune](app-based-conditional-access-intune.md)
- [Accès conditionnel dans Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal-get-started)