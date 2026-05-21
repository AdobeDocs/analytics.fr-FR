---
title: Profondeur d’accès
description: Numéro de l’accès lors de la visite.
feature: Dimensions
exl-id: 84c27e3f-4228-4455-95bf-0239928337b5
TQID: https://experienceleague.adobe.com/dH1ItdXZTw9vcqvej3VOQDM-J9FFA38f4bq8HTJbKMo
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: c069c44e-5426-4c1a-accc-8028662f2fdeid: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 262
ht-degree: 94%

---

# Profondeur d’accès

La [dimension](overview.md) « Profondeur de l’accès » indique la durée d’une visite pour un accès donné. Cette dimension est utile pour comprendre le moment où les visiteurs effectuent des actions sur votre site au cours de leur visite. La profondeur d’accès compte tous les types d’accès, y compris les vues de page ([`t()`](/help/implement/vars/functions/t-method.md)) et les accès de suivi des liens ([`tl()`](/help/implement/vars/functions/tl-method.md)).

## Renseignement de cette dimension avec des données

Cette dimension est prête à l’emploi pour toutes les implémentations. Cette dimension fonctionne si une suite de rapports contient des données.

## Éléments de dimension

Les éléments de dimension comprennent la chaîne `"Hit Depth"` suivie d’un nombre représentant l’ordre d’accès lors de la visite. L’élément de dimension de `"Hit Depth 1"` représente le premier accès de la visite, tandis que l’élément de dimension `"Hit Depth 8"` représente le huitième accès de la visite.

## Comparaison avec la profondeur de visite

La profondeur d’accès compte tous les types d’accès, y compris les vues de page et les accès de suivi des liens. La profondeur de visite est uniquement incrémentée par les accès de type vue de page _et_ l’élément de dimension [Page](page.md) n’est pas le même que la valeur de la page précédente. La profondeur de visite est également une dimension basée sur la visite, ce qui signifie qu’elle a la même valeur pour tous les accès de la visite. Le tableau suivant illustre un exemple de visite et détaille la profondeur d’accès et la profondeur de visite :

| Séquence de page | Profondeur d’accès | Compte dans la profondeur de visite ? | Profondeur de visite |
| --- | --- | --- | --- |
| Page d’accueil | 1 | Oui | 4 |
| Page produit | 2 | Oui | 4 |
| Page d’accueil | 3 | Oui | 4 |
| Clic sur lien personnalisé | 4 | Non (lien personnalisé) | 4 |
| Clic sur lien personnalisé | 5 | Non (lien personnalisé) | 4 |
| Page produit | 6 | Oui | 4 |
| Clic sur lien personnalisé | 7 | Non (lien personnalisé) | 4 |
| Page produit | 8 | Non (identique à la page précédente) | 4 |
