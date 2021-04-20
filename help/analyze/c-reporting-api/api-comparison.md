---
description: Tableau de comparaison des API de création de rapports dans Analytics. Vous y trouverez également des liens vers la documentation afférente.
title: Comparaison des API de création de rapports dans Analytics
uuid: fa533a8e-33c0-42f4-a294-cabee0258c8f
feature: API
role: Developer
translation-type: tm+mt
source-git-commit: 4359f451692b86087efe27d4b3ec49ca85b7addc
workflow-type: tm+mt
source-wordcount: '284'
ht-degree: 100%

---


# Comparaison des API de création de rapports dans Analytics

Tableau de comparaison des API de création de rapports dans Analytics. Vous y trouverez également des liens vers la documentation afférente.

>[!NOTE]
>
>À propos de la latence, Analytics pour Target (A4T) combine sur le même accès les données d’Analytics et de Target pour les rapports intégrés. Les appels à Analytics et à Target pouvant survenir à différents moments, les accès sont stockés avant tout traitement de collecte des données dans les deux solutions. Pour cette raison, le temps de latence de tous les points de contrôle est de **7 à 10 minutes** plus long.

<table id="table_7AF4FD678D494063ADF459B3CBC3EF3F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Type d’API </th> 
   <th colname="col2" class="entry"> Traitement complet </th> 
   <th colname="col3" class="entry"> Temps réel </th> 
   <th colname="col4" class="entry"> Livestream </th> 
   <th colname="col5" class="entry"> Data Warehouse </th> 
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
   <td colname="col1"> <p><a href="https://docs.adobe.com/content/help/fr-FR/analytics/technotes/latency.html"  > Latence</a> </p> </td> 
   <td colname="col2"> 30 à 90 minutes </td> 
   <td colname="col3"> * Secondes -10 minutes </td> 
   <td colname="col4"> Secondes -10 minutes </td> 
   <td colname="col5"> 90 minutes + </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Traitement</b> </td> 
   <td colname="col2"> Complet </td> 
   <td colname="col3"> Partiel </td> 
   <td colname="col4"> Partiel </td> 
   <td colname="col5"> Complet </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <a href="https://docs.adobe.com/content/help/fr-FR/analytics/landing/home.html"  > Interfaces de création de rapports</a> </td> 
   <td colname="col2"> Analysis Workspace, Reports &amp; Analytics, Report Builder, API </td> 
   <td colname="col3"> Rapport en temps réel dans Reports &amp; Analytics, Report Builder et l’API 1.4 </td> 
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
   <td colname="col1"> <b>Documentation</b> </td> 
   <td colname="col2"> <p> <a href="https://www.adobe.io/apis/experiencecloud/analytics/docs.html"  > API Analytics</a> </p> </td> 
   <td colname="col3"> <p> <a href="https://github.com/AdobeDocs/analytics-1.4-apis"  > Rapports Temps réel</a> </p> </td> 
   <td colname="col4"> <p> <a href="https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/live-stream-api/getting_started.md"  > Aperçu de Livestream</a> </p> </td> 
   <td colname="col5"> <p><a href="https://docs.adobe.com/content/help/fr-FR/analytics/export/data-warehouse/data-warehouse.html"  > Data Warehouse</a> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Aide connexe**

* [Adobe I/O](https://www.adobe.io/) - Source exhaustive de documentation technique et d’outils nécessaires pour intégrer les technologies Adobe à vos applications.
* [API de requête des Data Workbench](https://marketing.adobe.com/developer/documentation/data-workbench-query-api/c-ins-qry-api)

