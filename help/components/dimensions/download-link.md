---
title: Lien de téléchargement
description: Nom du lien de téléchargement.
feature: Dimensions
exl-id: 078014a2-1f09-4177-9575-b44c5da25816
TQID: https://experienceleague.adobe.com/vok8Znalf6GBA1N0Z9GE1d31QpaUmD-d0bOsHB2Wehc
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 27%
---
# Lien de téléchargement

La dimension [Lien de téléchargement](overview.md) indique les noms des liens de téléchargement implémentés sur votre site. Cette dimension est utile pour en savoir plus sur le comportement des visiteurs vis-à-vis des liens de téléchargement, par exemple :

* Les fichiers les plus fréquemment téléchargés à partir de votre site.
* Si certains fichiers sont téléchargés plus souvent pendant des périodes spécifiques.
* Indique si les visiteurs téléchargent différents types de fichiers lorsqu’ils sont proposés.

## Renseignement de cette dimension avec des données

Cette dimension est renseignée par [appels de suivi des liens (`tl()`)](/help/implement/vars/functions/tl-method.md). Il n’y a pas de variable dédiée à définir. Au lieu de cela, envoyez une demande d’image `tl()` avec un argument de type lien de `"d"` et définissez l’argument de nom du lien sur la valeur souhaitée. La chaîne de requête `pe` achemine le nom du lien vers la dimension de lien appropriée (`lnk_o` pour [liens personnalisés](custom-link.md), `lnk_d` pour [liens de téléchargement](download-link.md) et `lnk_e` pour [liens de sortie](exit-link.md)). Si aucun nom de lien n’est fourni, l’URL du lien est utilisée comme valeur de dimension et les valeurs dérivées des URL ne sont pas soumises à la limite d’octets.

```js
s.tl(true,"d","Example download link");
```

| Propriété | Valeur |
| --- | --- |
| **Variable** | [`tl()`](/help/implement/vars/functions/tl-method.md) |
| **Champ Web SDK/XDM** | Aucun |
| **Paramètre de requête** | [`pev2`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Balise XML** | [`<linkName>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Limite d’octets** | 100 octets |
| **Persistance** | Hit |

## Éléments de dimension

Cette variable étant basée sur une chaîne personnalisée de votre implémentation, votre entreprise détermine les éléments de dimension. Adobe recommande de regrouper les liens en catégories significatives en fonction de vos besoins pour les rapports. Si aucun nom de lien n’est fourni, les éléments de dimension apparaissent plutôt sous la forme d’URL brutes. Ces URL brutes sont plus difficiles à interpréter dans les rapports. Par conséquent, fournissez un nom de lien descriptif chaque fois que possible.
