---
description: Créez un projet et ajoutez des composants (dimensions, mesures, segments et plages de dates) au panneau à structure libre.
keywords: Analysis Workspace
seo-description: Créez un projet et ajoutez des composants (dimensions, mesures, segments et plages de dates) au panneau à structure libre.
seo-title: Création d'un projet Workspace
solution: Analytics
title: Création d'un projet Workspace
topic: Reports and Analytics
uuid: c 1 def 77 a-a 76 e -4699-9 fév fév -1 ede 5 b 70 b 7 ba
translation-type: tm+mt
source-git-commit: f5f5b294f503911108e1693b7c6cd128bee659c6

---


# Création d'un projet Workspace

Créez un projet et ajoutez des composants (dimensions, mesures, segments et plages de dates) au panneau à structure libre.

Cet article présente les éléments d’Analysis Workspace et explique comment créer un projet. For specific use cases, see [Use Cases for Analysis Workspace](../../../analyze/analysis-workspace/freeform-analysis-examples-use-cases.md#concept_173D1EB783F24EA89E754628BA30FF4B).

## Créez un projet

1. Spécifiez les autorisations de création et de traitement des projets de l’utilisateur.

   Avant de créer ou de traiter un projet Analysis Workspace, les administrateurs doivent vous ajouter à un groupe avec l’autorisation **[!UICONTROL Créer / Traiter les projets dans Analysis Workspace]** activée ou au groupe d’utilisateurs **Accès à tous les rapports** ( **[!UICONTROL Admin]** &gt; **[!UICONTROL User Management]** &gt; [Groups](https://marketing.adobe.com/resources/help/en_US/reference/?f=groups)).

1. In the [!DNL Experience Cloud], click **[!UICONTROL Analytics]** &gt; **[!UICONTROL Workspace]**.

   ![](assets/analysis_workspace_menu.png)

   Vous pouvez également entrer une barre oblique (/) afin d’ouvrir la barre de recherche des rapports, puis entrer *`workspace`*.

   ![](assets/analysis-app-search.png)

1. Click **[!UICONTROL Create New Project]**.

   Vous pouvez créer un projet d’après :

* un projet vierge (par défaut). Pour obtenir des instructions, voir ci-dessous.
* d’un modèle standard. Ces modèles créés par Adobe sont prêts à l’emploi. Pour obtenir des instructions, voir [Modèles](../../../analyze/analysis-workspace/build-workspace-project/starter-projects.md#concept_49B9A327C5004DB0A4BE6291435625C5) ;
* d’un modèle personnalisé. Les utilisateurs dotés de droits d’administration peuvent créer ces modèles. Pour obtenir des instructions, voir [Modèles](../../../analyze/analysis-workspace/build-workspace-project/starter-projects.md#concept_49B9A327C5004DB0A4BE6291435625C5).

   ![](assets/start_modal.png)

1. To create a project from a blank project, click **[!UICONTROL Blank Project]**.

   * Then click **[!UICONTROL Create]**, or
   * cliquez simplement sur **[!UICONTROL Entrée]**.
   Un projet vierge s’affiche, avec un panneau à structure libre et une visualisation de tableau de données.

   ![](assets/fa_project_new.png)

   >[!NOTE]
   >
   >Parfois, un message « Suite de rapports incompatible » s'affiche lors du chargement d'un projet (ou passage à une suite de rapports) où tous les composants (mesures/dimensions) inclus dans le projet sont inclus dans la suite de rapports. Vous pouvez consulter la liste des composants non compatibles et ainsi savoir pour quelle raison ce message s’affiche.

<table id="table_3989E45D9D4241CBB2E58B29DA257B2F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Élément </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><a href="../../../analyze/analysis-workspace/components/analysis-workspace-components.md#concept_BEBE3A75E072495D9E2F895567BBD462" format="dita" scope="local"> Composants</a> </td> 
   <td colname="col2"> <p>Dimensions, mesures, segments et périodes que vous faites glisser sur les projets. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="../../../analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#concept_09242627629147A88A68F1506954C276" format="dita" scope="local"> Visualisations</a> </td> 
   <td colname="col2"> <p>Éléments que vous pouvez faire glisser sur le panneau ou les zones du projet dans l’interface. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="../../../analyze/analysis-workspace/visualizations/freeform-table.md#concept_0D2E24FCCBAF4194AA941448860E422F" format="dita" scope="local">Panneau à structure libre</a> </td> 
   <td colname="col2"> <p>Trame ou espace de travail avec lequel vous interagissez dans Analysis Workspace. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Enregistrez le projet. Name the project, provide a description (optional, but useful) and tag the project (optional), then click **[!UICONTROL Save Project]**.

   ![](assets/save_project.png)

1. Désormais, vous pouvez cliquer avec le bouton droit de la souris sur une visualisation ou un panneau pour le copier, puis le coller (« insérer ») à un autre emplacement du projet ou dans un autre projet.

   Utilisez cette fonction pour créer des blocs de construction (visualisations ou panneaux prédéfinis) qui pourront être copiés dans d’autres projets afin de démarrer plus rapidement, avec des données spécifiques à votre entreprise.

   >[!NOTE]
   >
   >Après avoir copié/enregistré, les liens intra-liens sont maintenant relatifs au projet qu'ils ont actif, et non au projet d'origine où ils ont été copiés.

## Ajout de composants et de visualisations {#task_CDAC9B3007BE4A3790AFAD3746D669B1}

1. Build your project by dragging *`components`* and *`visualizations`* to the project.

   **Composants**

   La barre d’outils Composant contient les dimensions, mesures, segments et plages de dates pouvant faire l’objet de recherches et que vous utilisez le plus fréquemment.

<table id="table_4626163E26DE46CB86391868BBA3AD32"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Composant </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Dimensions (orange) </td> 
   <td colname="col2"> <p>Appliquez-les au niveau du projet. </p> <p><img  src="assets/dimensions.png" id="image_353BAF1A7AC04C7DB5F5CDFDE7614402" align="left" placement="break" width="300px" /> </p> <p>Les dimensions Prop#, eVar# et event# sont ajoutées aux noms des dimensions et vous pouvez en rechercher les numéros. Exemple : « Campagne interne » apparaît dans le rail de gauche comme « Campagne interne (evar2) ». </p> <p> Notez que les numéros des dimensions prop, eVar et event n’apparaissent pas dans le tableau (afin de conserver des titres courts). </p> <p>Il existe un ordre de classement par défaut pour certaines dimensions prêtes à l’emploi lorsqu’elles sont déposées dans un tableau à structure libre ou lorsqu’elles s’affichent dans le rail de gauche. Par exemple, lorsque la dimension « Heure du jour » est déposée dans un tableau ou affichée dans le rail de gauche, elle est triée par heure, de 00h à 23h. Vous avez toujours la possibilité de les classer en fonction de n’importe quelle colonne de mesures. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Mesures (vert) </td> 
   <td colname="col2"> <p>Appliquez-les au niveau du projet. </p> <p><img  src="assets/metrics.png" id="image_7C874C72992E414CBEE6B90CEF7B9F3C" /> </p> <p> <span class="term"> Occurrences</span> est la mesure par défaut du tableau de données. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Segments (bleu) </td> 
   <td colname="col2"> <p>Vous pouvez les faire glisser uniquement au niveau du panneau, mais vous pouvez créer des segments incorporés dans le tableau de données. </p> <p><img  src="assets/segments.png" id="image_5674B18BC3AB47A2B1FEE584E0FBF47C" /> </p> <p>See <a href="../../../analyze/analysis-workspace/freeform-analysis-examples-use-cases.md#concept_173D1EB783F24EA89E754628BA30FF4B" format="dita" scope="local"> Use Cases for Analysis Workspace</a> for more information. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Plages de dates et granularités (violet) </td> 
   <td colname="col2"> <p>Vous pouvez les faire glisser uniquement au niveau du panneau. Vous pouvez créer un projet à partir du calendrier, lorsque vous configurez une plage de dates. </p> <p><img  src="assets/date-ranges.png" id="image_A1750DA921234AD0BB02166865EB8FCC" /> </p> </td> 
  </tr> 
 </tbody> 
</table>

**[Visualisations](../../../analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#concept_09242627629147A88A68F1506954C276)**

Le panneau [!UICONTROL Visualisations] fournit des graphiques, des diagrammes, des anneaux, des tableaux de données,       des tableaux de [cohortes](../../../analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md#concept_9D240A490265427DA694D18D14EACC0E), des diagrammes de Venn, etc. Vous pouvez faire glisser-déposer plusieurs visualisations sur votre projet.

![Résultat de l’étape](assets/visualizations.png)

![](assets/fa_full_panel.png)

1. Étape

## Utilisation du menu contextuel pour personnaliser les données {#concept_8117C300F21843B99F4E1B9AB7B11B6F}

Grâce au menu contextuel, vous pouvez exécuter les actions suivantes, selon la cellule du tableau dans laquelle vous cliquez avec le bouton droit.

![Résultat de l’étape](assets/fa_data_table_actions.png)

<table id="table_0F84CC5B604D4D41BD0C9668DF525929"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Action </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><a href="../../../analyze/analysis-workspace/components/calendar-date-ranges/time-comparison.md#concept_93BCAD81B7A54ABBBA5CD9E419F6F764" format="dita" scope="local"> Ajout d’une colonne de période</a> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="../../../analyze/analysis-workspace/components/calendar-date-ranges/time-comparison.md#concept_93BCAD81B7A54ABBBA5CD9E419F6F764" format="dita" scope="local"> Comparaison de périodes</a> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Copier dans le Presse-papiers </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Supprimer la sélection </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="/help/components/c-alerts/intellligent-alerts.md" format="dita" scope="local"> Création d’une alerte d’après la sélection</a> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="../../../analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md#task_B594DA2476E84DFDA8279E831F0BD9C4" format="dita" scope="local"> Ventilation</a> 
    <ul id="ul_18C83B8514AD4C1C86C071AA8402CB5C"> 
     <li id="li_6CA84ED293EA4940A7495DA9D9121264">Dimensions </li> 
     <li id="li_EA16EE017B2E4A6998918706938A21BF">Mesures </li> 
     <li id="li_0405D339CD01405DB508A7D8D1A976B4">Segments </li> 
     <li id="li_819CE81C552F49BB9C1B83ED3B42C5F7">Heure </li> 
    </ul> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="../../../analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#concept_09242627629147A88A68F1506954C276" format="dita" scope="local"> Visualisation</a> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="../../../analyze/analysis-workspace/curate-share/download-send.md#concept_BB548979F47F45739679B830428C3025" format="dita" scope="local"> Téléchargement au format CSV</a> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="../../../analyze/analysis-workspace/analysis-workspace-features.md#concept_4D69EE46E3C24EEB97C935A8789364F9" format="dita" scope="local"> Sélection de tendances</a> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="../../../analyze/analysis-workspace/components/t-freeform-project-segment.md#task_11C6A2C7717B48049E5750B9D20FEC80" format="dita" scope="local"> Création d’un segment d’après une sélection</a> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="../../../analyze/analysis-workspace/c-panels/c-segment-comparison/segment-comparison.md#concept_74FAC1C6D0204F9190A110B0D9005793" format="dita" scope="local"> Comparaison des segments</a> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Affichage uniquement des lignes sélectionnées </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Afficher toutes les lignes </td> 
   <td colname="col2"> </td> 
  </tr> 
 </tbody> 
</table>

Voir [Interactions clavier-souris dans Analysis Workspace](../../../analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys.md#concept_9A6356084DBC4D468E265E7A65B3E051) pour obtenir des informations sur la copie et la sélection de lignes.
