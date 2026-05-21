---
description: Certaines mesures des visiteurs d’Adobe Analytics et d’Adobe Audience Manager ont des définitions similaires mais ne correspondent pas exactement, pour diverses raisons.
title: Différences entre les nombres de visiteurs
feature: Audience Analytics
exl-id: be5a935a-c3a2-4ab4-8cd7-ed54a37932c8
TQID: https://experienceleague.adobe.com/ksfYYDZ6G9vH7WEZVh-JsN93Rl-jsZTe9-CQADSwnfI
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 312
ht-degree: 44%

---

# Différences entre les nombres de visiteurs

Certaines mesures des visiteurs d’Adobe Analytics et d’Adobe Audience Manager ont des définitions similaires mais ne correspondent pas exactement, pour diverses raisons.

Les mesures du visiteur sont les suivantes :

<table id="table_F9FE107A89934C3B854C55D7D76AC6E8"> 
 <thead> 
  <tr> 
   <th colname="col2" class="entry"> Mesure </th> 
   <th colname="col3" class="entry"> Définition </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col2"> <p><a href="https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/segments/segment-builder-data.html?lang=fr"  > Adobe Audience Manager : population totale de segments</a> </p> </td> 
   <td colname="col3"> <p>Nombre d’appareils (Experience Cloud ID) qui étaient membres de votre segment pendant la période de recherche en amont. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><a href="https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/segments/segment-builder-data.html?lang=fr"  > Adobe Audience Manager : population de segments en temps réel</a> </p> </td> 
   <td colname="col3"> <p>Nombre d’appareils (Experience Cloud ID) qui étaient membres de votre segment et qui ont atteint vos propriétés pendant la période de recherche en amont. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Analytics : visiteurs uniques </p> </td> 
   <td colname="col3"> <p>Affiche le nombre de visiteurs uniques ayant atteint vos propriétés pendant la période de rapport. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Analytics : visiteurs avec Experience Cloud ID </p> </td> 
   <td colname="col3"> <p>Affiche le nombre de visiteurs uniques avec un Experience Cloud ID qui ont atteint vos propriétés pendant la période de création de rapports. </p> </td> 
  </tr> 
 </tbody> 
</table>

La population de segments en temps réel de Adobe Audience Manager et les visiteurs Analytics avec l’Experience Cloud ID utilisé dans les rapports Audience Analytics seront les plus similaires. Toutefois, à court terme, il y aura de légères divergences entre eux en raison de plusieurs facteurs. Les facteurs contributifs sont les suivants :

<table id="table_A391B37CC077456F8BB83BAA3C640EF6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Facteur </th> 
   <th colname="col2" class="entry"> Adobe Audience Manager : population de segments en temps réel </th> 
   <th colname="col3" class="entry"> Analytics : visiteurs avec Experience Cloud ID </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Fuseau horaire </p> </td> 
   <td colname="col2"> <p>UTC (temps universel coordonné) </p> </td> 
   <td colname="col3"> <p>Spécifié par suite de rapports </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Filtres personnalisés </p> </td> 
   <td colname="col2"> <p>Non </p> </td> 
   <td colname="col3"> <p>Oui, par exemple filtres IP, filtres de robots </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Limite de 150 segments </p> </td> 
   <td colname="col2"> <p>Non </p> </td> 
   <td colname="col3"> <p>Oui - Le nombre d’analyses peut être affecté jusqu’à 5 % par la limite d’intégration de 150 segments. « Limite d’audience atteinte » apparaîtra dans la dimension Nom d’audience en cas de troncation. </p> </td> 
  </tr> 
 </tbody> 
</table>

Reportez-vous à la section [Présentation des segments dans Analytics et Audience Manager](/help/integrate/c-audience-analytics/aam-analytics-segments.md) pour plus d’informations sur les nuances entre les données et la segmentation dans Analytics et Audience Manager.
