---
description: La fidélité de la clientèle révèle les modèles d’achat des clients.
title: Fidélité de la clientèle
topic: Reports
uuid: 7dc30b57-7b18-4228-a6ab-6eb66b3d9402
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Fidélité de la clientèle

La fidélité de la clientèle révèle les modèles d’achat des clients.

Le rapport affiche les schémas des clients sur la base de quatre catégories de fidélité :

* N’est pas un client
* Nouveau client
* Client régulier
* Client fidèle

Bien que ce rapport affiche également des mesures n’ayant pas de lien avec les achats (événements personnalisés, événements de panier, etc.), les catégories sont toujours basées sur le nombre de commandes effectuées. Il se peut, par exemple, qu’un visiteur ait ajouté au rapport un événement personnalisé nommé Recherches internes. La ligne [!UICONTROL Client régulier] affichera le nombre de recherches internes effectuées par les visiteurs qui ont réalisé deux achats précédemment, et non le nombre de visiteurs qui ont effectué deux recherches internes.

**Traitement de la fidélité de la clientèle**

Les tableaux suivants illustrent de quelle façon Analysis Workspace, les Reports &amp; Analytics, les Ad Hoc Analysis et Data Warehouse traitent actuellement la fidélisation des clients :

<table id="table_E6A5CA96BE5C47F29F09688A4D41BC60"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col2" class="entry"> <p>Après le 19 mai 2016 </p> </th> 
   <th colname="col3" class="entry"> <p>Entre le 21 avril et le 19 mai 2016 </p> <p>(non applicable à Data Warehouse) </p> </th> 
   <th colname="col4" class="entry"> <p>Avant le 21 avril 2016 </p> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>N’est pas un client </p> </td> 
   <td colname="col2"> <p>Visiteurs n’ayant jamais effectué d’achat </p> </td> 
   <td colname="col3"> <p>Visiteurs qui ont effectué 0 achat d’ici la fin d’une visite. </p> </td> 
   <td colname="col4"> <p>Non disponible. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nouveau client </p> </td> 
   <td colname="col2"> <p>Visiteurs ayant effectué un seul achat </p> </td> 
   <td colname="col3"> <p>Visiteurs qui ont effectué 1 achat d’ici la fin d’une visite. </p> <p>(Si un achat a eu lieu, l’état du client est mis à jour lors de la prochaine visite après cet achat.) </p> </td> 
   <td colname="col4"> <p>Visiteurs qui ont effectué 0 achat d’ici la fin de cette visite. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Client régulier </p> </td> 
   <td colname="col2"> <p>Visiteurs ayant effectué 2 achats </p> </td> 
   <td colname="col3"> <p>Visiteurs ayant effectué 2 achats d’ici la fin de la visite au cours de laquelle ils ont effectué leur deuxième achat. </p> <p>(Si un achat a eu lieu, l’état du client est mis à jour lors de la prochaine visite après cet achat.) </p> </td> 
   <td colname="col4"> <p>Visiteurs ayant effectué 1 achat d’ici la fin de la visite au cours de laquelle ils ont effectué cet achat. </p> <p>(Si un achat a eu lieu, l’état du client est mis à jour lors de la prochaine visite après cet achat.) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Client fidèle </p> </td> 
   <td colname="col2"> <p>Visiteurs ayant effectué 3 achats et plus </p> </td> 
   <td colname="col3"> <p>Visiteurs ayant effectué 3 achats et plus d’ici la fin de la visite au cours de laquelle ils ont effectué leur achat le plus récent. </p> <p>(Si un achat a eu lieu, l’état du client est mis à jour lors de la prochaine visite après cet achat.) </p> </td> 
   <td colname="col4"> <p>Visiteurs ayant effectué 2 achats et plus d’ici la fin de la visite au cours de laquelle ils ont effectué leur achat le plus récent. </p> <p>(Si un achat a eu lieu, l’état du client est mis à jour lors de la prochaine visite après cet achat.) </p> </td> 
  </tr> 
 </tbody> 
</table>

| Version 14 – Fidélisation des clients (Actuel) |
|---|
| Nouveau client | 1 visite et 1 achat |
| Client régulier | Plus d’1 visite et 2 achats |
| Client fidèle | Plus d’1 visite et 3 achats et plus |

L’état de fidélité change immédiatement après l’événement d’achat au cours de la même visite. Par exemple, un nouveau client (1 achat) effectue un achat, puis s’inscrit ensuite au bulletin d’information, au cours de la même visite. L’événement d’inscription au bulletin d’information est considéré comme une interaction Client régulier, car l’état de fidélité du client a changé immédiatement une fois l’achat effectué.
