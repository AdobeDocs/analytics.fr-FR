---
title: Fonctionnement des relectures
description: Comprendre le concept de « relecture » dans Analytics sur plusieurs appareils
exl-id: 0b7252ff-3986-4fcf-810a-438d9a51e01f
feature: CDA
role: Admin
TQID: 'https://experienceleague.adobe.com/UuIRVpQJxJDKTYBg7hlNMlVG4PgGMAoD0NLdJfeQydA'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
  - id: f99536a1-75c7-4151-a2c8-073630632526
    internal-label: CDA
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '501'
ht-degree: 89%
---
# Fonctionnement des relectures

{{available-existing-customers}}

Analytics sur plusieurs appareils effectue deux passages sur les données dans une suite de rapports virtuelle :

* **Assemblage en direct** : l’analyse entre appareils tente de grouper chaque hit au fur et à mesure. Les nouveaux appareils de la suite de rapports qui ne se sont jamais connectés ne sont généralement pas groupés à ce niveau. Les appareils reconnus sont groupés immédiatement.
* **Relecture** : environ une fois par semaine, l’analyse entre appareils « relit » les données en fonction des identifiants uniques appris. C’est à cette étape que les nouveaux appareils de la suite de rapports sont groupés.

## Exemple de tableau

Les tableaux suivants illustrent comment le ([groupement basé sur les champs](field-based-stitching.md) calcule le nombre de personnes uniques :

### Groupement en direct

Dès qu’un hit est collecté, l’analyse entre appareils tente de l’associer aux appareils connus. Prenons l’exemple suivant, où Bob utilise deux appareils.

*Données telles qu’elles apparaissent le jour de leur collecte :*

| Horodatage | ECID | eVar1 ou CustomerID | Explication du hit | Mesure Personnes (cumulative) à l’aide du groupement basé sur les champs |
| --- | --- | --- | --- | --- |
| `1` | `246` | - | Bob sur son ordinateur de bureau, sans authentification | `1` (246) |
| `2` | `246` | `Bob` | Bob se connecte sur son ordinateur de bureau | `2` (246 et Bob) |
| `3` | `3579` | - | Bob sur son appareil mobile, sans authentification | `3` (246, Bob et 3579) |
| `4` | `3579` | `Bob` | Bob se connecte sur son appareil mobile | `3` (246, Bob et 3579) |
| `5` | `246` | - | Bob accède à nouveau à votre site depuis son ordinateur de bureau, sans authentification | `3` (246, Bob et 3579) |
| `6` | `246` | `Bob` | Bob se connecte à nouveau sur son ordinateur de bureau | `3` (246, Bob et 3579) |
| `7` | `3579` | - | Bob accède à nouveau à votre site depuis son appareil mobile | `3` (246, Bob et 3579) |
| `8` | `3579` | `Bob` | Bob se connecte à nouveau sur son appareil mobile | `3` (246, Bob et 3579) |

Les accès authentifiés et non authentifiés sur les nouveaux appareils sont comptabilisés comme des personnes distinctes (temporairement).
Les accès non authentifiés sur les appareils reconnus sont assemblés en direct à partir de ce moment. L’attribution fonctionne dès que la variable personnalisée d’identification est liée à un appareil. Dans l’exemple ci-dessus, tous les hits, sauf le hit 1 et le hit 3, sont groupés en direct (ils utilisent tous l’identifiant `Bob`). L’attribution fonctionne sur les hits 1 et 3 après le groupement de relecture.

>[!NOTE]
>
>Les hits datant de plus de 12 heures ne sont pas regroupés lors de lʼassemblage dynamique. Cependant, ces hits sont inclus dans la relecture sʼils sont compris dans lʼintervalle de recherche en amont de celle-ci.

### Groupement de relecture

La fonctionnalité Replay s’exécute quotidiennement ou hebdomadairement, selon la façon dont vous avez demandé la configuration d’Analytics sur plusieurs appareils. Pendant la relecture, Analytics sur plusieurs appareils tente de retraiter les données historiques au cours dʼun intervalle de recherche en amont spécifié :

* La relecture quotidienne utilise un intervalle de recherche en amont dʼun jour.
* La relecture hebdomadaire utilise un intervalle de recherche en amont de 7 jours.

Si un appareil envoie des données alors qu’il n’est pas authentifié, puis se connecte, l’analyse entre appareils associe ces hits non authentifiés à la bonne personne. Le tableau suivant représente les mêmes données que ci-dessus, mais affiche des nombres différents à cause de la relecture des données.

*Les mêmes données après relecture :*

| Horodatage | ECID | eVar1 ou CustomerID | Explication du hit | Mesure Personnes (cumulative) à l’aide du groupement basé sur les champs |
| --- | --- | --- | --- | --- |
| `1` | `246` | - | Bob sur son ordinateur de bureau, sans authentification | `1` (Bob) |
| `2` | `246` | `Bob` | Bob se connecte sur son ordinateur de bureau | `1` (Bob) |
| `3` | `3579` | - | Bob sur son appareil mobile, sans authentification | `1` (Bob) |
| `4` | `3579` | `Bob` | Bob se connecte sur son appareil mobile | `1` (Bob) |
| `5` | `246` | - | Bob accède à nouveau à votre site depuis son ordinateur de bureau, sans authentification | `1` (Bob) |
| `6` | `246` | `Bob` | Bob se connecte à nouveau sur son ordinateur de bureau | `1` (Bob) |
| `7` | `3579` | - | Bob accède à nouveau à votre site depuis son appareil mobile | `1` (Bob) |
| `8` | `3579` | `Bob` | Bob se connecte à nouveau sur son appareil mobile | `1` (Bob) |
