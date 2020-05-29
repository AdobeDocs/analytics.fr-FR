---
title: Attribution algorithmique
description: Détails sur le modèle d’attribution algorithmique dans Adobe Analytics.
translation-type: tm+mt
source-git-commit: 5c5e442face936ccf1ff2a3d1580e362d42e0acb
workflow-type: tm+mt
source-wordcount: '277'
ht-degree: 2%

---


# Attribution algorithmique

>[!IMPORTANT]
>
>**[!UICONTROL Les tests d’attribution]** algorithmique sont actuellement limités. [En savoir plus](https://docs.adobe.com/content/help/en/analytics/landing/an-releases.html)

Le modèle [d’](attribution.md) attribution algorithmique d’Analyse Workspace diffère des autres modèles en ce sens qu’il utilise des techniques statistiques pour allouer du crédit sur les valeurs de dimension dans votre rapport ou tableau à structure libre. Comme tous les autres modèles d’attribution d’Analyse Workspace, il peut être utilisé sur n’importe quelle dimension ou mesure et prend en charge la segmentation et les ventilations illimitées et distribue 100 % des conversions à la ou aux dimensions du tableau (également appelée attribution fractionnelle).

L&#39;algorithme utilisé pour l&#39;attribution est basé sur le Dividende Harsanyi de la théorie du jeu coopératif. Le dividende de Harsanyi est une généralisation de la solution de valeur de Shapley (du nom de Lloyd Shapley, un économiste lauréat du prix Nobel) pour distribuer le crédit entre les joueurs dans un jeu avec des contributions inégales au résultat.

À un niveau élevé, le calcul d’attribution du crédit de conversion pour chaque point de contact considère chacun des points de contact marketing dans une fenêtre de recherche en amont comme une coalition de joueurs auxquels un excédent doit être réparti équitablement. La répartition de l’excédent de chaque coalition est déterminée en fonction de l’excédent précédemment créé par chaque sous-coalition (ou des valeurs de dimension précédemment participantes) de façon récursive. Pour plus de détails, voir les documents originaux de John Harsanyi et de Lloyd Shapley :

* Shapley, Lloyd S. (1953). Valeur pour les jeux en personne. *Contributions à la Théorie des Jeux, 2(28)*, 307-317.
* Harsanyi, John C. (1963). Un modèle de négociation simplifié pour le jeu coopératif en personne. *International Economic Review 4(2)*, 194-220.

>[!NOTE] Le résultat de l’attribution algorithmique ne diffère que des autres modèles lorsque plusieurs points de contact existent dans la fenêtre de recherche donnée. Les conversions avec un seul point de contact reçoivent un crédit de 100 %, quel que soit le modèle d’attribution.
