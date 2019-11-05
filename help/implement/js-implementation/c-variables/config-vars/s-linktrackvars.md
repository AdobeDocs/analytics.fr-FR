---
description: Les variables dynamiques vous permettent de copier des valeurs d’une variable vers une autre sans entrer les valeurs complètes à plusieurs reprises dans les demandes d’image sur votre site.
keywords: Mise en œuvre d’Analytics
seo-description: Les variables dynamiques vous permettent de copier des valeurs d’une variable vers une autre sans entrer les valeurs complètes à plusieurs reprises dans les demandes d’image sur votre site.
solution: null
title: Variables dynamiques
translation-type: tm+mt
source-git-commit: 8c4c368a84ba5499d85f0b7512c99de47ddb14c2

---


# s.linkTrackVars

La variable est une liste de variables séparées par des virgules qui sont envoyées avec des liens personnalisés, de téléchargement et de sortie.

Si la variable *`linkTrackVars`* est définie sur “”, toutes les variables qui comportent des valeurs sont envoyées avec des données de lien. Pour éviter le gonflement des instances ou des pages vues associées à d’autres variables, Adobe recommande de renseigner *`linkTrackVars`* et *`linkTrackEvents`* dans l’événement [!UICONTROL onClick] d’un lien utilisé pour le suivi des liens.

Toutes les variables qui doivent être envoyées avec des données de lien (liens personnalisés, de téléchargement et de sortie) doivent être répertoriées dans *`linkTrackVars`*. Si *`linkTrackEvents`* est utilisé, *`linkTrackVars`* doit contenir « events ».

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|---|---|---|---|
| N/D | N/D | Quelconque | "Aucun" |

When populating *`linkTrackVars`*, do not use the 's.' prefix for variables. Par exemple, au lieu de renseigner *`linkTrackVars`* avec « s.prop1 », vous devez le renseigner avec « prop1 ». L’exemple suivant illustre la manière d’utiliser *`linkTrackVars`*.

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

Dans la mesure où le lien vers google.com est un lien de sortie (sauf si votre société est Google), « event1 » et « eVar1 » sont envoyés avec les données du lien de sortie, ce qui a pour effet d’augmenter le nombre d’instances associées à « eVar1 » et le nombre de déclenchements de « event1 ». Dans le lien pointant vers [!DNL test.php], [!UICONTROL eVar1] est envoyée avec la valeur de « value C », car il s’agit de la valeur actuelle de [!UICONTROL eVar1] au moment où la fonction *`tl()`* est appelée.

## Syntaxe et valeurs possibles

La variable *`linkTrackVars`* est une liste de noms de variables séparés par des virgules et sensibles à la casse. Elle est dépourvue de préfixe de nom d’objet. Utilisez « eVar1 » plutôt que « s.eVar1 ».

```js
s.linkTrackVars="variable_name[,variable_name[...]]"
```

Il se peut que La variable *`linkTrackVars`* ne peut contenir que des variables envoyées vers [!DNL Analytics], à savoir : *`events`*, *`campaign`*, *`purchaseID`*, *`products`*, [!UICONTROL eVar1-75] ,[!UICONTROL prop1-75], [!UICONTROL hier1-5], *`channel`*, *`server`*, *`state`*, *`zip`* et *`pageType`*.

## Exemples

```js
s.linkTrackVars="events,prop1,eVar49"
```

```js
s.linkTrackVars="products"
```

## Paramètres de configuration

Aucun

## Pièges, questions et conseils

* Si *`linkTrackVars`* est vide, toutes les variables qui comportent des valeurs sont suivies avec tous les appels au serveur.
* Toute variable répertoriée dans *`linkTrackVars`* et qui comporte une valeur au moment où un lien personnalisé, de téléchargement ou de sortie est utilisé, est suivie.
* Si *`linkTrackEvents`* est utilisé, *`linkTrackVars`* doit contenir « events ».

* N’utilisez pas le préfixe « s. » ou « s_objectname. » pour les variables.
