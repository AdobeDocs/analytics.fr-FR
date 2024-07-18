---
title: Communication de l’impact aux utilisateurs
description: Découvrez des moyens efficaces de communiquer l’impact d’un événement dans votre entreprise.
exl-id: 9ba83f3f-2eea-44c2-80b2-a0a9111d51cf
feature: Event
source-git-commit: 93099d36a65ca2bf16fbd6342f01bfecdc8c798e
workflow-type: tm+mt
source-wordcount: '346'
ht-degree: 1%

---

# Communication de l’impact d’un événement aux utilisateurs

Si des données [ sont affectées par un événement](overview.md), il est important de communiquer cet événement aux utilisateurs de votre entreprise.

* Développer une clause de non-responsabilité courante que vous pouvez utiliser dans les communications pour assurer la cohérence
* Fournir une communication permanente aux utilisateurs d’Analytics et aux principaux intervenants pendant et après l’événement
* Placez un rappel de calendrier pour les jalons suivants, tels que le mois ou l’année suivant. Cette communication permet à l’avenir de rappeler aux utilisateurs qui visualisent des rapports l’impact dans les rapports d’un mois à l’autre ou d’une année à l’autre.

Dans Adobe Analytics, les sections suivantes présentent différentes manières de communiquer avec les utilisateurs de votre entreprise. Vous pouvez également utiliser d’autres méthodes en dehors d’Adobe Analytics, telles que le courrier électronique, pour communiquer avec les utilisateurs.

## Communication par le biais des descriptions de panneau ou de visualisation

Si un projet Workspace est partagé par les utilisateurs de votre entreprise, vous pouvez communiquer l’impact d’un événement au moyen de descriptions de panneau ou de visualisation. Cliquez avec le bouton droit sur un panneau ou un en-tête de visualisation, puis sélectionnez **[!UICONTROL Modifier la description]**.

![Description du panneau](assets/panel_description.png)

## Communication au moyen de visualisations textuelles

Vous pouvez également communiquer l’impact d’un événement au moyen de visualisations textuelles dédiées. Voir [Visualisations de texte](/help/analyze/analysis-workspace/visualizations/text.md) dans le guide d’utilisation Analyser.

![Visualisation de texte](assets/text_visualization.png)

## Ajout d’événements de calendrier personnalisés aux tendances dans Workspace

Pour toute visualisation avec tendance dans Workspace, vous pouvez ajouter une série qui représente la période affectée.

1. Créez une mesure calculée avec le segment &quot;Jours affectés&quot; en suivant [Exclure des dates spécifiques dans l’analyse](segments.md).
1. Ajoutez la mesure souhaitée au canevas de mesure calculée.

   ![Mesure](assets/calcmetric_event.png)

1. Ajoutez un titre et une description informant les utilisateurs de l’impact. Vous pouvez également baliser cette mesure en tant qu’annotation de calendrier, le cas échéant.

   ![Titre et description](assets/calcmetric_title_description.png)

1. Dans un tableau à structure libre, ajoutez la dimension &quot;Jour&quot;. Ajoutez &quot;Visites&quot; et votre mesure calculée sous forme de colonnes côte à côte.

   ![Tableau à structure libre](assets/calcmetric_freeform.png)

1. Cliquez sur l’icône d’engrenage des paramètres de colonne pour votre mesure calculée et activez l’option **[!UICONTROL Interpréter zéro comme n’étant pas une valeur]**.

   ![Paramètres des mesures calculées](assets/calcmetric_zero_no_value.png)

1. Ajoutez une visualisation Ligne . Les jours concernés sont représentés avec une couleur différente. Pour plus d’informations, les utilisateurs peuvent également cliquer sur l’icône &quot;Infos&quot; dans la mesure calculée.

   ![Icône Infos](assets/calcmetric_infoicon.png)

