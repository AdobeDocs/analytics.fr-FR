---
title: Type de connexion
description: La méthode de connexion du visiteur à Internet.
feature: Dimensions
exl-id: 149b2353-6128-4e0c-a73a-bc5a37c66b52
TQID: https://experienceleague.adobe.com/5kdDrW5vGzc4EKpLOF4VWzXish439t-aGp6q-XcK3Fs
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 236
ht-degree: 94%

---

# Type de connexion

La [dimension](overview.md) « Type de connexion » indique comment le visiteur s’est connecté à Internet. Cette dimension est utile pour déterminer la méthode de connexion à Internet utilisée par les visiteurs pour parcourir votre site. Vous pouvez lʼutiliser pour optimiser le contenu du site en fonction de la vitesse de connexion des visiteurs.

## Renseignement de cette dimension avec des données

Cette dimension utilise à la fois la [`ct` chaîne de requête](/help/implement/validate/query-parameters.md) et la logique côté serveur dʼAdobe. Adobe utilise les règles suivantes pour déterminer sa valeur :

1. Si la chaîne de requête `ct` est égale à `"modem"`, définissez lʼélément de dimension sur `"Modem"`. AppMeasurement collecte uniquement ces données sur les navigateurs Internet Explorer non pris en charge, cet élément de dimension est donc peu courant.
1. Vérifiez lʼadresse IP de lʼaccès et référencez-la à une table de recherche interne à Adobe. Si lʼadresse IP provient dʼun opérateur de téléphonie mobile, définissez lʼélément de dimension sur `"Mobile Carrier"`.
1. Si la chaîne de requête `ct` est égale à `"lan"`, définissez lʼélément de dimension sur `"LAN/Wifi"`.
1. Si lʼaccès provient dʼune [source de données](/help/import/data-sources/overview.md) ou est considéré comme un type dʼaccès spécial, définissez lʼélément de dimension sur `"Not specified"`.
1. Si aucune des règles ci-dessus nʼest respectée, la valeur par défaut est `"LAN/Wifi"`.

## Éléments de dimension

Les éléments de dimension comprennent `LAN/Wifi`, `Mobile Carrier`, `Modem` et `Not Specified`.

* **`LAN/Wifi`** : la connexion à Internet a été établie par le biais dʼune ligne fixe ou dʼun point dʼaccès Wi-Fi.
* **`Mobile Carrier`** : le visiteur sʼest connecté à Internet par le biais dʼun opérateur de téléphonie mobile.
* **`Modem`** : le visiteur sʼest connecté à Internet par lʼintermédiaire dʼun modem avec un navigateur Internet Explorer non pris en charge.
* **`Not Specified`** : lʼaccès ne présentait pas de type de connexion.
