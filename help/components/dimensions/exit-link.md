---
title: Lien de sortie
description: Le nom du lien de sortie.
feature: Dimensions
exl-id: 090d5fee-4b35-4be7-866c-5ef1d1c4c0a6
source-git-commit: 418e8d467ca29267314e14fba99783d0cb3d05a9
workflow-type: tm+mt
source-wordcount: '225'
ht-degree: 22%

---

# Lien de sortie

La [dimension](overview.md) « Lien de sortie » indique les noms des liens de sortie implémentés sur votre site. Les liens de sortie effectuent le suivi des clics sortants qui éloignent les visiteurs du domaine actuel. Cette dimension est utile lorsque vous souhaitez comprendre les liens sortants sur lesquels les utilisateurs cliquent le plus fréquemment.

## Renseignement de cette dimension avec des données

Cette dimension collecte des données de la chaîne de requête ](/help/implement/validate/query-parameters.md) dans les demandes d’image, en fonction de la valeur de la chaîne de requête `pe`. [`pev2`La chaîne de requête `pe` détermine la dimension de lien qui reçoit la valeur `pev2` :

* **[Lien personnalisé](custom-link.md)** : `lnk_o`
* **[Lien de téléchargement](download-link.md)** : `lnk_d`
* **Lien de sortie** (cette page) : `lnk_e`

Si `pev2` n’est pas fourni, l’URL du lien (`pev1`) est utilisée comme valeur de dimension à la place. Lorsqu’un nom de lien est explicitement fourni, la longueur maximale est de 100 octets. Les valeurs dérivées de l’URL du lien ne sont pas soumises à cette limite.

Pour remplir cette dimension à l’aide d’AppMeasurement, envoyez une demande d’image [`tl()`](/help/implement/vars/functions/tl-method.md) avec un argument de type lien de `"e"`. Définissez l’argument du nom du lien sur la valeur souhaitée :

```js
s.tl(true,"e","Example exit link");
```

## Éléments de dimension

Cette variable étant basée sur une chaîne personnalisée de votre implémentation, votre entreprise détermine les éléments de dimension. Adobe recommande de regrouper les liens en catégories significatives en fonction de vos besoins pour les rapports. Si aucun nom de lien n’est fourni, les éléments de dimension apparaissent plutôt sous la forme d’URL brutes. Ces URL brutes sont plus difficiles à interpréter dans les rapports. Par conséquent, fournissez un nom de lien descriptif chaque fois que possible.
