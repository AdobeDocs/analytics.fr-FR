---
description: Gérer les alertes.
title: Présentation d’Alert Manager
feature: Alerts
exl-id: 3408c79f-3d85-44b9-8fca-ce956853dfa4
source-git-commit: 49324ef7fd45adeef2c31167d0444a7e67041d6d
workflow-type: tm+mt
source-wordcount: '378'
ht-degree: 34%

---

# Gestionnaire d’alertes

La structure du gestionnaire d’alertes ressemble à celle du [ gestionnaire de segments](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-manage.html?lang=fr) et du [ gestionnaire de mesures calculées ](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-manager.html?lang=fr).

![](assets/alert-manager.png)

## Accès au gestionnaire des alertes

1. Dans Adobe Analytics, sélectionnez [!UICONTROL **Composants**] > [!UICONTROL **Alertes**].

## Actions disponibles dans le gestionnaire d’alertes

Dans le gestionnaire d’alertes, vous pouvez :

* Accéder au Générateur d’alertes en cliquant sur **[!UICONTROL + Ajouter]**
* Marquer les alertes ; permet d’organiser les alertes pour plus de facilité
* Supprimer des alertes
* Renommer les alertes
* Approuver les alertes
* Copier des alertes
* Activer/désactiver des alertes
* **Renouveler** la date d’expiration d’une alerte. Lorsqu’une ou plusieurs alertes sont sélectionnées, elles peuvent être renouvelées en cliquant sur **[!UICONTROL Renouveler]**. Cela prolonge leur date d’expiration d’un an à partir du moment où vous avez cliqué sur l’option **[!UICONTROL Renouveler]**, quelle que soit leur date d’expiration d’origine.
* Exporter une alerte au format .CSV
* Modifier des alertes en double-cliquant sur le titre de l’alerte
* Rechercher des alertes
* Ajouter des alertes à d’autres suites de rapports
* Spécifier/modifier le propriétaire d’une alerte
* Ajouter d’autres filtres
* Définir la **date d’expiration** d’une alerte

## Configuration des colonnes

Vous pouvez paramétrer les informations affichées pour chaque alerte dans le Gestionnaire d&#39;alertes en configurant les colonnes qui s&#39;affichent.

Pour configurer les colonnes visibles dans le gestionnaire d’alertes :

1. Dans Adobe Analytics, sélectionnez l’onglet **[!UICONTROL Composants]**, puis sélectionnez **[!UICONTROL Alertes]**.

1. Dans le gestionnaire d’alertes, sélectionnez l’icône **Personnaliser les colonnes** ![ icône ](assets/customize-columns-icon.png), puis sélectionnez les colonnes à afficher dans le gestionnaire d’alertes.

   Les colonnes suivantes sont disponibles :

   | Titre de la colonne | Description |
   |---|---|
   | Titre et description | Ces valeurs sont fournies dans le Générateur d’alertes. Pour modifier le titre et la description, sélectionnez le lien du titre pour ouvrir le Générateur d’alertes. |
   | Favoris | Affiche des icônes d’étoile en regard de chaque alerte, ce qui vous permet de marquer les alertes comme favorites. <!-- For more information, see [Mark calculated metrics as favorites](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-favorite.md). --> |
   | Type | Indique si l’alerte est une alerte de données Analytics ou une alerte d’utilisation de l’appel au serveur. |
   | Activé | Indique si l’alerte est actuellement activée ou désactivée. |
   | Suite de rapports | Indique dans quelle suite de rapports l’alerte a été enregistrée en dernier. |
   | Propriétaire | Indique qui possède l’alerte. En tant que non administrateur, vous ne pouvez afficher que les alertes que vous possédez ou celles qui ont été partagées avec vous. |
   | Balises | Affiche les balises qui ont été appliquées à l’alerte, soit par vous, soit par des personnes qui ont partagé l’alerte avec vous. |
   | Date d’expiration | Affiche la date et l’heure d’expiration de l’alerte. |
   | Date de modification | Indique la date de la dernière modification de l’alerte. |

   {style="table-layout:auto"}

   <!-- When "Last used" column is added, add this information as the description: Shows the date when the alert was last used. <p>This information can help you determine whether a component is valuable to users in your organization, where it is used, and if it needs to be deleted or modified.</p><p>Consider the following when viewing this column:</p><ul><li>This information does not include usage from the API, Report Builder, or Data Warehouse.</li><li>For some components, this column might not contain data if the component was last used prior to September 2023.</li></ul> -->


