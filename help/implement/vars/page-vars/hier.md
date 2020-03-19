---
title: hier
description: Mettez en oeuvre des variables de hiérarchie dans Adobe Analytics.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# hier

Les variables de hiérarchie sont des variables personnalisées qui vous permettent de voir la structure d’un site.

> [!TIP] Cette variable était plus courante dans les versions précédentes d’Adobe Analytics. Adobe conseille plutôt d’utiliser [des eVars](evar.md) et des classifications.

Cette variable est utile pour les sites qui comportent plus de trois niveaux dans leur structure de site. Par exemple, un site multimédia peut comporter 4 niveaux pour la section Sports : `Sports`, `Local Sports`, `Baseball`et `Team name`. Si un visiteur accède à la page Base-ball, les niveaux Sports, Sports locaux et Base-ball reflètent tous cette visite.

Adobe prend en charge jusqu’à 5 variables de hiérarchie dans votre implémentation. Au moment où la hiérarchie est activée, décidez d’un délimiteur pour la variable et du nombre maximal de niveaux pour la hiérarchie. Par exemple, si le délimiteur est une virgule, la hiérarchie se présente comme suit :

```js
s.hier1 = "Sports,Local Sports,Baseball";
```

Veillez à ce qu’aucun de vos noms de section ne comporte de séparateur. Par exemple, si l’une de vos sections est appelée `Coach Griffin, Jim`, choisissez un délimiteur autre qu’une virgule. La limite de variable totale est de 255 octets. Les délimiteurs peuvent être constitués de plusieurs caractères, tels que `||` ou `/|\`, qui sont moins susceptibles d’apparaître dans les valeurs de variable.

## Exemples

```js
s.hier1="Toys|Boys 6+|Legos|Super Block Tub";
```

```js
s.hier4="Sports/Local Sports/Baseball";
```
