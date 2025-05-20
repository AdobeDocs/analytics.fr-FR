---
description: Les mesures calculées et les mesures calculées avancées sont des mesures personnalisées que vous pouvez créer à partir de mesures existantes.
keywords: Mesures calculées ; mesures calculées avancées
title: Mesures calculées et mesures calculées avancées
feature: Calculated Metrics
exl-id: 9bf8239f-cf74-4feb-85e5-d47805e90afb
source-git-commit: 08e29da4847e8ef70bd4435949e26265d770f557
workflow-type: ht
source-wordcount: '552'
ht-degree: 100%

---

# Mesures calculées et mesures calculées avancées

Les mesures calculées et les mesures calculées avancées sont des mesures personnalisées que vous pouvez créer à partir de mesures existantes.

Nos outils de mesures calculées offrent un moyen bien plus souple pour créer, gérer et organiser les mesures. Ils vous permettent, en tant que spécialistes marketing, chefs de produits et analystes, de poser des questions relatives aux données sans avoir à modifier votre implémentation [!DNL Analytics]. Les mesures personnalisées disponibles dans chaque package [!DNL Analytics] sont les suivantes :

* Adobe [!DNL Analytics] Foundation : calculées
* [Adobe Analytics Select](https://www.adobe.com/fr/data-analytics-cloud/analytics/select.html) : calculées + calculées avancées
* [Adobe Analytics Prime](https://www.adobe.com/fr/data-analytics-cloud/analytics/prime.html) : calculées + calculées avancées
* [Adobe Analytics Ultimate](https://www.adobe.com/fr/data-analytics-cloud/analytics/ultimate.html) : calculées + calculées avancées

Dans le tableau ci-dessous, vous trouverez une comparaison des fonctionnalités des mesures calculées et des mesures calculées avancées :

| Options du créateur | Mesures calculées | Mesures calculées avancées |
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

* Créez des mesures dans [!UICONTROL Analysis Workspace], [!UICONTROL Report Builder], [!UICONTROL Détection des anomalies] et [!UICONTROL Analyse des contributions].
* Créer des mesures segmentées qui sont dérivées au moment de l’exécution du rapport, sans avoir à modifier l’implémentation. Elles peuvent être consultées de manière historique car elles sont basées sur des segments.


>[!BEGINSHADEBOX]

Consultez ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Mesures calculées](https://video.tv.adobe.com/v/25407?quality=12&learn=on){target="_blank"} pour une vidéo de démonstration.

>[!ENDSHADEBOX]

* Partagez des mesures dans l’ensemble des suites de rapports. Cela signifie que toutes les mesures nouvellement créées s’appliquent à toutes les suites de rapports de la même société de connexion.
* (Mesures calculées avancées uniquement) Segmenter sur les mesures. Par exemple, vous pouvez créer une mesure « Nouveaux visiteurs ou nouvelles visiteuses », avec un décompte des personnes pour lesquelles il s’agit de la première session.

* (Mesures calculées avancées uniquement) Incorporer les fonctions statistiques afin de vous aider à mieux décrire vos données. Par exemple, vous pouvez comptabiliser le nombre d’éléments d’un rapport ou ajouter le nombre d’écarts types pour chaque élément.


>[!BEGINSHADEBOX]

Consultez ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Mesures calculées segmentées dans les segments](https://video.tv.adobe.com/v/25409?quality=12&learn=on){target="_blank"} pour une vidéo de démonstration.

>[!ENDSHADEBOX]


## Limites {#section_CB878B02451541D68A68B508D4DBD19A}

Certaines fonctions d’[!DNL Analytics] permettent d’utiliser des événements, mais pas des mesures calculées :

* [!UICONTROL Abandons] dans [!UICONTROL Analysis Workspace]
* [!UICONTROL Analyse de cohortes] dans Analysis Workspace
* [!UICONTROL Data Warehouse]
* [!UICONTROL Segments]
* [!DNL Analytics] for [!DNL Target]

## Outils {#section_D65E9C067E9C45E1A50DD30F50561BB2}

Voici une brève vue d’ensemble des outils de [!UICONTROL mesures calculées] :

| Outil | Fonctionnalités |
|--- |--- |
| Créateur de mesures calculées | <ul><li>Créer des mesures calculées et calculées avancées à l’aide des modèles d’affectation avancés.</li><li>Ajouter des segments intégrés aux formules de mesure.</li><li>Comparer des segments dans le même rapport. Par exemple, comparer les visiteurs locaux et les visiteurs internationaux.</li><li>Utiliser les fonctions statistiques.</li><li>Fournir des descriptions de mesure détaillées (indiquer ce que la mesure fait, où l’utiliser, où NE PAS l’utiliser).</li><li>Copier des définitions dans les nouvelles mesures.</li><li>Fournir une vue d’ensemble des mesures intégrées.</li><li>Définir la polarité de la mesure qui indique si, lorsqu’un événement personnalisé (mesure) donné s’accroît, il s’agit un événement positif ou négatif.</li><li>Baliser les mesures.</li></ul> |
| Gestionnaire de mesures calculées | <ul><li>Partager des mesures avec d’autres personnes&lt;/li<li>Approuver et organiser les mesures.</li><li>Organiser (baliser) vos mesures afin que les personnes puissent les trouver.</li><li>Supprimer des mesures.</li><li>Renommer des mesures.</li></ul> |
| Rail Sélecteur de mesure | Cela permet de rechercher et d’ajouter/appliquer des mesures au rapport. Vous pouvez également modifier l’ordre de tri (les options sont : Alphabétique, Recommandés, Fréquemment utilisés, Récemment utilisés). En outre, vous pouvez filtrer les suites de rapports pour n’afficher que les mesures créées dans une suite de rapports spécifique. Pour accéder à ce sélecteur de mesure, cliquez sur l’icône Mesures située à gauche d’un rapport. |
| API pour les mesures calculées | Partie du jeu d’API d’Adobe Analytics 2.0. |
