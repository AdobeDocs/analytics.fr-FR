---
title: Lien personnalisé
description: Le nom du lien personnalisé.
feature: Dimensions
exl-id: c153f710-f03f-4be6-8e18-5ebf2ed80f01
source-git-commit: 5c1d50fa09b0fad228f24018de2b062d09b0fe5f
workflow-type: tm+mt
source-wordcount: '242'
ht-degree: 21%

---

# Lien personnalisé

La [dimension](overview.md) « Lien personnalisé » indique les noms des liens personnalisés implémentés sur votre site. Les liens personnalisés constituent un mécanisme de suivi flexible pour toute interaction qui n’est pas un téléchargement de fichier ou une navigation sortante. Les exemples courants incluent les clics sur les boutons, la navigation interne ou les interactions de formulaire. Cette dimension est utile lorsque vous souhaitez comprendre laquelle de ces interactions intéresse le plus les visiteurs.

## Renseignement de cette dimension avec des données

Cette dimension collecte des données de la chaîne de requête ](/help/implement/validate/query-parameters.md) dans les demandes d’image, en fonction de la valeur de la chaîne de requête `pe`. [`pev2`La chaîne de requête `pe` détermine la dimension de lien qui reçoit la valeur `pev2` :

* **Lien personnalisé** (cette page) : `lnk_o`
* **[Lien de téléchargement](download-link.md)** : `lnk_d`
* **[Lien de sortie](exit-link.md)** : `lnk_e`

Si `pev2` n’est pas fourni, l’URL du lien (`pev1`) est utilisée comme valeur de dimension à la place. Lorsqu’un nom de lien est explicitement fourni, la longueur maximale est de 100 octets. Les valeurs dérivées de l’URL du lien ne sont pas soumises à cette limite.

Pour remplir cette dimension à l’aide d’AppMeasurement, envoyez une demande d’image [`tl()`](/help/implement/vars/functions/tl-method.md) avec un argument de type lien de `"o"`. Définissez l’argument du nom du lien sur la valeur souhaitée :

```js
s.tl(true,"o","Example custom link");
```

## Éléments de dimension

Cette variable étant basée sur une chaîne personnalisée de votre implémentation, votre entreprise détermine les éléments de dimension. Adobe recommande de regrouper les liens en catégories significatives en fonction de vos besoins pour les rapports. Si aucun nom de lien n’est fourni, les éléments de dimension apparaissent plutôt sous la forme d’URL brutes. Ces URL brutes sont plus difficiles à interpréter dans les rapports. Par conséquent, fournissez un nom de lien descriptif chaque fois que possible.
