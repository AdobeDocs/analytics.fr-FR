---
title: linkURL
description: Permet de remplacer l’URL de lien générée automatiquement utilisée par AppMeasurement dans les appels de suivi des liens.
feature: Appmeasurement Implementation
exl-id: 15d6e423-d9fc-4f84-ad39-0bd91399cde4
role: Admin, Developer
source-git-commit: 24101efe2b860734c9d176ba8be8f17e26429442
workflow-type: tm+mt
source-wordcount: '204'
ht-degree: 34%

---

# linkURL

Chaque fois qu’un appel de suivi des liens est envoyé à Adobe, AppMeasurement détecte l’URL sur laquelle l’utilisateur a cliqué. Cette URL permet de déterminer le type de lien, tel que les liens de téléchargement et les liens de sortie. Utilisez la variable `linkURL` pour remplacer l’URL détectée.

Aucune dimension dans Analysis Workspace ne génère de rapport sur cette variable. Elle renseigne la colonne `page_event_var1` dans [Flux de données](/help/export/analytics-data-feed/data-feed-overview.md). Si vous souhaitez suivre l’URL d’un lien cliqué, Adobe recommande d’utiliser une variable personnalisée, telle qu’une [Prop](../page-vars/prop.md). L’utilisation de [Activity Map](/help/analyze/activity-map/overview.md) peut aider à rationaliser la collecte de données pour les liens cliqués.

## URL du lien à l’aide du SDK Web

L’URL du lien est mappée aux variables suivantes :

* [Objet XDM](/help/implement/aep-edge/xdm-var-mapping.md) : `web.webInteraction.URL`
* [Objet de données](/help/implement/aep-edge/data-var-mapping.md) : `data.__adobe.analytics.linkURL` ou `data.__adobe.analytics.pev1`

## URL du lien utilisant l’extension Adobe Analytics

Il n’existe pas de champ dédié dans l’extension Adobe Analytics pour utiliser cette variable. Utilisez l’éditeur de code personnalisé, en respectant la syntaxe AppMeasurement.

## s.linkURL dans AppMeasurement et l’éditeur de code personnalisé de l’extension Analytics

La variable `s.linkURL` est une chaîne contenant l’URL complète du lien sur lequel l’utilisateur a cliqué. Cette variable ne renseigne aucune dimension disponible dans les rapports.

```js
s.linkURL = "https://example.com";
```

Si le troisième argument de la méthode [tl()](../functions/tl-method.md) n’est pas défini, la variable `linkURL` est utilisée à la place.
