---
description: Affiche des données sur l’emplacement des visiteurs. Les rapports de géosegmentation incluent les pays, régions, villes, états et provinces et zones marketing numériques aux États-Unis. Les rapports de géosegmentation sont activés pour tous les clients.
title: Géosegmentation
topic: Reports
uuid: 66aa22c4-dcbc-491a-b23c-0c3d87444d23
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Géosegmentation

Affiche des données sur l’emplacement des visiteurs. Les rapports de géosegmentation incluent les pays, régions, villes, états et provinces et zones marketing numériques aux États-Unis. Les rapports de géosegmentation sont activés pour tous les clients.

Toutes les mesures disponibles à d’autres emplacements dans les Reports &amp; Analytics sont automatiquement incluses dans les rapports Pays, Régions, Villes, États américains et DMA : mesures de conversion et basées sur les visites ainsi que les mesures calculées. Pour plus d’informations, voir cette publication du [blog](https://blogs.adobe.com/digitalmarketing/analytics/introducing-new-metrics-in-geosegmentation-and-more/) Adobe.

<table id="table_566CFFC82E1149D8BAFE6641627FCF1F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Rapport </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Pays </td> 
   <td colname="col2"> <p> Division géographique la plus importante. Outre les vues « Classement » et « Tendance » standard disponibles pour la plupart des rapports, il existe également une vue « Carte » présentant les pays par couleurs en fonction de leur contribution relative au trafic total. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Régions </td> 
   <td colname="col2"> <p> Zone géographique plus petite qu’un pays, mais plus grande qu’une ville. Dans certains pays, une région est un état, une province ou une préfecture. Dans d’autres, il peut s’agir d’un pays constitutif, d’un département ou d’une région métropolitaine. À droite de chaque région affichée, le pays de la région est également indiqué entre parenthèses. </p> <p>Dans le détail du tableau, cliquez sur Exécuter un rapport Villes pour cette région (la loupe) afin d’exécuter un rapport comparant les performances de plusieurs villes d’une région sélectionnée. </p> <p>Voir <a href="/help/components/c-variables/dimensionslist/reports-geosegmentation-reference.md"  > Utilisation des régions et codes postaux de géosegmentation par pays</a> pour découvrir les pays qui utilisent des régions. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Villes </td> 
   <td colname="col2"> <p> Plus petite division géographique. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> États (É.-U.) </td> 
   <td colname="col2"> <p> Carte identifiant les visiteurs de chaque État des États-Unis. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> U.S. DMA </td> 
   <td colname="col2"> <p> (Zone marketing numérique) Divisions du marché des médias pour la radio et la télévision à l’échelle des États-Unis. Vous pouvez filtrer le rapport afin d’afficher uniquement les zones marketing d’un état particulier. Ces données sont fournies par l’intermédiaire d’un partenariat entre Adobe et Nielsen Media Research, Inc. </p> <p>Remarque : L’entrée Non spécifié du rapport DMA E.U. présente les visiteurs qu’il n’a pas été possible d’associer à une zone spécifique. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Précision des rapports </td> 
   <td colname="col2"> <p>Adobe a conclu un partenariat avec Digital Envoy, principal fournisseur de solutions d’authentification et de renseignements IP, en vue de proposer la géosegmentation, une fonctionnalité de mesure géographique basée sur les adresses IP des utilisateurs. Bien que la précision sur base de jeux de données individuels soit variable, Digital Envoy garantit généralement un taux de précision de plus de 99 % au niveau national, de plus de 97 % au niveau régional et de plus de 90 % au niveau de la ville. </p> <p>Remarque : ces chiffres supposent que [le paramètre] (/help/admin/admin/general-acct-settings-admin.md) qui permet de supprimer le dernier octet de l’adresse IP n’est PAS activé. </p> <p>Les adresses IP sont mises en correspondance avec les codes postaux, et chaque ville est définie par les codes postaux que les autorités définissent comme faisant partie de la ville en question. Par exemple, la banlieue de Berlin n’est pas incluse dans la définition de Berlin, mais chaque ville est répertoriée séparément, en supposant que les adresses IP peuvent être mises en correspondance avec précision avec un code postal de l’une de ces villes. </p> <p>Vous trouverez, ci-dessous, un aperçu des facteurs qui influencent les données de géosegmentation : </p> 
    <ul id="ul_1B05024AD5174232A8DB8145753FB09B"> 
     <li id="li_C3A21E7C1186490EB9A236634DB45E7F">Adresses IP représentant des serveurs proxy d’entreprise. Ces adresses peuvent apparaître sous la forme de trafic transitant par le réseau d’entreprise de l’utilisateur, lequel peut, en réalité, être un emplacement différent si l’utilisateur travaille à distance. </li> 
     <li id="li_56FC36B3598C420F9246D4E8772822A7">Adresses IP de mobiles. Le ciblage des adresses IP de mobiles fonctionne à différents niveaux en fonction de l’emplacement et du réseau. Plusieurs opérateurs renvoient le trafic IP via des POP centralisés ou régionaux. </li> 
     <li id="li_C1EED854AE584489BCBC2A7AA20B8EF1">Adresses IP appartenant à des clients de FAI par satellite. Identifier l’emplacement spécifique de ces utilisateurs s’avère difficile, dans la mesure où ils semblent toujours provenir de l’emplacement de la liaison montante. </li> 
     <li id="li_A735756F39554DF19E05D251CA614F02">Adresses IP militaires et gouvernementales. Cette catégorie englobe généralement les personnels qui voyagent autour du globe et accèdent aux sites par le biais de leur point d’origine, plutôt qu’au départ de la base ou du bureau où ils sont actuellement. </li> 
     <li id="li_ACFF1B8094684173B8325A44304CA32B">Les données de géosegmentation/IP sont fournies par un fournisseur tiers ; elles sont régulièrement mises à jour en fonction des informations fournies par les fournisseurs de services Internet et d’autres sources réseau. Les recherches d’adresses IP sont par essence volatiles, puisqu’elles sont fréquemment vendues et achetées dans le monde entier. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

