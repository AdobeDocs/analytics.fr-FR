---
description: Les variables dynamiques vous permettent de copier des valeurs d’une variable vers une autre sans entrer les valeurs complètes à plusieurs reprises dans les demandes d’image sur votre site.
keywords: Analytics Implementation
solution: null
title: Variables dynamiques
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# s.cookieLifetime

La variable est utilisée par les serveurs de collecte de données et JavaScript pour déterminer la durée de vie d’un cookie.

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|---|---|---|---|
| N/D | cl | Trafic &gt; Technologie &gt; Cookies – Tous les rapports liés aux visiteurs | "" |

If *`cookieLifetime`* is set, it overrides any other cookie expirations for both JavaScript and data collection servers, with one exception, described below. La variable *`cookieLifetime`* peut avoir l’une des trois valeurs ci-dessous :

* [!DNL Analytics] Cookies
* Cookies
* Modules externes et paramètres JavaScript

## Syntaxe et valeurs possibles

```js
s.cookieLifetime="value"
```

Les valeurs possibles sont répertoriées comme suit :

* ""
* "NONE"
* "SESSION"
* Nombre entier représentant le nombre de secondes avant l’expiration du cookie.

## Exemples

```js
s.cookieLifetime="SESSION"
```

```js
s.cookieLifetime="86400" // one day in seconds
```

## Paramètres de configuration

Aucun

## Pièges, questions et conseils

*`cookieLifetime`* affecte le suivi de [!DNL Analytics]. Si, par exemple, la valeur *`cookieLifetime`* est définie sur deux jours, les rapports mensuels, trimestriels et annuels sur les visiteurs uniques seront incorrects. Soyez prudent lors de la définition de la variable *`cookieLifetime`*.
