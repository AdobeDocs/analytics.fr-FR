---
description: Décrit la méthode de calcul de mesures courantes à l’aide de flux de données.
keywords: Data Feed;job;metrics;pre column;post column;bots;date filtering;event string;common;formulas
solution: Analytics
title: Mesures calculées
topic: Reports and analytics
uuid: a45ea5bb-7c83-468f-b94a-63add78931d7
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Mesures calculées

Décrit la méthode de calcul de mesures courantes à l’aide de flux de données.

<!--Meike, I commented out this heading because it contains no content, and I'm troubleshooting a dita error-Bob
## Pre vs. Post column {#section_19967AF2FD9D44D6A8EC30F77E71F2ED}
-->

## Robots {#section_06753B95800F47668AAF52E7227F27C8}

Les robots sont exclus des flux de données conformément aux [règles de robots](https://marketing.adobe.com/resources/help/en_US/reference/bot_rules.html) définies dans votre suite de rapports.

## Filtrage par date {#section_3BFF4F7EED1F4FA69EBF12BF98B347E8}

Incluez les lignes issues de la plage de dates que vous souhaitez inclure en filtrant le champ `date_time`. The `date_time` field is human readable (for example, `YYYY-MM-DD HH:MM:SS`) and is adjusted to the time zone of the report suite. Par exemple, `date_time starts with "2013-12"` inclut les accès de décembre 2013.

## Chaîne d’événements {#section_87B686512EFD4A6CA072165CB28A130A}

The event string in `event_list` and `post_event_list` contains a comma-delimited list of events, which may have a value and/or a unique ID. Il est conseillé d’effectuer tout le traitement sur la colonne `post_event_list`, car elle est dédupliquée et a déjà appliqué la logique pour supprimer les événements en double avec le même ID (voir [Sérialisation d’événements](https://marketing.adobe.com/resources/help/en_US/sc/implement/c_event_serialization.html)).

Pour la correspondance de l’ID d’événement avec le nom, consultez le fichier de recherche d’événement fourni avec votre flux de données.

Pour plus d’informations sur les événements, reportez-vous à la section [events](https://marketing.adobe.com/resources/help/en_US/sc/implement/c_events.html).

## Formules des mesures courantes {#section_E26A01C234484857BF8C74443222AE41}

Le tableau suivant contient des instructions permettant de calculer plusieurs mesures courantes.

<table id="table_814EA73C01EE4B2CA3CEB2839E19ADF9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Mesure </th> 
   <th colname="col2" class="entry"> Méthode de calcul </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Pages vues </td> 
   <td colname="col2"> <p> Page views can be calculated by counting when there is either a value in <code> post_pagename </code> or <code> post_page_url </code>. </p> 
    <p>Vous pouvez utiliser une logique semblable pour comptabiliser les liens personnalisés : </p> 
    <ul id="ul_8DFBEE3ED30C465D8E55B1F3880D5263"> 
     <li id="li_009F2B7E3F9443889AE95B3358169444"> <code> post_page_event = 100 </code> pour comptabiliser les liens personnalisés. </li> 
     <li id="li_866DA2F5C2404347863CD1417F822FE8"> <code> post_page_event = 101 </code> pour comptabiliser les liens de téléchargement. </li> 
     <li id="li_4BC6E62CE8B1474DB22448FA32C9EE01"> <code> post_page_event = 102 </code> pour comptabiliser les liens de sortie. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visites </td> 
   <td colname="col2"> 
    <ol id="ol_FE1831195A474650B07D7820DCD38728"> 
     <li id="li_274590E937A142D19B204768B1F10325">Exclude all rows where <code> exclude_hit &gt; 0 </code>. </li> 
     <li id="li_038B8FF66EA44E138C8A8932DA7B39E5">Exclude all rows with <code> hit_source = 5,7,8,9 </code>. 5, 8 et 9 sont des lignes récapitulatives téléchargées à l’aide de sources de données. 7 représente les téléchargements de source de données d’identifiant de transaction qui ne doivent pas être inclus dans les comptes de visites et de visiteurs. Reportez-vous à la section <a href="/help/export/analytics-data-feed/c-df-contents/datafeeds-hit-source.md"  > Recherche de sources d’accès </a>. </li> 
     <li id="li_7FCD9BDF4D8547719420B34BA48BFA2D">Combinez <code> post_visid_high </code>, <code> post_visid_low </code>, <code> visit_num </code>et <code> visit_start_time_gmt </code>*. Comptez le nombre unique de combinaisons. </li> 
    </ol> <p>*Dans de rares circonstances, des irrégularités Internet ou système ou l’utilisation d’identifiants visiteur personnalisés génèrent pour un même identifiant visiteur des valeurs <code> visit_num </code> en double qui ne concernent pas la même <a href="https://marketing.adobe.com/resources/help/en_US/reference/metrics_visit.html"  >visite </a>. To avoid resulting issues, also include <code> visit_start_time_gmt </code> when counting visits. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visiteurs </td> 
   <td colname="col2"> 
    <ol id="ol_E2BC9235A3164EF5936EFC5D9E9327D0"> 
     <li id="li_2C145CA54EBF4B358FC7DC78D8DA577D">Exclude all rows where <code> exclude_hit &gt; 0 </code>. </li> 
     <li id="li_9EF364652A214A4D9B66552BC6BBE527">Exclude all rows with <code> hit_source = 5,7,8,9 </code>. 5, 8 et 9 sont des lignes récapitulatives téléchargées à l’aide de sources de données. 7 représente les téléchargements de source de données d’identifiant de transaction qui ne doivent pas être inclus dans les comptes de visites et de visiteurs. Reportez-vous à la section <a href="/help/export/analytics-data-feed/c-df-contents/datafeeds-hit-source.md"  > Recherche de sources d’accès </a> </li> 
     <li id="li_4AB5129315644A29987E8FCB9C9F9C39">Combinez <code> post_visid_high </code> avec <code> post_visid_low </code>. Comptez le nombre unique de combinaisons. </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Instances d’événement </td> 
   <td colname="col2"> <p>When an event is set on a hit, <code> post_event_list </code> contains the event. The <code> post_event_list </code> is de-duplicated and is recommended to determine event instances. </p> <p>Par exemple : </p> 
    <code>
      post_event_list = 1,200 
    </code> <p>Indicates an instance of <code> purchase </code> and <code> event1 </code>. </p> 
    <ol id="ol_84B529A668A54686957D1EB36D944467"> 
     <li id="li_F953D7668C704C1AB7970123E369472A">Exclude all rows where <code> exclude_hit &gt; 0 </code>. </li> 
     <li id="li_65B0B504DB654479844EAE490D9283EB">Exclude all rows with <code> hit_source = 5,8,9 </code>. Il s’agit de lignes récapitulatives téléchargées à l’aide de sources de données. Reportez-vous à la section <a href="/help/export/analytics-data-feed/c-df-contents/datafeeds-hit-source.md"  > Recherche de sources d’accès </a>. </li> 
     <li id="li_FB1C31048EC7415088F41E8CDC01AEBD">Count the number of times the event lookup value appears in <code> post_event_list </code>. </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Instances d’eVar </td> 
   <td colname="col2"> <p>Lorsqu’une eVar est définie sur un accès, <code> event_list </code> contient une instance de cette eVar. </p> <p>Par exemple : </p> 
    <code>
      post_event_list&amp;nbsp;=&amp;nbsp;100,101,106 
    </code> <p>Indicates an instance of <code> eVar1 </code>, <code> eVar2 </code>, and <code> eVar7 </code>. Cela signifie qu’une valeur pour ces trois eVar a été définie sur l’accès. </p> <p>Pour calculer des instances pour des eVars, utilisez la même logique que celle expliquée dans la section <i>Instances d’événement</i> ci-dessus, mais comptez le nombre de fois où la recherche d’eVar apparaît dans la colonne <code> post_event_list </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Durée de la visite </td> 
   <td colname="col2"> <p>Pour calculer la durée passée, vous devez grouper les accès par visite, puis les classer en fonction du numéro de l’accès dans la visite. </p> 
    <ol id="ol_946E7CD6005A42EB9A4B79268BF84066"> 
     <li id="li_D109FAF4686D4935B7A6DCA5D383612F">Exclude all rows where <code> exclude_hit &gt; 0 </code>. </li> 
     <li id="li_D88F3691DB6746EBA84AA52841E56803">Group hits for a visit by concatenating <code> visid_high </code>, <code> visid_low </code>, and <code> visit_num </code>. </li> 
     <li id="li_08792F3BDFEA4DA29E0983C4BE65D73B">Order hits for each visit by <code> visit_page_num </code>. </li> 
     <li id="li_4B956734DBB84603B86DDA6A2B0B41A0">Using <a href="/help/export/analytics-data-feed/c-df-contents/datafeeds-page-event.md"  > page_event </a>, filter the types of hits you want. </li> 
     <li id="li_2C5AC0477CFC409B8F169079354C8226">Recherchez les accès où est définie la valeur pour laquelle vous souhaitez effectuer un suivi de la durée passée. Par exemple : <code>
        hit&nbsp;1:&nbsp;post_prop1=red hit&nbsp;2:&nbsp;post_prop1=blue 
      </code> </li> 
     <li id="li_20106B322F7B45CE8D2FBD9B0CB3D60D">Subtract the <code> post_cust_hit_time </code> for hit 1 from the <code> post_cust_hit_time </code> for hit 2 to determine the seconds between these two hits. The result is the time spent for <code> post_prop1=red </code>. Si le résultat est négatif, ceci indique que l’accès a eu lieu hors contexte et que le calcul doit être ignoré. </li> 
    </ol> <p>Cette logique peut être étendue afin de calculer la durée passée pour d’autres valeurs. When calculating time spent, Analytics calculates time spent based on the time the value was set in a <code> track </code> ( <code> page_event=0 </code>) or <code> trackLink </code> ( <code> page_event=10|11|12 </code>) call, to the time of the next page view ( <code> track </code> call). </p> <p>Lors du report de la durée de la visite pour une période spécifique, les Reports &amp; Analytics marketing et les Ad Hoc Analysis évaluent les accès au-delà de la période du rapport, afin de déterminer la durée de la visite pour les valeurs pendant la période du rapport, sauf quand la date de début et/ou de fin de la période correspond à une limite mensuelle. En raison de la complexité de ces calculs, il peut être difficile de faire correspondre exactement les mesures de durée de la visite. Data Warehouse n’évalue pas les accès au-delà de la période de création du rapport. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Recettes, commandes, unités </td> 
   <td colname="col2"> <p>La conversion de devise est appliquée à <code> post_product_list </code> en fonction des paramètres de la suite de rapports. L’utilisation de cette colonne est donc recommandée. </p> 
    <ol id="ol_03D62086EDDE42AD82049830D85FDC69"> 
     <li id="li_2A5B8205EA30492986C35DC382B91F16">Exclude all rows where <code> exclude_hit &gt; 0 </code>. </li> 
     <li id="li_6417C228AC414B01A30F85BE4842ED3C">Exclude all rows with <code> hit_source = 5,8,9 </code>. 5-9 représentent des lignes récapitulatives téléchargées à l’aide de sources de données. Reportez-vous à la section <a href="/help/export/analytics-data-feed/c-df-contents/datafeeds-hit-source.md"  > Recherche de sources d’accès </a>. </li> 
     <li id="li_C48F91C74F5E4286B5F0B285E33AF733">Ignore purchase data for rows where <code> duplicate_purchase = 1 </code>. Cet indicateur signale que l’achat est un doublon (ce qui signifie qu’un accès avec la même variable <code> purchaseID </code> a déjà été enregistré). </li> 
     <li id="li_FA1639FEF516419BA1BFDC37B063B346"> <p><code> post_product_list </code> utilise la même syntaxe que <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/c_products.html"  >s.products</a>. Vous pouvez donc analyser cette chaîne pour calculer des mesures. Par exemple : </p> 
      <code>
        ;Cross Trainers;1;69.95,;Athletic Socks;10;29.99 
      </code> <p>En analysant cette chaîne, vous pouvez déterminer qu’une paire de chaussures de sport a été achetée 69,95 USD et que le total des recettes de cet achat s’est élevé à 99,94 USD. </p> </li> 
    </ol> <p>Remarque : Analytics permet de transmettre des événements monétaires contenant des recettes de produit dans la chaîne d’événements. Dès lors, il se peut que vous deviez tenir compte des recettes qui ne figurent pas dans la chaîne de produits. Reportez-vous à la section <i>Événements numériques/monétaires</i> dans <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/c_events.html"  >s.events </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>
