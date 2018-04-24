---
title: Activer une règle de protection d’appareil
description: Activer une règle de protection de l’appareil contre les menaces mobiles dans la stratégie de conformité.
keywords: ''
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 03/21/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: c951692d-6538-46c0-a9f0-d607ded189ae
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: sandera
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: b39f7cac8c09813eb9db94e761ec6fa6ab53c7a0
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2018
---
# <a name="create-lookout-device-compliance-policy-in-intune"></a>Créer une stratégie de conformité des appareils Lookout dans Intune

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Intune avec Lookout Mobile Threat Defense vous permet de détecter les menaces sur les appareils mobiles et d’évaluer les risques sur ces appareils. Vous pouvez créer une règle de stratégie de conformité qui évalue le risque afin de déterminer si l’appareil est conforme. Vous pouvez ensuite utiliser la stratégie d’accès conditionnel pour autoriser ou bloquer l’accès à des services basés sur la conformité de l’appareil.

Configuration requise pour la stratégie de conformité avec Lookout Mobile Threat Defense :

- [Configuration de l’abonnement Lookout Mobile Threat Defense](setup-your-lookout-mtd-subscription.md)
- [Activer la connexion à Lookout dans Intune](enable-lookout-mtd-connection.md)
- [Configurer et déployer l’application Lookout for work](configure-deploy-lookout-for-work-app.md)

Dans le cadre de la configuration de Lookout Mobile Threat Defense, dans la [console Lookout](https://aad.lookout.com), vous avez créé une stratégie qui classe les diverses menaces selon les niveaux élevé, moyen et faible. Dans la stratégie de conformité Intune, vous définissez le niveau de menace maximal autorisé.

1. Dans la [console d'administration Intune](https://manage.microsoft.com), accédez à la page **Stratégies de conformité**. Vous pouvez utiliser une stratégie de conformité existante ou en créer une. Accédez à **Intégrité des appareils** et activez **Protection contre les menaces sur les appareils**.
   ![capture d’écran montrant la configuration de la règle de protection de l’appareil contre les menaces dans ](../media/mtp/mtp-compliance-policy-rule.png)

2. Sélectionnez le **Niveau de menace maximal autorisé** :
   * **Aucun (sécurisé)**  : c’est le niveau de sécurité le plus haut.  L'appareil ne peut pas avoir de menace présente et accéder aux ressources de l’entreprise.  Si des menaces sont détectées, l’appareil est évalué comme non conforme.  
   * **Faible** : l’appareil est conforme uniquement si les menaces détectées sont de niveau faible. La présence de menaces de niveau supérieur rend l’appareil non conforme.
   * **Moyen** : l’appareil est conforme si les menaces détectées sont de niveau faible ou moyen. Si des menaces de niveau élevé sont détectées, l’appareil est déterminé comme non conforme.
   * **Élevé** : cette option est la moins sécurisée. Cela autorise tous les niveaux de menace et utilise la protection contre les menaces mobiles Lookout uniquement à des fins de création de rapports.

![capture d’écran montrant l’option de niveau de menace pour configurer la règle de protection de l’appareil contre les menaces](../media/mtp/mtp-compliance-policy-setting.png)

Si vous créez des stratégies d’accès conditionnel pour Office 365 ou d’autres services, l’évaluation de la conformité est effectuée et les appareils non conformes ne peuvent pas accéder à ces services tant que la menace n’est pas résolue.

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
