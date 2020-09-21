---
title: Attribution algorithmique
description: Détails sur le modèle d’attribution algorithmique.
translation-type: ht
source-git-commit: 322e2e87ab532d5e8a864dc06613a9b275c71df5
workflow-type: ht
source-wordcount: '257'
ht-degree: 100%

---


# Attribution algorithmique

Le [modèle d’attribution](models.md) algorithmique dans Analysis Workspace diffère des autres modèles dans la mesure où il utilise des techniques statistiques pour répartir le crédit entre les éléments de dimension dans votre rapport ou tableau à structure libre. Comme tous les autres modèles d’attribution dans Analysis Workspace, il peut être utilisé sur n’importe quelle dimension ou mesure et prend en charge la segmentation et les ventilations illimitées. Il distribue 100 % des conversions aux dimensions du tableau (cela est également appelé attribution « partielle »).

L’algorithme utilisé pour l’attribution est basé sur le dividende d’Harsanyi de la théorie du jeu coopératif. Le dividende d’Harsanyi est une généralisation de la solution de valeur de Shapley (nommée en honneur de Lloyd Shapley, un lauréat du prix Nobel d’économie) pour distribuer le crédit entre les participants d’un jeu dont les contributions au résultat sont inégales.

À un niveau élevé, le calcul d’attribution du crédit de conversion pour chaque point de contact prend en compte chacun des points de contact marketing dans un intervalle de recherche en amont comme une coalition de joueurs auxquels un excédent doit être réparti équitablement. La répartition de l’excédent de chaque coalition est déterminée en fonction de l’excédent précédemment créé par chaque sous-coalition (ou des éléments de dimension ayant participé précédemment) de façon récurrente. Pour plus d’informations, consultez les publications originales de John Harsanyi et de Lloyd Shapley :

* Shapley, Lloyd S. 1953. A value for n-person games. *Contributions to the Theory of Games, 2(28)*, 307-317.
* Harsanyi, John C. 1963. A simplified bargaining model for the n-person cooperative game. *International Economic Review 4(2)*, 194-220.

>[!NOTE]
>
>Le résultat de l’attribution algorithmique diffère des autres modèles uniquement lorsque plusieurs points de contact existent dans l’intervalle de recherche en amont donné. Les conversions avec un seul point de contact reçoivent 100 % du crédit, quel que soit le modèle d’attribution.
