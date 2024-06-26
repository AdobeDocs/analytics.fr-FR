---
description: Un panneau est un ensemble de tableaux et de visualisations
title: Panneaux - Aperçu
feature: Panels
role: User, Admin
exl-id: dd1a3c40-8b5b-47dd-86d9-da766575ee46
source-git-commit: aacba26d0eb612146a9e0bf6386f9e755a9e8f07
workflow-type: tm+mt
source-wordcount: '1582'
ht-degree: 51%

---

# Panneaux - Aperçu

Un [!UICONTROL panneau] est un ensemble de tableaux et de visualisations. Vous pouvez accéder aux panneaux à partir de l’icône située en haut à gauche dans Workspace ou à partir d’un [panneau vierge](blank-panel.md). Les panneaux sont utiles pour organiser vos projets en fonction des périodes, des suites de rapports ou des cas d’utilisation d’analyses.

## Types de panneaux

Voici les types de panneau disponibles dans Analysis Workspace :

| Nom du panneau | Description |
| --- | --- |
| [Panneau vierge](blank-panel.md) | Faites votre choix parmi les panneaux et visualisations disponibles pour démarrer votre analyse. |
| [Panneau Quick Insights](quickinsight.md) | Construisez rapidement un tableau de forme libre et une visualisation d’accompagnement afin d’analyser et de découvrir des informations plus rapidement. |
| [Panneau Analytics for Target](a4t-panel.md) | Analysez les activités et les expériences Target dans Analysis Workspace. |
| [Panneau d’attribution](attribution.md) | Comparez et visualisez rapidement de nombreux modèles d’attribution en utilisant n’importe quelle dimension ou mesure de conversion. |
| [Panneau à structure libre](freeform-panel.md) | Effectuez des comparaisons et des répartitions illimitées, puis ajoutez des visualisations pour raconter une histoire riche en données. |
| [Panneau de lʼaudience moyenne par minute de média](average-minute-audience-panel.md) | Analysez lʼaudience moyenne par minute dans le temps, affichez des informations sur les pics dʼaudience, avec la possibilité de les ventiler et de les comparer. |
| [Panneau Observateurs simultanés de médias](media-concurrent-viewers.md) | Analysez les visionneuses au fil du temps, avec des informations sur la simultanéité la plus élevée, et sur la capacité à ventiler et à comparer. |
| [Panneau Temps de lecture de média](/help/analyze/analysis-workspace/c-panels/media-playback-time-spent.md) | Analysez les visionneuses au fil du temps, avec des informations sur la simultanéité la plus élevée, et sur la capacité à ventiler et à comparer. |
| [Panneau de comparaison des segments](c-segment-comparison/segment-comparison.md) | Comparez rapidement deux segments sur tous les points de données afin de rechercher automatiquement les différences pertinentes. |

![](assets/panel-overview.png)

[!UICONTROL Aperçu rapide], [!UICONTROL Vide] et [!UICONTROL Structure libre] Les panneaux constituent un excellent point de départ pour votre analyse. [!UICONTROL Analytics pour Target], [!UICONTROL Attribution], [!UICONTROL Visionneuses simultanées de médias] et [!UICONTROL Comparaison de segments] se prêtent à des analyses plus avancées. Un bouton `"+"` est disponible dans les projets afin que vous puissiez ajouter des panneaux vierges à tout moment.

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

La zone de dépôt des panneaux vous permet d’appliquer des filtres de segments et de menus déroulants à tous les tableaux et visualisations d’un panneau. Vous pouvez appliquer un ou plusieurs filtres à un panneau.

### Filtres de segments

Faites glisser les segments du rail de gauche vers la zone de dépôt du panneau pour commencer à filtrer le panneau. Répétez cette procédure pour ajouter des filtres supplémentaires au panneau. Les filtres s’affichent côte à côte en haut du panneau.

![Filtrer](assets/segment-filter.png)

### Filtres de segments ad hoc

Vous pouvez également faire glisser des composants qui ne sont pas des segments directement dans la zone de dépôt pour créer des segments ad hoc, ce qui vous permet de gagner du temps et vous évite de passer par le créateur de segments. Les segments ainsi créés sont automatiquement définis comme des segments de niveau accès. Vous pouvez modifier cette définition en cliquant sur l’icône d’informations (i) à côté du segment, puis sur l’icône de modification en forme de crayon, et la modifier dans le créateur de segments.

Les segments ad hoc sont un type de segment rapide et sont locaux au projet. Ils ne s’affichent pas dans le rail de gauche à moins que vous ne les rendiez publics.

Pour en savoir plus, voir [Segments rapides](/help/analyze/analysis-workspace/components/segments/quick-segments.md).

### Segments de liste déroulante statiques

Les segments déroulants statiques vous permettent d’interagir avec les données de manière contrôlée. Vous pouvez, par exemple, ajouter un segment déroulant pour les types d’appareils mobiles afin de segmenter le panneau par tablette, téléphone mobile ou bureau.

Les segments de liste déroulante statiques peuvent également être utilisés pour consolider de nombreux projets en un seul. Par exemple, si vous avez plusieurs versions d’un même projet avec des segments Pays différents appliqués, vous pouvez consolider toutes les versions en un seul projet et ajouter un segment déroulant Pays .

![](assets/dropdown-filter-intro.png)

#### Création de segments de liste déroulante statiques

* Pour les segments de liste déroulante utilisant des éléments de dimension, sélectionnez une seule dimension dans le rail de gauche et déposez-la dans la zone de dépôt du panneau. **pendant la conservation`[Shift]`**. Cela crée un segment déroulant avec tous les éléments de dimension associés à cette dimension.

  Ou, si vous souhaitez que le segment déroulant n’inclut que des éléments de dimension spécifiques associés à une dimension, cliquez sur l’icône de flèche vers la droite en regard de la dimension souhaitée dans le rail de gauche. Cette action affiche tous les éléments de dimension disponibles. Sélectionnez plusieurs éléments de dimension de cette liste à l’aide de la case `[Shift + Click]` ou `[Ctrl + Click]`, puis déposez-les dans la zone de dépôt du panneau **pendant la conservation** `[Shift]`.

* Pour les segments de liste déroulante utilisant un seul type de composant (par exemple, seules les dimensions, ou seuls les segments, ou uniquement les mesures), sélectionnez plusieurs éléments du même type dans le rail de gauche à l’aide de `[Shift + Click]` ou `[Ctrl + Click]`, puis déposez-les dans la zone de dépôt du panneau **pendant la conservation`[Shift]`**.

  Un segment déroulant unique est créé avec les composants que vous avez sélectionnés.

* Pour les segments de liste déroulante utilisant un mélange de types de composants (par exemple, 2 mesures et 3 filtres), sélectionnez plusieurs composants à l’aide de `[Shift + Click]` ou `[Ctrl + Click]`. Déposez la sélection dans la zone de dépôt du panneau **tout en maintenant la touche`[Shift]`** enfoncée. Dans ce contexte, tous les types de composants sont traités comme des segments déroulants distincts. Par exemple, si vous incluez à la fois des mesures et des éléments de dimension dans votre sélection, deux segments de liste déroulante distincts sont créés : un segment de liste déroulante inclut des éléments de dimension et l’autre inclut des mesures.

  ![Fenêtre Panneau avec le champ Segment de client mobile disponible pour déposer un segment déroulant statique. ](assets/create-dropdown.png)

Le fait de cliquer avec le bouton droit de la souris sur un segment déroulant offre les options suivantes :

* **[!UICONTROL Menu déroulant Supprimer]**: supprime le segment déroulant du panneau.
* **[!UICONTROL Supprimer le libellé]**: supprimez le texte au-dessus d’un segment déroulant. Pour modifier le libellé, sélectionnez l&#39;icône représentant un crayon.
* **[!UICONTROL Ajouter une étiquette]**: lorsque vous ajoutez un segment déroulant à un projet, un libellé est automatiquement défini sur le nom du composant. Si vous supprimez le libellé, vous pouvez l’ajouter à nouveau avec cette option.
* **[!UICONTROL Sélection requise]**: nécessite qu’un segment soit défini sur le panneau.

[Regardez la vidéo](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/using-panels/using-panels-to-organize-your-analysis-workspace-projects.html?lang=fr) pour en savoir plus sur l’ajout de filtres de menu déroulant à votre projet.

#### Utilisation de segments de liste déroulante statiques

Pour filtrer le panneau, utilisez le menu de segments déroulants de l’une des façons suivantes :

* Appliquez un seul segment au panneau en le sélectionnant dans le menu déroulant.

* Appliquez plusieurs segments au panneau en sélectionnant plusieurs segments dans le menu déroulant. Le panneau est filtré pour inclure l’un des segments sélectionnés.

  Pour supprimer un segment de la liste, sélectionnez-le à nouveau dans le menu déroulant.

  ![Sélection de plusieurs segments](assets/dropdown-filter-multiselect.png)

### Segments de liste déroulante dynamiques

Les segments de liste déroulante dynamiques vous permettent de déterminer les valeurs disponibles en fonction des données de la plage de rapports du panneau et les valeurs d’autres segments de liste déroulante. Par exemple, vous pouvez créer deux listes déroulantes dynamiques à l’aide de la variable [Pays](/help/components/dimensions/countries.md) dimension et [Villes](/help/components/dimensions/cities.md) dimension. Lorsque vous sélectionnez un pays dans le [!UICONTROL Pays] liste déroulante, la variable [!UICONTROL Villes] La liste déroulante s’ajuste dynamiquement pour afficher uniquement les villes de ce pays.

Ce même concept s’applique à toutes les dimensions. Seuls les éléments de dimension qui apparaissent dans la période du panneau et les segments sélectionnés sont visibles. Les éléments de Dimension sélectionnés dans les segments déroulants statiques affectent les valeurs disponibles dans les segments déroulants dynamiques. Cependant, l’inverse n’est pas vrai ; les éléments de Dimension sélectionnés dans les segments de liste déroulante dynamiques n’affectent pas les valeurs disponibles dans les segments de liste déroulante statiques.

La sélection manuelle d’éléments de dimension est possible si vous prévoyez qu’un élément de dimension donné sera collecté ultérieurement. Vous pouvez également effacer un segment de liste déroulante dynamique afin qu’il ne contienne aucune valeur, ce qui permet à d’autres segments de liste déroulante dynamique de contenir plus de valeurs. Sélectionner **[!UICONTROL Réinitialiser tout]** pour effacer la sélection de tous les segments déroulants de ce panneau.

Pour créer un segment de liste déroulante dynamique :

* Faites glisser et déposez une seule dimension dans la zone de dépôt du panneau **tout en maintenant la touche`[Shift]`** enfoncée.
* Les segments de liste déroulante dynamiques ne sont pas disponibles pour les mesures, les segments ou les périodes.
* Cliquez avec le bouton droit de la souris sur un segment déroulant et sélectionnez **[!UICONTROL Menu déroulant Supprimer]** pour le supprimer.

Un clic droit sur un filtre déroulant dynamique permet d’obtenir les mêmes options que les filtres déroulants statiques.

## Menu contextuel {#right-click}

Pour accéder à d’autres fonctionnalités d’un panneau, faites un clic droit sur l’en-tête du panneau.

![Menu contextuel](assets/right-click-menu.png)

Les paramètres suivants sont disponibles :

| Paramètre | Description |
| --- | --- |
| Insérer la copie du panneau/de la visualisation | Permet de coller (« insérer ») la copie d’un panneau ou d’une visualisation à un autre emplacement au sein du projet, ou dans un tout autre projet. |
| Copier le panneau | Permet de faire un clic droit et de copier un panneau de sorte que vous puissiez l’insérer à un autre emplacement au sein du projet, ou dans un tout autre projet. |
| Application de suites de rapports à tous les panneaux | Vous permet d’appliquer la suite de rapports active à tous les panneaux du projet. |
| Dupliquer le panneau | Crée un double exact du panneau actuel, que vous pouvez ensuite modifier. |
| Réduire/Développer tous les panneaux | Réduit et développe tous les panneaux du projet. |
| Réduire/Développer toutes les visualisations dans le panneau | Réduit et développe toutes les visualisations du panneau actif. |
| Modifier la description | Ajouter (ou modifier) une description textuelle du panneau. |
| Obtenir un lien vers le panneau | Permet de renvoyer un utilisateur vers un panneau spécifique dans un projet. Lorsque l’utilisateur clique sur le lien, le destinataire doit se connecter avant d’être dirigé vers le panneau exact auquel il est lié. |
