---
title: Guide de traduction des mesures couramment utilisées sur d’autres plateformes
description: Découvrez comment extraire des données de mesure pour de nombreux rapports courants en utilisant une terminologie plus familière aux utilisateurs de Google Analytics.
translation-type: tm+mt
source-git-commit: 3ce18f3f222286aed08c81dd2c958dab7e443df3

---


# Guide de traduction des mesures couramment utilisées sur d’autres plateformes

Sur d’autres plateformes, telles que Google Analytics, de nombreux rapports partagent un nombre commun de mesures. Utilisez cette page pour comprendre comment recréer les mesures utilisées dans de nombreux rapports.

Pour ajouter plusieurs mesures à un tableau à structure libre de l’espace de travail, faites glisser la mesure depuis la zone de composants située en regard de l’en-tête de mesure dans l’espace de travail :

![Mesure supplémentaire](/help/technotes/ga-to-aa/assets/new_metric.png)

## Mesures d’acquisition

**Utilisateurs** est approximativement égal à Visiteurs **** uniques dans Workspace. Pour plus d’informations, voir la mesure Visiteurs [](/help/components/c-variables/c-metrics/metrics-unique-visitors.md) uniques dans le guide de l’utilisateur Composants.

**Les nouveaux utilisateurs** peuvent être obtenus en procédant comme suit :

1. Faites glisser la mesure Visiteurs **** uniques sur l’espace de travail.
2. Faites glisser le segment **Premières visites** au-dessus des en-têtes de mesure Visiteurs uniques :

   ![Premières visites](../assets/first_time_visits.png)

**Les sessions** sont approximativement égales aux **visites** dans Analysis Workspace. Voir la mesure [Visites](/help/components/c-variables/c-metrics/metrics-visit.md) dans le guide de l’utilisateur Composants pour en savoir plus.

![Mesures d’acquisition](../assets/acquisition_metrics.png)

## Mesures de comportement

**Le taux** de rebonds est facilement disponible en tant que mesure dans Analysis Workspace. Pour plus d’informations, voir la mesure [Taux](/help/components/c-variables/c-metrics/metrics-bounce-rate.md) de rebonds dans le guide de l’utilisateur Composants.

**Pages/Session** est une mesure calculée. Il peut être obtenu par les moyens suivants :

1. Si vous avez déjà créé cette mesure calculée, localisez-la sous Mesures et faites-la glisser sur l’espace de travail.
2. Si vous n’avez pas encore créé cette mesure calculée, cliquez sur l’icône **+** en regard de la liste des mesures pour ouvrir le créateur de mesures calculées.
3. Donnez-lui un titre de "Pages vues par visite" et une description, le cas échéant.
4. Définissez le format sur Décimal et le nombre de décimales sur 2.
5. Faites glisser les mesures **Pages vues** et **Visites** dans la zone de définition.
6. Organisez la définition de sorte que la formule soit Vues de **page divisée par Visites**.

   ![Pages vues par visite](/help/technotes/ga-to-aa/assets/page_views_per_visit.png)

7. Cliquez sur Enregistrer pour revenir à votre espace de travail.
8. Faites glisser la mesure calculée nouvellement définie sur l’espace de travail.

   En savoir plus sur les mesures [calculées](/help/components/c-variables/c-metrics/calculated-metric.md) dans le guide de l’utilisateur Composants.

**Durée La durée** de la session est approximativement égale à la **durée de la visite (secondes)**. Pour en savoir plus sur les mesures [Durée de la visite](/help/components/c-variables/c-metrics/metrics-time-spent.md) , consultez le guide de l’utilisateur Composants.

## Mesures de conversion

**Le taux** de conversion des objectifs, l’exécution **des** objectifs et la valeur **des** objectifs nécessitent une implémentation supplémentaire sur les deux plates-formes. Si votre implémentation prend déjà en charge la dimension products et l’événement purchase, tenez compte des étapes suivantes :

1. Faites glisser les mesures **Commandes** , **Recettes** et **Visites** sur l’espace de travail.
1. Créez une mesure calculée de **commandes par visite**. Utilisez les touches Ctrl+clic (Windows) ou cmd+clic (Mac) sur les deux en-têtes de mesure pour les mettre en surbrillance. Cliquez avec le bouton droit de la souris sur l’un des en-têtes, sélectionnez **Créer une mesure à partir de la sélection**, puis cliquez sur **Diviser**. Cette nouvelle mesure est similaire à un taux de conversion des objectifs.
1. Si des décimales sont nécessaires, modifiez la mesure calculée. Cliquez sur le bouton Infos dans l’en-tête de la mesure, puis sur l’icône représentant un crayon. Ajoutez 1 ou 2 décimales dans la fenêtre Créateur de mesures calculées, puis cliquez sur Enregistrer.

   ![Commandes par visite](/help/technotes/ga-to-aa/assets/orders_per_visit.png)

Si votre implémentation ne prend pas encore en charge les données de produit ou de conversion, Adobe conseille de travailler avec un consultant en implémentation pour garantir la qualité et l’intégrité des données.
