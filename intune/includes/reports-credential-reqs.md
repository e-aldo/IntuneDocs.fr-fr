<!-- This include is part of the Intune Data Warehouse documentation. -->

## <a name="azure-ad-and-intune-credential-requirements"></a>Exigences liées aux informations d’identification Azure AD et Intune

L’authentification et l’autorisation sont basées sur les informations d’identification Azure AD et le contrôle d’accès en fonction du rôle (RBAC). Par défaut, tous les administrateurs généraux et les administrateurs de service Intune de votre locataire ont accès à l’entrepôt de données. Pour autoriser davantage d’utilisateurs, utilisez les rôles Intune et octroyez l’accès à la **ressource Rapports**.

Exigences liées à l’accès à l’entrepôt de données Intune (notamment l’API) :

  -  Une licence Intune doit être affectée à l’utilisateur
  -  L’utilisateur doit appartenir à l’une des catégories suivantes :
      -  Administrateur général Azure AD
      -  Administrateur de service Intune
      -  Utilisateur avec accès en fonction du rôle à la ressource **Rapports**