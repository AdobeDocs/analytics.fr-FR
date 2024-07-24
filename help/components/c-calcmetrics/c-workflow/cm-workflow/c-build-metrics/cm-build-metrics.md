---
description: Le créateur de mesures calculées fournit un canevas où faire glisser et déposer des dimensions, des mesures, des segments et des fonctions permettant de créer des mesures personnalisées en fonction de la logique de hiérarchie des conteneurs, des règles et des opérateurs. Grâce à cet outil de développement intégré, vous pouvez créer et enregistrer des mesures calculées simples ou des mesures calculées avancées complexes.
title: Création de mesures
feature: Calculated Metrics
exl-id: 12bb3734-e25d-4c67-8c62-e1226d9aef94
source-git-commit: f8541ac8f82e63f1664b06ed788d307c5d224ca9
workflow-type: tm+mt
source-wordcount: '1078'
ht-degree: 40%

---

# Création de mesures

Adobe Analytics fournit un canevas permettant de faire glisser et de déposer des dimensions, des mesures, des segments et des fonctions permettant de créer des mesures personnalisées en fonction de la logique de hiérarchie des conteneurs, des règles et des opérateurs. Grâce à cet outil de développement intégré, vous pouvez créer et enregistrer des mesures calculées simples ou complexes.

## Commencer à créer une mesure calculée

Vous pouvez utiliser le créateur de mesures calculées pour créer des mesures calculées. Une fois créées de cette manière, les mesures calculées sont disponibles dans la liste des composants et peuvent ensuite être utilisées dans des projets à l’échelle de votre organisation. Vous pouvez également créer une mesure calculée rapide, comme décrit dans la section [Créer des mesures calculées pour un seul projet](/help/analyze/analysis-workspace/components/apply-create-metrics.md#create-calculated-metrics-for-a-single-project) dans [Mesures](/help/analyze/analysis-workspace/components/apply-create-metrics.md).

Accédez au créateur de mesures calculées pour commencer à créer une mesure calculée disponible dans la liste des composants.

1. Accédez au créateur de mesures calculées de l’une des manières suivantes :

   * Dans Analysis Workspace, ouvrez un projet, puis sélectionnez **[!UICONTROL Composants]** > **[!UICONTROL Créer une mesure]**.
   * Dans Analysis Workspace, ouvrez un projet, puis sélectionnez l’icône **Plus** en regard de la section [!UICONTROL **Mesures**] dans le rail de gauche.
   * Dans [!DNL Customer Journey Analytics], accédez à **[!UICONTROL Composants]** > **[!UICONTROL Mesures calculées]**, puis sélectionnez **[!UICONTROL + Ajouter]** dans la partie supérieure de la page Mesures calculées.

1. Passez à la section [Zones du créateur de mesures calculées](#areas-of-the-calculated-metrics-builder).

## Zones du créateur de mesures calculées

L’image suivante et le tableau qui l’accompagne décrivent certains des principaux domaines et fonctionnalités du créateur de mesures calculées.

![](assets/cm_builder_ui.png)

| Emplacement dans l’image | Nom et fonction |
|---|---|
| 1 | **Titre :** Attribuer un nom à la mesure est obligatoire. Vous ne pouvez pas enregistrer la mesure tant qu’elle ne porte pas de nom. |
| 2 | **Description :** Donnez-lui une description conviviale pour montrer son utilisation et pour la distinguer des autres. <p>La description apparaît également dans le rapport. Il est préférable de NE PAS mettre la formule dans la description. A la place, décrivez ce pour quoi cette mesure doit être utilisée ou ne doit pas être utilisée. (La formule est générée lorsque vous créez la mesure, sous l’en-tête Résumé. Il n’est donc pas nécessaire d’ajouter la formule à la description.) </p> |
| 3 | **Format :** Les choix incluent Décimal, Heure, Pourcentage et Devise. |
| 4 | **Nombre de décimales :** indique le nombre de décimales qui apparaîtront dans le rapport. Le nombre maximal de décimales que vous pouvez spécifier est 10. |
| 5 | **Afficher la tendance à la hausse en tant que :** Ce paramètre de polarité des mesures indique si Analytics doit considérer une tendance à la hausse dans la mesure comme une bonne (verte) ou une mauvaise (rouge). En conséquence, le graphique du rapport s’affiche en vert ou rouge lorsque la tendance est à la hausse. |
| 6 | **Balises :** Le balisage est un bon moyen d’organiser les mesures. Tous les utilisateurs peuvent créer des balises et en appliquer une ou plusieurs à un segment. Néanmoins, vous ne pouvez afficher les balises que pour les segments que vous possédez ou qui ont été partagés avec vous. Quels types de balises devriez-vous créer ? Vous trouverez ci-dessous quelques suggestions de balises utiles :<ul><li>**Noms d’équipes**, tels que Social Marketing, Mobile Marketing.</li><li>**Projets** (balises d’analyse), comme l’analyse de page d’accès.</li><li>**Catégories**, telles que Femmes ; Géographie.</li><li>**Workflows**, tels que A approuver ; Traités pour (une unité opérationnelle spécifique)</li></ul> |
| 7 | **Résumé :** <p>La formule Résumé se met à jour chaque fois que vous apportez une modification à la définition de mesure. Cette formule s’affiche également dans le rail des mesures à gauche lorsque vous passez la souris sur une mesure et cliquez sur le Icône <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Info_18_N.svg" id="image_BDA0EAF89C19440CB02AE248BA3F968E" />. </p> |
| 8 | **Définition :** C’est là que vous faites glisser des mesures/mesures calculées, des segments et/ou des fonctions pour créer la mesure calculée. <ul><li>Si vous faites glisser une mesure calculée, elle développe automatiquement sa définition de mesure. </li> <li>Vous pouvez imbriquer des définitions dans des conteneurs. Néanmoins, à la différence des conteneurs de segments, ces conteneurs fonctionnent comme une expression mathématique et déterminent la séquence des opérations. </li> </ul> |
| 9 | **Opérateur :** divisé par ( <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Divide_18_N.svg" width="15" id="image_320D7363DE024BDEB21E44606C8B367F" width="25px" /> ) est l’opérateur par défaut, plus les opérateurs +, - et x. |
| 10 | **Aperçu :** fournit une lecture rapide des erreurs possibles. L’aperçu couvre les 90 derniers jours. C’est une manière d’évaluer initialement si vous avez sélectionné les composants appropriés à votre mesure. Un résultat inattendu signifie que vous devez vérifier à nouveau la définition de mesure. |
| 11 | **Compatibilité des produits :** La compatibilité des produits indique si la mesure est compatible avec les <a href="https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/current-data.html?lang=fr"  > données actives </a>, avec les données entièrement traitées, ou uniquement avec les rapports Canal marketing (allocation de première touche). <p>Remarque : Les données actives ne prennent pas en charge toutes les mesures. Les mesures qui comportent des segments ou des fonctions ne sont pas compatibles avec les données actives. <a href="/help/components/c-calcmetrics/cm-compatibility.md"  > Plus... </a> </p> </p> |
| 12 | **Ajouter :** Pour tous les types de mesures calculées, vous pouvez ajouter des conteneurs et des nombres statiques à la définition. Pour les mesures calculées avancées, vous pouvez également ajouter des segments et des fonctions. <ul><li>Les conteneurs fonctionnent comme une expression mathématique et déterminent la séquence des opérations. De ce fait, tout ce que contient un conteneur sera traité avant l’opération suivante.</li><li>Le glissement d’un segment vers un conteneur segmente tout ce que contient ce conteneur. (Mesures calculées avancées uniquement)</li><li>Vous pouvez empiler plusieurs segments dans un conteneur.</li></ul> |
| 13 | **Icône représentant un engrenage (type de mesure, attribution) :** En sélectionnant l’icône représentant un engrenage en regard d’une mesure, vous pouvez spécifier le <a href="/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md"  > type de mesure et les modèles d’attribution </a>. |
| 14 | **Nouveau :** vous permet de créer un composant, tel qu’un nouveau segment (qui vous dirige vers le <a href="/help/components/segmentation/segmentation-workflow/seg-build.md"  > créateur de segments </a>). |
| 15 | **Composants de recherche :** Cette barre de recherche vous permet de rechercher des dimensions, des mesures, des segments (mesures calculées avancées uniquement) et des fonctions (mesures calculées avancées uniquement). |
| 16 | **Liste des Dimensions :** Au lieu de quitter le créateur de mesures calculées pour créer un segment simple (dans le créateur de segments), par exemple &quot;Page = Page d’accueil&quot;, vous pouvez faire glisser Page et sélectionner Page d’accueil directement dans le créateur de mesures calculées.<p>Le processus de création de mesures calculées segmentées est ainsi beaucoup plus rationnel.</p> |
| 17 | **Liste des mesures :** Les mesures se divisent en 3 catégories : <ul> <li>Mesures standard (<img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg" id="image_65A80F54D73443E78542FE0B31CC3F20" />) </li><li>Mesures calculées ( <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg" id="image_C5674AB9B9EB4DA9A56782D15822C319" />) </li><li id="li_8735E76637ED4C3F983731A66E04C93E">Modèles de mesures ( <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Folder_18_N.svg" id="image_D236601511CC4DD3828F223431E27E88" />) - en bas de la liste. </li> </ul> <p>Lorsque vous passez la souris sur une mesure, vous pouvez voir l’icône Infos à droite de celle-ci : <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Info_18_N.svg" width="15px" id="image_5A65E772A68A4B94ACAD6552CCF21F5F" />. Le fait de cliquer sur cette icône vous donne les informations suivantes : </p><ul> <li>La formule de calcul. </li><li>Une tendance d’aperçu de la mesure. </li><li>Icône de modification (crayon) <img placement="break" align="center"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg" width="15px" id="image_7D5B2F026A034118BE4DA81B9215A883" /> dans la partie supérieure droite qui vous amène au créateur de mesures calculées où vous pouvez modifier cette mesure calculée. </li></ul> |
| 18 | **Liste de segments :** (Mesures calculées avancées uniquement) En tant qu’administrateur, cette liste affiche tous les segments créés dans votre société de connexion. Si vous êtes un utilisateur non administrateur, cette liste affiche les segments que vous possédez et ceux que vous partagez. <a href="https://experienceleague.adobe.com/docs/analytics/components/segmentation/segment-reference/seg-rights.html?lang=fr"  > Plus... </a> |
| 19 | **Liste des fonctions :** (mesures calculées avancées uniquement) Les fonctions sont divisées en deux listes : <a href="/help/components/c-calcmetrics/cm-reference/cm-functions.md"  > De base </a> (utilisée le plus souvent) et <a href="/help/components/c-calcmetrics/cm-reference/cm-adv-functions.md"  > Avancé </a>. |
| 20 | **Sélecteur de suite de rapports :** permet de passer à une autre suite de rapports. |

{style="table-layout:auto"}
