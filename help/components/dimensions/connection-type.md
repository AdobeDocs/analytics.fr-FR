---
title: Type de connexion
description: La méthode de connexion du visiteur à Internet.
feature: Dimensions
exl-id: 149b2353-6128-4e0c-a73a-bc5a37c66b52
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 94%

---

# Type de connexion

Le &#39;Type de connexion&#39; [dimension](overview.md) indique comment le visiteur s’est connecté à Internet. Cette dimension est utile pour déterminer la méthode de connexion à Internet utilisée par les visiteurs pour parcourir votre site. Vous pouvez lʼutiliser pour optimiser le contenu du site en fonction de la vitesse de connexion des visiteurs.

## Renseignement de cette dimension avec des données

Cette dimension utilise à la fois la [`ct` chaîne de requête](/help/implement/validate/query-parameters.md) et la logique côté serveur dʼAdobe. Adobe utilise les règles suivantes pour déterminer sa valeur :

1. Si la chaîne de requête `ct` est égale à `"modem"`, définissez lʼélément de dimension sur `"Modem"`. AppMeasurement collecte uniquement ces données sur les navigateurs Internet Explorer non pris en charge, cet élément de dimension est donc peu courant.
1. Vérifiez lʼadresse IP de lʼaccès et référencez-la à une table de recherche interne à Adobe. Si lʼadresse IP provient dʼun opérateur de téléphonie mobile, définissez lʼélément de dimension sur `"Mobile Carrier"`.
1. Si la chaîne de requête `ct` est égale à `"lan"`, définissez lʼélément de dimension sur `"LAN/Wifi"`.
1. Si lʼaccès provient dʼune [source de données](/help/import/data-sources/overview.md) ou est considéré comme un type dʼaccès spécial, définissez lʼélément de dimension sur `"Not specified"`.
1. Si aucune des règles ci-dessus nʼest respectée, la valeur par défaut est `"LAN/Wifi"`.

## Éléments de dimension

Les éléments de dimension comprennent `LAN/Wifi`, `Mobile Carrier`, `Modem` et `Not Specified`.

* **`LAN/Wifi`** : le visiteur sʼest connecté à Internet par le biais dʼune ligne fixe ou dʼun point dʼaccès Wi-Fi.
* **`Mobile Carrier`** : le visiteur sʼest connecté à Internet par le biais dʼun opérateur de téléphonie mobile.
* **`Modem`** : le visiteur sʼest connecté à Internet par lʼintermédiaire dʼun modem avec un navigateur Internet Explorer non pris en charge.
* **`Not Specified`** : lʼaccès ne présentait pas de type de connexion.
