---
description: Terminologie et tâches d’Ad Hoc Analysis comparées à celles d’Analysis Workspace.
title: Comparaison entre Analysis Workspace et Ad Hoc Analysis
uuid: e4b3e40f-2b08-49a0-95f1-384d85c1640d
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: ht
source-wordcount: '966'
ht-degree: 100%

---


# Comparaison entre Analysis Workspace et Ad Hoc Analysis

>[!IMPORTANT]
>
>La fin de vie d’Ad Hoc Analysis a été fixée au 1er mars 2021. [En savoir plus](https://adobe.ly/discoverworkspace)

Terminologie et tâches d’Ad Hoc Analysis comparées à celles d’Analysis Workspace.

La plupart des fonctions d’Ad Hoc Analysis sont accessibles par navigateur dans Analysis Workspace. Toutefois, si la terminologie et les fonctions des deux produits restent identiques, en partie du moins, Analysis Workspace introduit de nouveaux termes et de nouvelles approches en matière d’analyses.

Cliquez [ici](https://experienceleague.adobe.com/docs/analytics/admin/admin-overview/analytics-product-comparison.html?lang=fr) pour consulter une comparaison technique des fonctions clés et de la configuration système requise de ces deux produits.

## Comparaison de la terminologie clé {#section_6109406B83B043A18E46D38F130B1D2E}

| Ad Hoc Analysis | Analysis Workspace |
|--- |--- |
| Projet | Workspace ou projet |
| Workspace | Panneau |
| Rapport | Tableau à structure libre |
| Graphique | Visualisation |
| Hiérarchie : Projet > Workspace > Rapports | Hiérarchie : Projet > Panneaux > Tableaux |
| Modèles : rapports avec classement, de tendances, Totaux | Visualisation de tableau à structure libre |
| Modèle de flux | Visualisation de flux |
| Abandon | Visualisation des abandons |

## Comparaison des tâches clés {#section_F31446F1DFA742D794A30D713E223440}

<table id="table_90D4461F04F34D70844C5E3FBB0BBE44"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Ad Hoc Analysis Tâche </th> 
   <th colname="col2" class="entry"> Tâche d’Analysis Workspace </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Ajouter des dimensions et des segments aux colonnes de mesures </p> </td> 
   <td colname="col2"> <p>Vous pouvez insérer des éléments de dimension ou des segments sous forme d’en-têtes de colonne afin de créer facilement des vues comparatives des mesures. <a href="https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/metrics/adding-dimensions-and-metrics-to-your-project-in-analysis-workspace.html"  > Vidéo : Ajout de dimensions et de mesures à votre projet dans Analysis Workspace</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Appliquer les segments </p> </td> 
   <td colname="col2"> <p>Les segments sont disponibles sous le menu du composant Segment ; il est possible de les appliquer dans trois emplacements différents dans Analysis Workspace : </p> 
    <ol id="ol_800D81FE2C84459B94B085C51E140330"> 
     <li id="li_F2E050902F9A4831BBA57F466E07DEAE">Au <b>niveau du panneau</b>, ce qui applique les segments à toutes les visualisations du panneau. Ceci revient à appliquer un segment à un Workspace dans Ad Hoc Analysis. </li> 
     <li id="li_2D88E43E0161485C95B08DC3C593EFD9">Sous forme de <b>lignes d’un tableau</b>. Ceci revient à ajouter des segments à la section Lignes/ventilations du Générateur de tableau dans Ad Hoc Analysis. </li> 
     <li id="li_102E1A1DAA9247C08FC46C5AB3D78113">Sous forme de <b>colonnes d’un tableau</b>. Ceci revient à ajouter des segments à la section Colonnes du Générateur de tableau dans Ad Hoc Analysis ou à appliquer un segment au niveau du rapport dans Ad Hoc Analysis. </li> 
    </ol> <p><a href="https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/applying-segments/applying-segments-to-your-analysis-workspace-project.html?lang=fr"  > Vidéo : Utilisation de segments dans Analysis Workspace</a> </p> <p><a href="https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/using-panels/panel-level-segments.html"  > Vidéo : Application de segments dans un panneau</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Créer des segments temporaires (« ad hoc ») </p> </td> 
   <td colname="col2"> <p>Vous pouvez <a href="/help/analyze/analysis-workspace/components/t-freeform-project-segment.md"  >créer des segments instantanés et temporaires (« ad hoc »)</a> dans Analysis Workspace en faisant glisser les éléments de dimension sur la zone de dépôt des segments en haut du panneau. De plus, il est possible d’ajouter des filtres déroulants dans la zone de dépôt du panneau pour créer plusieurs segments temporaires en même temps, ce qui permet d’activer des interactions contrôlées avec le projet. </p> <p><a href="https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/applying-segments/ad-hoc-temporary-segments.html?lang=fr"  > Vidéo : Segments ad hoc dans Analysis Workspace</a> </p> <p><a href="https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/applying-segments/using-drop-down-filters.html"  > Vidéo : Filtres déroulants dans Analysis Workspace</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Choisir les plages de dates et les granularités </p> </td> 
   <td colname="col2"> <p>Les plages de dates et les granularités sont disponibles sous le menu du composant Période ; elles peuvent être appliquées de trois façons : </p> 
    <ol id="ol_8B57C8A840694A879B22B809C58E7482"> 
     <li id="li_58FAE6A87B494A5C9007CD35BB101608">Les plages de dates peuvent être appliquées aux colonnes et aux lignes ; elles remplacent la plage de dates sélectionnée dans le panneau. Cela est identique aux plages de dates au niveau du rapport. </li> 
     <li id="li_85BB89EFF9C8466A992815BB7804EA37">Cliquez sur Appliquer pour appliquer une plage de dates à toutes les visualisations d’un panneau. Cela est identique aux plages de dates d’un Workspace dans Ad Hoc Analysis. </li> 
     <li id="li_BC18564A8FBB48F4A522BCAC60838759">Cliquez sur Appliquer à tous les panneaux pour appliquer une plage de dates à tous les panneaux d’un projet Analysis Workspace. Cela est identique aux plages de dates d’un projet dans Ad Hoc Analysis. </li> 
    </ol> <p><a href="https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/dimensions/adding-dimensions-and-metrics-to-your-project-in-analysis-workspace.html?lang=fr"  > Vidéo : Utilisation des dates dans Analysis Workspace</a> </p> <p><a href="https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/calendar-and-date-ranges/creating-custom-date-ranges-in-analysis-workspace.html?lang=fr"  > Vidéo : Plages de dates personnalisées</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Utiliser les abandons et les entonnoirs de conversion </p> </td> 
   <td colname="col2"> <p>Les <a href="/help/analyze/analysis-workspace/visualizations/fallout/fallout-flow.md"  >visualisations Abandons</a> sont accessibles dans Analysis Workspace sous le menu du composant Visualisation. Semblable à Ad Hoc Analysis : </p> 
    <ol id="ol_625FF45AED4E403DBEE1A906282E8531"> 
     <li id="li_7B6C5F2682774641B82D2021786AE5C4">Les abandons peuvent couvrir une visite ou un visiteur ; toutes les visites peuvent être incluses, en option. Des tendances d’abandon peuvent rapidement être disponibles via le menu contextuel. </li> 
     <li id="li_CFBDDAB8E96A445DB0624640AEB25994">Les éléments de dimension peuvent être connectés par un opérateur OR (comme pour les groupes) ; les événements peuvent être utilisés dans l’entonnoir. </li> 
     <li id="li_6638E6A62C744A27B2C066E5F9EC62C0">Les étapes suivantes des transferts et des abandons peuvent également être générées via le menu contextuel. </li> 
    </ol> <p>En outre, dans Analysis Workspace, les abandons permettent d’utiliser des <a href="/help/analyze/analysis-workspace/visualizations/fallout/configuring-interdimensional-fallout.md"  > dimensions mixtes</a> dans les étapes, ce qui n’était pas possible dans Ad Hoc Analysis. Les dimensions mixtes dans les étapes sont gérées avec un opérateur AND. </p> <p><a href="https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/analyzing-customer-journeys/fallout-visualization.html?lang=fr"  > Vidéo : Visualisation des abandons</a> </p> <p><a href="https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/analyzing-customer-journeys/multi-dimensional-fallout.html?lang=fr"  > Vidéo : Utilisation de plusieurs dimensions d’abandons</a> </p> <p><a href="https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/analyzing-customer-journeys/comparing-segments-in-fallout.html?lang=fr"  > Vidéo : Comparaison des segments dans les abandons</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Examiner le flux (Cheminement) </p> </td> 
   <td colname="col2"> <p>Les <a href="/help/analyze/analysis-workspace/visualizations/c-flow/flow.md"  >visualisations Flux</a> sont accessibles dans Analysis Workspace sous le menu du composant Visualisation. Semblable à Ad Hoc Analysis : </p> 
    <ul id="ul_42D259310823496499F7D1474E1639AF"> 
     <li id="li_5DE6980EF66A49E58B8946A0422BC02C">Le flux peut couvrir une visite ou un visiteur. </li> 
     <li id="li_70A692266D32416BA3D70C1F8999F837">Les statistiques clés s’affichent sous la forme de pourcentage de vues chemins. </li> 
    </ul> <p>En outre, avec les flux, il est possible d’utiliser des <a href="/help/analyze/analysis-workspace/visualizations/c-flow/multi-dimensional-flow.md"  > dimensions mixtes</a> et de cliquer droit pour créer un segment, ce qui n’était pas le cas dans Ad Hoc Analysis. </p> <p>Actuellement, dans Analysis Workspace, les flux <b>ne permettent pas</b> aux utilisateurs de choisir un événement de succès. </li> 
    </ul> <p><a href="https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/analyzing-customer-journeys/flow-visualization.html?lang=fr"  > Vidéo : Présentation de la visualisation Flux</a> </p> <p><a href="https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/analyzing-customer-journeys/text-wrapping-and-multi-dimensional-flow.html?lang=fr"  > Vidéo : Flux multidimensionnel</a> </p> <p><a href="https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/analyzing-customer-journeys/expanding-on-flow-visualization.html?lang=fr"  > Vidéo : Création de segments à partir du flux</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Effectuer des ventilations infinies </p> </td> 
   <td colname="col2"> <p>Dans Analysis Workspace, vous pouvez descendre jusqu’à un niveau infini de la hiérarchie. Il est possible de mélanger les segments et les dimensions. Plusieurs éléments de dimension peuvent être ventilés à la fois en les sélectionnant tous puis en les faisant glisser sur une dimension de ventilation. </p> <p><a href="https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/building-freeform-tables/dimension-breakdown-by-position.html"  > Vidéo : Ventilations optimisées</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Calculer rapidement la tendance des données </p> </td> 
   <td colname="col2"> <p>Visualisez rapidement les données en cliquant sur l’icône de graphique dans la ligne du rapport. En outre, ces visualisations rapides seront liées au tableau source, de sorte que si vous cliquez sur différentes valeurs dans le tableau, le diagramme est automatiquement mis à jour. </p> <p><a href="https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/visualizations/dimension-graph-live-linking.html?lang=fr"  > Vidéo : Établissement de liens en direct dans les diagrammes de dimensions</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Sélectionner des suites de rapports </p> </td> 
   <td colname="col2"> <p>Vous pouvez ajouter plusieurs suites de rapports à un seul projet dans Analysis Workspace.  </p> <p><a href="https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/using-panels/multiple-report-suites-in-analysis-workspace.html?lang=fr"  > Vidéo : Suites de rapports multiples dans Workspace</a> </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Attribution IQ </p> </td> 
   <td colname="col2"> <p>L’<a href="/help/analyze/analysis-workspace/attribution/overview.md"  >Attribution IQ</a> dans Analysis Workspace vous permet d’ajouter de nombreux nouveaux types de modèles d’attribution aux tableaux à structure libre, aux visualisations et aux mesures calculées. Il comprend plus de 10 modèles algorithmiques et basés sur des règles. </p>  <p><a href="https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/attribution-iq/using-attribution-iq-in-freeform-tables.html?lang=fr"  > Vidéo : Attribution IQ dans les tableaux à structure libre</a> </p> </td> 
  </tr>  
 </tbody> 
</table>

