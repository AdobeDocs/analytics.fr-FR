---
description: valeur nulle
seo-description: valeur nulle
seo-title: FAQ sur l’Attribution IQ
title: FAQ sur l’Attribution IQ
uuid: 90961172-869 d -4 ed 3-aba 5-52374 e 53 b 603
translation-type: tm+mt
source-git-commit: ab2cda6d10bfeee13262581578bcdb4746112296

---


# FAQ sur l’Attribution IQ

<table id="table_590341C2F0DA4511ADEFDC1DB49CD248"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Question </th> 
   <th colname="col2" class="entry"> Réponse </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Q : Pourquoi l’attribut « aucun » a-t-il une plus grande importance que prévu lorsque j’utilise les nouveaux modèles d’attribution ?</b> </p> </td> 
   <td colname="col2"> <p>R : Ceci est probablement dû au créneau de rapport sélectionné, comme décrit <a href="../../../analyze/analysis-workspace/attribution-iq/attribution.md#section_BC71DA030E45487AA3C3F6ED247A3C4A" format="dita" scope="local">ici </a>. Ceci se produit généralement quand le créneau de rapport commence le premier jour du mois et que vous utilisez un intervalle (créneau de rapport) Visiteur. Afin de capturer d’autres intervalles d’attribution (et de réduire l’attribut « aucun »), incluez une période plus longue dans le créneau de rapport. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q : Je vois parfois des dates en dehors de mon créneau de rapport apparaître dans mon rapport lorsque j’utilise des modèles d’attribution. Pourquoi ?</b> </p> </td> 
   <td colname="col2"> <p>R : Ces dates supplémentaires sont un attribut de l’intervalle de recherche en amont du compte rendu des performances des visiteurs décrit <a href="../../../analyze/analysis-workspace/attribution-iq/attribution.md" format="dita" scope="local">ici </a>. L’article <a href="https://helpx.adobe.com/analytics/kb/data-appearing-outside-reporting-window.html" format="html" scope="external">Données apparaissant hors du créneau de rapport</a> explique pourquoi cela survient actuellement. Adobe Analytics filtrera ces rangées supplémentaires dans une prochaine version. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q : Puis-je utiliser un intervalle de recherche en amont personnalisé avec mes modèles d’attribution ?</b> </p> </td> 
   <td colname="col2"> <p>A: Currently, attribution models rely on either a visitor or visit lookback window - but either of these lookback windows are adjustable by either changing the reporting date range (for visitor lookback) or by using a custom visit definition as part of Virtual Report Suites and <a href="https://marketing.adobe.com/resources/help/en_US/reference/vrs-mobile-visit-processing.html" format="html" scope="external"> Context-Aware Sessions </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q : Quand dois-je utiliser une recherche en amont de l’attribution des « visites » par rapport à celle des « visiteurs » ?</b> </p> </td> 
   <td colname="col2"> <p>R : Le choix d’une recherche en amont de l’attribution dépend vraiment de votre cas d’utilisation. Si votre conversion a généralement un cycle de traitement plus long (ce qui prend plus de temps qu’une seule visite), nous vous recommandons d’utiliser une recherche en amont des visiteurs ou de créer une suite de rapports virtuelle avec une visite plus longue qui reflète plus précisément ce cycle de traitement. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q : Les modèles d’attribution sont-ils disponibles dans les flux de données ou dans le Data Warehouse ?</b> </p> </td> 
   <td colname="col2"> <p>R : Non. Comme les modèles d’attribution sont calculés à la période de rapport à l’aide du <a href="https://marketing.adobe.com/resources/help/en_US/reference/vrs-report-time-processing.html" format="html" scope="external">traitement de la période de rapport</a>, il n’est pas possible de les faire figurer dans les flux de données ou le Data Warehouse. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q : Les modèles d’attribution ne sont-ils disponibles que si j’utilise une suite de rapports virtuelle avec le traitement de la période de rapport activé ?</b> </p> </td> 
   <td colname="col2"> <p>R : Non, bien que les modèles d’attribution tirent parti du <a href="https://marketing.adobe.com/resources/help/en_US/reference/vrs-report-time-processing.html" format="html" scope="external">traitement de la période de rapport</a> sur le serveur principal, nous les avons rendus disponibles pour les suites de rapports virtuelles et les suites de rapports de base à des fins pratiques. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q : L’Attribution IQ dans Analysis Workspace prend-elle en charge un modèle d’attribution axé sur les données ou algorithmique ?</b> </p> </td> 
   <td colname="col2"> <p>R : Cette option n’est pas encore disponible dans Analysis Workspace, mais nous y travaillons activement. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q : Y a-t-il des dimensions ou des mesures qui ne sont pas prises en charge par l’Attribution IQ ?</b> </p> </td> 
   <td colname="col2"> <p>A : L'attribution IQ est prise en charge sur toutes les dimensions.</p> 
    <p>Les mesures qui <u>ne sont pas</u> prises en charge (principalement car elles n’auraient pas de sens) sont les suivantes : </p> 
    <ul id="ul_B12A1291DEEF41FDBAD110C4A9265234"> 
     <li id="li_245571C5377C45ADBAE6F735B91FCD1F"> Visiteurs uniques </li> 
     <li id="li_000CA7680A0745D9860CA7D5F62288D4">Visites </li> 
     <li id="li_53CAD3ECAE54451BBB0750FB62AF1243">Occurrences </li> 
     <li id="li_C589008CA92E4C69866E85EEEC88EF90"> Pages vues </li> 
     <li id="li_ACF8D24E3AC746E280DB0F71D4B772A3">Mesures d’A4T </li> 
     <li id="li_78BFE0A4F8024301A218C0415537F632">Mesures de durée de la visite </li> 
     <li id="li_29774EEFE9A04759B7929EA35AA9BEAD">Rebonds </li> 
     <li id="li_B163C6F24240465F85AB5C9792F0F013">Taux de rebond </li> 
     <li id="li_CF065E227A634C77BC2C48C2A6EC849A">Entrées </li> 
     <li id="li_ED962C5063B047F185EFC58EB43C661F">Sorties </li> 
     <li id="li_029F6D09433F48A38303E5C96E77480B">Pages introuvables </li> 
     <li id="li_8410AF29208247B5B3E49F72208913BA">Recherches </li> 
     <li id="li_8421F1D5F58148D98B1AB5C04FCCA9CF">Visites sur une seule page </li> 
     <li id="li_50D4EA0FF2E6438C8DD2A1B2EAD7B9D7">Accès unique </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q : En quoi l’Attribution IQ diffère-t-elle de l’attribution dans Data Workbench ?</b> </p> </td> 
   <td colname="col2"> <p>R : Data Workbench offre progressivement : </p> 
    <ul id="ul_5A8C979CDCD04FF5B9625C84B2678CC7"> 
     <li id="li_115DC58D4BDF40A4A0036E76F6E64158">la possibilité d’attribuer plus de sources de données au niveau des visiteurs, comme les impressions publicitaires et les points de vente ; </li> 
     <li id="li_C31891A4D5594D93AF97340F6D3A2E3E">la modélisation (<a href="https://marketing.adobe.com/resources/help/en_US/insight/client/c_attrib_algorithmic.html" format="html" scope="external">mieux adaptée</a>) algorithmique. L’Attribution IQ ne comprend que des modèles basés sur des règles ; </li> 
     <li id="li_749D5D11B34E40E9AB53908A38979CAA">des visualisations supplémentaires, telles que les <a href="https://marketing.adobe.com/resources/help/en_US/insight/client/c_lat_tbls.html" format="html" scope="external">tables de latence </a>. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q : Attribution IQ fonctionne-t-il avec les sources de données ?</b> </p> </td> 
   <td colname="col2"> <p>R : Actuellement, Attribution IQ fonctionne avec les sources de données autres que les sources de données récapitulatives. </p> <p> Ces sources de données récapitulatives n’étant pas liées à un identifiant visiteur Analytics, aucun attribution avancée n’est possible. Les sources de données ID de transaction sont également prises en charge, sauf si elles sont utilisées dans une suite de rapports virtuelle où le <a href="https://marketing.adobe.com/resources/help/en_US/reference/vrs-report-time-processing.html" format="html" scope="external">traitement du temps</a> est activé. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q : Attribution IQ fonctionne-t-il avec l’intégration d’<a href="https://marketing.adobe.com/resources/help/en_US/analytics/advertising/overview.html" format="html" scope="external">Advertising Analytics</a> ?</b> </p> </td> 
   <td colname="col2"> <p>R : Les mesures intégrées (impressions, coût, clics, position moyenne et note de qualité moyenne) sont des sources de données récapitulatives et sont donc incompatibles avec Attribution IQ. Toutefois, les dimensions de métadonnées (tels le type de correspondance et le mot-clé) fonctionneront avec l’attribution si celle-ci est utilisée avec des événements ou des mesures Analytics standard. </p> </td> 
  </tr> 
 </tbody> 
</table>

