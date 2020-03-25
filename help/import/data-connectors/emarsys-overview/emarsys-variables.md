---
description: L’intégration des Data Connectors pour emarsys effectue le suivi des résultats de mesure à l’aide des variables Analytics.
title: Variables Analytics
uuid: 4d5e087c-f495-4aab-9ad1-9b901d34a254
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Variables Analytics {#analytics-variables}

L’intégration des Data Connectors pour emarsys effectue le suivi des résultats de mesure à l’aide des variables Analytics.

Après avoir identifié l’événement et les eVars à utiliser avec l’intégration d’emarsys, activez-les dans [Admin Console](https://docs.adobe.com/content/help/fr-FR/analytics/admin/admin-tools/c-admin-tools.html).

**Variables obligatoires**

<table id="table_5B8F3A1EB55D4BB48F669FB84C857256"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Type de variable </th> 
   <th colname="col2" class="entry"> Nom </th> 
   <th colname="col3" class="entry"> Méthode de remplissage </th> 
   <th colname="col4" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Événement (numérique) </td> 
   <td colname="col2"> Rebonds au total </td> 
   <td colname="col3"> <p>Importation automatique depuis emarsys </p> </td> 
   <td colname="col4"> <p>L’événement Rebonds au total vous permet d’afficher le nombre de messages électroniques qui n’ont pas été remis aux destinataires en raison d’un problème de livraison. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Événement (numérique) </td> 
   <td colname="col2"> Cliqué </td> 
   <td colname="col3"> <p>Importation automatique depuis emarsys </p> </td> 
   <td colname="col4"> <p>L’événement Cliqué vous permet d’afficher le nombre de visiteurs qui ont cliqué sur le message électronique. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Événement (numérique) </td> 
   <td colname="col2"> Ouvert </td> 
   <td colname="col3"> <p>Importation automatique depuis emarsys </p> </td> 
   <td colname="col4"> <p>L’événement Ouvert vous permet d’afficher le nombre de visiteurs qui ont ouvert le message électronique. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Événement (numérique) </td> 
   <td colname="col2"> Envoyé </td> 
   <td colname="col3"> <p>Importation automatique depuis emarsys </p> </td> 
   <td colname="col4"> <p>L’événement Envoyé vous permet d’afficher le nombre de messages électroniques envoyés. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Événement (numérique) </td> 
   <td colname="col2"> Désabonné </td> 
   <td colname="col3"> <p>Importation automatique depuis emarsys </p> </td> 
   <td colname="col4"> <p>L’événement Désabonné vous permet d’afficher le nombre de visiteurs qui ont ouvert le message électronique, mais qui ont cliqué sur le lien Se désabonner pour ne plus recevoir à l’avenir de messages électroniques de votre organisation. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> eVar </td> 
   <td colname="col2"> Recipient ID </td> 
   <td colname="col3"> <p>Collecté à partir des paramètres de requête dans les liens de courrier électronique par le biais de la méthode de collecte automatisée ou d’un plug-in JavaScript. </p> </td> 
   <td colname="col4"> Recipient ID </td> 
  </tr> 
  <tr> 
   <td colname="col1"> eVar or s.campaign </td> 
   <td colname="col2"> ID de message </td> 
   <td colname="col3"> <p>Collecté à partir des paramètres de requête dans les liens de courrier électronique par le biais de la méthode de collecte automatisée ou d’un plug-in JavaScript. </p> </td> 
   <td colname="col4"> Cette valeur est souvent stockée dans la variable de campagne. </td> 
  </tr> 
 </tbody> 
</table>

