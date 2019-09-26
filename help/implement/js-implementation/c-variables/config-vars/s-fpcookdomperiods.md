---
description: Les variables dynamiques vous permettent de copier des valeurs d’une variable vers une autre sans entrer les valeurs complètes à plusieurs reprises dans les demandes d’image sur votre site.
keywords: Mise en œuvre d’Analytics
seo-description: Les variables dynamiques vous permettent de copier des valeurs d’une variable vers une autre sans entrer les valeurs complètes à plusieurs reprises dans les demandes d’image sur votre site.
solution: null
title: Variables dynamiques
translation-type: tm+mt
source-git-commit: b38ba4222951d957c607cd764224028527835c7e

---


# s.fpCookieDomainPeriods

La variable concerne les cookies définis par JavaScript (s_sq, s_cc, modules externes), qui sont intrinsèquement des cookies propriétaires, même si votre mise en œuvre utilise les domaines tiers 2o7.net ou omtrdc.net.

The *`fpCookieDomainPeriods`* variable should never be dynamically set . If you use , it is good practice to specify a value for  as well. *`cookieDomainPeriods`**`fpCookieDomainPeriods`* *`fpCookieDomainPeriods`* inherits the *`cookieDomainPeriods`* value. Note that *`fpCookieDomainPeriods`* does not affect the domain on which the visitor ID cookie is set, even if your implementation treats this as a first-party cookie.

The name " " refers to the number of periods (".") *`fpCookieDomainPeriods`* dans le domaine, lorsque celui-ci commence par « www ». For example, `www.mysite.com` contains two periods, while `www.mysite.co.jp` contains three periods. Another way to describe the variable is the number of sections in the main domain of the site (two for `mysite.com` and three for `mysite.co.jp`).

The [!DNL AppMeasurement] for JavaScript file uses the *`fpCookieDomainPeriods`* variable to determine the domain with which to set first-party cookies other than the [!UICONTROL visitor ID] (s_vi) cookie. There are at least two cookies affected by this variable, including `s_sq` and `s_cc` (used for visitor click map and cookie checking respectively). Les cookies utilisés par des modules externes, tels que [!UICONTROL getValOnce] sont également affectés.

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|---|---|---|---|
| N/D | N/D | N/D | cookieDomainPeriods |

## Exemple de code pour la définition de variables de domaine de cookies

```js
s.fpCookieDomainPeriods="2" 
var d=window.location.hostname 
if(d.indexOf('.co.uk')>-1||d.indexOf('.com.au')>-1) 
  s.fpCookieDomainPeriods="3" 
```

## Syntaxe et valeurs possibles

La syntaxe de la variable *`cookieDomainPeriods`* soit une chaîne, comme illustré ci-dessous.

```js
s.fpCookieDomainPeriods="3"
```

## Exemples

```js
s.fpCookieDomainPeriods="3"
```

```js
s.fpCookieDomainPeriods="2"
```

## Paramètres de configuration

Aucun