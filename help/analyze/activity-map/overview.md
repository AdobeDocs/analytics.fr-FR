---
description: Classez l’activité des liens à l’aide de superpositions visuelles pour surveiller l’engagement du public de vos pages web.
title: Activity Map - Aperçu
feature: Activity Map
role: User, Admin
exl-id: 30a800f7-e2c8-443e-b5d4-36834ef0ba20
source-git-commit: dee8f0a13a159f4c7902d2ccddd8848c4016b471
workflow-type: tm+mt
source-wordcount: '586'
ht-degree: 5%

---

# Vue d’ensemble d’Activity Map

Adobe Analytics Activity Map est une fonctionnalité d’Adobe Analytics qui fournit une représentation visuelle de l’engagement des utilisateurs et utilisatrices sur les pages web et les applications mobiles. Il permet aux spécialistes du marketing et aux analystes de suivre et d’analyser les interactions utilisateur, telles que les clics et le comportement de défilement. Activity Map génère des cartes thermiques et des rapports de recouvrement qui affichent les éléments les plus populaires sur une page web, ce qui vous permet d’optimiser vos expériences digitales.

Cette section de la documentation porte sur la superposition Activity Map. Cependant, l’utilisation d’Activity Map comporte d’autres aspects importants :

* **Paramètre de suite de rapports** : Activity Map doit être activé pour une suite de rapports. Voir [Rapports Activity Map](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/activity-map.md) dans les paramètres de la suite de rapports.
* **Implémentation** : la plupart des rapports Activity Map sont disponibles prêts à l’emploi. Cependant, certains sites web peuvent nécessiter une implémentation supplémentaire pour tirer le meilleur parti du suivi des liens. Les variables d’implémentation suivantes sont disponibles :
   * [`ActivityMap.linkExclusions`](/help/implement/vars/config-vars/activitymap-linkexclusions.md) : filtrez les données de clics par nom de lien.
   * [`ActivityMap.regionExclusions`](/help/implement/vars/config-vars/activitymap-regionexclusions.md) : filtrez les données de clics par nom de région.
   * [`ActivityMap.regionIDAttribute`](/help/implement/vars/config-vars/activitymap-regionidattribute.md) : modifiez l’attribut qui renseigne la dimension Région d’Activity Map .
   * [`ActivityMap.link`](/help/implement/vars/functions/activitymap-link.md) : personnalisez la logique utilisée par Activity Map pour renseigner la dimension Lien Activity Map .
   * [`ActivityMap.region`](/help/implement/vars/functions/activitymap-region.md) : personnalisez la logique utilisée par Activity Map pour renseigner la dimension Région Activity Map .
* **Dimensions** : en plus de l’extension de recouvrement, Activity Map fournit plusieurs dimensions que vous pouvez utiliser dans Analysis Workspace.
   * [Lien Activity Map ](/help/components/dimensions/activity-map-link.md) : nom du lien sur lequel l&#39;utilisateur a cliqué.
   * [Région Activity Map ](/help/components/dimensions/activity-map-region.md) : nom de la région sur laquelle l’utilisateur a cliqué.
   * [Page Activity Map ](/help/components/dimensions/activity-map-page.md) : nom de la page au moment où l’utilisateur a cliqué sur le lien.
   * [Lien Activity Map par région ](/help/components/dimensions/activity-map-link-by-region.md) : valeur concaténée du lien Activity Map et de la région Activity Map.

## Fonctionnalités et avantages

* **Visualisation de l’interaction client** : Activity Map offre une représentation visuelle dynamique du comportement de l’utilisateur, ce qui vous permet de voir exactement où cliquent les utilisateurs et utilisatrices. Ces données visuelles permettent d’identifier plus facilement les modèles, les tendances et les zones d’intérêt. Vous pouvez ensuite prendre des décisions éclairées concernant la conception, l’emplacement du contenu et le flux des utilisateurs.

* **Cartes thermiques** : Activity Map génère des cartes thermiques qui affichent les zones les plus cliquées ou ayant le plus interagi sur une page web. Les cartes thermiques utilisent un codage par couleur pour représenter le niveau d’engagement, ce qui vous permet d’identifier les zones réactives et de donner la priorité aux zones à fort impact. Ces informations peuvent s’avérer utiles pour optimiser les boutons, les liens, les formulaires ou tout autre élément interactif de call-to-action.

* **Rapports de recouvrement** : les rapports de recouvrement dans Activity Map fournissent des mesures de clics détaillées pour des éléments spécifiques d’une page web. En comprenant les taux de clics publicitaires et les niveaux d’engagement de chaque élément, vous pouvez affiner votre conception et vos stratégies de contenu pour améliorer les expériences utilisateur.

* **Analyse des segments** : vous pouvez analyser le comportement des utilisateurs et utilisatrices en fonction de différents segments, tels que les sources de trafic, les données démographiques ou les rôles. En segmentant les données, vous pouvez découvrir de précieuses informations sur des groupes d’utilisateurs spécifiques, ce qui permet d’offrir des expériences personnalisées et des stratégies marketing ciblées.

## Applications pratiques

* **Optimisation des sites web** : Activity Map vous aide à optimiser vos sites web en identifiant les éléments peu performants, en améliorant la navigation et en améliorant l’expérience utilisateur globale. En analysant les interactions utilisateur, vous pouvez prendre des décisions basées sur les données afin de rationaliser les flux utilisateur, de simplifier les formulaires ou d’ajuster le positionnement du contenu pour un impact maximal.

* **Optimisation du taux de conversion** : en visualisant l’interaction client et en analysant les taux de clics, Activity Map joue un rôle essentiel dans les efforts de CRO. Vous pouvez identifier les obstacles à la conversion et essayer différentes variantes de conception pour optimiser les entonnoirs de conversion, les pages de destination et les processus de passage en caisse.

* **Tests A/B** : Activity Map peut être associé à des tests A/B pour mesurer l’impact des modifications de conception ou de contenu. En comparant les mesures d’engagement entre différentes versions d’une page web, vous pouvez déterminer quelles variations entraînent une plus grande interaction des utilisateurs, des taux de conversion ou des recettes plus élevés.

