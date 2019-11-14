---
description: Décrit comment créer des rapports Chemin avec des filtres prédéfinis.
solution: Analytics
title: Filtrage des rapports Chemin en ajoutant des requêtes dépendantes
topic: Report builder
uuid: dd1294f8-a26b-4254-a9f6-1365b2912adf
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Filtrage des rapports Chemin en ajoutant des requêtes dépendantes

Décrit comment créer des rapports Chemin avec des filtres prédéfinis.

Les rapports et analyses marketing proposent quelques rapports autonomes qui sont des rapports Chemin supérieurs avec des filtres prédéfinis, tels que les rapports [!UICONTROL Section de site suivante] et [!UICONTROL précédente], [!UICONTROL Section d’accès au site et de sortie du site] et le rapport [!UICONTROL Section de site unique].

Report Builder does not offer these as standalone reports, but you can create them through the **[!UICONTROL Add dependent request]** &gt; **[!UICONTROL Path]** context menus. Les rapports suivants sont disponibles :

* Chemin &gt; Page - Abandon
* Chemin &gt; Chemin d’accès
* Chemin &gt; Chemin de sortie
* Chemin &gt; Page suivante
* Chemin &gt; Chemin d’accès &gt; Page suivante
* Chemin &gt; Page précédente
* Chemin &gt; Chemin de sortie &gt; Page précédente
* Chemin &gt; Chemin d’accès &gt; En tant que page d’entrée
* Chemin &gt; Chemin de sortie &gt; En tant que page de sortie

1. Select multiple rows from an existing request, then right-click **[!UICONTROL Add Dependent Request]** &gt; **[!UICONTROL Path]**.

   (Remarque : vous devez sélectionner au moins 3 lignes si vous souhaitez afficher l’option de menu **[!UICONTROL Page - Abandon].)**

   ![](assets/dependen_request.png)

1. Select the predefined filter, for example **[!UICONTROL Previous Page]**.

   L’Assistant Requête s’affiche, avec la mesure Page précédente déjà sélectionnée. 1. Continuez à affiner votre requête dans l’Assistant Requête et générez-la.
