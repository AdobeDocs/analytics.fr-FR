---
description: La segmentation des chemins d’accès par type d’utilisateur est une requête courante pour essayer de comprendre le cheminement de types d’utilisateurs spécifiques sur votre site.
keywords: Mise en œuvre d’Analytics
seo-description: La segmentation des chemins d’accès par type d’utilisateur est une requête courante pour essayer de comprendre le cheminement de types d’utilisateurs spécifiques sur votre site.
seo-title: Segmentation des chemins d’accès par type d’utilisateur
solution: Analytics
title: Segmentation des chemins d’accès par type d’utilisateur
topic: Développeur et mise en œuvre
uuid: 5c298f39-381d-453b-a608-109e3276b361
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Segmentation des chemins d’accès par type d’utilisateur

La segmentation des chemins d’accès par type d’utilisateur est une requête courante pour essayer de comprendre le cheminement de types d’utilisateurs spécifiques sur votre site.

Vous pouvez concaténer le type d’utilisateur et le nom de page dans une [!UICONTROL sprop], et activer le cheminement sur la [!UICONTROL sprop].

Supposons, par exemple, qu’il y ait deux types d’utilisateurs : des utilisateurs _enregistrés_ et des utilisateurs _non enregistrés_. Vous devez faire la distinction entre ces deux types sur chaque page et placer ces valeurs dans la [!UICONTROL sprop] désignée. Lorsque vous renseignez la prop, elle doit se présenter comme suit :

```js
 s.prop1="Registered : " + s.pageName;
```

Dans le cas d’un utilisateur enregistré qui a visité la page d’accueil, la valeur de la prop se présente comme suit :

```js
 "Registered : Home Page"
```

Si l’utilisateur clique sur une autre page appelée « Page 2 », la valeur correspondante se présente comme suit :

```js
 "Registered : Page 2"
```

Lorsque le [!UICONTROL cheminement] est activé, ces deux valeurs s’affichent l’une après l’autre. Pour savoir comment les utilisateurs enregistrés ont quitté la page d’accueil, recherchez la valeur « Registered : Home Page » dans l’un des rapports de cheminement et consultez les pages visitées ultérieurement. Dans le cas présent, ils se sont rendus sur la « Page 2 ».
