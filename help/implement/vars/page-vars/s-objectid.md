---
title: s_objectID
description: Aide Carte d’activités pour identifier les liens uniques de votre site.
translation-type: tm+mt
source-git-commit: c7d596be4f70c820039725be6a5fddc8572156d9

---


# s_objectID

La `s_objectID` variable fournit un identifiant unique pour un lien. Elle permet de rendre les rapports de Carte d’ [activités](/help/analyze/activity-map/activity-map.md) plus précis. Si une page comporte des liens qui changent fréquemment, vous pouvez utiliser la `s_objectID` variable pour indiquer à Carte d’activités un emplacement de lien unique afin qu’il puisse regrouper correctement les données selon vos besoins.

Si la précision de Carte d’activités est essentielle pour votre entreprise, Adobe conseille d’inclure la `s_objectID` variable dans l’ `onClick` événement des liens de votre site. Pour plus d’informations, voir Cas [d’utilisation du suivi des liens de Carte d’](/help/analyze/activity-map/activitymap-link-tracking/activitymap-link-tracking-use-case.md) activités dans le guide de l’utilisateur Analyser.

## ID d’objet dans Adobe Experience Platform Launch

Il n’existe pas de champ dédié dans Lancer pour utiliser cette variable. Utilisez l’éditeur de code personnalisé, en respectant la syntaxe AppMeasurement.

## s_objectID dans l’éditeur de code personnalisé AppMeasurement et Launch

La `s_objectID` variable est une variable globale, ce qui signifie qu’elle fonctionne indépendamment de l’objet de suivi Analytics (`s` par défaut). Les valeurs valides pour cette variable peuvent être n’importe quelle chaîne d’une longueur maximale de 100 octets. Si cette variable n’est pas définie, Carte d’activités utilise l’URL du lien comme identifiant du lien.

Cette variable est généralement définie dans l’ `onClick` événement d’un lien HTML.

```HTML
<a href="https://example.com" onClick="s_objectID='Example identifier';">Example link</a>
```

> [!NOTE] Incluez toujours le point-virgule qui termine une instruction JavaScript. Le point-virgule est nécessaire pour que Carte d’activités fonctionne.

## Cas d’utilisation

La `s_objectID` variable est utile lorsque vous souhaitez une précision accrue dans les rapports de Carte d’activités.

### Combiner les liens à partir de contenu très dynamique

Certains sites ont un contenu très dynamique, comme les sites d’actualités ou les sites de vente au détail avec des articles qui tournent fréquemment. Comme Carte d’activités utilise par défaut l’URL du lien comme identificateur, il est difficile de comprendre les zones sur lesquelles les liens font le plus de clics sur les pages où les liens changent fréquemment. Si vous utilisez les liens `s_objectID` au sein de ces liens, Carte d’activités sait quels liens peuvent être agrégés, quelles que soient les URL auxquelles ils pointent.

```HTML
<a href="story1.html" onClick="s_objectID='Top left link';">Story 1</a>
<a href="story2.html" onClick="s_objectID='Top center link';">Story 2</a>
<a href="story3.html" onClick="s_objectID='Top right link';">Story 3</a>
```

Quel que soit l’endroit où les liens pointent ou la fréquence à laquelle vous modifiez ces liens, Carte d’activités agrège les données en fonction de la valeur dans `s_objectID`.

### Séparer les liens d’une page

Certains sites comportent des liens pointant vers le même emplacement à différents endroits. Par exemple, un lien vers la page d’accueil dans l’en-tête et le pied de page de votre site. Ces liens ayant la même URL, Carte d’activités agrège leurs données. Vous pouvez les séparer à l’aide de la `s_objectID` variable :

```HTML
<a href="index.html" onClick="s_objectID='Header home link';">Example link in Header</a>
<a href="index.html" onClick="s_objectID='Footer home link';">Example link in Footer</a>
```

Même si les liens pointent vers la même URL, Carte d’activités peut utiliser la `s_objectID` variable pour les distinguer correctement dans les rapports.
