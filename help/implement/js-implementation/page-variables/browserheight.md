---
description: Les variables de page renseignent directement un rapport (pageName, props de liste, variables de liste, etc.).
keywords: Analytics Implementation
subtopic: Variables
title: Variables de page
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# browserHeight

La variable affiche la hauteur de la fenêtre du navigateur.


<!-- 
browserheight.xml
-->

Cette variable est complétée après le code de page et avant l’exécution de *`doPlugins`*.

> [!NOTE] Cette variable doit uniquement être lue et ne jamais être définie.

Vous pouvez lire ces valeurs et les copier dans props/eVars, mais vous ne pouvez, en aucun cas, les modifier. Cette variable est apparue avec la version H.11 du fichier JavaScript.

**Paramètres**

<table id="table_94598A2204CF42FF9DD14D353D5C0468"> 
 <thead> 
  <tr> 
   <th class="entry"> Paramètre de requête </th> 
   <th class="entry"> Valeur </th> 
   <th class="entry"> Exemple </th> 
   <th class="entry"> Rapports concernés </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> <p>bh </p> </td> 
   <td> <p>Entier positif </p> </td> 
   <td> <p>865 </p> </td> 
   <td> <p>Trafic &gt; Technologie &gt; Hauteur du navigateur </p> </td> 
  </tr> 
 </tbody> 
</table>

