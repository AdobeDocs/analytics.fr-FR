---
title: Fonctionnement des répétitions
description: Comprendre le concept de "relecture" dans l’Analytics sur plusieurs périphériques
translation-type: tm+mt
source-git-commit: 2230fa2c48358346d1d449f2db335ff75c6b1631
workflow-type: tm+mt
source-wordcount: '624'
ht-degree: 1%

---


# Fonctionnement des répétitions

Analytics sur plusieurs périphériques effectue deux passes sur les données dans une suite de rapports virtuelle :

* **Densité** en direct : L’ADC tente d’assembler chaque accès au fur et à mesure. Nettoyez les nouveaux périphériques à la suite de rapports qui n’ont jamais été connectés et ne sont généralement pas assemblés à ce niveau. Les périphériques déjà reconnus sont assemblés immédiatement.
* **Réexécuter**: Environ une fois par semaine, l&#39;ACD &quot;réexamine&quot; les données en fonction des identifiants uniques qu&#39;elle a appris. C&#39;est à cette étape que les nouveaux périphériques de la suite de rapports sont assemblés.

## Exemple de tableau

Les tableaux suivants illustrent comment les deux méthodes CDA (graphique[](field-based-stitching.md) Périphérique et [Field-based stitching](device-graph.md)) calculent le nombre de personnes uniques :

### Accrochage en direct

Dès qu’un accès est collecté, CDA tente de le raccorder à des périphériques connus. Prenons l’exemple suivant, où Bob utilise deux périphériques.

*Données telles qu’elles apparaissent le jour de leur collecte :*

| Horodatage | ECID | eVar1 ou CustomerID | Explication de l’accès | Mesure Personnes (cumulée) à l’aide du graphique de périphériques | Mesure des personnes (cumulative) à l’aide de l’assemblage basé sur les champs |
| --- | --- | --- | --- | --- | --- |
| `1` | `246` | - | Bob sur son ordinateur de bureau, non authentifié | `1` (246) | `1` (246) |
| `2` | `246` | `Bob` | Bob se connecte sur son bureau | `1` (246) | `2` (246 et Bob) |
| `3` | `3579` | - | Bob sur son appareil mobile, non authentifié | `2` (246 et 3579) | `3` (246, Bob et 3579) |
| `4` | `3579` | `Bob` | Bob se connecte sur mobile | `2` (246 et 3579) | `3` (246, Bob et 3579) |
| `5` | `246` | - | Bob accède de nouveau à votre site sur le bureau, sans authentification | `2` (246 et 3579) | `3` (246, Bob et 3579) |
| `6` | `246` | `Bob` | Bob se reconnecte via le bureau | `2` (246 et 3579) | `3` (246, Bob et 3579) |
| `7` | `3579` | - | Bob accède de nouveau à votre site sur mobile | `2` (246 et 3579) | `3` (246, Bob et 3579) |
| `8` | `3579` | `Bob` | Bob se reconnecte via mobile | `2` (246 et 3579) | `3` (246, Bob et 3579) |

Les accès non authentifiés et authentifiés sur les nouveaux périphériques sont comptabilisés comme des personnes distinctes (temporairement).

* **Si vous utilisez le graphique de périphériques,** les accès non authentifiés sur les périphériques reconnus sont assemblés en direct une fois qu’une grappe est publiée par le graphique de périphériques. La publication en grappe dure entre trois heures et deux semaines.

   Une troisième personne cumulative est également ajoutée lorsqu’un cluster est publié. Cette troisième personne représente la grappe elle-même, en plus des différents périphériques. Cette troisième &quot;personne&quot; reste jusqu’à la relecture des données.

   L’attribution ne fonctionne pas sur tous les périphériques tant qu’une grappe n’a pas été publiée, et même après, elle ne fonctionne qu’à partir de ce moment. Dans l’exemple ci-dessus, aucun accès n’est encore assemblé sur plusieurs périphériques. L’attribution sur plusieurs périphériques sur les accès existants ne fonctionne qu’après la reprise de la lecture.
* **Si vous utilisez l’assemblage sur le terrain,** les accès non authentifiés sur des périphériques reconnus sont assemblés en direct à partir de ce moment.

   L’attribution fonctionne dès que la variable personnalisée d’identification se connecte à un périphérique. Dans l’exemple ci-dessus, tous les accès, à l’exception des accès 1 et 3, sont assemblés en direct (ils utilisent tous l’ `Bob` identifiant). L’attribution fonctionne sur les accès 1 et 3 après l’assemblage de relecture.

### Relancer l’assemblage

Environ une fois par semaine, l’ADC recalcule les données historiques en fonction des périphériques qu’elle reconnaît maintenant. Si un périphérique envoie initialement des données alors qu’il n’est pas authentifié, puis se connecte, CDA associe ces accès non authentifiés à la bonne personne. Le tableau suivant représente les mêmes données que ci-dessus, mais affiche des nombres différents en fonction de la relecture des données.

*Les mêmes données après la relecture :*

| Horodatage | ECID | eVar1 ou CustomerID | Explication de l’accès | Mesure Personnes (cumulée) à l’aide du graphique de périphériques | Mesure des personnes (cumulative) à l’aide de l’assemblage basé sur les champs |
| --- | --- | --- | --- | --- | --- |
| `1` | `246` | - | Bob sur son ordinateur de bureau, non authentifié | `1` (Grappe1) | `1` (Bob) |
| `2` | `246` | `Bob` | Bob se connecte sur son bureau | `1` (Grappe1) | `1` (Bob) |
| `3` | `3579` | - | Bob sur son appareil mobile, non authentifié | `1` (Grappe1) | `1` (Bob) |
| `4` | `3579` | `Bob` | Bob se connecte sur mobile | `1` (Grappe1) | `1` (Bob) |
| `5` | `246` | - | Bob accède de nouveau à votre site sur le bureau, sans authentification | `1` (Grappe1) | `1` (Bob) |
| `6` | `246` | `Bob` | Bob se reconnecte via le bureau | `1` (Grappe1) | `1` (Bob) |
| `7` | `3579` | - | Bob accède de nouveau à votre site sur mobile | `1` (Grappe1) | `1` (Bob) |
| `8` | `3579` | `Bob` | Bob se reconnecte via mobile | `1` (Grappe1) | `1` (Bob) |

## Récupérer

* **Si vous utilisez un graphique de périphérique,** les données sont assemblées lorsqu’une grappe est publiée (généralement 3 à 2 semaines).
* **Si vous utilisez l’assemblage basé sur les champs,** les données datant de moins d’une semaine piquent immédiatement les périphériques connus, mais ne rassemble pas immédiatement les périphériques nouveaux ou non reconnus.
* Les données sont relues une fois par semaine et modifient les données historiques dans la suite de rapports virtuelle en fonction des périphériques qu’elle a appris à identifier.
