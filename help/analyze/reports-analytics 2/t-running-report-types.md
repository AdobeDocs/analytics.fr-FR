---
description: Procédure d’exécution de différents types de rapports
title: Exécution de différents types de rapports
uuid: f59ab2a1-e916-46e8-bb5b-e6361ba00dda
feature: Reports & Analytics Basics
role: User, Admin
exl-id: 2e8cac1b-d133-4095-b5db-886ce0566b82
source-git-commit: a2e69b5f39de3c964381bb5dd5ecd4d9714e9249
workflow-type: tm+mt
source-wordcount: '1071'
ht-degree: 94%

---

# Exécution de différents types de rapports

{{ra-eol}}

Vous pouvez exécuter de nombreux types de rapports différents dans Analysis Workspace. Voici quelques exemples.

Pour obtenir la liste complète des types de rapports prédéfinis disponibles, reportez-vous à la section [Utilisation de rapports prédéfinis](/help/analyze/analysis-workspace/reports/use-reports.md)

<!-- How do you do a Ranked Report in Workspace?

## Run a ranked report {#task_C570BA4A213F4F2EB7B30E012934BE7D}

In a ranked report, the table shows the rankings of the report pages in relation to the metric, according to number or percentage. Ranked reports can display multiple metrics in a report.

1. Generate a report, such as a [!UICONTROL Pages Report] ( [!UICONTROL **Workspace**] > **[!UICONTROL Engagement]** > **[!UICONTROL Pages]**).
1. In the report header, click **[!UICONTROL Ranked.]**
1. To rank the report, click a column heading in the table.

   Ranked reports can have up to 200 items listed in the table (such as products, categories, web pages, and so on) and ten metrics (revenue, orders, views, and so on).

-->

<!-- Can you do a Trended report? 

## Run a trended report {#task_F03B4E760B9E4EA29FC3F654E6316887}

Trended reports display metrics over time. You use this report type when you want to see how a segment performs from one time period to the next.

Most Conversion and Traffic reports have a Trended view available. Using the [!UICONTROL Calendar], you can show improvement for any time period breakdowns, including days of a month, weeks of a year, weeks of a quarter, months of a year, and so on. Trended reports show trends for a single metric (revenue, orders, views, and so on) for up to five items (such as products, categories, web pages, and so on).

**To run a trended report** 

1. Run a conversion or traffic report, such as **[!UICONTROL Reports]** > **[!UICONTROL Site Content]** > **[!UICONTROL Pages]**.
1. Under **[!UICONTROL Report Type]**, click **[!UICONTROL Trended.]**

-->

## Exécution d’un rapport sur les abandons {#task_8FD97C8260464F9DA731A93DB8F80184}

Le [!UICONTROL rapport sur les abandons] indique le nombre de visiteurs qui ont consulté une séquence de pages prédéfinie. Il indique également les taux de conversions et d’abandons entre deux étapes.

Découvrez le nouveau panneau [Analyse des abandons](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/fallout/fallout-flow.html?lang=fr) dans Analysis Workspace.

1. Dans [!UICONTROL Adobe Analytics], cliquez sur **[!UICONTROL Rapports]** > **[!UICONTROL Chemins]** > **[!UICONTROL Pages]** > **[!UICONTROL Abandon]**.
1. Sur la page du [!UICONTROL rapport sur les abandons], cliquez sur le bouton de **[!UICONTROL lancement du Report Builder d’abandons]**.

1. Sur la page [!UICONTROL Définir les points de contrôle], spécifiez les points de contrôle à utiliser pour votre rapport.
1. Cliquez sur **[!UICONTROL Exécuter le rapport]**.

## Exécution d’un rapport de flux de page {#task_133E8B87C3F04DA0A42D10CBA499305B}

Les rapports de flux de page indiquent l’ordre dans lequel les visiteurs accèdent aux pages et parcourent votre site.

Par exemple, cliquez sur **[!UICONTROL Workspace]** > **[!UICONTROL Rapports]** > **[!UICONTROL Engagement]** > **[!UICONTROL Flux de page suivante et précédente]**.

## Exécution d’un rapport Canal marketing {#task_64ADED5CC75248319E06E3E029B47F78}

Ce rapport fournit un aperçu de la première et de la dernière allocation de canal, avec des mesures de rapport standard telles que les recettes, les commandes et les coûts. Grâce à ces rapports, vous pouvez analyser combien de recettes sont générées par chaque canal.

Consultez l’aide sur le [canal marketing](/help/components/c-marketing-channels/analyze-mc.md) pour en savoir plus.

## Exécution d’un rapport Détection des anomalies {#task_4808C96327354D789C075823F5C3A049}

Vous pouvez exécuter [Détection des anomalies et analyse des contributions](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/virtual-analyst/anomaly-detection/anomaly-detection.html?lang=fr) uniquement dans Analysis Workspace.

## Exécution d’un rapport en temps réel {#task_5D25929C918E40B18965222FA94176B0}

Décrit comment afficher et interpréter les rapports en temps réel.

**[!UICONTROL Rapports > Mesures du site > Temps réel]**.

La création de rapports en temps réel offre deux rapports principaux : un rapport d’aperçu et un rapport détaillé. Ils sont chacun composés de plusieurs mini-rapports.

Voir [Rapports en temps réel - Aperçu](/help/components/c-real-time-reporting/realtime.md) pour plus d’informations.

1. Étudiez le rapport **[!UICONTROL Aperçu]** et ses composants :  ![](assets/rtr_overview_report.png)

   <table id="choicetable_8586BECF55E843B2B5CD41205567EA32"> 
   <thead class="chhead sthead"> 
   <th class="choptionhd"> Composant de l’interface utilisateur </th> 
   <th class="chdeschd"> Description </th> 
   </thead> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Sélectionner une suite de rapports</strong></td> 
   <td class="chdesc stentry"> Affiche la suite de rapports couverte par ce rapport en temps réel. Pour modifier la suite de rapports, voir <a href="https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/real-time-reports/t-realtime-admin.html?lang=fr"  >Configuration de rapports en temps réel </a>. </td> 
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
   <td class="chdesc stentry"> Les données de la ligne de tendance bleue affichent le trafic total pour l’ensemble du site. L’axe des X utilise des libellés littéraux (il y a 15 minutes, il y a 10 minutes) sauf pour la valeur actuelle qui s’affiche sous la forme d’une expression en temps réel. </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Petit rapport Total du site</strong></td> 
   <td class="chdesc stentry"> Présente un nombre (total du site) pour la mesure sélectionnée du rapport en temps réel au cours des N dernières minutes. « N » est configurable par l’intermédiaire du sélecteur de période. <p>La couleur et la direction de la flèche sont basées sur l’algorithme suivant : 
      <ul id="ul_9F40CEA33798467393CB1266BB36D500"> 
      <li id="li_CCD01A44F912487DA5681EA50113643C">Gain significatif (flèche vers le haut) : &gt; 100 % </li> 
      <li id="li_7402491A9A614851B7F2AE0C77BD9A97">Gain (flèche vers le haut et la droite) : entre 5 et 100 % </li> 
      <li id="li_BCA79C08B5714D4B9315068112C66107"> Neutre (flèche vers la droite) : entre 5 % et -5 % </li> 
      <li id="li_234ECBD7D83A4AE680E4A70BF288681F"> Perte (flèche vers le bas et la droite) : entre -5 % et -100 % </li> 
      <li id="li_10C5EA8803604C1CA714D3DB27478B31"> Perte significative (flèche vers le bas) : &lt; -100 % </li> 
      </ul> </p> <p>Si le total du site est signalé en « instances », ces instances reflètent la dimension du mini-rapport principal. Si un nom spécifique d’instance existe (par exemple « Pages vues »), le total du site signale ce nom. </p> </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Petit rapport principal</strong></td> 
   <td class="chdesc stentry"> Rapport pour la dimension principale du rapport en temps réel et pour ses mesures. Présente une ligne de tendance pour cet élément correspondant à la période sélectionnée. Le total des mesures représente la somme pour la ligne de tendance complète. La flèche indique si l’élément est en situation de forts gains, de gains, neutre, de pertes, de fortes pertes. </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Boîte de dialogue de recherche</strong></td> 
   <td class="chdesc stentry"> La recherche impacte tous les mini-rapports. Elle se poursuit lorsque vous affichez le rapport. </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Tri par... Le plus populaire/Gagnants/Perdants</strong></td> 
   <td class="chdesc stentry"> Vous pouvez basculer pour trier par <span class="uicontrol">Le plus populaire</span>(par défaut), <span class="uicontrol">Gagnants</span> (dimensions présentant les plus fortes croissances) et <span class="uicontrol">Perdants</span> (dimensions étant sur une trajectoire descendante). <p>La formule utilisée pour déterminer les gagnants ou les perdants est la suivante : le rapport en temps réel recherche l’échantillon le plus ancien et l’avant-dernier et effectue un simple calcul « modification en % ». Ainsi, si « 15 dernières minutes » est sélectionné et n représente la minute actuelle, n-1 est comparé à n-15. Le rapport en temps réel n’effectue pas, pour le moment, de pondération. La minute en cours est ignorée, car elle n’est pas terminée et produirait sans doute une modification en % erronée. </p> <p>Cette formule est cohérente pour toutes les mesures utilisées dans le rapport en temps réel. </p> </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Petit rapport secondaire 1</strong></td> 
   <td class="chdesc stentry"> Présente des rapports en temps réel pour la deuxième dimension du rapport configuré et pour sa mesure. <p>Le mini-rapport secondaire 1 affiche les 4 catégories supérieures ; la cinquième est une agrégation de toutes les valeurs restantes. Pour chaque catégorie, l’affichage brut total de la catégorie est fourni. En outre, le total de toutes les catégories s’affiche au centre. </p> <p> Le survol d’une section avec le curseur met en surbrillance la catégorie associée et affiche la ligne de tendance de la catégorie sous le beignet. </p> <p> Le survol d’un élément de ligne avec le curseur met en surbrillance ce dernier avec la section associée et affiche la ligne de tendance de la catégorie sous le beignet. </p> </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Petit rapport secondaire 2</strong></td> 
   <td class="chdesc stentry"> Présente des rapports en temps réel pour la troisième dimension du rapport configuré et pour sa mesure. Le survol du libellé de la ligne avec le curseur fait glisser le libellé vers la droite et révèle une ligne de tendance pour l’élément survolé. </td> 
   </tr> 
   </table>

2. Cliquez sur un élément de liste dans le petit rapport principal pour lancer la vue **[!UICONTROL Détails]** pour cet élément de liste :  ![](assets/rtr_detail_report.png)

   | **Mini-rapport Tendance des éléments** | Présente la ligne de tendance de l’élément qui a été sélectionné dans le rapport Aperçu pendant les N dernières minutes. Vous pouvez configurer N par l’intermédiaire du sélecteur de période. |
   |---|---|
   | **Mini-rapport Total des éléments** | Présente un nombre de mesures total pour l’élément qui a été sélectionné dans le rapport Aperçu au cours des N dernières minutes. Vous pouvez configurer N par l’intermédiaire du sélecteur de période. |
   | **Mini-rapport secondaire corrélé 1** | Ce mini-rapport est très similaire au mini-rapport secondaire 1. La seule différence est la source de données utilisée pour alimenter ce rapport : dans cet exemple, il montre la corrélation (ou répartition) entre une page spécifique (celle que vous avez sélectionnée dans le mini-rapport principal du rapport Aperçu) et les instances affichées. |
   | **Mini-rapport secondaire corrélé 2** | Ce mini-rapport est très similaire au mini-rapport secondaire 2. La seule différence est la source de données utilisée pour alimenter ce rapport : dans cet exemple, il montre la corrélation (ou répartition) entre une page spécifique (celle que vous avez sélectionnée dans le mini-rapport principal du rapport Aperçu) et la dimension de langue. |
