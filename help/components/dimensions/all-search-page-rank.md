---
title: Classement de toutes les pages de recherche
description: Déterminez la page d'un moteur de recherche sur laquelle un visiteur a cliqué pour accéder à votre site.
translation-type: tm+mt
source-git-commit: 4a7b3a00bdbf557c219de530e3e692c2b2db4a84
workflow-type: tm+mt
source-wordcount: '145'
ht-degree: 0%

---


# Classement de toutes les pages de recherche

La dimension &quot;Classement de toutes les pages de recherche&quot; fournit des informations sur la page des résultats de recherche sur laquelle un visiteur a cliqué pour accéder à votre site. Par exemple, si votre site apparaît sur la deuxième page des résultats de recherche d&#39;un moteur de recherche, la valeur de dimension de cette variable est &quot;Recherche de la page 2&quot;.

## Renseigner cette dimension avec des données

Pour que cette dimension fonctionne uniquement, vous devez configurer correctement les filtres [URL](/help/admin/admin/internal-url-filter-admin.md) internes de votre suite de rapports. AppMeasurement renseigne automatiquement cette dimension sans modification du code de mise en oeuvre.

## Valeurs de dimension

Si un visiteur clique sur votre site à partir d’un moteur de recherche, la valeur de cette dimension est &quot;Page de recherche&quot; suivie du numéro de page sur lequel il a cliqué. Si un accès ne provient pas d&#39;un moteur de recherche, la valeur de cette dimension est &quot;Non spécifié&quot;.
