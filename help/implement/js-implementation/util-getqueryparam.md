---
description: Renvoie la valeur d’un paramètre de chaîne de requête spécifié s’il se trouve dans l’URL de la page actuelle ou dans la chaîne fournie.
keywords: Mise en œuvre d’Analytics
seo-description: Renvoie la valeur d'un paramètre de chaîne de requête spécifié si elle se trouve dans l'URL de la page actuelle ou dans la chaîne fournie.
seo-title: Util.getQueryParam
solution: Analytics
subtopic: AppMeasurement pour JavaScript
title: Util.getQueryParam
topic: Développeur et mise en œuvre
uuid: 1 fecd 148-3 e 52-46 f 2-a 73 f -003563 f 7 a 62 c
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# Util.getQueryParam

Renvoie la valeur d’un paramètre de chaîne de requête spécifié s’il se trouve dans l’URL de la page actuelle ou dans la chaîne fournie.

Des données importantes (codes de suivi de campagne, mots-clés de recherche interne, etc.) sont disponibles dans la chaîne de requête d’une page. Aussi,   getQueryParam vous aide-t-il à les capturer dans des variables Analytics.

Cet utilitaire remplace le module externe [getQueryParam](../../implement/js-implementation/plugins/getqueryparam.md#concept_E3D0FEC81E1F4987B39CC467F19FFCFF).

**Syntaxe :**

```
s.Util.getQueryParam(key, [url], [delim])
```

>[!NOTE]
>
>La syntaxe de l'utilitaire diffère de celle du module externe.

**Paramètres :**

| Paramètre | Description |
|---|---|
| key | (Obligatoire) Nom du paramètre de chaîne de requête que vous souhaitez obtenir. Ce paramètre applique le respect de la casse. |
| url | (optional) Default url is `s.pageURL` or `window.location`. La spécification d’une valeur pour ce paramètre remplace l’URL à partir de laquelle le paramètre de requête est récupéré par celle spécifiée. |
| delim | (Facultatif) Délimiteur de paramètre de l’URL Le délimiteur par défaut est « &amp; ». Cela vous permet de spécifier un autre délimiteur de chaîne de requête tel que « ; ». |

**Retours :**

La fonction renvoie une chaîne vide "si aucune clé n'est fournie ou si aucune des options d'URL n'existe ou si la clé est introuvable dans l'URL. Si un délimiteur de fragment est détecté dans l'URL, tout ce qui suit le délimiteur de fragment n'est pas considéré. Si la clé existe et est affectée à une valeur, cette dernière est décodée et renvoyée.

**Exemple :**

```js
s.doPlugins = function(s) { 
  s.campaign = s.Util.getQueryParam("cid"); 
};
```

