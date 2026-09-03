---
title: Lien personnalisé
description: Le nom du lien personnalisé.
feature: Dimensions
exl-id: c153f710-f03f-4be6-8e18-5ebf2ed80f01
TQID: https://experienceleague.adobe.com/x4IAGJjozPnLsft1e9xs68L6TNDJbHW0H4Z23p9EDNg
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: 9b4525e014170b72688044a6ead344b1bde8c39b
workflow-type: tm+mt
source-wordcount: 242
ht-degree: 21%

---

# Lien personnalisé

La [dimension](overview.md) « Lien personnalisé » indique les noms des liens personnalisés implémentés sur votre site. Les liens personnalisés constituent un mécanisme de suivi flexible pour toute interaction qui n’est pas un téléchargement de fichier ou une navigation sortante. Les exemples courants incluent les clics sur les boutons, la navigation interne ou les interactions de formulaire. Cette dimension est utile lorsque vous souhaitez comprendre laquelle de ces interactions intéresse le plus les visiteurs.

## Renseignement de cette dimension avec des données

Cette dimension collecte des données de la chaîne de requête ](/help/implement/validate/query-parameters.md) dans les demandes d’image, en fonction de la valeur de la chaîne de requête `pe`. [`pev2`La chaîne de requête `pe` détermine la dimension de lien qui reçoit la valeur `pev2` :

* **Lien personnalisé** (cette page) : `lnk_o`
* **[Lien de téléchargement](download-link.md)** : `lnk_d`
* **[Lien de sortie](exit-link.md)** : `lnk_e`

Si `pev2` n’est pas fourni, l’URL du lien (`pev1`) est utilisée comme valeur de dimension à la place. Lorsqu’un nom de lien est explicitement fourni, la longueur maximale est de 100 octets. Les valeurs dérivées de l’URL du lien ne sont pas soumises à cette limite.

Pour remplir cette dimension à l’aide d’AppMeasurement, envoyez une demande d’image [`tl()`](/help/implement/vars/functions/tl-method.md) avec un argument de type lien de `"o"`. Définissez l’argument du nom du lien sur la valeur souhaitée :

```js
s.tl(true,"o","Example custom link");
```

## Éléments de dimension

Cette variable étant basée sur une chaîne personnalisée de votre implémentation, votre entreprise détermine les éléments de dimension. Adobe recommande de regrouper les liens en catégories significatives en fonction de vos besoins pour les rapports. Si aucun nom de lien n’est fourni, les éléments de dimension apparaissent plutôt sous la forme d’URL brutes. Ces URL brutes sont plus difficiles à interpréter dans les rapports. Par conséquent, fournissez un nom de lien descriptif chaque fois que possible.
