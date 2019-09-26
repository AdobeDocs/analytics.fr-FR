---
description: Les variables dynamiques vous permettent de copier des valeurs d’une variable vers une autre sans entrer les valeurs complètes à plusieurs reprises dans les demandes d’image sur votre site.
keywords: Mise en œuvre d’Analytics
seo-description: Les variables dynamiques vous permettent de copier des valeurs d’une variable vers une autre sans entrer les valeurs complètes à plusieurs reprises dans les demandes d’image sur votre site.
solution: null
title: Variables dynamiques
translation-type: tm+mt
source-git-commit: 60dd1b300035e5149f53870239de85fb3174a77a

---



# s.linkInternalFilters

La variable est utilisée pour déterminer les liens de votre site qui sont des liens de sortie.

Il s’agit d’une liste, séparée par des virgules, de filtres représentant les liens qui font partie du site.

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|---|---|---|---|
| N/D | N/D | Chemins &gt; Entrées et sorties &gt; Liens de sortie |  |

>[!NOTE]
>
>Nous avions précédemment suggéré de définir linkInternalFilters sur javascript:. Toutefois, il en résultait que tous les domaines étaient considérés comme externes, y compris le domaine actuel dans lequel réside la balise. Si vous voulez que plusieurs domaines soient considérés comme internes, vous pouvez les ajouter, tel qu’illustré dans les exemples ci-dessous.

The *`linkInternalFilters`* variable is used to determine whether a link is an exit link, which is defined as any link that takes a visitor away from your site. Le lien apparaît dans le rapport des liens de sortie, que la fenêtre cible soit une fenêtre contextuelle ou qu’il s’agisse de la fenêtre existante. Le suivi des liens de sortie est effectué uniquement si *`trackExternalLinks`* est définie sur `"true"`. (Voir [Suivi des liens](https://marketing.adobe.com/resources/help/en_US/dtm/link_tracking.html) dans la documentation relative à Dynamic Tag Management pour plus d’informations sur la façon dont Dynamic Tag Management gère les liens de sortie.) Les filtres dans *`linkInternalFilters`* ne sont pas sensibles à la casse.

La liste des filtres de *`linkInternalFilters`* s’applique par défaut au domaine et au chemin d’accès de tout lien. If *`linkLeaveQueryString`* is set to `"true"`, then the filters apply to the entire URL (domain, path, and query string). Les filtres sont toujours appliqués au chemin absolu de l’URL, même si un chemin relatif est utilisé comme valeur href.

Sachez que tous les domaines de votre site (ainsi que tout partenaire qui utilise votre fichier JavaScript) sont inclus dans *`linkInternalFilters`*. Si tous les domaines ne sont pas inclus dans la liste, tous les liens qui y sont associés sont considérés comme des liens de sortie, ce qui a pour effet d’augmenter le nombre d’appels au serveur envoyés. Si vous souhaitez que plusieurs domaines ou entreprises utilisent un seul [!DNL AppMeasurement] fichier JavaScript, vous pouvez envisager de renseigner *`linkInternalFilters`* la page, en remplaçant la valeur spécifiée dans le fichier JavaScript. S’il existe des domaines mineurs qui redirigent immédiatement vers votre domaine principal, ils ne doivent pas nécessairement être inclus dans la liste.

L’exemple suivant illustre l’utilisation de cette variable. In this example, the URL of the page is `https://www.mysite.com/index.html`.

```js
s.trackExternalLinks=true 
s.linkInternalFilters="mysite.com" 
s.linkExternalFilters="" 
s.linkLeaveQueryString=false 
... 
<a href="https://www.mysite.com">Not an Exit Link</a> 
<a href="/careers/job_list.html">Not an Exit Link</a> 
<a href="https://www2.site3.com">Exit Link</a> 
<a href="https://www2.site1.com/partners/">Exit Link</a> 
```

## Syntaxe et valeurs possibles

La syntaxe de la variable *`linkInternalFilters`* est une liste de caractères ASCII séparés par des virgules. Aucun espace n’est autorisé.

```js
s.linkInternalFilters="site1.com[,site2.com[,site3.net[...]]]"
```

## Exemples

```js
s.linkInternalFilters="mysite.com"
```

```js
s.linkInternalFilters="mysite.com,mysite.net,vanity1.com"
```

## Paramètres de configuration

Aucun

## Pièges, questions et conseils

* Include all domains that the [!DNL AppMeasurement] for JavaScript file may be served under in the filter list.
* Vérifiez régulièrement le rapport [!UICONTROL Chemins] &gt; [!UICONTROL Entrées et sorties] &gt; [!UICONTROL Liens de sortie] pour vous assurer que toutes les entrées qu’il contient sont correctes.

* Consultez régulièrement les contrats conclus avec les partenaires afin de déterminer s’ils contiennent des restrictions en termes de suivi des liens. Par exemple, vous pouvez ne pas être autorisé à effectuer le suivi des liens qui apparaissent dans des publicités de partenaires. Filtrez les liens des partenaires en ajoutant leur domaine à la variable *`linkInternalFilters`*:

```js
s.linkInternalFilters="mysite.com,mysite.net,mypartner.net/adclick"
```
