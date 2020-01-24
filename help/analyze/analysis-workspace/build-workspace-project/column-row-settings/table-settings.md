---
description: Les configurations des lignes varient selon le composant déposé dans le tableau.
title: Paramètres des lignes
uuid: f30c31d5-1fd4-4b93-94c3-ca441099fe2e
translation-type: tm+mt
source-git-commit: 5c2f2d098398927d8379f2eb9ea69ca9acbfd726

---


# Paramètres des lignes

Les configurations des lignes varient selon le composant déposé dans le tableau.

Vous pouvez aussi gérer les lignes sélectionnées à l’aide des [options contextuelles (clic avec le bouton droit) dans un tableau](/help/analyze/analysis-workspace/visualizations/freeform-table.md).

Pour accéder aux paramètres de ligne d’un tableau, cliquez sur l’icône Paramètres en regard d’une dimension, d’un segment, d’une mesure, d’une période ou d’une ventilation :

![](assets/row-settings.png)

<table id="table_7ACE6413DB1F40349ED2860020F92E55"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Paramètre de ligne </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><a href="/help/analyze/analysis-workspace/components/calendar-date-ranges/time-comparison.md"  > Comparaison de dates</a> </p> </td> 
   <td colname="col2"> <p><b>Harmonisez les dates de chaque colonne afin qu’elles commencent à la même ligne. </b> </p> <p>Si vous harmonisez les dates, par exemple dans le cadre d’une comparaison d’un mois à l’autre entre octobre et septembre 2016, la colonne de gauche commence au 1er octobre et la colonne de droite au 1er septembre : </p> <p><img placement="break"  src="assets/add-time-period-column3.png" width="500px" id="image_99398B13FEDA4715B8B818DF6093CA37" /> </p> <p>Option désactivée par défaut. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Pourcentages </p> </td> 
   <td colname="col2"> <p><b>Calculer les pourcentages par ligne</b> </p> <p>Oblige le tableau à structure libre à calculer les pourcentages des cellules par ligne, et non pas par colonne. Cette fonctionnalité est particulièrement utile pour les pourcentages de tendance. Elle est activée par défaut lorsque l’icône <span class="uicontrol">Visualiser</span> est utilisée. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Totaux des colonnes </p> </td> 
   <td colname="col2"> <p>Ce paramètre est accessible uniquement pour les <a href="/help/analyze/analysis-workspace/build-workspace-project/column-row-settings/manual-vs-dynamic-rows.md"  > lignes manuelles (statiques)</a> (quand vous avez sélectionné un ensemble fini d’éléments), et non pour les lignes dynamiques (quand vous déposez une dimension qui répertorie tous les éléments). <p>Remarque : Le paramètre est désactivé pour les lignes manuelles de <i>mesure</i>, puisque le cumul des mesures en dehors des lignes actuelles d’un tableau n’aurait aucun sens. </p> </p> <p><b>Calculer les totaux en totalisant les valeurs actuellement dans chaque colonne (activée par défaut) :</b> </p> <p>Cette option calcule seulement les lignes figurant actuellement dans le tableau. (Calcul côté client) </p> <p><b>Calculer les totaux d’après toutes les lignes pour chaque mesure (désactivée par défaut) :</b> </p> <p>Cette option comprend tous les éléments de cette dimension, même ceux qui ne sont pas répertoriés dans le tableau. (Calcul côté serveur) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ventilations </p> </td> 
   <td colname="col2"> <p><b>Ventilation par position:</b> </p> <p>Ventilez les données en fonction d’une position fixe dans un tableau à structure libre. Vous pouvez par exemple spécifier que les sept premières lignes du tableau sont toujours ventilées. </p> <p>(Auparavant, la liste des valeurs de la ventilation était « verrouillée ». Par conséquent, si par exemple vous aviez une ventilation de <span class="term"> date </span> par <span class="term"> page </span>, vous obteniez une liste des 50 premières pages pour la période sélectionnée. Si vous enregistriez ce rapport puis l’exécutiez à nouveau un mois plus tard, il est probable que les 50 premières pages auraient changé. Toutefois, Analysis Workspace utilisait les résultats de la ventilation d’origine et renvoyait les mêmes pages, avec pour période le mois en cours.) </p> <p>Pour ventiler des données en fonction d’une position fixe : </p> 
    <ol id="ol_A396A11566AA4F52BC3ABBC373CEF477"> 
     <li id="li_BDAB1E9A48D44944A4F7C31F1182B923">Ventilez quelques lignes du tableau. </li> 
     <li id="li_C5610437D3714CCEB9F3C771864B4336">Cliquez sur l’icône de paramètres (engrenage) en regard de la ligne de tableau à définir sur une position fixe. </li> 
     <li id="li_675E429DC3B94201978166F9408D30B1">Activez la case à cocher en regard de l’option <span class="uicontrol">Ventilation par position</span>. </li> 
     <li id="li_E8A417D0D6D1438CAE825843BA0A7060">Changez l’ordre de tri ou la plage de dates. Vous remarquerez que les ventilations sont maintenant liées à la position des lignes, et non aux lignes codées en dur. </li> 
    </ol> <p>Option désactivée par défaut. </p> </td> 
  </tr> 
 </tbody> 
</table>

| Paramètre de ligne | Description |
|--- |--- |
| Comparaison de dates | Harmonisez les dates de chaque colonne afin qu’elles commencent à la même ligne.   Lorsque vous choisissez d’aligner les dates, par exemple dans une comparaison mois-par mois entre octobre et septembre 2016, la colonne de gauche commence par le 1er octobre et la colonne de droite commence par le 1er septembre.<br>Option désactivée par défaut. |
| Pourcentages | Calculer les pourcentages par ligne Force le tableau à structure libre à calculer les pourcentages de cellules sur toute la ligne, par opposition à la colonne inférieure. Cette fonctionnalité est particulièrement utile pour les pourcentages de tendance.<br>Activé par défaut lors de l’utilisation de l’icône Visualize. |
| Totaux des colonnes | Ce paramètre est accessible uniquement pour les [static) rows](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/build-workspace-project/column-row-settings/manual-vs-dynamic-rows.html) (when you have selected a finite set of items), not with dynamic rows (i.e., when you drop in a dimension that shows all items).<ul><li>**[!UICONTROL Afficher la somme des lignes actuelles en tant que total]** : affiche la somme des lignes du tableau côté client, ce qui signifie que le total ne dédupliquera** pas **de mesures telles que les visites ou les visiteurs.</li><li>**[!UICONTROL Afficher le total général]** : indique une somme côté serveur, ce qui signifie que le total dédupliquera les mesures telles que les visites ou les visiteurs.</li></ul> |
| Ventilations | **[!UICONTROL Ventilation par position]**:  Vous pouvez effectuer des ventilations en fonction d’un emplacement fixe dans un tableau à structure libre. Vous pouvez par exemple spécifier que les sept premières lignes du tableau sont toujours ventilées.<br>(Auparavant, la liste des valeurs de la ventilation était « verrouillée ». Par conséquent, si par exemple vous aviez une ventilation de  date  par  page , vous obteniez une liste des 50 premières pages pour la période sélectionnée. Si vous enregistriez ce rapport puis l’exécutiez à nouveau un mois plus tard, il est probable que les 50 premières pages auraient changé. Toutefois, Analysis Workspace utilisait les résultats de la ventilation d’origine et renvoyait les mêmes pages, avec pour période le mois en cours.)<br>Pour effectuer des ventilations en fonction d’un emplacement fixe :1. Ventilez quelques lignes du tableau. 2. Cliquez sur l’icône Paramètres (engrenage) en regard de la ligne du tableau à placer en position fixe. 3. Cochez la case en regard de Ventiler par position. 4. Modifiez l’ordre de tri ou la plage de dates et notez que les ventilations sont désormais liées à la position de la rangée et non aux lignes codées en dur.<br>Option désactivée par défaut. |