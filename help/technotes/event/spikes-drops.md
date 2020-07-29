---
title: Résolution des pics et des pertes de données
description: Découvrez les raisons possibles pour lesquelles vous pouvez constater des augmentations ou des diminutions spectaculaires des rapports de tendances.
translation-type: tm+mt
source-git-commit: 178e372e63c436268a1f7028d986504983430b2f
workflow-type: tm+mt
source-wordcount: '855'
ht-degree: 2%

---


# Résolution des pics et des pertes de données

Alors que votre site collecte des données, il existe de nombreux facteurs pouvant fortement altérer la collection des données ou la création de rapports. Vous trouverez ci-dessous une liste d’explications possibles sur les raisons pour lesquelles certaines variables ou le trafic global augmente ou diminue considérablement.

À mesure que vous déterminez la cause et que vous vous dirigez vers une résolution, vous pouvez évaluer l’impact du événement sur vos données et déterminer comment vous souhaitez procéder. See the [overview page](overview.md) for more information.

## Baisses de trafic

Les chutes de trafic sont classées en deux sections : données partielles et zéro.

### Causes potentielles de données complètement manquantes (zéros rapports)

* **Latence** de la suite de rapports : Il arrive parfois qu’une suite de rapports connaisse une [latence](../latency.md) en raison de plusieurs facteurs. De nombreux problèmes de latence sont résolus en quelques heures. Si une suite de rapports spécifique vous préoccupe, contactez le service à la clientèle d’Adobe avec l’identifiant de la suite de rapports concernée.
* **Suppression** de la mise en oeuvre : Parfois, lorsqu’une entreprise modifie ou restructure son site, la réimplémentation d’Analytics est ignorée. Collaborez avec les développeurs de votre entreprise pour réimplémenter le code de votre site.
* **Problème** d’interface/de mise en cache d’Analytics : Dans de rares cas, le cache d’un navigateur contient des données non valides qui font que tous les rapports renvoient des zéros. Effacez les cookies et le cache du navigateur pour résoudre le problème. Si l’effacement de vos cookies/cache ne fonctionne pas, contactez le service à la clientèle pour connaître le rapport et la plage de dates manquants ; ils peuvent duplicata la question et fournir des renseignements supplémentaires.
* **Disponibilité** Analytics : Consultez [status.adobe.com](https://status.adobe.com/products/1173/) pour connaître les problèmes éventuels liés à la collecte ou au traitement des données.

### Cause potentielle de données partiellement manquantes ou de trafic réduit

* **Changements** d’implémentation : Utilisez le [débogueur](/help/implement/validate/debugger.md) pour vérifier que les dimensions de votre choix fonctionnent.
* **Diminution du trafic** de référence : Si une bannière publicitaire ou un hyperlien très utilisé sur un autre site est supprimé, cela peut entraîner une diminution spectaculaire du trafic. Déterminer la tendance de la dimension des domaines [](/help/components/dimensions/referring-domain.md) référents avant et après la recherche.
* **Problèmes** de performances du site : Une distribution incorrecte du trafic par le biais d’équilibreurs de charge ou de problèmes de serveur hébergeant votre site peut contribuer à une diminution du rapports Analytics. Collaborez avec l’équipe de votre organisation chargée de gérer l’intégrité et la santé de votre site afin d’étudier les éventuels problèmes de performances.
* **Modifications du classement** des recherches naturelles : Le trafic peut diminuer si un autre site supprime votre classement de recherche naturelle pour certains de vos mots-clés. Cette diminution peut être particulièrement évidente si votre site ne figure plus sur la première page des résultats de la recherche. Analysez de plus près la dimension des moteurs [de](/help/components/dimensions/search-engine.md) recherche.
* **Changements dans la publicité** PPC : La modification des titres et descriptions des publicités pour les campagnes existantes peut affecter votre note de qualité. En général, un score de qualité élevé signifie que votre mot-clé déclenche des publicités dans une position supérieure et à un coût par clic moindre. Analyser plus précisément les tendances des mots-clés de [recherche - dimension payée](/help/components/dimensions/search-keyword.md) .

## Pics de trafic

Les pics de trafic sont classés en deux sections : données de doublon proche et autres causes.

### Causes potentielles de la proximité ou du doublon exact des données attendues

* **Plusieurs demandes d’image au sein d’une implémentation**: Si votre implémentation contient plusieurs appels de [`t()`](/help/implement/vars/functions/t-method.md) méthode par page, elle doublon effectivement toutes les données collectées. Utilisez le débogueur sur votre site et recherchez plusieurs demandes d’image pour capturer des duplicata.
* **Fichiers de source de données de Duplicata téléchargés**: Si votre organisation utilise des sources [de](/help/import/c-data-sources/datasrc-home.md)données, un utilisateur de votre organisation peut télécharger le même fichier deux fois vers Adobe Analytics. L’exécution de ce duplicata de transfert doublon efficacement ces données dans le rapports, provoquant ainsi un pic de trafic.

### Autres causes potentielles de l&#39;augmentation du trafic

* **Araignées ou robots**: Si vous voyez une forte augmentation soudaine du trafic, la première chose à rechercher est la possibilité d&#39;une araignée ou d&#39;un robot. L’identification des robots peut parfois s’avérer délicate, dans la mesure où chacun dispose de sa propre manière d’exécuter du code sur votre site. Créez un rapport Data warehouse utilisant l’IP comme dimension pour identifier les adresses qui génèrent le plus de trafic. Vous pouvez ensuite utiliser des règles [de](/help/admin/admin/bot-removal/bot-rules.md) robots ou une règle VISTA pour éliminer le trafic de robots du rapports futur.
* **Campagnes** lancées : Les actions marketing telles que les campagnes par courriel ou l&#39;optimisation des moteurs de recherche peuvent potentiellement provoquer un pic de trafic sur votre site. Analyser plus précisément la tendance de la dimension du code [de](/help/components/dimensions/tracking-code.md) suivi. Il peut également vous aider à contacter votre équipe marketing pour vous assurer que le pic a été intentionnel.
* **Causes** environnementales ou circonstancielles : Si un jour férié ou un événement circonstanciel s’est produit (événement important où votre site est une ressource connue ou efforts marketing résiduels d’autres organisations), le trafic peut augmenter sur votre site. Il est difficile de résoudre la cause exacte, car il existe un nombre quasi illimité de raisons circonstancielles pour lesquelles le trafic peut augmenter. Ces causes sont toutefois parmi les plus importantes à déterminer pour que votre entreprise puisse en tirer parti et prendre des décisions commerciales en conséquence. La tendance de la dimension [Page](/help/components/dimensions/page.md) ou [Parrain](/help/components/dimensions/referrer.md) est probablement le meilleur endroit où début pour déterminer la source du trafic.

Si aucune des raisons ci-dessus n’est une cause potentielle d’augmentation ou de diminution du trafic sur votre site, contactez le service à la clientèle de l’Adobe. Ils peuvent vous aider à localiser la source du pic de trafic ou de la chute. Lors de la création de l&#39;incident, indiquez à l&#39;agent comment recréer un rapport spécifique qui illustre clairement le pic ou la baisse.
