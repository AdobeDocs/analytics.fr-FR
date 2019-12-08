---
description: Vous trouverez, dans le tableau ci-dessous, les paramètres de requête contenant la valeur de chaque variable d’analyse envoyée à la collecte de données.
keywords: Analytics Implementation
title: Paramètres de requête de la collecte de données
topic: Developer and implementation
uuid: 4d5af486-df27-42fe-bb9c-28938dddf2b2
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Paramètres de requête de la collecte de données

Vous trouverez, dans le tableau ci-dessous, les paramètres de requête contenant la valeur de chaque variable d’analyse envoyée à la collecte de données.

Ces informations peuvent être utilisées lors d’opérations de débogage réalisées à l’aide de [Analyseurs de paquets](/help/implement/impl-testing/packet-monitor.md), lors de la création manuelle de demandes d’image ou lors de l’utilisation de [variables dynamiques](/help/implement/js-implementation/c-variables/dynvars-overview.md).

<table id="table_5442E15BF0AE4BDA92DDADD1C08F7C13"> 
 <thead> 
  <tr> 
   <th class="entry"> Paramètre </th> 
   <th class="entry"> Variable Analytics </th> 
   <th class="entry"> Rapport rempli </th> 
   <th class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> aamlh </td> 
   <td colname="col2"> Aucun </td> 
   <td colname="col3"> Aucun </td> 
   <td colname="col4"> Conseil relatif à l’emplacement d’Audience Manager (utilisé dans l’intégration du profil partagé d’Experience Cloud) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> aamb </td> 
   <td colname="col2"> Aucun </td> 
   <td colname="col3"> Aucun </td> 
   <td colname="col4"> Audience Manager Blob (utilisé dans l’intégration du profil partagé d’Experience Cloud) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> aid </td> 
   <td colname="col2"> Aucun </td> 
   <td colname="col3"> Aucun </td> 
   <td colname="col4"> Identifiant visiteur Analytics </td> 
  </tr> 
  <tr> 
   <td> AQB </td> 
   <td> Aucun </td> 
   <td> Aucun </td> 
   <td> Indique le début d’une demande d’image. </td> 
  </tr> 
  <tr> 
   <td> AQE </td> 
   <td> Aucun </td> 
   <td> Aucun </td> 
   <td> Indique la fin d’une demande d’image, ce qui signifie que la demande n’a pas été tronquée. </td> 
  </tr> 
  <tr> 
   <td> bh </td> 
   <td> Aucun </td> 
   <td> Profil du visiteur | Technologie | Hauteur du navigateur </td> 
   <td> Hauteur de la fenêtre du navigateur (en pixels) </td> 
  </tr> 
  <tr> 
   <td> bw </td> 
   <td> Aucun </td> 
   <td> Profil du visiteur | Technologie | Largeur du navigateur </td> 
   <td> Largeur de la fenêtre du navigateur (en pixels) </td> 
  </tr> 
  <tr> 
   <td> c </td> 
   <td> Aucun </td> 
   <td> Profil du visiteur | Technologie | Profondeurs de couleur du moniteur </td> 
   <td> Qualité des couleurs (en bits) </td> 
  </tr> 
  <tr> 
   <td> </td><td><p></p></td><td><p></p></td><td><p></p><p><code> &lt;my.a&gt;red&lt;/my.a&gt; </code></p><p></p><p><code> &lt;my&gt;&lt;a&gt;red&lt;/a&gt;&lt;/my&gt; </code></p><p><code> my.a = red </code></p><p><code> c.&my.a=red </code></p></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td><code> D </code></td><td></td><td></td><td><p></p></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td><p><code> t </code></p><code>
      dd/mm/yyyy&amp;nbsp;hh:mm:ss&amp;nbsp;D&amp;nbsp;OFFSET 
    </code><p><code> 0-6 </code><code> OFFSET </code></p><code>
      offset&amp;nbsp;from&amp;nbsp;GMT&amp;nbsp;in&amp;nbsp;hours&amp;nbsp;*&amp;nbsp;60&amp;nbsp;*&amp;nbsp;-&amp;nbsp;1 
    </code><p></p><code>
      23/09/2016&amp;nbsp;14:00:00&amp;nbsp;1&amp;nbsp;420 
    </code></td></tr><tr><td><code> ts </code></td><td><p></p></td><td></td><td><p></p></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td><p></p></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td><p></p></td></tr></tbody></table>

