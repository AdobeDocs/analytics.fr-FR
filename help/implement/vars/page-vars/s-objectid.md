---
title: s_objectID
description: Permet d’aider Activity Map à identifier les liens uniques de votre site.
feature: Appmeasurement Implementation
exl-id: 7c0cb750-2bfe-41ca-ab27-30dda4b3a7fa
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '389'
ht-degree: 80%

---

# s_objectID

La variable `s_objectID` fournit un identifiant unique pour un lien. Elle permet de rendre les rapports d’[Activity Map](/help/analyze/activity-map/overview.md) plus précis. Si une page comporte des liens qui changent fréquemment, vous pouvez utiliser la variable `s_objectID` pour indiquer à Activity Map un emplacement de lien unique afin qu’il puisse regrouper correctement les données selon vos besoins.

Si la précision d’Activity Map est essentielle pour votre organisation, Adobe recommande d’inclure la variable `s_objectID` dans le `onClick` cas de liens sur votre site.

## Identifiant d’objet utilisant l’extension Adobe Analytics

Il n’existe pas de champ dédié dans l’extension Adobe Analytics pour utiliser cette variable. Utilisez l’éditeur de code personnalisé, en respectant la syntaxe AppMeasurement.

## s_objectID dans AppMeasurement et l’éditeur de code personnalisé de l’extension Analytics

La variable `s_objectID` est une variable globale, ce qui signifie qu’elle fonctionne indépendamment de l’objet de suivi Analytics (`s` par défaut). Les valeurs valides pour cette variable peuvent être n’importe quelle chaîne d’une longueur maximale de 100 octets. Si cette variable n’est pas définie, Activity Map utilise le texte du lien comme identifiant du lien.

Cette variable est généralement définie dans l’événement `onClick` d’un lien HTML.

```HTML
<a href="https://example.com" onClick="s_objectID='Example identifier';">Example link</a>
```

>[!NOTE]
>
>Incluez toujours le point-virgule qui termine une instruction JavaScript. Le point-virgule est nécessaire pour qu’Activity Map fonctionne.

## Cas d’utilisation

La variable `s_objectID` est utile lorsque vous souhaitez une précision accrue dans les rapports d’Activity Map.

### Combinaison des liens à partir de contenu très dynamique

Certains sites ont un contenu très dynamique, comme les sites d’actualités ou les sites de vente au détail avec des articles qui tournent fréquemment. Comme Activity Map utilise par défaut l’URL du lien comme identificateur, il est difficile de comprendre les zones sur lesquelles les liens font le plus de clics sur les pages où les liens changent fréquemment. Si vous utilisez les liens `s_objectID` au sein de ces liens, Activity Map sait quels liens peuvent être agrégés, quelles que soient les URL vers lesquelles ils renvoient.

```HTML
<a href="story1.html" onClick="s_objectID='Top left link';">Story 1</a>
<a href="story2.html" onClick="s_objectID='Top center link';">Story 2</a>
<a href="story3.html" onClick="s_objectID='Top right link';">Story 3</a>
```

Peu importe où renvoient les liens ou la fréquence à laquelle vous modifiez ces liens, Activity Map agrège les données en fonction de la valeur dans `s_objectID`.

### Séparation des liens d’une page

Certains sites comportent des liens qui renvoient vers le même emplacement à différents endroits. Par exemple, un lien vers la page d’accueil dans l’en-tête et le pied de page de votre site. Ces liens ayant la même URL, Activity Map agrège leurs données. Vous pouvez les séparer à l’aide de la variable `s_objectID` :

```HTML
<a href="index.html" onClick="s_objectID='Header home link';">Example link in Header</a>
<a href="index.html" onClick="s_objectID='Footer home link';">Example link in Footer</a>
```

Même si les liens pointent vers la même URL, Activity Map peut utiliser la variable `s_objectID` pour les distinguer correctement dans les rapports.
