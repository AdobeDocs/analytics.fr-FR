---
title: hier
description: Mettez en œuvre des variables de hiérarchie dans Adobe Analytics.
feature: Variables
exl-id: 72bdab8f-a001-4ada-b5e2-453a8e3f24a6
source-git-commit: a71db2fac9333b70a55da91fe9a94b0cc8434b42
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 93%

---

# hier

Les variables de hiérarchie sont des variables personnalisées qui vous permettent de voir la structure d’un site.

>[!TIP]
>
>Cette variable était plus courante dans les versions précédentes d’Adobe Analytics. Adobe recommande d’utiliser plutôt des [eVars](evar.md) et des classifications.

>[!IMPORTANT]
>
>La hiérarchie n’est pas prise en charge dans la collecte de données à l’aide de XDM pour Experience Edge.

Cette variable est utile pour les sites dont la structure comprend plus de trois niveaux. Par exemple, la section Sports d’un site multimédia peut comporter 4 niveaux : `Sports`, `Local Sports`, `Baseball` et `Team name`. Si un visiteur accède à la page Base-ball, les niveaux Sports, Sports locaux et Base-ball reflètent tous cette visite.

Adobe prend en charge jusqu’à 5 variables de hiérarchie dans votre implémentation. Au moment de l’activation de la hiérarchie, choisissez un séparateur pour la variable, ainsi que le nombre maximal de niveaux pour la hiérarchie. Par exemple, si le délimiteur est une virgule, la hiérarchie se présente comme suit :

```js
s.hier1 = "Sports,Local Sports,Baseball";
```

Veillez à ce qu’aucun de vos noms de section ne comporte de séparateur. Par exemple, si l’une de vos sections est appelée `Coach Griffin, Jim`, choisissez un délimiteur autre qu’une virgule. La limite de variable totale est de 255 octets. Les délimiteurs peuvent être composés de plusieurs caractères, tels que `||` ou `/|\`, qui sont moins susceptibles d’apparaître dans les valeurs de variable.

## Exemples

```js
s.hier1="Toys|Boys 6+|Legos|Super Block Tub";
```

```js
s.hier4="Sports/Local Sports/Baseball";
```
