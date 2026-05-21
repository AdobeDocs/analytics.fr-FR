---
title: Lien de sortie
description: Le nom du lien de sortie.
feature: Dimensions
exl-id: 090d5fee-4b35-4be7-866c-5ef1d1c4c0a6
TQID: https://experienceleague.adobe.com/lGKBkR5e2arJxGmfIE4qN84oGtYJ2zkfn6luqxEUJ-w
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: 9b4525e014170b72688044a6ead344b1bde8c39b
workflow-type: tm+mt
source-wordcount: 225
ht-degree: 22%

---

# Lien de sortie

La [dimension](overview.md) « Lien de sortie » indique les noms des liens de sortie implémentés sur votre site. Les liens de sortie effectuent le suivi des clics sortants qui éloignent les visiteurs du domaine actuel. Cette dimension est utile lorsque vous souhaitez comprendre les liens sortants sur lesquels les utilisateurs cliquent le plus fréquemment.

## Renseignement de cette dimension avec des données

Cette dimension collecte des données de la chaîne de requête ](/help/implement/validate/query-parameters.md) dans les demandes d’image, en fonction de la valeur de la chaîne de requête `pe`. [`pev2`La chaîne de requête `pe` détermine la dimension de lien qui reçoit la valeur `pev2` :

* **[Lien personnalisé](custom-link.md)** : `lnk_o`
* **[Lien de téléchargement](download-link.md)** : `lnk_d`
* **Lien de sortie** (cette page) : `lnk_e`

Si `pev2` n’est pas fourni, l’URL du lien (`pev1`) est utilisée comme valeur de dimension à la place. Lorsqu’un nom de lien est explicitement fourni, la longueur maximale est de 100 octets. Les valeurs dérivées de l’URL du lien ne sont pas soumises à cette limite.

Pour remplir cette dimension à l’aide d’AppMeasurement, envoyez une demande d’image [`tl()`](/help/implement/vars/functions/tl-method.md) avec un argument de type lien de `"e"`. Définissez l’argument du nom du lien sur la valeur souhaitée :

```js
s.tl(true,"e","Example exit link");
```

## Éléments de dimension

Cette variable étant basée sur une chaîne personnalisée de votre implémentation, votre entreprise détermine les éléments de dimension. Adobe recommande de regrouper les liens en catégories significatives en fonction de vos besoins pour les rapports. Si aucun nom de lien n’est fourni, les éléments de dimension apparaissent plutôt sous la forme d’URL brutes. Ces URL brutes sont plus difficiles à interpréter dans les rapports. Par conséquent, fournissez un nom de lien descriptif chaque fois que possible.
