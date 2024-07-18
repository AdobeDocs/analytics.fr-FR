---
description: Les mesures calculées ou calculées avancées (ou dérivées) sont des mesures personnalisées que vous pouvez créer à partir de mesures existantes.
keywords: Mesures calculées;mesures dérivées;mesures calculées avancées
title: Mesures calculées ou calculées avancées (dérivées)
feature: Calculated Metrics
exl-id: 9bf8239f-cf74-4feb-85e5-d47805e90afb
source-git-commit: 93099d36a65ca2bf16fbd6342f01bfecdc8c798e
workflow-type: tm+mt
source-wordcount: '542'
ht-degree: 58%

---

# Mesures calculées ou calculées avancées (dérivées)

Les mesures calculées ou calculées avancées (ou dérivées) sont des mesures personnalisées que vous pouvez créer à partir de mesures existantes.

Nos outils de mesures calculées offrent un moyen bien plus souple pour créer, gérer et organiser les mesures. Ils vous permettent, en tant que spécialistes marketing, chefs de produits et analystes, de poser des questions relatives aux données sans avoir à modifier votre implémentation [!DNL Analytics]. Les mesures personnalisées disponibles dans chaque package [!DNL Analytics] sont les suivantes :

* Adobe [!DNL Analytics] Foundation : calculées
* [Adobe Analytics Select](https://www.adobe.com/fr/data-analytics-cloud/analytics/select.html) : calculées + calculées avancées
* [Adobe Analytics Prime](https://www.adobe.com/fr/data-analytics-cloud/analytics/prime.html) : calculées + calculées avancées
* [Adobe Analytics Ultimate](https://www.adobe.com/fr/data-analytics-cloud/analytics/ultimate.html) : calculées + calculées avancées

Voici une comparaison entre les mesures calculées et les fonctionnalités de mesures calculées avancées :

| Options du créateur | Mesures calculées | Mesures calculées avancées (dérivées) |
|---|---|---|
| [Types de format (décimal, heure, pourcentage, devise)](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md) | Oui | Oui |
| [Modifications d’attribution (par défaut, linéaire, participation, etc.)](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md) | Oui | Oui |
| [Types de mesure (standard, total)](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md) | Oui | Oui |
| Opérateurs de base (ajouter, soustraire, multiplier, diviser) | Oui | Oui |
| [Appliquer les segments](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/metrics-with-segments.md) | Non | Oui |
| [Fonctions de base (décompte, valeur absolue, moyenne, etc.)](/help/components/c-calcmetrics/cm-reference/cm-functions.md) | Non | Oui |
| [Fonctions avancées (régression, si/alors, score normalisé, etc.)](/help/components/c-calcmetrics/cm-reference/cm-adv-functions.md) | Non | Oui |

## Fonctionnalités  {#section_A0A5C275B68A4D628950BBB0B1EE631F}

Vous pouvez

* Créez des mesures dans [!UICONTROL Analysis Workspace], [!UICONTROL Report Builder], [!UICONTROL Détection des anomalies] et [!UICONTROL Analyse des contributions].
* Créer des mesures segmentées qui sont dérivées au moment de l’exécution du rapport, sans avoir à modifier l’implémentation. Elles peuvent être consultées de manière historique car elles sont basées sur des segments.

  >[!VIDEO](https://video.tv.adobe.com/v/25407/?quality=12&learn=on)

* Partagez des mesures dans l’ensemble des suites de rapports. Cela signifie que toutes les mesures nouvellement créées s’appliquent à toutes les suites de rapports de la même société de connexion.
* (Mesures calculées avancées uniquement) Segmenter sur les mesures. Par exemple, vous pouvez créer une mesure « Nouveaux visiteurs », avec un décompte des personnes pour lesquelles il s’agit de la première session.

* (Mesures calculées avancées uniquement) Incorporez des fonctions statistiques pour vous aider à mieux décrire vos données. Par exemple, vous pouvez comptabiliser le nombre d’éléments d’un rapport ou ajouter le nombre d’écarts types pour chaque élément.

  >[!VIDEO](https://video.tv.adobe.com/v/25409/?quality=12&learn=on)

## Limites {#section_CB878B02451541D68A68B508D4DBD19A}

Certaines fonctions d’[!DNL Analytics] permettent d’utiliser des événements, mais pas des mesures calculées :

* [!UICONTROL Abandons] dans [!UICONTROL Analysis Workspace]
* [!UICONTROL Analyse de cohortes] dans Analysis Workspace
* [!UICONTROL Data Warehouse]
* [!UICONTROL Segments]
* [!DNL Analytics] for [!DNL Target]

## Outils {#section_D65E9C067E9C45E1A50DD30F50561BB2}

Voici un bref aperçu des outils [!UICONTROL de mesures calculées] :

| Outil | Fonctionnalités |
|--- |--- |
| Créateur de mesures calculées | <ul><li>Créer des mesures calculées et calculées avancées à l’aide des modèles d’affectation avancés.</li><li>Ajout de segments insérés aux formules de mesure</li><li>Comparer des segments dans le même rapport. Par exemple, comparer les visiteurs locaux et les visiteurs internationaux.</li><li>Utilisation des fonctions statistiques</li><li>Fournir des descriptions de mesure détaillées (indiquer ce qu’il fait, où l’utiliser, où NE PAS l’utiliser)</li><li>Copier des définitions dans de nouvelles mesures</li><li>Fournir un aperçu des mesures intégrées</li><li>Définissez la polarité de la mesure, qui indique si c’est une bonne ou une mauvaise chose qu’un événement personnalisé donné (mesure) augmente.</li><li>Baliser les mesures</li></ul> |
| Gestionnaire de mesures calculées | <ul><li>Partager des mesures avec d’autres&lt;/li<li>Approbation et traitement des mesures</li><li>Organiser (baliser) vos mesures afin que les personnes puissent les trouver</li><li>Suppression de mesures</li><li>Renommer les mesures</li></ul> |
| Rail Sélecteur de mesure | Permet de rechercher et d’ajouter/appliquer des mesures au rapport. Vous pouvez également modifier l’ordre de tri (les options sont : Alphabétique, Recommandés, Fréquemment utilisés, Récemment utilisés). En outre, vous pouvez filtrer selon les suites de rapports pour n’afficher que les mesures créées dans une suite de rapports spécifique.  Pour accéder à ce sélecteur de mesures, cliquez sur l’icône Mesures située à gauche d’un rapport. |
| API pour les mesures calculées | Partie du jeu d’API d’Adobe Analytics 2.0. |