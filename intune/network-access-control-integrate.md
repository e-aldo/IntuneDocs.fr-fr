---
title: "Intégration du contrôle d’accès réseau avec Intune"
titleSuffix: Intune on Azure
description: "Intégration du contrôle d’accès réseau avec Intune"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: aa7ecff7-8579-4009-8fd6-e17074df67de
ms.reviewer: davidra
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6037ec4638b487c0bae8fcecf2d9bd010e3bc59a
ms.sourcegitcommit: fd2e8f6f8761fdd65b49f6e4223c2d4a013dd6d9
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/03/2017
---
# <a name="network-access-control-nac-integration-with-intune"></a>Intégration du contrôle d’accès réseau avec Intune

Intune s’intègre avec les partenaires de contrôle d’accès réseau pour aider les organisations à sécuriser les données d’entreprise quand des appareils tentent d’accéder à des ressources locales.

## <a name="how-do-intune-and-nac-solutions-help-protect-your-organization-resources"></a>Comment les solutions de contrôle d’accès réseau et Intune aident-ils à protéger les ressources de votre organisation ?

Les solutions de contrôle d’accès réseau sont chargées de vérifier l’état de conformité et d’inscription de l’appareil auprès d’Intune afin de prendre des décisions en matière de contrôle d’accès. Si l’appareil n’est pas inscrit, ou est inscrit mais non conforme aux stratégies de conformité Intune, il doit être redirigé vers Intune pour l’inscription et/ou pour une vérification de conformité d’appareil.

### <a name="example"></a>Exemple

Si l’appareil est inscrit et conforme avec Intune, la solution de contrôle d’accès réseau doit autoriser l’accès aux ressources d’entreprise à l’appareil. Par exemple, l’accès peut être accordé ou refusé aux utilisateurs quand ils tentent d’accéder aux ressources d’entreprise par Wi-Fi ou VPN.

## <a name="nac-and-conditional-access"></a>Contrôle d’accès réseau et accès conditionnel

Le contrôle d’accès réseau fonctionne avec l’accès conditionnel pour fournir des décisions en matière de contrôle d’accès.

- Pour plus d’informations, consultez les [utilisations courantes de l’accès conditionnel avec Intune](conditional-access-intune-common-ways-use.md).

## <a name="how-the-nac-integration-works"></a>Fonctionnement de l’intégration du contrôle d’accès réseau

Voici une vue d’ensemble du fonctionnement de l’intégration du contrôle d’accès réseau en cas d’intégration à Intune. Les trois premières étapes expliquent le processus d’intégration initiale. Une fois la solution de contrôle d’accès réseau intégrée à Intune, les étapes 4 à 9 décrivent l’opération continue.

![Fonctionnement du contrôle d’accès réseau avec Intune](./media/ca-intune-common-ways-2.png)

1.  Inscrivez la solution du partenaire de contrôle d’accès réseau auprès d’Azure Active Directory (AAD) et accordez des autorisations déléguées à l’API de contrôle d’accès réseau Intune.

2.  Configurez la solution du partenaire de contrôle d’accès réseau avec les paramètres appropriés, notamment l’URL de découverte Intune.

3.  Configurez la solution du partenaire de contrôle d’accès réseau pour l’authentification par certificat.

4.  L’utilisateur se connecte au point d’accès Wi-Fi d’entreprise ou effectue une demande de connexion VPN.

5.  La solution du partenaire de contrôle d’accès réseau transfère les informations de l’appareil à Intune et demande à Intune quel est l’état d’inscription et de conformité de l’appareil.

6.  Si l’appareil n’est pas conforme ou pas inscrit, la solution du partenaire de contrôle d’accès réseau demande à l’utilisateur d’inscrire l’appareil ou de corriger sa conformité.

7.  L’appareil tente de revérifier sa conformité et/ou l’état d’inscription.

8.  Une fois l’appareil inscrit et conforme, la solution du partenaire de contrôle d’accès réseau obtient l’état auprès d’Intune.

9.  La connexion est établie, ce qui permet à l’appareil d’accéder aux ressources d’entreprise.

## <a name="next-steps"></a>Étapes suivantes

-   [Intégrer Cisco ISE avec Intune](http://www.cisco.com/c/en/us/td/docs/security/ise/2-1/admin_guide/b_ise_admin_guide_21/b_ise_admin_guide_20_chapter_01000.html)

-   [Intégrer Citrix NetScaler avec Intune](https://docs.citrix.com/netscaler-gateway/11-1/microsoft-intune-integration/configuring-network-access-control-device-check-for-netscaler-gateway-virtual-server-for-single-factor-authentication-deployment.html)

-   [Intégrer HP Aruba Clear passe avec Intune](https://support.arubanetworks.com/Documentation/tabid/77/DMXModule/512/Command/Core_Download/Default.aspx?EntryId=23757)
