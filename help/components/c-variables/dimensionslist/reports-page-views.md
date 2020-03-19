---
description: Rapport de tendance qui affiche le nombre de fois où les pages de votre site web ont été consultées pour une période donnée (heure, jour, semaine, mois, trimestre ou année). Ce rapport vous permet de suivre chaque page vue pour chaque page de votre site, ainsi qu’un groupe de pages vues pour la totalité du site.
title: Pages vues
topic: Reports
uuid: c78260c6-9ad4-4b85-84fd-763627392e44
translation-type: tm+mt
source-git-commit: 707b61d853a8ec68b3f77a35a1aa5f0c7dd8a1fd

---


# Pages vues

Rapport de tendance qui affiche le nombre de fois où les pages de votre site web ont été consultées pour une période donnée (heure, jour, semaine, mois, trimestre ou année). Ce rapport vous permet de suivre chaque page vue pour chaque page de votre site, ainsi qu’un groupe de pages vues pour la totalité du site.

Une [Page vue](/help/components/c-variables/c-metrics/metrics-page-view.md) est une requête pour une page entière, plutôt qu’un élément d’une page (image ou vidéo, par exemple). Par exemple, si un visiteur unique consulte 15 pages durant une visite, 15 pages vues sont comptabilisées. Si un visiteur affiche la même page trois fois durant une visite, trois pages vues sont comptabilisées.

## Propriétés des rapports

* This report references the number of times the [`t()`](/help/implement/vars/functions/t-method.md) method is called on your site.
* Les appels de suivi de liens qui utilisent la [`tl()`](/help/implement/vars/functions/tl-method.md) méthode ne sont pas comptabilisés dans ce rapport.
* Des demandes d’image sont envoyées lorsque l’utilisateur actualise la page ou clique sur le bouton Précédent. Par conséquent, ces actions sont également reprises dans le rapport.
* Les ventilations horaires sont basées sur le fuseau horaire de la suite de rapports.
* Ce rapport ne contient pas d’éléments. À ce titre, il peut uniquement être affiché sous la forme d’un rapport de tendance.
* Vous pouvez appliquer une granularité horaire, quotidienne, hebdomadaire, mensuelle, trimestrielle et annuelle. Cette granularité est disponible en fonction de la plage de dates des rapports.

## Informations spécifiques au produit

<table id="table_61F964F47D1D43508B271999F495F7F9"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p> Reports &amp; Analytics </p> </td> 
   <td colname="col2"> <p> <span class="uicontrol"> Contenu du site</span> &gt; <span class="uicontrol">Pages vues</span> </p> <p>Ce rapport peut utiliser des segments. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Ad Hoc Analysis </p> </td> 
   <td colname="col2"> 
    <ul id="ul_DB66B8F9F6BF473A83EC7668F59776D0"> 
     <li id="li_D1CB486058F040859560D5BFDF3972EE"> Ventile chaque élément du rapport selon tous les autres rapports et variables. Vous pouvez ainsi visualiser les ventilations en fonction de n’importe quelle granularité. </li> 
     <li id="li_BAADA9ADDD6F47B08D129FD30CD8EF2E">Vous pouvez utiliser toutes les mesures de trafic et de conversion de ce rapport, ainsi qu’une allocation différente pour toutes les mesures de conversion. </li> 
     <li id="li_3696CA6E0BD54305B3609CCC80F851BA">Ce rapport peut utiliser plusieurs segments très avancés. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

