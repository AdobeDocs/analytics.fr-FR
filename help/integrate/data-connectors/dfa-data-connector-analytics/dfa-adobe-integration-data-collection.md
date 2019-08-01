---
description: L’illustration suivante présente le fonctionnement de la collecte des données.
keywords: DFA
seo-description: L’illustration suivante présente le fonctionnement de la collecte des données.
seo-title: Intégration Adobe Real - Time Data Collection
solution: Analytics
title: Intégration Adobe Real - Time Data Collection
topic: Connecteurs de données
uuid: 5 dce 319 c -7 d 4 b -4475-8 e 6 d-dc 5 c 972 a 82 e 9
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Intégration Adobe : Collecte de données en temps réel{#adobe-integration-real-time-data-collection}

L’illustration suivante présente le fonctionnement de la collecte des données.

![](assets/DFA_data_collection.png)

La portion de collecte de données de l’intégration Adobe commence quand le visiteur parvient à la page d’entrée (1). Le code de collecte de données Adobe s’exécutant sur la page d’entrée ne connaît pas l’historique du visiteur eu égard aux publicités diffusées. L’équipe Google DFA a coordonné un service s’exécutant sur le serveur DFA Floodlight afin d’autoriser le code Adobe à interroger les informations publicitaires au sujet du visiteur actuellement sur le site (2). Pour obtenir ces données, la balise image Adobe est temporairement retardée et les données sont demandées auprès du serveur Floodlight.

Une fois les données reçues (ou si cela prend trop de temps), l’accès est déclenché sur les serveurs de suivi Adobe (3).

Le module Integrate est un module Adobe JavaScript principal spécial qui retarde la balise image Adobe, en attendant la demande d’un tiers pendant une durée spécifique ( *`s.maxDelay`*). *`s.maxDelay`* définit la durée pendant laquelle le module Integrate attend les données du serveur DFA Floodlight avant de déclencher la balise image sur le navigateur du visiteur. Ce comportement est important, de sorte que les données de base du visiteur continuent à être collectées même quand les serveurs DFA Floodlight sont hors service ou lourdement chargés. Si les données Floodlight arrivent avant l’expiration de *`s.maxDelay`*, les données de suivi Adobe sont immédiatement déclenchées et contiennent les données DFA supplémentaires.

Quand le délai expire, le code de la page peut spécifier un événement Rapports et analyses Adobe, qui sera utilisé comme événement de dépassement de délai. Cet événement est utile pour diagnostiquer les problèmes d’intégration ou lors du réglage de *`s.maxDelay`*. En cas de dépassements de délai excessifs, augmentez *`s.maxDelay`*. *`s.maxDelay`* peut être défini comme étant trop élevé, dans quels cas les visiteurs risquent de quitter le site avant que *`s.maxDelay`* le minuteur ne soit arrivé à expiration. For more discussion on this topic, see [Tuning s.maxDelay](../dfa-data-connector-analytics/dfa-integration/dfa-tuning-s-maxlelay.md#concept-6deb28eee18e414db220d6009d449f0d).

Il arrive que le serveur Floodlight réagisse à des erreurs au sujet du visiteur. Ceci survient généralement lorsque le serveur Floodlight ne sait rien au sujet du visiteur, car celui-ci n’a encore vu aucune publicité ou qu’il n’a pas de cookie de visiteur DFA. Le code de page peut spécifier une variable de conversion personnalisée (eVar) qui collectera ces erreurs et peut contribuer à résoudre les problèmes de mise en œuvre ou à signaler les erreurs relatives à la transaction Google. Erreurs les plus courantes : aucun historique, aucun cookie, erreur de requête et désabonnement, comme décrit dans le tableau suivant :

| Erreur | Nom | Description |
|---|---|---|
| nh | Aucun historique | Le visiteur n’a affiché aucune publicité ni cliqué dessus. |
| nc | Aucun cookie | Le visiteur n’a pas de cookie de visiteur DFA. |
| qe | Erreur de requête | Erreur lors de l’interrogation des données pour le serveur Floodlight. |
| oo | Désabonné | Le visiteur a désactivé le suivi des clics et des impressions Google. |

