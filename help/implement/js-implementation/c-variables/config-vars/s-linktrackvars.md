---
description: Les variables dynamiques vous permettent de copier des valeurs d’une variable vers une autre sans entrer les valeurs complètes à plusieurs reprises dans les demandes d’image sur votre site.
keywords: Mise en œuvre d’Analytics
seo-description: Les variables dynamiques vous permettent de copier des valeurs d’une variable vers une autre sans entrer les valeurs complètes à plusieurs reprises dans les demandes d’image sur votre site.
solution: null
title: Variables dynamiques
translation-type: tm+mt
source-git-commit: 82060388a9a2122b66c57725cafa0eb4ce54e147

---


# s.linkTrackVars

La variable est une liste de variables séparées par des virgules qui sont envoyées avec des liens personnalisés, de téléchargement et de sortie.

The [`linkTrackVars`](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linktrackvars.html) parameter should include each variable that you want to track with every file download, exit link, and custom link.

The settings for `linkTrackVars` and `linkTrackEvents` within the JS file affect every file download, exit link, and custom link. Les instances de chaque variable et de chaque événement peuvent être gonflées dans les situations où la variable (ou l’événement) s’applique à la page active, mais pas au téléchargement de fichier, lien de sortie ou lien personnalisé spécifique.

Pour vous assurer que les variables appropriées sont définies avec le code de lien personnalisé, Adobe recommande de définir `linkTrackVars` et `linkTrackEvents` dans le code de lien personnalisé, comme suit :

```js
<a href="index.html" onClick=" 
var s=s_gi('rsid'); 
s.linkTrackVars='prop1,prop2,eVar1,eVar2,events'; 
s.linkTrackEvents='event1'; 
s.prop1='Custom Property of Link'; 
s.events='event1'; 
s.tl(this,'o','Link Name'); 
">My Page 
```

Dans l’exemple ci-dessus, la valeur de prop1 est définie dans le code de lien personnalisé lui-même. La valeur de prop2 provient de la valeur actuelle de la variable, telle qu’elle est définie sur la page.

The values of `linkTrackVars` and `linkTrackEvents` override the settings in the JS file and ensure only the variables and events specified in the custom link code are set for the specific link.

*Remarque : Si`linkTrackVars`(ou`linkTrackEvents`) est nul (ou une chaîne vide telle que ""), toutes les variables (ou tous les événements) Analytics définis pour la page active sont suivis. En d’autres termes, toutes les variables ayant des valeurs seraient envoyées avec des données de lien. Cela gonflera probablement les instances de chaque variable. Pour éviter le gonflement des instances ou des pages vues associées à d’autres variables, Adobe recommande de renseigner`linkTrackVars`et`linkTrackEvents`dans l’événement[!UICONTROL onClick]d’un lien utilisé pour le suivi des liens.*

Toutes les variables qui doivent être envoyées avec des données de lien (liens personnalisés, de téléchargement et de sortie) doivent être répertoriées dans `linkTrackVars`. Si `linkTrackEvents` est utilisé, `linkTrackVars` doit contenir « events ».

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|---|---|---|---|
| N/D | N/D | Quelconque | "Aucun" |

When populating `linkTrackVars`, do not use the 's.' prefix for variables. Par exemple, au lieu de renseigner `linkTrackVars` avec « s.prop1 », vous devez le renseigner avec « prop1 ». L’exemple suivant illustre la manière d’utiliser `linkTrackVars`.

```js
s.linkTrackVars="eVar1,events" 
s.linkTrackEvents="event1" 
s.events="event1" 
s.eVar1="value A" 
s.eVar2="value B" 
s.t() // eVar1, event1 and event2 are recorded 
<a href="https://google.com">event1 and eVar1 are recorded</a> 
<a href="test.php" onClick="s=s_gi('rs1');s.eVar1='value C';s.events='';s.tl(this,'o')">eVar1 is recorded</a> 
```

Dans la mesure où le lien vers google.com est un lien de sortie (sauf si votre société est Google), « event1 » et « eVar1 » sont envoyés avec les données du lien de sortie, ce qui a pour effet d’augmenter le nombre d’instances associées à « eVar1 » et le nombre de déclenchements de « event1 ». Dans le lien pointant vers [!DNL test.php], [!UICONTROL eVar1] est envoyée avec la valeur de « value C », car il s’agit de la valeur actuelle de eVar1 au moment où la fonction `tl()` est appelée.

## Syntaxe et valeurs possibles

La variable `linkTrackVars` est une liste de noms de variables séparés par des virgules et sensibles à la casse. Elle est dépourvue de préfixe de nom d’objet. Utilisez « eVar1 » plutôt que « s.eVar1 ».

```
s.linkTrackVars="variable_name[,variable_name[...]]"
```

Il se peut que `linkTrackVars` variable may contain only variables that are sent to [!DNL Analytics], namely: `events`, `campaign`, `purchaseID`, `products`, `eVar1-75`, `prop1-75`, `hier1-5`, `channel`, `server`, `state`, `zip`, and `pageType`.

## Exemples

```
s.linkTrackVars="events,prop1,eVar49"
```

```
s.linkTrackVars="products"
```

## Paramètres de configuration

Aucun

## Pièges, questions et conseils

* Si `linkTrackVars` est vide, toutes les variables qui comportent des valeurs sont suivies avec tous les appels au serveur.
* Toute variable répertoriée dans `linkTrackVars` et qui comporte une valeur au moment où un lien personnalisé, de téléchargement ou de sortie est utilisé, est suivie.
* Si `linkTrackEvents` est utilisé, `linkTrackVars` doit contenir « events ».

* N’utilisez pas le préfixe « s. » ou « s_objectname. » pour les variables.
