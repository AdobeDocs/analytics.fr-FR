---
description: Cette section s’adresse aux administrateurs Adobe Analytics. Elle se concentre sur les nouveaux paramètres de suivi des liens et sur la façon dont ils assurent l’unicité et la cohérence des liens entre les navigateurs et les appareils, ainsi que sur la manière dont ils améliorent la gestion du repositionnement des liens sur une page.
seo-description: Cette section s’adresse aux administrateurs Adobe Analytics. Elle se concentre sur les nouveaux paramètres de suivi des liens et sur la façon dont ils assurent l’unicité et la cohérence des liens entre les navigateurs et les appareils, ainsi que sur la manière dont ils améliorent la gestion du repositionnement des liens sur une page.
seo-title: Méthodologie de suivi des liens
solution: Analytics
title: Méthodologie de suivi des liens
topic: Activity Map
uuid: 67864 bf 9-33 cd -46 fa -89 a 8-4 d 83 d 3 b 81152
translation-type: tm+mt
source-git-commit: 4f313ae50c4d5a0f3bfec493c2d554bc8614aeef

---


# Méthodologie de suivi des liens

Cette section s’adresse aux administrateurs Adobe Analytics. Elle se concentre sur les nouveaux paramètres de suivi des liens et sur la façon dont ils assurent l’unicité et la cohérence des liens entre les navigateurs et les appareils, ainsi que sur la manière dont ils améliorent la gestion du repositionnement des liens sur une page.

>[!IMPORTANT]
>
>Any link where the text (not the href) may contain PII (Personally Identifiable Information) should be implemented explicitly using [s_objectID](https://marketing.adobe.com/resources/help/en_US/sc/implement/s_objectID.html) or by excluding ActivityMap link collection with [s.ActivityMap.linkExclusions or s.ActivityMap.regionExclusions](../../../analyze/activity-map/activitymap-link-tracking/activitymap-link-tracking-methodology.md#section_634197EACD404AC086DF9A03B813C8C3). Pour obtenir plus d’informations sur la façon dont Activity Map collecte des données relatives aux informations d’identification personnelles, [cliquez ici](../../../analyze/activity-map/lnk-tracking-overview.md#section_A9F016E64F33446F8916855D8C69A7C6).

Activity Map base son suivi des liens sur ces deux ID :

* ID principal : il s’agit du paramètre reconnaissable du lien.
* Région de lien : il s’agit d’un paramètre secondaire qui permet aux utilisateurs de spécifier une chaîne représentative de l’ensemble de la zone de liens dans la page ou la région. Ce paramètre peut être généré automatiquement s’il n’est pas fourni par l’utilisateur.

## ID principal {#section_E8705CC1BDBC47FB8A4FE02293BACFE6}

Si le code HTML comprend une variable s_objectid, l’ID principal est remplacé par défaut par celle-ci. Dans le cas contraire, les paramètres suivants sont utilisés comme ID principal (dans cet ordre de priorité) :

* Innertext
* Alttext
* Title
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

## Link region {#section_75BF9B9E3CE94B59ACC3D9AF63E04535}

Ce nouvel attribut permet aux utilisateurs de spécifier une chaîne représentative de la région de page où se trouve le lien.

Par exemple, pour un lien « Nous contacter » situé dans la section du menu de la page web, l’utilisateur peut choisir de transmettre un paramètre de région « Menu ». De la même manière, pour un lien « Nous contacter » situé dans le pied de page de la page web, le paramètre de région peut être défini sur « pied de page ».

La valeur de la région de lien n’est pas définie sur le lien lui-même, mais sur un élément HTML de l’arborescence DOM HTML qui englobe cette région.
L’utilisation de la région de lien présente les avantages suivants :

* Elle permet de différencier des liens possédant le même ID principal.
* Les tendances d’une région sont moins affectées par l’aspect dynamique de la page web.
* Les utilisateurs peuvent consulter les liens les plus performants dans une région. Avec une région comme ancre, nous pouvons afficher des superpositions de liens qui ne sont actuellement pas visibles sur la page (Ajax, ciblage).
* Une région peut remplacer des pages, puisqu’une région donnée peut être utilisée sur de nombreuses pages web. Cela permet de répondre à des questions telles que la suivante : « Ma région "Offre de produits" obtient-elle de meilleurs résultats sur la page d’entrée des femmes ou sur celle des hommes ? ».
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

Si vous le souhaitez, vous pouvez baliser des éléments avec un identifiant de chaîne arbitraire, ici « lpos », puis ajouter des attributs avec le nom « lpos ».

```
s.ActivityMap.regionIDAttribute="lpos"; 
   
<div id="nav" lpos="navbar"> 
  <ul> 
     <li> Menu Category A 
    <ul> 
      <li><a href="">Menu Item A 1</a> 
      <li><a href="">Menu Item A 2</a> 
     </ul> 
    </li> 
     <li> Menu Category B 
     <ul> 
      <li><a href="">Menu Item B 1</a>  
      <li><a href="">Menu Item B 2</a> 
  
   </ul> 
</ul> 
</div> 
  
<div id="content" > 
  <div id="breaking_news" lpos="breaking_news> 
      <a href="breaking-news.html">...</a> 
   </div> 
 <div id="todays_top_headlines"> 
      <a href="breaking-news.html">...</a> 
   </div> 
</div>
```

## Configuration variables {#section_634197EACD404AC086DF9A03B813C8C3}

Notez que ces variables sont répertoriées à titre de référence uniquement. Activity Map doit être configurée correctement dès son installation, mais vous pouvez personnaliser votre mise en œuvre à l’aide de ces variables.

<table id="table_7BC8DC3F35CF49288D94BA707F06B283"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nom de variable  </th> 
   <th colname="col2" class="entry"> Exemple </th> 
   <th colname="col3" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> s. activitymap. regionidattribute </td> 
   <td colname="col2"> La valeur par défaut est le paramètre « id ». Vous pouvez définir un autre paramètre. </td> 
   <td colname="col3"> Chaîne qui identifie l’attribut de balise à utiliser comme ID de région à partir d’un élément ancêtre (parent, parent.parent, etc.) de s.linkObject, c’est-à-dire <b>l’élément sur lequel l’utilisateur a cliqué</b>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> s. activitymap. link </td> 
   <td colname="col2"> 
    <code>// use ever use « title » attributes from A tags function (clickedelement) {var linkid ; if (clickedelement &amp; &amp; clickedelement. tagname. touppercase () = = ='A ') {linkid = clickedelement. getattribute ('title ') ; } return linkid ; } </code>
  </td> 
   <td colname="col3"> Fonction qui reçoit l’HTMLElement visité et doit renvoyer une valeur de chaîne qui représente <b>le lien sur lequel l’utilisateur a cliqué</b>. <p>Si la valeur renvoyée est false (nul, non défini, chaîne vide, 0), aucun lien n’est suivi. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> s. activitymap. region </td> 
   <td colname="col2"> 
    <code>// only use minusercase version of tag name concatenated with first classname as the region function (clickedelement) {var regionid, classname ; while (clickedelement &amp; &amp; (clickedelement = clickedelement. parentnode)) {regionid = clickedelement. tagname ; if (regionid) {return regionid. tolowercase () ; }}} </code>
  </td> 
   <td colname="col3"> Fonction qui reçoit l’HTMLElement visité et doit renvoyer une valeur de chaîne qui représente <b>la région dans laquelle le lien a été trouvé lorsque l’utilisateur a cliqué dessus</b>. <p>Si la valeur renvoyée est false (nul, non défini, chaîne vide, 0), aucun lien n’est suivi. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> s.ActivityMap.linkExclusions </td> 
   <td colname="col2"> 
    <code>// Exclure les liens balisés avec une classe CSS linkexclue spéciale &lt; style &gt;. linkexclusion {display : block ; height : 1 px ; left : -9999 px ; overflow : masqué ; position : absolute ; width : 1 px ; } &lt;/style &gt; &lt; a href = "next-page.html" &gt; Le lien est suivi car le lien ne comporte pas de texte masqué correspondant au filtre.&lt;/a &gt; &lt; a href = "next-page.html" &gt; Lien non suivi car s. activitymap. linkexclusions est défini et que ce lien comporte du texte masqué correspondant au filtre. &lt; span class = "linkexclude" &gt; exclure-link 1 &lt;/span &gt; &lt;/a &gt; &lt; a href = "next-page.html" &gt; Lien non suivi car s. activitymap. linkexclusions est défini et que ce lien comporte du texte masqué correspondant au filtre.  &lt;span class="linkExcluded"&gt;exclude-link2&lt;/span&gt; &lt;/a&gt; &lt;script&gt;   var s = s_gi('samplersid');   s.ActivityMap.linkExclusions = 'exclude-link1,exclude-link2'; &lt;/script&gt; 
    </code> </td> 
   <td colname="col3"> <p>Chaîne qui reçoit une liste séparée par des virgules de chaînes à rechercher dans le texte du lien. En cas de résultat positif, le lien est exclu du suivi des liens d’Activity Map. Si cette variable n’est pas définie, aucun mécanisme de blocage du suivi du lien par Activity Map n’est activé. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> s.ActivityMap.regionExclusions </td> 
   <td colname="col2"> 
    <code>// Les régions Exclure sur la page de ses liens pouvant être suivis par activitymap &lt; div id = "links-inclus" &gt; &lt; a href = "next-page.html" &gt; Link font l'objet d'un suivi car s. activitymap. regionexclusions est défini mais ne correspond pas au filtre.&lt;/a &gt; &lt;/div &gt; &lt; div id = "links-exclude" &gt; &lt; a href = "next-page.html" &gt; Link not tracking because s. activitymap. regionexclusions est défini et ce lien correspond au filtre.&lt;/a&gt; &lt;/div&gt; &lt;script&gt;   var s = s_gi('samplersid');   s.ActivityMap.regionExclusions = 'links-excluded'; &lt;/script&gt;
    </code> </td> 
   <td colname="col3"> <p>Chaîne qui reçoit une liste séparée par des virgules de chaînes à rechercher dans le texte de région. En cas de résultat positif, le lien est exclu du suivi des liens d’Activity Map. Si cette variable n’est pas définie, aucun mécanisme de blocage du suivi du lien par Activity Map n’est activé. </p> </td> 
  </tr> 
 </tbody> 
</table>
