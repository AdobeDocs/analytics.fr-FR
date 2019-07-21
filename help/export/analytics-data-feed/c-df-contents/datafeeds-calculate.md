---
description: Décrit la méthode de calcul de mesures courantes à l’aide de flux de données.
keywords: Flux de données ; tâche ; mesures ; « pré » ; Colonne Post ; robots ; filtrage de date ; string, chaîne ; common ; formules
seo-description: Décrit la méthode de calcul de mesures courantes à l’aide de flux de données.
seo-title: Calcul des mesures
solution: Analytics
title: Calcul des mesures
topic: Reports and Analytics
uuid: a 45 ea 5 bb -7 c 83-468 f-b 94 a -63 add 78931 d 7
translation-type: tm+mt
source-git-commit: 01a6fc7e44dc71b868bd38a4f6a5a4089eae6349

---


# Calcul des mesures

Décrit la méthode de calcul de mesures courantes à l’aide de flux de données.

<!--Meike, I commented out this heading because it contains no content, and I'm troubleshooting a dita error-Bob
## Pre vs. Post column {#section_19967AF2FD9D44D6A8EC30F77E71F2ED}
-->

## Robots {#section_06753B95800F47668AAF52E7227F27C8}

Les robots sont exclus des flux de données conformément aux [règles de robots](https://marketing.adobe.com/resources/help/en_US/reference/?f=bot_rules) définies dans votre suite de rapports.

## Filtrage par date {#section_3BFF4F7EED1F4FA69EBF12BF98B347E8}

Incluez les lignes issues de la plage de dates que vous souhaitez inclure en filtrant le champ `date_time`. `date_time` Le champ est lisible par une personne (par exemple) `YYYY-MM-DD HH:MM:SS`et est ajusté au fuseau horaire de la suite de rapports. For example, `date_time starts with "2013-12"` includes hits from December 2013.

## Chaîne d’événements {#section_87B686512EFD4A6CA072165CB28A130A}

The event string in `event_list` and `post_event_list` contains a comma-delimited list of events, which may have a value and/or a unique ID. Il est conseillé d’effectuer tout le traitement sur la colonne `post_event_list`, car elle est dédupliquée et a déjà appliqué la logique pour supprimer les événements en double avec le même ID (voir [Sérialisation d’événements](https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=c_event_serialization)).

Pour la correspondance de l’ID d’événement avec le nom, consultez le fichier de recherche d’événement fourni avec votre flux de données.

Pour plus d’informations sur les événements, reportez-vous à la section [events](https://marketing.adobe.com/resources/help/en_US/sc/implement/index.html?f=c_events).

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
   <td colname="col2"> <p> Les pages vues peuvent être calculées en comptant le nombre de valeurs dans <code>post_pagename</code> ou <code>post_page_url </code>. </p> 
    <p>Vous pouvez utiliser une logique semblable pour comptabiliser les liens personnalisés : </p> 
    <ul id="ul_8DFBEE3ED30C465D8E55B1F3880D5263"> 
     <li id="li_009F2B7E3F9443889AE95B3358169444"> <code> post_page_event = 100</code> pour comptabiliser les liens personnalisés. </li> 
     <li id="li_866DA2F5C2404347863CD1417F822FE8"> <code> post_page_event = 101</code> pour comptabiliser les liens de téléchargement. </li> 
     <li id="li_4BC6E62CE8B1474DB22448FA32C9EE01"> <code> post_page_event = 102</code> pour comptabiliser les liens de sortie. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visites </td> 
   <td colname="col2"> 
    <ol id="ol_FE1831195A474650B07D7820DCD38728"> 
     <li id="li_274590E937A142D19B204768B1F10325">Excluez toutes les lignes où <code>exclude_hit &gt; 0 </code>. </li> 
     <li id="li_038B8FF66EA44E138C8A8932DA7B39E5">Excluez toutes les lignes dont la valeur <code>hit_source = 5,7,8,9 </code>. 5, 8 et 9 sont des lignes récapitulatives téléchargées à l’aide de sources de données. 7 représente les téléchargements de source de données d’identifiant de transaction qui ne doivent pas être inclus dans les comptes de visites et de visiteurs. Reportez-vous à la section <a href="../../../export/analytics-data-feed/c-df-contents/datafeeds-hit-source.md#concept_FE4C114F6A524F7593D5CAC944C36C42" format="dita" scope="local"> Recherche de sources d’accès </a>. </li> 
     <li id="li_7FCD9BDF4D8547719420B34BA48BFA2D">Combinez <code>post_visid_high</code>, <code>post_visid_low</code>, <code>visit_num</code> et <code>visit_start_time_gmt </code>*. Comptez le nombre unique de combinaisons. </li> 
    </ol> <p>*Dans de rares circonstances, des irrégularités Internet ou système ou l’utilisation d’identifiants visiteur personnalisés génèrent pour un même identifiant visiteur des valeurs <code>visit_num</code> en double qui ne concernent pas la même <a href="https://marketing.adobe.com/resources/help/en_US/reference/?f=metrics_visit" format="http" scope="external">visite </a>. Pour éviter des problèmes par la suite, incluez également <code>visit_start_time_gmt</code> lorsque vous comptabilisez les visites. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visiteurs </td> 
   <td colname="col2"> 
    <ol id="ol_E2BC9235A3164EF5936EFC5D9E9327D0"> 
     <li id="li_2C145CA54EBF4B358FC7DC78D8DA577D">Excluez toutes les lignes où <code>exclude_hit &gt; 0 </code>. </li> 
     <li id="li_9EF364652A214A4D9B66552BC6BBE527">Excluez toutes les lignes dont la valeur <code>hit_source = 5,7,8,9 </code>. 5, 8 et 9 sont des lignes récapitulatives téléchargées à l’aide de sources de données. 7 représente les téléchargements de source de données d’identifiant de transaction qui ne doivent pas être inclus dans les comptes de visites et de visiteurs. Reportez-vous à la section <a href="../../../export/analytics-data-feed/c-df-contents/datafeeds-hit-source.md#concept_FE4C114F6A524F7593D5CAC944C36C42" format="dita" scope="local"> Recherche de sources d’accès </a> </li> 
     <li id="li_4AB5129315644A29987E8FCB9C9F9C39">Combinez <code>post_visid_high</code> avec <code>post_visid_low </code>. Comptez le nombre unique de combinaisons. </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Instances d’événement </td> 
   <td colname="col2"> <p>Lorsqu’un événement est défini sur un accès, il est contenu dans la colonne <code>post_event_list</code>. La colonne <code>post_event_list</code> est dédupliquée et recommandée pour déterminer les instances d’événement. </p> <p>Par exemple : </p> 
    <code>post_ event_ list = 1 200 </code>
  <p>indique une instance de <code>purchase</code> et <code>event1 </code>. </p> 
    <ol id="ol_84B529A668A54686957D1EB36D944467"> 
     <li id="li_F953D7668C704C1AB7970123E369472A">Excluez toutes les lignes où <code>exclude_hit &gt; 0 </code>. </li> 
     <li id="li_65B0B504DB654479844EAE490D9283EB">Excluez toutes les lignes avec <code>hit_source = 5,8,9 </code>. Il s’agit de lignes récapitulatives téléchargées à l’aide de sources de données. Reportez-vous à la section <a href="../../../export/analytics-data-feed/c-df-contents/datafeeds-hit-source.md#concept_FE4C114F6A524F7593D5CAC944C36C42" format="dita" scope="local"> Recherche de sources d’accès </a>. </li> 
     <li id="li_FB1C31048EC7415088F41E8CDC01AEBD">Comptez le nombre de fois où la valeur de recherche d’événement apparaît dans la colonne <code>post_event_list </code>. </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Instances d’eVar </td> 
   <td colname="col2"> <p>Lorsqu’une eVar est définie sur un accès, <code>event_list</code> contient une instance de cette eVar. </p> <p>Par exemple : </p> 
    <code>post_ event_ list &amp; amp ; nbsp ; = &amp; amp ; nbsp ; 100,101,106 </code>
  <p>indique une instance de <code>eVar1</code>, <code>eVar2</code> et <code>eVar7 </code>. Cela signifie qu’une valeur pour ces trois eVar a été définie sur l’accès. </p> <p>Pour calculer des instances pour des eVars, utilisez la même logique que celle expliquée dans la section <i>Instances d’événement</i> ci-dessus, mais comptez le nombre de fois où la recherche d’eVar apparaît dans la colonne <code>post_event_list </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Durée de la visite </td> 
   <td colname="col2"> <p>Pour calculer la durée passée, vous devez grouper les accès par visite, puis les classer en fonction du numéro de l’accès dans la visite. </p> 
    <ol id="ol_946E7CD6005A42EB9A4B79268BF84066"> 
     <li id="li_D109FAF4686D4935B7A6DCA5D383612F">Excluez toutes les lignes où <code>exclude_hit &gt; 0 </code>. </li> 
     <li id="li_D88F3691DB6746EBA84AA52841E56803">Groupez les accès pour une visite en concaténant <code>visid_high</code>, <code>visid_low</code> et <code>visit_num </code>. </li> 
     <li id="li_08792F3BDFEA4DA29E0983C4BE65D73B">Classez les accès pour chaque visite par <code>visit_page_num </code>. </li> 
     <li id="li_4B956734DBB84603B86DDA6A2B0B41A0">Using <a href="../../../export/analytics-data-feed/c-df-contents/datafeeds-page-event.md#concept_A3AC076C3728445EB4CC572A6EDA5263" format="dita" scope="local"> page_event </a>, filter the types of hits you want. </li> 
     <li id="li_2C5AC0477CFC409B8F169079354C8226">Recherchez les accès où est définie la valeur pour laquelle vous souhaitez effectuer un suivi de la durée passée. For example: 
      <code>
        hit 1: post_prop1=red hit 2: post_prop1=blue 
      </code> </li> 
     <li id="li_20106B322F7B45CE8D2FBD9B0CB3D60D">Soustrayez la valeur <code>post_cust_hit_time</code> pour l’accès 1 de la valeur <code>post_cust_hit_time</code> pour l’accès 2 afin de déterminer les secondes entre ces deux accès. Le résultat correspond à la durée passée pour <code>post_prop1=red </code>. Si le résultat est négatif, ceci indique que l’accès a eu lieu hors contexte et que le calcul doit être ignoré. </li> 
    </ol> <p>Cette logique peut être étendue afin de calculer la durée passée pour d’autres valeurs. Lors du calcul de la durée de la visite, Analytics calcule la durée passée en fonction de l’heure à laquelle la valeur a été définie dans un appel <code>track</code> (<code>page_event=0</code>) ou <code>trackLink</code> (<code>page_event=10|11|12</code>), jusqu’à l’heure du prochain affichage de la page (appel <code>track</code>). </p> <p>Lors du report de la durée de la visite pour une période spécifique, les Reports &amp; Analytics marketing et les Ad Hoc Analysis évaluent les accès au-delà de la période du rapport, afin de déterminer la durée de la visite pour les valeurs pendant la période du rapport, sauf quand la date de début et/ou de fin de la période correspond à une limite mensuelle. En raison de la complexité de ces calculs, il peut être difficile de faire correspondre exactement les mesures de durée de la visite. Data Warehouse n’évalue pas les accès au-delà de la période de création du rapport. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Recettes, commandes, unités </td> 
   <td colname="col2"> <p>La conversion de devise est appliquée à <code>post_product_list</code> en fonction des paramètres de la suite de rapports. L’utilisation de cette colonne est donc recommandée. </p> 
    <ol id="ol_03D62086EDDE42AD82049830D85FDC69"> 
     <li id="li_2A5B8205EA30492986C35DC382B91F16">Excluez toutes les lignes où <code>exclude_hit &gt; 0 </code>. </li> 
     <li id="li_6417C228AC414B01A30F85BE4842ED3C">Excluez toutes les lignes avec <code>hit_source = 5,8,9 </code>. 5-9 représentent des lignes récapitulatives téléchargées à l’aide de sources de données. Reportez-vous à la section <a href="../../../export/analytics-data-feed/c-df-contents/datafeeds-hit-source.md#concept_FE4C114F6A524F7593D5CAC944C36C42" format="dita" scope="local"> Recherche de sources d’accès </a>. </li> 
     <li id="li_C48F91C74F5E4286B5F0B285E33AF733">Ignorez les données d’achat pour les lignes où <code>duplicate_purchase = 1 </code>. Cet indicateur signale que l’achat est un doublon (ce qui signifie qu’un accès avec la même variable <code>purchaseID</code> a déjà été enregistré). </li> 
     <li id="li_FA1639FEF516419BA1BFDC37B063B346"> <p><code>post_product_list</code> utilise la même syntaxe que <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=c_products" format="http" scope="external">s.products</a>. Vous pouvez donc analyser cette chaîne pour calculer des mesures. Par exemple : </p> 
      <code>; Formateurs croisés ; 1 ; 69.95 ; Chaussettes athlétiques ; 10 ; 29,99 </code>
  <p>En analysant cette chaîne, vous pouvez déterminer qu’une paire de chaussures de sport a été achetée 69,95 USD et que le total des recettes de cet achat s’est élevé à 99,94 USD. </p> </li> 
    </ol> <p>Remarque : Analytics permet de transmettre des événements monétaires contenant des recettes de produit dans la chaîne d’événements. Dès lors, il se peut que vous deviez tenir compte des recettes qui ne figurent pas dans la chaîne de produits. Reportez-vous à la section <i>Événements numériques/monétaires</i> dans <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=c_events" format="http" scope="external">s.events </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>
