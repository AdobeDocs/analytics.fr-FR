---
title: pageName
description: Nom de la page de votre site.
feature: Variables
exl-id: 24ac40a9-f0e7-4534-abf2-2397f5fe16c2
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '263'
ht-degree: 80%

---

# pageName

La variable `pageName` stocke généralement le nom d’une page donnée. Il est utile de déterminer les pages les plus populaires. Cette variable renseigne la dimension [Page](/help/components/dimensions/page.md).

Si cette variable n’est pas définie sur un appel de suivi de page donné, la variable [`pageURL`](pageurl.md) est utilisée à la place.

>[!NOTE]
>
>Les serveurs de collecte de données Adobe éliminent cette dimension de toutes les demandes dʼimage de [suivi des liens](/help/implement/vars/functions/tl-method.md). Si vous souhaitez que cette dimension apparaisse dans les accès de suivi des liens, pensez à copier cette dimension dans une [eVar](evar.md).

## Nom de page à l’aide du SDK Web

La page est [mappé pour Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html) sous le champ XDM `web.webPageDetails.name`.

## Nom de page à l’aide de l’extension Adobe Analytics

Vous pouvez définir le nom de la page lors de la configuration de l’extension Analytics (variables globales) ou sous des règles.

1. Connectez-vous à [Collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
2. Cliquez sur la propriété de balise de votre choix.
3. Accédez à l’onglet [!UICONTROL Règles], puis cliquez sur une règle (ou créez une règle).
4. Sous [!UICONTROL Actions], cliquez sur une action existante [!UICONTROL Adobe Analytics - Définir des variables] ou cliquez sur l’icône « + ».
5. Définissez la liste déroulante [!UICONTROL Extension] sur Adobe Analytics et le [!UICONTROL type d’action] sur [!UICONTROL Définir des variables].
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
