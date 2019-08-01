---
description: L'intégration des Connecteurs de données pour emarsys utilise les variables Analytics pour effectuer le suivi de diverses mesures emarsys.
seo-description: L'intégration des Connecteurs de données pour emarsys utilise les variables Analytics pour effectuer le suivi de diverses mesures emarsys.
seo-title: Variables Analytics
title: Variables Analytics
uuid: 4 d 5 e 087 c-f 495-4 aab -9 ad 1-9 b 901 d 34 a 254
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Variables Analytics{#analytics-variables}

L'intégration des Connecteurs de données pour emarsys utilise les variables Analytics pour effectuer le suivi de diverses mesures emarsys.

After identifying the Event and eVars to use with the emarsys integration, enable them in the [Admin Console](https://microsite.omniture.com/t2/help/en_US/reference/index.html?f=conversion_var_admin).

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
   <td colname="col1"> événement (numérique) </td> 
   <td colname="col2"> Nombre total de rebonds </td> 
   <td colname="col3"> <p>Automatiquement importé à partir de emarsys </p> </td> 
   <td colname="col4"> <p>L'événement Total rebonds vous permet de voir le nombre de messages électroniques qui n'ont pas été remis aux destinataires en raison d'un problème de remise. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> événement (numérique) </td> 
   <td colname="col2"> Cliqué </td> 
   <td colname="col3"> <p>Automatiquement importé à partir de emarsys </p> </td> 
   <td colname="col4"> <p>L'événement Clicked vous permet de voir le nombre de visiteurs qui ont cliqué sur le courriel. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> événement (numérique) </td> 
   <td colname="col2"> Ouvert </td> 
   <td colname="col3"> <p>Automatiquement importé à partir de emarsys </p> </td> 
   <td colname="col4"> <p>L'événement Ouvert vous permet de voir le nombre de visiteurs qui ont ouvert le courriel. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> événement (numérique) </td> 
   <td colname="col2"> Envoyé </td> 
   <td colname="col3"> <p>Automatiquement importé à partir de emarsys </p> </td> 
   <td colname="col4"> <p>L'événement Envoyer vous permet de voir le nombre de courriers électroniques envoyés. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> événement (numérique) </td> 
   <td colname="col2"> Désabonné </td> 
   <td colname="col3"> <p>Automatiquement importé à partir de emarsys </p> </td> 
   <td colname="col4"> <p>L'événement Non abonné vous permet de voir le nombre de visiteurs qui ont ouvert l'e-mail, mais d'autre part, cliquez sur le lien Désabonner pour exclure les messages électroniques futurs de votre organisation. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> eVar </td> 
   <td colname="col2"> Recipient ID </td> 
   <td colname="col3"> <p>Collecte à partir des paramètres de requête dans les liens de courrier électronique via la méthode de collecte automatisée ou un module JavaScript. </p> </td> 
   <td colname="col4"> Recipient ID </td> 
  </tr> 
  <tr> 
   <td colname="col1"> eVar  ou s. campaign </td> 
   <td colname="col2"> ID de message </td> 
   <td colname="col3"> <p>Collecte à partir des paramètres de requête dans les liens de courrier électronique via la méthode de collecte automatisée ou un module JavaScript. </p> </td> 
   <td colname="col4"> Cette valeur est souvent stockée dans la variable campaign. </td> 
  </tr> 
 </tbody> 
</table>

