---
description: Le panneau de configuration d’Activity Map vous permet de modifier les paramètres et les propriétés de tous les types de visualisations des superpositions.
title: Paramétrage d’Activity Map
topic: Activity map
uuid: 42a0309e-3efc-4506-989b-09b6fe419423
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Paramétrage d’Activity Map

Le panneau de configuration d’Activity Map vous permet de modifier les paramètres et les propriétés de tous les types de visualisations des superpositions.

Accédez au panneau de configuration d’Activity Map en cliquant sur l’icône de l’engrenage dans la barre d’outils d’Activity Map.

Le panneau de configuration affiche un contenu différent en fonction du mode d’application sélectionné. L’onglet Autre comprend des paramètres généraux.

| Standard | **[!UICONTROL Superpositions en dégradé]** ou **[!UICONTROL bulle]** |
|---|---|
| En direct | **[!UICONTROL Superpositions des gagnants et des perdants]** **[!UICONTROL en dégradé]** ou **[!UICONTROL bulle]** |
| Autre | Sélection de suite de rapports et sélection de langue |

## Paramètres de superposition en mode standard {#section_24DB95376E1A448494ECF3F57743FC19}

![](assets/settings_standard.png)

<table id="table_0244107DE6D142F2A1DA4882E0ED9826"> 
 <thead> 
  <tr> 
   <th colname="col2" class="entry"> Paramètres </th> 
   <th colname="col3" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Étiqueter les superpositions avec</span> </td> 
   <td colname="col3"> 
    <ul id="ul_13AD02789F2D4904A35215A8FA230F3E"> 
     <li id="li_8DB71636D2074C69B0D94D3FB0CAFE28"> <b>Aucune étiquette</b> : uniquement applicable pour la superposition en dégradé. Dans ce cas, la couleur de la superposition donnera une idée du classement du lien </li> 
     <li id="li_39C98D7EA9514C1D8731B9D21C0E73A6"> <b>Valeur</b> : valeur brute totale pour ce lien. </li> 
     <li id="li_A5F583E45BCD4F2399398F9DCC7FE382"> <b>Pourcentage</b> : pourcentage de la mesure pour ce lien par rapport à la mesure totale pour la page. </li> 
     <li id="li_E4BF7D3B863E4B6C8E737CF29ADA9D67"> <b>Classement</b> : classement de ce lien parmi tous les liens présents sur la page rendue. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Taille de police de l’étiquette</span> </td> 
   <td colname="col3"> Vous permet d’augmenter ou de réduire la taille de police de l’étiquette de la superposition à l’aide d’un curseur pour une meilleure lisibilité. </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Afficher</span> </td> 
   <td colname="col3">Sélectionnez <span class="uicontrol">Début</span>, <span class="uicontrol">Fin</span> ou <span class="uicontrol">Tous les liens</span> pour les afficher dans la superposition. Si vous sélectionnez Début ou Fin, vous devez également sélectionner le nombre de liens à afficher. </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol">Masquer les superpositions pour les liens qui n’ont reçu aucune visite.</span> </td> 
   <td colname="col3"> Cette case à cocher vous permet de masquer les superpositions pour les liens qui n’ont reçu aucune visite, afin de limiter l’encombrement de l’interface. </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Couleur du dégradé / Couleur de la bulle</span> </td> 
   <td colname="col3">Faites votre choix parmi une sélection de couleurs pour afficher les classements des liens de superposition pour les visualisations des superpositions <span class="uicontrol">en dégradé</span> ou <span class="uicontrol">bulle</span>. </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Couleur du dégradé basée sur</span> </td> 
   <td colname="col3"> 
    <ul id="ul_1B5C2A44A9EB465D8B8E9AD91AF79D69"> 
     <li id="li_C983CB68B90B492BB0774254292B5961"> <span class="uicontrol"> 30 premiers classements</span> : l’intensité des couleurs est normalisée pour les 30 premières valeurs. </li> 
     <li id="li_1E83431C8C734AB0BC82B5A66AED1189"> <span class="uicontrol"> Valeur de mesure absolue</span> : l’intensité des couleurs dépend de la valeur de mesure absolue. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Transparence du dégradé</span> </td> 
   <td colname="col3">Sélectionnez le niveau de transparence pour les superpositions en dégradé. <p>Ce paramètre n’affecte pas les superpositions bulle. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Paramètres de superposition en mode réel {#section_D30F6E62FB5D404090B588F396A460AF}

![](assets/settings_live.png)

| Paramètres | Description |
|---|---|
| **[!UICONTROL Afficher en haut]** | Sélectionnez les liens à afficher (ou tous) et les **[!UICONTROL gagnants]** ou **[!UICONTROL perdants]** (ou les deux) à afficher sous forme de superpositions. |
| **[!UICONTROL Exclure le bas (%)]** | Sélectionnez cette option pour éliminer les liens des gagnants et des perdants avec des données éparses. Filtrez les pourcentages inférieurs des changements de liens pour afficher uniquement les liens avec suffisamment de données pour présenter des gains ou des pertes significatives. Le pourcentage est calculé en fonction du nombre de liens sur la page. Par exemple, filtrer les 10 % inférieurs d’une liste de 200 liens filtrerait les 20 derniers liens. |
| **[!UICONTROL Mettre à jour les données automatiquement]** | Vous permet de décider si les données Analytics affichées dans l’interface doivent être mises à jour automatiquement lorsqu’une nouvelle période est calculée. |
| **[!UICONTROL Période de mise à jour automatique]** | Actualise la page web à chaque nouvelle récupération des données afin que les liens de la page soient mieux synchronisés avec les données collectées. |

## Autres paramètres {#section_697A12F099494D699A4BF498598178C5}

![](assets/settings_other.png)

<table id="table_0F560236F8844FA0928CBB9C50D5ABEF"> 
 <tbody> 
  <tr> 
   <td colname="col1"> Suite de rapports </td> 
   <td colname="col2"> <p>La liste des suites de rapports auxquelles vous avez accès ne se limite plus aux seules suites de rapports définies dans une balise de page web. Vous pouvez désormais remplacer la suite de rapports sélectionnée (correspondant à l’une des balises de la page) par une autre suite de rapports. Il n’est pas nécessaire que celle-ci soit liée à une balise sur la page. Si vous modifiez la suite de rapports sélectionnée dans les paramètres d’Activity Map, le processus d’<span class="uicontrol">enregistrement</span> entraînera l’actualisation de tous les rapports Analytics affectés. </p> <p> <p>Important : Les suites de rapports virtuelles sont uniquement compatibles avec le mode standard, et non le mode réel. Si vous vous trouvez en mode réel pour une suite de rapports standard, mais que vous sélectionnez une suite de rapports virtuelle dans cette boîte de dialogue, le mode standard s’affichera une fois que vous aurez cliqué sur <span class="uicontrol">OK</span>. </p> </p> <p>De plus, la commande Calendrier sera réinitialisée pour correspondre au type de calendrier de la suite de rapports (grégorien, vente au détail, personnalisé...). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Langue </td> 
   <td colname="col2"> La sélection correspond aux langues proposées dans Adobe Analytics. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> À propos de </td> 
   <td colname="col2"> Indique le nom et le numéro de version de l’application. </td> 
  </tr> 
 </tbody> 
</table>

