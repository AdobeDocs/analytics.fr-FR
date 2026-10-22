---
title: Version de JavaScript
description: Version de JavaScript prise en charge par le navigateur du visiteur.
feature: Dimensions
source-git-commit: a68e13c9232ef8d975fd1256168a0addf677f5ac
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 10%
---
# Version de JavaScript

La dimension « Version de JavaScript » [dimension](overview.md) indique la version de JavaScript prise en charge par le navigateur du visiteur. Il ne signale pas la version de la bibliothèque AppMeasurement.

>[!IMPORTANT]
>
>Cette dimension est uniquement disponible dans Data Warehouse. Si vous souhaitez utiliser la version de JavaScript dans d’autres solutions Analytics, pensez à copier la valeur dans une [eVar](evar.md) sur chaque accès.

## Renseignement de cette dimension avec des données

AppMeasurement détecte automatiquement les fonctionnalités JavaScript dans le navigateur et envoie une valeur de version dans le paramètre de chaîne de requête `j`. Aucune variable d’implémentation à définir. Cette détection utilise des libellés de version JavaScript hérités ; il ne s’agit pas d’une mesure complète de la prise en charge des fonctionnalités ECMAScript modernes.

| Propriété | Valeur |
| --- | --- |
| **Variable** | Aucun (collecté automatiquement) |
| **Champ Web SDK/XDM** | [`environment.browserDetails.javaScriptVersion`](/help/implement/aep-edge/xdm-var-mapping.md) |
| **Paramètre de requête** | [`j`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Balise XML** | [`<javaScriptVersion>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Colonne API d’insertion de données en bloc** | [`javaScriptVersion`](https://developer.adobe.com/analytics-collection-apis/methods/bulk-data-insertion/column-reference) |
| **Limite d’octets** | 5 octets |
| **Persistance** | Hit |

## Éléments de dimension

Les éléments Dimension incluent les valeurs de version JavaScript collectées à partir des navigateurs des visiteurs, tels que `1.5` et `1.6`.
