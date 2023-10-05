---
description: Gérer les alertes.
title: Présentation d’Alert Manager
feature: Alerts
exl-id: 3408c79f-3d85-44b9-8fca-ce956853dfa4
source-git-commit: 9a6c2e7c2f83882f6df630f975b0c44e75a2ed7a
workflow-type: tm+mt
source-wordcount: '448'
ht-degree: 38%

---

# Gestionnaire d’alertes

La structure du gestionnaire des alertes ressemble à celle de la fonction [Gestionnaire de segments](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-manage.html?lang=fr) et la variable [Gestionnaire de mesures calculées](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-manager.html?lang=fr).

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

1. Dans Adobe Analytics, sélectionnez la variable **[!UICONTROL Composants]** , puis sélectionnez **[!UICONTROL Alertes]**.

1. Dans le gestionnaire d’alertes, sélectionnez la variable **Personnalisation des colonnes** icon ![Icône Personnaliser les colonnes](assets/customize-columns-icon.png), puis sélectionnez les colonnes à afficher dans le Gestionnaire d’alertes.

   Les colonnes suivantes sont disponibles :

   | Titre de la colonne | Description |
   |---|---|
   | Favoris | Affiche des icônes d’étoile en regard de chaque alerte, ce qui vous permet de marquer les alertes comme favorites. <!-- For more information, see [Mark calculated metrics as favorites](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-favorite.md). --> |
   | Titre et description | Ces valeurs sont fournies dans le Générateur d’alertes. Pour modifier le titre et la description, sélectionnez le lien du titre pour ouvrir le Générateur d’alertes. |
   | Suite de rapports | Indique dans quelle suite de rapports l’alerte a été enregistrée en dernier. |
   | Propriétaire | Indique qui possède l’alerte. En tant que non administrateur, vous ne pouvez afficher que les alertes que vous possédez ou celles qui ont été partagées avec vous. |
   | Balises | Affiche les balises qui ont été appliquées à l’alerte, soit par vous, soit par des personnes qui ont partagé l’alerte avec vous. |
   | Partagé avec | Répertorie les individus ou les groupes (administrateur uniquement) ou toutes les personnes (administrateur uniquement) avec lesquelles vous avez partagé l’alerte. |
   | Date de modification | Indique la date de la dernière modification de l’alerte. |
   | Dernière utilisation | Affiche la date de la dernière utilisation de l’alerte. <p>Ces informations peuvent vous aider à déterminer si un composant est utile aux utilisateurs et utilisatrices de votre entreprise, où il est utilisé et s’il doit être supprimé ou modifié.</p><p>Tenez compte des points suivants lorsque vous affichez cette colonne :</p><ul><li>Ces informations n’incluent pas l’utilisation de l’API, du Report Builder ou du Data Warehouse.</li><li>Pour certains composants, cette colonne peut ne pas contenir de données si le composant a été utilisé pour la dernière fois avant septembre 2023.</li></ul> |

   {style="table-layout:auto"}
