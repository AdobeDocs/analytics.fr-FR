---
title: Lien de sortie
description: Le nom du lien de sortie.
feature: Dimensions
exl-id: 090d5fee-4b35-4be7-866c-5ef1d1c4c0a6
TQID: https://experienceleague.adobe.com/lGKBkR5e2arJxGmfIE4qN84oGtYJ2zkfn6luqxEUJ-w
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
source-wordcount: '251'
ht-degree: 22%
---
# Lien de sortie

La [dimension](overview.md) « Lien de sortie » indique les noms des liens de sortie implémentés sur votre site. Les liens de sortie effectuent le suivi des clics sortants qui éloignent les visiteurs du domaine actuel. Cette dimension est utile lorsque vous souhaitez comprendre les liens sortants sur lesquels les utilisateurs cliquent le plus fréquemment.

## Renseignement de cette dimension avec des données

Cette dimension est renseignée par [appels de suivi des liens (`tl()`)](/help/implement/vars/functions/tl-method.md). Il n’y a pas de variable dédiée à définir. Au lieu de cela, envoyez une demande d’image `tl()` avec un argument de type lien de `"e"` et définissez l’argument de nom du lien sur la valeur souhaitée. La chaîne de requête `pe` achemine le nom du lien vers la dimension de lien appropriée (`lnk_o` pour [liens personnalisés](custom-link.md), `lnk_d` pour [liens de téléchargement](download-link.md) et `lnk_e` pour [liens de sortie](exit-link.md)). Si aucun nom de lien n’est fourni, l’URL du lien est utilisée comme valeur de dimension et les valeurs dérivées des URL ne sont pas soumises à la limite d’octets.

```js
s.tl(true,"e","Example exit link");
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
