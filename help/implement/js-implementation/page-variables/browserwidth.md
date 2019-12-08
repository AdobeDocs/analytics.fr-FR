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



# browserWidth

La variable affiche la largeur de la fenêtre du navigateur.


<!-- 

browserwidth.xml

 -->

Cette variable est complétée après le code de page et avant l’exécution de *`doPlugins`*.

> [!NOTE] Cette variable doit uniquement être lue et ne jamais être définie.

Vous pouvez lire ces valeurs et les copier dans props/eVars, mais vous ne pouvez, en aucun cas, les modifier. Cette variable est apparue avec la version H.11 du fichier JavaScript.

**Paramètres**

<table id="table_B70F279A8CD240328520E5BD889806BD"> 
 <tbody> 
  <tr> 
   <td> <p> <b>Paramètre de requête</b> </p> </td> 
   <td> <p> <b>Valeur</b> </p> </td> 
   <td> <p> <b>Exemple</b> </p> </td> 
   <td> <p> <b>Rapports concernés</b> </p> </td> 
  </tr> 
  <tr> 
   <td> <p>bw </p> </td> 
   <td> <p>Entier positif </p> </td> 
   <td> <p>1179 </p> </td> 
   <td> <p>Trafic &gt; Technologie &gt; Largeur du navigateur </p> </td> 
  </tr> 
 </tbody> 
</table>
