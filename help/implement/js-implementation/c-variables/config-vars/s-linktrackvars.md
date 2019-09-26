---
description: Les variables dynamiques vous permettent de copier des valeurs d’une variable vers une autre sans entrer les valeurs complètes à plusieurs reprises dans les demandes d’image sur votre site.
keywords: Mise en œuvre d’Analytics
seo-description: Les variables dynamiques vous permettent de copier des valeurs d’une variable vers une autre sans entrer les valeurs complètes à plusieurs reprises dans les demandes d’image sur votre site.
solution: null
title: Variables dynamiques
translation-type: tm+mt
source-git-commit: 60dd1b300035e5149f53870239de85fb3174a77a

---


# s.linkTrackVars

La variable est une liste de variables séparées par des virgules qui sont envoyées avec des liens personnalisés, de téléchargement et de sortie.

If *`linkTrackVars`* is set to "", all variables that have values are sent with link data. Pour éviter le gonflement des instances ou des pages vues associées à d’autres variables, Adobe conseille de renseigner *`linkTrackVars`* et *`linkTrackEvents`* dans l’événement [!UICONTROL onClick] d’un lien utilisé pour le suivi des liens.

Toutes les variables qui doivent être envoyées avec des données de lien (liens personnalisés, de téléchargement et de sortie) doivent être répertoriées dans *`linkTrackVars`*. Si *`linkTrackEvents`* est utilisé, *`linkTrackVars`* doit contenir "events".

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|---|---|---|---|
| N/D | N/D | Quelconque | "Aucun" |

Lorsque vous renseignez *`linkTrackVars`*, do not use the 's.' prefix for variables. Par exemple, au lieu de renseigner *`linkTrackVars`* "s.prop1", vous devez le renseigner avec "prop1". L’exemple suivant illustre l’utilisation *`linkTrackVars`* à utiliser.

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

Dans la mesure où le lien vers google.com est un lien de sortie (sauf si votre société est Google), « event1 » et « eVar1 » sont envoyés avec les données du lien de sortie, ce qui a pour effet d’augmenter le nombre d’instances associées à « eVar1 » et le nombre de déclenchements de « event1 ». In the link to [!DNL test.php], [!UICONTROL eVar1] is sent with a value of 'value C' because that is the current value of [!UICONTROL eVar1] at the time that *`tl()`* is called.

## Syntaxe et valeurs possibles

La syntaxe de la variable *`linkTrackVars`* est une liste de noms de variables séparés par des virgules et sensibles à la casse. Elle est dépourvue de préfixe de nom d’objet. Utilisez « eVar1 » plutôt que « s.eVar1 ».

```js
s.linkTrackVars="variable_name[,variable_name[...]]"
```

Il se peut que ne peut contenir que des variables envoyées *`linkTrackVars`* [!DNL Analytics], à savoir : *`events`*, *`campaign`**`purchaseID`*, *`products`* eVar1-75 [!UICONTROL ,][!UICONTROL prop1-75, hier1-5,,, et.]*`channel`**`server`**`state`**`zip`**`pageType`*

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

* If *`linkTrackVars`* is blank, all variables that have values are tracked with all server calls.
* Any variable listed in *`linkTrackVars`* that has a value at the time of any download, exit, or custom link, are tracked.
* Si *`linkTrackEvents`* est utilisé, *`linkTrackVars`* doit contenir "events".

* N’utilisez pas le préfixe « s. » ou « s_objectname. » pour les variables.