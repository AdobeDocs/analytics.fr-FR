---
description: Gérez des utilisateurs, des groupes et des produits Analytics dans Adobe Admin Console.
subtopic: Users and groups
title: Gestion des utilisateurs et des produits
feature: Admin Tools
exl-id: c0fbbb3a-0011-49d2-89a2-70fce11e0fb2
role: Admin
source-git-commit: 938795c7378cb1f0537ff84eddeab3feddf8d073
workflow-type: tm+mt
source-wordcount: '254'
ht-degree: 98%

---

# Gestion des utilisateurs et des produits (héritée)

Gérez des utilisateurs, des groupes et des produits Analytics dans Adobe Admin Console.

>[!IMPORTANT]
>
>La gestion des utilisateurs et des produits se fait désormais dans [Adobe Admin Console](https://helpx.adobe.com/fr/enterprise/using/admin-console.html). Pour commencer à gérer les autorisations utilisateur pour les utilisateurs d’Adobe Analytics, consultez la section [Analytics dans Adobe Admin Console](/help/admin/admin-console/home.md).

## Ressources d’aide pour les administrateurs Adobe Admin Console {#help}

| Tâche ou ressource | Description |
| --- | --- |
| Migration des identifiants d’utilisateur Analytics vers Adobe Admin Console | Adobe aide les administrateurs Analytics à migrer les identifiants d’utilisateur vers Adobe Admin Console. Cette migration s’effectuera pas vagues. Lorsque c’est votre tour de migrer les utilisateurs, Adobe avertit les administrateurs d’Analytics par un e-mail comportant des instructions. Afin de simplifier cette tâche, un outil de migration est disponible dans [Gestion des utilisateurs Analytics](https://experienceleague.adobe.com/docs/analytics/admin/user-product-management/user-management/migrate-users/c-migration-tool.html?lang=fr).<p>**Important** : le jour de la migration, les anciens groupes d’autorisations sont automatiquement copiés vers Adobe Admin Console. Vous ne pourrez plus inviter de nouveaux utilisateurs ou créer des groupes dans les Outils d’administration Analytics. Consultez les questions fréquentes et l’aide dans Migration des utilisateurs d’Analytics vers Adobe Admin Console pour plus d’informations sur la préparation de la migration et sur les fonctionnalités d’administration affectées. |
| Lancement d’Adobe Admin Console | Une fois les comptes d’utilisateurs migrés, vous pouvez gérer les utilisateurs et les produits de toutes les solutions dans Adobe Admin Console. Accédez à : `https://adminconsole.adobe.com/enterprise/`. Reportez-vous également à la section [Gestion des utilisateurs et des produits Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/administration/admin-getting-started.html?lang=fr). |
| Gestion des profils de produit, des utilisateurs et des autorisations Adobe Analytics | Reportez-vous à la section [Analytics dans Adobe Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/home.html?lang=fr). |

<!---
## User Management Descriptions {#section_7C19842A3D4249109A9399D4DF18DE75}

The following table describes elements on the [!UICONTROL Users] tab in [!UICONTROL User Management].

<table id="table_6F81D1095EB945D8995FF971B65BA52A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Element </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Number of User Logins available</span> </td> 
   <td colname="col2"> The maximum number of user accounts you can create for this company. If necessary, you can contact your Account Representative or Customer Care to increase this number at no charge. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Number of User Logins in use</span> </td> 
   <td colname="col2"> The number of user accounts currently in use for this company. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Number of User Logins Remaining</span> </td> 
   <td colname="col2"> The difference between the user account maximum and the number of existing user accounts. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Add New User</span> </td> 
   <td colname="col2"> <p>Lets you add a user account to the company. This link is available only if the Number of User Logins Remaining is greater than 0. </p> <p>See <a href="/help/admin/user-management2/c-user-management/users.md"> Users</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Download Report</span> </td> 
   <td colname="col2">Exports the contents of the <span class="wintitle"> Users</span> table to a tab-delimited file. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Login</span> </td> 
   <td colname="col2"> <p>The user name. You can click the user name to edit the user account properties. </p> <p>See <a href="/help/admin/user-management2/c-user-management/users.md"> Users</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> First Name</span> </td> 
   <td colname="col2"> The user's first (given) name. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Last Name</span> </td> 
   <td colname="col2"> The user's surname (family name). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Title</span> </td> 
   <td colname="col2"> The user's job title. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Admin</span> </td> 
   <td colname="col2"> Specifies if the user account has administrative privileges. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Last Login</span> </td> 
   <td colname="col2"> Displays a timestamp of the last login for this user account. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="wintitle"> Create Time</span> </td> 
   <td colname="col2"> Shows the date and time when the login account was created. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Expires</span> </td> 
   <td colname="col2"> Displays the account expiration account, if applicable. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Manage</span> </td> 
   <td colname="col2"> Provides links for user account management. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Edit</span> </td> 
   <td colname="col2"> <p>Edit user account settings. </p> <p>See <a href="/help/admin/user-management2/c-user-management/users.md"> Users</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Delete</span> </td> 
   <td colname="col2"> Delete the user account. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Transfer</span> </td> 
   <td colname="col2">Assign the privileges (permissions and resource access) of one user account to another. <p>See <a href="/help/admin/user-management2/c-user-management/t-transfer-user-accout-privileges.md"> Transfer user account privileges</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="wintitle"> Login as this user</span> </td> 
   <td colname="col2"> <p>Allows admins to impersonate and log in as a non-admin account. Admin accounts cannot be impersonated. </p> </td> 
  </tr> 
 </tbody> 
</table>
-->