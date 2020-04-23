---
description: Affiche des données sur l’emplacement du. Les rapports de géosegmentation comprennent les pays, les régions, les villes, les États américains et la DMA (zone de marketing numérique) des États-Unis. Les rapports de géosegmentation sont activés pour tous les clients.
title: Géosegmentation
topic: Reports
uuid: 66aa22c4-dcbc-491a-b23c-0c3d87444d23
translation-type: tm+mt
source-git-commit: 5e47974fcf95625def21a9011ad981197ae39c99

---


# Géosegmentation

Affiche des données sur l’emplacement du. Les rapports de géosegmentation comprennent les pays, les régions, les villes, les États américains et la DMA (zone de marketing numérique) des États-Unis. Les rapports de géosegmentation sont activés pour tous les clients.

Toutes les mesures disponibles ailleurs dans les rapports et analyses sont automatiquement incluses dans les rapports Pays, Régions, Villes, Etats américains et DMA : les mesures basées sur les conversions et les visites, ainsi que les mesures calculées. For more information, see this Adobe [blog](https://blogs.adobe.com/digitalmarketing/analytics/introducing-new-metrics-in-geosegmentation-and-more/) post.

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
   <td colname="col2"> <p> La plus grande division géographique. Outre les vues « Classement » et « Tendance » standard disponibles pour la plupart des rapports, il existe également une vue « Carte » présentant les pays par couleurs en fonction de leur contribution relative au trafic total. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Régions </td> 
   <td colname="col2"> <p> Zone géographique plus petite qu’un pays mais plus grande qu’une ville. Dans certains pays, une région est un état, une province ou une préfecture. Dans d'autres régions, il s'agit d'un pays, d'un département ou d'une région métropolitaine constitutive. A droite de chaque région affichée, le pays de la région est également indiqué entre parenthèses. </p> <p>Dans le détail du tableau, cliquez sur Exécuter un rapport Villes pour cette région (la loupe) pour exécuter un rapport qui présente les performances des villes d’une région sélectionnée par rapport aux autres villes de la région. </p> <p>See <a href="/help/components/c-variables/dimensionslist/reports-geosegmentation-reference.md"  > GeoSegmentation Regions and Postal Code usage by Country</a> to see which countries use regions. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Villes </td> 
   <td colname="col2"> <p> La plus petite division géographique. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Etats-Unis (É.-U.) </td> 
   <td colname="col2"> <p> Carte thermique montrant les de chaque état des États-Unis. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> U.S. DMA </td> 
   <td colname="col2"> <p> (Zone de marketing numérique) Divisions du marché des médias pour la radio et la télévision à travers les États-Unis. Vous pouvez filtrer le rapport pour n’afficher que les zones marketing d’un état particulier. Ces données sont fournies dans le cadre d’un partenariat entre Adobe et Nielsen Media Research, Inc. </p> <p>Remarque : L’entrée Non spécifié du rapport DMA E.U. présente les visiteurs qu’il n’a pas été possible d’associer à une zone spécifique. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Précision des rapports </td> 
   <td colname="col2"> <p>Adobe s’est associé à Digital Envoy, un fournisseur de premier plan de solutions d’authentification et d’intelligence IP, pour  la géoSegmentation , une fonctionnalité de mesure géographique basée sur les adresses IP des utilisateurs finaux. Bien que la précision basée sur des ensembles de données individuels puisse varier, en général, Digital Envoy  une précision de plus de 99 % au niveau du pays, de plus de 97 % au niveau de la région et de plus de 90 % au niveau de la ville. </p> <p>Note: These numbers assume that <a href="/help/admin/admin/general-acct-settings-admin.md">the setting</a> to remove the last octet of the IP address is NOT enabled. </p> <p>Les adresses IP sont mises en correspondance avec les codes postaux, et chaque ville est définie par les codes postaux que les autorités définissent comme faisant partie de la ville en question. Par exemple, la banlieue de Berlin n’est pas incluse dans la définition de Berlin, mais chaque ville est répertoriée séparément, en supposant que les adresses IP peuvent être mises en correspondance avec précision avec un code postal de l’une de ces villes. </p> <p>Voici quelques facteurs qui peuvent influencer les données de géosegmentation : </p> 
    <ul id="ul_1B05024AD5174232A8DB8145753FB09B"> 
     <li id="li_C3A21E7C1186490EB9A236634DB45E7F">Adresses IP représentant des serveurs proxy d’entreprise. Elles peuvent apparaître comme du trafic provenant du réseau d’entreprise de l’utilisateur, qui peut être un autre emplacement si l’utilisateur travaille à distance. </li> 
     <li id="li_56FC36B3598C420F9246D4E8772822A7">Adresses IP mobiles. Le ciblage des adresses IP de mobiles fonctionne à différents niveaux en fonction de l’emplacement et du réseau. Un certain nombre d'opérateurs redirigent le trafic IP via des POP centralisés ou régionaux. </li> 
     <li id="li_C1EED854AE584489BCBC2A7AA20B8EF1">Adresses IP appartenant aux utilisateurs des FAI satellites. Il est difficile d’identifier l’emplacement spécifique de ces utilisateurs, puisqu’ils semblent provenir généralement de l’emplacement du lien montant. </li> 
     <li id="li_A735756F39554DF19E05D251CA614F02">Les IP militaires et gouvernementales. Cela représente souvent le personnel qui voyage autour du monde et qui entre par leur lieu d'origine, plutôt que la base ou le bureau où ils sont actuellement stationnés. </li> 
     <li id="li_ACFF1B8094684173B8325A44304CA32B">Nos données de géosegmentation/IP sont fournies par un fournisseur tiers et sont mises à jour régulièrement en fonction des informations fournies par les FAI et d'autres sources du réseau. Les recherches d’adresses IP sont intrinsèquement volatiles, car elles sont achetées et vendues fréquemment dans le monde entier. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

