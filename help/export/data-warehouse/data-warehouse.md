---
description: L’entrepôt de données fait référence à la copie de données Analytics pour les rapports de stockage et personnalisés, que vous pouvez exécuter en filtrant les données. Vous pouvez demander des rapports qui présentent un niveau avancé de relations entre les données brutes, en fonction de vos questions. Les rapports d’entrepôt de données sont envoyés par courriel ou par FTP. Leur traitement peut prendre jusqu’à 72 heures. La durée de traitement dépend de la complexité de la requête et de la quantité des données demandées.
title: Data Warehouse - Aperçu
topic: Data warehouse
uuid: 768557dd-1644-4ce6-bfc2-8c46dd6e1cd1
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Data Warehouse - Aperçu

Data Warehouse fait référence à la copie de données Analytics pour les rapports de stockage et personnalisés, que vous pouvez exécuter en filtrant les données. Vous pouvez demander des rapports qui présentent un niveau avancé de relations entre les données brutes, en fonction de vos questions. Les rapports d’entrepôt de données sont envoyés par courriel ou par FTP. Leur traitement peut prendre jusqu’à 72 heures. La durée de traitement dépend de la complexité de la requête et de la quantité de données demandée.

Adobe active Data Warehouse pour les seuls utilisateurs de niveau administrateur et ce, pour des suites de rapports spécifiques. (Cette API peut être activée pour les suites de rapports globales et secondaires, mais pas pour les suites de rapports de cumul.) L’administrateur peut créer un groupe ayant accès à Data Warehouse, puis y associer des utilisateurs qui ne sont pas administrateurs.

Data Warehouse compresse automatiquement les fichiers de plus de 1 Mo. La taille totale des pièces jointes d’un courrier électronique ne peut pas dépasser 10 Mo.

Data Warehouse peut traiter un nombre illimité de lignes dans une seule demande pour des rapports distincts téléchargés et planifiés.

> [!NOTE] L’entrepôt de données signale la première valeur rencontrée dans la période du rapport.

>[!IMPORTANT]
>
>Lors de la segmentation sur des valeurs classées, Analysis Workspace et Data Warehouse traitent différemment les valeurs "non spécifiées". Dans Workspace, « Non spécifié » fait référence à des valeurs qui ne sont pas classées, tandis que dans Data Warehouse, cela fait référence à des valeurs que vous avez classées comme « Non spécifiées ».

## Description des demandes de Data Warehouse {#section_F21C78ED36884C389C852E876AF5CDE8}

Ce tableau décrit les champs et options de l’onglet [!UICONTROL Demande Data Warehouse].

<table id="table_7325A2466866460E8B0AF7D696152713"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Élément </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Nom de la demande</span> </td> 
   <td colname="col2"> Identifie la demande. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Date de création du rapport</span> </td> 
   <td colname="col2"> <p>Date et granularité de la demande. </p> 
    <ul id="ul_C00F4529BD9E4113B517A61751B1DD5C"> 
     <li id="li_4D7C26812DF94ED7B64F985309541F46"> <span class="wintitle"> Personnalisée</span> : plage de dates que vous configurez dans le calendrier. </li> 
     <li id="li_2B272087006847148A936350D1B2D523"> <span class="wintitle"> Prédéfinie</span> : plage prédéfinie. Cette plage dépend de la date du rapport. </li> 
     <li id="li_745989965BB94D489FF7046587E13C42"> <span class="wintitle"> Granularité</span> : granularité temporelle. Les valeurs valides sont Aucune, Horaire, Journalière, Hebdomadaire, Mensuelle, Trimestrielle et Annuelle. </li> 
    </ul> <p>Dans Data Warehouse, la création de rapports sur les suites de rapports virtuelles prend en charge le fuseau horaire alternatif configuré dans la suite de rapports virtuelle. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Segments disponibles</span> </td> 
   <td colname="col2"> <p>Permet de sélectionner la population de visiteurs que vous souhaitez étudier et de générer des segments complexes. Vous pouvez charger des segments préconfigurés, créer des segments et stocker les composants de segments dans une bibliothèque afin de les utiliser pour générer des segments supplémentaires. </p> <p>Vous pouvez désormais empiler les segments. Lors de la sélection de plusieurs segments, la zone d’aperçu, le Gestionnaire de requêtes et la fenêtre contextuelle Détail de la demande affichent une liste des noms séparés par des virgules (Segment1, Segment2, par exemple). </p> <p>See the <a href="/help/components/c-segmentation/seg-home.md"> Segmentation Guide</a> for more information. </p> <p>Remarque : Vous ne pouvez pas inclure un filtre de segment et une ventilation sur un même segment dans un même rapport Data Warehouse. Sinon, une erreur se produira. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Ventilations</span> </td> 
   <td colname="col2"> <p>Permet de catégoriser des données à l’aide de ventilations. Les segments se distinguent des ventilations dans la mesure où ils filtrent les données d’un jeu de données, tandis qu’une ventilation classe des données par catégorie entre toutes les valeurs pertinentes. </p> Vous pouvez également ventiler un rapport selon un ou plusieurs segments. Vous ne pouvez pas toutefois inclure un filtre de segment et une ventilation sur un même segment dans un même rapport Data Warehouse. Sinon, une erreur se produira. <p> Utilisez, par exemple, les segments pour retirer un sexe de l’ensemble des données et une ventilation pour afficher les données réparties par sexe. </p> <p>Lorsqu’une demande Data Warehouse est envoyée avec plusieurs dimensions à plusieurs valeurs (par ex. plusieurs rapports mobiles), un nombre exponentiel de lignes peut être généré à partir d’un seul accès. Le nombre de lignes pouvant être généré par un seul accès est plafonné à 100 (1 000 auparavant). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Mesures</span> </td> 
   <td colname="col2">Vous permet d’ajouter des mesures sur lesquelles vous souhaitez créer des rapports. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="wintitle"> Tri des mesures</span> </td> 
   <td colname="col2">Fournit des rapports de ventilation avec classement, triés par valeurs de mesure décroissantes, semblables à ce qui s’affiche dans l’interface utilisateur des Reports &amp; Analytics, de Data Workbench, etc. <a href="/help/export/data-warehouse/sorting-by-metric.md"  > Plus...</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Planifier la livraison du rapport</span> </td> 
   <td colname="col2"> <p>Permet de planifier une remise automatique des demandes à des intervalles sélectionnés ou de programmer un rapport unique ponctuel. Avec le format par défaut, le rapport est envoyé par courriel au format .csv. </p> <p>Pour ajouter la plage de dates, indiquez <span class="filepath">%R</span> dans le nom du fichier. Cette valeur représente les valeurs de dates demandées dans le rapport. Si, par exemple, vous demandez des données du 1er mai 2013 au 7 mai 2013, la variable <span class="filepath">%R</span> présente un nom de fichier contenant la plage de dates 20130501 - 20130507. </p> </td> 
  </tr> 
 </tbody> 
</table>

