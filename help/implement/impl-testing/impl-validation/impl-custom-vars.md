---
description: Liste des variables personnalisées utilisées dans Analytics.
keywords: Mise en œuvre d’Analytics
seo-description: Liste des variables personnalisées utilisées dans Analytics.
seo-title: Variables personnalisées
solution: Analytics
title: Variables personnalisées
topic: Développeur et mise en œuvre
uuid: 54 adf 622-7 f 05-49 c 0-b 7 e 6-702 bb 2 f 17 b 1 c
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Variables personnalisées

Liste des variables personnalisées utilisées dans Analytics.

<table id="table_E8C7871F63F648A59644638FB56BD0E1"> 
 <thead> 
  <tr> 
   <th class="entry"> Variable </th> 
   <th class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> Variables de trafic </td> 
   <td> Vérifier la valeur de prop1 à prop75. Voici la liste des éléments à vérifier. 
    <ul id="ul_0EE2D50BA90F4F21BD63268A5082F980"> 
     <li id="li_A6E4D66E8A03400491A26A08E4945908">La casse utilisée est-elle correcte ? « ValueA » est un enregistrement différent de « valueA ». Vous pouvez tout mettre en minuscules, étant donné qu’un petit groupe de navigateurs convertit toutes les variables en minuscules. </li> 
     <li id="li_65CBFB908E7B4ED5AF9518FE5B58D4E2">Les valeurs comportent-elles moins de 100 caractères ? Si tel n’est pas le cas, il se peut que des valeurs soient tronquées. </li> 
     <li id="li_CC506D114AFE44699D89AB84BBCCEBFC"> Toutes les valeurs d’une variable de propriété unique sont-elles liées ou certaines valeurs vous semblent-elles déplacées ? </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td> Variables de conversion </td> 
   <td> eVar 1 à eVar 75 font partie des variables <span class="wintitle">Econversion</span>.  Voici la liste des points à vérifier. 
    <ul id="ul_CA10C5B9F24B4C49A64CA84A9DCE8E63"> 
     <li id="li_8CCD92F3AD5E49EBA91C9B008DA47016">La casse utilisée est-elle correcte ? « ValueA » est un enregistrement différent de « valueA ». Vous pouvez tout mettre en minuscules, étant donné qu’un petit groupe de navigateurs convertit toutes les variables en minuscules. </li> 
     <li id="li_5B6FDEDB2C32409AA59D6BB0DF2346CB">Les valeurs comportent-elles moins de 255 caractères ? Si tel n’est pas le cas, il se peut que des valeurs soient tronquées. </li> 
     <li id="li_C31AFBAC99D84E96A1244E795CE7765D">Toutes les valeurs d’une eVar unique sont-elles liées ou certaines valeurs vous semblent-elles déplacées ? </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td> Evénements personnalisés </td> 
   <td> Les événements comprennent à la fois des valeurs standard (<span class="wintitle">prodView</span>, <span class="wintitle">scOpen</span>, <span class="wintitle">scAdd</span>, <span class="wintitle">scCheckout</span>, <span class="wintitle">purchase</span>) et des événements personnalisés entre event1 et event100. Tous les événements sont envoyés dans la variable « events ». Si plusieurs événements figurent sur une même page, ils doivent être séparés par une virgule (sans espace).  
    <ul id="ul_2213CC9DE892433FAF6FC1F5A2B841B4"> 
     <li id="li_15E31A9FF1654DFA93C158F422B9EAE3">Pour tous les événements de conversion standard, les produits pertinents doivent également être renseignés dans « products ». Pour tous les événements, à l’exception d’un achat, les éléments « quantité » et « prix » sont facultatifs. </li> 
     <li id="li_03ED9AAC45DA47A58AB482E2CEBF5108">L’événement <span class="wintitle">purchase</span> ne doit être défini qu’une seule fois par session après l’exécution et la confirmation de l’achat. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

