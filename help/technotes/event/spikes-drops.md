---
title: Résolution des problèmes liés aux pics et aux baisses de données
description: Découvrez les raisons expliquant les hausses ou les baisses spectaculaires des rapports de tendance.
exl-id: 1a91f95e-818f-423d-9247-e0bb96bd0018
feature: Curate and Share, Data Configuration and Collection
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '853'
ht-degree: 100%

---

# Résolution des problèmes liés aux pics et aux baisses de données

Alors que votre site collecte des données, il existe de nombreux facteurs pouvant fortement altérer la collection des données ou la création de rapports. La liste suivante répertorie les potentielles explications de la forte diminution ou augmentation du trafic global ou de certaines variables.

En déterminant la cause et en progressant vers une solution, vous pouvez évaluer l’impact de l’événement sur les données et déterminer comment procéder. Pour de plus amples informations, rendez-vous sur la [page d’aperçu](overview.md).

## Baisses de trafic

Les baisses de trafic sont classées dans deux sections : données partielles et aucune donnée.

### Causes possibles de l’absence totale de données (rapports de zéros)

* **Latence de suite de rapports** : il arrive parfois qu’une suite de rapports subisse une [latence](../latency.md) due à un certain nombre de facteurs. De nombreux problèmes de latence sont résolus en quelques heures. Si une suite de rapports spécifique vous préoccupe, contactez l’assistance clientèle d’Adobe avec l’identifiant de la suite de rapports concernée.
* **Suppression de la mise en œuvre** : parfois, lorsqu’une entreprise apporte des modifications à la mise en œuvre ou restructure son site, la nouvelle mise en œuvre d’Analytics est négligée. Collaborez avec les développeurs de l’entreprise pour implémenter de nouveau le code du site.
* **Problème d’interface/de mise en cache d’Analytics** : dans de rares cas, le cache d’un navigateur contient des données non valides qui entraînent le renvoi de zéros dans tous les rapports. Effacez les cookies et le cache du navigateur pour résoudre le problème. Si l’effacement des cookies et du cache ne fonctionne pas, contactez l’assistance clientèle avec la période et le rapport manquants. L’assistance peut dupliquer le problème et fournir des informations supplémentaires.
* **Disponibilité d’Analytics** : consultez [status.adobe.com](https://status.adobe.com/products/1173/fr) pour tout problème lié à la collecte ou au traitement des données.

### Causes possibles de données partiellement manquantes ou de diminution du trafic

* **Changements d’implémentation** : utilisez le [débogueur](/help/implement/validate/debugger.md) pour vérifier que les dimensions de votre choix fonctionnent.
* **Diminution du trafic référent** : si une bannière publicitaire populaire ou un hyperlien sur un autre site est supprimé, cela peut entraîner une diminution spectaculaire du trafic. Déterminez la tendance de la dimension [Domaines référents](/help/components/dimensions/referring-domain.md) avant et après la baisse pour approfondir la recherche.
* **Problèmes de performance du site** : une mauvaise répartition du trafic par des équilibreurs de charge ou des problèmes de serveur hébergeant le site peut contribuer à une diminution des rapports Analytics. Collaborez avec l’équipe de l’entreprise chargée de gérer l’intégrité et l’état du site afin d’examiner les éventuels problèmes de performance.
* **Modifications du classement des référencements naturels** : le trafic peut éventuellement diminuer si un autre site supprime votre classement de référencement naturel pour certains de vos mots-clés. Cette diminution peut être particulièrement évidente si le site ne figure plus sur la première page des résultats de recherche. Déterminez la tendance de la dimension [Moteurs de recherche](/help/components/dimensions/search-engine.md) pour approfondir la recherche.
* **Changements dans la publicité PPC** : la modification des titres et descriptions des publicités pour les campagnes existantes peut affecter la note de qualité. En général, une note de qualité élevée signifie que le mot-clé déclenche des publicités dans une position supérieure et à un coût par clic moindre. Déterminez la tendance de la dimension [Mots-clés de recherche - payants](/help/components/dimensions/search-keyword.md) pour approfondir la recherche.

## Pics de trafic

Les pics de trafic sont classés dans deux sections : pratiquement deux fois plus de données et autres causes.

### Causes possibles du doublement exact ou approximatif des données attendues

* **Plusieurs demandes d’image au sein d’une implémentation** : si l’implémentation contient plus d’un appel de méthode [`t()`](/help/implement/vars/functions/t-method.md) par page, elle double efficacement toutes les données collectées. Utilisez le débogueur sur le site et recherchez plusieurs demandes d’image pour repérer les doublons.
* **Fichiers de source de données en double chargés** : si l’entreprise utilise des [sources de données](/help/import/data-sources/overview.md), un utilisateur de l’entreprise peut charger le même fichier deux fois vers Adobe Analytics. Le chargement de ce doublon permet de doubler efficacement les données dans les rapports, provoquant ainsi un pic de trafic.

### Autres causes possibles de l’augmentation du trafic

* **Robots ou robots d’indexation** : si vous constatez une augmentation importante et soudaine du trafic, commencez par vérifier la présence éventuelle d’un robot ou d’un robot d’indexation. Il est parfois difficile d’identifier les robots, car ils possèdent tous leur propre façon d’exécuter le code sur le site. Créez un rapport Data Warehouse à l’aide de l’adresse IP comme dimension pour identifier les adresses qui génèrent le plus de trafic. Vous pouvez ensuite utiliser des [règles de robots](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/bot-rules.md) ou une règle VISTA pour éliminer le trafic de robots des futurs rapports.
* **Campagnes lancées** : les actions marketing telles que les campagnes par e-mail ou l’optimisation du moteur de recherche peuvent potentiellement provoquer un pic de trafic sur le site. Déterminez la tendance de la dimension [Code de suivi](/help/components/dimensions/tracking-code.md) pour approfondir la recherche. Elle permet également de contacter l’équipe marketing pour s’assurer que le pic était intentionnel.
* **Causes environnementales ou circonstancielles** : le trafic sur le site est susceptible d’augmenter en cas de congé ou d’événement circonstanciel (un événement important dans lequel le site est une ressource connue ou des actions marketing résiduelles d’autres entreprises). Il est difficile de résoudre la cause exacte, car il existe un nombre quasi illimité de raisons circonstancielles expliquant l’augmentation du trafic. Ces causes comptent toutefois parmi les plus importantes à identifier pour que l’entreprise puisse en tirer parti et prendre des décisions professionnelles adaptées. Déterminer la tendance de la dimension [Page](/help/components/dimensions/page.md) ou [Référent](/help/components/dimensions/referrer.md) est probablement le meilleur point de départ pour identifier la source du trafic.

Si aucune des raisons ci-dessus n’est une cause potentielle d’augmentation ou de diminution du trafic sur le site, contactez l’assistance clientèle d’Adobe. L’assistance peut vous aider à localiser la source du pic ou de la baisse de trafic. Lors de la création de l’incident, indiquez à l’agent comment recréer un rapport spécifique qui illustre clairement le pic ou la baisse.
