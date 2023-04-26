---
description: Un panneau est un ensemble de tableaux et de visualisations
title: Panneaux - Aperçu
feature: Panels
role: User, Admin
exl-id: dd1a3c40-8b5b-47dd-86d9-da766575ee46
source-git-commit: 017559d2b909deb4bf87fb5fe41db8250f2ca2ac
workflow-type: tm+mt
source-wordcount: '1202'
ht-degree: 68%

---

# Panneaux - Aperçu

Un [!UICONTROL panneau] est un ensemble de tableaux et de visualisations. Vous pouvez accéder aux panneaux à partir de l’icône supérieure gauche dans Workspace ou d’un [panneau vierge](blank-panel.md). Les panneaux sont utiles pour organiser vos projets en fonction des périodes, des suites de rapports ou des cas d’utilisation d’analyses.

## Types de panneaux

Voici les types de panneau disponibles dans Analysis Workspace :

| Nom du panneau | Description |
| --- | --- |
| [Panneau vierge](blank-panel.md) | Faites votre choix parmi les panneaux et visualisations disponibles pour démarrer votre analyse. |
| [Panneau Quick Insights](quickinsight.md) | Construisez rapidement un tableau de forme libre et une visualisation d’accompagnement afin d’analyser et de découvrir des informations plus rapidement. |
| [Panneau Analytics for Target](a4t-panel.md) | Analysez les activités et les expériences Target dans Analysis Workspace. |
| [Panneau d’attribution](attribution.md) | Comparez et visualisez rapidement de nombreux modèles d’attribution en utilisant n’importe quelle dimension ou mesure de conversion. |
| [Panneau à structure libre](freeform-panel.md) | Effectuez des comparaisons et des ventilations illimitées, puis ajoutez des visualisations pour raconter une histoire riche en données. |
| [Panneau de lʼaudience moyenne par minute de média](average-minute-audience-panel.md) | Analysez lʼaudience moyenne par minute dans le temps, affichez des informations sur les pics dʼaudience, avec la possibilité de les ventiler et de les comparer. |
| [Panneau Observateurs simultanés de médias](media-concurrent-viewers.md) | Analysez les visionneuses au fil du temps, avec des informations sur la simultanéité la plus élevée, et sur la capacité à ventiler et à comparer. |
| [Panneau Temps de lecture de média](media-playback-timespent/media-playback-time-spent.md) | Analysez les visionneuses au fil du temps, avec des informations sur la simultanéité la plus élevée, et sur la capacité à ventiler et à comparer. |
| [Panneau de comparaison des segments](c-segment-comparison/segment-comparison.md) | Comparez rapidement deux segments sur tous les points de données afin de rechercher automatiquement les différences pertinentes. |

![](assets/panel-overview.png)

Les panneaux [!UICONTROL Quick Insights], [!UICONTROL vierges] et [!UICONTROL à structure libre] sont idéaux pour commencer votre analyse, tandis que les panneaux [!UICONTROL Analytics for Target], [!UICONTROL Attribution IQ], celui des [!UICONTROL observateurs simultanés de médias] et celui de [!UICONTROL comparaison des segments] se prêtent à des analyses plus avancées. Un bouton `"+"` est disponible dans les projets afin que vous puissiez ajouter des panneaux vierges à tout moment.

Le panneau de démarrage par défaut est le panneau [!UICONTROL à structure libre], mais vous pouvez également choisir d’utiliser le [panneau vierge](/help/analyze/analysis-workspace/c-panels/blank-panel.md) par défaut.

## Suite de rapports {#report-suite}

Les tableaux et les visualisations au sein d’un panneau obtiennent des données de la [!UICONTROL suite de rapports] sélectionnée en haut à droite du panneau. La suite de rapports détermine également les composants disponibles dans le rail de gauche. Dans un projet, vous pouvez utiliser une ou [plusieurs suites de rapports](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/multiple-report-suites.html?lang=fr) selon les cas pratiques de votre analyse. Pour appliquer une suite de rapports unique à tous les panneaux d’un projet, **faites un clic droit sur l’en-tête du panneau > Application de suites de rapports à tous les panneaux**.

La liste des suites de rapports est triée en fonction de la pertinence. Adobe définit cette dernière selon le caractère récent et la fréquence d’utilisation de la suite par l’utilisateur, ainsi que selon sa fréquence d’utilisation au sein de l’organisation.

![](assets/panel-report-suite.png)

## Calendrier {#calendar}

Le calendrier du panneau contrôle la plage de compte-rendu des performances des tableaux et des visualisations dans un panneau.

>[!NOTE]
>Si un composant de période (violet) est utilisé dans un tableau, une visualisation ou une zone de dépôt de panneau, il remplace le calendrier du panneau.

![](assets/panel-calendar.png)

Vous pouvez appliquer une période au niveau de la minute dans les paramètres avancés du calendrier du panneau. Si vous créez des rapports sur une période qui sʼétale sur plusieurs jours, lʼheure de début sʼapplique au premier jour et lʼheure de fin au dernier jour de celle-ci.

## Zone de dépôt {#dropzone}

La zone de dépôt des panneaux vous permet d’appliquer des filtres de segments et de menus déroulants à tous les tableaux et visualisations d’un panneau. Vous pouvez appliquer un ou plusieurs filtres à un panneau. Le titre au-dessus de chaque filtre peut être modifié en cliquant sur le crayon de modification. Vous pouvez également faire un clic droit pour le supprimer complètement.

### Filtres de segments

Faites glisser et déposez un segment du rail de gauche dans la zone de dépôt du panneau pour commencer à filtrer le panneau.

![Filtrer](/help/admin/admin/assets/filter.png)

### Filtres de segments ad hoc

Vous pouvez également faire glisser des composants qui ne sont pas des segments directement dans la zone de dépôt pour créer des segments ad hoc, ce qui vous permet de gagner du temps et vous évite de passer par le créateur de segments. Les segments ainsi créés sont automatiquement définis comme des segments de niveau accès. Vous pouvez modifier cette définition en cliquant sur l’icône d’informations (i) à côté du segment, puis sur l’icône de modification en forme de crayon, et la modifier dans le créateur de segments.

Les segments ad hoc sont un type de segment rapide et sont locaux au projet. Elles ne s’affichent pas dans le rail de gauche à moins que vous ne les rendiez publiques.

Pour plus d’informations, voir [Segments rapides](/help/analyze/analysis-workspace/components/segments/quick-segments.md).

### Filtres déroulants statiques

Les filtres déroulants permettent d&#39;interagir avec les données de manière contrôlée. Par exemple, vous pouvez ajouter un filtre de menu déroulant pour les types d’équipement mobile afin de segmenter le panneau par tablette, téléphone mobile ou bureau.

Les filtres de menu déroulant peuvent également servir à fusionner plusieurs projets. Par exemple, si vous avez plusieurs versions d’un même projet avec des segments Pays différents, vous pouvez les fusionner en un seul projet et ajouter un filtre de menu déroulant Pays.

![](assets/dropdown-filter-intro.png)

Pour créer un filtre de liste déroulante statique :

* Pour les filtres déroulants utilisant des éléments de dimension, cliquez sur l’icône de flèche vers la droite située en regard de la dimension souhaitée dans le rail de gauche. Cette action expose tous les éléments de dimension disponibles. Sélectionnez plusieurs éléments de dimension de cette liste à l’aide de la case `[Shift + Click]` ou `[Ctrl + Click]`, puis déposez-les dans la zone de dépôt du panneau **pendant la conservation`[Shift]`**.
* Pour les filtres déroulants utilisant d’autres composants tels que des mesures, des segments ou des périodes, sélectionnez plusieurs composants à l’aide de la fonction `[Shift + Click]` ou `[Ctrl + Click]`. Déposez la sélection dans la zone de dépôt du panneau. **pendant la conservation`[Shift]`**. Tous les types de composants sont traités comme des segments dans ce contexte.
* Un filtre déroulant unique ne peut contenir qu’un seul type de composant. Si vous incluez plusieurs types de composants dans votre sélection, un filtre déroulant distinct est créé par type de composant. Par exemple, si vous incluez des mesures et des éléments de dimension dans votre sélection, deux filtres déroulants distincts sont créés. Un filtre de menu déroulant comprend des éléments de dimension, tandis que l’autre inclut des mesures.

Sélectionnez l’une des options de la liste déroulante pour modifier les données du panneau. Vous pouvez également choisir de ne pas filtrer les données du panneau en sélectionnant **[!UICONTROL Aucun filtre]**.

![](assets/create-dropdown.png)

Le fait de cliquer avec le bouton droit de la souris sur un filtre déroulant propose les options suivantes :

* **[!UICONTROL Ajouter une étiquette]**: Lorsque vous ajoutez un filtre déroulant à un projet, un libellé est automatiquement défini sur le nom du composant. Si vous supprimez le libellé, vous pouvez l’ajouter à nouveau avec cette option.
* **[!UICONTROL Supprimer le libellé]**: Supprimez le texte au-dessus d’un filtre déroulant.
* **[!UICONTROL Supprimer le filtre déroulant]**: Supprime le filtre de liste déroulante du panneau.

[Regardez la vidéo](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/using-panels/using-panels-to-organize-your-analysis-workspace-projects.html?lang=fr) pour en savoir plus sur l’ajout de filtres de menu déroulant à votre projet.

<!--### Dynamic drop-down filters

Dynamic drop-down filters allow you to determine available values based on data within the panel's reporting range and values in other drop-down filters. For example, you can create two dynamic drop-downs using the [Countries](/help/components/dimensions/countries.md) dimension and [Cities](/help/components/dimensions/cities.md) dimension. When you select a country from the [!UICONTROL Countries] drop-down list, the [!UICONTROL Cities] drop-down list dynamically adjusts to only show cities within that country.

This same concept applies to all dimensions; only dimension items that appear within the panel's date range and selected filters are visible. Dimension items selected in static drop-down filters affect available values in dynamic drop-down filters. However, the inverse is not true; Dimension items selected in dynamic drop-down filters do not affect available values in static drop-down filters.

Manual selection of dimension items is available if you anticipate a certain dimension item to be collected in the future. You can also clear a dynamic drop-down filter so that it does not contain a value, allowing other dynamic drop-down filters to contain more values. Select **[!UICONTROL Clear All]** to clear the selection from all drop-down filters for that panel.

To create a dynamic drop-down filter:

* Drag and drop a single dimension into the panel dropzone **while holding `[Shift]`**.
* Dynamic drop-down filters are not available for metrics, segments, or date ranges.
* Right-click a drop-down filter and select **[!UICONTROL Delete filter]** to delete it.

Right-clicking a dynamic drop-down filter provides the same options as static drop-down filters.-->

## Menu contextuel {#right-click}

Pour accéder à d’autres fonctionnalités d’un panneau, faites un clic droit sur l’en-tête du panneau.

![Menu contextuel](assets/right-click-menu.png)

Les paramètres suivants sont disponibles :

| Paramètre | Description |
| --- | --- |
| Insérer la copie du panneau/de la visualisation | Permet de coller (&quot;insérer&quot;) un panneau ou une visualisation copié à un autre emplacement du projet ou dans un autre projet. |
| Copier le panneau | Permet de cliquer avec le bouton droit de la souris et de copier un panneau, de sorte que vous puissiez l’insérer à un autre emplacement du projet ou dans un autre projet. |
| Application de suites de rapports à tous les panneaux | Vous permet d’appliquer la suite de rapports active à tous les panneaux du projet. |
| Dupliquer le panneau | Crée un double exact du panneau actuel, que vous pouvez ensuite modifier. |
| Réduire/Développer tous les panneaux | Réduit et développe tous les panneaux du projet. |
| Réduire/Développer toutes les visualisations dans le panneau | Réduit et développe toutes les visualisations du panneau actif. |
| Modifier la description | Ajouter (ou modifier) une description textuelle du panneau. |
| Obtenir un lien vers le panneau | Permet de renvoyer un utilisateur vers un panneau spécifique dans un projet. Lorsque l’utilisateur clique sur le lien, le destinataire doit se connecter avant d’être dirigé vers le panneau exact auquel il est lié. |
