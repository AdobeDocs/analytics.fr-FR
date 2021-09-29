---
title: Type de connexion
description: La méthode de connexion du visiteur à Internet.
exl-id: 149b2353-6128-4e0c-a73a-bc5a37c66b52
source-git-commit: 82d6137bc9229bbaa997c6856690bf76c20b755c
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 7%

---

# Type de connexion

La dimension &quot;Type de connexion&quot; indique comment le visiteur s’est connecté à Internet. Cette dimension est utile pour déterminer la manière dont les visiteurs se connectent à Internet pour parcourir votre site. Vous pouvez l’utiliser pour optimiser le contenu du site en fonction de la vitesse de connexion des visiteurs.

## Renseignement de cette dimension avec des données

Cette dimension utilise une combinaison de la [`ct` chaîne de requête](/help/implement/validate/query-parameters.md) et de la logique côté serveur de l’Adobe. Adobe utilise les règles suivantes pour déterminer sa valeur :

1. Si la chaîne de requête `ct` est égale à `"modem"`, définissez l’élément de dimension sur `"Modem"`. AppMeasurement collecte uniquement ces données sur les navigateurs Internet Explorer non pris en charge, ce qui rend cet élément de dimension rare.
1. Vérifiez l’adresse IP de l’accès et référencez-la à une table de recherche interne à Adobe. Si l’adresse IP provient d’un opérateur de téléphonie mobile, définissez l’élément de dimension sur `"Mobile Carrier"`.
1. Si la chaîne de requête `ct` est égale à `"lan"`, définissez l’élément de dimension sur `"LAN/Wifi"`.
1. Si l’accès provient d’une [source de données](/help/import/c-data-sources/datasrc-home.md) ou est considéré comme un type spécial d’accès, définissez l’élément de dimension sur `"Not specified"`.
1. Si aucune des règles ci-dessus n’est respectée, la valeur par défaut est `"LAN/Wifi"`.

## Éléments de dimension

Les éléments de Dimension incluent `LAN/Wifi`, `Mobile Carrier`, `Modem` et `Not Specified`.

* **`LAN/Wifi`**: Le visiteur se connecte à Internet par le biais d’une ligne fixe ou d’une zone réactive Wi-Fi.
* **`Mobile Carrier`**: Le visiteur s’est connecté à Internet par le biais d’un opérateur de téléphonie mobile.
* **`Modem`**: Le visiteur s’est connecté à Internet par l’intermédiaire d’un modem dans un navigateur Internet Explorer non pris en charge.
* **`Not Specified`**: L’accès n’avait pas de type de connexion.
