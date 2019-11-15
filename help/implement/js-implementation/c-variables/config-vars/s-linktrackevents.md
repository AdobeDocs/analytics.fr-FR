---
description: Les variables dynamiques vous permettent de copier des valeurs d’une variable vers une autre sans entrer les valeurs complètes à plusieurs reprises dans les demandes d’image sur votre site.
keywords: Analytics Implementation
solution: null
title: Variables dynamiques
translation-type: tm+mt
source-git-commit: ca0797a353661a72d4064aa5aa84c3d9b7eb38a5

---


# s.linkTrackEvents

La variable  est une liste d’événements séparés par des virgules, qui sont envoyés avec un lien personnalisé, de sortie ou de téléchargement. The `linkTrackEvents` parameter should include each event you want to track with every file download, exit link, and custom link. Lorsque l’un de ces types de liens se présente, la valeur actuelle de chaque variable identifiée est suivie. Cette variable n’est prise en compte que si [`linkTrackVars`](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linktrackvars.html) contient « events ».

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|---|---|---|---|
| N/D | N/D | Conversion | "Aucun" |

If an event is not in `linkTrackEvents`, it is not sent to Analytics, even if it is populated in the `onClick` event of a link, as shown in the following example:

```js
s.linkTrackVars="events" 
s.events="event1,event2" 
s.t() // both event1 and event2 are recorded 
<a href="help.php" onClick="s=s_gi('rs1');s.tl(this,'o')">event1 is recorded</a> 
<a href="test.php" onClick="s=s_gi('rs1');s.events='event2';s.tl(this,'o')">No events are recorded</a> 
```

The values of [`linkTrackVars`](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linktrackvars.html) and `linkTrackEvents` override the settings in the JS file and ensure only the variables and events specified in the custom link code are set for the specific link. Les paramètres de ces deux options affectent chaque téléchargement de fichier, lien de sortie et lien personnalisé. Les instances de chaque variable et de chaque événement peuvent être gonflées dans les situations où la variable (ou l’événement) s’applique à la page active, mais pas au téléchargement de fichier, lien de sortie ou lien personnalisé spécifique.

Pour garantir que les variables appropriées sont définies avec le code de lien personnalisé, Adobe conseille de définir *`linkTrackVars`* and *`linkTrackEvents`* within the custom link code, as follows:

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

In the above example, the value for `prop1` is set within the custom link code itself. The value of `prop2` comes from the current value of the variable as set on the page.

*Remarque : Si`linkTrackVars`(ou`linkTrackEvents`) est nul (ou une chaîne vide telle que ""), toutes les variables (ou tous les événements) Analytics définis pour la page active sont suivis. En d’autres termes, toutes les variables ayant des valeurs seraient envoyées avec des données de lien. Cela gonflera probablement les instances de chaque variable. Pour éviter le gonflement des instances ou des pages vues associées à d’autres variables, Adobe recommande de renseigner`linkTrackVars`et`linkTrackEvents`dans l’événement`onClick`d’un lien utilisé pour le suivi des liens.*

Toutes les variables qui doivent être envoyées avec des données de lien (liens personnalisés, de téléchargement et de sortie) doivent être répertoriées dans `linkTrackVars`. Si `linkTrackEvents` est utilisé, `linkTrackVars` doit contenir « events ».

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|---|---|---|---|
| N/D | N/D | Quelconque | "Aucun" |

When populating `linkTrackEvents`, do not use the 's.' prefix for variables. Par exemple, au lieu de le renseigner avec "s.event1", vous devez le renseigner avec "event1". L’exemple suivant illustre son utilisation.

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

Dans le premier lien, notez que la variable events conserve la valeur définie avant que le lien ne soit cliqué. This allows `event1` to be sent with the custom link. In the second example, the link to `event2` is not recorded because it is not listed in `linkTrackEvents`.

Pour éviter toute confusion et tout problème potentiel, Adobe recommande de renseigner [`linkTrackVars`](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linktrackvars.html) et `linkTrackEvents` dans l’événement `onClick` d’un lien utilisé pour le suivi des liens.

## Syntaxe et valeurs possibles

La variable *`linkTrackEvents`* est une liste d’événements séparés par des virgules (aucun espace).

```
s.linkTrackEvents="event1[,event2[,event3[...]]]"
```

Seuls les noms d’événement sont autorisés dans `linkTrackEvents`. Ces événements sont répertoriés à la section [Événements](https://docs.adobe.com/content/help/en/analytics/implementation/analytics-basics/ref-events.html). Si un espace apparaît avant ou après le nom de l’événement, l’événement ne peut pas être envoyé avec des demandes d’image de lien.

## Exemples

To track `prop1`, `eVar1`, and `event1` with every file download, exit link, and custom link, use the following settings within the global JS file:

```
s.linkTrackVars="prop1,eVar1,events"
```

```
s.linkTrackEvents="event1"
```

**Autres exemples**

```
s.linkTrackEvents="purchase,event1"
```

```
s.linkTrackEvents="scAdd,scCheckout,purchase,event14"
```

## Paramètres de configuration

Aucun

## Pièges, questions et conseils

* Le fichier JavaScript utilise uniquement `linkTrackEvents` si `linkTrackVars` contient la variable « events ». La variable « events » ne doit être incluse dans `linkTrackVars` uniquement lorsque la variable `linkTrackEvents` est définie.

* Soyez vigilant si un événement est déclenché sur une page et répertorié dans `linkTrackEvents`. Cet événement est à nouveau enregistré avec tout lien de sortie, de téléchargement ou personnalisé, sauf si la variable « events » est réinitialisée avant qu’il ne se produise (dans l’événement `onClick` d’un lien ou après l’appel à la fonction `t()`).

* Si la variable `linkTrackEvents` contient des espaces entre les noms d’événements, les événements ne sont pas enregistrés.
