---
title: Créer une couche de données
description: Découvrez comment une couche de données prend en charge votre implémentation Analytics, pourquoi Adobe recommande la couche de données client Adobe et comment lire les valeurs de couche de données avec chaque méthode d’implémentation.
feature: Implementation Basics
exl-id: 271dd8fa-3ba1-4a7f-b16a-c48a736a5bb5
role: Admin, Developer, Leader
TQID: 'https://experienceleague.adobe.com/JmxM3-AVA5--7Xt4kuES35KFtYbicdGO9JZXsygzuuE'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
  - id: a421fb65-2c82-457a-921c-28c46b697a39
    internal-label: Analytics basics
subfeature_v2:
  - id: df312454-73c4-43f6-a90e-18f5043f074c
    internal-label: Tags
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
    internal-label: Variables
  - id: c24fe15a-643a-47bd-8278-5e027df49785
    internal-label: Implementation basics
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
    internal-label: Leader
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 7151dca7425bfb99271db71a3132485f85941a5e
workflow-type: tm+mt
source-wordcount: '1063'
ht-degree: 7%
---
# Créer une couche de données

Une couche de données est une structure JavaScript de votre site qui expose les données collectées par votre implémentation Analytics, telles que les noms de page, les détails de produit et les ID de commande. Le code de votre site écrit dans la couche de données, et votre implémentation lit à partir de celle-ci pour définir les variables Analytics. Comme votre implémentation ne dépend pas d’HTML de la page, vous pouvez reconcevoir votre site sans interrompre la collecte de données.

## Conditions préalables

[Créez un document de conception de solution](solution-design.md) : il est important que votre organisation s’aligne sur les exigences de suivi. Assurez-vous d’être préparé et de disposer d’un document de conception de solution avant de contacter les équipes de développement de votre organisation. Les données requises par la conception de votre solution déterminent ce que contient votre couche de données.

## Choisir une spécification de couche de données {#specifications}

Adobe recommande la [couche de données client Adobe](https://experienceleague.adobe.com/fr/docs/experience-platform/collection/acdl/overview) (ACDL) pour les nouvelles implémentations ou les implémentations restructurées. ACDL est une bibliothèque JavaScript open source qui fournit à votre site un moyen standard de pousser des données et des événements vers un tableau `adobeDataLayer` global. Les balises, le SDK Web et AppMeasurement peuvent tous en lire un extrait, et les composants principaux de Adobe Experience Manager peuvent le remplir automatiquement.

Votre entreprise peut utiliser d’autres spécifications, telles que la [couche de données numériques de l’expérience client](https://www.w3.org/2013/12/ceddl-201312.pdf) (CEDDL), qui stocke les données dans un objet `digitalData` global, ou une spécification personnalisée. Le plus important est que votre entreprise s’aligne sur une spécification qui répond à ses besoins.

Le tableau suivant compare l’ACDL aux couches de données basées sur des objets telles que CEDDL :

| | Couche De Données Client Adobe (`adobeDataLayer`) | Couche de données basée sur un objet, telle que CEDDL (`digitalData`) |
| --- | --- | --- |
| Écriture des données par le code de site | Envoie les objets : `adobeDataLayer.push({ page: { name: "Home" } })` | Définit les propriétés : `digitalData.page.pageInfo.pageName = "Home"` |
| Lecture d’une valeur par votre implémentation | `adobeDataLayer.getState("page.name")` ou un élément de données **État calculé de la couche de données** à partir de l’extension de balise de la couche de données client Adobe | `digitalData.page.pageInfo.pageName` ou un élément de données **Variable JavaScript** de l’extension de balise Core |
| Comment votre implémentation sait que les données sont prêtes | Le code de site envoie un événement, tel que `{ event: "page view" }`, et votre implémentation l’écoute. Les écouteurs s’exécutent également pour les événements qui ont été transmis avant leur ajout. | Votre implémentation doit lire l’objet une fois que le code du site l’a renseigné, par exemple à l’aide d’une règle Appel direct . |

## Exemple de couche de données {#example}

ACDL ne nécessite pas de structure de données spécifique. Concevez la structure autour de votre document de conception de solution et documentez-le pour toutes les personnes qui écrivent dans la couche de données ou qui en lisent. Les exemples de ce guide utilisent la structure suivante.

Lors du chargement d’une page, le code du site transmet les données de la page et un événement de page vue :

```js
window.adobeDataLayer = window.adobeDataLayer || [];
window.adobeDataLayer.push({
  event: "page view",
  page: {
    name: "Home",
    section: "Products",
    url: "https://example.com/products",
    referrer: "https://example.com/"
  }
});
```

Lorsqu’un visiteur effectue un achat, le code du site transmet les détails de la commande et un événement d’achat :

```js
window.adobeDataLayer.push({
  event: "purchase",
  transaction: { id: "ABC123" },
  products: [
    { name: "Example product", category: "Example category", quantity: 1, price: 25 }
  ]
});
```

ACDL fusionne chaque notification push dans un seul objet appelé état calculé, que votre implémentation lit. Les objets d’événement indiquent à votre implémentation quand le lire. Voir [Données et l’état calculé](https://experienceleague.adobe.com/en/docs/experience-platform/collection/acdl/concepts/computed-state) et [Événements](https://experienceleague.adobe.com/en/docs/experience-platform/collection/acdl/concepts/events).

## Workflow {#workflow}

La mise en œuvre d’Adobe Analytics à l’aide d’une couche de données suit généralement les étapes suivantes :

1. **Collaborez avec l’équipe de développement de votre site pour implémenter une couche de données** : l’équipe de développement de votre site est principalement chargée de s’assurer que la couche de données contient les valeurs correctes. Consultez cette page avec votre équipe de développement de site pour vous assurer que les attentes sont harmonisées entre les équipes. Voir [Installation de la couche de données client Adobe](https://experienceleague.adobe.com/fr/docs/experience-platform/collection/acdl/install).
1. **Validez la couche de données à l’aide d’une console de navigateur** : ouvrez la console de développement de votre navigateur, ce que vous pouvez faire dans la plupart des navigateurs avec la clé `F12`. Exécutez `adobeDataLayer.getState()` pour afficher l’état calculé, ou `adobeDataLayer.getState("page.name")` pour afficher une seule valeur. Voir [Vérification de l&#39;installation](https://experienceleague.adobe.com/fr/docs/experience-platform/collection/acdl/install#verify).
1. **Connecter la couche de données à Adobe Analytics** : cette étape varie en fonction de la méthode de mise en œuvre de votre organisation. Voir [Connexion de la couche de données à Adobe Analytics](#connect).

## Connecter la couche de données à Adobe Analytics {#connect}

Le tableau suivant montre comment chaque méthode d’implémentation lit à partir de la couche de données client Adobe :

| Méthode de mise en œuvre | Comment lire la couche de données | Informations supplémentaires |
| --- | --- | --- |
| Extension de balises du SDK Web | Déclenchez des règles avec l’événement **Push de couche de données** de l’extension Adobe Client Data Layer. Mappez les valeurs de la couche de données aux champs XDM ou à l’objet `data` avec l’action **Mettre à jour la variable** de Web SDK, puis envoyez-les avec l’action **Envoyer l’événement**. | [Envoyer des données de la couche de données client Adobe avec le Web SDK](https://experienceleague.adobe.com/fr/docs/experience-platform/collection/acdl/web-sdk), [Mappage de champs d’objet XDM](../aep-edge/xdm-var-mapping.md) et [Mappage de champs d’objet de données](../aep-edge/data-var-mapping.md) |
| Bibliothèque JavaScript Web SDK | Écoutez les événements de couche de données avec `addEventListener()` et définissez les champs XDM ou `data` de la couche de données lorsque vous appelez `sendEvent`. | [Envoyer des données de la couche de données client Adobe avec le Web SDK](https://experienceleague.adobe.com/fr/docs/experience-platform/collection/acdl/web-sdk), [Mappage de champs d’objet XDM](../aep-edge/xdm-var-mapping.md) et [Mappage de champs d’objet de données](../aep-edge/data-var-mapping.md) |
| Extension Analytics | Déclenchez des règles avec l’événement **Push de couche de données** et créez des éléments de données **État calculé de couche de données** à partir de l’extension de la couche de données client Adobe. Attribuez les éléments de données aux variables Analytics dans l’action **Définir les variables**, puis envoyez les données avec l’action **Envoyer la balise**. | [Mapper des objets de couche de données aux éléments de données](../launch/layer-to-elements.md) et [Mapper des éléments de données aux variables Analytics](../launch/elements-to-variable.md) |
| AppMeasurement | Lire les valeurs avec `getState()` après le chargement de l’ACDL, puis appeler `s.t()`. | [Lire la couche de données avec AppMeasurement](#appmeasurement) |

### Lire la couche de données avec AppMeasurement {#appmeasurement}

L’ACDL ajoute sa méthode `getState()` au tableau `adobeDataLayer` lors du chargement de la bibliothèque. Pour vous assurer que la bibliothèque a été chargée et que l’état calculé inclut les données les plus récentes, lisez les valeurs dans un écouteur d’événement :

```js
window.adobeDataLayer = window.adobeDataLayer || [];
window.adobeDataLayer.push(function(dl) {
  dl.addEventListener("page view", function(event) {
    s.pageName = dl.getState("page.name");
    s.channel = dl.getState("page.section");
    s.t();
  });
});
```

Le listener s&#39;exécute une fois pour chaque événement `page view`, y compris les événements qui ont été transmis avant l&#39;ajout du listener. Les pages de variables de ce guide, telles que [`pageName`](../vars/page-vars/pagename.md), montrent comment lire des valeurs individuelles avec `getState()`. Utilisez ces exemples dans un écouteur comme celui-ci ou dans l’éditeur de code personnalisé d’une règle d’extension Analytics déclenchée par un événement de couche de données **push**.

Si votre implémentation envoie plusieurs accès par page, par exemple dans une application d’une seule page, utilisez [`clearVars()`](../vars/functions/clearvars.md) afin que les valeurs d’un accès ne persistent pas à l’autre.

## Étapes suivantes

* [Mapper des objets de couche de données aux éléments de données](../launch/layer-to-elements.md) : utilisez la couche de données de votre site dans les balises Adobe Experience Platform.
* [Documentation sur la couche de données client Adobe](https://experienceleague.adobe.com/fr/docs/experience-platform/collection/acdl/overview) : découvrez chaque méthode ACDL, événement et bonnes pratiques.
