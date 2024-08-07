---
title: Classement de toutes les pages de recherche
description: Déterminez la page de moteur de recherche sur laquelle un visiteur a cliqué pour accéder à votre site.
feature: Dimensions
exl-id: 58ce54c3-cc45-4e84-a14d-5fec0b70f50f
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '146'
ht-degree: 85%

---

# Classement de toutes les pages de recherche

La [dimension](overview.md) de &quot;Classement de toutes les pages de recherche&quot; fournit des informations sur la page des résultats de recherche sur laquelle un visiteur a cliqué pour accéder à votre site. Par exemple, si votre site apparaît sur la deuxième page de résultats d’un moteur de recherche, l’élément de dimension de cette variable est « Page de recherche 2 ».

## Renseignement de cette dimension avec des données

Pour que cette dimension fonctionne, vous devez simplement configurer correctement les [filtres URL internes](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/internal-url-filter-admin.md) de votre suite de rapports. AppMeasurement renseigne automatiquement cette dimension sans modification du code d’implémentation.

## Éléments de dimension

Si un visiteur utilise un moteur de recherche pour accéder à votre site, la valeur de cette dimension est « Page de recherche » suivie du numéro de la page sur laquelle il a cliqué. Si un accès ne provient pas d’un moteur de recherche, la valeur de cette dimension est « Non spécifié ».
