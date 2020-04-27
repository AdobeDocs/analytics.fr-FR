---
description: Décrit comment créer des rapports Chemin avec des filtres prédéfinis.
title: Filtrage des rapports Chemin en ajoutant des requêtes dépendantes
topic: Report builder
uuid: dd1294f8-a26b-4254-a9f6-1365b2912adf
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Filtrage des rapports Chemin en ajoutant des requêtes dépendantes

Décrit comment créer des rapports Chemin avec des filtres prédéfinis.

Rapports et analyses marketing  de  de quelques rapports autonomes qui sont des rapports de cheminement principaux avec des, tels que [!UICONTROL Next] et [!UICONTROL Previous Site Section] des rapports, des rapports d’entrée et [!UICONTROL Exit Site Section] et des rapports [!UICONTROL Single Site Section] .

Report Builder does not offer these as standalone reports, but you can create them through the **[!UICONTROL Add dependent request]** > **[!UICONTROL Path]** context menus. Les rapports suivants sont disponibles :

* Chemin > Page - Abandon
* Chemin > Chemin d’accès
* Chemin > Chemin de sortie
* Chemin > Page suivante
* Chemin > Chemin d’accès > Page suivante
* Chemin > Page précédente
* Chemin > Chemin de sortie > Page précédente
* Chemin > Chemin d’accès > En tant que page d’entrée
* Chemin > Chemin de sortie > En tant que page de sortie

1. Sélectionnez plusieurs lignes d’une requête existante, puis cliquez avec le bouton droit **[!UICONTROL Add Dependent Request]** > **[!UICONTROL Path]**.

   (Note that you have to select at least 3 rows if you want to see the **[!UICONTROL Page Fallout]** menu item.)

   ![](assets/dependen_request.png)

1. Select the predefined filter, for example **[!UICONTROL Previous Page]**.

   L’Assistant Requête s’affiche, avec la mesure Page précédente déjà sélectionnée. 1. Continuez à préciser votre requête dans l’Assistant Requête avant de la générer.
