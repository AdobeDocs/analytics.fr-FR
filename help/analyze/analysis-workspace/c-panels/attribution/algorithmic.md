---
title: Attribution algorithmique
description: Détails sur le modèle d’attribution algorithmique dans Adobe Analytics.
translation-type: tm+mt
source-git-commit: 143cbed5f2159b7faab387e10896af836d0780f7

---


# Attribution algorithmique

Le modèle [d’](attribution.md) attribution algorithmique d’Analysis Workspace diffère des autres modèles en ce sens qu’il utilise des techniques statistiques pour attribuer le crédit entre les valeurs de dimension dans votre rapport ou tableau à structure libre. Comme tous les autres modèles d’attribution d’Analysis Workspace, il peut être utilisé sur n’importe quelle dimension ou mesure et prend en charge la segmentation et les ventilations illimitées et distribue 100 % des conversions aux dimensions du tableau (également appelées attribution fractionnelle).

L&#39;algorithme utilisé pour l&#39;attribution est basé sur le Dividend Harsanyi de la théorie du jeu coopératif. Le dividende de Harsanyi est une généralisation de la solution de valeur de Shapley (du nom de Lloyd Shapley, un économiste lauréat du prix Nobel) pour répartir le crédit entre les joueurs dans un jeu avec des contributions inégales au résultat.

À un niveau élevé, le calcul d’attribution du crédit de conversion pour chaque point de contact considère chacun des points de contact marketing dans une fenêtre de recherche comme une coalition d’acteurs auxquels un excédent doit être réparti équitablement. La répartition de l’excédent de chaque coalition est déterminée en fonction de l’excédent précédemment créé par chaque sous-coalition (ou des valeurs de dimension précédemment participantes) de manière récursive. Pour plus de détails, voir les documents originaux de John Harsanyi et de Lloyd Shapley :

* Shapley, Lloyd S. &quot;Une valeur pour les jeux en personne.&quot; *Contributions à la théorie des jeux 2.28*, 1953, pp. 307-317.
* Harsanyi, John C. &quot;Un modèle de négociation simplifié pour le jeu coopératif en personne.&quot; *International Economic Review 4.2*, 1963, p. 194-220.

> [!NOTE] Le résultat de l’attribution algorithmique diffère uniquement des autres modèles lorsque plusieurs points de contact existent dans la fenêtre de recherche donnée. Les conversions avec un seul point de contact reçoivent un crédit de 100 %, quel que soit le modèle d’attribution.
