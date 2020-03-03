---
description: Description de la procédure par laquelle les administrateurs peuvent activer l’accès aux rapports de Data Warehouse pour un groupe d’utilisateurs.
title: Ajouter un groupe d’utilisateurs dans Data Warehouse
topic: Data warehouse
uuid: d89294db-caa3-4044-b70d-65b512b0dc1c
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Ajouter un groupe d’utilisateurs dans Data Warehouse

Description de la procédure par laquelle les administrateurs peuvent activer l’accès aux rapports de Data Warehouse pour un groupe d’utilisateurs.

1. Cliquez sur **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Gestion utilisateur]**.
1. Cliquez sur **[!UICONTROL Modifier les groupes]**.
1. Cliquez sur **[!UICONTROL Ajouter un nouveau groupe d’utilisateurs]**.
1. Entrez un nom dans le champ Nom du groupe de la section **[!UICONTROL Définir un groupe d’utilisateurs]**. Indiquez les informations suivantes sur le groupe :

   Par exemple : `Data Warehouse Access`.
1. Entrez une description dans le champ **[!UICONTROL Description du groupe.]**
1. Dans la section **[!UICONTROL Accès aux suites de rapports]**, sélectionnez les suites de rapports auxquelles vous souhaitez autoriser les membres à accéder.
1. Sous [!UICONTROL Outils], activez **[!UICONTROL Tous les outils]**.

   Vous pouvez également cliquer sur **[!UICONTROL Personnaliser]**, puis activer **[!UICONTROL Rapport Data Warehouse personnalisé]**.

1. Ajoutez les identifiants de connexion d’utilisateur souhaités sous [!UICONTROL Affecter les identifications utilisateur.]
1. Cliquez sur **[!UICONTROL Enregistrer le groupe]**.

   La prochaine fois que les utilisateurs ajoutés à ce groupe se connecteront, l’option Data Warehouse sera ajoutée au menu de [!UICONTROL Reports &amp; Analytics].

   >[!NOTE]
   >
   >En cas de conflit d’autorisations (dans le cas d’un utilisateur affecté à deux groupes, par exemple, l’un d’eux refuse l’accès à une certaine fonctionnalité, tandis que l’autre lui accorde), le système limite cette autorisation. Il se peut que les utilisateurs appartenant à des groupes qui refusent l’accès à Data Warehouse doivent être supprimés de ces groupes.

>[!MORELIKETHIS]
>
>* [Groupes](/help/admin/user-management2/c-user-groups/groups.md)

