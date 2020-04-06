---
description: Adobe exige un préavis pour les nouvelles configurations de compte, les pics de trafic et les augmentations de trafic. Le matériel doit être alloué à l'avance afin de minimiser la latence et les impacts négatifs possibles sur l'ensemble du système.
title: Délai d’avance requis pour les augmentations de trafic
topic: Admin tools
uuid: aa3fb882-51b0-458f-917b-7c54d5659623
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Délai d’avance requis pour les augmentations de trafic

Adobe exige un préavis pour les nouvelles configurations de compte, les pics de trafic et les augmentations de trafic. Le matériel doit être alloué à l&#39;avance afin de minimiser la latence et les impacts négatifs possibles sur l&#39;ensemble du système.

L’allocation du matériel dépend des alertes envoyées au moyen de l’interface utilisateur des Reports &amp; Analytics.

>[!IMPORTANT] Adobe ne peut pas prendre en charge les demandes de modification du trafic « d’espace réservé ». Sauf indication contraire, respectez autant que possible le délai d’avance suggéré, y compris en n’envoyant pas d’alerte trop tôt. Voir [Prévision d’un pic de trafic](/help/admin/c-traffic-management/t-traffic-schedule-spike.md) ou [Indication d’une augmentation permanente du trafic](/help/admin/c-traffic-management/t-traffic-permanent.md).

Suivez les instructions suivantes pour déterminer à quel moment vous devez envoyer une alerte de trafic à l’avance :

## Délais d&#39;avance de l&#39;allocation matériel

<table id="table_A67CC3B164F740088797BD8913244E47">
 <thead>
  <tr>
   <th colname="col1" class="entry"> Estimations du trafic quotidien (accès) </th>
   <th colname="col2" class="entry"> <p>Délai d’avance requis (janvier à octobre) </p> </th>
   <th colname="col3" class="entry"> <p>Délai d’avance requis (novembre à décembre) </p> </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> Jusqu'à 1 000 000 </td>
   <td colname="col2"> Aucun délai d'avance requis </td>
   <td colname="col3"> Aucun délai d'avance requis </td>
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
   <td colname="col1"> <p>Plus de 25 000 000 </p> </td>
   <td colname="col2"> Un ou plusieurs mois </td>
  </tr>
 </tbody>
</table>

Autres points à prendre en compte :

* Si plusieurs suites de rapports commencent ou augmentent et correspondent aux nombres répertoriés ci-dessus, le délai d’avance s’applique sous forme de somme du trafic attendu pour chacune d’elles.
* Disposer des informations suivantes pour envoyer un changement de trafic :

   * Identifiant de suite de rapports
   * Estimation des accès par jour
   * Date d&#39;activation

* Des alertes client sont également nécessaires lorsque le trafic diminue ou qu’une suite de rapports est obsolète.

## Réallocation de matériel en raison d’un trafic non réalisé

Le matériel pour les nouveaux comptes, pics et augmentations de trafic sera réalloué si le trafic prévu dans l’alerte client ne se matérialise pas sous quatre semaines à partir de la « date d’activation ». Si le trafic est toujours attendu, une nouvelle alerte client doit être générée lorsque le trafic augmente.
