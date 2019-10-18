---
description: Cette section s’adresse aux administrateurs Adobe Analytics. Elle se concentre sur les nouveaux paramètres de suivi des liens et sur la façon dont ils assurent l’unicité et la cohérence des liens entre les navigateurs et les appareils, ainsi que sur la manière dont ils améliorent la gestion du repositionnement des liens sur une page.
seo-description: Cette section s’adresse aux administrateurs Adobe Analytics. Elle se concentre sur les nouveaux paramètres de suivi des liens et sur la façon dont ils assurent l’unicité et la cohérence des liens entre les navigateurs et les appareils, ainsi que sur la manière dont ils améliorent la gestion du repositionnement des liens sur une page.
seo-title: Méthodologie de suivi des liens
solution: Analytics
title: Méthodologie de suivi des liens
topic: Activity Map
uuid: 67864bf9-33cd-46fa-89a8-4d83d3b81152
translation-type: tm+mt
source-git-commit: 36637b76b8026fbf87ad48adcfa47386c530e732

---


# Méthodologie de suivi des liens

Cette section s’adresse aux administrateurs Adobe Analytics. Elle se concentre sur les nouveaux paramètres de suivi des liens et sur la façon dont ils assurent l’unicité et la cohérence des liens entre les navigateurs et les appareils, ainsi que sur la manière dont ils améliorent la gestion du repositionnement des liens sur une page.

>[!IMPORTANT]
>
>Any link where the text (not the href) may contain PII (Personally Identifiable Information) should be implemented explicitly using [s_objectID](https://marketing.adobe.com/resources/help/en_US/sc/implement/s_objectID.html) or by excluding ActivityMap link collection with [s.ActivityMap.linkExclusions or s.ActivityMap.regionExclusions](../../../analyze/activity-map/activitymap-link-tracking/activitymap-link-tracking-methodology.md#section_634197EACD404AC086DF9A03B813C8C3). For more information on how [!DNL Activity Map] may be collecting PII data, go [here](../../../analyze/activity-map/lnk-tracking-overview.md#section_A9F016E64F33446F8916855D8C69A7C6).

[!DNL Activity Map] base son suivi des liens sur les deux ID suivants :

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
* It improves readability, so users can start analyzing Link tracking reports outside [!DNL Activity Map].

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

## Variables de configuration {#section_634197EACD404AC086DF9A03B813C8C3}

Notez que ces variables sont répertoriées à titre de référence uniquement. [!DNL Activity Map] doit être configurée correctement dès son installation, mais vous pouvez personnaliser votre mise en œuvre à l’aide de ces variables.

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
   <td colname="col1"> s.ActivityMap.regionIDAttribut </td> 
   <td colname="col2"> La valeur par défaut est le paramètre « id ». Vous pouvez définir un autre paramètre. </td> 
   <td colname="col3"> Chaîne qui identifie l’attribut de balise à utiliser comme ID de région à partir d’un élément ancêtre (parent, parent.parent, etc.) de s.linkObject, c’est-à-dire <b>l’élément sur lequel l’utilisateur a cliqué</b>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> s.ActivityMap.link </td> 
   <td colname="col2"> 
    <code>
      //&nbsp;only&nbsp;ever&nbsp;use&nbsp;"title"&nbsp;attributes&nbsp;from&nbsp;A&nbsp;tags function(clickedElement){ &nbsp;&nbsp;&nbsp;var&nbsp;linkId; &nbsp;&nbsp;&nbsp;if(clickedElement&nbsp;&amp;&amp;&nbsp;clickedElement.tagName.toUpperCase()&nbsp;===&nbsp;'A'){ &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;linkId&nbsp;=&nbsp;clickedElement.getAttribute('title'); &nbsp;&nbsp;&nbsp;} &nbsp;&nbsp;&nbsp;return&nbsp;linkId; } 
    </code> </td> 
   <td colname="col3"> Fonction qui reçoit l’HTMLElement visité et doit renvoyer une valeur de chaîne qui représente <b>le lien sur lequel l’utilisateur a cliqué</b>. <p>Si la valeur renvoyée est false (nul, non défini, chaîne vide, 0), aucun lien n’est suivi. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> s.ActivityMap.region </td> 
   <td colname="col2"> 
    <code>
      //&nbsp;only&nbsp;ever&nbsp;use&nbsp;lowercase&nbsp;version&nbsp;of&nbsp;tag&nbsp;name&nbsp;concatenated&nbsp;with&nbsp;first&nbsp;className&nbsp;as&nbsp;the&nbsp;region function(clickedElement){ &nbsp;&nbsp;&nbsp;var&nbsp;regionId,className; &nbsp;&nbsp;&nbsp;while(clickedElement&nbsp;&amp;&amp;&nbsp;(clickedElement=&nbsp;clickedElement.parentNode)){ &nbsp;regionId&nbsp;=&nbsp;clickedElement.tagName; &nbsp;if(regionId){ &nbsp;return&nbsp;regionId.toLowerCase(); &nbsp;} &nbsp;} } 
    </code> </td> 
   <td colname="col3"> Fonction qui reçoit l’HTMLElement visité et doit renvoyer une valeur de chaîne qui représente <b>la région dans laquelle le lien a été trouvé lorsque l’utilisateur a cliqué dessus</b>. <p>Si la valeur renvoyée est false (nul, non défini, chaîne vide, 0), aucun lien n’est suivi. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> s.ActivityMap.linkExclusions </td> 
   <td colname="col2"> 
    <code>
      //&nbsp;Exclude&nbsp;links&nbsp;tagged&nbsp;with&nbsp;a&nbsp;special&nbsp;linkExcluded&nbsp;CSS&nbsp;class &nbsp;&lt;style&gt; .linkExcluded{ &nbsp;&nbsp;display:&nbsp;block; &nbsp;&nbsp;height:&nbsp;1px; &nbsp;&nbsp;left:&nbsp;-9999px; &nbsp;&nbsp;overflow:&nbsp;hidden; &nbsp;&nbsp;position:&nbsp;absolute; &nbsp;&nbsp;width:&nbsp;1px; } &lt;/style&gt; &lt;a&nbsp;href="next-page.html"&gt;Link&nbsp;is&nbsp;tracked&nbsp;because&nbsp;link&nbsp;does&nbsp;not&nbsp;have&nbsp;hidden&nbsp;text&nbsp;matching&nbsp;the&nbsp;filter.&nbsp;&lt;/a&gt; &lt;a&nbsp;href="next-page.html"&gt;Link&nbsp;not&nbsp;tracked&nbsp;because&nbsp;s.ActivityMap.linkExclusions&nbsp;is&nbsp;set&nbsp;and&nbsp;this&nbsp;link&nbsp;has&nbsp;hidden&nbsp;text&nbsp;matching&nbsp;the&nbsp;filter. &nbsp;&lt;span&nbsp;class="linkExcluded"&gt;exclude-link1&lt;/span&gt; &lt;/a&gt; &lt;a&nbsp;href="next-page.html"&gt;Link&nbsp;not&nbsp;tracked&nbsp;because&nbsp;s.ActivityMap.linkExclusions&nbsp;is&nbsp;set&nbsp;and&nbsp;this&nbsp;link&nbsp;has&nbsp;hidden&nbsp;text&nbsp;matching&nbsp;the&nbsp;filter. &nbsp;&lt;span&nbsp;class="linkExcluded"&gt;exclude-link2&lt;/span&gt; &lt;/a&gt; &lt;script&gt; &nbsp;&nbsp;var&nbsp;s&nbsp;=&nbsp;s_gi('samplersid'); &nbsp;&nbsp;s.ActivityMap.linkExclusions&nbsp;=&nbsp;'exclude-link1,exclude-link2'; &lt;/script&gt; 
    </code> </td> 
   <td colname="col3"> <p>Chaîne qui reçoit une liste séparée par des virgules de chaînes à rechercher dans le texte du lien. S’il est trouvé, le lien est exclu du suivi par [!Carte d’activités DNL]. S’il n’est pas défini, aucune tentative d’arrêt du suivi du lien par [!Carte d’activités DNL] n’est effectuée. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> s.ActivityMap.regionExclusions </td> 
   <td colname="col2"> 
    <code>
      //&nbsp;Exclude&nbsp;regions&nbsp;on&nbsp;the&nbsp;page&nbsp;from&nbsp;its&nbsp;links&nbsp;being&nbsp;trackable&nbsp;by&nbsp;ActivityMap &lt;div&nbsp;id="links-included"&gt;&nbsp; &nbsp;&nbsp;&lt;a&nbsp;href="next-page.html"&gt;Link&nbsp;is&nbsp;tracked&nbsp;because&nbsp;s.ActivityMap.regionExclusions&nbsp;is&nbsp;set&nbsp;but&nbsp;does&nbsp;not&nbsp;match&nbsp;the&nbsp;filter.&lt;/a&gt; &lt;/div&gt; &lt;div&nbsp;id="links-excluded"&gt;&nbsp; &nbsp;&nbsp;&lt;a&nbsp;href="next-page.html"&gt;Link&nbsp;not&nbsp;tracked&nbsp;because&nbsp;s.ActivityMap.regionExclusions&nbsp;is&nbsp;set&nbsp;and&nbsp;this&nbsp;link&nbsp;matches&nbsp;the&nbsp;filter.&lt;/a&gt; &lt;/div&gt; &lt;script&gt; &nbsp;&nbsp;var&nbsp;s&nbsp;=&nbsp;s_gi('samplersid'); &nbsp;&nbsp;s.ActivityMap.regionExclusions&nbsp;=&nbsp;'links-excluded'; &lt;/script&gt;
    </code> </td> 
   <td colname="col3"> <p>Chaîne qui reçoit une liste séparée par des virgules de chaînes à rechercher dans le texte de région. S’il est trouvé, le lien est exclu du suivi par [!Carte d’activités DNL]. S’il n’est pas défini, aucune tentative d’arrêt du suivi du lien par [!Carte d’activités DNL] n’est effectuée. </p> </td> 
  </tr> 
 </tbody> 
</table>
