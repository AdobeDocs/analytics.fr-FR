---
description: Tous les segments créés dans le Créateur de segments ne sont pas compatibles avec Data Warehouse. Ce tableau répertorie les fonctions prises en charge.
title: Compatibilité des segments avec Data Warehouse
topic: Segments
uuid: 370258c5-8614-4434-871c-41753ed77f5c
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Compatibilité des segments avec Data Warehouse

Tous les segments créés dans le Créateur de segments ne sont pas compatibles avec l’[!DNL Data Warehouse]. Ce tableau répertorie les fonctions prises en charge.

<table id="table_BBB1DAFDF85041598FA4AF869172CF7F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col2" class="entry"> Analysis Workspace, Reports &amp; Analytics, Analyses ad hoc </th> 
   <th colname="col3" class="entry"> Data Warehouse </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Exclut</b> </td> 
   <td colname="col2"> Pris en charge à n’importe quel niveau </td> 
   <td colname="col3"> Pris en charge uniquement dans des cas spéciaux au niveau supérieur </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Segments séquentiels</b> </td> 
   <td colname="col2"> Pris en charge </td> 
   <td colname="col3"> Non pris en charge </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ET et OU peuvent être associés sans limites</b> </td> 
   <td colname="col2"> Pris en charge </td> 
   <td colname="col3"> Certaines limites. Voir *note* ci-dessous tableau. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Conteneurs imbriqués</b> </td> 
   <td colname="col2"> Pris en charge </td> 
   <td colname="col3"> Certaines limites (dont la portée doit diminuer, par exemple les visiteurs peuvent contenir des accès mais non l’inverse) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Dimensions</b> </td> 
   <td colname="col2">Faites glisser-déposer une dimension dans le champ <span class="uicontrol">Définitions</span> du Créateur de segments pour découvrir sa compatibilité avec les produits. Par exemple, les dimensions suivantes ne sont prises en charge que dans les Analysis Workspace, les Reports &amp; Analytics et les Ad Hoc Analysis : 
    <ul id="ul_BD708CC3A16743F49F998D1046EC70A3"> 
     <li id="li_240DA619D50B4336ACD9117BF59AF10A">Serveur d’accès </li> 
     <li id="li_222D4D4116674EF8A52945CCB9C78719">Catégorie d’accès </li> 
     <li id="li_5A43C846E2EA4EFCB892DE9E0607C68C">Date d’accès </li> 
     <li id="li_8E9CABBE04FC4A7A9A5D2BDD34AD3C87">Classement de toutes les pages de recherche </li> 
    </ul> </td> 
   <td colname="col3"> Faites glisser-déposer une dimension dans le champ <span class="uicontrol">Définitions</span> du Créateur de segments pour découvrir sa compatibilité avec les produits. Par exemple, les dimensions suivantes ne sont prises en charge que dans Data Warehouse : 
    <ul id="ul_61A5B314CCCF497DB0385324E3309E22"> 
     <li id="li_1254089BDFAE4E0F8E51CB1511BBBF53">Adresse IP </li> 
     <li id="li_D8E040F77A8C46A084547F4FE685CB10">URL de la page </li> 
     <li id="li_4C79AE900CF6458780C124143DC6FA5B">Identifiant visiteur </li> 
     <li id="li_4EC10645DE9740609D8DDFD4F668FE67">Identifiant visiteur Experience Cloud </li> 
    </ul> <p>Il <b>n’est pas</b> possible d’utiliser les dimensions ci-après dans les segments de Data Warehouse : </p> 
    <ul id="ul_FE143F6D1ABF45DAA444E1B5691C7D4F"> 
     <li id="li_E77F3CC45BA04674B857FE5AB19D56F1">Classement de toutes les pages de recherche </li> 
     <li id="li_95E1549C13F14BA0B32686401EE78E31">Matin/après-midi </li> 
     <li id="li_6F1C8FC2E7674A0CA14B70B65784D896">Jour du mois </li> 
     <li id="li_79D1A91D741D4CCC937D07906D71F964">Jour de la semaine </li> 
     <li id="li_4008565353084611BD782B98D50C0611">Jour de l’année </li> 
     <li id="li_F87D78F125874087BFF74FAAE2BA46F5">Unité opérationnelle d’entrée </li> 
     <li id="li_53DA4E64C6714CFF90D164245D01C16A">Entrée (toutes les dimensions commençant avec l’entrée, à l’exception de la page d’accès) </li> 
     <li id="li_7F26B0E54A4A48319F31D8FC499D1CF2">Sortie (toutes les dimensions commençant avec la sortie, à l’exception de Lien de sortie et Page de sortie) </li> 
     <li id="li_1877D2D8A95B43F29CAA426BF2FE4996">Hiérarchie (toutes les dimensions commençant avec la hiérarchie) </li> 
     <li id="li_DF0BCC63ED274ABEA1C5A28274936310">Détail des accès </li> 
     <li id="li_98BE56213E1A4FD28D4858D53C46D23E">Type d’accès </li> 
     <li id="li_52ECB31657DF4180BDB9C8D21CC74313">Heure de la journée </li> 
     <li id="li_93716207F2614822ACB84100B35D27BC">Mois de l’année </li> 
     <li id="li_FFC8E1F7092C4876A7E9F2365CC234B9">Pages introuvables </li> 
     <li id="li_7A070C8E0F664F5AB554555B17D0E4E6">Recherche payante </li> 
     <li id="li_12228C18BF90463C8D8394FB810843D3">Trimestre de l’année </li> 
     <li id="li_1833B6E2011C4757A60CAA2C98B35AFA">Fréquence des retours </li> 
     <li id="li_39154CD74A534D9AA09C701FE1E2C521">Visites sur une seule page </li> 
     <li id="li_84BDE34DD577488881E8842D2DE72D3C">Durée avant événement </li> 
     <li id="li_552BE3414CC949B3B24BE99298945874">Durée de consultation de la page – Regroupement </li> 
     <li id="li_33D815E04CB3493C82BE33E958C2D7B9">Durée par visite – Regroupement </li> 
     <li id="li_76F2BB88B8CD456DB50D04F36BB7854B">Suivi du motif d’exclusion </li> 
     <li id="li_07345E08D0584CEC99128A0542587019">États américains </li> 
     <li id="li_3D6BD9E927334B9BBC29E602D1103F7A">Jour ouvrable/week-end </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Empilement de segments</b> </td> 
   <td colname="col2"> Pris en charge </td> 
   <td colname="col3"> Non pris en charge </td> 
  </tr> 
 </tbody> 
</table>

*Remarque : L’entrepôt de données ne prend pas en charge tous les cas d’utilisation d’un`exclusion`conteneur ou d’un`without`conteneur lors de l’utilisation`AND/OR`. Lors de l’utilisation d’une telle combinaison, seuls les segments qui peuvent être réécrits en tant que`A AND NOT B`(ou **incluent cette caractéristique**et **excluent cette caractéristique**) sont pris en charge dans Data Warehouse.*
