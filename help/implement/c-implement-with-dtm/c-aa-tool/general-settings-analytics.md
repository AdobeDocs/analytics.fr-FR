---
description: Description des champs pour les paramètres Général dans le gestionnaire dynamique de balises, pour déploiement d’Adobe Analytics.
keywords: Implémentation d'Analytics ; implementation method ; gestion dynamique des balises ; dtm ; paramètres généraux ; conformité à l'Union ; character - set ; code de devise ; serveur de suivi ; serveur de suivi SSL
seo-description: Description des champs pour les paramètres Général dans le gestionnaire dynamique de balises, pour déploiement d’Adobe Analytics.
seo-title: Général
solution: Analytics
title: Général
topic: Développeur et mise en œuvre
uuid: 93008719-6 fb 6-4 e 39-9 a 75-c 937 fe 3247 b 9
translation-type: tm+mt
source-git-commit: 49c81e50ff10060ef7a3debe82132d1099e25118

---


# Général

Description des champs des paramètres généraux dans DTM, pour déployer Adobe Analytics.

**[!UICONTROL &lt; Propriété &gt;]** &gt; ![](assets/settings_gear.png)**[!UICONTROL Modifier l'outil]** &gt; **[!UICONTROL Général]**

<table id="table_DD8DA303698041D296DD5DB080AF7971"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Élément </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Activer la conformité UE pour <span class="keyword">Adobe Analytics </span> </p> </td> 
   <td colname="col2"> <p> Permet d’activer ou de désactiver le suivi selon le cookie de confidentialité de l’UE. </p> <p>Lorsqu’une page est chargée, le système vérifie si un cookie appelé <span class="filepath">sat_track</span> est défini (ou le nom du cookie personnalisé spécifié dans la page <span class="wintitle">Modifier une propriété</span>). Prenez en compte les points suivants : </p> 
    <ul id="ul_42A6D728F0BC4FBABB0069EFB66DCB01"> 
     <li id="li_227CB14326344AA3980F20C7EACF2AD2"> <p> Si le cookie n’existe pas ou si le cookie existe et est défini sur une valeur autre que <span class="term"> true </span>, le chargement de l'outil est ignoré lorsque ce paramètre est activé. En d’autres termes, les parties de la règle qui utilisent cet outil ne sont pas appliquées. </p> <p>Si une règle contient des analyses avec la mise en conformité avec les normes de l’UE activée et du code de page tiers et si le cookie est défini sur la valeur <span class="term"> false </span>, le code tiers s'exécute toujours. Les variables d’analyse ne seront toutefois pas définies. </p> </li> 
     <li id="li_1E74E02D7E4646ACA86D862A1D3C6679"> Si le cookie existe mais est défini sur <span class="term"> true </span>, l'outil se charge normalement. </li> 
    </ul> <p>You are responsible for setting the <span class="filepath"> sat_track </span> (or custom named) cookie to <span class="term"> false </span> if a visitor opts out. Vous pouvez pour cela utiliser du code personnalisé : </p> <p> 
     <code>_ satellite. setcookie (« sat_ track », &amp; amp ; nbsp ; « false ») ; </code>
  </p> <p> You must also have a mechanism to set that cookie to <span class="term"> true </span> if you want a visitor to be able to opt in later: </p> <p> 
     <code>_ satellite. setcookie (« sat_ track », &amp; amp ; nbsp ; « true ») ; </code>
  </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Jeu de caractères </p> </td> 
   <td colname="col2"> <p>Affiche les jeux de codage de caractères disponible. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Code de devise </p> </td> 
   <td colname="col2"> <p>Affiche les codes de devise pris en charge pour la sélection. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Serveur de suivi </p> </td> 
   <td colname="col2"> <p>Domaine au niveau duquel sont écrits le cookie et la demande d’image. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Serveur de suivi SSL </p> </td> 
   <td colname="col2"> <p>Domaine au niveau duquel sont écrits le cookie et la demande d’image. Cet élément est utilisé pour les pages sécurisées. Si cet élément   n’est pas défini, les données SSL sont envoyées à la variable <span class="term"> trackingServer </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Centre de données </p> </td> 
   <td colname="col2"> <p>Centre de données Adobe utilisé pour la collecte des données. </p> </td> 
  </tr> 
 </tbody> 
</table>

