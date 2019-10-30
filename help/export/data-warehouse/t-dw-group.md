---
description: Description de la procédure par laquelle les administrateurs peuvent activer l’accès aux rapports de Data Warehouse pour un groupe d’utilisateurs.
seo-description: Description de la procédure par laquelle les administrateurs peuvent activer l’accès aux rapports de Data Warehouse pour un groupe d’utilisateurs.
seo-title: Ajouter un groupe d’utilisateurs de l’Data Warehouse
solution: Analytics
title: Ajouter un groupe d’utilisateurs de l’Data Warehouse
topic: Data Warehouse
uuid: d89294db-caa3-4044-b70d-65b512b0dc1c
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Ajouter un groupe d’utilisateurs de l’Data Warehouse

Description de la procédure par laquelle les administrateurs peuvent activer l’accès aux rapports de Data Warehouse pour un groupe d’utilisateurs.

1. Click **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL User Management]**.
1. Click **[!UICONTROL Edit Groups]**.
1. Click **[!UICONTROL Add New User Group]**.
1. In the **[!UICONTROL Define User Group]** section, type a name in the Group Name field. Indiquez les informations suivantes sur le groupe : 

   Par exemple : `Data Warehouse Access`.
1. Type a description in the **[!UICONTROL Group Description]** field.
1. In the **[!UICONTROL Report Suite Access]** section, select the report suites that you want group members to be able to access.
1. Sous [!UICONTROL Outils]**, activez[!UICONTROL Tous les outils]**.

   Vous pouvez également cliquer sur **[!UICONTROL Personnaliser]**, puis activer **[!UICONTROL Rapport Data Warehouse personnalisé]**.

1. Ajoutez les identifiants de connexion d’utilisateur souhaités sous [!UICONTROL Affecter les identifications utilisateur.]
1. Click **[!UICONTROL Save Group]**.

   La prochaine fois que les utilisateurs ajoutés à ce groupe se connecteront, l’option Data Warehouse sera ajoutée au menu des [!UICONTROL Reports &amp; Analytics].

   >[!NOTE]
   >
   >En cas de conflit d’autorisations (par exemple, un utilisateur affecté à deux groupes, dont l’un refuse l’accès à une fonctionnalité et l’autre lui accorde), le système limite les autorisations. Il se peut que les utilisateurs appartenant à des groupes qui refusent l’accès à Data Warehouse doivent être supprimés de ces groupes.

>[!MORE_LIKE_THIS]
>
>* [Groupes](/help/admin/user-management2/c-user-groups/groups.md)

