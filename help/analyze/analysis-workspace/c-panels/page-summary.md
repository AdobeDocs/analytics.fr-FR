---
description: Découvrez comment utiliser le panneau de résumé de la page pour afficher un résumé des informations d’une page sélectionnée.
title: Panneau Résumé de la page
feature: Panels
role: User, Admin
exl-id: f0b7cd92-17b2-452d-9aab-f78629360ab8
source-git-commit: 19c2c1abd7f1799598597c0e696d0b001c1ef0ea
workflow-type: tm+mt
source-wordcount: '642'
ht-degree: 90%

---

# Panneau Synthèse de la page {#page-summary}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_pagesummary_button"
>title="Résumé de la page"
>abstract="Passez rapidement en revue certaines des mesures de haut niveau ainsi que le mouvement vers et depuis une page spécifique."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_pagesummary_panel"
>title="Panneau Synthèse de la page"
>abstract="Passez rapidement en revue certaines des mesures de haut niveau ainsi que le mouvement vers et depuis une page spécifique.<br/><br/>**Paramètres &#x200B;**<br/>**Ajouter un élément de dimension de page** : ouvrez le rail du composant, recherchez la dimension Page et développez-la en cliquant sur la carotte pour afficher les éléments de dimension. Ensuite, faites glisser et déposez la page spécifique que vous souhaitez découvrir dans le créateur. Une fois que vous avez fait glisser et déposé l’élément de dimension, le rapport est automatiquement renseigné avec des informations clés sur la page."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_Cet article présente le panneau Synthèse de la page dans_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _&#x200B;**Adobe Analytics**._<br/>_Il n’existe pas de panneau équivalent dans_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _&#x200B;**Customer Journey Analytics**._

>[!ENDSHADEBOX]

Un panneau **[!UICONTROL Synthèse de la page]** vous permet d’explorer les statistiques clés concernant des pages spécifiques.

## Utilisation

Pour utiliser un panneau **[!UICONTROL Synthèse de la page]**, procédez comme suit :

1. Créez un panneau **[!UICONTROL Synthèsede la page]**. Pour plus d’informations sur la création d’un panneau, consultez [Créer un panneau](panels.md#create-a-panel).

1. Spécifiez l’[entrée](#panel-input) du panneau.

1. Observez la [sortie](#panel-output) du panneau.



Vous pouvez accéder au panneau depuis [!UICONTROL Rapports] ou dans [!UICONTROL Workspace].

| Point d’accès | Description |
| --- | --- |
| [!UICONTROL Rapports] | <ul><li>Le panneau est déjà déposé dans un projet.</li><li>Le rail de gauche est réduit.</li><li>Seule la dimension Page est prise en charge.</li><li>Un paramètre par défaut a déjà été appliqué, dans ce cas, la page la plus visitée pour la dimension [!UICONTROL Page]. Vous pouvez modifier ce paramètre.</li></ul> |
| Workspace | Créez un projet et sélectionnez l’icône Panneau dans le rail de gauche. Faites glisser le panneau [!UICONTROL Synthèse de la page] au-dessus du tableau à structure libre. Notez que le champ [!UICONTROL Élément de dimension] Page reste vide. Sélectionnez une dimension dans la liste déroulante. |

### Entrée du panneau {#panel-input}

Vous pouvez configurer le panneau [!UICONTROL Synthèse de la page] à l’aide des paramètres d’entrée suivants :

![Résumé des entrées de page](assets/page-summary-input.png)

| Entrée | Description |
| --- | --- |
| **[!UICONTROL Page]** | Sélectionnez une dimension de page pour laquelle vous souhaitez explorer les statistiques clés. Par exemple, **[!UICONTROL accueil]** pour explorer les statistiques de la page d’accueil. Utilisez le menu déroulant pour sélectionner une page ou commencez à saisir (par exemple, `home`) pour rechercher rapidement des pages. |

{style="table-layout:auto"}


Sélectionnez **[!UICONTROL Créer]** pour créer le panneau.

### Sortie du panneau {#panel-output}

Le panneau [!UICONTROL Synthèse de la page] renvoie un riche ensemble de données de mesures et de visualisations pour vous aider à mieux comprendre les statistiques sur des pages spécifiques.

![Panneau Synthèse de la page](assets/page-summary-output.png)

| Visualisation | Description |
| --- | --- |
| **[!UICONTROL Pages vues] - Mois en cours (jusqu’à présent)** | Visualisation [Synthèse des chiffres](/help/analyze/analysis-workspace/visualizations/summary-number-change.md) qui affiche le nombre de pages vues pour cette page pour le mois en cours. |
| **[!UICONTROL Pages vues] - 4 semaines avant** | Visualisation [Synthèse des chiffres](/help/analyze/analysis-workspace/visualizations/summary-number-change.md) qui affiche le nombre de pages vues pour cette page au cours du dernier mois. |
| **[!UICONTROL Pages vues] - 52 semaines avant** | Visualisation [Synthèse des chiffres](/help/analyze/analysis-workspace/visualizations/summary-number-change.md) qui indique le nombre de pages vues pour cette page au cours de l’année écoulée. |
| **[!UICONTROL Tendance]** | Visualisation [en courbes](/help/analyze/analysis-workspace/visualizations/line.md) des tendances des pages vues pour ce mois-ci, 4 semaines avant et 52 semaines avant. |
| **[!UICONTROL Pourcentage de toutes les pages vues]** | Synthèse des chiffres du pourcentage de toutes les pages vues qui ont été sur cette page. |
| **[!UICONTROL Durée de consultation de la page]** | Visualisation [Barres horizontales](/help/analyze/analysis-workspace/visualizations/horizontal-bar.md) qui affiche le temps passé sur cette page. |
| **[!UICONTROL Visites sur une seule page]** | [Synthèse des chiffres](/help/analyze/analysis-workspace/visualizations/summary-number-change.md) qui indique le nombre de pages vues où cette page a été la seule page visitée. |
| **[!UICONTROL Actualisations]** | [Synthèse des chiffres](/help/analyze/analysis-workspace/visualizations/summary-number-change.md) qui indique le nombre de fois où un élément de dimension était présent au cours d’une actualisation. Une personne rafraîchissant son navigateur est la méthode la plus courante pour déclencher une actualisation. |
| **[!UICONTROL Entrées]** | [Synthèse des chiffres](/help/analyze/analysis-workspace/visualizations/summary-number-change.md) qui indique le nombre de fois où un élément de dimension donné est capturé comme première valeur d’une visite. |
| **[!UICONTROL Sorties]** | [Synthèse des chiffres](/help/analyze/analysis-workspace/visualizations/summary-number-change.md) qui indique le nombre de fois qu’un élément de dimension donné est capturé comme dernière valeur d’une visite. |
| **[!UICONTROL Flux]** | Visualisation [Flux](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) avec la page sélectionnée comme point focal. Vous pouvez explorer davantage les données, comme dans n’importe quelle visualisation [Flux](/help/analyze/analysis-workspace/visualizations/c-flow/create-flow.md). |

{style="table-layout:auto"}

Utilisez ![Modifier](/help/assets/icons/Edit.svg) pour reconfigurer et recréer le panneau.
