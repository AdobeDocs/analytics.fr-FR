---
description: Classez l’activité des liens à l’aide de superpositions visuelles afin de surveiller l’engagement de l’audience de vos pages web.
title: Activity Map - Aperçu
feature: Activity Map
role: User, Admin
exl-id: 30a800f7-e2c8-443e-b5d4-36834ef0ba20
source-git-commit: 72b38970e573b928e4dc4a8c8efdbfb753be0f4e
workflow-type: tm+mt
source-wordcount: '628'
ht-degree: 4%

---

# Vue d’ensemble d’Activity Map

Adobe Analytics Activity Map est une fonctionnalité d’Adobe Analytics qui fournit une représentation visuelle de l’engagement des utilisateurs et utilisatrices sur les pages web et les applications mobiles. Il permet aux spécialistes du marketing et aux analystes de suivre et d’analyser les interactions utilisateur, telles que les clics et le comportement de défilement. Activity Map génère des cartes thermiques et des rapports de superposition qui présentent les éléments les plus populaires d’une page web, ce qui vous permet d’optimiser vos expériences numériques.

Cette section de la documentation porte sur la superposition Activity Map. Cependant, il existe d’autres parties importantes à l’utilisation d’Activity Map :

* **Paramètre de suite de rapports** : un Activity Map doit être activé dans une suite de rapports. Voir [Création de rapports Activity Map](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/activity-map.md) dans les paramètres de la suite de rapports.
* **Mise en oeuvre** : la plupart des rapports Activity Map sont disponibles prêts à l’emploi. Cependant, certains sites web peuvent nécessiter une mise en oeuvre supplémentaire pour tirer le meilleur parti du suivi des liens. Les variables de mise en oeuvre suivantes sont disponibles :
   * [`ActivityMap.linkExclusions`](/help/implement/vars/config-vars/activitymap-linkexclusions.md) : filtrez les données de clic par nom de lien.
   * [`ActivityMap.regionExclusions`](/help/implement/vars/config-vars/activitymap-regionexclusions.md) : filtrez les données de clic par nom de région.
   * [`ActivityMap.regionIDAttribute`](/help/implement/vars/config-vars/activitymap-regionidattribute.md) : modifiez l’attribut qui renseigne la dimension Région Activity Map.
   * [`ActivityMap.link`](/help/implement/vars/functions/activitymap-link.md) : personnalisez la logique utilisée par l’Activity Map pour renseigner la dimension Lien Activity Map .
   * [`ActivityMap.region`](/help/implement/vars/functions/activitymap-region.md) : personnalisez la logique utilisée par l’Activity Map pour renseigner la dimension Région Activity Map.
* **Dimensions** : en plus de l’extension de superposition, Activity Map fournit plusieurs dimensions que vous pouvez utiliser dans Analysis Workspace.
   * [Lien Activity Map](/help/components/dimensions/activity-map-link.md) : nom du lien sur lequel l’utilisateur a cliqué.
   * [Région Activity Map](/help/components/dimensions/activity-map-region.md) : nom de région sur lequel l’utilisateur a cliqué.
   * [Page Activity Map](/help/components/dimensions/activity-map-page.md) : nom de page au moment où vous avez cliqué sur le lien.
   * [Lien Activity Map par région](/help/components/dimensions/activity-map-link-by-region.md) : valeur concaténée de lien Activity Map et de région Activity Map.

## Fonctionnalités et avantages

* **Visualisation de l’engagement des utilisateurs** : Activity Map offre une représentation visuelle dynamique du comportement des utilisateurs, ce qui vous permet de voir exactement où les utilisateurs cliquent. Ces données visuelles permettent d’identifier plus facilement des schémas, des tendances et des centres d’intérêt. Vous pouvez ensuite prendre des décisions éclairées concernant la conception, le placement du contenu et le flux d’utilisateurs.

* **Cartes thermiques** : l’Activity Map génère des cartes thermiques qui affichent les zones les plus cliquées ou interactives d’une page web. Les cartes thermique utilisent un codage par couleur pour représenter le niveau d’engagement, ce qui vous permet d’identifier les zones réactives et de privilégier l’attention aux zones à fort impact. Ces informations peuvent s’avérer utiles pour optimiser les boutons d’appel à l’action, les liens, les formulaires ou tout autre élément interactif.

* **Rapports de superposition** : les rapports de superposition dans Activity Map fournissent des mesures de clics détaillées pour des éléments spécifiques d’une page web. En comprenant les taux de clics publicitaires et les niveaux d’engagement de chaque élément, vous pouvez affiner votre conception et vos stratégies de contenu afin d’améliorer les expériences utilisateur.

* **Analyse de segment** : vous pouvez analyser le comportement des utilisateurs en fonction de différents segments, tels que les sources de trafic, les données démographiques ou les personas. En segmentant les données, vous pouvez découvrir des informations précieuses sur des groupes d’utilisateurs spécifiques, ce qui permet d’offrir des expériences personnalisées et des stratégies marketing ciblées.

## Applications pratiques

* **Optimisation du site web** : Activity Map vous aide à optimiser vos sites web en identifiant les éléments peu performants, en améliorant la navigation et en améliorant l’expérience globale de l’utilisateur. En analysant les interactions utilisateur, vous pouvez prendre des décisions pilotées par les données afin de rationaliser les flux utilisateur, de simplifier les formulaires ou d’ajuster le placement de contenu pour un impact maximal.

* **Optimisation du taux de conversion** : en visualisant l’engagement des utilisateurs et en analysant les taux de clics publicitaires, l’Activity Map joue un rôle essentiel dans les efforts CRO. Vous pouvez identifier les obstacles à la conversion et tester différentes variations de conception afin d’optimiser les entonnoirs de conversion, les pages d’entrée et les processus de passage en caisse.

* **Test A/B** : l’Activity Map peut être combiné avec un test A/B pour mesurer l’impact des modifications de conception ou de contenu. En comparant les mesures d’engagement entre différentes versions d’une page web, vous pouvez déterminer les variations qui génèrent un engagement des utilisateurs, des taux de conversion ou des recettes plus élevés.

* **Optimisation des applications mobiles** : l’Activity Map ne se limite pas aux sites web ; il étend également ses fonctionnalités aux applications mobiles. Vous pouvez obtenir des informations sur les interactions utilisateur dans les applications, ce qui leur permet d’améliorer la convivialité, d’améliorer la navigation et d’affiner les fonctionnalités pour une expérience mobile transparente.
