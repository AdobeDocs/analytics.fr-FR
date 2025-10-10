---
description: Découvrez comment utiliser un histogramme, similaire à un graphique à barres, mais qui regroupe les nombres en plages (intervalles).
title: Histogramme
uuid: 8a6bd2c4-da15-4f64-b889-ab9add685046
feature: Visualizations
role: User, Admin
exl-id: f3dd7507-db2c-495c-b6b9-6c770c7c7ddc
source-git-commit: 978bd8642011dd2c8e43564c90303f194689a64e
workflow-type: tm+mt
source-wordcount: '346'
ht-degree: 89%

---

# Histogramme {#histogram}

>[!CONTEXTUALHELP]
>id="workspace_histogram_button"
>title="Histogramme"
>abstract="Créez une visualisation sous forme d’histogramme représentant la distribution des données numériques en groupes de plages."


>[!BEGINSHADEBOX]

_Cet article présente la visualisation Histogramme dans_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _&#x200B;**Adobe Analytics**._<br/>_Voir [Histogramme](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-workspace/visualizations/histogram) pour la_ version ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _&#x200B;**Customer Journey Analytics** de cet article._

>[!ENDSHADEBOX]


La visualisation ![Histogramme](/help/assets/icons/Histogram.svg) **[!UICONTROL Histogramme]** est semblable à une visualisation [!UICONTROL Barres], à ceci près qu’elle regroupe les chiffres par classes (intervalles). Analytics automatise la classification des chiffres. Vous pouvez toutefois modifier les paramètres dans les [Paramètres avancés](#advanced-settings).

## Utilisation

Pour créer un histogramme, procédez comme suit :

1. Ajoutez une visualisation ![Histogramme](/help/assets/icons/Histogram.svg) **[!UICONTROL Histogramme]**. Consultez [Ajouter une visualisation à un panneau](freeform-analysis-visualizations.md#add-visualizations-to-a-panel).
1. Faites glisser une mesure à partir de la liste des composants **[!UICONTROL Mesures]** ou sélectionnez une mesure dans le menu déroulant [!UICONTROL *Ajouter une mesure*].
1. (Facultatif) Sélectionnez **[!UICONTROL Afficher les paramètres avancés]**. Consultez [Paramètres avancés](#advanced-settings).
1. Sélectionnez la **[!UICONTROL Version]**.

>[!NOTE]
>
>Les histogrammes prennent seulement en charge les mesures standard, et non les mesures calculées.

Dans l’exemple ci-dessous, un histogramme est utilisé pour regrouper les sessions pour le nombre de personnes. L’histogramme indique que la plupart des personnes disposent de 16 à 21 sessions pour la période sélectionnée.

![](assets/histogram.png)

## Paramètres avancés

Dans le cadre de la visualisation, des paramètres d’histogramme spécifiques sont disponibles.

| Paramètres de l’histogramme | Description |
|---|---|
| **[!UICONTROL Compartiment de début]** | Détermine par quel intervalle commence l’histogramme. « 1 » par défaut. Peut être défini sur 0 à l’infini (aucun nombre négatif). |
| **[!UICONTROL Compartiments de mesure]** | Permet d’augmenter ou de réduire le nombre de plages de données (compartiments). Le nombre maximal de compartiments est de 50. |
| **[!UICONTROL Taille du compartiment de mesure]** | Permet de définir la taille de chaque intervalle. Vous pouvez par exemple modifier la taille de l’intervalle d’une page vue à deux pages vues. |
| **[!UICONTROL Méthode de comptage]** | Faites votre choix entre **[!UICONTROL Personne]**, **[!UICONTROL Session]** ou **[!UICONTROL Événement]**. Par exemple, pages vues par session ou pages vues par personne ou pages vues par événement. |

<!--Russ or Meike - Check Hit Type link above. -->

**Exemples** :

| Compartiment de début | Compartiments de mesure | Taille du compartiment de mesure | Résultats |
|:----:|:--:|:--:|:--|
| 1 | 5 | 2 | ![Histogramme, compartiment de début 1, compartiments de mesure 5, taille de compartiment de mesure 2](assets/histogram-1-5-2.png) |
| 0 | 3 | 5 | ![Histogramme, compartiment de début 0, compartiments de mesure 3, taille de compartiment de mesure 5](assets/histogram-0-3-5.png) |

>[!MORELIKETHIS]
>
>[Ajouter une visualisation à un panneau](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>&#x200B;>[Paramètres de visualisation](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>&#x200B;>[Menu contextuel de visualisation](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>&#x200B;>[Utiliser des histogrammes pour identifier les valeurs de données inattendues](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/using-histograms-to-identify-unexpected-data-values/ba-p/596168)

