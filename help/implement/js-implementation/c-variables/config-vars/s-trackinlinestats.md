---
description: Les variables dynamiques vous permettent de copier des valeurs d’une variable vers une autre sans entrer les valeurs complètes à plusieurs reprises dans les demandes d’image sur votre site.
keywords: Mise en œuvre d’Analytics
seo-description: Les variables dynamiques vous permettent de copier des valeurs d’une variable vers une autre sans entrer les valeurs complètes à plusieurs reprises dans les demandes d’image sur votre site.
solution: null
title: Variables dynamiques
translation-type: tm+mt
source-git-commit: 8c4c368a84ba5499d85f0b7512c99de47ddb14c2

---


# s.trackInlineStats

La variable détermine si les données ClickMap sont collectées.

Si la variable *`trackInlineStats`* est définie sur « true », les données relatives à la page et au lien sur lequel l’utilisateur a cliqué sont stockées dans un cookie appelé s_sq. Si elle est définie sur « false », le cookie s_sq reçoit la valeur « [[B]] », qui est considérée comme nulle.

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|---|---|---|---|
| N/D | N/D | ClickMap | False |

## Syntaxe et valeurs possibles

```
js
s.trackInlineStats=true|false
```

La variable *`trackInlineStats`* doit être définie sur « true » ou « false ».

## Exemples

```js
s.trackInlineStats=true
```

```js
s.trackInlineStats=false
```

## Paramètres de configuration

Aucun
