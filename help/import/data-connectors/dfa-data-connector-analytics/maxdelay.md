---
title: maxDelay
description: Déterminez la durée maximale pendant laquelle AppMeasurement attend une réponse de DFA avant d’envoyer une demande d’image.
translation-type: ht
source-git-commit: 4a6cfa479559a644588613bd127c5b45ee8787e6

---


# maxDelay

La variable `s.maxDelay` est principalement utilisée dans les connecteurs de données DFA pour déterminer le délai d’inactivité lors du contact de l’hôte DFA. Si Adobe ne reçoit pas de réponse des serveurs de DFA dans le délai spécifié qui est défini dans cette variable, la connexion est établie et les données sont traitées normalement. Incluez cette variable dans votre implémentation si le temps de réponse de DFA sur chaque page vous préoccupe. Adobe recommande d’utiliser cette valeur pour déterminer le délai d’expiration optimale.

Cette variable n’est utilisée que dans les implémentations utilisant le connecteur de données DFA. Même avec les implémentations utilisant DFA, cette variable est facultative.

## Variable Max Delay (Délai maximal) dans Adobe Experience Platform Launch

Il n’existe pas de champ dédié dans Launch pour utiliser cette variable. Utilisez l’éditeur de code personnalisé, en respectant la syntaxe AppMeasurement.

## s.maxDelay dans AppMeasurement et éditeur de code personnalisé Launch

La variable `s.maxDelay` est un entier représentant le nombre de millisecondes pendant lesquelles AppMeasurement attend une réponse de DFA. Si AppMeasurement ne reçoit pas de réponse de DFA à temps, une demande d’image est envoyée à Adobe sans données DFA.

```js
s.maxDelay = 750;
```

## Propriétés

* L’augmentation du délai d’attente permet de collecter des données DFA supplémentaires, mais augmente aussi le risque de perte des données d’accès Analytics. La perte de ces données Analytics survient lorsque l’utilisateur quitte la page pendant le délai `s.maxDelay`.
* La diminution du délai d’attente limite le risque de perte des données d’accès Analytics, mais peut diminuer le nombre de données DFA envoyées avec les données d’accès.
* La perte des données d’intégration DFA survient lorsque la période `s.maxDelay` ne permet pas à l’hôte DFA de répondre.

> [!NOTE] Adobe ne contrôle pas le temps de réponse de DFA. Si vous rencontrez des problèmes même après avoir augmenté le délai de la variable, contactez l’administrateur de compte DFA de votre société.
