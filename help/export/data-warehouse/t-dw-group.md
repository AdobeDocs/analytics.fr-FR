---
description: Description de la procédure par laquelle les administrateurs peuvent activer l’accès aux rapports de Data Warehouse pour un groupe d’utilisateurs.
title: Ajouter un groupe d’utilisateurs dans Data Warehouse
topic: Data warehouse
uuid: d89294db-caa3-4044-b70d-65b512b0dc1c
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Ajouter un groupe d’utilisateurs dans Data Warehouse

Description de la procédure par laquelle les administrateurs peuvent activer l’accès aux rapports de Data Warehouse pour un groupe d’utilisateurs.

1. Cliquez sur **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL User Management]**.
1. Cliquez sur **[!UICONTROL Edit Groups]**.
1. Cliquez sur **[!UICONTROL Add New User Group]**.
1. In the **[!UICONTROL Define User Group]** section, type a name in the Group Name field. Indiquez les informations suivantes sur le groupe :

   Par exemple : `Data Warehouse Access`.
1. Entrez une description dans le **[!UICONTROL Group Description]** champ.
1. In the **[!UICONTROL Report Suite Access]** section, select the report suites that you want group members to be able to access.
1. Sous [!UICONTROL Tools], activez **[!UICONTROL All Tools]**.

   Vous pouvez également cliquer sur **[!UICONTROL Customize]**, puis activer **[!UICONTROL Custom Data Warehouse Report]**.

1. Sous [!UICONTROL Assign User Logins], ajoutez les identifications utilisateur souhaitées.
1. Cliquez sur **[!UICONTROL Save Group]**.

   La prochaine fois que les utilisateurs ajoutés à ce groupe se connecteront, l’option Data Warehouse sera ajoutée au menu de [!UICONTROL Reports & Analytics].

   >[!NOTE]
   >
   >En cas de conflit d’autorisations (dans le cas d’un utilisateur affecté à deux groupes, par exemple, l’un d’eux refuse l’accès à une certaine fonctionnalité, tandis que l’autre lui accorde), le système limite cette autorisation. Il se peut que les utilisateurs appartenant à des groupes qui refusent l’accès à Data Warehouse doivent être supprimés de ces groupes.

>[!MORELIKETHIS]
>
>* [Groupes](/help/admin/user-management2/c-user-groups/groups.md)

