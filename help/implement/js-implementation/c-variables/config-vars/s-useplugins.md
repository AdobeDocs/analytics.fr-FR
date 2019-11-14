---
description: Les variables dynamiques vous permettent de copier des valeurs d’une variable vers une autre sans entrer les valeurs complètes à plusieurs reprises dans les demandes d’image sur votre site.
keywords: Analytics Implementation
solution: null
title: Variables dynamiques
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# s.usePlugins

Si la fonction  est disponible et contient du code utile, la variable [!UICONTROL s_usePlugins] doit être définie sur « true ».

Lorsque [!UICONTROL usePlugins] a la valeur « true », la fonction *`s_doPlugins`* est appelée avant chaque demande d’image.

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|---|---|---|---|
| N/D | N/D | N/D | True |

## Syntaxe et valeurs possibles

```js
s.usePlugins=true|false
```

La variable [!UICONTROL usePlugins] doit être définie sur « true » ou « false ».

## Exemples

```js
s.usePlugins=true
```

```js
s.usePlugins=false
```

La variable [!UICONTROL usePlugins] ne doit être définie sur « false » (ou non déclarée) que si la fonction *`s_doPlugins`* n’est pas déclarée dans votre fichier JavaScript.

## Paramètres de configuration

Aucun
