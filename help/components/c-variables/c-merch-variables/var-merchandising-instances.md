---
description: Description de la méthode de comptabilisation des instances sur les variables de marchandisage.
keywords: Mise en œuvre d’Analytics
seo-description: Description de la méthode de comptabilisation des instances sur les variables de marchandisage.
seo-title: Instances sur les variables de marchandisage
solution: Analytics
title: Instances sur les variables de marchandisage
topic: Développeur et mise en œuvre
uuid: 4cdfd53e-88aa-48cf-a135-98f7fc8dcece
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Instances sur les variables de marchandisage

Description de la méthode de comptabilisation des instances sur les variables de marchandisage.

Les instances ne sont actuellement pas prises en charge pour les variables de marchandisage. Si vous observez des instances dans un rapport contenant une variable de marchandisage, ceci indique que l’eVar est définie en certains emplacements en dehors de la chaîne de produits et ne doit pas être considérée comme un nombre réel d’instances pour la variable de marchandisage sélectionnée.

Si vous utilisez le paramètre Syntaxe de la variable de conversion, une instance est comptabilisée chaque fois que la variable est définie. Cependant, l’instance est attribuée à « Aucun », sauf si les événements suivants se produisent chaque fois que la variable est définie :

* Un événement de liaison est défini.
* La variable products est définie.
* L’eVar de marchandisage comporte une valeur.

Par exemple, l’instance suivante d’eVar1 est allouée à « Extérieur:Lunettes de ski » :

```js
s.eVar1="Outdoors:Ski Goggles" 
s.events="prodView" 
s.products=";Fernie Snow Goggles"
```

Cependant, dans l’exemple suivant, l’instance d’eVar1 est allouée à « Aucun », étant donné que toutes les conditions ne sont pas remplies lorsque l’eVar est définie (aucun événement de liaison n’est présent et la variable products n’est pas définie) :

Page 1 de la visite :

```js
s.eVar1="Outdoors:Ski Goggles"
```

Page 2 de la visite :

```js
s.events="prodView" 
s.products=";Fernie Snow Goggles"
```

L’instance n’est allouée à « Aucun » que si vous définissez une valeur pour une eVar sur une page sur laquelle aucun événement de liaison ne survient ou si vous définissez la valeur d’eVar dans la chaîne de produits sans événement de liaison.

> [!NOTE] La fonctionnalité actuelle de comptabilisation des instances sur les variables de marchandisage est en cours de révision et devrait être modifiée dans une prochaine version.

