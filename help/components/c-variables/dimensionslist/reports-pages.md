---
description: Classe les pages de votre site en fonction du niveau de trafic. Si votre interrogation porte sur les données quantitatives des pages, utilisez ce rapport en y ajoutant les mesures appropriées.
title: Pages
topic: Reports
uuid: 6435e262-e734-4c15-af5b-173799d5cc43
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Pages

Classe les pages de votre site en fonction du niveau de trafic. Si votre interrogation porte sur les données quantitatives des pages, utilisez ce rapport en y ajoutant les mesures appropriées.

## Attribution, expiration et valeurs spéciales {#section_4D8CE5E111DD48FBBDCF9B5A1F16E92E}

Remarque : dans les Reports &amp; Analytics, les mesures sur le rapport Pages ont recours à une attribution linéaire. Par exemple, les recettes sont fractionnées entre toutes les pages affichées avant un événement d’achat. Ceci peut porter à confusion pour certaines mesures censées se produire sur une seule page, comme par exemple l’ajout à un panier.

<table id="table_EC7423532C7E44DE97B7FC0321585A2B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col2" class="entry">Rapports &amp; <p>Analytics </p> </th> 
   <th colname="col3" class="entry"> Ad Hoc Analysis </th> 
   <th colname="col4" class="entry"> Data Warehouse </th> 
   <th colname="col5" class="entry"> Analysis Workspace </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Attribution des mesures </td> 
   <td colname="col2"> Linéaire </td> 
   <td colname="col3"> L’attribution est propre à chaque dimension. L’attribution par défaut est l’attribution Dernière touche, mais la dimension pagename constitue une exception. Si vous appliquez un événement personnalisé à pagename, l’attribution sera une attribution Correspondance exacte. </td> 
   <td colname="col4"> <p>Valeurs définies sur la même page </p> </td> 
   <td colname="col5"> <p>Valeurs définies sur la même page </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Valeurs Expire après </td> 
   <td colname="col2"> Page vue </td> 
   <td colname="col3"> Page vue </td> 
   <td colname="col4"> Page vue </td> 
   <td colname="col5"> Page vue </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Valeur Limites </td> 
   <td colname="col2"> <p>Les premières 500 000 visites uniques par mois + nouvelles valeurs avec trafic </p> </td> 
   <td colname="col3"> <p>Les premières 500 000 visites uniques par mois + nouvelles valeurs avec trafic </p> </td> 
   <td colname="col4"> Aucun </td> 
   <td colname="col5"> <p>Les premières 500 000 visites uniques par mois + nouvelles valeurs avec trafic </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Valeurs spéciales </td> 
   <td colname="col2"> <p>(Faible trafic) Représente les valeurs au-delà des 500 000 premières visites qui n’ont pas encore suffisamment de trafic pour être reportées. </p> </td> 
   <td colname="col3"> <p>(Faible trafic) Représente les valeurs au-delà des 500 000 premières visites qui n’ont pas encore suffisamment de trafic pour être reportées. </p> </td> 
   <td colname="col4"> Aucune </td> 
   <td colname="col5"> <p>(Faible trafic) Représente les valeurs au-delà des 500 000 premières visites qui n’ont pas encore suffisamment de trafic pour être reportées. </p> </td> 
  </tr> 
 </tbody> 
</table>

Dans les Reports &amp; Analytics, si vous appliquez un événement personnalisé en tant que mesure dans un rapport Pages, une attribution linéaire s’applique.

Ainsi, même si cet événement a été envoyé avec un appel s.tl(), il obtient l’attribution linéaire de tout appel s.t() précédent. Exemple :

| Nom de page | Page_event | Événements |
|---|---|---|
| Page 1 | **s.t()** |  |
| Page 1 | s.tl() | Événement 1 |
| Page 1 | s.tl() | Événement 1 |
| Page 1 | s.tl() | Événement 1 |
| Page 2 | **s.t()** |  |
| Page 2 | **s.t()** |  |
| Page 2 | s.tl() | Événement 1 |

Pour ce scénario, l’attribution suivante serait obtenue dans le rapport Pages :

| Pages | Pageviews | Événement 1 |
|---|---|---|
| Page 1 | 1 | 1+1+1+1/3 = 3.33 |
| Page 2 | 2 | 2/3 = 0.67 |

Même si l’événement est envoyé au moment d’un appel s.tl, la page vue avant l’envoi de l’événement (appel s.t()) obtient un crédit partiel.

## Remarques {#section_47B0F4746D4847AC9E8697127063F4D0}

* S’il n’existe aucun nom de page, l’URL est utilisée.
* Si vous avez un accès sans nom de page, URL de page ou liste d’événements (aucun événement commercial), celui-ci est exclu.
* Les ventilations sur les pages présentent toutes les pages qui ont une valeur permanente.

