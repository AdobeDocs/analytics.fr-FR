---
description: Initiation à Adobe Analytics.
keywords: Analysis Workspace
seo-description: Initiation à Adobe Analytics.
seo-title: Guide de prise en main
solution: Analytics
title: Guide de prise en main
topic: Reports and Analytics
uuid: 851 feadb -5 e 30-45 ab -9 f 66-02 bdf 844 fa 54
translation-type: tm+mt
source-git-commit: a0158b98089c044091f61796d782604865aa4eba

---


# Analysis Workspace

Analysis Workspace est l'un des outils phares d'Adobe pour prendre des décisions exploitables basées sur les données pour votre organisation. La visualisation la plus courante, le tableau à structure libre, vous permet de créer facilement des rapports personnalisés à l'aide de dimensions, de mesures, de segments et de plages de dates.

## Conditions préalables

[Envoi de données à Adobe Analytics à l'aide du lancement d'Adobe Experience Platform](../../implement/implement-with-launch/validate-publish-prod.md): L'utilisation d'Analysis Workspace requiert une implémentation opérationnelle. Assurez-vous que votre organisation envoie des données à Adobe avant d'utiliser l'outil. D'autres implémentations, telles que la gestion dynamique des balises ou les implémentations manuelles héritées, peuvent également fonctionner.

## Extraction d'un rapport de classement de base dans Workspace

Extrayez un rapport de classement de base à l'aide d'Analysis Workspace. Un rapport avec classement montre une vue totale agrégée de chaque valeur de dimension, en commençant par les valeurs les plus élevées. Ces types de rapports sont utiles pour identifier les composants de votre site les plus efficaces, par exemple les pages qui génèrent le plus de trafic ou les produits les plus vendus.

1. Log in to [experiencecloud.adobe.com](https://experiencecloud.adobe.com) using your Adobe ID credentials.
2. Cliquez sur l'icône 9 carrée dans l'angle supérieur droit, puis cliquez sur le logo Analytics coloré.
3. Dans la barre de navigation supérieure, cliquez sur Espace de travail.
4. Cliquez sur le bouton Créer un projet.
5. Dans la fenêtre contextuelle modale, assurez-vous que l'option Projet vierge est sélectionnée, puis cliquez sur Créer.
6. A gauche, vous devriez voir une liste de dimensions, de mesures, de segments et de plages de dates. Recherchez la dimension Pages (orange), puis faites-la glisser sur la trame où elle indique « Déposer une dimension ici ».
7. Notez que si la suite de rapports contient des données, un rapport présentant les pages principales pour ce mois est visible. Analysis Workspace automatically populated the report with the [Occurrences](../../components/c-variables/c-metrics/metrics-occurrences.md) metric.
8. Locate the Visits metric (colored green), and drag it either **over** or **next to** the Occurrences metric header (avoid placing it above the metric). Si vous faites glisser la mesure Visites au-dessus des occurrences, la mesure est remplacée dans les rapports. Si vous faites glisser la mesure Visites en regard des Occurrences, les deux mesures sont affichées côte à côte.
9. If you'd like to save your project, click *[!UICONTROL Project]&gt;[!UICONTROL Save]* in the upper left menu.

## Extraction d'un rapport de tendance de base dans Workspace

Extrayez un rapport de tendance de base à l'aide d'Analysis Workspace. Un rapport de tendance affiche une vue temporelle des mesures au cours de la période sélectionnée. Ces types de rapports sont utiles pour identifier les tendances au fil du temps et permettre d'évaluer la réussite ou l'échec des décisions entreprises. Par exemple, vous pouvez consulter un rapport Pages vues avec tendance au fil du temps pour déterminer si une reconception du site a contribué à augmenter ou diminuer le trafic.

1. Log in to [experiencecloud.adobe.com](https://experiencecloud.adobe.com) using your Adobe ID credentials.
2. Cliquez sur l'icône 9 carrée dans l'angle supérieur droit, puis cliquez sur le logo Analytics coloré.
3. Dans la barre de navigation supérieure, cliquez sur Espace de travail.
4. Cliquez sur le bouton Créer un projet.
5. Dans la fenêtre contextuelle modale, assurez-vous que l'option Projet vierge est sélectionnée, puis cliquez sur Créer.
6. A gauche, vous devriez voir une liste de dimensions, de mesures, de segments et de plages de dates. Recherchez la dimension Pages vues et faites-la glisser vers le petit espace du canevas intitulé « Déposer une mesure ici ». Evitez de le déposer dans l'espace réservé aux dimensions (au moins pour cet exercice).
7. Notez que si la suite de rapports comporte des données, un rapport de base des pages vues doit s'afficher sur le mois en cours. Analysis Workspace est automatiquement placé dans la plage de dates « Jour » afin que vous puissiez voir la tendance des pages vues pour le mois en cours.
8. Localisez la plage de dates Semaine (violet violet) dans la liste des composants de plage de dates à gauche. Cliquez sur le titre de la plage de dates pour développer et afficher tous les composants de plage de dates ou utilisez la barre de recherche.
9. Faites glisser la plage de dates Semaine sur l'en-tête de la plage de dates du jour sur la trame pour le remplacer.
10. Notez que votre rapport de tendances est désormais agrégé par semaine plutôt que par jour.
11. If you'd like to save your project, click *[!UICONTROL Project]&gt;[!UICONTROL Save]* in the upper left menu.

## Testez l'outil

Analysis Workspace étant un outil de création de rapports, il n'a aucun impact sur la collecte de données. Il n'y a aucune incidence sur la glissement sans discernement des composants dans un projet pour voir ce qui fonctionne. Faites glisser différentes combinaisons de dimensions et de mesures dans votre projet d'espace de travail pour voir ce qui est disponible.

Si vous faites glisser accidentellement un composant non valide vers votre projet d'espace de travail ou si vous souhaitez revenir à une étape, appuyez sur Ctrl + Z (Windows) ou cmd + Z (Mac) pour annuler la dernière action effectuée. You can also start with a clean slate by clicking *[!UICONTROL Project]&gt;[!UICONTROL New]* in the upper left menu.

## Résolution des problèmes

**Lorsque je fais glisser une mesure, elle indique « Données incorrectes ».**

Des données non valides signifie qu'Adobe ne peut pas renvoyer de données à l'aide de la combinaison de dimensions et de mesures utilisées dans le rapport. Par exemple, deux mesures empilées les unes par rapport aux autres ne peuvent pas être renvoyées sous forme de données, car il n'existe aucun moyen d'afficher deux mesures de cette façon. Placez plutôt les mesures côte à côte.

**Lorsque je fais glisser une mesure, je ne vois aucune donnée réelle - juste des zéros.**

Si vous avez réussi à créer un rapport d'espace de travail mais qu'il n'y a aucune donnée, vous pouvez vérifier quelques éléments :

* Vérifiez deux fois la suite de rapports et assurez-vous qu'elle comporte des données.
* Si vous utilisez un segment dans votre rapport, les critères de segment peuvent ne correspondre à aucune donnée. Essayez de supprimer le segment ou d'en modifier la définition.
* Vérifiez la plage de dates dans l'angle supérieur droit et assurez-vous qu'elle est définie sur une valeur attendue.
* Accédez à votre site Web et utilisez le débogueur pour vérifier que les données sont collectées.

## Ressources supplémentaires

* [Notes de mise à jour d'Analysis Workspace](../../analyze/analysis-workspace/new-features-in-analysis-workspace.md): Découvrez les dernières fonctionnalités introduites dans l'outil.
* [Analysis Workspace sur YouTube](https://www.youtube.com/playlist?list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS): Découvrez comment utiliser la plupart des fonctionnalités d'Analysis Workspace via cette liste de lecture exhaustive.
* Conseils sur le produit : Des conseils de jour, ainsi que des vidéos courtes, s'affichent parfois dans le coin inférieur droit de l'espace de travail d'analyse. If these tips are dismissed, they can be reached through *[!UICONTROL Help]&gt;[!UICONTROL Tips]* at any time.
* [Communauté Analysis Workspace](https://forums.adobe.com/community/experience-cloud/analytics-cloud/analytics/analysis-workspace): Discutez d'Analysis Workspace avec d'autres utilisateurs et votez sur les fonctionnalités que vous souhaitez voir dans l'outil.
* Publications de blog :
   * [Empowering Organizations with Smarter Analysis](https://blogs.adobe.com/digitalmarketing/analytics/adobe-analytics-fall-2016-release-empowering-organizations-smarter-analysis/) (blog, en anglais)
   * [Nouvelles fonctionnalités d'Adobe Analytics rendant les statistiques puissantes plus accessibles](https://blogs.adobe.com/digitalmarketing/analytics/new-adobe-analytics-capabilities-make-powerful-insights-accessible/)
   * [5 conseils pour optimiser votre productivité avec Analysis Workspace](https://blogs.adobe.com/digitalmarketing/analytics/5-tips-maximize-productivity-analysis-workspace/)
   * [Statistiques plus rapides à l’aide d’Analysis Workspace](https://blogs.adobe.com/digitalmarketing/analytics/faster-insights-with-the-analysis-workspace/)
   * [Pour quelles raisons devriez-vous utiliser Analysis Workspace](https://blogs.adobe.com/digitalmarketing/analytics/why-you-should-be-using-analysis-workspace-in-adobe-analytics/)

## Étapes suivantes

Vous trouverez de nombreuses instructions pour approfondir votre compréhension de l'Espace de travail d'analyse. Voici quelques principes de base qu'Adobe recommande :

### Fin - utilisateurs souhaitant approfondir l'utilisation d'Analysis Workspace

* [Détails sur l'interface utilisateur](../../analyze/analysis-workspace/build-workspace-project/t-freeform-project.md)de Workspace : Maintenant que vous avez créé un rapport de base, familiarisez-vous avec le reste de l'interface.
* [Visualisations dans Workspace](visualizations/freeform-analysis-visualizations.md): Les tableaux à structure libre ne sont qu'un type de visualisation dans Analysis Workspace. Découvrez comment utiliser d'autres visualisations comme les graphiques linéaires, les graphiques à barres et les zones géographiques.
* [Dimensions dans Workspace](../../analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md): Apprenez-en plus sur les dimensions et sur la manière de les utiliser dans plus de rapports que simplement avec classement.
* [Mesures dans Workspace](../../analyze/analysis-workspace/components/apply-create-metrics.md): Découvrez les mesures et comment les utiliser dans d'autres parties des tableaux à structure libre.
* [Présentation de la segmentation](../../analyze/analysis-workspace/components/t-freeform-project-segment.md): Découvrez quels segments sont et extrayez un rapport de base à l'aide d'un segment.
* [Plages de dates dans Workspace](../../analyze/analysis-workspace/components/calendar-date-ranges/calendar.md): Découvrez les dates relatives et roulantes et utilisez-les dans les projets d'espace de travail.
* Partage de projets dans Workspace : Montrez à votre collègue le formidable projet Workspace que vous avez créé.
* [(Avancé) Panneaux dans Workspace](c-panels/panels.md): Utilisez des fonctionnalités avancées dans Workspace, telles que Attribution et Comparaison des segments.

### Pour les analystes et les administrateurs qui cherchent à améliorer la qualité de l'espace de travail dans leur organisation

* [Autorisations d'Analysis Workspace](https://marketing.adobe.com/resources/help/en_US/mcloud/admin_getting_started.html): Attribuez des autorisations d'utilisateurs à Workspace via la console d'administration Adobe.
* [Création d'un document de conception de solution](../../implement/prepare/solution-design.md): Commencez à planifier la manière dont votre organisation collecte des dimensions ou des mesures supplémentaires spécifiques à votre site.
* [Modèles dans Workspace](../../analyze/analysis-workspace/build-workspace-project/starter-projects.md): Créez des modèles afin que vos collègues puissent commencer avec un espace de projet adapté à leurs besoins.
* [Traitement de l'espace de travail](curate-share/curate.md): Création d'un projet limitant les composants disponibles, rendant ainsi l'espace de travail plus accessible aux personnes qui connaissent moins cet outil