---
description: Consultez et gérez les rapports planifiés de l’ensemble de l’organisation.
title: Gestionnaire de projets planifiés
feature: Admin Tools
exl-id: 8bc8d983-f680-48fa-8483-694c87a9ae4c
source-git-commit: d4d0eeac4f1f29e4c68e80b6fa0fe987a1fb32b9
workflow-type: tm+mt
source-wordcount: '789'
ht-degree: 42%

---

# Projets planifiés

Les projets Analysis Workspace planifiés peuvent être gérés dans Adobe Analytics à l’aide de **[!UICONTROL Composants]** > **[!UICONTROL Projets planifiés]**.

Dans **[!UICONTROL Projets planifiés]**, vous pouvez modifier et supprimer les planifications de projets récurrentes.  La [liste des projets planifiés](#scheduled-project-list) affiche les éléments créés par un utilisateur spécifique. Si le compte utilisateur est désactivé dans l’application, toutes les diffusions planifiées s’arrêtent.

![Interface des projets planifiés](assets/scheduled-projects.png)

## Liste des projets planifiés

La liste Projets planifiés affiche ➊ des colonnes pour :

| Colonne | Description |
| --- | --- |
| ![SelectBox](/help/assets/icons/SelectBox.svg) | Lorsqu’un ou plusieurs projets planifiés sont sélectionnés, une barre d’actions bleue s’affiche en bas de l’interface des Projets planifiés . Pour plus de détails, consultez [Actions](#actions). |
| ![Étoile](/help/assets/icons/Star.svg) | Sélectionnez pour favoriser ![Star](/help/assets/icons/Star.svg) ou annuler la préférence ![StarOutline](/help/assets/icons/StarOutline.svg) un projet planifié. |
| **[!UICONTROL Identifiant de planning]** | Identifiant utilisé principalement à des fins de débogage. |
| **[!UICONTROL Nom]** | Nom de ce projet.<br/>Sélectionnez ![InfoOutline](/help/assets/icons/InfoOutline.svg) pour afficher plus de détails sur le projet planifié.<br/>Sélectionnez ![Plus](/help/assets/icons/More.svg) pour ouvrir un menu contextuel. À partir de ce menu, vous pouvez :<ul><li>![Supprimer](/help/assets/icons/Delete.svg) **[!UICONTROL Supprimer]** un projet planifié.</li><li>![Libellés](/help/assets/icons/Labels.svg) **[!UICONTROL Balise]** un projet planifié.</li><li>![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL Approuver]** un projet planifié.</li><li>![FileCSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL Export CSV]** : exportez un projet planifié dans un fichier CSV.</li></ul> |
| **[!UICONTROL Propriétaire]** | Personne qui a créé le projet et qui en est propriétaire. |
| **[!UICONTROL Balises]** | (facultatif) Le balisage est un moyen efficace d’organiser les projets. Tous les utilisateurs peuvent créer des balises et en appliquer une ou plusieurs à un projet. Néanmoins, vous ne pouvez afficher les balises que pour les projets que vous possédez ou qui ont été partagés avec vous. |
| **[!UICONTROL Distribué à]** | Les destinataires de ce projet planifié. |
| **[!UICONTROL Date d’expiration]** | Vous pouvez définir des dates d’expiration maximales allant jusqu’à un an pour les projets planifiés, quelle que soit la fréquence de planification. |
| **[!UICONTROL Fréquence]** | Fréquence à laquelle vous souhaitez envoyer ce projet planifié à un ou plusieurs destinataires. |
| **[!UICONTROL Heure d’exécution]** | Heure à laquelle ce projet planifié est envoyé. |
| **[!UICONTROL Nombre de requêtes]** | Nombre de requêtes concernant ce projet. |
| **[!UICONTROL Période la plus longue]** | Période la plus longue définie pour le projet planifié. Cette valeur peut être pertinente pour examiner les problèmes de performances. Voir [Gestionnaire des activités de rapport](/help/admin/admin/reporting-activity-manager/reporting-activity-overview.md) pour plus d’informations. |
| **[!UICONTROL Nombre de requêtes]** | Nombre de requêtes exécutées pour le projet planifié. Cette valeur peut être pertinente pour examiner les problèmes de performances. Voir [Gestionnaire des activités de rapport](/help/admin/admin/reporting-activity-manager/reporting-activity-overview.md) pour plus d’informations. |


Vous pouvez utiliser ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) pour configurer les colonnes à afficher.

Recherchez un projet planifié à l’aide de ![Rechercher](/help/assets/icons/Search.svg). Vous pouvez également voir si des filtres sont appliqués à partir du panneau Filtres . Pour supprimer un filtre, sélectionnez ![CrossSize75](/help/assets/icons/CrossSize75.svg). Pour supprimer tous les filtres, sélectionnez **[!UICONTROL Effacer tout]**.

Pour modifier un projet planifié, sélectionnez le titre du projet planifié. Utilisez la boîte de dialogue **[!UICONTROL Modifier le projet planifié]** pour mettre à jour les détails du planning. Voir [Envoyer des fichiers à d’autres](../analyze/analysis-workspace/curate-share/t-schedule-report.md) pour plus d’informations.

![Modifier le projet planifié](assets/edit-scheduled-project.png)

Sélectionnez **[!UICONTROL Mettre à jour]** pour mettre à jour le planning.




## Actions

Voici des actions courantes du gestionnaire de projets planifiés : Vous pouvez sélectionner des actions dans le menu contextuel ou dans la barre d’actions bleue lors de la sélection d’un ou de plusieurs projets planifiés.

| Icône | Action | Description |
|:---:|---|---|
| ![Fermer](/help/assets/icons/Close.svg) | **[!UICONTROL *x *sélectionné]** | Sélectionnez pour désélectionner les projets planifiés sélectionnés. |
| ![Supprimer](/help/assets/icons/Delete.svg) | **[!UICONTROL Supprimer]** | Supprimer les projets planifiés sélectionnés pour le projet ; les projets ne sont pas supprimés. |
| ![Étiquettes](/help/assets/icons/Labels.svg) | **[!UICONTROL Étiquette]** | Balisez les projets planifiés sélectionnés. Dans les **[!UICONTROL Projets planifiés de balises]** sélectionnez des balises et sélectionnez **[!UICONTROL Enregistrer]** pour enregistrer. |
| ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | **[!UICONTROL Approuver]** | Valider les projets planifiés sélectionnés. |
| ![Fichier CSV](/help/assets/icons/FileCSV.svg) | **[!UICONTROL Exporter dans un fichier CSV]** | Exportez les projets planifiés sélectionnés vers un fichier nommé `Export Scheduled Projects List.csv`. |


## Filtre

Vous pouvez filtrer les projets planifiés [liste des projets planifiés](#scheduled-project-list) à l’aide du panneau de filtrage ➌. Pour afficher ou masquer le panneau Filtrer, utilisez ![Filtrer](/help/assets/icons/Filter.svg).

Le panneau Filtrer se compose des sections suivantes.

### Balises

| Balises | Description |
|---|---|
| ![Étiquettes](/help/components/assets/scheduledprojects-filter-tags.png){width="300"} | La section **[!UICONTROL Balises]** permet de filtrer par balise. <ul><li>Vous utilisez ![Rechercher](/help/assets/icons/Search.svg) **[!UICONTROL Rechercher des balises]** pour rechercher les balises que vous souhaitez utiliser pour filtrer.</li><li>Vous pouvez sélectionnez plusieurs balises. Les balises disponibles dépendent des sélections effectuées dans d’autres sections du panneau Filtrer.</li><li>Les chiffres indiquent ce qui suit :<ul><li>7︎⃣ : nombre de projets planifiés associés à la balise spécifique.</li></ul></li></ul> |


### Propriétaires

| Propriétaire | Description |
|---|---|
| ![Propriétaires](/help/components/assets/scheduledprojects-filter-owners.png){width="300"} | La section **[!UICONTROL Propriétaire]** vous permet de filtrer les propriétaires. <ul><li>Utilisez ![Rechercher](/help/assets/icons/Search.svg) *Rechercher des propriétaires* pour rechercher les propriétaires que vous souhaitez utiliser pour filtrer.</li><li>Vous pouvez sélectionner plusieurs propriétaires. Les propriétaires disponibles dépendent des sélections effectuées dans d’autres sections du panneau Filtrer.</li><li>Les chiffres indiquent ce qui suit :<ul><li>4︎⃣ : nombre de projets planifiés associés au propriétaire spécifique.</li></ul></li></ul> |


### Autres filtres

| Autres filtres | Description |
|---|---|
| ![Autres filtres](/help/components/assets/scheduledprojects-filter-otherfilters.png){width="300"} | La section **[!UICONTROL Autres filtres]** vous permet de filtrer selon un autre filtre prédéfini.<ul><li>Vous pouvez sélectionner l’une ou plusieurs des options suivantes :<ul><li> **[!UICONTROL Expiré]** : filtrez les projets planifiés ayant expiré.</li><li>**[!UICONTROL Échec]** : filtrez les projets planifiés pour lesquels la planification a échoué.</li></ul>Ce que vous pouvez sélectionner dépend de votre rôle et de vos autorisations.</li><li>Vous pouvez sélectionner plusieurs filtres. Les autres filtres disponibles dépendent des sélections effectuées dans d’autres sections du panneau Filtrer.</li><li>Les chiffres indiquent ce qui suit :<ul><li>4︎⃣ : nombre de projets planifiés associés à l’autre filtre spécifique.</li></ul></li></ul> |


<!--
# Scheduled projects

Scheduled Analysis Workspace projects can be managed under **Analytics > Components > Scheduled Projects**.

When you manage scheduled projects, you can edit and delete recurring project schedules:

*  Change the file type (.csv or PDF)
*  Update the project description
*  Add or remove recipients
*  Change the frequency

To modify a scheduled project

1.  Select **Analytics > Components > Scheduled Projects**.
1.  Search for a schedule in the search bar or by using the filter options in the left rail. You can filter by [!UICONTROL Tags], [!UICONTROL Owners], [!UICONTROL Favorites], and more.

![Screenshot showing the scheduled projects list with the column displaying title, owner, tags, delivered to, and other columns described in the Available columns section.](assets/scheduled-project-manager2.png)

## Available columns

| Field | Description |
| --- | --- |
| [!UICONTROL Favorites] | Selecting the star icon makes this schedule a favorite. |
| [!UICONTROL Schedule ID] | This ID is used mainly for debugging purposes. |
| [!UICONTROL Title and description] | Title and description of this project. |
| [!UICONTROL Owner] | The person who created and owns the project. |
| [!UICONTROL Tags] | (optional) Tagging is a good way to organize projects. All users can create tags and apply one or more tags to a project. However, you can see tags only for those projects that you own or that have been shared with you.  |
| [!UICONTROL Delivered to] | The recipient(s) of this scheduled project. |
| [!UICONTROL Expiration date] | For any scheduled project frequency, you can set the expiration date for up to one year in the future. |
| [!UICONTROL Frequency] | How often you want to have this schedule project sent to the recipient(s). |
| [!UICONTROL Execution time] | At what time of day this scheduled project gets sent. |
| [!UICONTROL Number of queries] | The number of queries against this project. | 

## Common actions

The following are common actions in the Scheduled Projects manager:

|Action|Description|
|---|---|
|**[!UICONTROL Edit]**|Select the title of the schedule to update its delivery settings.|
|**[!UICONTROL Delete]**|Select the scheduled project in the list and then click Delete from the menu. This will delete the selected schedule for the project; the project itself will not be deleted.|
|**[!UICONTROL Tag]**|Select the scheduled project in the list and then choose "Tag" or "Approve" to organize your schedules and make them easier to search for.|
|**[!UICONTROL View failed schedules]**|Navigate to the left rail > Other filters > Failed to see schedules that have failed.|
|**[!UICONTROL View expired schedules]**|Navigate to the left rail > Other filters > Expired to see schedules that have expired. Click the title of the schedule to setup a new delivery schedule.|
|**[!UICONTROL View schedule ID]**|Navigate to column options in the top right and add the Schedule ID column to the table. The scheduled ID is often useful for debugging.|

The Scheduled Projects manager shows the items that a specific user created. If the user account is disabled in the application, all scheduled deliveries stop. Scheduled project ownership can be transferred to a new user under **Admin** > **Analytics Users & Assets** > **Transfer Assets**.
-->