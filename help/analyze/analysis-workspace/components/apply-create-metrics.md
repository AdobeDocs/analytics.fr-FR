---
description: Dans Analysis Workspace, vous pouvez utiliser les mesures de deux façons.
title: Mesures dans Analysis Workspace
feature: Metrics
role: User, Admin
exl-id: 0a5dc709-c4e8-412a-a6cf-37b85d811f65
source-git-commit: c1b679dab7b66754ae4b6fd7503243f40d0f2178
workflow-type: ht
source-wordcount: '416'
ht-degree: 100%

---

# Mesures

Les mesures vous permettent de quantifier les points de données dans Analysis Workspace. Elles sont généralement utilisées comme colonnes dans une visualisation et liées aux dimensions.

## Types de mesures

Adobe propose plusieurs types de mesures à utiliser dans Analysis Workspace :

* **Mesures standard** : la plupart des mesures que vous utilisez dans les projets sont des mesures standard. Exemples : [Pages vues](/help/components/metrics/page-views.md), [Revenu](/help/components/metrics/revenue.md)ou [Événements personnalisés](/help/components/metrics/custom-events.md). Pour plus d’informations, consultez la section [Vue d’ensemble des mesures](/help/components/metrics/overview.md) du guide d’utilisation des composants.

  ![Mesure standard](assets/standard-metric.png)

* **Mesures calculées** : mesures définies par l’utilisateur ou l’utilisatrice et basées sur des mesures standard, des nombres statiques ou des fonctions algorithmiques. Les mesures calculées définies par l’utilisateur ou l’utilisatrice affichent une icône de calculateur dans la liste des composants disponibles. Pour plus d’informations, consultez la section [Vue d’ensemble des mesures calculées](/help/components/c-calcmetrics/cm-overview.md) du guide d’utilisation des composants.

  ![Mesure calculée](assets/calculated-metric.png)

* **Modèles de mesures calculées** : mesures définies par Adobe qui se comportent de la même manière que les mesures calculées. Vous pouvez les utiliser tels quels dans les projets Workspace ou enregistrer une copie pour personnaliser sa logique. Les modèles de mesures calculées affichent une icône Adobe dans la liste des composants disponibles.

  ![Modèle de mesure calculée](assets/calculated-metric-template.png)

## Utilisation des mesures de dans Analysis Workspace

Les mesures peuvent être utilisées de différentes manières dans Analysis Workspace. Vous pouvez :

* Faire glisser une mesure vers un tableau à structure libre vide pour afficher les tendances de cette mesure sur la période du projet.

* Faire glisser une mesure lorsqu’une dimension est présente pour la comparer à chaque élément de la dimension.

* Faire glisser une mesure au-dessus d’un en-tête de mesure existant pour le remplacer.

* Faire glisser une mesure près d’un en-tête pour afficher les deux côte à côte.

>[!VIDEO](https://video.tv.adobe.com/v/40817/?quality=12)

## Mesures calculées

Les mesures calculées vous permettent de voir facilement comment les mesures sont liées les unes aux autres à l’aide d’opérateurs simples ou de fonctions statistiques. Il existe plusieurs façons de créer des mesures calculées.

* Cliquez sur l’icône « + » près de l’en-tête des mesures sous la liste des composants à gauche.
* Accédez à **[!UICONTROL Composants]** > **[!UICONTROL Mesures calculées]** > **[!UICONTROL Ajouter]**.
* Cliquez avec le bouton droit sur un en-tête de colonne > **[!UICONTROL Créer une mesure à partir d’une sélection]** lorsqu’une ou plusieurs cellules de colonne d’en-tête sont sélectionnées. Cette option crée automatiquement une mesure calculée pour vous sans avoir à utiliser le créateur de règles de mesures calculées.

[Mesures calculées : mesures sans implémentation](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/components/calculated-metrics/calculated-metrics-implementationless-metrics.html?lang=fr) (3:42)

## Comparaison de mesures avec différents modèles d’attribution

Si vous souhaitez comparer rapidement et facilement deux modèles d’attribution, faites un clic droit sur une mesure et sélectionnez **[!UICONTROL Comparer les modèles d’attribution]** :

![Comparer l’attribution](assets/compare-attribution.png)

Ce raccourci vous permet de comparer rapidement et facilement deux modèles d’attribution sans faire glisser une mesure et la configurer deux fois.

## Utilisation de la fonction [!UICONTROL moyenne cumulée] pour appliquer le lissage des mesures

Regardez une vidéo sur ce sujet :

>[!VIDEO](https://video.tv.adobe.com/v/27068/?quality=12)
