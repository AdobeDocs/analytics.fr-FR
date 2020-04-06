---
description: Description de la méthode de comptabilisation des instances sur les variables de marchandisage.
keywords: Analytics Implementation
title: Instances sur les variables de marchandisage
topic: Developer and implementation
uuid: 4cdfd53e-88aa-48cf-a135-98f7fc8dcece
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Instances sur les variables de marchandisage

Description de la méthode de comptabilisation des instances sur les variables de marchandisage.

Les instances ne sont actuellement pas prises en charge pour les variables de marchandisage. Si vous remarquez des instances dans un rapport contenant une variable de marchandisage, cela indique que l’eVar est définie à certains emplacements en dehors de la chaîne de produits et ne doit pas être considérée comme un nombre réel d’instances pour la variable de marchandisage sélectionnée.

Si vous utilisez la syntaxe des variables de conversion, une instance est comptabilisée chaque fois que la variable est définie. Toutefois, l’instance est attribuée à &quot;None&quot;, sauf si les événements suivants se produisent chaque fois que la variable est définie :

* Un  de liaison est défini.
* La variable products est définie.
* L’eVar de marchandisage a une valeur.

Par exemple, l’instance suivante d’eVar1 est allouée à &quot;Extérieur:Lunettes de ski&quot; :

```js
s.eVar1="Outdoors:Ski Goggles" 
s.events="prodView" 
s.products=";Fernie Snow Goggles"
```

Cependant, dans l’exemple suivant, l’instance d’eVar1 est allouée à &quot;Aucun&quot;, car toutes les conditions ne sont pas remplies lorsque l’eVar est définie (il n’existe pas de  de liaison et la variable products n’est pas définie) :

Page 1 de la visite :

```js
s.eVar1="Outdoors:Ski Goggles"
```

Page 2 de la visite :

```js
s.events="prodView" 
s.products=";Fernie Snow Goggles"
```

L’attribution à &quot;Aucun&quot; se produit si vous définissez une valeur pour une eVar sur une page où aucun de liaison ne se produit ou si vous définissez la valeur de l’eVar dans la chaîne de produits sans de liaison.

>[!NOTE] L’actuelle fonctionnalité de comptabilisation des instances sur des variables de marchandisage fait l’objet d’une révision. Sa modification est prévue pour une prochaine version.

