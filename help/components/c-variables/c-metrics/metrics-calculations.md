---
description: Les mesures sont calculées selon des méthodes d’attribution standard, de participation, récente et linéaire. Chaque méthode calcule les valeurs selon des formules différentes.
title: Calculs de mesures
topic: Metrics
uuid: 2af58f1e-12c5-4828-ae39-c9aeaef6b705
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Calculs de mesures

Les mesures sont calculées selon des méthodes d’attribution standard, de participation, récente et linéaire. Chaque méthode calcule les valeurs selon des formules différentes.

<table id="table_6F81A12174D84124B7FD81FBBEDF18A2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Calcul de la mesure </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Origine </td> 
   <td colname="col2"> <p>Tout le crédit est attribué à la première valeur de variable associée à l’événement de succès. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Récente </td> 
   <td colname="col2"> <p>Tout le crédit est attribué à la dernière valeur de variable associée à l’événement de succès. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Linéaire </td> 
   <td colname="col2"> <p>Lorsque l’allocation linéaire est sélectionnée, les événements de succès sont répartis uniformément entre toutes les valeurs variables affichées dans la visite. Pour les événements numériques et monétaires, tels que <span class="term"> Recettes</span>, le montant monétaire est divisé. Pour les événements de compteur tels que <span class="term"> Commandes</span>, une partie de l’événement est attribuée à chaque valeur de variable de la visite. Ces parties sont additionnées dans le cadre des rapports, puis arrondies à l’entier le plus proche. </p> <p>Par exemple, pour une visite où quatre pages ont été consultées avant un événement de succès, chaque page reçoit un crédit de 25 % de l’événement. Si, au cours d’une même visite, la La <span class="varname"> campagne</span> a deux valeurs, chaque valeur de campagne recevra 50 % du crédit pour l’événement. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Participation </td> 
   <td colname="col2"> <p>Attribue tout le crédit à chaque valeur de variable qui a contribué à l’événement de succès au cours d’une visite. Ce calcul peut également s’appliquer à plusieurs sessions de visiteurs, si vous utilisez des mesures de participation inter-visites. </p> <p>Voir <a href="/help/components/c-variables/c-metrics/metrics-participation.md"  > Participation</a> pour plus d’informations. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Exemple – Calcul de mesure {#section_4CE01DA35108418D9909823A7ECC4B45}

Supposons que votre site comporte une recherche interne dont le suivi est réalisé à l’aide d’une variable de conversion (eVar). Le visiteur effectue plusieurs recherches internes avant de réaliser un achat d’un montant de 100 $ :

*`Pet`* &gt; *`Feline`* &gt; *`Cat`* &gt; *`Kitten`* &gt; 100 $ d’achat

Dans le rapport, l’attribution de crédit est la suivante :

<table id="table_91A7244E77854838A8392B49366FB445"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Valeur eVar </th> 
   <th colname="col2" class="entry"> Premier </th> 
   <th colname="col3" class="entry"> Dernier </th> 
   <th colname="col4" class="entry"> Linéaire </th> 
   <th colname="col5" class="entry"> Participation </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Animal domestique </p> </td> 
   <td colname="col2"> <p>100 $ </p> </td> 
   <td colname="col3"> <p>$0 </p> </td> 
   <td colname="col4"> <p>$25 </p> </td> 
   <td colname="col5"> <p>100 $ </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Félin </p> </td> 
   <td colname="col2"> <p>$0 </p> </td> 
   <td colname="col3"> <p>$0 </p> </td> 
   <td colname="col4"> <p>$25 </p> </td> 
   <td colname="col5"> <p>100 $ </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Chat </p> </td> 
   <td colname="col2"> <p>$0 </p> </td> 
   <td colname="col3"> <p>$0 </p> </td> 
   <td colname="col4"> <p>$25 </p> </td> 
   <td colname="col5"> <p>100 $ </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Chaton </p> </td> 
   <td colname="col2"> <p>$0 </p> </td> 
   <td colname="col3"> <p>100 $ </p> </td> 
   <td colname="col4"> <p>$25 </p> </td> 
   <td colname="col5"> <p>100 USD </p> </td> 
  </tr> 
 </tbody> 
</table>

