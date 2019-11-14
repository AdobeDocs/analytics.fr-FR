---
description: Initiation à Adobe Analytics.
keywords: Analysis Workspace
solution: Analytics
title: Guide de prise en main
topic: Reports and analytics
uuid: 851feadb-5e30-45ab-9f66-02bdf844fa54
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Analysis Workspace

Analysis Workspace est l’un des outils phares d’Adobe pour prendre des décisions basées sur les données exploitables pour votre entreprise. La visualisation la plus courante, le tableau à structure libre, vous permet de créer facilement des rapports personnalisés à l’aide de dimensions, de mesures, de segments et de plages de dates.

## Conditions préalables

[Envoyer des données à Adobe Analytics à l’aide d’Adobe Experience Platform Launch](/help/implement/implement-with-launch/validate-publish-prod.md): L’utilisation d’Analysis Workspace nécessite une implémentation efficace. Assurez-vous que votre entreprise envoie les données à Adobe avant d’utiliser l’outil. D’autres implémentations, telles que la gestion dynamique des balises ou les implémentations manuelles héritées, peuvent également fonctionner.

## Extraction d’un rapport avec classement de base dans Workspace

Récupérez un rapport avec classement de base à l’aide d’Analysis Workspace. Un rapport avec classement affiche une vue totale agrégée de chaque valeur de dimension, indiquant d’abord les valeurs les plus élevées. Ces types de rapports sont utiles pour identifier les composants de votre site les plus efficaces, tels que les pages qui génèrent le plus de trafic ou les produits les plus vendus.

1. Connectez-vous à [experience.adobe.com](https://experiencecloud.adobe.com) à l’aide de vos identifiants Adobe ID.
2. Cliquez sur l’icône à 9 carrés dans l’angle supérieur droit, puis sur le logo Analytics coloré.
3. Dans la barre de navigation supérieure, cliquez sur Espace de travail.
4. Cliquez sur le bouton Créer un projet.
5. Dans la fenêtre contextuelle modale, assurez-vous que l’option "Projet vierge" est sélectionnée, puis cliquez sur Créer.
6. Sur la gauche, vous devriez voir une liste de dimensions, de mesures, de segments et de plages de dates. Localisez la dimension Pages (orange de couleur), puis faites-la glisser sur le canevas où il est indiqué "Déposer une dimension ici".
7. Notez que si la suite de rapports comporte des données, un rapport présentant les pages principales pour ce mois-ci est visible. Analysis Workspace a automatiquement renseigné le rapport avec la mesure [Occurrences](/help/components/c-variables/c-metrics/metrics-occurrences.md) .
8. Localisez la mesure Visites (en vert coloré) et faites-la glisser **sur** ou **** en regard de l’en-tête de la mesure Occurrences (évitez de la placer au-dessus de la mesure). Si vous faites glisser la mesure Visites au-dessus d’Occurrences, elle est remplacée dans les rapports. Si vous faites glisser la mesure Visites en regard d’Occurrences, les deux mesures s’affichent côte à côte.
9. Si vous souhaitez enregistrer votre projet, cliquez sur *[!UICONTROL Projet]&gt;[!UICONTROL Enregistrer]* dans le menu supérieur gauche.

## Extraire un rapport de tendances de base dans Workspace

Extrayez un rapport de tendances de base à l’aide d’Analysis Workspace. Un rapport de tendances affiche une vue temporelle des mesures utilisant la période sélectionnée. Ces types de rapports sont utiles pour identifier les tendances dans le temps et peuvent être utilisés pour évaluer la réussite ou l’échec des décisions prises par l’entreprise. Vous pouvez, par exemple, examiner un rapport Pages vues avec tendance au fil du temps pour voir si la reconception d’un site contribue à augmenter ou à diminuer le trafic.

1. Connectez-vous à [experience.adobe.com](https://experiencecloud.adobe.com) à l’aide de vos identifiants Adobe ID.
2. Cliquez sur l’icône à 9 carrés dans l’angle supérieur droit, puis sur le logo Analytics coloré.
3. Dans la barre de navigation supérieure, cliquez sur Espace de travail.
4. Cliquez sur le bouton Créer un projet.
5. Dans la fenêtre contextuelle modale, assurez-vous que l’option "Projet vierge" est sélectionnée, puis cliquez sur Créer.
6. Sur la gauche, vous devriez voir une liste de dimensions, de mesures, de segments et de plages de dates. Localisez la dimension Pages vues, puis faites-la glisser vers le petit espace de la trame intitulé "Déposer une mesure ici". Evitez de le déposer dans l’espace réservé aux dimensions (au moins pour cet exercice).
7. Notez que si la suite de rapports comporte des données, vous devriez voir un rapport de base Pages vues avec tendance sur le mois en cours. Analysis Workspace insère automatiquement la plage de dates "Jour" afin que vous puissiez voir la tendance des pages vues pour le mois en cours.
8. Localisez la plage de dates Semaine (violet coloré) dans la liste des composants de plage de dates sur la gauche. Cliquez sur le titre de la plage de dates pour développer et afficher tous les composants de la plage de dates ou utilisez la barre de recherche.
9. Faites glisser la plage de dates Semaine au-dessus de l’en-tête de plage de dates Jour sur la trame pour la remplacer.
10. Notez que votre rapport de tendances est désormais agrégé par semaine plutôt que par jour.
11. Si vous souhaitez enregistrer votre projet, cliquez sur *[!UICONTROL Projet]&gt;[!UICONTROL Enregistrer]* dans le menu supérieur gauche.

## Testez l'outil

Analysis Workspace étant un outil de création de rapports, il n’a aucun impact sur la collecte de données. Il n'y a aucune répercussion à faire glisser sans distinction des composants dans un projet pour voir ce qui fonctionne. Faites glisser différentes combinaisons de dimensions et de mesures dans votre projet d’espace de travail pour voir ce qui vous est disponible.

Si vous faites glisser accidentellement un composant non valide vers votre projet d’espace de travail ou souhaitez revenir en arrière d’une étape, appuyez sur ctrl+Z (Windows) ou cmd+Z (Mac) pour annuler la dernière action effectuée. Vous pouvez également commencer par une ardoise propre en cliquant sur *[!UICONTROL Projet]&gt;[!UICONTROL Nouveau]* dans le menu supérieur gauche.

## Résolution des problèmes

**Lorsque je fais glisser une mesure sur l’écran, elle indique "Données non valides".**

Les données non valides signifient qu’Adobe ne peut pas renvoyer de données à l’aide de la combinaison de dimensions et de mesures utilisées dans le rapport. Par exemple, deux mesures empilées les unes sur les autres ne peuvent pas être renvoyées sous forme de données, car il n’est pas possible d’afficher deux mesures de cette manière. Placez les mesures côte à côte.

**Lorsque je fais glisser une mesure sur l’écran, je ne vois aucune donnée réelle - juste des zéros.**

Si vous avez réussi à créer un rapport sur l’espace de travail mais qu’il n’y a aucune donnée, vous pouvez vérifier quelques éléments :

* Vérifiez deux fois la suite de rapports et assurez-vous qu’elle contient des données.
* Si vous utilisez un segment dans votre rapport, il se peut que les critères de segment ne correspondent à aucune donnée. Essayez de supprimer le segment ou d’ajuster la définition du segment.
* Vérifiez la plage de dates dans l’angle supérieur droit et assurez-vous qu’elle est définie sur la valeur attendue.
* Accédez à votre site Web et utilisez le débogueur pour vérifier que les données sont en cours de collecte.

## Ressources supplémentaires

* [Notes](/help/analyze/analysis-workspace/new-features-in-analysis-workspace.md)de mise à jour d’Analysis Workspace : Lisez les dernières fonctionnalités introduites dans l'outil.
* [Analysis Workspace sur YouTube](https://www.youtube.com/playlist?list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS): Découvrez comment utiliser la plupart des fonctionnalités d’Analysis Workspace à l’aide de cette liste de lecture exhaustive.
* Conseils sur les produits : Des conseils du jour, ainsi que de courtes vidéos, apparaissent parfois dans le coin inférieur droit d’Analysis Workspace. Si ces conseils sont rejetés, vous pouvez les joindre à tout moment par le biais de *[!UICONTROL Aide]&gt;[!UICONTROL Conseils]* .
* [Communauté](https://forums.adobe.com/community/experience-cloud/analytics-cloud/analytics/analysis-workspace)Analysis Workspace : Discutez d’Analysis Workspace avec d’autres utilisateurs et votez sur les fonctionnalités que vous souhaitez voir dans l’outil.
* Blog :
   * [Empowering Organizations with Smarter Analysis](https://blogs.adobe.com/digitalmarketing/analytics/adobe-analytics-fall-2016-release-empowering-organizations-smarter-analysis/) (blog, en anglais)
   * [Les Nouvelles Fonctionnalités D’Adobe Analytics Rendent Les Informations Puissantes Plus Accessibles](https://blogs.adobe.com/digitalmarketing/analytics/new-adobe-analytics-capabilities-make-powerful-insights-accessible/)
   * [5 conseils pour optimiser votre productivité avec Analysis Workspace](https://blogs.adobe.com/digitalmarketing/analytics/5-tips-maximize-productivity-analysis-workspace/)
   * [Statistiques plus rapides à l’aide d’Analysis Workspace](https://blogs.adobe.com/digitalmarketing/analytics/faster-insights-with-the-analysis-workspace/)
   * [Pour quelles raisons devriez-vous utiliser Analysis Workspace](https://blogs.adobe.com/digitalmarketing/analytics/why-you-should-be-using-analysis-workspace-in-adobe-analytics/)

## Étapes suivantes

Il existe de nombreuses directions pour approfondir votre compréhension de l’Espace de travail d’analyse. Adobe recommande quelques principes de base :

### Pour les utilisateurs finaux qui souhaitent approfondir leurs connaissances sur l’utilisation d’Analysis Workspace

* [Détails sur l’interface utilisateur](/help/analyze/analysis-workspace/build-workspace-project/t-freeform-project.md)de Workspace : Maintenant que vous avez créé un rapport de base, familiarisez-vous avec le reste de l'interface.
* [Visualisations dans Workspace](visualizations/freeform-analysis-visualizations.md): Les tableaux à structure libre ne sont qu’un type de visualisation dans Analysis Workspace. Découvrez comment utiliser d’autres visualisations, telles que des diagrammes en courbes, des graphiques à barres et des cartes géographiques.
* [Dimensions dans Workspace](/help/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md): En savoir plus sur les dimensions et leur utilisation dans des rapports non seulement avec classement.
* [Mesures dans Workspace](/help/analyze/analysis-workspace/components/apply-create-metrics.md): En savoir plus sur les mesures et leur utilisation dans d’autres parties des tableaux à structure libre.
* [Introduction à la segmentation](/help/analyze/analysis-workspace/components/t-freeform-project-segment.md): Découvrez les segments et extrayez un rapport de base à l’aide d’un segment.
* [Plages de dates dans Workspace](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md): Découvrez les dates relatives et variables et utilisez-les dans les projets d’espace de travail.
* Partage de projets dans Workspace : Montrez à votre collègue l'incroyable projet Workspace que vous avez créé.
* [(Avancé) Panneaux dans Workspace](c-panels/panels.md): Utilisez les fonctionnalités avancées de Workspace, telles que la comparaison des attributs et des segments.

### Pour les analystes et les administrateurs qui souhaitent améliorer la qualité de l’espace de travail dans leur organisation

* [Autorisations](https://marketing.adobe.com/resources/help/en_US/mcloud/admin_getting_started.html)d’Analysis Workspace : Attribuez des autorisations d’utilisateur à Workspace via la console d’administration Adobe.
* [Créez un document](/help/implement/prepare/solution-design.md)de conception de solution : Commencez à planifier la manière dont votre entreprise collecte des dimensions ou mesures supplémentaires spécifiques à votre site.
* [Modèles dans Workspace](/help/analyze/analysis-workspace/build-workspace-project/starter-projects.md): Créez des modèles pour que vos collègues puissent commencer avec un espace de projet adapté à leurs besoins.
* [Traitement](curate-share/curate.md)de l’espace de travail : Créez un projet qui limite les composants disponibles, rendant l’espace de travail plus accessible aux personnes moins familières avec l’outil
