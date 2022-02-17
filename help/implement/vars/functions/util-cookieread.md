---
title: Util.cookieRead
description: Obtient la valeur d’un cookie.
feature: Variables
exl-id: b05b628c-bae6-4dba-bc1d-6a1ab56e3660
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '171'
ht-degree: 100%

---

# Util.cookieRead

Les cookies peuvent stocker et récupérer des informations sur plusieurs pages du même domaine. Utilisez la méthode `Util.cookieRead()` pour récupérer une valeur d’un cookie.

## Lecture des cookies à l’aide de balises dans Adobe Experience Platform

Vous pouvez lire les cookies en définissant des valeurs dans les éléments de données.

1. Connectez-vous à l’[interface utilisateur de la collecte de données](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
2. Cliquez sur la propriété de votre choix.
3. Accédez à l’onglet [!UICONTROL Éléments de données], puis cliquez sur l’élément de données souhaité (ou créez un élément de données).
4. Définissez la liste déroulante [!UICONTROL Extension] sur [!UICONTROL Core] et le [!UICONTROL Type d’élément de données] sur [!UICONTROL Cookie].
5. Entrez le nom du cookie dans le champ de texte.

La valeur du cookie est stockée dans l’élément de données. Vous pouvez ensuite référencer l’élément de données dans les règles pour affecter des variables Analytics.

## s.Util.cookieRead() dans AppMeasurement et l’éditeur de code personnalisé

Appelez la méthode `s.Util.cookieRead()` pour lire une valeur de cookie. Son seul argument est une chaîne obligatoire. Cette méthode renvoie une chaîne contenant la valeur du cookie. Si les cookies n’existent pas, une chaîne vide est renvoyée.

```js
// Reads the value set in the cookie named 'example' and assigns the value to eVar1
s.eVar1 = s.Util.cookieRead("example");
```
