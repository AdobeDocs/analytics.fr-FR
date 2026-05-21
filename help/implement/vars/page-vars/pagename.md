---
title: pageName
description: Nom de la page de votre site.
feature: Appmeasurement Implementation
exl-id: 24ac40a9-f0e7-4534-abf2-2397f5fe16c2
role: Admin, Developer
TQID: https://experienceleague.adobe.com/8afiyqnZrImK-YJ-GvQGu0H4fzhcJrMh20QN2WbO0T0
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 262
ht-degree: 86%

---

# pageName

La variable `pageName` stocke généralement le nom d’une page donnée. Il est utile de déterminer les pages les plus populaires. Cette variable renseigne la dimension [Page](/help/components/dimensions/page.md).

Si cette variable n’est pas définie sur un appel de suivi de page donné, la variable [`pageURL`](pageurl.md) est utilisée à la place.

>[!NOTE]
>
>Les serveurs de collecte de données Adobe éliminent cette dimension de toutes les demandes dʼimage de [suivi des liens](/help/implement/vars/functions/tl-method.md). Si vous souhaitez que cette dimension apparaisse dans les accès de suivi des liens, pensez à copier cette dimension dans une [eVar](evar.md).

## Nom de page utilisant le SDK Web

Le nom de page est mappé aux variables suivantes :

* [Objet XDM](/help/implement/aep-edge/xdm-var-mapping.md) : `xdm.web.webPageDetails.name`
* [Objet de données](/help/implement/aep-edge/data-var-mapping.md) : `data.__adobe.analytics.pageName`

## Nom de page utilisant l’extension Adobe Analytics

Vous pouvez définir le nom de la page lors de la configuration de l’extension Analytics (variables globales) ou sous des règles.

1. Connectez-vous à [la collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
2. Cliquez sur la propriété de balise de votre choix.
3. Accédez à l’onglet [!UICONTROL Règles], puis cliquez sur une règle (ou créez une règle).
4. Sous [!UICONTROL Actions], cliquez sur une action existante [!UICONTROL Adobe Analytics - Définir des variables] ou cliquez sur l’icône « + ».
5. Définissez la liste déroulante [!UICONTROL Extension] sur Adobe Analytics et le [!UICONTROL type d’action] sur [!UICONTROL Définir des variables].
6. Recherchez la section [!UICONTROL Nom de la page].

Vous pouvez définir le nom de la page sur n’importe quelle valeur de chaîne, y compris les éléments de données.

## s.pageName dans AppMeasurement et l’éditeur de code personnalisé de l’extension Analytics

La variable `s.pageName` est une chaîne qui contient généralement le nom de la page. Celle-ci a une valeur maximale de 100 octets ; les valeurs plus longues sont tronquées. Cette troncature inclut les instances auxquelles elle redevient `pageURL` si cette variable est vide.

```js
// Set page name to a static value
s.pageName = "Example page name";

// Set page name to the page's title
s.pageName = window.document.title;
```

Si vous utilisez la `digitalData` [couche de données](../../prepare/data-layer.md) :

```js
s.pageName = digitalData.page.pageInfo.pageName;
```
