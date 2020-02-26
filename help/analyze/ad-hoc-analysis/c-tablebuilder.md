---
description: Utilisez le Générateur de tableau pour créer un rapport avec n’importe quelle configuration de mesures, de dimensions et de segments. Par exemple, vous pouvez ajouter plusieurs mesures au Générateur de tableau, puis appliquer le segment à toutes en même temps. Vous pouvez appliquer des options des volets d’outils sous forme de lignes, de ventilations ou de colonnes, puis faire pivoter le tableau pour obtenir une vue différente. Après avoir créé le tableau, vous pouvez interagir directement avec le tableau de données qui en résulte afin d’effectuer une analyse plus approfondie. Pour rappel, lorsque vous générez un tableau de données à partir du Générateur de tableau, une requête est exécutée et un nouveau tableau est créé.
title: Générateur de tableau
uuid: d5dbd05e-9ebd-4571-b3a5-3856c28b65f3
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Générateur de tableau

Utilisez le Générateur de tableau pour créer un rapport avec n’importe quelle configuration de mesures, de dimensions et de segments. Par exemple, vous pouvez ajouter plusieurs mesures au Générateur de tableau, puis appliquer le segment à toutes en même temps. Vous pouvez appliquer des options des volets d’outils sous forme de lignes, de ventilations ou de colonnes, puis faire pivoter le tableau pour obtenir une vue différente. Après avoir créé le tableau, vous pouvez interagir directement avec le tableau de données qui en résulte afin d’effectuer une analyse plus approfondie. Pour rappel, lorsque vous générez un tableau de données à partir du Générateur de tableau, une requête est exécutée et un nouveau tableau est créé.

## Générateur de tableau {#concept_574FEDC73B244101935D3C86C39DB70F}

Utilisez le Générateur de tableau pour créer un rapport avec n’importe quelle configuration de mesures, de dimensions et de segments. Par exemple, vous pouvez ajouter plusieurs mesures au Générateur de tableau, puis appliquer le segment à toutes en même temps. Vous pouvez appliquer des options des volets d’outils sous forme de lignes, de ventilations ou de colonnes, puis faire pivoter le tableau pour obtenir une vue différente. Après avoir créé le tableau, vous pouvez interagir directement avec le tableau de données qui en résulte afin d’effectuer une analyse plus approfondie. Pour rappel, lorsque vous générez un tableau de données à partir du Générateur de tableau, une requête est exécutée et un nouveau tableau est créé.

Le [!UICONTROL Générateur de tableau] n’est pas disponible pour certains rapports de cheminement tels que [!UICONTROL Analyse de site], [!UICONTROL Abandon], [!UICONTROL Flux] et [!UICONTROL Orientation virtuelle].

## Descriptions du générateur de tableau {#section_4B7B96546B864142AB91DF3996918590}

<table id="table_C11D78E62DEF48A78B50EFB8669817BC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Élément </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Lignes / Ventilations</span> </td> 
   <td colname="col2"> <p>Crée des lignes et des ventilations à partir d’éléments ajoutés. Le premier élément que vous faites glisser dans <span class="wintitle">Lignes / Ventilations</span> devient la colonne gauche du tableau de données ou l’élément parent dans une ventilation. Des ventilations sont créées lors de l’ajout des éléments suivants. </p> <p>Si vous ajoutez, par exemple, les dimensions Pages, puis Villes, le rapport ventile la page par villes. Vous pouvez configurer le nombre de lignes et de ventilations à afficher pour chaque élément à l’aide des menus suivants : </p> 
    <ul id="ul_702F215DFB814398B8F1879EDFEC103F"> 
     <li id="li_95C4DF2B33524C94BBD2E07397393300">  <span class="uicontrol">Afficher</span> et <span class="uicontrol">Ventilation</span> : permettent de spécifier le nombre d’éléments et de ventilations à afficher. </li> 
     <li id="li_D594C7F31A094D1EA1A070B80794E006"> <span class="uicontrol"> Par défaut</span> : utilise les paramètres configurés dans les <span class="wintitle">Propriétés de ventilation</span>. </li> 
    </ul> <p>Vous pouvez également configurer une liste de valeurs fixes afin de ventiler une mesure en fonction de plusieurs autres, par exemple. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Propriétés de ventilation</span> </td> 
   <td colname="col2"> <p><img placement="inline"  src="assets/Settings_Illustrative.png" id="image_C46860621CF94E88AF592B8660F28E57"> </img> </p> <p>Ces propriétés vous permettent de définir des paramètres par défaut concernant le nombre de lignes et de ventilations à afficher, en fonction de l’ordre dans lequel vous ajoutez des éléments. Vous pouvez indiquer le nombre de résultats totaux à afficher par page, ainsi que le nombre de lignes à ventiler. </p> <p>Les paramètres définis dans le <span class="wintitle">Générateur de tableau</span> remplacent les paramètres par défaut des <span class="wintitle">Propriétés de ventilation</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Modifier les éléments</span> </td> 
   <td colname="col2"> <p><img  src="assets/Edit_Buttcon.png" id="image_E44BCC4B0BFF453D8564047E3DA2501A"> </img> </p> <p>Sélectionnez une liste de dimensions pour créer une liste fixe pour les ventilations. Lorsque vous ajoutez des éléments à cette liste, ils deviennent persistants dans un rapport enregistré et ne seront pas réduits lorsque vous ouvrez un rapport enregistré ou planifié. </p> <p>Pour plus d’informations, voir <a href="/help/analyze/ad-hoc-analysis/c-reports-configure.md#task_29BEE0AF09DA4625B9B44BAB77D7C841"  >Ventilation des données tabulaires</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Colonnes</span> </td> 
   <td colname="col2"> <p>Cette fonctionnalité vous permet de créer des colonnes avec des éléments issus de dimensions, de segments et de mesures. Vous pouvez également faire pivoter les colonnes à l’aide de l’icône de flèche, qui pivote sur les axes X et Y. </p> <p> <span class="uicontrol"> Afficher</span> : permet de limiter le nombre de colonnes générées dans le tableau de données. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Résumé</span> </td> 
   <td colname="col2"> <p>Affiche la structure du rapport, de telle sorte que vous sachiez combien de lignes et de colonnes seront créées. Le résumé représente la configuration spécifiée dans les groupes <span class="uicontrol">Lignes / Ventilations</span> et <span class="uicontrol">Colonnes</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Remplacer le tableau</span> </td> 
   <td colname="col2"> <p>Construit (et remplace) le tableau existant, sur la base de votre configuration <span class="wintitle">Générateur de tableau</span>. </p> <p>Remarque : Lorsque vous cliquez sur <span class="uicontrol">Remplacer le tableau</span>, le rapport est exécuté à nouveau et les données de la grille de tableau sont remplacées. Si vous ajoutez des éléments à la grille de tableau, la corrélation entre le tableau et le <span class="wintitle">Générateur de tableau</span> n’est plus valide. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Avertissement </td> 
   <td colname="col2"> <p><img id="image_619E1068C6084D41853DA3DD6B85DFC9"  src="assets/AlertRed_Illustrative.png" placement="inline" /> </p> <p>Indique que la configuration du <span class="wintitle">Générateur de tableau</span> ne renverra aucune donnée ou qu’aucune mesure n’est sélectionnée. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Génération d’un rapport à partir du Générateur de tableau {#task_B04801AC9848485C93DF02E96C9A9902}

Cette procédure décrit l’utilisation du [!UICONTROL Générateur de tableau].

<!-- 

t_table_builder.xml

 -->

1. Pour accéder au [!UICONTROL Générateur de tableau], exécutez un rapport pris en charge, puis cliquez sur **[!UICONTROL Générateur de tableau]**.
1. Faites glisser des éléments (dimensions, mesures, segments) depuis les volets d’outils vers le [!UICONTROL Générateur de tableau].
1. Configurez les éléments sous la forme de lignes, ventilations et colonnes.
1. Cliquez sur **[!UICONTROL Remplacer le tableau]** pour générer le rapport.

   Lorsque vous cliquez sur **[!UICONTROL Remplacer le tableau]**, une nouvelle requête est exécutée et un tableau de données est créé. Les modifications manuelles apportées au tableau détaillé ne sont pas répercutées dans le Générateur de tableau.

