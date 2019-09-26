---
description: Les variables dynamiques vous permettent de copier des valeurs d’une variable vers une autre sans entrer les valeurs complètes à plusieurs reprises dans les demandes d’image sur votre site.
keywords: Mise en œuvre d’Analytics
seo-description: Les variables dynamiques vous permettent de copier des valeurs d’une variable vers une autre sans entrer les valeurs complètes à plusieurs reprises dans les demandes d’image sur votre site.
solution: null
title: Variables dynamiques
translation-type: tm+mt
source-git-commit: 60dd1b300035e5149f53870239de85fb3174a77a

---


# s.cookieLifetime

La variable est utilisée par les serveurs de collecte de données et JavaScript pour déterminer la durée de vie d’un cookie.

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|---|---|---|---|
| N/D | cl | Trafic &gt; Technologie &gt; Cookies – Tous les rapports liés aux visiteurs | "" |

Si la variable *`cookieLifetime`* est définie, elle remplace toute autre expiration de cookie pour les servers de collecte de données et JavaScript, à une exception près, décrite ci-dessous. The *`cookieLifetime`* variable can have one of three values:

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

*`cookieLifetime`* affecte le [!DNL Analytics] suivi. If, for example, *`cookieLifetime`* is two days, then monthly, quarterly, and yearly unique visitor reports will be incorrect. Soyez prudent lors de la définition de la variable *`cookieLifetime`*.