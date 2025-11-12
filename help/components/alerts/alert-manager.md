---
description: Découvrez comment gérer les alertes.
title: Gérer les alertes
feature: Alerts
exl-id: 3408c79f-3d85-44b9-8fca-ce956853dfa4
source-git-commit: ca84a5f807545d7196e2e0e90d3209c32d3fd789
workflow-type: tm+mt
source-wordcount: '596'
ht-degree: 22%

---


# Gérer les alertes


Vous pouvez filtrer, baliser, supprimer, renommer, copier, activer, désactiver, renouveler et exporter des alertes à partir d’une interface de gestion centrale [!UICONTROL Alertes]. Pour gérer des alertes :

* Sélectionnez **[!UICONTROL Composants]** dans l’interface principale, puis sélectionnez **[!UICONTROL Alertes]**.

La structure du gestionnaire d’alertes est similaire à celle du [gestionnaire de segments](/help/components/segmentation/segmentation-workflow/seg-manage.md) et du [gestionnaire de mesures calculées](/help/components/calculated-metrics/workflow/cm-manager.md).


## Gestionnaire d’alertes

Le gestionnaire d’alertes comporte les éléments d’interface suivants :

![Interface des filtres](assets/alerts-manager.png)

### Liste des alertes

La liste des alertes affiche ➊ toutes les alertes que vous possédez, celles qui ont été incluses dans tous vos projets et celles qui ont été partagées avec vous. La liste comporte les colonnes suivantes :

| Colonne | Description |
|---|---|
| ![Contour en forme d’étoile](/help/assets/icons/StarOutline.svg) | Sélectionnez pour favoriser ![Étoile](/help/assets/icons/Star.svg) ou ne pas favoriser ![ÉtoileContour](/help/assets/icons/StarOutline.svg) une alerte. |
| **[!UICONTROL Titre et description]** | Pour modifier l’alerte, cliquez sur le lien du titre, qui ouvre le [créateur d’alertes](alert-builder.md#alert-builder). |
| **[!UICONTROL Type]** | Type de l’alerte : une alerte de données Adobe Analytics ou une alerte d’utilisation des appels au serveur . |
| **[!UICONTROL Activé]** | L’alerte est activée ou désactivée. |
| **[!UICONTROL Suite de rapports]** | Les suites de rapports auxquelles cette alerte s’applique. |
| **[!UICONTROL Propriétaire]** | Propriétaire de l’alerte. En tant que non-administrateur, vous ne voyez que les alertes que vous possédez ou celles qui sont partagées avec vous. |
| **[!UICONTROL Balises]** | Balises pour cette alerte. |
| **[!UICONTROL Date d’expiration]** | Date et heure d’expiration de l’alerte. |
| **[!UICONTROL Date de modification]** | Date et heure de la dernière modification de l’alerte. |

<!-- 

When "Last used" column is added, add this information as the description: Shows the date when the alert was last used. <p>This information can help you determine whether a component is valuable to users in your organization, where it is used, and if it needs to be deleted or modified.</p><p>Consider the following when viewing this column:</p><ul><li>This information does not include usage from the API, Report Builder, or Data Warehouse.</li><li>For some components, this column might not contain data if the component was last used prior to September 2023.</li></ul>

-->

Utilisez ![Paramètres de colonne](/help/assets/icons/ColumnSetting.svg) pour spécifier les colonnes à afficher.

### Barre d’actions

Vous pouvez agir sur les alertes à l’aide de la barre d’actions ➋. La barre d’actions contient les actions suivantes :

| Icône | Action | Description |
|:---:|---|---|
| ![Cercle d’ajout](/help/assets/icons/AddCircle.svg) | **[!UICONTROL Ajouter]** | Ajoutez une autre alerte à l’aide du [créateur d’alertes](alert-builder.md#alert-builder). |
| ![Recherche](/help/assets/icons/Search.svg) | [!UICONTROL *Rechercher par titre*] | Lorsqu’aucune alerte n’est sélectionnée dans la liste, recherchez des alertes à l’aide de ce champ de recherche. |
| ![Libellé](/help/assets/icons/Label.svg) | **[!UICONTROL Étiquette]** | Balisez les alertes sélectionnées. Dans la boîte de dialogue **[!UICONTROL Alerte de balise]**, sélectionnez ou désélectionnez les balises pour les alertes sélectionnées. Sélectionnez **[!UICONTROL Enregistrer]** pour enregistrer les balises des alertes sélectionnées. |
| ![Supprimer](/help/assets/icons/Delete.svg) | **[!UICONTROL Supprimer]** | Supprimez les alertes sélectionnées. Il vous est demandé de confirmer. |
| ![Modifier](/help/assets/icons/Edit.svg) | **[!UICONTROL Renommer]** | Renommez une alerte sélectionnée. Lorsque cette option est sélectionnée, vous pouvez renommer l’alerte en ligne. |
| ![Copier](/help/assets/icons/Copy.svg) | **[!UICONTROL Copier]** | Copiez l’alerte sélectionnée. De nouvelles alertes sont créées avec le même nom et le même suffixe `(Copy)`. |
| ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | **[!UICONTROL activer]** ou **[!UICONTROL désactiver]** | Activer ou désactiver les alertes sélectionnées. |
| ![Actualiser](/help/assets/icons/Refresh.svg) | **[!UICONTROL Renouveler]** | Renouvelle la date d’expiration d’une alerte. La date d’expiration s’étend sur 1 an à compter du jour où vous sélectionnez cette option, quelle que soit la date d’expiration d’origine. |
| ![Fichier CSV](/help/assets/icons/FileCSV.svg) | **[!UICONTROL Exporter dans un fichier CSV]** | Exportez les alertes dans un fichier `Alerts List.csv`. |


### Barre de filtres actifs

La barre de filtrage affiche ➌ les filtres actifs appliqués à partir du panneau de filtrage à la liste des alertes (le cas échéant). Vous pouvez supprimer rapidement un filtre à l’aide de ![CrossSize75](/help/assets/icons/CrossSize75.svg). Si plusieurs filtres sont spécifiés, vous pouvez tous les supprimer à l’aide de **[!UICONTROL Tout supprimer]**.


### Panneau Filtrer

Vous pouvez filtrer la liste des alertes à l’aide du ![ du panneau de gauche ](/help/assets/icons/Filter.svg)Filtrer **** Filtrer➍. Le panneau de filtrage affiche le type de filtre et le nombre d’alertes qui respectent le filtre spécifique.


1. Sélectionnez ![Filtrer](/help/assets/icons/Filter.svg) pour ouvrir le panneau Filtres. Si vous avez besoin de plus d’espace pour la liste des alertes, vous pouvez sélectionner ![Filtrer](/help/assets/icons/Filter.svg) une fois de plus pour fermer le panneau.
1. Sélectionnez des filtres dans l’une des sections de filtres disponibles.


#### Section de filtrage des balises

{{tagfiltersection}}


#### Section de filtrage de la suite de rapports

{{reportsuitefiltersection}}


#### Section de filtre des propriétaires

{{ownerfiltersection}}


#### Section Filtre de statut activé

{{enabledstatusfiltersection}}


#### Section de filtre de type

{{typefiltersection}}


#### Section des autres filtres

{{otherfiltersfiltersection}}



## Modifier les alertes

Vous pouvez modifier une alerte.

* Dans la liste [[!UICONTROL Alerte]](#alerts-list), sélectionnez le titre de l’alerte.

Vous utilisez le [créateur d’alertes](alert-builder.md#alert-builder) pour modifier l’alerte.

## Résolution des problèmes liés à une alerte

Lors de la résolution d’un problème avec une alerte, indiquez le numéro JID (Job Instance ID) à l’assistance Adobe. Le numéro de JID se trouve au bas de l’e-mail de notification d’alerte que vous recevez.

![E-mail d’alerte](assets/alerts-email.PNG)


<!--

# Manage alerts

You can manage existing alerts in the Alerts manager. You can perform various management tasks on alerts, such as tagging, renaming, deleting, and more.

The Alerts manager is structured very much like the [Segment Manager](/help/components/segmentation/segmentation-workflow/seg-manage.md) and the [Calculated Metric Manager](/help/components/calculated-metrics/calcmetric-workflow/cm-manager.md).

 ![](assets/alert-manager.png)

## Create alerts

To create alerts from the Alerts manager:

1. Select **[!UICONTROL Components]** > **[!UICONTROL Alerts]** to access the Alerts manager in Adobe Analytics.

   ![](assets/alert-manager.png)

1. Select [!UICONTROL **Add**] (or [!UICONTROL **Create new alert**] if you don't have any existing alerts).

1. Select the alert type that corresponds to the alert that you want to create:

   * [!UICONTROL **Analytics data alert**]: An alert to notify you when abnormal events occur in your data. 

     If you select this option, continue with [Create alerts](/help/components/alerts/alert-builder.md) for more details about creating alerts.

   * [!UICONTROL **Server call usage alert**]: An alert to notify you of the risk or occurrence of an overage in your server call consumption and commitment data. 

     If you select this option, continue with [Server call usage alerts](/help/admin/tools/server-call-usage/scu-alerts.md).

     >[!NOTE]
     >
     >You must be an Analytics administrator or a user with the Server call usage permission in order to have access to server call usage. 

## Manage existing alerts

You can perform various actions on existing alerts, such as tagging, renaming, deleting, and so forth.

To manage existing alerts in the Alerts manager:

1. Select **[!UICONTROL Components]** > **[!UICONTROL Alerts]** to access the Alerts manager in Adobe Analytics.

   ![](assets/alert-manager.png)

1. Select one or more alerts that you want to manage.

   ![](assets/alert-manager-tasks.png)

1. In the action bar, select any of the following options:

   | Action | Function |
   |---------|----------|
   | [!UICONTROL **Tag**] | Apply a tag to an alert. This helps you to organize alerts for ease of use. |
   | [!UICONTROL **Delete**] | Deletes the alert. |
   | [!UICONTROL **Rename**] | Renames the alert. |
   | [!UICONTROL **Approve**] | Mark the alert as Approved. |
   | [!UICONTROL **Copy**] | Creates a copy (duplicate) of the alert. |
   | [!UICONTROL **Disable**] | Disables an alert that is currently enabled. |
   | [!UICONTROL **Enable**] | Enables an alert that is currently disabled. |
   | [!UICONTROL **Renew**] | Renews the alert expiration date. This extends the  expiration date to be 1 year from the day you selected this option, regardless of the original expiration date. |
   | [!UICONTROL **Export to CSV**] | Exports the alert to a .CSV file. |

## Edit an alert

To edit an existing alert:

1. Select **[!UICONTROL Components]** > **[!UICONTROL Alerts]** to access the Alerts manager in Adobe Analytics.

   ![](assets/alert-manager.png)

1. Select the alert name in the [!UICONTROL **Title and description**] column.

1. Edit the alert as desired. 

   Following are some of the things you can do when editing an alert:

   * Add alerts to other report suites
   * Add or modify the description
   * Modify the time granularity
   * Modify the recipients 
   * Modify the expiration date
   * Modify the metrics and filters

1. Select [!UICONTROL **Save**].

## Configure columns 

You can configure the information displayed for each alert in the Alerts manager by configuring the columns that are displayed.

To configure the visible columns in the Alerts manager:

1. In Adobe Analytics, select the **[!UICONTROL Components]** tab, then select **[!UICONTROL Alerts]**. 

1. In the Alert manager, select the **Customize columns** icon ![Customize columns icon](assets/customize-columns-icon.png), then select the columns that you want to be displayed in the Alerts manager.

   The following columns are available:

   | Column title  | Description |
   |---|---|
   | Title and description | These values are provided in the Alert builder. To edit the title and description, select the title link to open the Alert builder.  |
   | Favorites  | Displays star icons next to each alert, allowing you to mark alerts as favorites. |
   | Type | Shows whether the alert is an Analytics data alert or a Server call usage alert. |
   | Enabled | Shows whether the alert is currently enabled or disabled. |
   | Report suite | Indicates in which report suite the alert was last saved.  |
   | Owner | Indicates who owns the alert. As a non-admin, you can see only alerts you own or those that were shared with you.  |
   | Tags | Shows tags that were applied to the alert, either by you or by people who shared the alert with you.  |
   | Expiration date | Shows the date and time when the alert is set to expire. |
   | Date modified | Indicates the date when the alert was last modified.  |

   {style="table-layout:auto"}
   
   
    When "Last used" column is added, add this information as the description: Shows the date when the alert was last used. <p>This information can help you determine whether a component is valuable to users in your organization, where it is used, and if it needs to be deleted or modified.</p><p>Consider the following when viewing this column:</p><ul><li>This information does not include usage from the API, Report Builder, or Data Warehouse.</li><li>For some components, this column might not contain data if the component was last used prior to September 2023.</li></ul> 
   
-->

