## <a name="enable-windows-10-automatic-enrollment"></a>Activer l’inscription automatique Windows 10

L’inscription automatique permet aux utilisateurs d’inscrire des PC Windows 10 d’entreprise ou personnels et des appareils Windows 10 Mobile dans Intune en ajoutant un compte professionnel ou scolaire, puis en validant leur gestion. C’est aussi simple que cela. En arrière-plan, l’appareil de l’utilisateur s’inscrit et rejoint Azure Active Directory. Une fois inscrit, l’appareil est géré par Intune.

**Conditions préalables**
- Abonnement Premium à Azure Active Directory ([abonnement d’évaluation](http://go.microsoft.com/fwlink/?LinkID=816845))
- Abonnement Microsoft Intune


### <a name="configure-automatic-mdm-enrollment"></a>Configurer l’inscription automatique de la gestion des appareils mobiles

1. Connectez-vous au [Portail de gestion Azure](https://portal.azure.com) (https://manage.WindowsAzure.com), puis sélectionnez **Azure Active Directory**.

  ![Capture d’écran du portail Azure](../media/auto-enroll-azure-main.png)

2. Sélectionnez **Mobilité (gestion des données de référence et gestion des applications mobiles)**.

  ![Capture d’écran du portail Azure](../media/auto-enroll-mdm.png)

3. Sélectionnez **Microsoft Intune**.

  ![Capture d’écran du portail Azure](../media/auto-enroll-intune.png)

4. Configurez les utilisateurs qui s’inscriront automatiquement.

  ![Capture d’écran du portail Azure](../media/auto-enroll-scope.png)

  Utilisez les valeurs par défaut pour les URL suivantes :
  - **Inscription MDM**
  - **Conditions d’utilisation de MDM**
  - **Conformité MDM**

5. Spécifiez les appareils des utilisateurs qui doivent être gérés par Microsoft Intune. Les appareils Windows 10 de ces utilisateurs sont automatiquement inscrits à la gestion avec Microsoft Intune.

  - **Tous**
  - **Groupes**
  - **Aucun**

6. Sélectionnez **Enregistrer**.
