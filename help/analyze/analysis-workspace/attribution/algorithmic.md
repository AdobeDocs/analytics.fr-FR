---
title: Attribution algorithmique
description: Détails sur le modèle d’attribution algorithmique.
feature: Attribution
role: User, Admin
exl-id: dd2b2a5b-9c36-4534-999f-f96604f29eab
source-git-commit: d7a6867796f97f8a14cd8a3cfad115923b329c7c
workflow-type: tm+mt
source-wordcount: '277'
ht-degree: 84%

---

# Attribution algorithmique

Le [modèle d’attribution](models.md) algorithmique dans Analysis Workspace diffère des autres modèles dans la mesure où il utilise des techniques statistiques pour répartir le crédit entre les éléments de dimension dans votre rapport ou tableau à structure libre. Comme tous les autres modèles d’attribution dans Analysis Workspace, il peut être utilisé sur n’importe quelle dimension ou mesure et prend en charge la segmentation et les répartitions illimitées. Il distribue 100 % des conversions aux dimensions du tableau (cela est également appelé attribution « partielle »).


>[!BEGINSHADEBOX]

Voir ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Attribution algorithmique](https://video.tv.adobe.com/v/36205?quality=12&learn=on){target="_blank"} pour une vidéo de démonstration.

>[!ENDSHADEBOX]


L’algorithme utilisé pour l’attribution est basé sur le dividende d’Harsanyi de la théorie du jeu coopératif. Le dividende d’Harsanyi est une généralisation de la solution de valeur de Shapley (nommée en honneur de Lloyd Shapley, un lauréat du prix Nobel d’économie) pour distribuer le crédit entre les participants d’un jeu dont les contributions au résultat sont inégales.

À un niveau élevé, le calcul d’attribution du crédit de conversion pour chaque point de contact prend en compte chacun des points de contact marketing dans un intervalle de recherche en amont comme une coalition de joueurs auxquels un excédent doit être réparti équitablement. La distribution des excédents de chaque coalition est déterminée en fonction de l&#39;excédent qui a été précédemment créé par chaque sous-coalition (ou les éléments de dimension précédemment participants) de manière récursive. Pour plus de détails, voir les articles originaux de John Harsanyi et Lloyd Shapley :

* Shapley, Lloyd S. 1953. A value for n-person games. *Contributions to the Theory of Games, 2(28)*, 307-317.
* Harsanyi, John C. 1963. A simplified bargaining model for the n-person cooperative game. *International Economic Review 4(2)*, 194-220.

>[!NOTE]
>
>Le résultat de l’attribution algorithmique diffère des autres modèles uniquement lorsque plusieurs points de contact existent dans l’intervalle de recherche en amont donné. Les conversions avec un seul point de contact reçoivent 100 % du crédit, quel que soit le modèle d’attribution.
