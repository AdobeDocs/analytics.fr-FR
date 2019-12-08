---
description: Mise en route avec Adobe Analytics.
keywords: Analysis Workspace
title: Guide de prise en main
topic: Reports and analytics
uuid: 851feadb-5e30-45ab-9f66-02bdf844fa54
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Analysis Workspace

Analysis Workspace est l’un des outils phares d’Adobe pour prendre des décisions pratiques basées sur les données pour votre entreprise. La visualisation la plus courante, le tableau à structure libre, vous permet de créer facilement des rapports personnalisés à l’aide de dimensions, de mesures, de segments et de périodes.

## Conditions préalables

[Envoyer des données à Adobe Analytics à l’aide d’Adobe Experience Platform Launch](/help/implement/implement-with-launch/validate-publish-prod.md) : l’utilisation d’Analysis Workspace nécessite une implémentation efficace. Assurez-vous que votre entreprise envoie les données à Adobe avant d’utiliser l’outil. D’autres implémentations, telles que la gestion dynamique des balises ou les implémentations manuelles héritées, peuvent également fonctionner.

## Extraction d’un rapport de classement de base dans Workspace

Effectuez l’extraction d’un rapport de classement de base à l’aide d’Analysis Workspace. Un rapport de classement affiche une vue totale agrégée de chaque valeur de dimension, en indiquant d’abord les valeurs les plus élevées. Ces types de rapports sont utiles pour identifier les composants de votre site les plus efficaces, tels que les pages qui génèrent le plus de trafic ou les produits les plus vendus.

1. Connectez-vous à [experiencecloud.adobe.com](https://experiencecloud.adobe.com) à l’aide de vos identifiants Adobe ID.
2. Cliquez sur l’icône à 9 carrés dans le coin supérieur droit, puis sur le logo Analytics coloré.
3. Dans la barre de navigation supérieure, cliquez sur Workspace.
4. Cliquez sur le bouton Créer un projet.
5. Dans la fenêtre contextuelle modale, assurez-vous que l’option « Projet vierge » est sélectionnée, puis cliquez sur Créer.
6. Sur la gauche, vous devriez voir une liste de dimensions, de mesures, de segments et de périodes. Recherchez la dimension Pages (de couleur orange), puis faites-la glisser sur la zone de travail qui indique « Déposer la dimension ici ».
7. Notez que si la suite de rapports contient des données, il est possible de consulter un rapport présentant les pages principales pour ce mois. Analysis Workspace a automatiquement renseigné la mesure [Occurrences](/help/components/c-variables/c-metrics/metrics-occurrences.md) dans le rapport.
8. Recherchez la mesure Visites (de couleur verte) et faites-la glisser **sur** ou **en regard** de l’en-tête de la mesure Occurrences (évitez de la placer au-dessus de la mesure). Si vous faites glisser la mesure Visites au-dessus de la mesure Occurrences, elle est remplacée dans les rapports. Si vous faites glisser la mesure Visites en regard de la mesure Occurrences, les deux mesures s’affichent côte à côte.
9. Si vous souhaitez enregistrer votre projet, cliquez sur *[!UICONTROL Projet] &gt; [!UICONTROL Enregistrer]* dans le menu supérieur gauche.

## Extraire un rapport de tendance de base dans Workspace

Effectuez l’extraction d’un rapport de tendance de base à l’aide d’Analysis Workspace. Un rapport de tendance affiche une vue de dépassement de délai à l’aide de la période sélectionnée. Ces types de rapports sont utiles pour identifier les tendances dans le temps et peuvent servir à évaluer l’issue positive ou négative des décisions professionnelles. Vous pouvez, par exemple, examiner un rapport de pages vues avec des tendances au fil du temps pour voir si un site repensé a contribué à augmenter ou à diminuer le trafic.

1. Connectez-vous à [experiencecloud.adobe.com](https://experiencecloud.adobe.com) à l’aide de vos identifiants Adobe ID.
2. Cliquez sur l’icône à 9 carrés dans le coin supérieur droit, puis sur le logo Analytics coloré.
3. Dans la barre de navigation supérieure, cliquez sur Workspace.
4. Cliquez sur le bouton Créer un projet.
5. Dans la fenêtre contextuelle modale, assurez-vous que l’option « Projet vierge » est sélectionnée, puis cliquez sur Créer.
6. Sur la gauche, vous devriez voir une liste de dimensions, de mesures, de segments et de périodes. Recherchez la dimension Pages vues, puis faites-la glisser vers le petit espace de la zone de travail intitulé « Faire glisser la mesure ici ». Évitez de la déposer dans l’espace réservé aux dimensions (au moins pour cet exercice).
7. Notez que si la suite de rapports contient des données, vous devriez voir un rapport de pages vues de base avec des tendances pour le mois en cours. Analysis Workspace insère automatiquement la période « Jour » afin que vous puissiez afficher la tendance des pages vues pour le mois en cours.
8. Recherchez la période Semaine (de couleur violette) dans la liste des composants de périodes sur la gauche. Cliquez sur le titre de la période pour développer et afficher tous les composants de la période ou utilisez la barre de recherche.
9. Faites glisser la période Semaine au-dessus de l’en-tête de la période Jour sur la zone de travail afin de la remplacer.
10. Notez que votre rapport de tendance est désormais agrégé par semaine plutôt que par jour.
11. Si vous souhaitez enregistrer votre projet, cliquez sur *[!UICONTROL Projet] &gt; [!UICONTROL Enregistrer]* dans le menu supérieur gauche.

## Tester l’outil

Analysis Workspace étant un outil de reporting, il n’a aucun impact sur la collecte de données. Il n’y a aucune répercussion si vous faites glisser sans distinction des composants dans un projet pour voir ce qui fonctionne. Faites glisser différentes combinaisons de dimensions et de mesures dans votre projet Workspace pour voir ce qui est mis à votre disposition.

Si vous faites glisser accidentellement un composant non valide vers votre projet Workspace ou souhaitez revenir en arrière d’une étape, appuyez sur ctrl+Z (Windows) ou sur cmd+Z (Mac) pour annuler la dernière action effectuée. Vous pouvez également commencer à zéro en cliquant sur *[!UICONTROL Projet] &gt; [!UICONTROL Nouveau]* dans le menu supérieur gauche.

## Résolution des problèmes

**Lorsque je fais glisser une mesure sur l’écran, un message indique « Données incorrectes ».**

Le message Données incorrectes signifie qu’Adobe ne peut pas renvoyer de données à l’aide de la combinaison de dimensions et de mesures utilisée dans le rapport. Par exemple, deux mesures empilées les unes sur les autres ne peuvent pas être renvoyées sous forme de données, car il n’est pas possible d’afficher deux mesures de cette manière. Placez plutôt les mesures côte à côte.

**Lorsque je fais glisser une mesure sur l’écran, je ne vois aucune donnée à proprement dit, seulement des zéros.**

Si vous êtes parvenu à créer un rapport Workspace, qui ne comporte cependant aucune donnée, vous pouvez effectuer quelques vérifications :

* Vérifiez deux fois la suite de rapports et assurez-vous qu’elle contient des données.
* Si vous utilisez un segment dans votre rapport, il se peut que les critères de segment ne correspondent à aucune donnée. Essayez de supprimer le segment ou d’ajuster la définition du segment.
* Vérifiez la période dans le coin supérieur droit et assurez-vous qu’elle est définie sur la valeur attendue.
* Accédez à votre site web et utilisez Debugger pour vérifier que la collecte des données s’effectue.

## Ressources supplémentaires

* [Notes de mise à jour d’Analysis Workspace](/help/analyze/analysis-workspace/new-features-in-analysis-workspace.md) : prenez connaissance des dernières fonctionnalités intégrées à l’outil.
* [Analysis Workspace sur YouTube](https://www.youtube.com/playlist?list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS) : découvrez comment utiliser la plupart des fonctionnalités d’Analysis Workspace à l’aide de cette liste de lecture exhaustive.
* Conseils intégrés au produit : des conseils du jour, ainsi que de courtes vidéos, s’affichent parfois dans le coin inférieur droit d’Analysis Workspace. Si vous ignorez ces conseils, vous pouvez y accéder à tout moment via *[!UICONTROL Aide] &gt; [!UICONTROL Conseils]*.
* [Communauté Analysis Workspace](https://forums.adobe.com/community/experience-cloud/analytics-cloud/analytics/analysis-workspace) : discutez d’Analysis Workspace avec d’autres utilisateurs et votez à propos des fonctionnalités que vous souhaitez voir apparaître dans l’outil.
* Publications du blog :
   * [Empowering Organizations with Smarter Analysis](https://blogs.adobe.com/digitalmarketing/analytics/adobe-analytics-fall-2016-release-empowering-organizations-smarter-analysis/) (Doter les entreprises d’outils nécessaires grâce à Smarter Analysis, en anglais)
   * [New Adobe Analytics Capabilities Make Powerful Insights More Accessible](https://blogs.adobe.com/digitalmarketing/analytics/new-adobe-analytics-capabilities-make-powerful-insights-accessible/) (Nouvelles fonctionnalités d’Adobe Analytics rendant les statistiques utiles plus accessibles, en anglais)
   * [5 Tips to Maximize Your Productivity with Analysis Workspace](https://blogs.adobe.com/digitalmarketing/analytics/5-tips-maximize-productivity-analysis-workspace/) (5 conseils pour optimiser votre productivité avec Analysis Workspace, en anglais)
   * [Faster Insights with Analysis Workspace](https://blogs.adobe.com/digitalmarketing/analytics/faster-insights-with-the-analysis-workspace/) (Statistiques plus rapides à l’aide d’Analysis Workspace, en anglais)
   * [Why You Should Be Using Analysis Workspace](https://blogs.adobe.com/digitalmarketing/analytics/why-you-should-be-using-analysis-workspace-in-adobe-analytics/) (Pour quelles raisons devriez-vous utiliser Analysis Workspace, en anglais)

## Étapes suivantes

Il existe de nombreuses instructions pour approfondir votre compréhension d’Analysis Workspace. Voici quelques principes de base recommandés par Adobe :

### Pour les utilisateurs finaux qui souhaitent approfondir leurs connaissances sur l’utilisation d’Analysis Workspace

* [Détails sur l’interface utilisateur de Workspace](/help/analyze/analysis-workspace/build-workspace-project/t-freeform-project.md) : maintenant que vous avez créé un rapport de base, familiarisez-vous avec le reste de l’interface.
* [Visualisations dans Workspace](visualizations/freeform-analysis-visualizations.md) : les tableaux à structure libre ne sont qu’un type de visualisation dans Analysis Workspace. Découvrez comment utiliser d’autres visualisations, comme des graphiques en courbes, des graphiques en barres et des cartes géographiques.
* [Dimensions dans Workspace](/help/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md) : apprenez-en plus sur les dimensions et leur utilisation dans d’autres cas que les rapports de classement.
* [Mesures dans Workspace](/help/analyze/analysis-workspace/components/apply-create-metrics.md) : apprenez-en plus sur les mesures et leur utilisation dans d’autres parties des tableaux à structure libre.
* [Introduction à la segmentation](/help/analyze/analysis-workspace/components/t-freeform-project-segment.md) : apprenez-en plus sur les segments et extrayez un rapport de base à l’aide d’un segment.
* [Périodes dans Workspace](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md) : apprenez-en plus sur les dates relatives et roulantes, et utilisez-les dans les projets Workspace.
* Partage de projets dans Workspace : montrez à votre collègue l’incroyable projet Workspace que vous avez créé.
* [(Avancé) Panneaux dans Workspace](c-panels/panels.md) : utilisez les fonctionnalités avancées de Workspace, telles que la comparaison d’attributs et de segments.

### Pour les analystes et les administrateurs qui souhaitent améliorer la qualité de Workspace au sein de leur entreprise

* [Autorisations d’Analysis Workspace](https://marketing.adobe.com/resources/help/en_US/mcloud/admin_getting_started.html) : attribuez des autorisations d’utilisateur à Workspace via Adobe Admin Console.
* [Création d’un document de conception de solution](/help/implement/prepare/solution-design.md) : commencez à planifier la manière dont votre entreprise recueille des dimensions ou des mesures supplémentaires spécifiques à votre site.
* [Modèles dans Workspace](/help/analyze/analysis-workspace/build-workspace-project/starter-projects.md) : créez des modèles pour que vos collègues puissent commencer avec un espace de projet adapté à leurs besoins.
* [Traitement de Workspace](curate-share/curate.md) : créez un projet qui limite les composants disponibles, en rendant Workspace plus accessible aux personnes moins familières avec l’outil.
