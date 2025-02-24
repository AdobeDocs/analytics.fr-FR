---
description: Le créateur de mesures calculées fournit un canevas où faire glisser et déposer des dimensions, des mesures, des segments et des fonctions permettant de créer des mesures personnalisées en fonction de la logique de hiérarchie des conteneurs, des règles et des opérateurs. Grâce à cet outil de développement intégré, vous pouvez créer et enregistrer des mesures calculées simples ou des mesures calculées avancées complexes.
title: Création de mesures
feature: Calculated Metrics
exl-id: 12bb3734-e25d-4c67-8c62-e1226d9aef94
source-git-commit: a1567366c9fad42b3836f43c681d5380e97b09f3
workflow-type: tm+mt
source-wordcount: '1150'
ht-degree: 43%

---

# Création de mesures {#build-metrics}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_productcompatibility"
>title="Compatibilité des produits"
>abstract="Indique l’endroit où cette mesure calculée peut être utilisée dans Customer Journey Analytics, par exemple dans Analysis Workspace, Report Builder, etc. Certaines mesures calculées ne peuvent pas être utilisées avec l’expérimentation."
>additional-url="https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-workspace/panels/experimentation#use-in-experimentation" text="Utiliser les mesures calculées dans l’expérimentation"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_externalid"
>title="ID externe"
>abstract="La modification de l’ID externe peut avoir une incidence sur la manière dont la mesure calculée apparaît dans des sources externes, telles que les outils de Business Intelligence."

<!-- markdownlint-enable MD034 -->

Adobe Analytics fournit une zone de travail dans laquelle faire glisser et déposer des dimensions, des mesures, des segments et des fonctions permettant de créer des mesures personnalisées en fonction de la logique de hiérarchie des conteneurs, des règles et des opérateurs. Grâce à cet outil de développement intégré, vous pouvez créer et enregistrer des mesures calculées simples ou complexes.

## Commencer à créer une mesure calculée

Vous pouvez utiliser le créateur de mesures calculées pour créer ou modifier des mesures calculées. Une fois créées de cette manière, les mesures calculées sont disponibles dans la liste des composants et peuvent ensuite être utilisées dans les projets de l’ensemble de votre organisation. Vous pouvez également créer rapidement une mesure calculée qui n’est disponible que pour le projet dans lequel elle a été créée, comme décrit dans la section [Création de mesures calculées pour un seul projet](/help/analyze/analysis-workspace/components/apply-create-metrics.md#create-calculated-metrics-for-a-single-project) dans [Mesures](/help/analyze/analysis-workspace/components/apply-create-metrics.md).

Accédez au créateur de mesures calculées pour commencer à créer une mesure calculée disponible dans la liste des composants.

1. Accédez au créateur de mesures calculées de l’une des manières suivantes :

   * Dans Analysis Workspace, ouvrez un projet, puis sélectionnez **[!UICONTROL Composants]** > **[!UICONTROL Créer une mesure]**.
   * Dans Analysis Workspace, ouvrez un projet, puis sélectionnez l’icône **Plus** en regard de la section [!UICONTROL **Mesures**] dans le rail de gauche.
   * Dans [!DNL Adobe Analytics], accédez à **[!UICONTROL Composants]** > **[!UICONTROL Mesures calculées]**, puis sélectionnez **[!UICONTROL + Ajouter]** en haut de la page Mesures calculées.

1. Continuez avec [Zones du créateur de mesures calculées](#areas-of-the-calculated-metrics-builder).

## Zones du créateur de Mesures calculées

L’image suivante et le tableau qui l’accompagne présentent certaines des principales zones et fonctionnalités du créateur de Mesures calculées.

![](assets/cm_builder_ui.png)

| Emplacement dans l’image | Nom et fonction |
|---|---|
| 1 | **Titre :** le nom de la mesure est obligatoire. Vous ne pouvez pas enregistrer la mesure tant qu’elle ne porte pas de nom. |
| 2 | **Description :** donnez-lui une description conviviale pour montrer à quoi elle sert et pour la distinguer de mesures similaires. <p>La description apparaît également dans le rapport. Il est préférable de NE PAS mettre la formule dans la description. A la place, décrivez ce pour quoi cette mesure doit être utilisée ou ne doit pas être utilisée. (La formule est générée lorsque vous créez la mesure, sous l’en-tête Résumé. Il n’est donc pas nécessaire d’ajouter la formule à la description.) </p> |
| 3 | **Format :** les choix incluent la décimale, l’heure, le pourcentage et la devise. |
| 4 | **Nombre de décimales :** indique le nombre de décimales affichées dans le rapport. Le nombre maximal de décimales que vous pouvez spécifier est 10. |
| 5 | **Afficher la tendance à la hausse comme :** ce paramètre de polarité des mesures indique si Analytics doit considérer une tendance à la hausse de la mesure comme bonne (verte) ou mauvaise (rouge). En conséquence, le graphique du rapport s’affiche en vert ou rouge lorsque la tendance est à la hausse. |
| 6 | **Balises :** le balisage est un bon moyen d’organiser les mesures. Tous les utilisateurs peuvent créer des balises et en appliquer une ou plusieurs à un segment. Néanmoins, vous ne pouvez afficher les balises que pour les segments que vous possédez ou qui ont été partagés avec vous. Quels types de balises devriez-vous créer ? Vous trouverez ci-dessous quelques suggestions de balises utiles :<ul><li>**Noms d’équipes**, par exemple Marketing des réseaux sociaux, Marketing des appareils mobiles.</li><li>**Projets** (balises d’analyse), comme l’analyse de la page d’entrée.</li><li>**Catégories** telles que Femmes ; Géographie.</li><li>**Workflows** tels que À approuver ; Traitement pour (une unité opérationnelle spécifique)</li></ul> |
| 7 | **Résumé:** <p>La formule Résumé se met à jour chaque fois que vous apportez une modification à une définition de mesure. Cette formule s’affiche également dans le rail des mesures à gauche lorsque vous passez la souris sur une mesure et cliquez sur la Icône <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Info_18_N.svg" id="image_BDA0EAF89C19440CB02AE248BA3F968E" />. </p> |
| 8 | **Définition :** c’est là que vous faites glisser les mesures/mesures calculées, les segments et/ou les fonctions pour créer la mesure calculée. <ul><li>Si vous faites glisser une mesure calculée, elle développe automatiquement sa définition de mesure. </li> <li>Vous pouvez imbriquer des définitions dans des conteneurs. Néanmoins, à la différence des conteneurs de segments, ces conteneurs fonctionnent comme une expression mathématique et déterminent la séquence des opérations. </li> </ul> |
| 9 | **Opérateur:** divisé par ( <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Divide_18_N.svg" width="15" id="image_320D7363DE024BDEB21E44606C8B367F" width="25px" /> ) est l’opérateur par défaut, auquel s’ajoutent les opérateurs +, - et x. |
| 10 | **Aperçu :** fournit une lecture rapide de toutes les erreurs possibles. L’aperçu couvre les 90 derniers jours. C’est une manière d’évaluer initialement si vous avez sélectionné les composants appropriés à votre mesure. Un résultat inattendu signifie que vous devez vérifier à nouveau la définition de mesure. |
| 11 | **Compatibilité des produits :** la compatibilité des produits vous indique si la mesure est compatible avec <a href="https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/current-data.html?lang=fr"  >’</a> de données actuelle, avec les données entièrement traitées ou uniquement avec les rapports de canal marketing (attribution Première touche). <p>Remarque : Les données actives ne prennent pas en charge toutes les mesures. Les mesures qui comportent des segments ou des fonctions ne sont pas compatibles avec les données actives. <a href="/help/components/c-calcmetrics/cm-compatibility.md"  > Plus... </a> </p> </p> |
| 12 | **Ajouter :** pour tous les types de mesures calculées, vous pouvez ajouter des conteneurs et des nombres statiques à la définition. Pour les mesures calculées avancées, vous pouvez également ajouter des segments et des fonctions. <ul><li>Les conteneurs fonctionnent comme une expression mathématique et déterminent la séquence des opérations. De ce fait, tout ce que contient un conteneur sera traité avant l’opération suivante.</li><li>Le glissement d’un segment vers un conteneur segmente tout ce que contient ce conteneur. (Mesures calculées avancées uniquement)</li><li>Vous pouvez empiler plusieurs segments dans un conteneur.</li></ul> |
| 13 | **Icône d’engrenage (Type de mesure, Attribution) :** en sélectionnant l’icône d’engrenage en regard d’une mesure, vous pouvez spécifier le type de mesure <a href="/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md"  > et les modèles d’attribution </a>. |
| 14 | **Nouveau :** permet de créer un nouveau composant, tel qu’un nouveau segment (qui vous mène au créateur de segments <a href="/help/components/segmentation/segmentation-workflow/seg-build.md"  ></a>). |
| 15 | **Rechercher des composants :** cette barre de recherche vous permet de rechercher des dimensions, des mesures, des segments (mesures calculées avancées uniquement) et des fonctions (mesures calculées avancées uniquement). |
| 16 | **Liste des dimensions :** plutôt que de quitter le créateur de mesures calculées pour créer un segment simple (dans le créateur de segments), par exemple « Page = Page d’accueil », vous pouvez faire glisser dans Page et sélectionner Page d’accueil directement à partir du créateur de mesures calculées.<p>Le processus de création de mesures calculées segmentées est ainsi beaucoup plus rationnel.</p> |
| 17 | **Liste des mesures :** les mesures peuvent être classées en 3 catégories : <ul> <li>Mesures standard (<img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg" id="image_65A80F54D73443E78542FE0B31CC3F20" />) </li><li>Mesures calculées ( <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg" id="image_C5674AB9B9EB4DA9A56782D15822C319" />) </li><li id="li_8735E76637ED4C3F983731A66E04C93E">Modèles de mesures ( <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Folder_18_N.svg" id="image_D236601511CC4DD3828F223431E27E88" />) - au bas de la liste. </li> </ul> <p>Lorsque vous pointez sur une mesure, vous pouvez voir l’icône Infos à droite : <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Info_18_N.svg" width="15px" id="image_5A65E772A68A4B94ACAD6552CCF21F5F" />. Le fait de cliquer sur cette icône vous donne les informations suivantes : </p><ul> <li>La formule de calcul. </li><li>Une tendance d’aperçu de la mesure. </li><li>Icône Modifier (crayon) <img placement="break" align="center"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg" width="15px" id="image_7D5B2F026A034118BE4DA81B9215A883" /> en haut à droite qui vous mènera au Créateur de mesures calculées où vous pouvez modifier cette mesure calculée. </li></ul> |
| 18 | **Liste de segments :** (mesures calculées avancées uniquement) En tant qu’administrateur, cette liste affiche tous les segments créés dans votre société de connexion. Si vous êtes un utilisateur non administrateur, cette liste affiche les segments que vous possédez et ceux que vous partagez. <a href="https://experienceleague.adobe.com/docs/analytics/components/segmentation/segment-reference/seg-rights.html?lang=fr"  > Plus... </a> |
| 19 | **Liste des fonctions :** (mesures calculées avancées uniquement) Les fonctions sont divisées en deux listes : <a href="/help/components/c-calcmetrics/cm-reference/cm-functions.md"  > de base </a> (utilisée le plus souvent) et <a href="/help/components/c-calcmetrics/cm-reference/cm-adv-functions.md"  > Avancé </a>. |
| 20 | **Sélecteur de suite de rapports :** permet de passer à une autre suite de rapports. |

{style="table-layout:auto"}
