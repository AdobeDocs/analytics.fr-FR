---
description: Les variables dynamiques vous permettent de copier des valeurs d’une variable vers une autre sans entrer les valeurs complètes à plusieurs reprises dans les demandes d’image sur votre site.
keywords: Analytics Implementation
solution: null
title: Variables dynamiques
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

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
