---
description: Affiche le nombre de visites effectuées sur l’ensemble de votre site web au cours d’une période spécifiée.
title: Visites
topic: Reports
uuid: ff65bddf-fb65-4cf0-8aae-4ab59c2bb0a7
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Visites

Affiche le nombre de visites effectuées sur l’ensemble de votre site web au cours d’une période spécifiée.

**Propriétés des rapports**

* Une visite est définie comme une séquence de pages vues consécutives sans pause de 30 minutes ou avec une activité continue de 12 heures.
* À l’expiration d’une visite, une nouvelle visite est lancée sur toute demande d’image suivante.
* En règle générale, un visiteur contient au moins une visite (et probablement plusieurs).
* Une visite débute par la première demande d’image en provenance d’un nouveau visiteur ou l’expiration de la visite d’un utilisateur existant. Cela peut être identifié comme étant la page d’entrée.
* La fin d’une visite est la dernière demande d’image avant l’expiration d’une visite. Cela peut être identifié comme étant la page de sortie.

   Voir [Rapports Entrées et Sorties](/help/components/c-variables/dimensionslist/reports-entries-exits.md).
* Les ventilations horaires sont basées sur le fuseau horaire de la suite de rapports.
* Ce rapport ne contient pas d’éléments. Il ne peut être visualisé qu’au format « tendance ».
* Vous pouvez appliquer une granularité horaire, quotidienne, hebdomadaire, mensuelle, trimestrielle et annuelle. Ces paramètres de granularité sont disponibles en fonction de la plage de dates des rapports.

Voir [Mesure Visite](/help/components/c-variables/c-metrics/metrics-visit.md) pour plus d’informations sur la manière dont Experience Cloud traite cette mesure.

**Informations sur les rapports propres au produit**

<table id="table_3138CA443CAC4F55838216E8B8786EE2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Produit </th> 
   <th colname="col2" class="entry"> Navigation </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> Reports &amp; Analytics </p> </td> 
   <td colname="col2"> <p> <span class="uicontrol"> Mesures du site</span> &gt; <span class="uicontrol">Visites</span> </p> <p>Vous pouvez exécuter un rapport <span class="wintitle">Visites</span> sur une page sélectionnée. Les visites qui s’étendent au-delà de minuit sont comptabilisées le jour où elles commencent et celui où elles se terminent. Cependant, le total de la période donnée est dédupliqué. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Ad Hoc Analysis </p> </td> 
   <td colname="col2"> <p> <span class="uicontrol"> Rapports</span> &gt; <span class="uicontrol">Mesures du site</span> &gt; <span class="uicontrol">Visites</span> </p> 
    <ul id="ul_73FEE02C129041D6A63F2DB07676960F"> 
     <li id="li_CC3BB22DE97941EB8032BE4421FFC173"> Vous pouvez ventiler chaque élément du rapport selon pratiquement tous les autres rapports et variables, ce qui vous permet de visualiser les ventilations selon n’importe quelle granularité. </li> 
     <li id="li_D53D480D73264D47945C9E1202B7BD4F">Les visites qui s’étendent au-delà de minuit sont comptabilisées le jour où elles commencent et celui où elles se terminent. Cependant, le total de la période donnée est dédupliqué. </li> 
     <li id="li_B8BCC584F95B407DB87F5EA57CC88F62">Vous pouvez utiliser toutes les mesures de trafic et de conversion de ce rapport, ainsi qu’une allocation différente pour toutes les mesures de conversion. </li> 
     <li id="li_0F342D3DCFF44ABAB79BD0F9E7F43E1E">Ce rapport peut utiliser plusieurs segments très avancés. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

