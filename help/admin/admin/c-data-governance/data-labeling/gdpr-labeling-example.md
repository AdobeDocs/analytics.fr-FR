---
description: Présente des exemples sur la manière d’étiqueter les données relatives aux accès, aux demandes d’accès et aux demandes de suppression.
title: Exemples dʼétiquetage
feature: Data Governance
role: Admin
exl-id: 9bea8636-c79c-4998-8952-7c66d31226e3
source-git-commit: 429aaa43fdae669350bdb5a5a54a7d4b9b1c65f2
workflow-type: tm+mt
source-wordcount: '862'
ht-degree: 99%

---

# Exemples dʼétiquetage

## Exemple de données d’accès {#hit}

Supposons que vous avez les données d’accès suivantes :

* La première ligne contient les étiquettes pour chaque variable.
* La deuxième ligne correspond au nom de la variable. Si elle comporte une étiquette d’identification, elle contient l’espace de noms attribué entre parenthèses.
* Les données d’accès commencent à partir de la troisième ligne.

| Étiquettes | I2 <br> ID-PERSON <br> DEL-PERSON <br> ACC-PERSON | I2 <br> ID-DEVICE <br> DEL-DEVICE <br> ACC-ALL | I2 <br> DEL-PERSON <br> ACC-PERSON | I2 <br> DEL-DEVICE <br> DEL-PERSON <br> ACC-ALL | I2 <br> ID-DEVICE <br> DEL-DEVICE <br> ACC-ALL |
|---|---|---|---|---|---|
| **Nom de variable** <br> **(Espace de noms)** | **MyProp1** <br> **(utilisateur)** | **Identifiant visiteur** <br> **(AAID)** | **MyEvar1** | **MyEvar2** | **MyEvar3** <br> **(xyz)** |
| Données d’accès | Mary | 77 | A | M | X |
| | Mary | 88 | B | N | Y |
| | Mary | 99 | C | O | Z |
| | John | 77 | D | P | W |
| | John | 88 | E | N | U |
| | John | 44 | F | Q | V |
| | John | 55 | G | R | X |
| | Alice | 66 | A | N | Z |

## Exemple de requêtes d’accès {#access}

Si je soumets une demande dʼaccès, le fichier récapitulatif contient les valeurs indiquées dans le tableau ci-dessous. Une demande peut renvoyer un fichier d’appareil, un fichier de personne ou les deux. Deux fichiers récapitulatifs sont renvoyés uniquement si un ID de personne est utilisé et que « expandIDs » a la valeur « true ».

<table>
  <tr>
    <th colspan="2" style="text-align:center">Valeurs de l’API</th>
    <th rowspan="2"><br>Type de fichier renvoyé</th>
    <th colspan="5" style="text-align:center">Données du fichier d’accès récapitulatif</th>
  </tr>
  <tr>
    <th>Espace de noms/ID</th>
    <th>expandIDs</th>
    <th>MyProp1</th>
    <th>Identifiant visiteur</th>
    <th>MyEvar1</th>
    <th>MyEvar2</th>
    <th>MyEvar3 </th>
  </tr>
  <tr>
    <td>AAID=77</td>
    <td>false</td>
    <td>appareil</td>
    <td>non présente</td>
    <td>77</td>
    <td>non présente</td>
    <td>M, P</td>
    <td>X, W</td>
  </tr>
  <tr>
    <td>AAID=77</td>
    <td>true</td>
    <td>appareil</td>
    <td>non présente</td>
    <td>77</td>
    <td>non présente</td>
    <td>M, P</td>
    <td>X, W</td>
  </tr>
  <tr>
    <td>user=Mary</td>
    <td>false</td>
    <td>Personne</td>
    <td>Mary</td>
    <td>77, 88, 99</td>
    <td>A, B, C</td>
    <td>M, N, O</td>
    <td>X, Y, Z</td>
  </tr>
  <tr>
    <td rowspan="2">user=Mary</td>
    <td rowspan="2">true</td>
    <td>Personne</td>
    <td>Mary</td>
    <td>77, 88, 99</td>
    <td>A, B, C</td>
    <td>M, N, O</td>
    <td>X, Y, Z</td>
  </tr>
  <tr>
    <td>appareil</td>
    <td>non présente</td>
    <td>77, 88</td>
    <td>A, B, C</td>
    <td>N, P</td>
    <td>U, W</td>
  </tr>
  <tr>
    <td rowspan="2">user=Mary<br>AAID=66</td>
    <td rowspan="2">true</td>
    <td>Personne</td>
    <td>Mary</td>
    <td>77, 88, 99</td>
    <td>A, B, C</td>
    <td>M, N, O</td>
    <td>X, Y, Z</td>
  </tr>
  <tr>
    <td>appareil</td>
    <td>non présente</td>
    <td>66, 77, 88</td>
    <td>A, B, C</td>
    <td>N, P</td>
    <td>U, W, Z</td>
  </tr>
  <tr>
    <td>xyz=X</td>
    <td>false</td>
    <td>appareil</td>
    <td>non présente</td>
    <td>55, 77</td>
    <td>non présente</td>
    <td>M, R</td>
    <td>X</td>
  </tr>
  <tr>
    <td>xyz=X</td>
    <td>true</td>
    <td>appareil</td>
    <td>non présente</td>
    <td>55, 77</td>
    <td>non présente</td>
    <td>M, P, R</td>
    <td>W, X</td>
  </tr>
</table>

Notez que le paramètre des expandIDs n’influence pas le résultat lorsqu’un ID de cookie est utilisé.

## Exemples de requêtes de suppression {#delete}

Avec une demande de suppression qui utilise les valeurs de l’API de la première ligne du tableau, le tableau d’accès sera mis à jour comme suit :

<table>
  <tr>
    <th colspan="5" style="text-align:center">AAID=77 <br>(les valeurs des expandID nʼont pas dʼimportance)</th>
  </tr>
  <tr>
    <th>MyProp1</th>
    <th>AAID</th>
    <th>MyEvar1</th>
    <th>MyEvar2</th>
    <th>MyEvar3 </th>
  </tr>
  <tr>
    <td>Mary</td>
    <td>42</td>
    <td>A</td>
    <td>Privacy-7398</td>
    <td>Privacy-9152</td>
  </tr>
  <tr>
    <td>Mary</td>
    <td>88</td>
    <td>B</td>
    <td>N</td>
    <td>Y</td>
  </tr>
  <tr>
    <td>Mary</td>
    <td>99</td>
    <td>C</td>
    <td>O</td>
    <td>Z</td>
  </tr>
  <tr>
    <td>John</td>
    <td>42</td>
    <td>D</td>
    <td>Privacy-1866</td>
    <td>Privacy-8216</td>
  </tr>
  <tr>
    <td>John</td>
    <td>88</td>
    <td>E</td>
    <td>N</td>
    <td>U</td>
  </tr>
  <tr>
    <td>John</td>
    <td>44</td>
    <td>F</td>
    <td>Q</td>
    <td>V</td>
  </tr>
  <tr>
    <td>John</td>
    <td>55</td>
    <td>G</td>
    <td>R</td>
    <td>X</td>
  </tr>
  <tr>
    <td>Alice</td>
    <td>66</td>
    <td>A</td>
    <td>N</td>
    <td>Z</td>
  </tr>
</table>

>[!NOTE]
>
>Seules les cellules des lignes contenant AAID=77 et une étiquette DEL-DEVICE sont impactées.

<table>
  <tr>
    <th colspan="5" style="text-align:center">user=Mary <br> expandIDs=false</th>
  </tr>
  <tr>
    <th>MyProp1</th>
    <th>AAID</th>
    <th>MyEvar1</th>
    <th>MyEvar2</th>
    <th>MyEvar3 </th>
  </tr>
  <tr>
    <td>Privacy-0523</td>
    <td>77</td>
    <td>Privacy-1866</td>
    <td>Privacy-3681</td>
    <td>X</td>
  </tr>
  <tr>
    <td>Privacy-0523</td>
    <td>88</td>
    <td>Privacy-2178</td>
    <td>Privacy-1975</td>
    <td>Y</td>
  </tr>
  <tr>
    <td>Privacy-0523</td>
    <td>99</td>
    <td>Privacy-9045</td>
    <td>Privacy-2864</td>
    <td>Z</td>
  </tr>
  <tr>
    <td>John</td>
    <td>77</td>
    <td>D</td>
    <td>P</td>
    <td>W</td>
  </tr>
  <tr>
    <td>John</td>
    <td>88</td>
    <td>E</td>
    <td>N</td>
    <td>U</td>
  </tr>
  <tr>
    <td>John</td>
    <td>44</td>
    <td>F</td>
    <td>Q</td>
    <td>V</td>
  </tr>
  <tr>
    <td>John</td>
    <td>55</td>
    <td>G</td>
    <td>R</td>
    <td>X</td>
  </tr>
  <tr>
    <td>Alice</td>
    <td>66</td>
    <td>A</td>
    <td>N</td>
    <td>Z</td>
  </tr>
</table>

>[!NOTE]
>
>Seules les cellules des lignes contenant user=Mary et une étiquette DEL-PERSON sont impactées. De plus, dans la pratique, la variable contenant A_ID serait probablement une prop ou une eVar. Sa valeur de remplacement serait une chaîne commençant par « Privacy- » suivi dʼun numéro aléatoire (GUID), plutôt que de remplacer la valeur numérique par une valeur numérique aléatoire différente.

<table>
  <tr>
    <th colspan="5" style="text-align:center">user=Mary <br> expandIDs=true</th>
  </tr>
  <tr>
    <th>MyProp1</th>
    <th>AAID</th>
    <th>MyEvar1</th>
    <th>MyEvar2</th>
    <th>MyEvar3 </th>
  </tr>
  <tr>
    <td>Privacy-5782</td>
    <td>09</td>
    <td>Privacy-0859</td>
    <td>Privacy-8183</td>
    <td>Privacy-9152</td>
  </tr>
  <tr>
    <td>Privacy-5782</td>
    <td>16</td>
    <td>Privacy-6104</td>
    <td>Privacy-2911</td>
    <td>Privacy-6821</td>
  </tr>
  <tr>
    <td>Privacy-5782</td>
    <td>83</td>
    <td>Privacy-2714</td>
    <td>Privacy-0219</td>
    <td>Privacy-4395</td>
  </tr>
  <tr>
    <td>John</td>
    <td>09</td>
    <td>D</td>
    <td>Privacy-8454</td>
    <td>Privacy-8216</td>
  </tr>
  <tr>
    <td>John</td>
    <td>16</td>
    <td>E</td>
    <td>Privacy-2911</td>
    <td>Privacy-2930</td>
  </tr>
  <tr>
    <td>John</td>
    <td>44</td>
    <td>F</td>
    <td>Q</td>
    <td>V</td>
  </tr>
  <tr>
    <td>John</td>
    <td>55</td>
    <td>G</td>
    <td>R</td>
    <td>X</td>
  </tr>
  <tr>
    <td>Alice</td>
    <td>66</td>
    <td>A</td>
    <td>N</td>
    <td>Z</td>
  </tr>
</table>

Prenez note des points suivants :

* Les cellules des lignes contenant `user=Mary` et une étiquette `DEL-PERSON` sont impactées.
* En raison de l’extension d’ID, les cellules des lignes contenant `AAID=77`, `AAID=88` ou `AAID=99` (qui sont les valeurs AAID des lignes contenant `user=Mary`) et une étiquette `DEL-DEVICE` sont impactées. Cela inclut les cellules avec un libellé `DEL-DEVICE` sur les lignes contenant `user=Mary`. En conséquence, les cellules des lignes 4 et 5 (ainsi que des lignes 1 à 3) avec les libellés `DEL-DEVICE` (AAID, MyEvar2 et MyEvar3) sont obfusquées.
* Le paramètre pour les expandID ne sʼétend pas à lʼappel pour inclure les valeurs présentes dans MyEvar3 (`X`, `Y` et `Z`), qui possède un libellé ID-DEVICE, en cas de `user=Mary`. Les expandID ne sʼétendent que pour inclure les identifiants visiteur (AAID dans cet exemple, mais également lʼECID) sur les lignes contenant `user=Mary`. Ainsi, les deux dernières lignes, dont les valeurs de MyEvar3 sont `X` et `Z`, ne sont pas impactées.
* Les valeurs d’`MyEvar2` sont mises à jour dans les lignes 4 et 5, car elles contiennent les mêmes valeurs dʼidentifiant visiteur (`77` et `88`) que les lignes 1 et 2. Par conséquent, lʼextension dʼID les inclut pour les suppressions de niveau appareil.
* Les valeurs de `MyEvar2` des deuxième et cinquième lignes correspondent avant et après la suppression. En revanche, après la suppression, elles ne correspondent plus à la valeur `N` présente dans la dernière ligne, car cette dernière nʼa pas été mise à jour suite à la demande de suppression.
* `MyEvar3` se comporte très différemment avec l’extension d’ID, car sans extension d’ID, aucun `ID-DEVICES` ne correspondait. Désormais, `AAID` correspond dans les cinq premières lignes.
