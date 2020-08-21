---
title: Profondeur d’accès
description: Numéro de l’accès lors de la visite.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 75%

---


# Profondeur d’accès

La dimension « Profondeur d’accès » indique l’ordre des accès pendant la visite. Cette dimension est utile pour comprendre le moment où les visiteurs effectuent des actions sur votre site au cours de leur visite. La profondeur d’accès compte tous les types d’accès, y compris les vues de page ([`t()`](/help/implement/vars/functions/t-method.md)) et les accès de suivi des liens ([`tl()`](/help/implement/vars/functions/tl-method.md)).

## Renseignement de cette dimension avec des données

Cette dimension est prête à l’emploi pour toutes les implémentations. Cette dimension fonctionne si une suite de rapports contient des données.

## Éléments de Dimension

Dimension items include the string `"Hit Depth"` followed by a number representing the number of hits into the visit. The dimension item of `"Hit Depth 1"` represents the first hit of the visit, while the dimension item `"Hit Depth 8"` represents the 8th hit of the visit.

## Comparaison avec la profondeur de visite

La profondeur d’accès compte tous les types d’accès, y compris les vues de page et les accès de suivi des liens. Visit depth only increments for page view hits, _and_ the [Page](page.md) dimension item is not the same as the value on the previous page. La profondeur de visite est également une dimension basée sur la visite, ce qui signifie qu’elle a la même valeur pour tous les accès de la visite. Le tableau suivant illustre un exemple de visite et détaille la profondeur d’accès et la profondeur de visite :

| Séquence de page | Profondeur d’accès | Compte dans la profondeur de visite ? | Profondeur de visite |
| --- | --- | --- | --- |
| Page d’accueil | 1 | Oui | 4 |
| Page de produit | 2 | Oui | 4 |
| Page d’accueil | 3 | Oui | 4 |
| Clic sur lien personnalisé | 4 | Non (lien personnalisé) | 4 |
| Clic sur lien personnalisé | 5 | Non (lien personnalisé) | 4 |
| Page de produit | 6 | Oui | 4 |
| Clic sur lien personnalisé | 7 | Non (lien personnalisé) | 4 |
| Page de produit | 8 | Non (identique à la page précédente) | 4 |
