---
description: L’histogramme est un nouveau type de visualisation d’Analysis Workspace.
title: Histogramme
uuid: 8a6bd2c4-da15-4f64-b889-ab9add685046
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Histogramme

Un histogramme est semblable à un graphique à barres, à ceci près qu’il répartit les chiffres en classes (intervalles). Analytics automatise la classification des chiffres. Vous pouvez toutefois modifier les paramètres dans les [Paramètres avancés](#section_09D774C584864D4CA6B5672DC2927477).

## Création d’un histogramme {#section_74647707CC984A1CB6D3097F43A30B45}

Pour créer un histogramme, procédez comme suit :

1. Click **[!UICONTROL Visualizations]** in the left rail.
1. Drag **[!UICONTROL Histogram]** to the panel.
1. Choose a Metric to drag to the Histogram visualization and click **[!UICONTROL Build]**.

![](assets/histogram.png)

>[!NOTE] Les histogrammes prennent seulement en charge les mesures standard, et non les mesures calculées.

Ici, nous avons utilisé la mesure Pages vues par visiteurs uniques. La première classe (à gauche) correspond à une page vue par visiteur unique, la deuxième à deux pages vues, etc.

![](assets/histogram2.png)

## Paramètres avancés {#section_09D774C584864D4CA6B5672DC2927477}

Pour régler les paramètres de l’histogramme, cliquez sur l’icône d’engrenage Paramètres dans le coin supérieur droit. Voici les paramètres que vous pouvez modifier :

| Paramètres de l’histogramme | Description |
|---|---|
| Intervalle de début | Détermine par quel intervalle commence l’histogramme. « 1 » par défaut. Peut être défini sur 0 à l’infini (aucun nombre négatif). |
| Intervalles de mesures | Permet d’augmenter ou de réduire le nombre de classes de données (intervalles). Il ne peut pas y avoir plus de 50 intervalles. |
| Taille de l’intervalle de mesures | Permet de définir la taille de chaque intervalle. Vous pouvez par exemple modifier la taille de l’intervalle d’une page vue à deux pages vues. |
| Méthode de comptage | Choisissons entre [Visiteur](https://marketing.adobe.com/resources/help/fr_FR/reference/visitors.html), [Visite](https://marketing.adobe.com/resources/help/fr_FR/reference/metrics_visit.html) ou [Accès](https://marketing.adobe.com/resources/help/fr_FR/reference/hit.html). Par exemple, pages vues par visite ou pages vues par visiteur ou pages vues par accès. Pour l’accès, la mesure « Occurrences » est utilisée comme mesure de l’axe Y dans un tableau à structure libre. |

**Exemples** :

* Intervalle de début : 1 ; Intervalles de mesures : 5 ; Taille de l’intervalle de mesures : 2 générera cet histogramme : 1-2, 3-4, 5-6, 7-8, 9-10.
* Intervalle de début : 0 ; Intervalles de mesures : 3 ; Taille de l’intervalle de mesures : 5 générera cet histogramme : 0-4, 5-9, 10-14.

## Affichage et modification des données de l’histogramme {#section_B2CD7CDF0F6B432F928103AE7AAA3617}

To view or change the data source for the histogram chart, click the dot next to the Histogram header to go to **[!UICONTROL Data Source Settings]** > **[!UICONTROL Show Data Source]**.

![](assets/manage-data-source.png)

Les segments prédéfinis du tableau sont des segments internes ; ils n’apparaîtront pas dans le sélecteur de segments. Click the &quot;i&quot; icon next to the segment name, then click **[!UICONTROL Make public]** to make the segment public.

![](assets/prebuilt_segments.png)

Pour découvrir d’autres façons de générer des tableaux de données à structure libre et d’autres visualisations (ventilations de données, par exemple), cliquez [ici](https://marketing.adobe.com/resources/help/fr_FR/analytics/analysis-workspace/freeform-analysis-visualizations.html).
