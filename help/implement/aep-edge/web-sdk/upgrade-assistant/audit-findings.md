---
title: Résultats d’audit dans l’assistant de mise à niveau de Web SDK
description: Consultez et résolvez les recommandations de nettoyage facultatives pour vos composants de balises avant de migrer vers Web SDK.
feature: Implementation Basics
role: Admin, Developer, Leader
badge: Beta
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
  - id: a421fb65-2c82-457a-921c-28c46b697a39
    internal-label: Analytics basics
subfeature_v2:
  - id: e4f5f438-eabb-4c54-9133-b817e3d125f5
    internal-label: Use cases
  - id: c24fe15a-643a-47bd-8278-5e027df49785
    internal-label: Implementation basics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
    internal-label: Leader
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 629efca210346d32b8555c60f7db15d1d8285b20
workflow-type: tm+mt
source-wordcount: '336'
ht-degree: 2%
---
# Résultats de l’audit

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_upgradeassistant_auditfindings"
>title="Résultats de l’audit"
>abstract="Les résultats indiquent les règles et les éléments de données que vous pouvez nettoyer avant de migrer, tels que les éléments de données auxquels rien ne fait référence. Acceptez un résultat pour inclure sa modification recommandée dans la migration ou refusez-le pour laisser le composant en l’état. Cette étape est facultative."

<!-- markdownlint-enable MD034 -->

L’assistant de mise à niveau vérifie les règles et les éléments de données sélectionnés dans [sélection de composant](component-selection.md) et signale ceux que vous souhaitez peut-être nettoyer avant la migration :

* Règles en double ou règles partageant des événements et des conditions que vous pouvez consolider
* Séquences d’actions de règle pouvant affecter la précision des données
* Dupliquer les éléments de données que vous pouvez consolider
* Éléments de données pouvant être inutilisés, que vous pouvez désactiver

Cette étape est facultative. Vous pouvez résoudre autant de résultats que vous le souhaitez ou passer directement à la [vérification de la suite de rapports](rs-verification.md).

## Vérifier un résultat {#review}

Sélectionnez un résultat pour en afficher les détails, notamment :

* Description du résultat
* La configuration actuelle du composant
* L’endroit où le composant est utilisé, à la fois dans la propriété des balises et dans Adobe Analytics

Chaque résultat comprend une action recommandée, qui dépend du type de résultat. Par exemple, l’action recommandée pour un élément de données auquel rien ne fait référence est de le désactiver.

>[!IMPORTANT]
>
>Un élément de données marqué comme inutilisé peut toujours être référencé dynamiquement ou depuis l’extérieur des balises. Avant d’accepter une recherche, vérifiez ses modifications proposées, le code personnalisé, l’ordre d’action et les références pour vous assurer qu’ils conservent le comportement souhaité.

## Résoudre les résultats {#resolve}

Lorsque vous effectuez l’action recommandée d’une recherche, la recherche est acceptée. L’assistant de mise à niveau ajoute la modification à la migration et l’applique lorsque vous [finalisez la migration](final-review.md#finalize). Si vous ne souhaitez pas apporter de modification, refusez plutôt la recherche.

Vous pouvez rouvrir un résultat accepté ou refusé si vous changez d&#39;avis. Pour mettre à jour plusieurs résultats à la fois, sélectionnez-les dans la liste.
