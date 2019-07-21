---
description: Informations relatives aux caractères spéciaux utilisés dans le flux de données.
keywords: Flux de données ; tâche ; caractères spéciaux ; hit_ data ; variables à plusieurs valeurs ; events_ list ; products_ list ; mvvars
seo-description: Informations relatives aux caractères spéciaux utilisés dans le flux de données.
seo-title: Caractères spéciaux
solution: Analytics
subtopic: flux de données
title: Caractères spéciaux
topic: Reports and Analytics
uuid: 5 efe 019 b -39 e 6-4226-a 936-88202 a 02 f 5 e 6
translation-type: tm+mt
source-git-commit: 01a6fc7e44dc71b868bd38a4f6a5a4089eae6349

---


# Caractères spéciaux

Informations relatives aux caractères spéciaux utilisés dans le flux de données.

* [Caractères spéciaux dans le fichier hit_data](../../../export/analytics-data-feed/c-df-contents/datafeeds-spec-chars.md#section_9759C7A6AE684EB5B4A154FB6A26B39E)
* [Caractères spéciaux dans des variables à plusieurs valeurs (events_list, products_list, mvvars)](../../../export/analytics-data-feed/c-df-contents/datafeeds-spec-chars.md#section_056F8D540FFC4F24A001DC74331C2AAC)
* [Exemple de processus](../../../export/analytics-data-feed/c-df-contents/datafeeds-spec-chars.md#section_97F8C2925A35433DA2E7E8BE60037E37)

## Caractères spéciaux dans le fichier hit_data {#section_9759C7A6AE684EB5B4A154FB6A26B39E}

Les caractères suivants revêtent une signification particulière dans le fichier hit_data :

| Caractère | Signification | Description |
|--- |--- |--- |
| \t (caractère de tabulation) | Fin de colonne | Marque la fin d’un champ de données. |
| \n (caractère de nouvelle ligne) | Fin de ligne | Marque la fin d’une ligne de données. |
| \  (barre oblique inverse) | Caractère d’échappement | Annule une tabulation, une nouvelle ligne et une barre oblique inverse lorsque le caractère faisait partie de la valeur envoyée au cours de la collecte de données. |

Lorsque l’un des caractères spéciaux est précédé d’une barre oblique inverse, il représente un caractère littéral.

| Caractère | Signification | Description |
|--- |--- |--- |
| \\t | Tabulation | Caractère de tabulation littéral. Ce caractère faisait partie de la valeur envoyée au cours de la collecte de données. |
| \\n | Nouvelle ligne | Nouvelle ligne littérale. Ce caractère faisait partie de la valeur envoyée au cours de la collecte de données. |
| \\ | Barre oblique inverse | Caractère « barre oblique inverse » littéral. Ce caractère faisait partie de la valeur envoyée au cours de la collecte de données. |

## Caractères spéciaux dans des variables à plusieurs valeurs (events_list, products_list, mvvars) {#section_056F8D540FFC4F24A001DC74331C2AAC}

Les caractères suivants revêtent une signification particulière dans des variables à plusieurs valeurs :

<table id="table_FDA13DE05A784ED4972C2955BD2642C7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Caractère </th> 
   <th colname="col02" class="entry"> Signification </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <code> , </code> (virgule) </td> 
   <td colname="col02"> Fin de valeur </td> 
   <td colname="col2"> <p>Sépare des chaînes de produits, des identifiants d’événements ou d’autres valeurs dans des variables qui en comportent plusieurs. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> ; </code> (point-virgule) </td> 
   <td colname="col02"> Fin de sous-valeur à l’intérieur d’une valeur de produit </td> 
   <td colname="col2"> <p>Sépare les valeurs associées à un produit donné dans la liste <code>product_list </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> = </code> (caractère égal) </td> 
   <td colname="col02"> Attribution de valeur </td> 
   <td colname="col2"> <p>Attribue une valeur à un événement de la liste <code>event_list </code>. </p> </td> 
  </tr> 
 </tbody> 
</table>

Lorsque l’un des caractères spéciaux est précédé d’un accent circonflexe, il représente un caractère littéral.

| Caractère | Signification | Description |
|--- |--- |--- |
| ^, | Virgule | Caractère « virgule » littéral. Ce caractère faisait partie de la valeur envoyée au cours de la collecte de données. |
| ^; | Point-virgule | Caractère « point-virgule » littéral. Ce caractère faisait partie de la valeur envoyée au cours de la collecte de données. |
| ^= | Est égal à | Caractère « égal » littéral. Ce caractère faisait partie de la valeur envoyée au cours de la collecte de données. |
| ^^ | Accent circonflexe | Caractère « accent circonflexe » littéral. Ce caractère faisait partie de la valeur envoyée au cours de la collecte de données. |

## Exemple de processus {#section_97F8C2925A35433DA2E7E8BE60037E37}

Si certaines des colonnes de votre flux de données contiennent des données envoyées par l’utilisateur, il est conseillé de rechercher des caractères spéciaux avant de séparer les données par colonne ou par ligne à l’aide de `split`, `readLine` ou d’une fonction similaire.

Tenez compte des données suivantes :

| Largeur du navigateur | Hauteur du navigateur | eVar1 | prop1 |
|---|---|---|---|
| 1680 | 1050 | search\nstring | en |
| 800 | 600 | search\tstring | en |

Au cours de l’exportation, les caractères « nouvelle ligne » et « tabulation » des valeurs eVar1 font l’objet d’une séquence d’espacement. Le flux de données de ces lignes se présente comme suit :

```
1680\t1050\tsearch\\nstring\ten\n 
800\t600\tsearch\\tstring\ten\n
```

Calling `readLine()` on the first row returns the following partial string:

```
800\t600\tsearch\
```

Calling `split("\t")` on the second row returns the following string array:

```
800 
600 
search\ 
string 
en
```

Pour éviter cela, utilisez une solution semblable à ceci :

1. En commençant au début du fichier, effectuez la lecture jusqu’à ce que vous localisiez un caractère « tabulation », « nouvelle ligne », « barre oblique inverse » ou « accent circonflexe ».
1. Effectuez une action en fonction du caractère spécial trouvé :

   * Tabulation : insérez la chaîne jusqu’à ce point dans une cellule de stockage de données et continuez.
   * Nouvelle ligne : terminez la ligne de stockage de données.
   * Barre oblique inverse : lisez le caractère suivant, insérez le littéral de chaîne approprié, puis continuez.
   * Accent circonflexe : lisez le caractère suivant, insérez le littéral de chaîne approprié, puis continuez.

