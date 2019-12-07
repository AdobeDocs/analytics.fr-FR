---
description: Affiche le domaine ou l’URL de provenance des visiteurs avant qu’ils arrivent sur votre site, les méthodes utilisées par les visiteurs pour trouver votre site web et le nombre de visites sur votre site qui proviennent de ces référents.
title: Référents
topic: Reports
uuid: e63b47b4-49f3-43af-8409-3272bec0484e
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Référents

Affiche le domaine ou l’URL de provenance des visiteurs avant qu’ils arrivent sur votre site, les méthodes utilisées par les visiteurs pour trouver votre site web et le nombre de visites sur votre site qui proviennent de ces référents.

Si, par exemple, un visiteur clique sur un lien du Site A et arrive sur votre site, le Site A est le référent s’il n’est pas défini comme faisant partie de votre domaine. Lors de l’implémentation, votre conseiller peut vous aider à définir les domaines et adresses URL qui font partie de votre site web. (Notez que cette modification peut être effectuée après la mise en œuvre.)

Les domaines ou URL ne faisant pas partie de ces domaines et URL définis sont considérés comme des référents. Par exemple, les pages Web A et Web B sont ajoutées au filtre URL interne, mais la page web C ne l’est pas. Dans ce cas, la page web C est considérée comme un référent.

## Attribution, expiration et valeurs spéciales {#section_4D8CE5E111DD48FBBDCF9B5A1F16E92E}

<table id="table_EC7423532C7E44DE97B7FC0321585A2B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col2" class="entry"> Reports &amp; Analytics marketing (SiteCatalyst) </th> 
   <th colname="col3" class="entry"> Analyses ad hoc </th> 
   <th colname="col4" class="entry"> Data Warehouse </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Attribution des mesures </td> 
   <td colname="col2"> Le plus récent </td> 
   <td colname="col3"> Le plus récent </td> 
   <td colname="col4"> Le plus récent </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Valeurs Expire après </td> 
   <td colname="col2"> Visite </td> 
   <td colname="col3"> Visite </td> 
   <td colname="col4"> Visite </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Valeur Limites </td> 
   <td colname="col2"> Aucune limite (peut changer dans les versions ultérieures) </td> 
   <td colname="col3"> Aucune limite (peut changer dans les versions ultérieures) </td> 
   <td colname="col4"> Aucune </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Valeurs spéciales </td> 
   <td colname="col2"> <p>« Aucun » : totaux à l’échelle du site qui n’avaient aucun référent durant la visite. </p> </td> 
   <td colname="col3"> <p>« Aucun » : totaux à l’échelle du site qui n’avaient aucun référent durant la visite. </p> </td> 
   <td colname="col4"> <p> Vide : équivalent à « Aucun », totaux à l’échelle du site qui n’avaient aucun référent durant la visite. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Remarques {#section_B83A3571D64E4E7792712FAF740D7955}

* Le référent, le type de référent et le domaine de référent sont définis au premier accès de la visite ou durant une visite lorsque le référent est externe (par exemple, si un visiteur quitte votre site, utilise un moteur de recherche, puis revient sur votre site avant l’expiration de la première visite). Ces valeurs sont définies en même temps et persistent pendant toute la visite.
* Les URL internes sont filtrées. Seuls les référents qui ne correspondent pas aux filtres d’URL internes figurent dans ce rapport.
* La mesure correspondante est appelée Instance du référent dans l’Ad Hoc Analysis.
* Les valeurs « Tapé/Marqué » ne sont pas incluses sur le rapport Référents. En d’autres termes, les visites à l’échelle du site ne correspondent pas aux visites sur ce rapport.

## Historique des rapports {#section_6C0FCEA9DAF04D97BA056E153B7E4628}

<table id="table_9DFA79EC6A5A48648F2FB5418E1752DB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Date </th> 
   <th colname="col2" class="entry"> Changement </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 16/1/2014 </td> 
   <td colname="col2"> Data Warehouse a été mis à jour pour correspondre à la logique utilisée par les Reports &amp; Analytics marketing. Auparavant, les mots-clés de recherche ne persistaient pas pendant la visite. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 19/6/2012 </td> 
   <td colname="col2"> <p> Avant juillet 2012, « Aucun » incluait tout le trafic mobile, les visites « Tapé/Marqué » et les visites sans code JavaScript. Depuis juillet 2012, « Aucun » comprend uniquement les accès sans code JavaScript sur la première page de la visite. </p> </td> 
  </tr> 
 </tbody> 
</table>

