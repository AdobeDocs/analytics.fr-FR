---
description: Tableau de comparaison des API de création de rapports dans Analytics. Vous y trouverez également des liens vers la documentation afférente.
title: Comparaison des API de création de rapports dans Analytics
uuid: fa533a8e-33c0-42f4-a294-cabee0258c8f
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Comparaison des API de création de rapports dans Analytics

Tableau de comparaison des API de création de rapports dans Analytics. Vous y trouverez également des liens vers la documentation afférente.

> [!NOTE] En ce qui concerne la latence, Analytics pour Target (A4T) combine les données Analytics et Target sur le même accès pour la création de rapports intégrée. Les appels à Analytics et à Target pouvant survenir à différents moments, les accès sont stockés avant tout traitement de collecte des données dans les deux solutions. Pour cette raison, le temps de latence de tous les points de contrôle est de **7 à 10 minutes** plus long.

<table id="table_7AF4FD678D494063ADF459B3CBC3EF3F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Type d’API </th> 
   <th colname="col2" class="entry"> Traitement complet </th> 
   <th colname="col3" class="entry"> Temps réel </th> 
   <th colname="col4" class="entry"> Livestream </th> 
   <th colname="col5" class="entry"> Data Warehouse </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Description</b> </td> 
   <td colname="col2"> Données finalisées intégralement traitées disponibles dans toutes les interfaces d’Analytics. </td> 
   <td colname="col3"> Mesures limitées partiellement traitées disponibles quelques secondes après la collecte. </td> 
   <td colname="col4"> Données d’accès partiellement traitées disponibles quelques secondes après la collecte. </td> 
   <td colname="col5"> Données finalisées entièrement traitées utilisées pour l’extraction d’exportations volumineuses de données. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><a href="https://marketing.adobe.com/resources/help/en_US/analytics/whitepapers/analytics-data-availability.pdf"  > Latence</a> </p> </td> 
   <td colname="col2"> 30 à 90 minutes </td> 
   <td colname="col3"> * Secondes -10 minutes </td> 
   <td colname="col4"> Secondes -10 minutes </td> 
   <td colname="col5"> 90 minutes et + </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Traitement</b> </td> 
   <td colname="col2"> Complet </td> 
   <td colname="col3"> Partiel </td> 
   <td colname="col4"> Partiel </td> 
   <td colname="col5"> Complet </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <a href="https://marketing.adobe.com/resources/help/en_US/reference/"  > Interfaces de création de rapports</a> </td> 
   <td colname="col2"> Reports &amp; Analytics, Report Builder, API </td> 
   <td colname="col3"> Rapport en temps réel dans les Reports &amp; Analytics, le Report Builder, l’API </td> 
   <td colname="col4"> API seulement </td> 
   <td colname="col5"> Data Warehouse et API </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Granularité des données</b> </td> 
   <td colname="col2"> Récapitulatif </td> 
   <td colname="col3"> Récapitulatif </td> 
   <td colname="col4"> Au niveau des accès </td> 
   <td colname="col5"> Récapitulatif </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Traitement du profil du visiteur</b> </td> 
   <td colname="col2"> Oui </td> 
   <td colname="col3"> Non </td> 
   <td colname="col4"> Non </td> 
   <td colname="col5"> Oui </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Prise en charge des segments</b> </td> 
   <td colname="col2"> Oui </td> 
   <td colname="col3"> Non </td> 
   <td colname="col4"> Non </td> 
   <td colname="col5"> Oui (mais seulement les segments compatibles avec Data Warehouse) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Analytics SKU</b> </td> 
   <td colname="col2"> Standard+ </td> 
   <td colname="col3"> Standard+ </td> 
   <td colname="col4"> Premium Complete ou Predictive Intelligence </td> 
   <td colname="col5"> Standard+ </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Documentation</b> </td> 
   <td colname="col2"> <p> <a href="https://marketing.adobe.com/developer/documentation/analytics-reporting-1-4/get-started%E2%80%8B"  > Services web</a> </p> </td> 
   <td colname="col3"> <p> <a href="https://marketing.adobe.com/developer/documentation/analytics-reporting-1-4/real-time"  > Rapports Temps réel</a> </p> </td> 
   <td colname="col4"> <p> <a href="https://marketing.adobe.com/developer/documentation/analytics-live-stream/overview-1%E2%80%8B"  > Aperçu de Livestream</a> </p> </td> 
   <td colname="col5"> <p><a href="https://marketing.adobe.com/resources/help/en_US/reference/data_warehouse.html"  > Data Warehouse</a> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Aide connexe**

* [Adobe/IO](https://www.adobe.io/) - Source exhaustive de documentation technique et d’outils nécessaires pour intégrer les technologies Adobe à vos applications.
* [API de requête des Data Workbench](https://marketing.adobe.com/developer/documentation/data-workbench-query-api/c-ins-qry-api)

