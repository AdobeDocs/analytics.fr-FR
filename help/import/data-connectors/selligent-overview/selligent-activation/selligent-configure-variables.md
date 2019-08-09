---
description: Cette intégration requiert 2 evars à réserver pour chaque implémentation de suite de rapports.
seo-description: Cette intégration requiert 2 evars à réserver pour chaque implémentation de suite de rapports.
seo-title: Configuration des variables Analytics pour Selligent
solution: Analytics
title: Configuration des variables Analytics pour Selligent
uuid: 3 b 7 b 8 b 4 b -7614-4439-bcb 0-dbdec 5304844
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# Configuration des variables Analytics pour Selligent{#configure-analytics-variables-for-selligent}

Cette intégration requiert 2 evars à réserver pour chaque implémentation de suite de rapports.

Outre ces evars, certains événements peuvent être réservés en fonction des données de Selligent, que vous souhaitez voir dans Analytics. Ces evars et événements sont décrits ci-dessous :

<table id="table_2FFB865DBD80412F90DA8E224B12FB62"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Type de variable </th> 
   <th colname="col2" class="entry"> Nom de variable </th> 
   <th colname="col3" class="entry"> Mode d'utilisation </th> 
   <th colname="col4" class="entry"> Paramètres </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> eVar </td> 
   <td colname="col2"> ID de message </td> 
   <td colname="col3"> Capture de l'identification des campagnes de courriel individuel </td> 
   <td colname="col4"> <p><b>Etat</b>: Activé </p> <p><b>Affectation</b>: Le plus récent </p> <p><b>Expire après</b>: « Décision professionnelle » </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> eV ar </td> 
   <td colname="col2"> Recipient ID </td> 
   <td colname="col3"> Pour capturer l'identification anonyme de votre client qui a cliqué sur la campagne par courriel. </td> 
   <td colname="col4"> <p><b>Etat</b>: Activé </p> <p><b>Affectation</b>: Le plus récent </p> <p><b>Expire après</b>: « Décision professionnelle » </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Événement </td> 
   <td colname="col2"> Envoyé </td> 
   <td colname="col3"> Pour stocker le nombre de courriers électroniques envoyés par Selligent. </td> 
   <td colname="col4"> <p><b>Type</b>: Numérique </p> <p><b>Participation</b>: Activé </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Événement </td> 
   <td colname="col2"> Livré </td> 
   <td colname="col3"> Pour stocker le nombre de courriers électroniques remis. </td> 
   <td colname="col4"> <p><b>Type</b>: Numérique </p> <p><b>Participation</b>: Activé </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Événement </td> 
   <td colname="col2"> Vues </td> 
   <td colname="col3"> Pour stocker le nombre de courriers électroniques uniques affichés. </td> 
   <td colname="col4"> <p><b>Type</b>: Numérique </p> <p><b>Participation</b>: Activé </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Événement </td> 
   <td colname="col2"> Clics </td> 
   <td colname="col3"> Pour stocker le nombre de clics sur un courrier électronique. </td> 
   <td colname="col4"> <p><b>Type</b>: Numérique </p> <p><b>Participation</b>: Activé </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Événement </td> 
   <td colname="col2"> Rejeté </td> 
   <td colname="col3"> Pour stocker le nombre de courriers électroniques rejetés. </td> 
   <td colname="col4"> <p><b>Type</b>: Numérique </p> <p><b>Participation</b>: Activé </p> </td> 
  </tr> 
 </tbody> 
</table>

