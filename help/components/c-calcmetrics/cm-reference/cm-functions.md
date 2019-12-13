---
description: Le créateur de mesures calculées permet d’appliquer des fonctions statistiques et mathématiques afin de créer des mesures calculées avancées.
title: 'Référence : fonctions de base'
uuid: 5c2b4a0e-613c-4b27-95b8-01d480aeab78
translation-type: tm+mt
source-git-commit: 83066f8e372fb5f8af3b7db2c165ab1cd8b76a10

---


# Référence : fonctions de base

Le créateur de mesures calculées permet d’appliquer des fonctions statistiques et mathématiques afin de créer des mesures calculées avancées.

Vous trouverez ci-dessous une liste alphabétique des fonctions ainsi que leur définition.

> [!NOTE] Lorsque [!DNL metric] est identifié en tant qu’argument d’une fonction, d’autres expressions des mesures sont également autorisées. Par exemple, [!DNL MAXV(metrics)] autorise également [!DNL MAXV(PageViews + Visits).].

## Fonctions de tableau et fonctions de ligne {#section_8977BE40A47E4ED79EB543A9703A4905}

Une fonction de tableau consiste à ce que la sortie soit la même pour chaque ligne du tableau. Une fonction de ligne consiste à ce que la sortie soit différente pour chaque ligne du tableau.

## Valeur absolue (ligne) {#concept_4CC47884F7CA49D5B84AC898EA596673}

Renvoie la valeur absolue d’un nombre. La valeur absolue d’un nombre est le nombre doté d’une valeur positive.

```
ABS(metric)
```

| Argument | Description |
|---|---|
| *metric* | Mesure pour laquelle vous souhaitez obtenir la valeur absolue. |

## Max. colonne {#concept_B25518D717D24F82B65CDE49A153D3A3}

Renvoie la valeur la plus grande d’un ensemble d’éléments de dimension pour une colonne de mesures. MAXV évalue verticalement dans une seule colonne (mesure) sur l’ensemble des éléments de dimension.

```
MAXV(metric)
```

| Argument | Description |
|---|---|
| *metric* | Mesure que vous souhaiteriez faire évaluer. |

## Min. colonne {#concept_5B1033F8ACE9485F9AD3CDC0D146391B}

Renvoie la valeur la plus petite d’un ensemble d’éléments de dimension pour une colonne de mesures. MINV évalue verticalement dans une seule colonne (mesure) sur l’ensemble des éléments de dimension.

```
MINV(metric)
```

| Argument | Description |
|---|---|
| *metric* | Mesure que vous souhaiteriez faire évaluer. |

## Somme de la colonne {#concept_391F04FBC3CC43368CA0C5AACE74D4B1}

Ajoute toutes les valeurs numériques pour une mesure dans une colonne (sur l’ensemble des éléments d’une dimension).

```
SUM(metric)
```

| Argument | Description |
|---|---|
| *metric* | Mesure pour laquelle vous souhaitez obtenir la valeur totale ou la somme. |

## Décompte (tableau) {#concept_2C6ED2B88AB74481BD130969FB071A41}

Renvoie le nombre, ou le décompte, des valeurs différentes de zéro pour une mesure dans une colonne (le nombre d’éléments uniques signalés dans une dimension).

```
COUNT(metric)
```

| Argument | Description |
|---|---|
| *metric* | Mesure que vous souhaitez décompter. |

## Exposant (ligne) {#concept_17554F9D234449FB8DDEE895816B3FF1}

Renvoie *e* élevé à la puissance d’un nombre donné. La constante *e* est égale à 2,71828182845904, la base du logarithme népérien. EXP est l’inverse de LN, l’algorithme népérien d’un nombre.

```
EXP(metric)
```

| Argument | Description |
|---|---|
| *metric* | Exposant appliqué à la base *e*. |

## Elévation à une puissance {#concept_941578534F1E4583B1BEB067C8113A21}

Opérateur de puissance

<pre>
pow(x,y) =<sup>xy</sup> = x*x*x*... (y fois)
</pre>

## Moyenne (tableau) {#concept_F4FF950580304D0B99DA7FBB5DB8730A}

Renvoie la moyenne arithmétique, ou moyenne, pour une mesure dans une colonne.

```
MEAN(metric)
```

| Argument | Description |
|---|---|
| *metric* | Mesure pour laquelle vous souhaitez obtenir la moyenne. |

## Médiane (tableau) {#concept_183EC31208524EDB8463D986DE2E895F}

Renvoie la médiane pour une mesure dans une colonne. La médiane est le nombre au milieu d’un ensemble de nombres, c’est-à-dire que la moitié des nombres ont une valeur supérieure ou égale à la médiane et la moitié une valeur inférieure ou égale à la médiane.

```
MEDIAN(metric)
```

| Argument | Description |
|---|---|
| *metric* | Mesure pour laquelle vous souhaitez obtenir la médiane. |

## Modulo {#concept_DE0825D7A51643219CB01F59667EA352}

Reste de col1 / col2, en utilisant la division euclidienne.

Renvoie le reste après la division de x par y.

```
x = floor(x/y) + modulo(x,y)
```

La valeur de renvoi comporte le même signe que l’entrée (ou est égale à zéro).

```
modulo(4,3) = 1 
modulo(-4,3) = -1 
modulo(-3,3) = 0
```

Pour obtenir systématiquement un nombre positif, utilisez

```
modulo(modulo(x,y)+y,y)
```

## Percentile (tableau) {#concept_51DF57B606D14F898E5010DBA61CA979}

Renvoie le percentile k-th des valeurs pour une mesure. Vous pouvez utiliser cette fonction pour établir un seuil d’acceptation. Par exemple, vous pouvez décider d’examiner les éléments de dimension dont le score est supérieur au 90e percentile.

```
PERCENTILE(metric,k)
```

<table id="table_35CD840ACFB44CD9979881DB8823CC53"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Argument </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <i>metric</i> </td> 
   <td colname="col2"> Colonne de mesures qui définit l’étendue relative. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>k </p> </td> 
   <td colname="col2"> Percentile dans la plage de 0 à 100, inclusif. </td> 
  </tr> 
 </tbody> 
</table>

## Quartile (tableau) {#concept_BFD37F0F23A24AD181407142233FA151}

Renvoie le quartile des valeurs pour une mesure. Par exemple, les quartiles peuvent être utilisés pour trouver les 25 % de produits générant le plus de recettes. MINV, MEDIAN et MAXV renvoient la même valeur que QUARTILE lorsque quart est égal à 0 (zéro), 2 et 4, respectivement.

```
QUARTILE(metric,quart)
```

<table id="table_64EA3DAAE77541439D59FAF0353F83A2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Argument </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <i>metric</i> </td> 
   <td colname="col2"> Mesure pour laquelle vous souhaitez obtenir la valeur du quartile. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>quart </p> </td> 
   <td colname="col2"> Indique la *valeur à retourner. </td> 
  </tr> 
 </tbody> 
</table>

*Si *quart* = 0, QUARTILE renvoie la valeur minimale. Si *quart* = 1, QUARTILE renvoie le premier quartile (25e percentile). Si *quart* = 2, QUARTILE renvoie le premier quartile (50e percentile). Si *quart* = 3, QUARTILE renvoie le premier quartile (75e percentile). Si *quart* = 4, QUARTILE renvoie la valeur maximale.

## Tour {#concept_2F12F2A6ACD445A0A8FF648AE4D4CB9E}

Renvoie l’entier le plus proche pour une valeur donnée. Par exemple, si vous souhaitez éviter de signaler les décimales de devise pour les recettes et qu’un produit a une recette de 569,34 $, utilisez la formule Arrondi(*Recettes*) pour arrondir la recette au dollar le plus proche, soit 569 $. Un produit à 569,51 $ est arrondi au dollar le plus proche, soit 570 $.

```
ROUND(metric)
```

| Argument | Description |
|---|---|
| *number* | Mesure que vous souhaitez arrondir. |

Un arrondi sans paramètre de positions décimales est identique à un arrondi avec 0 position décimale, soit un arrondi au nombre entier le plus proche. Avec un paramètre de positions décimales, la valeur renvoyée contient ce nombre de positions à droite de la décimale. Si le paramètre est négatif, il renvoie des 0 à gauche de la décimale.

```
round( 314.15, 0) = 314 
round( 314.15, 1) = 314.1 
round( 314.15, -1) = 310 
round( 314.15, -2) = 300
```

## Décompte de lignes {#concept_0DBF5995881C47CF95F793125F3A0E2B}

Renvoie le nombre de lignes pour une colonne donnée (le nombre d’éléments uniques pris en compte dans une dimension). « Nombre d’éléments uniques dépassé » compte pour 1.

## Max. ligne {#concept_984D045D7EDD4A1ABED454CDF2EC23C5}

Nombre maximal de colonnes dans chaque ligne.

## Min. ligne {#concept_A6FB9E72C70A43D0B31565E70B8122BD}

Nombre minimal de colonnes dans chaque ligne.

## Somme de la ligne {#concept_E9EAB0FC5233498F907E7A078698A98E}

Somme des colonnes de chaque ligne.

## Racine carrée (ligne) {#concept_6460DFA51EC24527A2317970FB76D404}

Renvoie la racine carrée positive d’un nombre. La racine carrée d’un nombre est la valeur de ce nombre élevée à la puissance 1/2.

```
SQRT(metric)
```

| Argument | Description |
|---|---|
| *number* | Mesure pour laquelle vous souhaitez obtenir la racine carrée. |

## Écart type (tableau) {#concept_A383A8BCC6FA42D7B73F7C83997D782A}

Renvoie l’écart type, ou la racine carrée de l’écart, selon l’échantillon de population de données.

L’équation pour l’écart type (STDEV) est la suivante :

![](assets/std_dev.png)

où x est l’exemple de moyenne (*metric*) et *n* l’exemple de taille.

```
STDEV(metric)
```

<table id="table_8BCF2E4B02434AABAAD026FB3C4E8B2F"> 
 <tbody> 
  <tr> 
   <td> <b> Argument</b> </td> 
   <td> <b> Description</b> </td> 
  </tr> 
  <tr> 
   <td> <b> <i> metric</i> </b> </td> 
   <td> <p> Mesure pour laquelle vous souhaitez obtenir l’écart type. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Variance (tableau) {#concept_269751EDC5A34E689112AE16E04A11B0}

Renvoie la variance basée sur un échantillon de population de données.

L’équation pour la VARIANCE est la suivante :

![](assets/variance_eq.png)

où x est l’exemple de moyenne MOYENNE(*mesure*) et *n* l’exemple de taille.

```
VARIANCE(metric)
```

| Argument | Description |
|---|---|
| *metric* | Mesure pour laquelle vous souhaitez obtenir la variance. |

Pour calculer une variance, vous prenez une colonne entière de nombres. Vous calculez d’abord la moyenne de cette série de nombres. Une fois que vous avez obtenu la moyenne, vous effectuez les opérations suivantes avec chaque entrée :

1. Vous soustrayez la moyenne du nombre.

2. Vous calculez le carré du résultat.

3. Vous ajoutez ce résultat au total.

Une fois que vous avez effectué ces opérations sur la colonne entière, vous obtenez un total unique. Vous divisez ensuite ce total par le nombre d’éléments de la colonne. Ce nombre est la variance de la colonne. Il s’agit d’un seul nombre. Il est toutefois présenté sous la forme d’une colonne de nombres.

Prenons comme exemple une colonne de 3 éléments :

1

2

3

La moyenne de cette colonne est 2. La variance de la colonne est ((1 - 2)² + (2 - 2)² + (3 - 2)²/3 = 2/3. Dans les Ad Hoc Analysis, vous verrez :

1 2/3

2 2/3

3 2/3
