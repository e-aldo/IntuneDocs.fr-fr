## <a name="set-up-windows-10-and-windows-10-mobile-automatic-enrollment-with-azure-active-directory-premium"></a>Configuration de l’inscription automatique Windows 10 et Windows 10 Mobile avec Azure Active Directory Premium

L’inscription automatique permet aux utilisateurs d’inscrire des PC Windows 10 d’entreprise ou personnels et des appareils Windows 10 Mobile dans Intune en ajoutant un compte professionnel ou scolaire, puis en validant leur gestion. C’est aussi simple que cela. En arrière-plan, l’appareil de l’utilisateur s’inscrit et rejoint Azure Active Directory. Une fois inscrit, l’appareil est géré par Intune.

**Conditions préalables**
- Abonnement Premium à Azure Active Directory ([abonnement d’évaluation](http://go.microsoft.com/fwlink/?LinkID=816845))
- Abonnement Microsoft Intune


### <a name="configure-automatic-mdm-enrollment"></a>Configurer l’inscription automatique de la gestion des appareils mobiles

1. Dans le [portail de gestion Azure](https://portal.azure.com) (https://manage.windowsazure.com), accédez au nœud **Active Directory** et sélectionnez votre annuaire.

2. Sélectionnez l'onglet **Applications**. **Microsoft Intune** s’affiche dans la liste d’applications.

    ![Applications Azure AD avec Microsoft Intune](../media/aad-intune-app.png)

3. Cliquez sur la flèche pour **Microsoft Intune**. Une page s’ouvre et vous permet de configurer Microsoft Intune.

4. Sélectionnez **Configurer** pour démarrer la configuration de l’inscription automatique de la gestion des appareils mobiles auprès de Microsoft Intune.

5. Utilisez les valeurs par défaut pour les URL suivantes :

  - **Inscription MDM**
  - **Conditions d’utilisation de MDM** 
  - **Conformité MDM**

6.  Spécifiez les appareils des utilisateurs qui doivent être gérés par Microsoft Intune. Les appareils Windows 10 de ces utilisateurs sont automatiquement inscrits à la gestion avec Microsoft Intune.

  - **Tous**
  - **Groupes**
  - **Aucun**

7. Choisissez **Enregistrer**.
