---
description: Utilisation de la visualisation en ligne pour représenter les jeux de données des tendances (temporels).
title: Ligne
uuid: 0508ff29-43fe-4f3a-a5f7-051869271b55
feature: Visualizations
role: User, Admin
exl-id: d177b39f-add7-4011-977a-1bdf3a9368cb
source-git-commit: 5a35d2acd428d16afff3d8e85cfb084d6a6476c4
workflow-type: tm+mt
source-wordcount: '532'
ht-degree: 24%

---

# Ligne {#line}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_line_button"
>title="Ligne"
>abstract="Créez une visualisation sous forme de graphe à courbes qui montre l’évolution des valeurs. Pour pouvoir utiliser un graphe à courbes, le temps doit être défini comme une dimension."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_Cet article présente la visualisation Ligne dans_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics**._<br/>_Voir [Ligne](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/visualizations/line) pour la version_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics** de cet article._

>[!ENDSHADEBOX]

La visualisation ![GraphTrend](/help/assets/icons/GraphTrend.svg) **[!UICONTROL Ligne]** représente les mesures à l’aide d’une ligne pour montrer l’évolution des valeurs au fil du temps. Une visualisation en ligne ne peut être utilisée que lorsque le temps est utilisé comme dimension.

![Visualisation en ligne](assets/line-viz.png)


## Paramètres

Dans le cadre des [paramètres de visualisation](freeform-analysis-visualizations.md#settings), des paramètres de visualisation en ligne spécifiques sont disponibles.

| Paramètre | Description |
|---|---|
| **[!UICONTROL Granularité]** | Faites votre choix dans le menu déroulant granularité pour modifier une visualisation des tendances de quotidienne à hebdomadaire en mensuelle, etc. La granularité est également mise à jour dans le tableau de la source de données. |
| **[!UICONTROL Afficher min]** <br/>**[!UICONTROL Afficher max ]** | Vous pouvez superposer un libellé de valeur minimale et maximale pour mettre en surbrillance les valeurs minimale et maximale d’une mesure. Les valeurs min/max sont dérivées des points de données visibles dans la visualisation, et non du jeu complet de valeurs dans une dimension.<br/>![Recouvrement avec les étiquettes de valeur minimale et maximale.](assets/min-max-labels.png) |
| **[!UICONTROL Afficher la tendance]** | Vous pouvez choisir d’ajouter une ligne de tendance de moyenne glissante ou de régression à votre série de lignes. Les courbes de tendance permettent de dépeindre un motif plus clair dans les données. Lorsque cette option est sélectionnée, sélectionnez un modèle dans la liste. Consultez [Modèles](#models) pour obtenir un aperçu et une description des modèles disponibles.<br/>![Courbe de tendance linéaire](assets/show-linear-trendline.png). |

>[!TIP]
>
>Il est recommandé d’appliquer des tendances aux données qui n’incluent pas les dates d’aujourd’hui (données partielles) ou de demain. Les dates d’aujourd’hui ou de demain biaisent la tendance. Toutefois, si vous devez inclure des dates futures, supprimez les zéros des données afin dʼéviter que ces jours ne soient faussés. Accédez au tableau de la source de données de la visualisation, choisissez votre colonne de mesures, puis activez **[!UICONTROL Paramètres des colonnes]** > **[!UICONTROL Interpréter zéro comme n’étant pas une valeur]**.



### Modèles

Toutes les courbes de tendance des modèles de régression sont ajustées à lʼaide des moindres carrés ordinaires :

| Modèle | Description |
| --- | --- |
| **[!UICONTROL Linéaire]** | Créez une ligne droite adaptée aux jeux de données linéaires simples et utile lorsque les données augmentent ou diminuent à un taux constant. Équation : `y = a + b * x` |
| **[!UICONTROL Logarithmique]** | Créez une ligne courbe parfaitement adaptée et utile lorsque le taux de modification des données augmente ou diminue rapidement, puis s’ajuste. Une courbe de tendance logarithmique peut utiliser des valeurs négatives et positives. Équation : `y = a + b * log(x)` |
| **[!UICONTROL Exponentiel]** | Créez une ligne incurvée utile lorsque les données augmentent ou diminuent à un rythme croissant. Cette option ne doit pas être utilisée si vos données contiennent des valeurs nulles ou négatives. Équation : `y = a + e^(b * x)` |
| **[!UICONTROL Puissance]** | Créez une ligne incurvée utile pour les jeux de données qui comparent des mesures qui augmentent à une vitesse spécifique. Cette option ne doit pas être utilisée si vos données contiennent des valeurs nulles ou négatives. Équation : `y = a * x^b` |
| **[!UICONTROL Quadratique]** | Trouve la meilleure réponse pour un jeu de données en forme de parabole (concave vers le haut ou vers le bas). Équation : `y = a + b * x + c * x^2` |
| **[!UICONTROL Moyenne glissante]** | Créez une courbe de tendance lisse basée sur un ensemble de moyennes. Connue également sous le nom de moyenne mobile, une moyenne glissante utilise un nombre spécifique de points de données (déterminé par votre [!UICONTROL Granularité] sélection), calcule leur moyenne et utilise cette moyenne comme point dans la ligne. Par exemple, une moyenne glissante de sept jours ou de quatre semaines. |

>[!MORELIKETHIS]
>
>[Ajouter une visualisation à un panneau](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[Paramètres de visualisation ](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[Menu contextuel de visualisation](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>

