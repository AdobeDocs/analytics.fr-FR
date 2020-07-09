---
description: Le panneau Analytics for Cible (A4T) vous permet d’analyser vos activités d’Adobe Target et vos expériences dans l’Analysis Workspace.
title: Panneau Analytics for Cible (A4T)
translation-type: tm+mt
source-git-commit: fe6202288cfc07575db437f7d0c055f1b40ddcf6
workflow-type: tm+mt
source-wordcount: '834'
ht-degree: 14%

---


# Panneau Analytics for Cible (A4T)

Le panneau Analytics for Target (A4T) vous permet d’analyser vos activités et expériences Adobe Target dans Analysis Workspace. Il vous permet également d’afficher l’effet élévateur et la fiabilité pour 3 mesures de réussite au maximum. Pour accéder au panneau A4T, accédez à une suite de rapports avec les composants A4T activés. Cliquez ensuite sur l’icône du panneau située à l’extrémité gauche et faites glisser le panneau Analytics for Cible dans votre projet Analysis Workspace.

## Entrées de panneau {#Input}

Vous pouvez configurer le panneau A4T à l’aide des paramètres d’entrée suivants :

| Paramètre | Description |
|---|---|
| Activité Target | Effectuez une sélection à partir d’une liste d’Activités de Cible ou faites glisser et déposez une activité à partir du rail de gauche.<br>**Remarque :**La liste est remplie avec les 6 derniers mois d’activités qui ont eu au moins 1 accès. Si vous ne voyez pas d&#39;activité dans la liste, elle peut être plus vieille que 6 mois. Il peut encore être ajouté à partir du rail gauche, qui a une période de rétrospective de 18 mois. |
| Expérience de contrôle | Sélectionnez votre expérience de contrôle. Vous pouvez le modifier si nécessaire dans la liste déroulante. |
| Mesure de normalisation | Choisissez entre Visiteurs uniques, Visites ou Impressions d’Activité. Un visiteur unique est recommandé pour la plupart des cas d’utilisation d’analyses. Cette mesure (également appelée méthodologie de comptabilisation) devient le dénominateur du calcul de l’effet élévateur. Elle affecte également la manière dont les données sont agrégées avant l’application du calcul du degré de confiance. |
| Mesures de succès | Sélectionnez jusqu’à 3 événements de réussite standard (non calculés) dans les listes déroulantes ou faites glisser les mesures depuis le rail de gauche. Chaque mesure comporte un tableau et une visualisation dédiés dans le panneau rendu. |
| Période du calendrier | Cette variable est automatiquement renseignée en fonction de la plage de dates d’Activité, à partir de l’Adobe Target. Vous pouvez le modifier, si nécessaire. |

![Générateur de panneau](assets/a4t-panel-builder2.png)

## Sortie de panneau {#Output}

Le panneau Analytics for Cible renvoie un riche ensemble de données et de visualisations pour vous aider à mieux comprendre les performances de votre activité d’Adobe Target et de vos expériences. En haut du panneau, une ligne de résumé vous rappelle les paramètres du panneau que vous avez sélectionnés. A tout moment, vous pouvez modifier le panneau en cliquant sur le crayon de modification en haut à droite.

Pour chaque mesure de réussite sélectionnée, un tableau à structure libre et une tendance de taux de conversion s’affichent :

![Rendu](assets/a4t-rendered.png)


Chaque tableau à structure libre affiche les colonnes de mesures suivantes :

| Mesure | Description |
|---|---|
| Normalisation des mesures | Impressions d’Visiteurs, de visites ou d’Activités uniques. |
| Mesure de succès | Mesure sélectionnée dans le créateur |
| Taux de conversion | Mesure de réussite/normalisation |
| Effet élévateur | Compare le taux de conversion de chaque expérience à l’expérience de contrôle.<br>**Remarque :**L’effet élévateur est une &quot;mesure verrouillée&quot; des expériences de Cible ; il ne peut pas être ventilé ou utilisé avec d&#39;autres dimensions. |
| Effet élévateur (inférieur) | Représente le pire lift qu’une expérience de variante pourrait avoir sur l’expérience de contrôle. |
| Effet élévateur (médian) | Représente le lift moyen qu’une variante de l’expérience pourrait avoir sur le contrôle, avec un intervalle de confiance de 95%. &quot;Effet élévateur&quot; dans les rapports et Analytics. |
| Effet élévateur (supérieur) | Représente le meilleur lift qu’une expérience de variante pourrait avoir sur l’expérience de contrôle. |
| Degré de confiance | Le test en t des étudiants calcule le niveau de confiance, ce qui indique la probabilité que les résultats soient dupliqués si le test était exécuté de nouveau. Une plage de mise en forme conditionnelle fixe de 75 %/85 %/95 % a été appliquée à la mesure. Cette mise en forme peut être personnalisée si nécessaire sous Paramètres de colonne. <br>**Remarque :**La confiance est une &quot;mesure verrouillée&quot; des expériences de Cible ; il ne peut pas être ventilé ou utilisé avec d&#39;autres dimensions. |

Comme pour n’importe quel panneau de l’Analysis Workspace, vous pouvez continuer votre analyse en ajoutant des tableaux et [visualisations](https://docs.adobe.com/content/help/fr-FR/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html) supplémentaires qui vous aideront à analyser vos activités d’Adobe Target.

## Questions fréquentes {#FAQ}

| Question | Réponse |
|---|---|
| Quels types d’activité sont pris en charge dans A4T ? | [En savoir plus](https://docs.adobe.com/content/help/en/target/using/integrate/a4t/a4t-faq/a4t-faq-activity-setup.html) sur les types d’activité pris en charge. |
| Les mesures calculées sont-elles prises en charge dans les calculs d’effet élévateur et de fiabilité ? | Non. [En savoir plus](https://docs.adobe.com/content/help/en/target/using/integrate/a4t/a4t-faq/a4t-faq-lift-and-confidence.html) sur les raisons pour lesquelles les mesures calculées ne sont pas prises en charge dans l’effet élévateur et la fiabilité. Les mesures calculées peuvent toutefois être utilisées dans un rapports A4T en dehors de ces mesures. |
| Pourquoi les visiteurs uniques varieraient-ils entre la Cible et le Analytics ? | [En savoir plus](https://docs.adobe.com/content/help/en/target/using/integrate/a4t/a4t-faq/a4t-faq-viewing-reports.html) sur les écarts de visiteurs uniques entre les produits. |
| Lorsque j’applique un segment d’accès pour une activité de Cible spécifique dans mon analyse, pourquoi est-ce que les expériences sans rapport sont renvoyées ? | La dimension A4T est une variable de liste, ce qui signifie qu’elle peut contenir de nombreuses activités (et expériences) en même temps. [En savoir plus](https://docs.adobe.com/content/help/en/target/using/integrate/a4t/a4t-faq/a4t-faq-viewing-reports.html) |
| La mesure de confiance tient-elle compte des commandes extrêmes ou applique-t-elle une correction Bonferroni pour plusieurs offres ? | Non. [En savoir plus](https://docs.adobe.com/content/help/en/target/using/integrate/a4t/a4t-faq/a4t-faq-lift-and-confidence.html) sur la façon dont Analytics calcule la fiabilité. |

Pour plus d’informations sur Analytics for Cible rapports, consultez le rapports [A4T.](https://docs.adobe.com/content/help/en/target/using/integrate/a4t/reporting.html)
