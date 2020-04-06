---
description: Procédure d’exécution de différents types de rapports
title: Exécution de différents types de rapports
topic: Reports,Reports and analytics
uuid: f59ab2a1-e916-46e8-bb5b-e6361ba00dda
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Exécution de différents types de rapports

Procédure d’exécution de différents types de rapports


## Exécution d’un rapport de classement {#task_C570BA4A213F4F2EB7B30E012934BE7D}

Dans un rapport avec classement, le tableau présente le classement des pages du rapport par rapport à la mesure, en fonction du nombre ou du pourcentage. Ces rapports peuvent afficher plusieurs mesures.

<!-- 

t_reports_ranked.xml

 -->

1. Générez un rapport, par exemple [!UICONTROL Pages Report] ( **[!UICONTROL Reports]** > **[!UICONTROL Site Content]** > **[!UICONTROL Pages]**).
1. In the report header, click **[!UICONTROL Ranked.]**
1. Pour classer le rapport, cliquez sur un en-tête de colonne dans le tableau.

   Le tableau d’un rapport de classement peut comprendre jusqu’à 200 éléments (par exemple, produits, catégories, pages web, etc.) et dix mesures (recettes, commandes, vues, etc.).

## Exécution d’un rapport de tendances {#task_F03B4E760B9E4EA29FC3F654E6316887}

Les rapports de tendances affichent les mesures au fil du temps. Vous utilisez ce type de rapport lorsque vous souhaitez voir comment un segment fonctionne d’une période à l’autre.

<!-- 

t_reports_trended.xml

 -->

La plupart des rapports Conversion et Trafic disposent d’un  de tendances. Grâce à [!UICONTROL Calendar], vous pouvez afficher des améliorations pour les ventilations de toutes les périodes, y compris les jours d’un mois, les semaines d’une année, les semaines d’un trimestre, les mois d’une année, etc. Les rapports de tendances indiquent les tendances pour une mesure unique (recettes, commandes, , etc.) pour cinq éléments au maximum (produits,, pages Web, etc.).

**Pour exécuter un rapport de tendances**

1. Exécutez un rapport de conversion ou de trafic, tel que **[!UICONTROL Reports]** > **[!UICONTROL Site Content]** > **[!UICONTROL Pages]**.
1. Under **[!UICONTROL Report Type]**, click **[!UICONTROL Trended.]**

## Exécution d’un rapport Entonnoir de conversion {#task_B926A74AA6A641138C2986C1635120CB}

Les rapports Entonnoir de conversion affichent le pourcentage de qui passent par un ensemble de  afin d’effectuer l’action souhaitée. Vous pouvez, par exemple, voir le nombre de qui sont passés de la visite de votre page Web à l’ajout d’éléments dans un panier, puis à l’achat d’un élément. Ce rapport montre aussi le nombre de personnes qui sont tombées en chemin.

<!-- 

t_reports_conversion_funnel.xml

 -->

Pour exécuter ce rapport, sélectionnez un rapport, tel qu’un rapport Pages ( **[!UICONTROL Reports]** > **[!UICONTROL Campaigns]** > **[!UICONTROL Tracking Code]** > **[!UICONTROL Campaign Conversion Funnel]**).

Pour obtenir une description, reportez-vous à la section [Rapports de conversion](https://marketing.adobe.com/resources/help/fr_FR/reference/reports_conversion.html).

## Exécution d’un rapport sur les abandons {#task_8FD97C8260464F9DA731A93DB8F80184}

Le [!UICONTROL Fallout Report] montre le nombre de qui ont consulté une séquence de pages prédéfinie. Il montre également les taux de conversion et d’abandon entre chaque étape.

<!-- 

t_reports_fallout.xml

 -->

Découvrez le nouveau panneau de  d&#39; [abandons](https://marketing.adobe.com/resources/help/fr_FR/analytics/analysis-workspace/fallout_flow.html) dans  Espace de travail de de !

1. Dans [!UICONTROL Adobe Analytics], cliquez sur **[!UICONTROL Reports]** > **[!UICONTROL Paths]** > **[!UICONTROL Pages]** > **[!UICONTROL Fallout]**.
1. Sur la [!UICONTROL Fallout Report] page, cliquez sur **[!UICONTROL Launch the Fallout Report Builder]**.

   ![Résultat de l’étape](assets/fallout_add_items.png)

1. On the [!UICONTROL Define Checkpoints] page, specify the checkpoints that you want to use for the report.
1. Cliquez sur **[!UICONTROL Run Report]**.

   ![Résultat de l’étape](assets/fallout_report.png)

>[!MORELIKETHIS]
>
>* [Description du rapport sur les abandons](https://docs.adobe.com/content/help/fr-FR/analytics/components/variables/dimensions-reports/reports-fallout.translate.html)


## Exécution d’un rapport de flux de page {#task_133E8B87C3F04DA0A42D10CBA499305B}

Les rapports de flux de page indiquent l’ordre dans lequel vos accèdent aux pages et naviguent sur votre site. Ce rapport permet de répondre à

Découvrez la nouvelle visualisation [Flux](https://marketing.adobe.com/resources/help/fr_FR/analytics/analysis-workspace/flow.html) dans   Espace de travail !

Exécutez un rapport [Chemins](https://marketing.adobe.com/resources/help/fr_FR/reference/reports_paths.html) .

Par exemple, cliquez sur **[!UICONTROL Reports]** > **[!UICONTROL Paths]** > **[!UICONTROL Pages]** > **[!UICONTROL Next Page Flow]**.

![](assets/page_flow.png)

Vous lisez ce rapport de gauche à droite, en commençant par la page sélectionnée. Les pages qui ont été consultées après la page sélectionnée sont illustrées comme une branche qui s’étend vers la droite.

Le pourcentage d’affichage de chaque page suivante s’affiche en regard du nom de la page. La largeur de la ligne reliée à chaque page suivante représente ce pourcentage relatif.

**[!UICONTROL Path Views]**: Indique le nombre de fois où une page a été consultée, lorsqu’elle est restreinte aux chemins affichés.

Par exemple, la page Règles relatives aux informations à caractère personnel peut avoir 10 000  de page au total, mais seulement 500 de ces de page  ont eu lieu immédiatement après la . Ainsi, le terme de chemin est utilisé.

Le pourcentage relatif est représenté par la largeur relative de la ligne. Par défaut, ce rapport affiche cinq branches de deuxième niveau et cinq branches de troisième niveau. Vous pouvez augmenter le nombre de branches pour  jusqu’à dix branches de deuxième niveau et cinq branches de troisième niveau. Cela augmente la hauteur du rapport et nécessite probablement un défilement pour du graphique entier.

## Exécution d’un rapport Entonnoir {#task_2BBF6FACD48F479E8B2EE458919941CB}

Vous pouvez sélectionner des  de réussite et les ajouter à un [!UICONTROL Purchase Conversion Funnel] rapport ou à un [!UICONTROL Product Conversion Funnel] rapport.

<!-- 

t_reports_funnel.xml

 -->

1. Cliquez sur **[!UICONTROL Reports]** > **[!UICONTROL Products]** > Entonnoir [de conversion de](https://marketing.adobe.com/resources/help/fr_FR/reference/reports_conversion_funnel.html)produits.

## Exécution d’un rapport Canal marketing {#task_64ADED5CC75248319E06E3E029B47F78}

Le de  marketing  fournit un rapport d’ensemble sur l’attribution des  Première touche et Dernière touche, avec des mesures de standard telles que les recettes, les commandes et les coûts. Ces rapports vous permettent d’analyser les recettes générées par chaque.

<!-- 

t_reports_marketing_channel.xml

 -->

See the [Marketing Channel](https://marketing.adobe.com/resources/help/fr_FR/mchannel/index.html) help system for more information.

## Exécution d’un rapport Détection des anomalies {#task_4808C96327354D789C075823F5C3A049}

Décrit comment interpréter les graphiques de mesures synthétiques et individuels de la détection des anomalies.

<!-- 

t_anomaly_view.xml

 -->

Découvrez les nouvelles fonctions de [détection des anomalies et d’analyse des contributions](https://marketing.adobe.com/resources/help/fr_FR/analytics/analysis-workspace/anomaly_detection.html) d’Analysis Workspace.

**[!UICONTROL Reports]** > **[!UICONTROL Site Metrics]** > **[!UICONTROL Anomaly Detection]** .

>[!NOTE] Vous pouvez également exécuter la détection des anomalies directement depuis les projets Analysis Workspace. [Plus...](https://marketing.adobe.com/resources/help/fr_FR/analytics/analysis-workspace/anomaly_detection.html)

Pour plus d&#39;informations sur la configuration de la détection des anomalies, consultez le Guide [de](https://marketing.adobe.com/resources/help/fr_FR/sc/user/index.html#Setting_up_Anomaly_Detection)référence.

La détection des anomalies présente deux types de graphiques : Graphique récapitulatif et graphiques de mesures individuels. Les graphiques de mesures individuels ne s’affichent que si au moins une anomalie a été détectée pour cette mesure.

<table id="table_88163CD8FC164342855D90D01F9C581A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Type de graphique </p> </th> 
   <th colname="col2" class="entry"> <p>Ce que fait </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Graphique récapitulatif </p> <p><img placement="break"  src="assets/ad_summary_chart.png" width="570px" id="image_1CD4C4770BAA43C4AD7CBB824AD41338" /> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_D26DA3024CD7468291369F549557B28A"> 
      <li id="li_1C22B6E02FFB479FB71EFAD89EB37A4E">Chaque zone représente une anomalie, suivie par jour, qui correspond à une mesure ci-dessous. </li> 
      <li id="li_8FC587D3FF4E452D83263CC7A10B6675">Le vert indique les anomalies au-dessus de la ligne de tendance, le bleu au-dessous de la ligne de tendance. </li> 
      <li id="li_25135AB691BF443599AF2A3A60E2E71A">Indique la force de l’anomalie : Plus l’anomalie est grande, plus la couleur du point de données est foncée et plus éloignée de la ligne de tendance. </li> 
      <li id="li_0C42AFA8897D420D8AB1A5D0F65B3B3A">Le fait de cliquer sur des anomalies individuelles permet d’afficher le graphique de mesures individuel de cette anomalie (sous le graphique de synthèse) en haut. </li> 
      <li id="li_85C0F426952547B5A75D6BD31DE19CA5">Les valeurs de pourcentage d’écart (à gauche du graphique) sont calculées comme suit : 
       <ul id="ul_BEC0A88BFFAC4CF78BC9885FEB749694"> 
        <li id="li_1BAB2F50482745B69937DFAF1E09982E">Si les limites supérieures et la valeur attendue sont identiques, le % d’écart est de 100 %. </li> 
        <li id="li_CA48064F5788448C8646CCE196161237">Sinon, le % d’écart est égal à : ((valeur réelle - valeur limite supérieure) / (valeur limite supérieure - valeur attendue)) * 100 </li> 
        <li id="li_4090357A0D214BC7B1C3DE0615875554">Si les limites inférieures et la valeur attendue sont identiques, le % d’écart est de -100 % </li> 
        <li id="li_EF694E1A4E874ECD94E1E8F7302E494F">Sinon, le % d’écart est ((valeur réelle inférieure - valeur réelle) / (valeur attendue - valeur limite inférieure)) * -100 </li> 
       </ul> </li> 
      <li id="li_5C05EF7023484CC993E96D63E842B65C">Cliquez sur <span class="uicontrol">Afficher Segments</span> pour afficher le rail des segments à partir duquel vous pouvez appliquer des segments à un rapport de détection des anomalies. <a href="https://marketing.adobe.com/resources/help/fr_FR/analytics/segment/"  > Plus d’informations</a> sur la segmentation. </li> 
      <li id="li_1B41CABF13D1407886C68EE3BC201E60">Cliquez sur <span class="uicontrol">Modifier des mesures</span> pour sélectionner et désélectionner des mesures pour lesquelles vous souhaitez détecter des anomalies. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Graphique de mesures individuel </p> <p><img placement="break"  src="assets/metric_report.png" width="570px" id="image_5BBECFD91CF14478AA4761E6256BBCB9" /> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_739C5687013743A29B63089FDA763F45"> 
      <li id="li_456A0BDA4D4E46CE9CC1C3DBAA1E2220">Affiche les points de données anormaux pour les mesures de tendances individuelles (y compris les mesures calculées) sous forme de points. </li> 
      <li id="li_89FD847C65F04F48BCA7CD38D0EC51CD">Affiche la plus récente anomalie en haut et classe ensuite par nombre d’anomalies. </li> 
      <li id="li_98B97A9706DE4455B8D8850904CBDE03">Affiche une ligne pleine pour indiquer les données réelles actuellement collectées. Ceci est comparé à la prévision et à la marge d’erreur pour déterminer si les points de données sont anormaux. </li> 
      <li id="li_0EEA38DDDC344BF3879430E67D74EB72">Affiche une ligne en pointillés qui représente une prévision basée sur des données historiques (c.-à-d. la période de formation). </li> 
      <li id="li_035BD2725D004AEDB630BF8DFF4DA4F3">Affiche les intervalles/limites de confiance de 95 % supérieure et inférieure dans un gris foncé. </li> 
      <li id="li_021A3D1F2EDB4319B9B39620EF1C038A">Vous permet de réduire et de développer des rapports individuels en cliquant sur les flèches vers le haut ou vers le bas du en regard du nom de la mesure. </li> 
      <li id="li_722E4B9FC21047AC96D7B143197E293D">Modifie l’ordre d’affichage des graphiques de mesures en réagissant aux analyses détaillées dans le rapport d’aperçu (voir ci-dessus). </li> 
      <li id="li_A2441169B185475AA68A64F81E6E40B8">Permet de filtrer les graphiques à l’aide de termes de recherche, tels que "page", pour toutes les mesures liées aux pages. </li> 
      <li id="li_F1BBBFCA8E2A43C29658E4FCAA36C904">Vous permet d’afficher toutes les mesures que vous avez définies ou uniquement celles qui présentent des anomalies. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Configuration de la détection des anomalies {#task_AF347B34F56E44A6AE70E019B6EB2F08}

Cette section décrit la procédure à suivre pour sélectionner des suites de rapports, des mesures et des périodes de formation/ pour la détection des anomalies.

<!-- 

t_anomaly_config.xml

 -->

Vous configurez la détection des anomalies indépendamment pour chaque suite de rapports.

1. Accédez à **[!UICONTROL Analytics > Reports > Site Metrics > Anomaly Detection]** .
1. Sélectionnez la suite de rapports pour laquelle vous souhaitez suivre quotidiennement la détection des anomalies. Pour afficher une liste des suites de rapports, cliquez sur le menu déroulant du sélecteur de suite de rapports.
1. To select the metrics and/or define filtered metrics, click **[!UICONTROL Edit Metrics]** at the top right of the screen:  ![](assets/metrics_icon.png).

   Vous pouvez sélectionner des mesures dans la liste (y compris des mesures calculées) de toutes les mesures ou dans une liste de mesures suivies. Vous pouvez également filtrer des termes spécifiques afin de préciser les résultats. 1. Once the report has been generated, define the **[!UICONTROL Training Period]** and the **[!UICONTROL View Period]** for anomaly detection. (Considérez la période de formation en tant que « période d’apprentissage » pour l’algorithme.)

   ![](assets/view_training_periods.png)

   Gardez les éléments suivants à l’esprit :

* La période de formation se termine juste avant la  de la période de .
* La valeur par défaut des deux périodes est de 30 jours et vous pouvez les étendre à 60 ou 90 jours.
* L’extension de la période de formation place vos données dans un contexte plus large et peut réduire la taille d’une anomalie.

   Le rapport des mesures de détection des anomalies est actualisé chaque fois que vous modifiez un paramètre.
1. (Optional) Apply segments to the report by clicking **[!UICONTROL Show Segments]** and selecting one or more existing segments or creating a new segment and applying it.

   ![](assets/ad_top_menu.png)

   Voir le [guide de segmentation d’Analytics](https://marketing.adobe.com/resources/help/fr_FR/analytics/segment/) pour en savoir plus sur la création et la gestion des segments. 1. (Facultatif) Définissez le rapport comme favori ou signet.
1. (Facultatif) Modifiez la date de fin de la période d’affichage. La valeur par défaut est « hier ». 
1. Vous pouvez à présent commencer à interpréter le rapport. [Affichage des graphiques de détection des anomalies](/help/analyze/reports-analytics/t-running-report-types.md#task_4808C96327354D789C075823F5C3A049).

## Exécution d’un rapport en temps réel {#task_5D25929C918E40B18965222FA94176B0}

Décrit comment afficher et interpréter les rapports en temps réel.

<!-- 

reports_realtime.xml

 -->

**[!UICONTROL Reports > Site Metrics > Real-Time]** .

Le en temps réel   deux rapports principaux : un rapport d’aperçu et un rapport détaillé. Ils se composent chacun d’un certain nombre de petits rapports.

Pour plus d’informations sur la configuration des rapports en temps réel, consultez le Guide [de référence d’](https://marketing.adobe.com/resources/help/fr_FR/reference/index.html#RealTime_Reports_Configuration)Analytics.

1. Take a look at the **[!UICONTROL Overview]** report and its components:  ![](assets/rtr_overview_report.png)

   <table id="choicetable_8586BECF55E843B2B5CD41205567EA32"> 
   <thead class="chhead sthead"> 
   <th class="choptionhd"> Composant d’interface </th> 
   <th class="chdeschd"> Description </th> 
   </thead> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Sélectionner une suite de rapports</strong></td> 
   <td class="chdesc stentry"> Affiche la suite de rapports couverte par ce rapport en temps réel. Pour modifier la suite de rapports, voir <a href="https://marketing.adobe.com/resources/help/fr_FR/reference/t_realtime_admin.html"  >Configuration de rapports en temps réel </a>. </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Basculer entre les rapports</strong></td> 
   <td class="chdesc stentry"> Permet de basculer entre les rapports que vous avez configurés (3 au maximum). </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Sélectionner une période</strong></td> 
   <td class="chdesc stentry"> Permet de choisir la période globale à utiliser par tous les petits rapports du rapport. </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Configurer les rapports</strong></td> 
   <td class="chdesc stentry"> Ce lien d’icône d’engrenage n’est visible que si vous êtes doté des droits d’administration. Si vous cliquez sur ce lien, vous accédez au gestionnaire des suites de rapports sous <span class="ignoretag"><span class="uicontrol">Outils d’administration</span> &gt; <span class="uicontrol">Suites de rapports</span> &gt; <span class="uicontrol">Modifier paramètres</span> &gt; <span class="uicontrol">Temps réel </span> </span>. </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Affichage plein écran</strong></td> 
   <td class="chdesc stentry"> L’icône d’affichage plein écran n’est visible que si votre écran comporte un format spécifique (16:9 ou 16:10) ET si votre navigateur le prend en charge. Notez que vous ne pouvez pas interagir avec l’écran lorsqu’il est en mode plein écran (appuyez sur <span class="uicontrol">Échap</span> pour quitter). Le mode plein écran n’a pas de délai d’expiration. </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Mini-rapport Trafic du site</strong></td> 
   <td class="chdesc stentry"> Les données de ligne de tendance bleue indiquent le total du trafic pour l’ensemble du site. L’axe X utilise des libellés littéraux (il y a 15 minutes, il y a 10 minutes), à l’exception de la valeur actuelle, qui s’affiche sous la forme d’un   en temps réel. </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Petit rapport Total du site</strong></td> 
   <td class="chdesc stentry"> Présente le nombre total du site pour la mesure sélectionnée du rapport en temps réel au cours des N dernières minutes. "N" est configurable par le biais du sélecteur de période. <p>La couleur et la direction de la flèche sont basées sur l’algorithme suivant : 
      <ul id="ul_9F40CEA33798467393CB1266BB36D500"> 
      <li id="li_CCD01A44F912487DA5681EA50113643C">Gain significatif (flèche vers le haut) : &gt; 100 % </li> 
      <li id="li_7402491A9A614851B7F2AE0C77BD9A97">Gain (flèche vers le haut et la droite) : entre 5 % et 100 % </li> 
      <li id="li_BCA79C08B5714D4B9315068112C66107"> Plat (flèche droite) : entre 5 % et -5 % </li> 
      <li id="li_234ECBD7D83A4AE680E4A70BF288681F"> Perte (flèche vers le bas à droite) : entre -5 % et -100 % </li> 
      <li id="li_10C5EA8803604C1CA714D3DB27478B31"> Perte significative (flèche vers le bas) : &lt; -100 % </li> 
      </ul> </p> <p>Si le total du site est rapporté dans "instances", ces instances reflètent la dimension dans le mini-rapport principal. S’il existe un nom spécifique à une instance (tel que " de page", par exemple), le total du site indique ce nom. </p> </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Petit rapport principal</strong></td> 
   <td class="chdesc stentry"> Rapport pour la dimension principale du rapport en temps réel et pour sa mesure. Présente une ligne de tendance pour cet élément pour la période sélectionnée. Le total de la mesure représente la somme de la ligne de tendance complète. La flèche indique si l’élément est en train de gagner, de gagner, de stagner, de perdre ou de perdre fortement. </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Boîte de dialogue de recherche</strong></td> 
   <td class="chdesc stentry"> La recherche a un impact sur tous les petits rapports. La recherche persiste lorsque vous  le rapport. </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Tri par... Le plus populaire/Gagnants/Perdants</strong></td> 
   <td class="chdesc stentry"> Vous pouvez basculer pour trier par <span class="uicontrol">Le plus populaire</span>(par défaut), <span class="uicontrol">Gagnants</span> (dimensions présentant les plus fortes croissances) et <span class="uicontrol">Perdants</span> (dimensions étant sur une trajectoire descendante). <p>La formule utilisée pour déterminer les gagnants ou les perdants est la suivante : le rapport en temps réel recherche l’échantillon le plus ancien et l’avant-dernier et effectue un simple calcul « modification en % ». Ainsi, si « 15 dernières minutes » est sélectionné et n représente la minute actuelle, n-1 est comparé à n-15. Actuellement, la pondération n’est pas effectuée en temps réel. La minute actuelle est ignorée, car elle n’est pas terminée et produirait probablement une modification de % erronée. </p> <p>Cette formule est cohérente pour toutes les mesures utilisées dans le rapport en temps réel. </p> </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Petit rapport secondaire 1</strong></td> 
   <td class="chdesc stentry"> Présente des rapports en temps réel pour la deuxième dimension du rapport configuré et pour la mesure. <p>Le mini-rapport secondaire 1 affiche les 4 principaux  de ; la cinquième est une agrégation de toutes les valeurs restantes. Pour chaque  de, le brut total de cette  est fourni. En outre, le total de tous les  de s’affiche au centre. </p> <p> Le survol d’une section met en surbrillance le  de associé et affiche la ligne de tendance du  sous le beignet. </p> <p> Le survol d’un élément de ligne met en surbrillance l’élément de ligne plus la section associée et affiche la ligne de tendance  sous le beignet. </p> </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Petit rapport secondaire 2</strong></td> 
   <td class="chdesc stentry"> Présente des rapports en temps réel pour la troisième dimension du rapport configuré et pour la mesure. Le survol du libellé de l’élément fait glisser le libellé vers la droite et révèle une ligne de tendance pour l’élément survolé. </td> 
   </tr> 
   </table>

1. Click a list item in the Primary Reportlet to launch the **[!UICONTROL Details]** view for that list item:  ![](assets/rtr_detail_report.png)

   | **Petit rapport Tendance des éléments** | Présente la ligne de tendance de l’élément sélectionné dans le rapport Aperçu au cours des N dernières minutes. N est configurable par le biais du sélecteur de période. |
   |---|---|
   | **Petit rapport Total élément** | Présente un nombre total de mesures pour l’élément sélectionné dans le rapport Aperçu au cours des N dernières minutes. N est configurable par le biais du sélecteur de période. |
   | **Mini-rapport secondaire corrélé 1** | Ce mini-rapport est très similaire au mini-rapport secondaire 1. La seule différence réside dans la source de données utilisée pour remplir ce rapport : dans cet exemple, il montre la corrélation (ou ventilation) entre une page spécifique (celle que vous avez sélectionnée dans le mini-rapport principal du rapport Aperçu) et les instances affichées. |
   | **Mini-rapport secondaire corrélé 2** | Ce petit rapport est très similaire au petit rapport secondaire 2. La seule différence réside dans la source de données utilisée pour remplir ce rapport : dans cet exemple, il montre la corrélation (ou ventilation) entre une page spécifique (celle que vous avez sélectionnée dans le mini-rapport principal du rapport Aperçu) et la dimension de langue. |
