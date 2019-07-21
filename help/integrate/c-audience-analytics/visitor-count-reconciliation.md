---
description: Certaines mesures des visiteurs d’Adobe Analytics et d’Adobe Audience Manager ont des définitions similaires mais ne correspondent pas exactement, pour diverses raisons.
seo-description: Certaines mesures des visiteurs d’Adobe Analytics et d’Adobe Audience Manager ont des définitions similaires mais ne correspondent pas exactement, pour diverses raisons.
seo-title: Différences de nombre de visiteurs
title: Différences de nombre de visiteurs
uuid: c 3 bbb 887-bd 02-4 c 1 c -9 a 2 b -64811 c 0 ef 56 a
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Différences de nombre de visiteurs

Certaines mesures des visiteurs d’Adobe Analytics et d’Adobe Audience Manager ont des définitions similaires mais ne correspondent pas exactement, pour diverses raisons.

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
   <td colname="col2"> <p><a href="https://marketing.adobe.com/resources/help/en_US/aam/segment-builder-data.html" format="html" scope="external"> AAM : Population totale du segment</a> </p> </td> 
   <td colname="col3"> <p>Nombre de périphériques (Experience Cloud ID) qui étaient membres de votre segment pendant la période de recherche en amont. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><a href="https://marketing.adobe.com/resources/help/en_US/aam/segment-builder-data.html" format="html" scope="external"> AAM : Population des segments en temps réel</a> </p> </td> 
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

Les mesures Population des segments en temps réel d’AAM et Visiteurs avec un Experience Cloud ID d’Analytics utilisées pour la création de rapports Audience Analytics seront les plus semblables. À court terme cependant, elles présenteront de légères différences en raison de plusieurs facteurs, à savoir :

<table id="table_A391B37CC077456F8BB83BAA3C640EF6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Facteur </th> 
   <th colname="col2" class="entry"> AAM : Population des segments en temps réel </th> 
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

Voir [Présentation des segments dans Analytics et Audience Manager](../../integrate/c-audience-analytics/aam-analytics-segments.md#concept_AB72F76AFAF14F82A5BB17809925813B) pour une explication supplémentaire sur les nuances entre les données et la segmentation dans Analytics et Audience Manager.
