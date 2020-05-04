---
description: Une fois un rapport exécuté, vous pouvez le personnaliser de manière à afficher et à analyser les données en fonction de vos besoins. Vous pouvez filtrer les données du rapport, modifier la manière dont elles sont présentées graphiquement, modifier leur granularité, etc.
title: Personnalisation des rapports - Aperçu
topic: Reports and analytics
uuid: 37d221b7-50fd-4425-b2ba-f40911b72a2f
translation-type: tm+mt
source-git-commit: ad9a7729924636055e456d0fd7ab928be227034d

---


# Personnalisation des rapports - Aperçu

Une fois un rapport exécuté, vous pouvez le personnaliser de manière à afficher et à analyser les données en fonction de vos besoins. Vous pouvez filtrer les données du rapport, modifier la manière dont elles sont présentées graphiquement, modifier leur granularité, etc.

## Création d’un rapport personnalisé {#task_BA6EACA3039C40AEA5605E1D8C76E646}

Cette section décrit la procédure à suivre pour enregistrer la configuration actuelle d’un rapport en tant que nouveau rapport personnalisé que tous les utilisateurs peuvent afficher.

<!-- 

t_reports_custom.xml

 -->

Seuls les administrateurs peuvent créer un rapport personnalisé. Lorsque vous créez un rapport personnalisé, il est ajouté au menu de rapport principal à côté du rapport sur lequel il repose.

**Pour créer un rapport personnalisé**

1. Exécutez un rapport et configurez-le selon vos besoins.
1. Cliquez sur **[!UICONTROL More]** > **[!UICONTROL Create Custom Report]**.
1. Name the report, then click **[!UICONTROL Save.]**

   Vérifiez que ce nom n’existe pas déjà.

>[!MORELIKETHIS]
>
>* [Personnalisation des menus](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/customize-menus.html)


## Sélection d’une date ou d’une période {#task_9BEF7D4D839A4748B76E8500D1406C34}

Cette section décrit la procédure à suivre pour choisir les périodes des données de rapport.

<!-- 

t_reports_select_date.xml

 -->

Vous pouvez sélectionner des jours, semaines, mois ou années spécifiques. Vous pouvez également exécuter des rapports de comparaison.

Lorsque vous ouvrez un tableau de bord contenant des mini-rapports avec différentes plages de dates, vous pouvez en définir une nouvelle dans le calendrier. Les modifications s’appliquent à tous les mini-rapports du tableau de bord.

**Pour sélectionner une plage de dates**

1. Exécutez un rapport.
1. Cliquez sur l’icône du calendrier en haut à droite.
1. Sélectionnez une date.

   Vous pouvez :

   * Afficher les jours, les mois ou les années (jusqu’à trois).
   * Faire glisser le curseur sur les dates afin de sélectionner une plage.
   * Entrer les dates manuellement.
   * Cliquer sur le nom d’un mois afin de sélectionner ce dernier.
   * Cliquez sur **[!UICONTROL Select Preset]** pour sélectionner une date prédéfinie.
   * Comparaison de dates.

1. Cliquez sur **[!UICONTROL Run Report]**.

## Comparaison de dates {#task_95155C3700774B709F5FB81AE96B0824}

Cette section décrit la procédure à suivre pour utiliser le calendrier afin de lancer une comparaison de dates entre des rapports de classement.

<!-- 

t_reports_comparing_dates.xml

 -->

Il est impossible de comparer les dates entre des rapports de tendances.

>[!NOTE] Si vous souhaitez réaliser une comparaison de dates sur des mesures clés d’un tableau de bord, vous pouvez extraire les données dans [Report Builder](https://docs.adobe.com/content/help/fr-FR/analytics/analyze/report-builder/home.html) à l’aide de deux requêtes distinctes. Vous utilisez ensuite des formules personnalisées dans Excel afin d’analyser la différence entre les deux.

Pour comparer les dates entre des rapports de classement dans Reports &amp; Analytics :

1. Exécutez un rapport.
1. Cliquez sur le calendrier en haut à droite.
1. Cliquez sur **[!UICONTROL Compare Dates]**.
1. Sélectionnez les dates à utiliser.
1. Cliquez sur **[!UICONTROL Run Report]**.

## Affichage d’un pourcentage sous forme de graphique {#task_BC28CA19A4834AF6BFE68B5B5AEFE75D}

Cette section décrit la procédure à suivre pour spécifier d’afficher les pourcentages d’un tableau de rapport sous forme de graphique.

<!-- 

t_reports_graph_percent.xml

 -->

Cette visualisation est également disponible dans les mini-rapports du tableau de bord.

1. Run a report that supports percentages, such as a [!UICONTROL Pages Report].
1. Cliquez sur **[!UICONTROL Percent Shown As: Graph]**.

## Normalisation des données de rapport {#task_8005B55E59BD479DA67BC618FF8BC94A}

Cette section décrit la procédure à suivre pour normaliser les données de rapport.

<!-- 

t_reports_normalize.xml

 -->

Après exécution d’un rapport de comparaison de dates, ou pour les comparaisons A/B, vous pouvez normaliser les données afin d’afficher le pourcentage de changement entre les rapports. Le jeu de données secondaire est ajusté afin de compenser les différences de nombre de jours sélectionnés ou les différents volumes de trafic.

**Pour normaliser les données de rapport**

1. Exécutez un rapport permettant les comparaisons de dates.
1. Cliquez sur **[!UICONTROL Compare Dates]**, puis spécifiez la comparaison de dates.
1. Cliquez sur **[!UICONTROL Run Report]**.
1. Cliquez sur **[!UICONTROL Normalize Data: Yes]**.

## Sélection d’une page pour un rapport {#task_5CAC3B76BD4C4208B8D53DD972D4771F}

Cette section décrit la procédure à suivre pour sélectionner une page spécifique de votre site web pour un rapport.

<!-- 

t_reports_select_page.xml

 -->

1. Générez un rapport, par exemple un [!UICONTROL Page Views Report] ( **[!UICONTROL Reports]** > **[!UICONTROL Site Metrics]** > **[!UICONTROL Page Views]**).
1. Click the **[!UICONTROL Selected Page]** link.
1. On [!UICONTROL Choose Page], select the pages you want to display.
1. Localisez la page.
1. Cliquez sur **[!UICONTROL OK.]**

## Comparaison de suites de rapports {#task_6BEBEB2D4F36497C9DA5B18ADAD35546}

Cette section décrit la procédure à suivre pour afficher en un seul et même rapport les rapports de deux suites.

<!-- 

t_reports_compare_suites.xml

 -->

Outre l’affichage graphique, le tableau du rapport donne une comparaison en pourcentage. Les rapports suivants peuvent être exécutés avec comparaisons :

* Contenu du site
* Mobile
* Sources de trafic
* Campagnes
* Produits
* Rétention des visiteurs
* Profil du visiteur
* Conversion personnalisée
* Trafic personnalisé
* Target
* Enquête

**Pour comparer des suites de rapports**

1. Générez un rapport qui vous permette de comparer les rapports.
1. Click the **[!UICONTROL Compare to Site]** link.
1. Localisez la suite de rapports.
1. Cliquez sur **[!UICONTROL OK.]**

## Spécification de la granularité d’un rapport {#task_7ED3EEC9E1704A918B25D06ADA3412E0}

Cette section décrit la procédure à suivre pour afficher les totaux des rapports par heure, jour, semaine, mois, trimestre ou année.

<!-- 

t_reports_granularity.xml

 -->

La période du rapport détermine quelles sont les options de granularité disponibles. For example, you can select only **[!UICONTROL Hourly]** if you have a one or two day time frame selected. You can select only **[!UICONTROL Yearly]** granularity if you have more than one year selected.

**Pour spécifier la granularité d’un rapport**

1. Générez un rapport de tendances, tel que **[!UICONTROL Site Content]** > **[!UICONTROL Pages.]**
1. Click the **[!UICONTROL View by]** link, then click a granularity.

## Exécution d’un rapport Jour de la semaine {#task_67CC818ACC3749839B69BDB2ED9AE6B8}

Cette section décrit la procédure à suivre pour exécuter des rapports un jour précis de la semaine, par exemple chaque lundi d’une période donnée.

<!-- 

t_reports_day_of_week.xml

 -->

Cette fonctionnalité s’applique uniquement aux rapports de tendances filtrés avec une plage de dates Semaine ou Jour.

1. Exécutez un rapport de tendances pour une période spécifiée.
1. Cliquez sur le **[!UICONTROL Day of Week]** lien, puis sur un jour.

## Bouton Essayer dans l’espace de travail {#concept_DA41E22460B94BD9ADF63B1CEE2714A7}

Clicking the **[!UICONTROL Try In Workspace]** button at the top of a report will load the same report in Analysis Workspace.

<!-- 

try_in_workspace.xml

 -->

La plupart des rapports dans Reports &amp; Analytics contiennent désormais un bouton Essayer dans l’espace de travail qui vous permet de reproduire la vue actuelle dans Analysis Workspace à des fins de personnalisation.

Actuellement, le bouton n’est disponible que si votre nom d’utilisateur dispose des droits complets dans Analysis Workspace.

Pour plus d’informations sur tous les moyens de personnaliser votre rapport, reportez-vous au guide [Analysis Workspace](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/home.html).
