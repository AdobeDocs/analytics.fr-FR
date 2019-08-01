---
description: Décrit les evars et les événements à réserver pour chaque implémentation de suite de rapports.
seo-description: Décrit les evars et les événements à réserver pour chaque implémentation de suite de rapports.
seo-title: Configuration des variables Adobe Analytics pour Lyris
solution: Analytics
title: Configuration des variables Adobe Analytics pour Lyris
uuid: 12 e 150 c 4-052 a -481 c -8 c 27-ef 45 ee 801977
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Configure Adobe Analytics variables for Lyris{#configure-adobe-analytics-variables-for-lyris}

Décrit les evars et les événements à réserver pour chaque implémentation de suite de rapports.

Cette intégration nécessite au moins 2 evars pour chaque implémentation de suite de rapports. Outre ces evars, certains événements peuvent être réservés selon les données Lyologiques que vous souhaitez voir dans Analytics. Ces evars et événements sont décrits dans le tableau ci-dessous :

<table id="table_43E32344E9E54FED8491F28047249329"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Type de variable </th> 
   <th colname="col2" class="entry"> Nom de variable </th> 
   <th colname="col3" class="entry"> Utilisation de la variable </th> 
   <th colname="col4" class="entry"> Paramètres </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> eVar </td> 
   <td colname="col2"> ID de message </td> 
   <td colname="col3"> Pour capturer l'identification des campagnes de courriel individuel </td> 
   <td colname="col4"> <p>Etat : Activé </p> <p>Affectation : Le plus récent </p> <p>Expire après : « Décision professionnelle » </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> eVar </td> 
   <td colname="col2"> Email Recipient ID </td> 
   <td colname="col3"> Pour capturer l'identification anonyme de votre client qui a cliqué sur la campagne par courriel </td> 
   <td colname="col4"> <p>Etat : Activé </p> <p>Affectation : Le plus récent </p> <p>Expire après : « Décision professionnelle » </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Événement </td> 
   <td colname="col2"> Lyris - Courriers électroniques envoyés </td> 
   <td colname="col3"> Pour stocker non. des courriers électroniques envoyés à partir de Lyris </td> 
   <td colname="col4">Type : Numérique <p>Participation : Activé </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Événement </td> 
   <td colname="col2"> Lyris - Emails ouverts </td> 
   <td colname="col3"> Pour stocker non. des courriers électroniques ouverts </td> 
   <td colname="col4">Type : Numérique <p>Participation : Activé </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Événement </td> 
   <td colname="col2"> Lyris - Courriers électroniques uniques ouverts </td> 
   <td colname="col3"> Pour stocker non. des courriers électroniques uniques ouverts </td> 
   <td colname="col4">Type : Numérique <p>Participation : Activé </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Événement </td> 
   <td colname="col2"> Lyris - Clics publicitaires par courriel </td> 
   <td colname="col3"> Pour stocker non. des fois où un clic a été activé sur un courrier électronique </td> 
   <td colname="col4">Type : Numérique <p>Participation : Activé </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Événement </td> 
   <td colname="col2"> Lyris - Rebonds par courriel </td> 
   <td colname="col3"> Pour stocker le non. des courriers électroniques qui ont été rejetés </td> 
   <td colname="col4">Type : Numérique <p>Participation : Activé </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Événement </td> 
   <td colname="col2"> Lyris - Courriel désabonné </td> 
   <td colname="col3"> Pour stocker le non. des abonnements par courrier électronique désactivés </td> 
   <td colname="col4">Type : Numérique <p>Participation : Activé </p> </td> 
  </tr> 
 </tbody> 
</table>

