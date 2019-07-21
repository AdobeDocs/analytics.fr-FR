---
description: La segmentation des chemins d’accès par type d’utilisateur est une requête courante pour essayer de comprendre le cheminement de types d’utilisateurs spécifiques sur votre site.
keywords: Mise en œuvre d’Analytics
seo-description: La segmentation des chemins d’accès par type d’utilisateur est une requête courante pour essayer de comprendre le cheminement de types d’utilisateurs spécifiques sur votre site.
seo-title: Chemins de segment par type d'utilisateur
solution: Analytics
title: Chemins de segment par type d'utilisateur
topic: Développeur et mise en œuvre
uuid: 5 c 298 f 39-381 d -453 b-a 608-109 e 3276 b 361
translation-type: tm+mt
source-git-commit: 76d0ce11d9b560e0df866be9e753804b6fa4bb3d

---


# Chemins de segment par type d'utilisateur

La segmentation des chemins d’accès par type d’utilisateur est une requête courante pour essayer de comprendre le cheminement de types d’utilisateurs spécifiques sur votre site.

Vous pouvez concaténer le type d’utilisateur et le nom de page dans une [!UICONTROL sprop], et activer le cheminement sur la [!UICONTROL sprop].

For example, let's say you have two user types: _Registered_ users and _Non-Registered_ users. Vous devez faire la distinction entre ces deux types sur chaque page et placer ces valeurs dans la [!UICONTROL sprop] désignée. Lorsque vous renseignez la prop, elle doit se présenter comme suit :

```js
 s.prop1=”Registered : “ + s.pageName;
```

Dans le cas d’un utilisateur enregistré qui a visité la page d’accueil, la valeur de la prop se présente comme suit :

```js
 “Registered : Home Page”
```

Si l’utilisateur clique sur une autre page appelée « Page 2 », la valeur correspondante se présente comme suit :

```js
 “Registered : Page 2”
```

Lorsque le [!UICONTROL cheminement] est activé, ces deux valeurs s’affichent l’une après l’autre. Pour savoir comment les utilisateurs enregistrés ont quitté la page d’accueil, recherchez la valeur « Registered : Home Page » dans l’un des rapports de cheminement et consultez les pages visitées ultérieurement. Dans le cas présent, ils se sont rendus sur la « Page 2 ».
