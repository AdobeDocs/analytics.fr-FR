---
description: Une mise en œuvre réussie de DFA implique d’optimiser s.maxDelay pour votre site.
keywords: DFA
seo-description: Une mise en œuvre réussie de DFA implique d’optimiser s.maxDelay pour votre site.
seo-title: Réglage de s.maxDelay
solution: Analytics
title: Réglage de s.maxDelay
topic: Connecteurs de données
uuid: 7640 af 26-6 ac 6-427 e -9 cfc -932 c 86 ccf 5 ab
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# Réglage de s.maxDelay{#tuning-s-maxdelay}

Une mise en œuvre réussie de DFA implique d’optimiser s.maxDelay pour votre site.

En général, la décision d'augmenter ou de réduire *`s.maxDelay`* implique un compromis entre l'obtention d'autres données de visiteur DFA et la mise en danger de la collecte des données des visiteurs Adobe. Increasing *`s.maxDelay`* obtains more DFA visitor data, but (placed excessively high) could endanger the collection of Adobe visitor data. Si vous réduisez s.maxDelay, la collecte des données sur les visiteurs d’Adobe est garantie, mais des données sur les visiteurs de DFA risquent d’être omises.

*`s.maxDelay`* ne se contente pas d’encapsuler le temps pris par les communications réseau pour contacter DFA ; il représente également les délais qui s’écoulent avant que le navigateur ne déclenche et n’évalue le code JavaScript sur lequel reposent ces communications. Cela est dû au fait que le module Integrate démarre le *`s.maxDelay`* minuteur après avoir inséré l'élément HTML dans le modèle DOM qui extrait les données du serveur DFA Floodlight. Le temps pris par le navigateur pour réellement initier la demande HTTP d’après ce nouvel élément HTML varie en fonction des autres images ou des fichiers JavaScript qui se chargent simultanément, de la vitesse de l’ordinateur des visiteurs et des mises en œuvre de navigateur spécifiques. En outre, lorsque les données JSON sont récupérées auprès du serveur DFA Floodlight, le code JavaScript doit être évalué par le navigateur. Ceci dépend entièrement du navigateur et peut être retardé si la quantité de code JavaScript s’exécutant simultanément est conséquente ou s’il y a plusieurs demandes JavaScript asynchrones.

Ainsi, *`s.maxDelay`* doit être défini en fonction de la complexité de la page d’entrée et du délai réseau avec DFA. Sur certains sites, l’une des manières possibles de réduire la complexité de la page consiste à déclencher le code de collecte Adobe au début du chargement de la page, de sorte que le navigateur soit moins occupé au moment où le serveur Floodlight est appelé.

La variable de dépassement de délai est obligatoire lors du réglage de *`s.maxDelay`* car elle est incrémentée chaque fois que le délai d'expiration s. maxdelay est atteint. Lorsque vous décidez d'augmenter ou diminuer *`s.maxDelay`* , nous recommandons de suivre ce processus :

1. Collectez plusieurs jours de données avec *`s.maxDelay`* une valeur particulière.
1. Exécutez un [!DNL Daily Unique Visitors Report] pour la période.
1. Run the [!DNL Timeout Event Report] to check the number of timeouts that are coming through. N’oubliez pas qu’un dépassement de délai est collecté une seule fois par visiteur.

Avec les chiffres dont vous disposez, calculez :

```
Timeout Percentage = [Step 3] / [Step 2] * 100
```

Le pourcentage de dépassement de délai prend actuellement en compte tous les visiteurs sur le site. Certains de ces visiteurs peuvent en fait n’avoir aucune connexion avec DFA ; le dépassement de délai est donc trompeur. Pour améliorer ce calcul, une autre analyse consiste à prendre en compte seulement les visiteurs uniques sur les pages avec le paramètre `clickThroughParam` défini (par exemple, `?CID=1`). Les résultats seront ainsi plus précis.

Si le pourcentage de dépassement de délai est très faible, envisagez de réduire *`s.maxDelay`*. S’il est très élevé, augmentez *`s.maxDelay`*. When decreasing *`s.maxDelay`*, you will want to rerun the [!DNL Timeout Report] to ensure that timeouts have not dramatically increased. When increasing *`s.maxDelay`*, you will want to run a [!DNL Page Views Report] to make sure page views aren’t falling out due to lost data. Each time *`s.maxDelay`* is changed observe the data for several days in order to ensure that the data represents a trend, and not just a day-to-day fluctuation.

The optimal setting for *`s.maxDelay`* is the point at which the timeout percentage is minimized while Page Views do not drop off.

Les dépassements de délai devraient normalement diminuer quand vous passerez à la version 2.0 de l’intégration, en raison de l’élimination des redirections 302. Les premières conclusions obtenues des utilisateurs de la version bêta ont démontré une réduction constante des dépassements de délai ; davantage de données DFA sont ainsi collectées.
