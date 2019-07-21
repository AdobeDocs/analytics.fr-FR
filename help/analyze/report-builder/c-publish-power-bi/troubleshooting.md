---
description: Voici quelques-unes des difficultés courantes qui peuvent survenir lors de l’utilisation du Créateur de rapports avec Power BI.
seo-description: Voici quelques-unes des difficultés courantes qui peuvent survenir lors de l’utilisation du Créateur de rapports avec Power BI.
seo-title: Résolution des problèmes d'intégration de Power BI
title: Résolution des problèmes d'intégration de Power BI
uuid: c 1 e 7 e 164-4 bc 6-4513-9332-92 c 53 be 021 cc
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Résolution des problèmes d'intégration de Power BI

Voici quelques-unes des difficultés courantes qui peuvent survenir lors de l’utilisation du Créateur de rapports avec Power BI.

## Étape 1. Failure to publish to Power BI {#section_5B87DC1C302C4FD8AB9E4DD6B162DC9B}

Les classeurs planifiés qui nécessitent une publication sur Power BI dépendent du bon fonctionnement des services Power BI. Les deux principales raisons d’un échec de publication sont :

* Les services Power BI sont peut-être arrêtés.
* L’utilisateur qui a planifié le classeur ne dispose plus d’Informations d’identification valides pour son compte Microsoft.

Chaque tâche planifiée par le Créateur de rapports bénéficie de trois tentatives par exécution planifiée :

* Après l’échec de la première tentative, vous obtenez le message suivant : « Nous n’avons pas pu publier ce classeur planifié sur Microsoft Power BI. Une nouvelle tentative sera effectuée prochainement. »
* Après l’échec de la deuxième tentative, vous n’obtenez aucun message.
* Après l’échec de la troisième tentative, vous obtenez le message suivant : « Nous n’avons pas pu publier ce classeur planifié sur Microsoft Power BI. »

## Étape 2 : Broken visualizations in Power BI {#section_FFFE200D06F843B2AF093710FD678166}

Voici les principales raisons pour lesquelles vous pourriez obtenir des visualisations corrompues suite à la publication de requêtes du Créateur de rapports sur Power BI :

* Vous avez modifié une requête dans le Créateur de rapports, par exemple vous avez modifié des mesures ou des dimensions, puis vous l’avez à nouveau publiée sur Power BI. La modification des requêtes peut entraîner la corruption de vos visualisations.
* Vous avez supprimé une requête qui était utilisée dans une visualisation.

