---
description: valeur nulle
title: Attribution algorithmique
uuid: bb345642-4f45-4fb8-82d0-803248dd52ea
translation-type: tm+mt
source-git-commit: b5418e6321b09ddbab36e0052f75f36067086e3e

---


# Attribution algorithmique

![Algorithmique](assets/algorithmic.png)

Le modèle [d’](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/attribution/attribution.html#attribution-models) attribution algorithmique d’Analysis Workspace diffère des autres modèles de l’IQ d’attribution en ce sens qu’il utilise des techniques statistiques pour allouer du crédit sur les valeurs de dimension dans votre rapport ou tableau à structure libre. Comme tous les autres modèles d’attribution d’Analysis Workspace, il peut être utilisé sur n’importe quelle dimension ou mesure et prend en charge la segmentation et les ventilations illimitées et distribue 100 % des conversions aux dimensions du tableau (également appelées attribution fractionnelle).

L&#39;algorithme utilisé pour l&#39;attribution est basé sur le Dividend Harsanyi de la théorie du jeu coopératif. Le dividende de Harsanyi est une généralisation de la solution de valeur de Shapley (du nom de Lloyd Shapley, un économiste lauréat du prix Nobel) pour répartir le crédit entre les joueurs dans un jeu avec des contributions inégales au résultat.

À un niveau élevé, le calcul d’attribution du crédit de conversion pour chaque point de contact considère chacun des points de contact marketing dans une fenêtre de recherche comme une coalition d’acteurs auxquels un excédent doit être réparti équitablement. La répartition de l’excédent de chaque coalition est déterminée en fonction de l’excédent précédemment créé par chaque sous-coalition (ou des valeurs de dimension précédemment participantes) de manière récursive. Pour plus de détails, veuillez consulter les documents originaux de John Harsanyi et de Lloyd Shapley :

* Shapley, Lloyd S. &quot;Une valeur pour les jeux en personne.&quot; Contributions à la théorie des jeux 2.28 (1953) : 307-317.

* Harsanyi, John C. &quot;Un modèle de négociation simplifié pour le jeu coopératif en personne.&quot; Examen économique international 4.2 (1963) : 194-220.

*Remarque : Le résultat de l’attribution algorithmique diffère uniquement des autres modèles lorsque plusieurs points de contact existent dans la fenêtre de recherche donnée. Par exemple, avec un seul point de contact, 100 % du crédit sera attribué à cette valeur, quel que soit le modèle d’attribution sélectionné.*