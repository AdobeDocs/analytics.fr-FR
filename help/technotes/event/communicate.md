---
title: Communiquer l’impact aux utilisateurs
description: Découvrez des moyens efficaces de communiquer l’impact d’un événement dans votre organisation.
exl-id: 9ba83f3f-2eea-44c2-80b2-a0a9111d51cf
feature: Curate and Share
source-git-commit: 29ab0cc535bd8f74b50428c11756bf8b446a23ab
workflow-type: tm+mt
source-wordcount: '346'
ht-degree: 1%

---

# Communication de l’impact des événements aux utilisateurs

Si des données [affectées par un événement](overview.md) sont présentes, il est important de communiquer cet événement aux utilisateurs et utilisatrices de votre organisation.

* Développez une clause de non-responsabilité commune que vous pouvez utiliser dans les communications par souci de cohérence
* Communiquer de manière continue avec les utilisateurs d’Analytics et les principales parties prenantes pendant et après l’événement
* Placez un rappel de calendrier pour les jalons suivants, par exemple pour le mois ou l’année suivant. À l’avenir, cette communication rappellera aux utilisateurs et utilisatrices qui consultent les rapports l’impact dans les rapports mois par mois ou année par année.

Dans Adobe Analytics, les sections suivantes présentent différentes manières de communiquer avec les utilisateurs de votre entreprise. Vous pouvez également utiliser d’autres méthodes en dehors d’Adobe Analytics, telles que l’e-mail, pour communiquer avec les utilisateurs.

## Communication par le biais de descriptions de panneau ou de visualisation

Si vous partagez un projet Workspace avec des utilisateurs de votre entreprise, vous pouvez communiquer l’impact d’un événement au moyen de descriptions de panneau ou de visualisation. Cliquez avec le bouton droit sur un panneau ou un en-tête de visualisation, puis sélectionnez **[!UICONTROL Modifier la description]**.

![Description du panneau](assets/panel_description.png)

## Communication par le biais de visualisations textuelles

Vous pouvez également communiquer l’impact d’un événement par le biais de visualisations textuelles dédiées. Voir [Visualisations textuelles](/help/analyze/analysis-workspace/visualizations/text.md) dans le guide d’utilisation Analyser.

![Visualisation de texte](assets/text_visualization.png)

## Ajout d’événements de calendrier personnalisés aux tendances dans Workspace

Pour toute visualisation des tendances dans Workspace, vous pouvez ajouter dans une série qui représente la période concernée.

1. Créez une mesure calculée avec le segment « Jours affectés » en suivant [Exclure des dates spécifiques dans l’analyse](segments.md).
1. Ajoutez la mesure souhaitée à la zone de travail des mesures calculées.

   ![Mesure](assets/calcmetric_event.png)

1. Ajoutez un titre et une description informant les utilisateurs de l’impact. Vous pouvez également baliser cette mesure en tant qu’annotation de calendrier, si vous le souhaitez.

   ![Titre et description](assets/calcmetric_title_description.png)

1. Dans un tableau à structure libre, ajoutez la dimension « Jour ». Ajoutez « Visites » et votre mesure calculée sous forme de colonnes côte à côte.

   ![Tableau à structure libre](assets/calcmetric_freeform.png)

1. Cliquez sur l’icône d’engrenage des paramètres de colonne pour votre mesure calculée, puis activez **[!UICONTROL Interpréter zéro comme n’étant pas une valeur]**.

   ![&#x200B; Paramètres des mesures calculées &#x200B;](assets/calcmetric_zero_no_value.png)

1. Ajoutez une visualisation Ligne . Les jours concernés sont représentés avec une couleur différente. Les utilisateurs peuvent également cliquer sur l’icône « Infos » dans la mesure calculée pour obtenir plus d’informations.

   ![&#x200B; Icône Infos &#x200B;](assets/calcmetric_infoicon.png)

