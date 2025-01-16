---
description: Le panneau Résumé de la page affiche un résumé des informations d’une page de votre choix.
title: Panneau Résumé de la page
feature: Panels
role: User, Admin
exl-id: f0b7cd92-17b2-452d-9aab-f78629360ab8
source-git-commit: 33fdd685de21736964d0cbfbc479794a9154e8a3
workflow-type: tm+mt
source-wordcount: '547'
ht-degree: 8%

---

# Panneau Résumé de la page {#page-summary}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_pagesummary_button"
>title="Résumé de la page"
>abstract="Passez rapidement en revue certaines des mesures de haut niveau ainsi que le mouvement vers et depuis une page spécifique."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_pagesummary_panel"
>title="Panneau Résumé de la page"
>abstract="Passez rapidement en revue certaines des mesures de haut niveau ainsi que le mouvement vers et depuis une page spécifique.<br/><br/>**Paramètres **<br/>**Ajouter un élément de dimension de page** : ouvrez le rail du composant, recherchez la dimension Page et développez-la en cliquant sur la carotte pour afficher les éléments de dimension. Ensuite, faites glisser et déposez la page spécifique que vous souhaitez découvrir dans le créateur. Une fois que vous avez fait un glisser-déposer de l’élément de dimension, le rapport est automatiquement renseigné avec des informations clés sur la page."

<!-- markdownlint-enable MD034 -->


Ce panneau vous permet d’explorer facilement les statistiques clés concernant des pages spécifiques.

## Accès au panneau

Vous pouvez accéder au panneau depuis [!UICONTROL Reports] ou dans [!UICONTROL Workspace].

| Point d&#39;accès | Description |
| --- | --- |
| [!UICONTROL Rapports] | <ul><li>Le panneau est déjà déposé dans un projet.</li><li>Le rail de gauche est réduit.</li><li>Seule la dimension Page est prise en charge.</li><li>Un paramètre par défaut a déjà été appliqué, dans ce cas, la page la plus visitée pour la dimension [!UICONTROL Page]. Vous pouvez modifier ce paramètre.</li></ul> |
| Workspace | Créez un projet et sélectionnez l’icône Panneau dans le rail de gauche. Faites glisser le panneau [!UICONTROL Résumé de la page] au-dessus du tableau à structure libre. Notez que le champ [!UICONTROL Élément de Dimension ] de la page n&#39;est pas renseigné. Sélectionnez un élément de dimension dans la liste déroulante. |

## Entrées de panneau {#Input}

Vous pouvez configurer le panneau [!UICONTROL Résumé de la page] à l’aide des paramètres de saisie suivants :

| Paramètre | Description |
| --- | --- |
| Zone de dépôt des segments (ou autres composants) | Vous pouvez faire glisser et déposer des segments ou d’autres composants pour filtrer davantage les résultats de votre panneau. |
| Élément de dimension de page | Dans la liste déroulante, sélectionnez l’élément de dimension Page dont vous souhaitez explorer les statistiques clés. |

{style="table-layout:auto"}

Cliquez sur **[!UICONTROL Créer]** pour créer le panneau.

## Sortie du panneau {#output}

Le panneau [!UICONTROL Résumé de la page] renvoie un riche ensemble de données de mesures et de visualisations pour vous aider à mieux comprendre les statistiques sur des pages spécifiques.

| Mesure/Visualisation | Description |
| --- | --- |
| [!UICONTROL Pages vues] - Mois en cours, jusqu’à présent | Nombre de pages vues pour cette page pour le mois en cours. |
| [!UICONTROL Pages vues] - 4 semaines avant | Nombre de pages vues pour cette page au cours du dernier mois. |
| [!UICONTROL Pages vues] - 52 semaines précédentes | Nombre de pages vues pour cette page au cours de l’année dernière. |
| [!UICONTROL Tendance] | Graphique de tendances des pages vues pour le mois en cours, les 4 semaines précédentes et les 52 semaines précédentes. |
| [!UICONTROL Pourcentage de toutes les pages vues] | Synthèse des chiffres du pourcentage de toutes les pages vues qui ont été envoyées à cette page. |
| [!UICONTROL Durée de consultation de la page] | Graphique à barres horizontales répertoriant le temps passé sur cette page. |
| [!UICONTROL Visites de page unique] | Synthèse des chiffres répertoriant le nombre de pages vues pour lesquelles il s’agissait de la seule page visitée. |
| [!UICONTROL Actualisations] | La mesure [!UICONTROL Rechargements] indique le nombre de fois où un élément de dimension était présent lors d’un rechargement. Un visiteur actualisant son navigateur est la méthode la plus courante pour déclencher une actualisation. |
| [!UICONTROL Entrées] | La mesure [!UICONTROL Entrées] indique le nombre de fois où un élément de dimension donné est capturé comme première valeur d’une visite. |
| [!UICONTROL Sorties] | La mesure [!UICONTROL Sorties] indique le nombre de fois où un élément de dimension donné est capturé comme dernière valeur d’une visite. |
| [!UICONTROL Flux] | Diagramme de flux avec la page sélectionnée comme point focal. Vous pouvez explorer davantage les données, comme dans n’importe quel [diagramme de flux](/help/analyze/analysis-workspace/visualizations/c-flow/create-flow.md). |

{style="table-layout:auto"}

![Panneau Résumé de la page](assets/page-sum1.png)

![Mesures et flux](assets/page-sum2.png)
