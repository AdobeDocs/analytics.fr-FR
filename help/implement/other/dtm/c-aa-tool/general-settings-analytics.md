---
description: Description des champs pour les paramètres Général dans le gestionnaire dynamique de balises, pour déploiement d’Adobe Analytics.
keywords: Analytics Implementation;implementation method;dynamic tag management;dtm;general settings;eu compliance;character set;currency code;tracking server;ssl tracking server
title: Général
topic: Developer and implementation
uuid: 93008719-6fb6-4e39-9a75-c937fe3247b9
translation-type: ht
source-git-commit: ebf149df7974f9f2889b6fe938088eda90c84051

---


# Général

Description des champs pour les paramètres Général dans DTM, pour déploiement d’Adobe Analytics.

**[!UICONTROL &lt;Propriété>]** > ![](assets/settings_gear.png) **[!UICONTROL Modifier l’outil]** > **[!UICONTROL Général]**

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
     <li id="li_227CB14326344AA3980F20C7EACF2AD2"> <p> Si le cookie n’existe pas ou si le cookie existe et est défini sur une valeur autre que <span class="term"> true </span>, le chargement de l’outil est ignoré lorsque ce paramètre est activé. En d’autres termes, les parties de la règle qui utilisent cet outil ne sont pas appliquées. </p> <p>Si une règle contient des analyses avec la mise en conformité avec les normes de l’UE activée et du code de page tiers et si le cookie est défini sur la valeur <span class="term"> false </span>, le code tiers s’exécute toujours. Les variables d’analyse ne seront toutefois pas définies. </p> </li> 
     <li id="li_1E74E02D7E4646ACA86D862A1D3C6679"> Si le cookie existe mais est défini sur <span class="term"> true </span>, l’outil charge normalement. </li> 
    </ul> <p>Il vous incombe de définir le cookie <span class="filepath"> sat_track </span> (ou le cookie personnalisé) sur <span class="term"> false </span> si un visiteur opt-out. Vous pouvez pour cela utiliser du code personnalisé : </p> <p> 
     <code>
       _satellite.setCookie("sat_track",&amp;nbsp;"false"); 
     </code> </p> <p> Vous devez également disposer d’un mécanisme pour définir ce cookie sur <span class="term"> true </span> si vous souhaitez qu’un visiteur puisse opt-in ultérieurement : </p> <p> 
     <code>
       _satellite.setCookie("sat_track",&amp;nbsp;"true"); 
     </code> </p> </td> 
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
   <td colname="col2"> <p>Domaine au niveau duquel sont écrits le cookie et la demande d’image. Cet élément est utilisé pour les pages sécurisées. Si la variable n’est pas défini, les données SSL sont envoyées à la variable  <span class="term">trackingServer</span>.  </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Centre de données </p> </td> 
   <td colname="col2"> <p>Centre de données Adobe utilisé pour la collecte des données. </p> </td> 
  </tr> 
 </tbody> 
</table>

