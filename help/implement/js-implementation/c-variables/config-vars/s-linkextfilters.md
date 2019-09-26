---
description: Les variables dynamiques vous permettent de copier des valeurs d’une variable vers une autre sans entrer les valeurs complètes à plusieurs reprises dans les demandes d’image sur votre site.
keywords: Mise en œuvre d’Analytics
seo-description: Les variables dynamiques vous permettent de copier des valeurs d’une variable vers une autre sans entrer les valeurs complètes à plusieurs reprises dans les demandes d’image sur votre site.
solution: null
title: Variables dynamiques
translation-type: tm+mt
source-git-commit: b38ba4222951d957c607cd764224028527835c7e

---


# s.linkExternalFilters

Si votre site contient plusieurs liens vers des sites externes et que vous ne souhaitez pas suivre tous les liens de sortie, vous pouvez utiliser la variable pour créer des rapports sur un sous-ensemble spécifique de liens de sortie.

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|---|---|---|---|
| N/D | N/D | Chemins &gt; Entrées et sorties &gt; Liens de sortie | "" |

La variable *`linkExternalFilters`* est une variable facultative utilisée conjointement *`linkInternalFilters`* pour déterminer si un lien est un lien de sortie. On désigne sous le nom de lien de sortie tout lien qui permet à un visiteur de quitter votre site. Le lien apparaît dans le rapport des liens de sortie, que la fenêtre cible soit une fenêtre contextuelle ou qu’il s’agisse de la fenêtre existante. Le suivi des liens de sortie est effectué uniquement si la variable *`trackExternalLinks`* is set to 'true.' Les filtres dans *`linkExternalFilters`* et *`linkInternalFilters`* ne sont pas sensibles à la casse.

>[!NOTE]
>
>Si vous ne souhaitez pas l'utiliser *`linkExternalFilters`*, supprimez-le ou définissez-le sur "".

Les filtres sont répertoriés dans *`linkExternalFilters`* et *`linkInternalFilters`* s’appliquent par défaut au domaine et au chemin d’accès de n’importe quel lien. Si *`linkLeaveQueryString`* est défini sur "true", les filtres s’appliquent à l’intégralité de l’URL (domaine, chemin et chaîne de requête). Ces filtres sont toujours appliqués au chemin absolu de l’URL, même si un chemin relatif est utilisé comme valeur href.

La plupart des entreprises estiment que la variable *`linkInternalFilters`* leur confère suffisamment de contrôle sur les liens de sortie, rendant de ce fait inutile la variable *`linkExternalFilters`*. Using *`linkExternalFilters`* simply decreases the likelihood that an exit link is considered external. If *`linkExternalFilters`* has a value, then a link is considered only external if it does not match *`linkInternalFilters`* and does match *`linkExternalFilters`*.

L’exemple suivant illustre l’utilisation de cette variable. In this example, the URL of the page is `https://www.mysite.com/index.html`.

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

La syntaxe de la variable *`linkExternalFilters`* est une liste de caractères ASCII séparés par des virgules. Aucun espace n’est autorisé.

```js
s.linkExternalFilters="site1.com[,site2.com[,site3.net[...]]]"
```

Toute partie d’une URL peut être incluse dans la variable *`linkExternalFilters`*, separated by commas.

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

* Using *`linkExternalFilters`* can result in fewer links on your site being exit links. N’utilisez pas cette variable au lieu de *`linkInternalFilters`* forcer les liens internes à devenir des liens de sortie.

* Si *`linkExternalFilters`* vous devez appliquer la chaîne de requête d’un lien, assurez-vous *`linkLeaveQueryString`* qu’elle est définie sur "true". See [linkLeaveQueryString](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html) before setting to `"true"`.

* To disable exit link tracking, set *`trackExternalLinks`* to `"false"`.
