---
description: Affiche les liens sur lesquels les visiteurs cliquent le plus souvent et qui pointent vers des sites externes. Ces liens pointent généralement vers des sites de partenaires ou de sociétés affiliées. Il peut toutefois s’agir de tout emplacement sur lequel vous avez implémenté un lien externe. Vous pouvez utiliser ce rapport pour afficher les liens de sites affiliés les plus populaires ou faciliter la validation du nombre de renvois que vous fournissez, selon les indications de vos partenaires.
title: Liens de sortie
topic: Reports
uuid: e1452f04-389d-4aa3-8763-732880284302
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Liens de sortie

Affiche les liens sur lesquels les visiteurs cliquent le plus souvent et qui pointent vers des sites externes. Ces liens pointent généralement vers des sites de partenaires ou de sociétés affiliées. Il peut toutefois s’agir de tout emplacement sur lequel vous avez implémenté un lien externe. Vous pouvez utiliser ce rapport pour afficher les liens de sites affiliés les plus populaires ou faciliter la validation du nombre de renvois que vous fournissez, selon les indications de vos partenaires.

Il convient de respecter certaines exigences pour que cette page soit renseignée correctement :

* Si vous utilisez le suivi manuel de liens personnalisés, une requête *`s.tl()`* doit être déclenchée en définissant le paramètre du milieu sur *e*.

* Si vous utilisez le suivi automatique de liens personnalisés, toutes les exigences doivent être respectées :
* 

   * [s.trackExternalLinks](https://marketing.adobe.com/resources/help/en_US/sc/implement/c_trackexlinks.html) doit être défini sur *true*.

   * Le lien sur lequel l’utilisateur a cliqué ne doit correspondre à aucune valeur de la variable [s.linkInternalFilters](https://marketing.adobe.com/resources/help/en_US/sc/implement/c_linkinfilters.html).
   * Si la variable [s.linkInternalFilters](https://marketing.adobe.com/resources/help/en_US/sc/implement/c_linkinfilters.html) est implémentée, le lien externe doit correspondre à au moins l’une des valeurs définies.

* Si l’une des exigences ci-dessus n’est pas respectée, l’accès n’est pas renseigné dans ce rapport.

* 
* Comme c’est le cas avec les accès de suivi de liens personnalisés, la variable [s.pageName](https://marketing.adobe.com/resources/help/en_US/sc/implement/c_pagename.html) est supprimée de la requête d’image afin d’éviter la croissance incontrôlée des pages vues.
* Ce rapport est visible en tant que rapport de tendance et avec classement.
* Ce rapport peut utiliser un filtre de recherche afin de localiser des éléments spécifiques.
* Vous pouvez créer des [répartitions](/help/analyze/reports-analytics/reports-customize/breakdowns.md) avec toute autre variable au moyen des outils d’administration.
* [Les instances](/help/components/c-variables/c-metrics/metrics-instance.md) sont les seules mesures disponibles par défaut dans ce rapport. Elles comptabilisent le nombre de fois où le lien de sortie est déclenché.
* Vous pouvez activer des visiteurs quotidiens, hebdomadaires, mensuels et trimestriels pour ce rapport. Sachez toutefois que seul un représentant Adobe est habilité à les activer, moyennant paiement. L’activation de visiteurs uniques pour toute variable de suivi de liens personnalisés augmente sensiblement la latence pour la suite de rapports.

