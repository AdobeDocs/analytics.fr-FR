---
title: Profondeur d’accès
description: Numéro de l’accès lors de la visite.
feature: Dimensions
exl-id: 84c27e3f-4228-4455-95bf-0239928337b5
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 94%

---

# Profondeur d’accès

La [dimension](overview.md) &quot;Profondeur d’accès&quot; indique le niveau d’un accès donné lors d’une visite. Cette dimension est utile pour comprendre le moment où les visiteurs effectuent des actions sur votre site au cours de leur visite. La profondeur d’accès compte tous les types d’accès, y compris les vues de page ([`t()`](/help/implement/vars/functions/t-method.md)) et les accès de suivi des liens ([`tl()`](/help/implement/vars/functions/tl-method.md)).

## Renseignement de cette dimension avec des données

Cette dimension est prête à l’emploi pour toutes les implémentations. Cette dimension fonctionne si une suite de rapports contient des données.

## Éléments de dimension

Les éléments de dimension comprennent la chaîne `"Hit Depth"` suivie d’un nombre représentant l’ordre d’accès lors de la visite. L’élément de dimension de `"Hit Depth 1"` représente le premier accès de la visite, tandis que l’élément de dimension `"Hit Depth 8"` représente le huitième accès de la visite.

## Comparaison avec la profondeur de visite

La profondeur d’accès compte tous les types d’accès, y compris les vues de page et les accès de suivi des liens. La profondeur de visite est uniquement incrémentée par les accès de type vue de page _et_ l’élément de dimension [Page](page.md) n’est pas le même que la valeur de la page précédente. La profondeur de visite est également une dimension basée sur la visite, ce qui signifie qu’elle a la même valeur pour tous les accès de la visite. Le tableau suivant illustre un exemple de visite et détaille la profondeur d’accès et la profondeur de visite :

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
