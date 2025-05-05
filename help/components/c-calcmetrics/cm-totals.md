---
title: Totaux des mesures calculées
description: Découvrez les totaux des mesures calculées dans Analysis Workspace
feature: Calculated Metrics
exl-id: 3e4429de-3e0c-49a5-b32c-3a4d24a29816
source-git-commit: be5a73347d417c8dc6667d4059e7d46ef5f0f5cd
workflow-type: tm+mt
source-wordcount: '149'
ht-degree: 89%

---

# Totaux des mesures calculées dans Analysis Workspace

Lorsque vous affichez des données dans Analysis Workspace, les totaux des mesures calculées s’affichent dans la plupart des cas. Dans certains cas, il n’est pas possible de fournir un total, par exemple lorsque les lignes du rapport présentent un format mixte (décimal et devise, par exemple).

Lorsque des totaux sont affichés, ils sont souvent calculés côté serveur, ce qui signifie que le total déduplique les mesures telles que les visites ou les visiteurs. Dans certaines circonstances, les mesures calculées sont générées côté client en additionnant les lignes du tableau, ce qui signifie que le total ne déduplique pas les mesures, comme les visites ou les visiteurs. Cela se produit dans les circonstances suivantes :

* Lorsque des [lignes statiques](/help/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md) sont utilisées dans des tableaux à structure libre, l’option **[!UICONTROL Afficher comme somme des lignes actuelles]** (par défaut) est sélectionnée.
* Dans la [visualisation Anneau](/help/analyze/analysis-workspace/visualizations/donut.md), afin que la somme des nombres s’élève à 100 %.

Pour plus dʼinformations sur les totaux dans Analysis Workspace, consultez la section [Totaux dans Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/workspace-totals.html?lang=fr#static-row-total).
