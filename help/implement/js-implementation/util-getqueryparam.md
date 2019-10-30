---
description: Renvoie la valeur d'un paramètre de chaîne de requête spécifié si elle se trouve dans l'URL de la page actuelle ou dans la chaîne fournie.
keywords: Mise en œuvre d’Analytics
seo-description: Renvoie la valeur d’un paramètre de chaîne de requête spécifié si elle se trouve dans l'URL de la page actuelle ou dans la chaîne fournie.
seo-title: Util.getQueryParam
solution: Analytics
subtopic: AppMeasurement pour JavaScript
title: Util.getQueryParam
topic: Développeur et mise en œuvre
uuid: 1fecd148-3e52-46f2-a73f-003563f7a62c
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Util.getQueryParam

Renvoie la valeur d'un paramètre de chaîne de requête spécifié si elle se trouve dans l'URL de la page actuelle ou dans la chaîne fournie.

Des données importantes (codes de suivi de campagne, mots-clés de recherche interne, etc.) sont disponibles dans la chaîne de requête d’une page. Aussi, getQueryParam vous aide-t-il à les capturer dans des variables Analytics.

Cet utilitaire remplace le module externe [getQueryParam](../../implement/js-implementation/plugins/getqueryparam.md#concept_E3D0FEC81E1F4987B39CC467F19FFCFF).

**Syntaxe :**

```
s.Util.getQueryParam(key, [url], [delim])
```

> [!NOTE] La syntaxe de l’utilitaire est différente de celle du module externe.

**Paramètres:**

| Paramètre | Description |
|---|---|
| key | (Obligatoire) Nom du paramètre de chaîne de requête que vous souhaitez obtenir. Ce paramètre applique le respect de la casse. |
| url | (Facultatif) L’URL par défaut est `s.pageURL` ou `window.location`. La spécification d’une valeur pour ce paramètre remplace l’URL à partir de laquelle le paramètre de requête est récupéré par celle spécifiée. |
| delim | (Facultatif) Délimiteur de paramètre de l’URL Le délimiteur par défaut est « &amp; ». Cela vous permet de spécifier un autre délimiteur de chaîne de requête tel que « ; ». |

**Retours:**

La fonction renvoie une chaîne vide "" si aucune clé n’est fournie, si aucune des options d’URL n’existe ou si la clé est introuvable dans l’URL. Si un délimiteur de fragment # est trouvé dans l’URL, tout ce qui le suit n’est pas pris en compte. Si la clé existe et est affectée à une valeur, elle est décodée et renvoyée par l’URL.

**Exemple :**

```js
s.doPlugins = function(s) { 
  s.campaign = s.Util.getQueryParam("cid"); 
};
```

