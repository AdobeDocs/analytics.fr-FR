---
description: Data Warehouse fait référence à la copie de données Analytics pour les rapports de stockage et personnalisés, que vous pouvez exécuter en filtrant les données. Vous pouvez demander des rapports pour afficher des relations de données avancées à partir de données brutes en fonction de vos questions uniques. Les rapports de l’entrepôt de données sont envoyés par courriel ou par FTP. Leur traitement peut prendre jusqu’à 72 heures. La durée de traitement dépend de la complexité de la requête et de la quantité de données demandées.
title: Data Warehouse - Aperçu
topic: Data warehouse
uuid: 768557dd-1644-4ce6-bfc2-8c46dd6e1cd1
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Data Warehouse - Aperçu

L’entrepôt de données fait référence à la copie des données Analytics pour les  de  et les rapports personnalisés, que vous pouvez exécuter en filtrant les données. Vous pouvez demander des rapports pour afficher des relations de données avancées à partir de données brutes en fonction de vos questions uniques. Les rapports de l’entrepôt de données sont envoyés par courriel ou par FTP. Leur traitement peut prendre jusqu’à 72 heures. La durée de traitement dépend de la complexité de la requête et de la quantité de données demandées.

Adobe active Data Warehouse pour les seuls utilisateurs de niveau administrateur, et ce, pour des suites de rapports spécifiques. (Il peut être activé pour les suites de rapports globales et enfants, mais pas pour les suites de rapports de cumul.) L’administrateur peut créer un groupe ayant accès à l’entrepôt de données, puis y associer des utilisateurs non administrateurs.

L’entrepôt de données compresse automatiquement les fichiers de plus de 1 Mo. La taille maximale des pièces jointes du courrier électronique est de 10 Mo.

L’entrepôt de données peut traiter un nombre illimité de lignes dans une seule requête pour des rapports planifiés et téléchargés individuels.

>[!NOTE] Data Warehouse consigne la première valeur rencontrée dans la période de création du rapport.

>[!IMPORTANT]
>
>Lors de la segmentation des valeurs classifiées, Analysis Workspace et Data Warehouse traitent différemment les valeurs « non spécifiées ». Dans Workspace, « Non spécifié » fait référence à des valeurs qui ne sont pas classées, tandis que dans Data Warehouse, cela fait référence à des valeurs que vous avez classées comme « Non spécifiées ».

## Description des demandes de Data Warehouse {#section_F21C78ED36884C389C852E876AF5CDE8}

Ce tableau décrit les champs et options de l’ [!UICONTROL Data Warehouse Request] onglet.

<table id="table_7325A2466866460E8B0AF7D696152713"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elément </th> 
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
    </ul> <p>Le de l'entrepôt de données sur les suites de rapports virtuelles prend en charge le fuseau horaire alternatif configuré sur la suite de rapports virtuelle. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Segments disponibles</span> </td> 
   <td colname="col2"> <p>Permet de sélectionner la partie de la population de à examiner et de générer des segments complexes. Vous pouvez charger des segments préconfigurés, créer de nouveaux segments et stocker des composants de segments dans une bibliothèque afin de les utiliser pour créer des segments supplémentaires. </p> <p>Vous pouvez désormais empiler des segments. Lors de la sélection de plusieurs segments, la zone  du, le Gestionnaire de requêtes et la fenêtre contextuelle Détails de la requête affichent un de noms séparé par des virgules (Segment1, Segment2, par exemple). </p> <p>Pour plus d’informations, consultez le <a href="/help/components/c-segmentation/seg-home.md"> Guide de segmentation</a>. </p> <p>Remarque : vous ne pouvez pas inclure un filtre de segment et une ventilation sur un même segment dans un même rapport Data Warehouse. Sinon, une erreur se produira. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Ventilations</span> </td> 
   <td colname="col2"> <p>Vous permet de classer les données par catégorie à l’aide de ventilations. Les segments et les ventilations diffèrent en ce qu’un segment  des données d’un jeu de données, tandis qu’une ventilation compartimente les données de toutes les valeurs valides pour la ventilation. </p> Vous pouvez également ventiler un rapport selon un ou plusieurs segments. Cependant, vous ne pouvez pas inclure à la fois un filtre de segment et une ventilation sur le même segment, dans le même rapport Entrepôt de données. Sinon, une erreur se produira. <p> Par exemple, utilisez les segments pour supprimer un sexe du jeu de données et utilisez une ventilation pour afficher les données séparées par sexe. </p> <p>Lorsqu’une demande d’entrepôt de données est envoyée avec plusieurs dimensions à plusieurs valeurs (par exemple, divers rapports mobiles), un nombre exponentiel de lignes peut être généré à partir d’un seul accès. Le nombre de lignes pouvant être générées à partir d’un seul accès est plafonné à 100 (1 000 auparavant). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Mesures</span> </td> 
   <td colname="col2">Vous permet d’ajouter des mesures que vous souhaitez exécuter. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="wintitle"> Tri des mesures</span> </td> 
   <td colname="col2">Fournit des rapports de ventilation avec classement, triés par valeurs de mesure décroissantes, semblables à ce qui s’affiche dans l’interface utilisateur de Reports &amp; Analytics, de Data Workbench, etc. <a href="/help/export/data-warehouse/sorting-by-metric.md"  > Plus...</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Planifier la livraison du rapport</span> </td> 
   <td colname="col2"> <p>Vous permet de planifier des demandes de  automatique à des intervalles sélectionnés ou sous la forme d’un rapport unique. Si vous utilisez le format par défaut, le rapport est envoyé par courrier électronique sous la forme d’un fichier .csv. </p> <p>Pour ajouter la plage de dates, indiquez <span class="filepath">%R</span> dans le nom du fichier. Cette valeur représente les valeurs de dates demandées dans le rapport. Si, par exemple, vous demandez des données du 1er mai 2013 au 7 mai 2013, la variable <span class="filepath">%R</span> présente un nom de fichier contenant la plage de dates 20130501 - 20130507. </p> </td> 
  </tr> 
 </tbody> 
</table>

