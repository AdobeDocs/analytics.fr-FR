---
title: Classement de toutes les pages de recherche
description: Déterminez la page de moteur de recherche sur laquelle un visiteur a cliqué pour accéder à votre site.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '145'
ht-degree: 100%

---


# Classement de toutes les pages de recherche

La dimension « Classement de toutes les pages de recherche » fournit des informations sur la page de résultats de recherche sur laquelle un visiteur a cliqué pour accéder à votre site. Par exemple, si votre site apparaît sur la deuxième page de résultats d’un moteur de recherche, l’élément de dimension de cette variable est « Page de recherche 2 ».

## Renseignement de cette dimension avec des données

Pour que cette dimension fonctionne, vous devez simplement configurer correctement les [filtres URL internes](/help/admin/admin/internal-url-filter-admin.md) de votre suite de rapports. AppMeasurement renseigne automatiquement cette dimension sans modification du code d’implémentation.

## Éléments de dimension

Si un visiteur utilise un moteur de recherche pour accéder à votre site, la valeur de cette dimension est « Page de recherche » suivie du numéro de la page sur laquelle il a cliqué. Si un accès ne provient pas d’un moteur de recherche, la valeur de cette dimension est « Non spécifié ».
