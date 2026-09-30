---
title: Attribution algorithmique
description: Comprenez les détails du modèle d’attribution algorithmique.
feature: Attribution
role: User, Admin
exl-id: dd2b2a5b-9c36-4534-999f-f96604f29eab
TQID: 'https://experienceleague.adobe.com/jPLoQcRU8bpCGjKJ37mioUdZOFDUwNehmyBhdx7lj8c'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
subfeature_v2:
  - id: b3a8b8a0-1cc2-48a8-ac82-ffd9c66ccab4
    internal-label: Attribution
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 38%
---
# Attribution algorithmique

Le [modèle d’attribution](models.md) algorithmique dans Analysis Workspace diffère des autres modèles dans la mesure où il utilise des techniques statistiques pour répartir le crédit entre les éléments de dimension dans votre rapport ou tableau à structure libre. Comme tous les autres modèles d’attribution d’Analysis Workspace, l’attribution algorithmique peut être utilisée sur n’importe quelle dimension ou mesure. L’attribution algorithmique prend en charge une segmentation et des répartitions illimitées et distribue 100 % des conversions à une ou plusieurs dimensions du tableau (également appelée attribution « partielle »).


>[!BEGINSHADEBOX]

Voir ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Attribution algorithmique](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/attribution-iq/algorithmic-model-in-attribution-iq){target="_blank"} pour une vidéo de démonstration.

>[!ENDSHADEBOX]


L’algorithme utilisé pour l’attribution est basé sur le dividende d’Harsanyi de la théorie du jeu coopératif. Le dividende de Harsanyi est une généralisation de la solution de valeur de Shapley (du nom de Lloyd Shapley, lauréat du prix Nobel d&#39;économie) pour répartir le crédit entre les joueurs d&#39;un jeu ayant des contributions inégales au résultat.

À un niveau élevé, le calcul de l’attribution du crédit de conversion pour chaque point de contact considère chacun des points de contact marketing dans un intervalle de recherche en amont comme une coalition de joueurs. Pour cette coalition d&#39;acteurs, un surplus doit être équitablement réparti. La distribution des excédents de chaque coalition est déterminée à partir de l&#39;excédent que chaque sous-coalition a créé de manière récursive auparavant.

Pour plus de détails, voir les articles originaux de John Harsanyi et Lloyd Shapley :

* Shapley, Lloyd S. (1953). Une valeur pour les jeux à n joueurs. *Contributions to the Theory of Games, 2(28)*, 307-317.
* Harsanyi, John C. (1963). Un modèle simplifié de négociation pour le jeu coopératif à n personnes *International Economic Review 4(2)*, 194-220.

>[!NOTE]
>
>Le résultat de l’attribution algorithmique diffère des autres modèles uniquement lorsque plusieurs points de contact existent dans l’intervalle de recherche en amont donné. Les conversions avec un seul point de contact reçoivent 100 % du crédit, quel que soit le modèle d’attribution.
