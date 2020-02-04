---
title: hier
description: Mettez en oeuvre des variables de hiérarchie dans Adobe Analytics.
translation-type: tm+mt
source-git-commit: 751d19227d74d66f3ce57888132514cf8bd6f7fc

---


# hier

Les variables de hiérarchie sont des variables personnalisées qui vous permettent de voir la structure d’un site.

Cette variable est particulièrement utile pour les sites dont la structure comprend plus de trois niveaux. Par exemple, la section Sports d’un site de médias peut comporter 4 niveaux : Sports, Sports locaux, Base-ball et Red Sox. Si un visiteur accède à la page Base-ball, les niveaux Sports, Sports locaux et Base-ball reflètent tous cette visite.

Cinq variables de [!UICONTROL hiérarchie] sont disponibles. Elles doivent être activées par le service à la clientèle Adobe. Au moment de l’activation de la hiérarchie, vous devez choisir un séparateur pour la variable, ainsi que le nombre maximal de niveaux pour la hiérarchie. Par exemple, si le délimiteur est une virgule, la hiérarchie Sports peut se présenter comme suit.

```js
s.hier1="Sports,Local Sports,Baseball"
```

Veillez à ce qu’aucun de vos noms de section ne comporte de séparateur. Par exemple, si l’une de vos sections s’intitule « Coach Griffin, Jim », vous devez opter pour un séparateur autre que la virgule. Chaque section de la hiérarchie est limitée à 255 octets, la limite de variable totale étant de 255 octets. Une fois le séparateur choisi (au moment de la création de la hiérarchie), il est difficile de le modifier.

Contactez le service à la clientèle Adobe pour modifier le séparateur d’une hiérarchie existante. Les séparateurs peuvent également se composer de plusieurs caractères, tels que || ou /|\, dont les probabilités d’affichage dans une section sont moins élevées.

## Syntaxe et valeurs possibles

N’insérez pas d’espace entre deux séparateurs. Dans l’exemple de syntaxe ci-dessous, N est un nombre compris entre 1 et 5.

```js
s.hierN="Level 1[<delimiter>Level 2[<delimiter>Level 3[...]]]"
```

N’utilisez le séparateur que pour délimiter les niveaux de la hiérarchie. Le séparateur peut être un ou plusieurs caractères de votre choix.

## Exemples

```js
s.hier1="Toys|Boys 6+|Legos|Super Block Tub"
```

```js
s.hier4="Sports/Local Sports/Baseball"
```

## Pièges, questions et conseils

* Une fois la hiérarchie configurée, le séparateur ne peut plus être modifié. S’il s’avère nécessaire de modifier le séparateur de votre hiérarchie, contactez le service à la clientèle Adobe.
* Une fois la hiérarchie configurée, le nombre de niveaux ne peut plus être modifié.

> [!NOTE] Toute modification apportée à une hiérarchie peut entraîner des frais de service.
