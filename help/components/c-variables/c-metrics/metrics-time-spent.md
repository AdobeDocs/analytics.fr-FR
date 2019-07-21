---
description: Adobe Analytics propose différentes mesures et dimensions de durée de la visite. Découvrez-les ainsi que leur mode de calcul.
seo-description: Adobe Analytics propose différentes mesures et dimensions de durée de la visite. Découvrez-les ainsi que leur mode de calcul.
seo-title: Durée de la visite
solution: Analytics
title: Durée de la visite
topic: Mesures
uuid: a 9 f 63 da 3-7 e 79-49 c 3-9 b 0 b -6 dcd 2 ae 6 aadc
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Durée de la visite

Adobe Analytics propose différentes mesures et dimensions de durée de la visite. Découvrez-les ainsi que leur mode de calcul.

* [Mesures de durée de la visite](../../../components/c-variables/c-metrics/metrics-time-spent.md#section_4F54D70300944748A62088F5870E4B6C)
* [Dimensions de durée de la visite](../../../components/c-variables/c-metrics/metrics-time-spent.md#section_D51606544CB046FC902E2E317318892C)
* [Mode de calcul de la durée de la visite](../../../components/c-variables/c-metrics/metrics-time-spent.md#section_90A3882638974969A4B8B674FFDB7624)
* [Questions fréquentes relatives à la durée de la visite](../../../components/c-variables/c-metrics/metrics-time-spent.md#section_51C2735BACAB42CCBA1DD3CBF238E2F7)
* [Exemples de calcul](../../../components/c-variables/c-metrics/metrics-time-spent.md#section_3D63D6A601F34E42AD5366435CB610D5)

## Mesures de durée de la visite {#section_4F54D70300944748A62088F5870E4B6C}

Ce tableau répertorie les diverses mesures de durée de la visite, leur définition et les modules d’Adobe Analytics dans lesquels vous pouvez les utiliser.

<table id="table_7095406DF1614F3CAD5E437B919598D1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Mesure </th> 
   <th colname="col2" class="entry"> Définition </th> 
   <th colname="col3" class="entry"> Disponible dans </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Durée totale (secondes) </p> </td> 
   <td colname="col2"> <p>Représente la durée totale pendant laquelle les visiteurs interagissent avec un élément de dimension spécifique. </p> <p>Inclut l’instance d’une valeur et la persistance sur tous les accès suivants. Dans le cas des props, la durée de la visite est également prise en compte dans les événements de lien ultérieurs. </p> </td> 
   <td colname="col3"> <p>Analysis Workspace </p> <p>Reports &amp; Analytics </p> <p>Report Builder (appelé « durée totale de la visite ») </p> <p>Data Warehouse </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Durée de la visite (secondes) </p> </td> 
   <td colname="col2"> <p><i>Durée totale (secondes)/(visite-rebonds)</i> </p> <p>Représente la durée moyenne pendant laquelle les visiteurs interagissent avec un élément de dimension spécifique lors de chaque visite. </p> </td> 
   <td colname="col3"> <p>Analysis Workspace </p> <p>Reports &amp; Analytics </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Durée par visiteur (secondes) </p> </td> 
   <td colname="col2"> <p><i>Durée totale (secondes)/(visiteur unique - visiteurs uniques en rebond)</i> </p> <p>Représente la durée moyenne pendant laquelle les visiteurs interagissent avec un élément de dimension spécifique pendant la durée de vie du visiteur (durée de leur cookie). </p> </td> 
   <td colname="col3"> <p>Analysis Workspace </p> <p>Reports &amp; Analytics </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Durée moyenne de la visite du site (secondes) </p> </td> 
   <td colname="col2"> <p>Représente la durée totale pendant laquelle les visiteurs interagissent avec un élément de dimension spécifique, par séquence avec un élément de dimension. Cette option n’est pas limitée aux moyennes de la visite du « site » comme son nom l’indique. Pour plus d’informations sur les séquences, voir Mode de calcul de la durée de la visite. </p> <p>Remarque : Cette mesure différera très probablement de la durée de la visite au niveau d’un élément de dimension en raison des différences de dénominateur dans le calcul. </p> </td> 
   <td colname="col3"> <p>Analysis Workspace </p> <p>Reports &amp; Analytics (indiquée en minutes) </p> <p>Report Builder (indiquée en minutes) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Durée de consultation moyenne de la page </p> </td> 
   <td colname="col2"> <p><b>Mesure obsolète. </b> </p> <p>Il est recommandé d’utiliser « Durée moyenne de la visite du site » si la durée moyenne d’un élément de dimension est requise. </p> </td> 
   <td colname="col3"> <p>Report Builder (lorsqu’une dimension figure dans la demande) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Durée totale de la session </p> <p>(Aussi connue sous le nom : Durée de la session précédente) </p> </td> 
   <td colname="col2"> <p>SDK d’applications mobiles uniquement. Déterminée la prochaine fois que l’application est lancée, pour la session précédente. Calculée en secondes, cette mesure ne compte pas lorsque l’application est en arrière-plan, mais uniquement lorsqu’elle est en cours d’utilisation. Il s’agit d’une mesure au niveau de la session. </p> <p>Par exemple : vous installez l’application ABC et la lancez. Vous l’utilisez pendant 2 minutes, puis vous la fermez. Aucune donnée n’est envoyée pour cette mesure pendant cette session. La prochaine fois que vous la lancez, la durée totale de la session est envoyée avec une valeur de 120. </p> </td> 
   <td colname="col3"> <p>Analysis Workspace </p> <p>Reports &amp; Analytics </p> <p>Report Builder </p> <p>Interface utilisateur de Mobile Services </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Durée de session moyenne (mobile) </p> </td> 
   <td colname="col2"> <p>Durée totale de session/(lancements - Premiers lancements) </p> <p>SDK d’applications mobiles uniquement. Il s’agit d’une mesure au niveau de la session. </p> </td> 
   <td colname="col3"> <p>Report Builder </p> <p>Interface utilisateur de Mobile Services </p> </td> 
  </tr> 
 </tbody> 
</table>

## Dimensions de durée de la visite {#section_D51606544CB046FC902E2E317318892C}

Ce tableau répertorie les diverses dimensions de durée de la visite, leur définition et les modules d’Adobe Analytics dans lesquels vous pouvez les utiliser.

<table id="table_BF1B7B8620714105BFB5C1AC37ABE02C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Dimension </th> 
   <th colname="col2" class="entry"> Définition </th> 
   <th colname="col3" class="entry"> Disponible dans </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Temps passé par visite - Valeur granulaire </p> </td> 
   <td colname="col2"> <p>Durée totale passée lors la visite arrondie à la seconde la plus proche et appliquée à chaque accès qui faisait partie de la visite. Il s’agit d’une dimension du niveau de la visite. </p> </td> 
   <td colname="col3"> <p>Analysis Workspace </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Durée par visite – Regroupement </p> </td> 
   <td colname="col2"> <p>Dimension granulaire regroupée en 9 plages différentes. Il s’agit d’une dimension du niveau de la visite. Les plages incluent : </p> 
    <ul id="ul_BC909A2D22ED4D48A3F7CE6A666F26E5"> 
     <li id="li_0FB28A1F0D894B7C95724A8C6BD5B00B">Moins de 1 minute </li> 
     <li id="li_10223656420A475AAB3443981D49D10E">1-5 minutes </li> 
     <li id="li_0DEE723B81C64EAFB5BD1125D48D3AD2">5-10 minutes </li> 
     <li id="li_B736AC970E0049EB8844480702F345A6">10-30 minutes </li> 
     <li id="li_21B8ECC3EE66497E8D870A004351B04B">30-60 minutes </li> 
     <li id="li_79FB658128FD4F97AAE1A803F1687BD1">1-2 heures </li> 
     <li id="li_CCC0746FEB954BECB9E670ECCDBF30F3">2-5 heures </li> 
     <li id="li_BD7AFC524C814F9FAE423A4E301661D4">5-10 heures </li> 
     <li id="li_C9B5F1A83F99437A98A61756EE286687">10-15 heures </li> 
     <li id="li_8CC5A279D5804C5EA34C1B3589EF07BA">Plus de 15 heures </li> 
    </ul> <p>Remarque : Les visites de plus de 12 heures peuvent survenir lorsque les accès sont reçus dans le désordre. </p> </td> 
   <td colname="col3"> <p>Analysis Workspace </p> <p>Reports &amp; Analytics </p> <p>Report Builder </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Durée de consultation de la page - Granulaire </p> </td> 
   <td colname="col2"> <p>Durée totale passée sur chaque accès, arrondie à la seconde la plus proche. Il s’agit d’une dimension du niveau de l’accès. Elle comprend à la fois des pages vues et des événements de lien. Elle n’est pas limitée à la dimension « page » comme son nom l’indique. </p> </td> 
   <td colname="col3"> <p>Analysis Workspace </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Durée de consultation de la page – Regroupement </p> </td> 
   <td colname="col2"> <p>La dimension granulaire a été regroupée en 10 plages. Cependant, la dimension regroupée ne décompte que les pages vues (et exclut les événements de lien). Il s’agit d’une dimension du niveau de l’accès. Les plages incluent : </p> 
    <ul id="ul_D5F067A2520646A99AA261F9A4625C03"> 
     <li id="li_82307DE66EC548F0AD79DB1505A21F0D">moins de 15 secondes </li> 
     <li id="li_585965B82C4D43B6870978A5CE63B5B6">15 à 29 secondes </li> 
     <li id="li_5C20DC78E126472A838818EBA1D954D0">30 à 59 secondes </li> 
     <li id="li_2579C0B9279340ABA3AD4A527D758239">1 à 3 minutes </li> 
     <li id="li_E0FD800E948049A48DB4329A3E7A2478">3 à 5 minutes </li> 
     <li id="li_D9DBBFE6004F42BD80BB4F9268DF7DA7">5 à 10 minutes </li> 
     <li id="li_20F146799679456E8D6434D79EE12C31">10 à 15 minutes </li> 
     <li id="li_A38951A553A14AE7A0F23A904EEE35DE">15 à 20 minutes </li> 
     <li id="li_D44D773A344E47BFAA771302A49D8BD4">20 à 30 minutes </li> 
     <li id="li_8766683DB29147CD8470D2317F750E97">plus de 30 minutes </li> 
    </ul> </td> 
   <td colname="col3"> <p>Analysis Workspace </p> <p>Reports &amp; Analytics </p> </td> 
  </tr> 
 </tbody> 
</table>

## Mode de calcul de la durée de la visite {#section_90A3882638974969A4B8B674FFDB7624}

Adobe Analytics utilise des valeurs explicites (y compris les événements de lien et les affichages de vidéos) pour calculer la [!UICONTROL durée de la visite].

>[!NOTE]
>
>Without link events like [!UICONTROL Video Views] or [!UICONTROL Exit Links], time spent on the last hit of a visit cannot be known. En outre, pour des raisons similaires, les [!UICONTROL Visites de rebond] (c’est-à-dire les [!UICONTROL Visites] avec un seul accès) n’auront pas de [!UICONTROL Durée de la visite] associée.

Le **numérateur** dans tous les calculs de durée de la visite est « Durée totale (secondes) ».

Le **dénominateur** n’est pas disponible comme mesure distincte dans Analytics. Pour les mesures de durée de la visite au niveau de l’accès, les séquences sont utilisées comme dénominateur. Une séquence est un jeu consécutif d’accès pour lequel une variable donnée contient la même valeur (qu’elle soit définie, propagée ou persistante). Le terme « propagé » fait référence à la persistance des props entre les pages vues (c’est-à-dire entre les événements de lien ultérieurs), dans le but de calculer la durée de la visite.

* Par exemple, dans le cas du [!UICONTROL Nom de page] ou d’autres dimensions au niveau des accès, le dénominateur correspond essentiellement aux [!UICONTROL Instances] ou aux [!UICONTROL Pages vues], mais avec des actualisations et des valeurs non définies (par exemple, les événements de lien) comptabilisées comme une seule interaction (une séquence).

* Les accès [!UICONTROL Rebond] et [!UICONTROL Sortie] sont également supprimés du dénominateur car la durée de la visite ne peut pas être connue.

## Questions fréquentes relatives à la durée de la visite {#section_51C2735BACAB42CCBA1DD3CBF238E2F7}

<table id="table_D8BA825412B6420390CA78D77A5E57C2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Question </th> 
   <th colname="col2" class="entry"> Réponse </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>L’ensemble des mesures de durée de la visite peuvent-elles être appliquées à n’importe quelle dimension ? </p> </td> 
   <td colname="col2"> <p>Les mesures suivantes de durée de la visite peuvent être appliquées à n’importe quelle dimension : </p> 
    <ul id="ul_FC9513D0184B4A74BA1F4CCEA8BC1940"> 
     <li id="li_669156CC549040E08AB4977AF4B8AECB">Durée totale (secondes) </li> 
     <li id="li_3CCD7E7D127448689228E98A5EE854CB">Durée de la visite (secondes) </li> 
     <li id="li_1F61C157EC414C7F8702BC3F365AA2D7">Durée par visiteur (secondes) </li> 
     <li id="li_A3EF959A9BAB4872915F1A5C1A86D48E">Durée moyenne de la visite du site (secondes) </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Quelle dimension de durée de la visite est la plus appropriée pour une utilisation dans les ventilations avec d’autres dimensions ? </p> </td> 
   <td colname="col2"> <p>La dimension Durée de consultation de la page est une dimension de niveau accès. La ventilation de cette dimension en une autre dimension indique le nombre de secondes de la durée d’un accès lorsque la dimension de ventilation était également présente. </p> <p>Dans l’exemple ci-dessous, le terme de recherche « classifieds » est associé à des durées d’accès de 54 secondes, 59 secondes, etc., indiquant peut-être que les visiteurs passent du temps à lire le contenu renvoyé par ce terme de recherche. </p> <p><img placement="break" align="center"  src="assets/time-spent1.png" id="image_99FB62DCADDA4F8887B14333E65FF8FA" width="500px" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Quelle mesure convient à la dimension « Durée de consultation de la page - granulaire » ? </p> </td> 
   <td colname="col2"> <p>N’importe quelle mesure. La dimension indique la durée de la visite sur l’accès exact où l’événement s’est produit. Une durée plus longue de la visite signifie qu’un visiteur est resté plus longtemps sur une page (accès) où l’événement s’est produit. </p> <p><img placement="break" align="center"  src="assets/time-spent2.png" id="image_A741C1BA52254124B5C28D030FE20EFF" width="500px" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> En quoi la <span class="wintitle">Durée moyenne de la visite du site</span> diffère-t-elle de la <span class="wintitle">Durée de la visite</span> ? </td> 
   <td colname="col2"> <p>La différence est le dénominateur de la mesure : </p> 
    <ul id="ul_E9D7B4D3EDCC4691B2C724E0FE5480D2"> 
     <li id="li_CA34D84A3164473A8737D258425CA468">  La <span class="wintitle">Durée moyenne de la visite du site</span> utilise les séquences qui incluent un élément de dimension. </li> 
     <li id="li_2F2639480BE24927919732D00364EECA"> La <span class="wintitle">Durée de la visite</span> utilise le nombre de visites. </li> 
    </ul> <p>Par conséquent, ces mesures peuvent donner des résultats similaires au niveau de la visite, mais elles seront différentes au niveau de l’accès. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Exemples de calcul {#section_3D63D6A601F34E42AD5366435CB610D5}

Supposons que le jeu d’appels au serveur suivant concerne un seul visiteur au cours d’une visite unique :

<table id="table_63CBB5097E5A46659877E2CA3C94D81C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Accès de la visite </th> 
   <th colname="col2" class="entry"> 1 </th> 
   <th colname="col3" class="entry"> 2 </th> 
   <th colname="col4" class="entry"> 3 </th> 
   <th colname="col5" class="entry"> 4 </th> 
   <th colname="col6" class="entry"> 5 </th> 
   <th colname="col7" class="entry"> 6 </th> 
   <th colname="col8" class="entry"> 7 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Temps écoulé de la visite (sec)</b> </td> 
   <td colname="col2"> 0 </td> 
   <td colname="col3"> 30 </td> 
   <td colname="col4"> 80 </td> 
   <td colname="col5"> 180 </td> 
   <td colname="col6"> 190 </td> 
   <td colname="col7"> 230 </td> 
   <td colname="col8"> 290 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Secondes écoulées</b> </td> 
   <td colname="col2"> 30 </td> 
   <td colname="col3"> 50 </td> 
   <td colname="col4"> 100 </td> 
   <td colname="col5"> 10 </td> 
   <td colname="col6"> 40 </td> 
   <td colname="col7"> 60 </td> 
   <td colname="col8"> - </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Type d’accès</b> </td> 
   <td colname="col2"> Page </td> 
   <td colname="col3"> Lien </td> 
   <td colname="col4"> Page </td> 
   <td colname="col5"> Page </td> 
   <td colname="col6"> Page </td> 
   <td colname="col7"> Page </td> 
   <td colname="col8"> Page </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Nom de page</b> </td> 
   <td colname="col2"> Accueil </td> 
   <td colname="col3"> - </td> 
   <td colname="col4"> Produit </td> 
   <td colname="col5"> Accueil </td> 
   <td colname="col6"> Accueil <p>(recharge) </p> </td> 
   <td colname="col7"> Panier </td> 
   <td colname="col8"> Confirmation de commande </td> 
  </tr> 
 </tbody> 
</table>

### Exemple evar

<table id="table_6D0CF0C53DC145D3A53C06EC3012BCC0">  
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Accès de la visite </th> 
   <th colname="col2" class="entry"> 1 </th> 
   <th colname="col3" class="entry"> 2 </th> 
   <th colname="col4" class="entry"> 3 </th> 
   <th colname="col5" class="entry"> 4 </th> 
   <th colname="col6" class="entry"> 5 </th> 
   <th colname="col7" class="entry"> 6 </th> 
   <th colname="col8" class="entry"> 7 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>eVar1</b> </td> 
   <td colname="col2"> Rouge <p>(définie) </p> </td> 
   <td colname="col3"> Rouge <p>(persistante) </p> </td> 
   <td colname="col4"> (expirée) </td> 
   <td colname="col5"> Bleu <p>(définie) </p> </td> 
   <td colname="col6"> Bleu <p>(définie) </p> </td> 
   <td colname="col7"> Bleu <p>(persistante) </p> </td> 
   <td colname="col8"> Rouge <p>(définie) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>secondes écoulées eVar</b> </td> 
   <td colname="col2"> 30 </td> 
   <td colname="col3"> 50 </td> 
   <td colname="col4"> - </td> 
   <td colname="col5"> 10 </td> 
   <td colname="col6"> 40 </td> 
   <td colname="col7"> 60 </td> 
   <td colname="col8"> - </td> 
  </tr> 
 </tbody> 
</table>

### Exemple prop

<table id="table_1CB4D24A6CAA479C8E59A7C77FFB8226">  
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Accès de la visite </th> 
   <th colname="col2" class="entry"> 1 </th> 
   <th colname="col3" class="entry"> 2 </th> 
   <th colname="col4" class="entry"> 3 </th> 
   <th colname="col5" class="entry"> 4 </th> 
   <th colname="col6" class="entry"> 5 </th> 
   <th colname="col7" class="entry"> 6 </th> 
   <th colname="col8" class="entry"> 7 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>prop1</b> </td> 
   <td colname="col2"> A <p>(définie) </p> </td> 
   <td colname="col3"> A <p>(propagée) </p> </td> 
   <td colname="col4"> (non définie) </td> 
   <td colname="col5"> B <p>(définie) </p> </td> 
   <td colname="col6"> B <p>(définie) </p> </td> 
   <td colname="col7"> A <p>(définie) </p> </td> 
   <td colname="col8"> C <p>(définie) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>secondes écoulées prop1</b> </td> 
   <td colname="col2"> 30 </td> 
   <td colname="col3"> 50 </td> 
   <td colname="col4"> - </td> 
   <td colname="col5"> 10 </td> 
   <td colname="col6"> 40 </td> 
   <td colname="col7"> 60 </td> 
   <td colname="col8"> - </td> 
  </tr> 
 </tbody> 
</table>

Sur la base du tableau ci-dessus, les mesures de durée de la visite sont calculées comme suit :

| prop1 | Durée totale (secondes) | Durée de la visite | Durée par visiteur | Nombre de séquences | Durée moyenne de la visite du site |
|---|---|---|---|---|---|
| A | 30+50+60=140 | 140/1=140 | 140/1=140 | 2 | 140/2=70 |
| B | 10+40=50 | 50/1=50 | 50/1=50 | 1 | 50/1=50 |
| C | 0 | 0 | 0 | 0 | 0 |
| Durée non attribuée | 100 | - | - | - | - |

| eVar1 | Durée totale (secondes) | Durée de la visite | Durée par visiteur | Nombre de séquences | Durée moyenne de la visite du site |
|---|---|---|---|---|---|
| Rouge | 30+50=80 | 80/1=80 | 80/1=80 | 1 | 80/1=80 |
| Bleu | 10+40+60=110 | 110/1=110 | 110/1=110 | 1 | 110/1=110 |
| Durée non attribuée | 100 | - | - | - | - |

Pour les dimensions de durée de la visite, les lignes suivantes apparaîtront dans les rapports associés :

* Durée de la visite (granulaire) : 290
* Durée de consultation de la page (granulaire) : 10, 30, 40, 50, 60, 100

Quelques remarques supplémentaires à l’appui de l’exemple :

* Tous les calculs de durée de la visite sont basés sur le temps écoulé de la visite qui commence à zéro lors du premier accès de la visite.
* Les « secondes écoulées » correspondent à la différence entre l’horodatage de l’accès actuel et l’horodatage de l’accès suivant. En conséquence, le dernier accès de la visite (et rebonds) ne comporte pas de durée de la visite.
* Une « séquence » est un jeu consécutif d’accès pour lequel une variable donnée contient la même valeur (qu’elle soit définie, propagée ou persistante). Par exemple, prop1 « A » comporte deux séquences : accès 1 et 2 et accès 6. Les valeurs du dernier accès de la visite ne démarrent pas une nouvelle séquence car le dernier accès ne comporte pas de durée de la visite. La durée moyenne de la visite du site utilise des séquences du dénominateur.

   * Pour les besoins de la durée de la visite uniquement, les props sont « propagées » à partir des accès à la page vers les accès au lien suivant, comme indiqué ci-dessus pour prop1 sur l’accès 2. Cela permet à la valeur qui a été définie pour prop1 sur l’accès 1 (« A ») d’accumuler de la durée de visite sur l’accès 2.
   * Les eVars accumulent de la durée de visite sur n’importe quel accès pour lequel l’eVar est définie ou persistante. La persistance des eVars est définie par les paramètres d’eVar dans l’administration d’Analytics.
