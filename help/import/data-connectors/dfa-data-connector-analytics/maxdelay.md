---
title: maxDelay
description: Déterminez la durée maximale pendant laquelle AppMeasurement attend une réponse de DFA avant d’envoyer une demande d’image.
translation-type: tm+mt
source-git-commit: 4a6cfa479559a644588613bd127c5b45ee8787e6

---


# maxDelay

The `s.maxDelay` variable is used in the DFA data connector to determine the timeout period in contacting the DFA host. Si Adobe ne reçoit pas de réponse des serveurs DFA dans le délai spécifié défini dans cette variable, la connexion est interrompue et les données sont traitées normalement. Incluez cette variable dans votre implémentation si vous êtes concerné par le temps de réponse de DFA sur chaque page. Adobe recommande d’utiliser cette valeur pour déterminer la période d’expiration optimale.

Cette variable n’est utilisée que dans les implémentations utilisant le connecteur de données DFA. Même avec les implémentations utilisant DFA, cette variable est facultative.

## Délai maximal dans le lancement d’Adobe Experience Platform

Il n’existe pas de champ dédié dans Lancer pour utiliser cette variable. Utilisez l’éditeur de code personnalisé, en respectant la syntaxe AppMeasurement.

## s.maxDelay dans AppMeasurement et lancement de l’éditeur de code personnalisé

La `s.maxDelay` variable est un entier représentant le nombre de millisecondes pendant lesquelles AppMeasurement attend une réponse de DFA. Si AppMeasurement ne reçoit pas de réponse de DFA à temps, une demande d’image est envoyée à Adobe sans données DFA.

```js
s.maxDelay = 750;
```

## Propriétés

* L’augmentation du délai d’attente permet de collecter des données DFA supplémentaires, mais augmente aussi le risque de perte des données d’accès Analytics. Losing Analytics hit data happens when the user navigates away from the page during the `s.maxDelay` period.
* La réduction du temps d’attente réduit le risque de perte des données d’accès Analytics, mais peut réduire la quantité de données DFA envoyées avec les données d’accès.
* Losing DFA integration data happens when the `s.maxDelay` period does not accommodate enough time for the DFA host to respond.

> [!NOTE] Adobe ne contrôle pas le temps de réponse de DFA. Si vous rencontrez des problèmes cohérents même après avoir augmenté le délai maximal à un délai raisonnable, consultez l’administrateur de compte DFA de votre entreprise.
