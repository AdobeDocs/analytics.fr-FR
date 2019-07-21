---
description: Lorsque vous sélectionnez l’icône représentant un engrenage en regard d’une mesure, vous pouvez spécifier le type de mesure et le modèle d’attribution.
seo-description: Lorsque vous sélectionnez l’icône représentant un engrenage en regard d’une mesure, vous pouvez spécifier le type de mesure et le modèle d’attribution.
seo-title: Type de mesure et attribution
title: Type de mesure et attribution
uuid: 64649698-df 2 a -42 c 3-bb 31-938 f 766 e 1 d 1 f
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Type de mesure et attribution

Lorsque vous sélectionnez l’icône représentant un engrenage en regard d’une mesure, vous pouvez spécifier le type de mesure et le modèle d’attribution.

* [Type de mesure](../../../../../components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md#section_34A86FB402F94E988724232283BF18B7)
* [Modèle d’attribution de colonnes](../../../../../components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md#section_F9690FD1943B403AB28E2FAC54EFE032)
* [Fonctionnement de l’allocation linéaire (à partir du 19 juillet 2018)](../../../../../components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md#section_EDBB2E14A6C248C5A79C0913C02D7CA1)

## Type de mesure {#section_34A86FB402F94E988724232283BF18B7}

![](assets/cm_type_alloc.png)

| Type de mesure | Définition |
|---|---|
| Standard | These metrics are the same metrics used in standard [!DNL Analytics] reporting. Si une formule est composée d’une seule mesure standard, elle affiche des données identiques à sa contrepartie de mesure non calculée. Les mesures standard sont utiles pour créer des mesures calculées spécifiques à chaque ligne. For example, [Orders] / [Visits] takes orders for that specific line item and divides it by the number of visits for that specific line item. |
| Total | Utilisez le total correspondant à la période de création de rapports de chaque ligne. Si une formule est composée d’un nombre total de mesures unique, elle affiche le même nombre total sur chaque ligne. Le nombre total de mesures est utile pour la création de mesures calculées qui sont comparées au nombre total de données du site. For example, [Orders] / [Total Visits] shows the proportion of orders against ALL visits to your site, not just the visits to the specific line item. |

## Modèle d’attribution de colonnes {#section_F9690FD1943B403AB28E2FAC54EFE032}

>[!IMPORTANT]
>
>In July 2018, [!DNL Analytics] introduced [Attribution IQ](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/attribution.html), which revised the way allocation models in calculated metrics are evaluated. Dans le cadre de cette modification, les mesures calculées qui n’utilisent pas un modèle d’attribution par défaut ont été migrées vers des nouveaux modèles d’attribution améliorés :
>
>* Pour obtenir la liste complète des modèles d’attribution qui ne sont pas par défaut et les intervalles de recherche en amont pris en charge, consultez la documentation d’[Attribution IQ](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/attribution.html).
>* Les modèles d’attribution « Dernière touche canal marketing » et « Première touche canal marketing » seront migrés vers les nouveaux modèles d’attribution « Dernière touche » et « Première touche », respectivement. (Remarque : les rapports « Canaux marketing » ne seront pas obsolètes, seuls les deux modèles d’attribution qui apparaissent dans les mesures calculées le seront.)
>* De plus, nous corrigerons la façon dont l’affectation linéaire est calculée. Pour les clients qui utilisent des mesures calculées avec des modèles d’attribution « linéaire », les rapports peuvent légèrement changer afin de tenir compte du nouveau modèle d’attribution corrigé. This change to calculated metrics will be reflected in Analysis Workspace, [!UICONTROL Reports &amp; Analytics], the Reporting API, Report Builder, and Ad Hoc Analysis. Pour plus d’informations, voir la section [Fonctionnement de l’allocation linéaire (à partir du 19 juillet 2018)](../../../../../components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md#section_EDBB2E14A6C248C5A79C0913C02D7CA1).
>



## Fonctionnement de l’allocation linéaire (à partir du 19 juillet 2018) {#section_EDBB2E14A6C248C5A79C0913C02D7CA1}

En juillet 2018, Adobe a modifié la manière dont l'allocation linéaire est consignée pour les mesures calculées. This change impacts Analysis Workspace, Ad Hoc Analysis, [!UICONTROL Reports &amp; Analytics], Report Builder, Activity Map, and the Reporting APIs. Elle concernera essentiellement les eVars et autres dimensions présentant une persistance. Note that these changes will only apply to calculated metrics and will not impact other reports using linear allocation (such as the Pages report in [!UICONTROL Reports &amp; Analytics]). Les autres rapports utilisant l’affectation linéaire continueront d’appliquer la méthode existante d’affectation linéaire.

L’exemple suivant explique comment les mesures calculées avec l’affectation linéaire changeront dans les rapports :

<table id="table_E66D066A3E7B4232BBC220775F8B985A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col2" class="entry"> Accès 1 </th> 
   <th colname="col3" class="entry"> Accès 2 </th> 
   <th colname="col4" class="entry"> Accès 3 </th> 
   <th colname="col5" class="entry"> Accès 4 </th> 
   <th colname="col6" class="entry"> Accès 5 </th> 
   <th colname="col7" class="entry"> Accès 6 </th> 
   <th colname="col8" class="entry"> Accès 7 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Données envoyées dans </p> </td> 
   <td colname="col2"> PROMO A </td> 
   <td colname="col3"> - </td> 
   <td colname="col4"> PROMO A </td> 
   <td colname="col5"> PROMO B </td> 
   <td colname="col6"> - </td> 
   <td colname="col7"> PROMO C </td> 
   <td colname="col8"> 10 $ </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>eVar de dernière touche </p> </td> 
   <td colname="col2"> PROMO A </td> 
   <td colname="col3"> PROMO A </td> 
   <td colname="col4"> PROMO A </td> 
   <td colname="col5"> PROMO B </td> 
   <td colname="col6"> PROMO B </td> 
   <td colname="col7"> PROMO C </td> 
   <td colname="col8"> 10 $ </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>eVar de première touche </p> </td> 
   <td colname="col2"> PROMO A </td> 
   <td colname="col3"> PROMO A </td> 
   <td colname="col4"> PROMO A </td> 
   <td colname="col5"> PROMO A </td> 
   <td colname="col6"> PROMO A </td> 
   <td colname="col7"> PROMO A </td> 
   <td colname="col8"> 10 $ </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Exemple de Prop </p> </td> 
   <td colname="col2"> PROMO A </td> 
   <td colname="col3"> - </td> 
   <td colname="col4"> PROMO A </td> 
   <td colname="col5"> PROMO B </td> 
   <td colname="col6"> - </td> 
   <td colname="col7"> PROMO C </td> 
   <td colname="col8"> 10 $ </td> 
  </tr> 
 </tbody> 
</table>

Dans cet exemple, les valeurs A, B et C ont été envoyées dans une variable aux accès 1, 3, 4 et 6 avant la réalisation d’un achat de 10 $ à l’accès 7. Dans la deuxième ligne, ces valeurs persistent dans les accès sur une base de visite de dernière touche. La troisième ligne représente une persistance de visite de première touche. Enfin, la dernière ligne indique comment les données seraient enregistrées pour une Prop qui ne présente pas de persistance.

**Résumé du fonctionnement de l’affectation linéaire avant le mois de juillet 2018**

Avant le 19 juillet 2018, l’attribution linéaire était calculée après que la persistance de première touche ou de dernière touche ait eu lieu. Cela signifiait que pour l’eVar de dernière touche ci-dessus, les 10 $ auraient été distribués comme suit : A = 10 * (3/6) = 5 $, B = 10 * (2/6) = 3,33 $, C = 10 * (1/6) = 1,67 $.

Pour l’eVar de première touche ci-dessus, les 10 $ auraient été entièrement attribués à A. Pour la Prop : A = 10 * (2/4) = 5 $, B = 10 * (1/4) = 2,50 $, et C = 10 * (1/4) = 2,50 $. Pour résumer l’affectation linéaire telle qu’elle fonctionnait auparavant :

| Valeurs | eVar de dernière touche actuelle | eVar de première touche actuelle | Prop actuelle |
|---|---|---|---|
| PROMO A | 5,00 $ | 10,00 $ | 5,00 $ |
| PROMO B | 3,33 $ | 0 $ | 2,50 $ |
| PROMO C | 1,67 $ | 0 $ | 2,50 $ |
| Total | 10,00 $ | 10,00 $ | 10,00 $ |

**Résumé du fonctionnement de l’affectation linéaire à partir du 19 juillet 2018**

À compter du 19 juillet, nous avons corrigé ce comportement dans les mesures calculées. Instead of using the persisted values based on last touch or first touch, [!DNL Analytics] now uses only the values that were passed in (the first row of the top table). En tant que tels, les paramètres d’affectation de dimension n’ont plus d’impact sur la manière dont l’affectation linéaire est calculée (autrement dit, les Props et les eVars sont traitées de la même manière), et les résultats reflètent ce qui a été passé à l’origine plutôt que les valeurs de première touche et de dernière touche qui peuvent avoir persisté. Ainsi, dans les trois cas, A = 10 * (2/4) = 5 $, B = 10 * (1/4) = 2,50 $ et C = 10 * (1/4) = 2,50 $.

| Valeurs | Nouvelle eVar de dernière touche | Nouvelle eVar de première touche | Nouvelle Prop |
|---|---|---|---|
| PROMO A | 5,00 $ | 5,00 $ | 5,00 $ |
| PROMO B | 2,50 $ | 2,50 $ | 2,50 $ |
| PROMO C | 2,50 $ | 2,50 $ | 2,50 $ |
| Total | 10,00 $ | 10,00 $ | 10,00 $ |

<!-- 

<p>Additionally, as part of this change, [!DNL Analytics] is <b>changing how multiple sequential successes</b> are treated. In the following example, 7 hits occurred in the same visit with two orders, one $10 order on hit 4, and one $5 order on hit 7: </p> 
<table id="table_4647AA466D1447F6961DDC10468FCCE1"> 
 <tgroup cols="8">
  <colspec colnum="1" colname="col1" colwidth="1.00*" />
  <colspec colnum="2" colname="col2" colwidth="1.04*" />
  <colspec colnum="3" colname="col3" colwidth="1.02*" />
  <colspec colnum="4" colname="col4" colwidth="1.02*" />
  <colspec colnum="5" colname="col5" colwidth="1.03*" />
  <colspec colnum="6" colname="col6" colwidth="1.02*" />
  <colspec colnum="7" colname="col7" colwidth="1.02*" />
  <colspec colnum="8" colname="col8" colwidth="1.03*" />
  <thead> 
   <tr> 
    <th colname="col1" class="entry"> </th> 
    <th colname="col2" class="entry"> Hit 1 </th> 
    <th colname="col3" class="entry"> Hit 2 </th> 
    <th colname="col4" class="entry"> Hit 3 </th> 
    <th colname="col5" class="entry"> Hit 4 </th> 
    <th colname="col6" class="entry"> Hit 5 </th> 
    <th colname="col7" class="entry"> Hit 6 </th> 
    <th colname="col8" class="entry"> Hit 7 </th> 
   </tr>
  </thead> 
  <tbody> 
   <tr> 
    <td colname="col1"> <p>Data Sent In </p> </td> 
    <td colname="col2"> PROMO A </td> 
    <td colname="col3"> - </td> 
    <td colname="col4"> PROMO B </td> 
    <td colname="col5"> $10 </td> 
    <td colname="col6"> - </td> 
    <td colname="col7"> PROMO C </td> 
    <td colname="col8"> $5 </td> 
   </tr> 
   <tr> 
    <td colname="col1"> <p>Last Touch eVar </p> </td> 
    <td colname="col2"> PROMO A </td> 
    <td colname="col3"> PROMO A </td> 
    <td colname="col4"> PROMO B </td> 
    <td colname="col5"> $10 </td> 
    <td colname="col6"> PROMO B </td> 
    <td colname="col7"> PROMO C </td> 
    <td colname="col8"> $5 </td> 
   </tr> 
   <tr> 
    <td colname="col1"> <p>First Touch eVar </p> </td> 
    <td colname="col2"> PROMO A </td> 
    <td colname="col3"> PROMO A </td> 
    <td colname="col4"> PROMO A </td> 
    <td colname="col5"> $10 </td> 
    <td colname="col6"> PROMO A </td> 
    <td colname="col7"> PROMO A </td> 
    <td colname="col8"> $5 </td> 
   </tr> 
   <tr> 
    <td colname="col1"> <p>Example prop </p> </td> 
    <td colname="col2"> PROMO A </td> 
    <td colname="col3"> - </td> 
    <td colname="col4"> PROMO A </td> 
    <td colname="col5"> $10 </td> 
    <td colname="col6"> - </td> 
    <td colname="col7"> PROMO C </td> 
    <td colname="col8"> $5 </td> 
   </tr> 
  </tbody> 
 </tgroup> 
</table> 
<p> </p> 
<p>Currently (<b>prior to July 19, 2018</b>), linear attribution would carry forward past the initial conversion and persist into the second conversion </p> 
<ul id="ul_FD09813B59F04FF2A96A70BBE0A8F349"> 
 <li id="li_2EC965DDAE334C1795530F7C6F1674C5">In our first-touch eVar example, the total revenue for each promotion would be calculated using the promos prior to conversion on hit 4 for revenue on hit 4, but all promos for the conversion on hit 7. </li> 
 <li id="li_687C03C4B0A941AA800084F324A95FD6">In our last-touch eVar example, this would be: A = (2/3) * 10 + (2/5) * 5 = $8.66, B = (1/3) * 10 + (2/5) * 5 = $5.33, C = (1/5) * 5 = $1.00. In our FT eVar example: A = (3/3) * 10 + (5/5) * 5 = $15.00, and for the prop: A = (1/2) * 10 + (1/3) * 5 = $6.66, B = (1/2) * 10 + (1/3) * 5 = $6.66, and C = (1/3) * 5 = $1.66. </li> 
</ul> 
<p>Resulting in a distribution as follows: </p> 
<table id="table_6A066E602BF641B0BD4B175EE9753C6E"> 
 <tgroup cols="4">
  <colspec colnum="1" colname="col1" colwidth="*" />
  <colspec colnum="2" colname="col2" colwidth="*" />
  <colspec colnum="3" colname="col3" colwidth="*" />
  <colspec colnum="4" colname="col4" colwidth="*" />
  <thead> 
   <tr> 
    <th colname="col1" class="entry"> Values </th> 
    <th colname="col2" class="entry"> Current Last Touch eVar </th> 
    <th colname="col3" class="entry"> Current First Touch eVar </th> 
    <th colname="col4" class="entry"> Current Prop </th> 
   </tr>
  </thead> 
  <tbody> 
   <tr> 
    <td colname="col1"> PROMO A </td> 
    <td colname="col2"> $8.66 </td> 
    <td colname="col3"> $15.00 </td> 
    <td colname="col4"> $6.66 </td> 
   </tr> 
   <tr> 
    <td colname="col1"> PROMO B </td> 
    <td colname="col2"> $5.33 </td> 
    <td colname="col3"> $0.00 </td> 
    <td colname="col4"> $6.66 </td> 
   </tr> 
   <tr> 
    <td colname="col1"> PROMO C </td> 
    <td colname="col2"> $1.00 </td> 
    <td colname="col3"> $0.00 </td> 
    <td colname="col4"> $1.66 </td> 
   </tr> 
   <tr> 
    <td colname="col1"> Total </td> 
    <td colname="col2"> $15.00 </td> 
    <td colname="col3"> $15.00 </td> 
    <td colname="col4"> $15.00 </td> 
   </tr> 
  </tbody> 
 </tgroup> 
</table> 
<p> </p> 
<p><b>After July 19, 2018</b>, [!DNL Analytics] will treat each sequence of conversions independently, meaning linear attribution will no longer carry forward from one conversion to another. In the previous example, attribution will always be treated the same way (regardless of the eVar allocation settings as stated above) and will be calculated as follows: A = (1/2) * 10 = $5, B = (1/2) * 10 = $5, and C = (1/1) * 5 = $5. To summarize: </p> 
<table id="table_2D39CCD158BF488EA404324DF50B9579"> 
 <tgroup cols="4">
  <colspec colnum="1" colname="col1" colwidth="*" />
  <colspec colnum="2" colname="col2" colwidth="*" />
  <colspec colnum="3" colname="col3" colwidth="*" />
  <colspec colnum="4" colname="col4" colwidth="*" />
  <thead> 
   <tr> 
    <th colname="col1" class="entry"> Values </th> 
    <th colname="col2" class="entry"> New Last Touch eVar </th> 
    <th colname="col3" class="entry"> New First Touch eVar </th> 
    <th colname="col4" class="entry"> New Prop </th> 
   </tr>
  </thead> 
  <tbody> 
   <tr> 
    <td colname="col1"> PROMO A </td> 
    <td colname="col2"> $5.00 </td> 
    <td colname="col3"> $5.00 </td> 
    <td colname="col4"> $5.00 </td> 
   </tr> 
   <tr> 
    <td colname="col1"> PROMO B </td> 
    <td colname="col2"> $5.00 </td> 
    <td colname="col3"> $5.00 </td> 
    <td colname="col4"> $5.00 </td> 
   </tr> 
   <tr> 
    <td colname="col1"> PROMO C </td> 
    <td colname="col2"> $5.00 </td> 
    <td colname="col3"> $5.00 </td> 
    <td colname="col4"> $5.00 </td> 
   </tr> 
   <tr> 
    <td colname="col1"> Total </td> 
    <td colname="col2"> $15.00 </td> 
    <td colname="col3"> $15.00 </td> 
    <td colname="col4"> $15.00 </td> 
   </tr> 
  </tbody> 
 </tgroup> 
</table>

 -->

