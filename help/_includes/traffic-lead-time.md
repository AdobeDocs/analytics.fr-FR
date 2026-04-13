---
description: Adobe nécessite un préavis pour les nouvelles configurations de compte, les pics de trafic et les augmentations de trafic. Le matériel doit être alloué à l’avance afin de minimiser la latence et les éventuels effets indésirables sur le système dans son ensemble.
title: Délai d’avance requis pour les augmentations de trafic
feature: Report Suite Settings
exl-id: fb428f8d-9dff-43a6-a1e8-1a892cbed7ac
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: ht
source-wordcount: '325'
ht-degree: 100%

---

# Délai d’avance requis pour les augmentations de trafic

Adobe nécessite un préavis pour les nouvelles configurations de compte, les pics de trafic et les augmentations de trafic. Le matériel doit être alloué à l’avance afin de minimiser la latence et les éventuels effets indésirables sur le système dans son ensemble.

>[!IMPORTANT]
>
> Adobe ne peut pas prendre en charge les demandes de modification du trafic « d’espace réservé ». Sauf indication contraire, respectez autant que possible le délai d’avance suggéré, y compris en n’envoyant pas d’alerte trop tôt.

Suivez les instructions suivantes pour déterminer la durée à l’avance à laquelle vous devez soumettre une alerte de trafic :

## Délais de l’allocation matériel


<table id="table_A67CC3B164F740088797BD8913244E47">
 <thead>
  <tr>
   <th colname="col1" class="entry"> Type de modification du trafic </th>
   <th colname="col2" class="entry"> Délai requis </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> Configuration de nouveau compte </td>
   <td colname="col2"> <ul><li>3 jours ouvrables</li></ul></td>
  </tr>
  <tr>
   <td colname="col1"> Pic de trafic ou augmentation soudaine et permanente du trafic allant jusqu’à 25 % du volume quotidien moyen par rapport aux 30 derniers jours</td>
   <td colname="col2"> <ul><li>Suites de rapports avec moins de 100 millions d’accès par jour : aucune notification requise</li><li>Suites de rapports avec plus de 100 millions d’accès par jour : 5 jours ouvrables</li></ul></td>
  </tr>
  <tr>
   <td colname="col1"> Pic de trafic ou augmentation soudaine et permanente du trafic de plus de 25 % du volume quotidien moyen par rapport aux 30 derniers jours</td>
   <td colname="col2"> <ul><li>5 jours ouvrables</li></ul></td>
  </tr>
  <tr>
   <td colname="col1"> Événements de vacances d’octobre à décembre </td>
   <td colname="col2"> <ul><li>Un mois calendaire</li></ul> </td>
  </tr>
 </tbody>
</table>

Autres éléments à prendre en compte :

* Si plusieurs suites de rapports démarrent ou augmentent en fonction des nombres répertoriés ci-dessus, le délai s’applique en tant que somme du trafic attendu pour chacune d’elles.
* Vous devez disposer des informations suivantes pour envoyer une modification de trafic :

   * Identifiant de suite de rapports
   * Estimation des accès par jour
   * Date de mise en production

* Des alertes clientèle sont également nécessaires lorsque le trafic diminue ou qu’une suite de rapports est obsolète.

## Réallocation de matériel en raison d’un trafic non réalisé

Le matériel pour les nouveaux comptes, pics et augmentations de trafic sera réalloué si le trafic prévu dans l’alerte client ne se matérialise pas sous quatre semaines à partir de la « date d’activation ». Si le trafic est toujours attendu, une nouvelle alerte client doit être générée lorsque le trafic augmente.
