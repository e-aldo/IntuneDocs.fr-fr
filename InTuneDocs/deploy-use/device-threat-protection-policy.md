---
title: "Activer une règle de protection des appareils | Microsoft Docs"
description: "Activer une règle de protection de l’appareil contre les menaces mobiles dans la stratégie de conformité."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c951692d-6538-46c0-a9f0-d607ded189ae
ms.reviewer: sandera
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 9f05e516723976dcf6862475dbb78f9dce2913be
ms.openlocfilehash: 08edca426901eda3017bf17dda3b330dd186ce58


---

# <a name="enable-device-threat-protection-rule-in-the-compliance-policy"></a>Activer une règle de protection de l’appareil contre les menaces dans la stratégie de conformité

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Intune avec protection contre les menaces mobiles Lookout vous permet de détecter les menaces sur les appareils mobiles et d’évaluer les risques sur ces appareils. Vous pouvez créer une règle de stratégie de conformité qui évalue le risque afin de déterminer si l’appareil est conforme. Vous pouvez ensuite utiliser la stratégie d’accès conditionnel pour autoriser ou bloquer l’accès à des services basés sur la conformité de l’appareil.

Configuration requise pour la stratégie de conformité avec protection contre les menaces mobiles sur les appareils Lookout :

- [Configurer l'abonnement pour la protection contre les menaces sur les appareils Lookout](set-up-your-subscription-with-lookout-mtp.md)
- [Activer la connexion à Lookout dans Intune](enable-lookout-mtp-connection-in-intune.md)
- [Configurer l’application Lookout for Work](configure-and-deploy-lookout-for-work-apps.md)

Dans le cadre de la configuration du service Lookout de protection des appareils contre les menaces, dans la [console Lookout](https://aad.lookout.com), vous avez créé une stratégie qui classifie les diverses menaces selon leur niveau (élevé, moyen et faible). Dans la stratégie de conformité Intune, vous définissez le niveau de menace maximal autorisé.

1. Dans la [console d'administration Intune](https://manage.microsoft.com), accédez à la page **Stratégies de conformité**. Vous pouvez utiliser une stratégie de conformité existante ou en créer une. Accédez à **Intégrité des appareils** et activez **Protection contre les menaces sur les appareils**.
  ![capture d’écran montrant la configuration de la règle de protection de l’appareil contre les menaces dans ](../media/mtp/mtp-compliance-policy-rule.png)

2. Sélectionnez le **Niveau de menace maximal autorisé** :
  * **Aucun (sécurisé)** : c’est le niveau de sécurité le plus haut.  L'appareil ne peut pas avoir de menace présente et accéder aux ressources de l’entreprise.  Si des menaces sont détectées, l’appareil est évalué comme non conforme.  
  * **Faible** : l’appareil est conforme uniquement si les menaces détectées sont de niveau faible. La présence de menaces de niveau supérieur rend l’appareil non conforme.
  * **Moyen** : l’appareil est conforme si les menaces détectées sont de niveau faible ou moyen. La présence de menaces de niveau élevé rend l’appareil non conforme.
  * **Élevé** : cette option est la moins sécurisée. Cela autorise tous les niveaux de menace et utilise la protection contre les menaces mobiles Lookout uniquement à des fins de création de rapports.

![capture d’écran montrant l’option de niveau de menace pour configurer la règle de protection de l’appareil contre les menaces](../media/mtp/mtp-compliance-policy-setting.png)

Si vous créez des stratégies d’accès conditionnel pour Office 365 et d’autres services, l’évaluation de la conformité est effectuée, ce qui signifie que l’accès à ces services est bloqué pour les appareils non conformes tant que la menace n’est pas résolue.

## <a name="monitor-device-threats"></a>Surveillance des menaces sur les appareils
Pour voir l’état de conformité d’un appareil, ouvrez la [console d'administration Intune](https://manage.microsoft.com) et consultez **Tous les appareils**.

![capture d’écran de la page Appareils dans la console Administrateur Intune montrant l’état de conformité d’un appareil](../media/mtp/mtp-device-status-intune-console.png)

## <a name="next-steps"></a>Étapes suivantes
* Créer la stratégie d’accès conditionnel
  * [Exchange Online](restrict-access-to-exchange-online-with-microsoft-intune.md)
  * [Exchange sur site](restrict-access-to-exchange-onpremises-with-microsoft-intune.md)
  * [SharePoint Online](restrict-access-to-sharepoint-online-with-microsoft-intune.md)
  * [Skype Entreprise Online](restrict-access-to-skype-for-business-online-with-microsoft-intune.md)
  * [Dynamics CRM](restrict-access-to-dynamics-crm-online-with-microsoft-intune.md)



<!--HONumber=Jan17_HO4-->


