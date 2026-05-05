---
title: Lien de téléchargement
description: Nom du lien de téléchargement.
feature: Dimensions
exl-id: 078014a2-1f09-4177-9575-b44c5da25816
source-git-commit: 418e8d467ca29267314e14fba99783d0cb3d05a9
workflow-type: tm+mt
source-wordcount: '242'
ht-degree: 28%

---

# Lien de téléchargement

La dimension [Lien de téléchargement](overview.md) indique les noms des liens de téléchargement implémentés sur votre site. Cette dimension est utile pour en savoir plus sur le comportement des visiteurs vis-à-vis des liens de téléchargement, par exemple :

* Les fichiers les plus fréquemment téléchargés à partir de votre site.
* Si certains fichiers sont téléchargés plus souvent pendant des périodes spécifiques.
* Indique si les visiteurs téléchargent différents types de fichiers lorsqu’ils sont proposés.

## Renseignement de cette dimension avec des données

Cette dimension collecte des données de la chaîne de requête ](/help/implement/validate/query-parameters.md) dans les demandes d’image, en fonction de la valeur de la chaîne de requête `pe`. [`pev2`La chaîne de requête `pe` détermine la dimension de lien qui reçoit la valeur `pev2` :

* **[Lien personnalisé](custom-link.md)** : `lnk_o`
* **Lien de téléchargement** (cette page) : `lnk_d`
* **[Lien de sortie](exit-link.md)** : `lnk_e`

Si `pev2` n’est pas fourni, l’URL du lien (`pev1`) est utilisée comme valeur de dimension à la place. Lorsqu’un nom de lien est explicitement fourni, la longueur maximale est de 100 octets. Les valeurs dérivées de l’URL du lien ne sont pas soumises à cette limite.

Pour remplir cette dimension à l’aide d’AppMeasurement, envoyez une demande d’image [`tl()`](/help/implement/vars/functions/tl-method.md) avec un argument de type lien de `"d"`. Définissez l’argument du nom du lien sur la valeur souhaitée :

```js
s.tl(true,"d","Example download link");
```

## Éléments de dimension

Cette variable étant basée sur une chaîne personnalisée de votre implémentation, votre entreprise détermine les éléments de dimension. Adobe recommande de regrouper les liens en catégories significatives en fonction de vos besoins pour les rapports. Si aucun nom de lien n’est fourni, les éléments de dimension apparaissent plutôt sous la forme d’URL brutes. Ces URL brutes sont plus difficiles à interpréter dans les rapports. Par conséquent, fournissez un nom de lien descriptif chaque fois que possible.
