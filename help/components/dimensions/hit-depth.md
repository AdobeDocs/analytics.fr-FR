---
title: Profondeur d’accès
description: Nombre d’accès à la visite.
translation-type: tm+mt
source-git-commit: 0328de560185e716a3913080feda9cd078e0f206
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 7%

---


# Profondeur d’accès

La dimension &quot;Profondeur d’accès&quot; indique la profondeur d’une visite donnée. Cette dimension est utile pour comprendre jusqu’où les visiteurs effectuent des actions sur votre site au cours d’une visite. La profondeur d’accès compte tous les types d’accès, y compris les vues de page ([`t()`](/help/implement/vars/functions/t-method.md))et les accès de suivi de liens ([`tl()`](/help/implement/vars/functions/tl-method.md)).

## Renseigner cette dimension avec des données

Cette dimension est prête à l’emploi pour toutes les implémentations. Si une suite de rapports contient des données, cette dimension fonctionne.

## Valeurs de dimension

Les valeurs de dimension comprennent la chaîne `"Hit Depth"` suivie d’un nombre représentant le nombre d’accès à la visite. La valeur de dimension de `"Hit Depth 1"` représente le premier accès de la visite, tandis que la valeur de dimension `"Hit Depth 8"` représente le huitième accès de la visite.

## Comparaison avec la profondeur de visite

La profondeur d’accès compte tous les types d’accès, y compris la vue de page et le suivi des liens. La profondeur de visite est incrémentée uniquement pour les accès de vue de page _et la valeur de dimension_ Page [](page.md) n’est pas la même que celle de la page précédente. La profondeur de visite est également une dimension basée sur les visites, ce qui signifie qu’elle est la même valeur pour tous les accès de la visite. Le tableau suivant présente un exemple de visite et explique comment il considère la profondeur d’accès + profondeur de visite :

| Séquence de page | Profondeur d’accès | Comptabilisation de la profondeur de visite ? | Profondeur de visite |
| --- | --- | --- | --- |
| Page d&#39;accueil | 1 | Oui | 4 |
| Page de produit | 2 | Oui | 4 |
| Page d&#39;accueil | 3 | Oui | 4 |
| clic sur le lien personnalisé | 4 | Non (lien personnalisé) | 4 |
| clic sur le lien personnalisé | 5 | Non (lien personnalisé) | 4 |
| Page de produit | 6 | Oui | 4 |
| clic sur le lien personnalisé | 7 | Non (lien personnalisé) | 4 |
| Page de produit | 8 | Non (identique à la page précédente) | 4 |
