---
title: Fonctionnement des relectures
description: Comprendre le concept de « relecture » dans les analyses entre appareils
translation-type: tm+mt
source-git-commit: f3f5f82a236d376eda07d4d39e7effa60e929499
workflow-type: tm+mt
source-wordcount: '589'
ht-degree: 92%

---


# Fonctionnement des relectures

Analytics sur l’ensemble des appareils effectue deux transitions de données dans une suite de rapports virtuelle :

* **groupement en direct** : l’analyse entre appareils tente de grouper chaque accès au fur et à mesure. Les nouveaux appareils réseau de la suite de rapports n’ayant jamais été connectés ne sont généralement pas groupés à ce niveau. Les appareils reconnus sont groupés immédiatement.
* **Relecture** : environ une fois par semaine, l’analyse entre appareils « relit » les données en fonction des identifiants uniques appris. C’est à cette étape que les nouveaux appareils de la suite de rapports sont groupés.

## Exemple de tableau

Les tableaux suivants illustrent la façon dont les deux méthodes d’analyse entre appareils ([groupement basé sur les champs](field-based-stitching.md) et [graphique d’appareil](device-graph.md)) calculent le nombre de personnes uniques :

### Groupement en direct

Dès qu’un accès est collecté, l’analyse entre appareils tente de le grouper aux appareils connus. Prenons l’exemple suivant, où Bob utilise deux appareils.

*Données telles qu’elles apparaissent le jour de leur collecte :*

| Horodatage | ECID | evar1 ou CustomerID | Explication de l’accès | Mesure « Personnes » (cumulée) à l’aide du graphique d’appareil | Mesure « Personnes » (cumulée) à l’aide du groupement basé sur les champs |
| --- | --- | --- | --- | --- | --- |
| `1` | `246` | - | Bob sur son ordinateur de bureau, sans authentification | `1` (246) | `1` (246) |
| `2` | `246` | `Bob` | Bob se connecte sur son ordinateur de bureau | `1` (246) | `2` (246 et Bob) |
| `3` | `3579` | - | Bob sur son appareil mobile, sans authentification | `2` (246 et 3579) | `3` (246, Bob et 3579) |
| `4` | `3579` | `Bob` | Bob se connecte sur son appareil mobile | `2` (246 et 3579) | `3` (246, Bob et 3579) |
| `5` | `246` | - | Bob accède à nouveau à votre site depuis son ordinateur de bureau, sans authentification | `2` (246 et 3579) | `3` (246, Bob et 3579) |
| `6` | `246` | `Bob` | Bob se connecte à nouveau sur son ordinateur de bureau | `2` (246 et 3579) | `3` (246, Bob et 3579) |
| `7` | `3579` | - | Bob accède à nouveau à votre site depuis son appareil mobile | `2` (246 et 3579) | `3` (246, Bob et 3579) |
| `8` | `3579` | `Bob` | Bob se connecte à nouveau sur son appareil mobile | `2` (246 et 3579) | `3` (246, Bob et 3579) |

Les accès authentifiés et non authentifiés sur les nouveaux appareils sont (temporairement) comptabilisés comme des personnes distinctes.

* **Si vous utilisez le graphique d’appareil**, les accès non authentifiés sur les appareils reconnus sont groupés en direct une fois qu’une grappe est publiée par le graphique d’appareil. La publication d’une grappe prend entre trois heures et deux semaines.

   Lorsqu’une grappe est publiée, une troisième personne cumulative est également ajoutée. Cette troisième personne représente la grappe elle-même, en plus des différents appareils. Cette troisième « personne » reste jusqu’à la relecture des données.

   L’attribution ne fonctionne pas sur tous les appareils tant qu’une grappe n’a pas été publiée et, même en cas de publication, elle ne fonctionne qu’à partir de ce moment-là. Dans l’exemple ci-dessus, aucun accès n’a été groupé sur les appareils. L’attribution entre appareils sur les accès existants ne fonctionne qu’après le groupement de relecture.
* **Si vous utilisez le groupement basé sur les champs**, les accès non authentifiés sur des appareils reconnus sont groupés en direct à partir de ce moment-là.

   L’attribution fonctionne dès que la variable personnalisée d’identification est liée à un appareil. Dans l’exemple ci-dessus, tous les accès sauf l’accès 1 et l’accès 3 sont groupés en direct (ils utilisent tous l’identifiant `Bob`). L’attribution fonctionne sur les accès 1 et 3 après le groupement de relecture.

### Groupement de relecture

La relecture se produit tous les jours ou toutes les semaines, selon la façon dont vous avez demandé la configuration de CDA. Au cours de la relecture, CDA tente de retraiter les données historiques dans une fenêtre de recherche en amont définie :

* La relecture quotidienne utilise une fenêtre de recherche en amont d’un jour.
* La relecture hebdomadaire utilise une fenêtre de recherche en amont de 7 jours.

Si un appareil envoie des données alors qu’il n’est pas authentifié, puis se connecte, l’analyse entre appareils associe ces accès non authentifiés à la bonne personne. Le tableau suivant représente les mêmes données que ci-dessus, mais affiche des nombres différents à cause de la relecture des données.

*Les mêmes données après relecture :*

| Horodatage | ECID | evar1 ou CustomerID | Explication de l’accès | Mesure « Personnes » (cumulée) à l’aide du graphique d’appareil | Mesure « Personnes » (cumulée) à l’aide du groupement basé sur les champs |
| --- | --- | --- | --- | --- | --- |
| `1` | `246` | - | Bob sur son ordinateur de bureau, sans authentification | `1` (grappe 1) | `1` (Bob) |
| `2` | `246` | `Bob` | Bob se connecte sur son ordinateur de bureau | `1` (grappe 1) | `1` (Bob) |
| `3` | `3579` | - | Bob sur son appareil mobile, sans authentification | `1` (grappe 1) | `1` (Bob) |
| `4` | `3579` | `Bob` | Bob se connecte sur son appareil mobile | `1` (grappe 1) | `1` (Bob) |
| `5` | `246` | - | Bob accède à nouveau à votre site depuis son ordinateur de bureau, sans authentification | `1` (grappe 1) | `1` (Bob) |
| `6` | `246` | `Bob` | Bob se connecte à nouveau sur son ordinateur de bureau | `1` (grappe 1) | `1` (Bob) |
| `7` | `3579` | - | Bob accède à nouveau à votre site depuis son appareil mobile | `1` (grappe 1) | `1` (Bob) |
| `8` | `3579` | `Bob` | Bob se connecte à nouveau sur son appareil mobile | `1` (grappe 1) | `1` (Bob) |
