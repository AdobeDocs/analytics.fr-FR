---
description: Cette section s’adresse aux administrateurs Adobe Analytics. Elle se concentre sur les nouveaux paramètres de suivi des liens et sur la façon dont ils assurent l’unicité et la cohérence des liens entre les navigateurs et les appareils, ainsi que sur la manière dont ils améliorent la gestion du repositionnement des liens sur une page.
title: Méthodologie de suivi des liens
uuid: 67864bf9-33cd-46fa-89a8-4d83d3b81152
feature: Activity Map
role: User, Admin
exl-id: 6aef3a0f-d0dd-4c84-ad44-07b286edbe18
source-git-commit: a6b38c6e7a34c876524ebe15514ac205898549d0
workflow-type: tm+mt
source-wordcount: '992'
ht-degree: 100%

---

# Méthodologie de suivi des liens

Cette section s’adresse aux administrateurs Adobe Analytics. Elle se concentre sur les nouveaux paramètres de suivi des liens et sur la façon dont ils assurent l’unicité et la cohérence des liens entre les navigateurs et les appareils, ainsi que sur la manière dont ils améliorent la gestion du repositionnement des liens sur une page.

>[!IMPORTANT]
>
>Tout lien dont le texte (pas le href) est susceptible de contenir des informations d’identification personnelles doit être mis en œuvre de façon explicite à l’aide de [s_objectID](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/page-variables.html?lang=fr) ou en excluant la collecte des liens Activity Map à l’aide de [s.ActivityMap.linkExclusions ou de s.ActivityMap.regionExclusions](/help/analyze/activity-map/activitymap-link-tracking/activitymap-link-tracking-methodology.md#configuration-vars). Pour obtenir plus d’informations sur la façon dont Activity Map collecte des données relatives aux informations d’identification personnelles, [cliquez ici](/help/analyze/activity-map/lnk-tracking-overview.md).

Activity Map base son suivi des liens sur ces deux ID :

* ID principal : il s’agit du paramètre reconnaissable du lien.
* Région de lien : il s’agit d’un paramètre secondaire qui permet aux utilisateurs de spécifier une chaîne représentative de l’ensemble de la zone de liens dans la page ou la région. Ce paramètre peut être généré automatiquement s’il n’est pas fourni par l’utilisateur.

## ID principal {#section_E8705CC1BDBC47FB8A4FE02293BACFE6}

Si le code HTML comprend une variable s_objectid, l’ID principal est remplacé par défaut par celle-ci. Dans le cas contraire, les paramètres suivants sont utilisés comme ID principal (dans cet ordre de priorité) :

* Innertext
* Alttext
* Titre
* Src
* Action

## Utilisation du paramètre InnerText ou d’une action de lien (URL) {#section_70C3573E22274522A8CC035BF18EC468}

Une action de lien est l’action effectuée par la page web lorsque l’utilisateur clique sur le lien ; en général, il s’agit de l’URL visitée après le clic sur le lien. Il se peut que vous rencontriez les problèmes suivants lors de l’utilisation d’une action de lien :

* plusieurs liens différents avec le même ID ;
* lisibilité du lien ;
* un lien avec plusieurs actions (en fonction de l’appareil sur lequel vous accédez au lien).

Par conséquent, nous utilisons le paramètre InnerText qui présente les avantages suivants par rapport à l’utilisation d’une action de lien (URL) :

* Il s’agit d’une bonne représentation de l’identité du lien. La duplication des ID principaux est réduite de manière significative, car il est rare que plusieurs liens contiennent le même texte.
* Il assure la cohérence de l’ID principal sur tous les appareils et les types de navigateurs.
* Il n’est pas affecté par un repositionnement des liens sur la page.
* Il améliore la lisibilité afin que les utilisateurs puissent commencer à analyser les rapports de suivi des liens en dehors d’Activity Map.

## Région de lien {#section_75BF9B9E3CE94B59ACC3D9AF63E04535}

Ce nouvel attribut permet aux utilisateurs de spécifier une chaîne représentative de la région de page où se trouve le lien.

Par exemple, pour un lien « Nous contacter » situé dans la section du menu de la page web, l’utilisateur peut choisir de transmettre un paramètre de région « Menu ». De la même manière, pour un lien « Nous contacter » situé dans le pied de page de la page web, le paramètre de région peut être défini sur « pied de page ».

La valeur de la région de lien n’est pas définie sur le lien lui-même, mais sur un élément HTML de l’arborescence DOM HTML qui englobe cette région.
L’utilisation de la région de lien présente les avantages suivants :

* Elle permet de différencier des liens possédant le même ID principal.
* Les tendances d’une région sont moins affectées par l’aspect dynamique de la page web.
* Les utilisateurs peuvent consulter les liens les plus performants dans une région. Avec une région comme ancre, nous pouvons afficher des superpositions de liens qui ne sont actuellement pas visibles sur la page (Ajax, ciblage).
* Une région peut remplacer des pages, puisqu’une région donnée peut être utilisée sur de nombreuses pages web. Cela permet de répondre à des questions telles que la suivante : « Ma région &quot;Offre de produits&quot; obtient-elle de meilleurs résultats sur la landing page des femmes ou sur celle des hommes ? ».
* En soi, une région est une dimension pertinente pour l’analyse de pages web très dynamiques. En effet, elle supprime le bruit dû au changement constant des liens : une région « Dernières actualités » sur la page d’entrée de CNN peut contenir de nombreux changements de liens. Mais la région sera toujours présente. Il pourrait donc être intéressant d’établir les tendances au niveau de la région sur plusieurs jours.

**Suivi des régions personnalisé**

Vous pouvez personnaliser le paramètre Région pour un lien (la valeur par défaut est l’ID de lien) : une balise définie sur « ID » utilisera tous les éléments HTML avec un paramètre « id » comme région. Par conséquent, définir la balise Région sur « id » renverra probablement de nombreuses régions distinctes (autant qu’il y a d’« ID » différents sur la page). Si vous souhaitez une mise en œuvre plus personnalisée, vous pouvez également définir la balise Région sur quelque chose de plus spécifique, tel que « region_id ».

Vous trouverez ci-dessous un exemple de HTML utilisant l’attribut ID de région par défaut, « id ».

```
<div id="content">
  <div id="breaking_news">
    <a href="breaking-news.html">...</a>
  </div>
  <div id="todays_top_headlines">
    <a href="breaking-news.html">...</a>
  </div>
```

Si vous le souhaitez, vous pouvez baliser des éléments avec un identifiant de chaîne arbitraire, ici « lpos », puis ajouter des attributs avec le nom « lpos ».

```
<script language="JavaScript" type="text/javascript">
s.ActivityMap.regionIDAttribute = "lpos";
</script>
<div id="nav" lpos="navbar">
  <ul>
    <li>Menu Category A
      <ul>
        <li><a href="">Menu Item A 1</a>
        <li><a href="">Menu Item A 2</a>
      </ul>
    </li>
    <li>Menu Category B
      <ul>
        <li><a href="">Menu Item B 1</a>
        <li><a href="">Menu Item B 2</a>
      </ul>
    </li>
  </ul>
</div> 
  
<div id="content">
  <div id="breaking_news" lpos="breaking_news>
    <a href="breaking-news.html">...</a>
  </div>
  <div id="todays_top_headlines">
    <a href="breaking-news.html">...</a>
  </div>
```

## Variables de configuration {#configuration-vars}

Notez que ces variables sont répertoriées à titre de référence uniquement. Activity Map doit être configurée correctement dès son installation, mais vous pouvez personnaliser votre mise en œuvre à l’aide de ces variables.

### `s.ActivityMap.regionIDAttribute`

Chaîne qui identifie l’attribut de balise à utiliser comme ID de région à partir d’un élément ancêtre (parent, parent.parent, etc.) de `s.linkObject`, c’est-à-dire **l’élément sur lequel l’utilisateur a cliqué**.

**Exemple**

La valeur par défaut est le paramètre « id ». Vous pouvez définir un autre paramètre.

### `s.ActivityMap.link`

Fonction qui reçoit lʼ`HTMLElement` visité et doit renvoyer une valeur de chaîne qui représente le lien sur lequel l’utilisateur a cliqué. Si la valeur renvoyée est false (nul, non défini, chaîne vide, 0), aucun lien n’est suivi.

**Exemple**

```
// only ever use "title" attributes from A tags
function(clickedElement) {
  var linkId;
  if (clickedElement && clickedElement.tagName.toUpperCase() === 'A') {
    linkId = clickedElement.getAttribute('title');
  }
  return linkId;
}
```

### `s.ActivityMap.region`

Fonction qui reçoit l’HTMLElement visité et doit renvoyer une valeur de chaîne qui représente **la région dans laquelle le lien a été trouvé lorsque l’utilisateur a cliqué dessus.** Si la valeur renvoyée est false (nul, non défini, chaîne vide, 0), aucun lien n’est suivi.

**Exemple**

```
// only ever use lowercase version of tag name concatenated with first className as the region
function(clickedElement) {
  var regionId, className;
  while (clickedElement && (clickedElement = clickedElement.parentNode)) {
    regionId = clickedElement.tagName;
    if (regionId) {
      return regionId.toLowerCase();
    }
  }
}
```

### `s.ActivityMap.linkExclusions`

Chaîne qui reçoit une liste séparée par des virgules de chaînes à rechercher dans le texte du lien. En cas de résultat positif, le lien est exclu du suivi des liens d’Activity Map. Si cette variable n’est pas définie, aucun mécanisme de blocage du suivi du lien par Activity Map n’est activé.

**Exemple**

```
// Exclude links tagged with a special linkExcluded CSS class
<style>
.linkExcluded {
  display: block;
  height: 1px;
  left: -9999px;
  overflow: hidden;
  position: absolute;
  width: 1px;
}
</style>
<a href="next-page.html">
  Link is tracked because link does not have hidden text matching the filter. 
</a>
<a href="next-page.html">
  Link not tracked because s.ActivityMap.linkExclusions is set and this link has hidden text matching the filter.
  <span class="linkExcluded">exclude-link1</span>
</a>
<a href="next-page.html">
  Link not tracked because s.ActivityMap.linkExclusions is set and this link has hidden text matching the filter.
  <span class="linkExcluded">exclude-link2</span>
</a>
<script>
  var s = s_gi('samplersid');
  s.ActivityMap.linkExclusions = 'exclude-link1,exclude-link2';
</script>
```

### `s.ActivityMap.regionExclusions`

Chaîne qui reçoit une liste séparée par des virgules de chaînes à rechercher dans le texte de région. En cas de résultat positif, le lien est exclu du suivi des liens d’Activity Map. Si cette variable n’est pas définie, aucun mécanisme de blocage du suivi du lien par Activity Map n’est activé.

**Exemple**

```
// Exclude regions on the page from its links being trackable by ActivityMap
<div id="links-included">
  <a href="next-page.html">
    Link is tracked because s.ActivityMap.regionExclusions is set but does not match the filter.
  </a>
</div>
<div id="links-excluded"> 
  <a href="next-page.html">
    Link not tracked because s.ActivityMap.regionExclusions is set and this link matches the filter.
  </a>
</div>
<script>
  var s = s_gi('samplersid');
  s.ActivityMap.regionExclusions = 'links-excluded';
</script>
```
