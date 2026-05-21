---
description: Classez l’activité des liens à l’aide de recouvrements visuels pour surveiller l’engagement du public de vos pages web.
title: Activity Map - Aperçu
feature: Activity Map
role: User, Admin
exl-id: 30a800f7-e2c8-443e-b5d4-36834ef0ba20
TQID: https://experienceleague.adobe.com/1-o8wAr6cY8jSR2facQEvh--wvXByJf6R01r4RcVEhI
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
  - id: c069c44e-5426-4c1a-accc-8028662f2fde
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
  - id: fab61dd8-112a-4e5e-ad5f-fb0240b7a60b
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 634
ht-degree: 100%

---

# Vue d’ensemble d’Activity Map

Adobe Analytics Activity Map est une fonctionnalité d’Adobe Analytics qui fournit une représentation visuelle de l’engagement des utilisateurs et utilisatrices sur les pages web et les applications mobiles. Elle permet aux spécialistes du marketing et de l’analyse de suivre et d’analyser les interactions des utilisateurs et utilisatrices, telles que les clics et le comportement de défilement. Activity Map génère des cartes thermiques et des rapports de recouvrement qui affichent les éléments les plus populaires sur une page web, ce qui vous permet d’optimiser vos expériences numériques.

Le concept d’Activity Map se compose de plusieurs composants importants :

* **Paramètre de suite de rapports** : Activity Map doit être activé pour une suite de rapports avant de pouvoir commencer à l’utiliser. Consultez [Rapports Activity Map](/help/admin/tools/manage-rs/edit-settings/activity-map.md) dans les paramètres de la suite de rapports.
* **Implémentation** : la plupart des rapports Activity Map sont disponibles et prêts à l’emploi. Cependant, certains sites web peuvent nécessiter une implémentation supplémentaire pour tirer le meilleur parti du suivi des liens. Les variables de mise en œuvre suivantes sont disponibles :
   * [`ActivityMap.linkExclusions`](/help/implement/vars/config-vars/activitymap-linkexclusions.md) : filtrez les données de clics par nom de lien.
   * [`ActivityMap.regionExclusions`](/help/implement/vars/config-vars/activitymap-regionexclusions.md) : filtrez les données de clics par nom de région.
   * [`ActivityMap.regionIDAttribute`](/help/implement/vars/config-vars/activitymap-regionidattribute.md) : modifiez l’attribut qui renseigne la dimension Région d’Activity Map.
   * [`ActivityMap.link`](/help/implement/vars/functions/activitymap-link.md) : personnalisez la logique utilisée par Activity Map pour renseigner la dimension Lien Activity Map.
   * [`ActivityMap.region`](/help/implement/vars/functions/activitymap-region.md) : personnalisez la logique utilisée par Activity Map pour renseigner la dimension Région Activity Map.
* **Recouvrement** : extension de navigateur qui vous permet d’afficher les données de clic superposées sur votre site web. Consultez [Interface de l’extension Activity Map](overlay/overview.md) pour plus d’informations. Cette fonctionnalité n’est pas disponible pour les implémentations du SDK web.
* **Dimensions** : en plus de l’extension de recouvrement, Activity Map fournit plusieurs dimensions que vous pouvez utiliser dans Analysis Workspace.
   * [Lien Activity Map](/help/components/dimensions/activity-map-link.md) : nom du lien sur lequel la personne a cliqué.
   * [Région Activity Map](/help/components/dimensions/activity-map-region.md) : nom de la région sur laquelle la personne a cliqué.
   * [Page Activity Map](/help/components/dimensions/activity-map-page.md) : nom de la page au moment où la personne a cliqué sur le lien.
   * [Lien Activity Map par région](/help/components/dimensions/activity-map-link-by-region.md) : valeur concaténée du lien Activity Map et de la région Activity Map.

## Fonctionnalités et avantages

* **Visualisation de l’interaction client** : Activity Map offre une représentation visuelle dynamique du comportement de la personne, ce qui vous permet de voir exactement où cliquent les utilisateurs et utilisatrices. Ces données visuelles permettent d’identifier plus facilement les modèles, les tendances et les zones d’intérêt. Vous pouvez ensuite prendre des décisions éclairées concernant la conception, l’emplacement du contenu et le flux des utilisateurs et utilisatrices.

* **Cartes thermiques** : Activity Map génère des cartes thermiques qui affichent les zones ayant fait l’objet du maximum de clics ou d’interactions d’une page web. Les cartes thermiques utilisent un codage par couleur pour représenter le niveau d’engagement. Cela vous permet d’identifier les zones les plus actives et de concentrer votre attention sur celles à fort impact. Ces informations peuvent s’avérer très utiles pour optimiser les boutons d’appel à l’action, les liens, les formulaires ou tout autre élément interactif.

* **Rapports de recouvrement** : les rapports de recouvrement dans Activity Map fournissent des mesures de clics détaillées pour des éléments spécifiques d’une page web. En comprenant les taux de clics publicitaires et les niveaux d’engagement des éléments individuels, vous pouvez affiner votre conception et vos stratégies de contenu afin d’améliorer les expériences clientèle. Cette fonctionnalité n’est pas disponible pour les implémentations du SDK web.

* **Analyse des segments** : vous pouvez analyser le comportement des utilisateurs et utilisatrices en fonction de différents segments, tels que les sources de trafic, les données démographiques ou les rôles. En segmentant les données, vous pouvez découvrir des informations précieuses sur des groupes d’utilisateurs et d’utilisatrices spécifiques. Cela permet d’offrir des expériences personnalisées et des stratégies marketing ciblées.

## Applications pratiques

* **Optimisation des sites web** : Activity Map vous aide à optimiser vos sites web en identifiant les éléments peu performants, en améliorant la navigation et l’expérience clientèle globale. En analysant les interactions des utilisateurs et utilisatrices, vous pouvez prendre des décisions pilotées par les données afin de rationaliser les flux d’utilisation, de simplifier les formulaires ou d’ajuster le placement de contenu pour un impact maximal.

* **Optimisation du taux de conversion** : en visualisant l’engagement des utilisateurs et utilisatrices et en analysant les taux de clics publicitaires, Activity Map joue un rôle essentiel dans les efforts CRO. Vous pouvez identifier les obstacles à la conversion et expérimenter différentes variations de conception afin d’optimiser les entonnoirs de conversion, les pages de destination et les processus de passage en caisse.

* **Tests A/B** : Activity Map peut être combiné avec des tests A/B pour mesurer l’impact des modifications de conception ou de contenu. En comparant les mesures d’engagement entre différentes versions d’une page web, vous pouvez déterminer les variations qui génèrent un engagement des utilisateurs et utilisatrices, des taux de conversion ou des recettes plus élevés.

