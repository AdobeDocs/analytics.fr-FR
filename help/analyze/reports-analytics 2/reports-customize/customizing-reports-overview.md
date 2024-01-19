---
description: Une fois un rapport exécuté, vous pouvez le personnaliser de manière à afficher et à analyser les données en fonction de vos besoins. Vous pouvez filtrer les données du rapport, modifier la manière dont elles sont présentées graphiquement, modifier leur granularité, etc.
title: Personnalisation des rapports - Aperçu
uuid: 37d221b7-50fd-4425-b2ba-f40911b72a2f
feature: Reports & Analytics Basics
role: User, Admin
exl-id: 5a042fac-926e-4560-83bf-11f66ddb8273
source-git-commit: a2e69b5f39de3c964381bb5dd5ecd4d9714e9249
workflow-type: tm+mt
source-wordcount: '680'
ht-degree: 80%

---

# Personnalisation des rapports

Une fois un rapport exécuté, vous pouvez le personnaliser de manière à afficher et à analyser les données en fonction de vos besoins. Vous pouvez filtrer les données du rapport, modifier la manière dont elles sont présentées graphiquement, modifier leur granularité, etc.

## Sélectionner une date ou une période {#task_9BEF7D4D839A4748B76E8500D1406C34}

Vous pouvez choisir les périodes des données du rapport.

<!-- 

t_reports_select_date.xml

 -->

Vous pouvez sélectionner des jours, semaines, mois ou années spécifiques. Vous pouvez également exécuter des rapports de comparaison.

Lorsque vous ouvrez un tableau de bord contenant des mini-rapports avec différentes périodes, vous pouvez en définir une nouvelle dans le calendrier. Les modifications s’appliquent à tous les mini-rapports du tableau de bord.

Pour sélectionner une plage de dates :

1. Exécutez un rapport.
1. Cliquez sur l’icône du calendrier en haut à droite.
1. Sélectionnez une date.

   Vous pouvez :

   * Afficher les jours, les mois ou les années (jusqu’à trois).
   * Faire glisser le curseur sur les dates afin de sélectionner une plage.
   * Entrer les dates manuellement.
   * Cliquer sur le nom d’un mois afin de sélectionner ce dernier.
   * Cliquer sur **[!UICONTROL Sélectionner une valeur prédéfinie]** afin de sélectionner une date prédéfinie.
   * Comparaison de dates.

1. Cliquez sur **[!UICONTROL Exécuter le rapport]**.

## Comparer des dates {#task_95155C3700774B709F5FB81AE96B0824}

Vous pouvez utiliser le calendrier pour lancer des comparaisons de dates entre des rapports de classement.

<!-- 

t_reports_comparing_dates.xml

 -->

Il est impossible de comparer les dates entre des rapports de tendances.

>[!NOTE]
>
>Si vous souhaitez réaliser une comparaison de dates sur des mesures clés d’un tableau de bord, vous pouvez extraire les données dans [Report Builder](https://experienceleague.adobe.com/docs/analytics/analyze/report-builder/home.html?lang=fr) à l’aide de deux requêtes distinctes. Vous utilisez ensuite des formules personnalisées dans Excel afin d’analyser la différence entre les deux.

<!-- delete this procedure, but what about this entire "Compare dates" section?

To compare dates between ranked reports in Reports & analytics: 

1. Run a report.
1. Click the calendar at the top right.
1. Click **[!UICONTROL Compare Dates]**.
1. Select the dates you want to use.
1. Click **[!UICONTROL Run Report]**.

-->

## Afficher des pourcentages sous forme de graphique {#task_BC28CA19A4834AF6BFE68B5B5AEFE75D}

Vous pouvez indiquer si le pourcentage doit être affiché sous forme de graphique dans un tableau de rapport.

<!-- 

t_reports_graph_percent.xml

 -->

Cette visualisation est également disponible dans les mini-rapports du tableau de bord.

Pour afficher le pourcentage sous forme de graphique dans un tableau de rapport :

1. Exécutez un rapport qui prend les pourcentages en charge, tel qu’un [!UICONTROL rapport Pages].
1. Cliquez sur **[!UICONTROL Pourcentage affiché comme : graphique]**.

## Normaliser des données de rapport {#task_8005B55E59BD479DA67BC618FF8BC94A}

<!-- 

t_reports_normalize.xml

 -->

Après exécution d’un rapport de comparaison de dates, ou pour les comparaisons A/B, vous pouvez normaliser les données afin d’afficher le pourcentage de changement entre les rapports. Le jeu de données secondaire est ajusté afin de compenser les différences de nombre de jours sélectionnés ou les différents volumes de trafic.

Pour normaliser les données de rapport :

1. Exécutez un rapport permettant les comparaisons de dates.
1. Cliquez sur **[!UICONTROL Comparer les dates]**, puis spécifiez les dates à comparer.
1. Cliquez sur **[!UICONTROL Exécuter le rapport]**.
1. Cliquez sur **[!UICONTROL Normaliser les données : oui]**.

## Sélectionner une page pour un rapport {#task_5CAC3B76BD4C4208B8D53DD972D4771F}

Pour sélectionner une page spécifique des pages de votre site web pour un rapport :

<!-- 

t_reports_select_page.xml

 -->

1. Générez un rapport, tel qu’un [!UICONTROL Rapport Pages vues] (**[!UICONTROL Rapports]** > **[!UICONTROL Mesures du site]** > **[!UICONTROL Pages vues]**).
1. Cliquez sur le lien **[!UICONTROL Page sélectionnée]**.
1. Sous [!UICONTROL Sélectionner les pages], sélectionnez celles que vous souhaitez afficher.
1. Localisez la page.
1. Cliquez sur **[!UICONTROL OK]**.

## Comparer des suites de rapports {#task_6BEBEB2D4F36497C9DA5B18ADAD35546}

Vous pouvez afficher dans le même rapport les rapports de deux suites de rapports.

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

Pour comparer des suites de rapports :

1. Générez un rapport qui vous permette de comparer les rapports.
1. Cliquez sur le lien **[!UICONTROL Comparer au site]**.
1. Localisez la suite de rapports.
1. Cliquez sur **[!UICONTROL OK]**.

## Spécifier la granularité d’un rapport {#task_7ED3EEC9E1704A918B25D06ADA3412E0}

Vous pouvez afficher les totaux des rapports par heure, jour, semaine, mois, trimestre ou année.

<!-- 

t_reports_granularity.xml

 -->

La période du rapport détermine quelles sont les options de granularité disponibles. Par exemple, l’option **[!UICONTROL Heure]** peut être sélectionnée uniquement si vous avez choisi une période de 1 ou 2 jours. L’option **[!UICONTROL Année]** est visible uniquement si plus d’une année est sélectionnée.

Pour spécifier la granularité d’un rapport :

1. Générez un rapport de tendances, tel que **[!UICONTROL Contenu du site]** > **[!UICONTROL Pages]**.
1. Cliquez sur le lien **[!UICONTROL Vue par]**, puis sur une granularité.

## Exécuter un rapport Jour de la semaine {#task_67CC818ACC3749839B69BDB2ED9AE6B8}

Vous pouvez exécuter des rapports un jour spécifique de la semaine, par exemple chaque lundi d’une période donnée.

<!-- 

t_reports_day_of_week.xml

 -->

Cette fonctionnalité s’applique uniquement aux rapports de tendances filtrés avec une plage de dates Semaine ou Jour.

Pour exécuter un rapport Jour de la semaine :

1. Exécutez un rapport de tendances pour une période spécifiée.
1. Cliquez sur le lien **[!UICONTROL Jour de la semaine]**, puis cliquez sur un jour.
