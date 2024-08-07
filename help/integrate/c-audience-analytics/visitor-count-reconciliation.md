---
description: Certaines mesures des visiteurs d’Adobe Analytics et d’Adobe Audience Manager ont des définitions similaires mais ne correspondent pas exactement, pour diverses raisons.
title: Différences entre les nombres de visiteurs
feature: Audience Analytics
exl-id: be5a935a-c3a2-4ab4-8cd7-ed54a37932c8
source-git-commit: 15f1cd260709c2ab82d56a545494c31ad86d0ab0
workflow-type: tm+mt
source-wordcount: '285'
ht-degree: 85%

---

# Différences entre les nombres de visiteurs

Certaines mesures des visiteurs d’Adobe Analytics et d’Adobe Audience Manager ont des définitions similaires mais ne correspondent pas exactement, pour diverses raisons.

Les mesures des visiteurs sont :

<table id="table_F9FE107A89934C3B854C55D7D76AC6E8"> 
 <thead> 
  <tr> 
   <th colname="col2" class="entry"> Mesure </th> 
   <th colname="col3" class="entry"> Définition </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col2"> <p><a href="https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/segments/segment-builder-data.html?lang=fr"  > Adobe Audience Manager : Population totale du segment</a> </p> </td> 
   <td colname="col3"> <p>Nombre d’appareils (Experience Cloud ID) qui étaient membres de votre segment pendant la période de recherche en amont. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><a href="https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/segments/segment-builder-data.html?lang=fr"  > Adobe Audience Manager : population de segments en temps réel </a> </p> </td> 
   <td colname="col3"> <p>Nombre de périphériques (Experience Cloud ID) qui étaient membres de votre segment et ont atteint vos propriétés pendant la période de recherche en amont. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Analytics : Visiteurs uniques </p> </td> 
   <td colname="col3"> <p>Indique le nombre de visiteurs uniques qui ont atteint vos propriétés pendant la fenêtre de rapport. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Analytics : Visiteurs avec un Experience Cloud ID </p> </td> 
   <td colname="col3"> <p>Indique le nombre de visiteurs uniques avec un Experience Cloud ID qui ont atteint vos propriétés pendant la fenêtre de rapport. </p> </td> 
  </tr> 
 </tbody> 
</table>

La population des segments en temps réel de Adobe Audience Manager et les visiteurs Analytics avec un ID d’Experience Cloud utilisé dans les rapports d’Audience Analytics seront les plus similaires. À court terme cependant, elles présenteront de légères différences en raison de plusieurs facteurs, à savoir :

<table id="table_A391B37CC077456F8BB83BAA3C640EF6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Facteur </th> 
   <th colname="col2" class="entry"> Adobe Audience Manager : population de segments en temps réel </th> 
   <th colname="col3" class="entry"> Analytics : Visiteurs avec un Experience Cloud ID </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Fuseau horaire </p> </td> 
   <td colname="col2"> <p>UTC (Temps universel coordonné) </p> </td> 
   <td colname="col3"> <p>Spécifié selon la suite de rapports </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Filtres personnalisés </p> </td> 
   <td colname="col2"> <p>Non </p> </td> 
   <td colname="col3"> <p>Oui, p. ex. filtres d’adresses IP, filtres de robots </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Limite de 150 segments </p> </td> 
   <td colname="col2"> <p>Non </p> </td> 
   <td colname="col3"> <p>Oui. Les mesures Analytics peuvent être affectées de 5 % maximum par la limite d’intégration de 150 segments. « Limite d’audience atteinte » apparaîtra dans la dimension Nom d’audience en cas de troncation. </p> </td> 
  </tr> 
 </tbody> 
</table>

Reportez-vous à la section [Présentation des segments dans Analytics et Audience Manager](/help/integrate/c-audience-analytics/aam-analytics-segments.md) pour plus d’informations sur les nuances entre les données et la segmentation dans Analytics et Audience Manager.
