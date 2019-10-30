---
description: Les variables dynamiques vous permettent de copier des valeurs d’une variable vers une autre sans entrer les valeurs complètes à plusieurs reprises dans les demandes d’image sur votre site.
keywords: Mise en œuvre d’Analytics
seo-description: Les variables dynamiques vous permettent de copier des valeurs d’une variable vers une autre sans entrer les valeurs complètes à plusieurs reprises dans les demandes d’image sur votre site.
solution: null
title: Variables dynamiques
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# s.fpCookieDomainPeriods

La variable concerne les cookies définis par JavaScript (s_sq, s_cc, modules externes), qui sont intrinsèquement des cookies propriétaires, même si votre mise en œuvre utilise les domaines tiers 2o7.net ou omtrdc.net.

La variable *`fpCookieDomainPeriods`* ne doit jamais être définie de manière dynamique. Si vous utilisez *`cookieDomainPeriods`*, il est recommandé de spécifier également une valeur pour *`fpCookieDomainPeriods`*. *`fpCookieDomainPeriods`* hérite de la valeur *`cookieDomainPeriods`*. Notez que *`fpCookieDomainPeriods`* n’affecte pas le domaine sur lequel le cookie d’identifiant visiteur est défini, même si votre mise en œuvre le considère comme un cookie propriétaire.

Le nom « *`fpCookieDomainPeriods`* » fait référence au nombre de points (« . ») dans le domaine, lorsque celui-ci commence par « www ». Par exemple, `www.mysite.com` comporte deux points, tandis que `www.mysite.co.jp` en comporte trois. Une autre méthode pour décrire la variable consiste à utiliser le nombre de sections contenues dans le domaine principal du site (deux pour `mysite.com` et trois pour `mysite.co.jp`).

Le fichier [!DNL AppMeasurement] pour JavaScript utilise la variable *`fpCookieDomainPeriods`* pour déterminer le domaine qui sert à définir des cookies internes différents du cookie d’[!UICONTROL ID de visiteur] (s_vi). There are at least two cookies affected by this variable, including `s_sq` and `s_cc` (used for visitor click map and cookie checking respectively). Les cookies utilisés par des modules externes, tels que [!UICONTROL getValOnce] sont également affectés.

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

Il est prévu que la variable *`cookieDomainPeriods`* soit une chaîne, comme illustré ci-dessous.

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