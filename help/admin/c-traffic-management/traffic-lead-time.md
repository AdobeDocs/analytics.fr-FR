---
description: Adobe requiert d’être informée à l’avance de la configuration de nouveaux comptes, ainsi que des pics et augmentations de trafic. Le matériel doit être alloué à l’avance afin de minimiser la latence et les impacts négatifs sur l’ensemble du système.
title: Délai d’avance requis pour les augmentations de trafic
topic: Admin tools
uuid: aa3fb882-51b0-458f-917b-7c54d5659623
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Délai d’avance requis pour les augmentations de trafic

Adobe requiert d’être informée à l’avance de la configuration de nouveaux comptes, ainsi que des pics et augmentations de trafic. Le matériel doit être alloué à l’avance afin de minimiser la latence et les impacts négatifs sur l’ensemble du système.

L’allocation du matériel dépend des alertes envoyées au moyen de l’interface utilisateur des Reports &amp; Analytics.

> [!IMPORTANT] Adobe ne peut pas prendre en charge les demandes de modification du trafic « d’espace réservé ». Sauf indication contraire, respectez autant que possible le délai d’avance suggéré, y compris en n’envoyant pas d’alerte trop tôt. Voir [Prévision d’un pic de trafic](/help/admin/c-traffic-management/t-traffic-schedule-spike.md) ou [Indication d’une augmentation permanente du trafic](/help/admin/c-traffic-management/t-traffic-permanent.md).

Suivez les directives suivantes pour déterminer à quel moment envoyer une alerte de trafic :

## Délais d’avance de l’allocation matériel

<table id="table_A67CC3B164F740088797BD8913244E47">
 <thead>
  <tr>
   <th colname="col1" class="entry"> Estimations (accès) du trafic QUOTIDIEN </th>
   <th colname="col2" class="entry"> <p>Délai d’avance requis (janvier à octobre) </p> </th>
   <th colname="col3" class="entry"> <p>Délai d’avance requis (novembre à décembre) </p> </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> Jusqu’à 1 000 000 </td>
   <td colname="col2"> Pas de délai d’avance requis </td>
   <td colname="col3"> Pas de délai d’avance requis </td>
  </tr>
  <tr>
   <td colname="col1"> 1 000 000 - 5 000 000 </td>
   <td colname="col2"> Deux jours OUVRABLES </td>
   <td colname="col3" morerows="3"> Toute augmentation de trafic prévue pour novembre-décembre doit être soumise au plus tard le 1er septembre. Cela permet de conserver un délai pour acheter de la capacité, le cas échéant, pour s’adapter au trafic de la période des fêtes. </td>
  </tr>
  <tr>
   <td colname="col1"> 5 000 000 - 10 000 000 </td>
   <td colname="col2"> Une semaine calendaire </td>
  </tr>
  <tr>
   <td colname="col1"> 10 000 000 - 25 000 000 </td>
   <td colname="col2"> Deux semaines calendaires </td>
  </tr>
  <tr>
   <td colname="col1"> <p>Au-dessus de 25 000 000 </p> </td>
   <td colname="col2"> Un ou plusieurs mois </td>
  </tr>
 </tbody>
</table>

Autres éléments à prendre en compte :

* Si vous possédez plusieurs suites de rapports commençant aux nombres répertoriés ci-dessus, ou les atteignant par ajouts, le délai d’avance s’applique à ces suites sous la forme de la somme du trafic attendu pour chacune d’elle.
* Les informations suivantes sont requises pour soumettre un changement de trafic :

   * Identifiant de suite de rapports
   * Estimation des accès par jour
   * Date d’activation

* Les alertes client sont également requises lorsque le trafic augmente ou qu’une suite de rapports devient obsolète.

## Réallocation de matériel en raison d’un trafic non réalisé

Le matériel pour les nouveaux comptes, pics et augmentations de trafic sera réalloué si le trafic prévu dans l’alerte client ne se matérialise pas sous quatre semaines à partir de la « date d’activation ». Si le trafic est toujours attendu, une nouvelle alerte client doit être générée lorsque le trafic augmente.
