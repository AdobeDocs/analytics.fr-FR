---
description: Les variables dynamiques vous permettent de copier des valeurs d’une variable vers une autre sans entrer les valeurs complètes à plusieurs reprises dans les demandes d’image sur votre site.
keywords: Analytics Implementation
solution: null
title: Variables dynamiques
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# s.linkExternalFilters

Si votre site contient plusieurs liens vers des sites externes et que vous ne souhaitez pas suivre tous les liens de sortie, vous pouvez utiliser la variable pour créer des rapports sur un sous-ensemble spécifique de liens de sortie.

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|---|---|---|---|
| N/D | N/D | Chemins &gt; Entrées et sorties &gt; Liens de sortie | "" |

The *`linkExternalFilters`* variable is an optional variable used in conjunction with *`linkInternalFilters`* to determine whether a link is an exit link. On désigne sous le nom de lien de sortie tout lien qui permet à un visiteur de quitter votre site. Le lien apparaît dans le rapport des liens de sortie, que la fenêtre cible soit une fenêtre contextuelle ou qu’il s’agisse de la fenêtre existante. Le suivi des liens de sortie est effectué uniquement si la variable La variable *`trackExternalLinks`* est définie sur « true ». Les filtres dans *`linkExternalFilters`* et *`linkInternalFilters`* sont sensibles à la casse.

> [!NOTE]Si vous ne souhaitez pas utiliser la variable *`linkExternalFilters`*, supprimez-la ou définissez-la sur «  ».

La liste des filtres de *`linkExternalFilters`* et *`linkInternalFilters`* s’applique par défaut au domaine et au chemin d’accès de tous les liens. Si la variable *`linkLeaveQueryString`* est définie sur « true », les filtres s’appliquent à l’intégralité de l’URL (domaine, chemin et chaîne de requête). Ces filtres sont toujours appliqués au chemin absolu de l’URL, même si un chemin relatif est utilisé comme valeur href.

La plupart des entreprises estiment que la variable *`linkInternalFilters`* leur confère suffisamment de contrôle sur les liens de sortie, rendant de ce fait inutile la variable *`linkExternalFilters`*. L’utilisation de *`linkExternalFilters`* réduit simplement la probabilité qu’un lien de sortie soit considéré comme externe. Si *`linkExternalFilters`* contient une valeur, un lien n’est considéré comme externe que s’il ne correspond pas à *`linkInternalFilters`* et s’il correspond à *`linkExternalFilters`*.

L’exemple suivant illustre l’utilisation de cette variable. Dans cet exemple, l’URL de la page est `https://www.mysite.com/index.html`.

```js
s.trackExternalLinks=true 
s.linkInternalFilters="javascript:,mysite.com" 
s.linkExternalFilters="site1.com,site2.com,site3.com/partners" 
s.linkLeaveQueryString=false 
...
<a href="https://www.mysite.com">Not an Exit Link</a> 
<a href="/careers/job_list.html">Not an Exit Link</a> 
<a href="https://www2.site3.com">Not an Exit Link</a> 
<a href="https://www.site1.com">Exit Link</a> 
<a href="https://www2.site3.com/partners/offer.asp">Exit Link</a> 
```

## Syntaxe et valeurs possibles

La variable *`linkExternalFilters`* est une liste de caractères ASCII séparés par des virgules. Aucun espace n’est autorisé.

```js
s.linkExternalFilters="site1.com[,site2.com[,site3.net[...]]]"
```

Toute partie d’une URL peut être incluse dans la variable *`linkExternalFilters`* ; des virgules doivent être utilisées comme séparateurs.

## Exemples

```js
s.linkExternalFilters="partnersite.com,partnertwo.net/path/"
```

```js
s.linkExternalFilters=""
```

## Paramètres de configuration

Aucun

## Pièges, questions et conseils

* L’utilisation de *`linkExternalFilters`* peut contribuer à réduire le nombre de liens de sortie sur votre site. N’utilisez pas cette variable au lieu de *`linkInternalFilters`* pour forcer des liens internes à devenir des liens de sortie.

* S’il convient d’appliquer *`linkExternalFilters`* à la chaîne de requête d’un lien, assurez-vous que la variable *`linkLeaveQueryString`* est définie sur « true ». Reportez-vous à la section [linkLeaveQueryString](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html) avant de définir cette valeur sur `"true"`.

* Pour désactiver le suivi des liens de sortie, définissez *`trackExternalLinks`* sur `"false"`.
