---
description: 'null'
title: Exemple d’étiquetage
uuid: a9a5b937-dbde-4f0f-a171-005ef4c79df9
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Exemple d’étiquetage

## Exemple de données d’accès

Supposons que vous disposiez des données d’accès suivantes :

* La première ligne contient les libellés de chaque variable.
* La deuxième ligne est le nom de la variable. S’il possède un libellé d’ID, il contient le  de  assigné entre parenthèses.
* de données d’accès dans la troisième ligne.

| Étiquettes | I2<br>ID-PERSON<br>DEL-PERSON<br>ACC-PERSON | I2<br>ID-DEVICE<br>DEL-DEVICE<br>ACC-ALL | I2<br>DEL-PERSON<br>ACC-PERSON | I2<br>DEL-DEVICE<br>DEL-PERSON<br>ACC-ALL | I2<br>ID-DEVICE<br>DEL-DEVICE<br>ACC-ALL |
|---|---|---|---|---|---|
| **Nom de variable **<br>**(espace de noms)** | **MyProp1 **<br>**(utilisateur)** | **Identifiant visiteur **<br>**(AAID)** | **MyEvar1** | **MyEvar2** | **MyEvar3 **<br>**(xyz)** |
| Données d’accès | Marie | 77 | A  | L | X |
|  | Marie | 88 | B | N | Y |
|  | Marie | 99 | C  | O | Z |
|  | John | 77 | D | P | Me |
|  | John | 88 | E | N | U |
|  | John | 44 | Ve | Q | V |
|  | John | 55 | G | R | X |
|  | Alice | 66 | A  | N | Z |

## Exemple de demande d’accès

Si j&#39;envoie une demande d&#39;accès, le fichier récapitulatif contiendra les valeurs indiquées dans le tableau ci-dessous. Une requête ne peut renvoyer qu’un fichier de périphérique, qu’un fichier de personne ou l’un des deux. Deux fichiers de résumé ne sont renvoyés que si un ID de personne est utilisé et que la variable expandedIds est vraie.

| Valeurs API | Valeurs API | Type de fichier renvoyé | Données du <br>fichier d’accès récapitulatif | Données du <br>fichier d’accès récapitulatif | Données du <br>fichier d’accès récapitulatif | Données du <br>fichier d’accès récapitulatif | Données du <br>fichier d’accès récapitulatif |
|--- |--- |--- |---|---|---|---|---|
| **Espace de noms/ID** | **expandIDs** |  | **MyProp1** | **Identifiant visiteur** | **MyEvar1** | **MyEvar2** | **MyEvar3** |
| AAID=77 | false | périphérique | Variable absente | 77 | Variable absente | M, P | X, W |
| AAID=77 | true | périphérique | Variable absente | 77 | Variable absente | M, P | X, W |
| user=Mary | false | personne | Marie | 77, 88, 99 | A, B, C | M, N, O | X, Y, Z |
| user=Mary | true | personne | Marie | 77, 88, 99 | A, B, C | M, N, O | X, Y, Z |
| user=Mary | true | périphérique | non présent | 77, 88 | non présent | N, P | U, W |
| user=Mary  AAID=66 | true | personne | Marie | 77, 88, 99 | A, B, C | M, N, O | X, Y, Z |
| user=Mary  AAID=66 | true | périphérique | non présent | 66, 77, 88 | non présent | N, P | U, W, Z |
| xyz=X | false | périphérique | non présent | 55, 77 | non présent | M, R | X |
| xyz=X | true | périphérique | non présent | 55, 77 | non présent | M, P, R | W, X |

Notez que le paramètre pour expandedIDs n’a aucune incidence sur la sortie lorsqu’un ID de cookie est utilisé.

## Exemple de demande de suppression

Avec une requête de suppression utilisant les valeurs de l’API dans la première ligne du tableau, le tableau des accès sera mis à jour pour ressembler à ceci :

| AAID=77 expandIDs value<br>does not matter | AAID=77 expandIDs value<br>does not matter | AAID=77 expandIDs value<br>does not matter | AAID=77 expandIDs value<br>does not matter | AAID=77 expandIDs value<br>does not matter |
|---|---|---|---|---|
| **MyProp1** | **AAID** | **MyEvar1** | **MyEvar2** | **MyEvar3** |
| Marie | 42 | A  | Privacy-7398 | Privacy-9152 |
| Marie | 88 | B | N | Y |
| Marie | 99 | C  | O | Z |
| John | 42 | D | Privacy-1866 | Privacy-8216 |
| John | 88 | E | N | U |
| John | 44 | Ve | Q | V |
| John | 55 | G | R | X |
| Alice | 66 | A  | N | Me |

>[!NOTE] Seules les cellules des lignes contenant AAID = 77 et une étiquette DEL-DEVICE sont impactées.

| user=Mary<br>expandIDs=false | user=Mary<br>expandIDs=false | user=Mary<br>expandIDs=false | user=Mary<br>expandIDs=false | user=Mary<br>expandIDs=false |
|--- |---|---|---|---|
| **MyProp1** | **AAID** | **MyEvar1** | **MyEvar2** | **MyEvar3** |
| Privacy-0523 | 77 | Privacy-1866 | Privacy-3681 | X |
| Privacy-0523 | 88 | Privacy-2178 | Privacy-1975 | Y |
| Privacy-0523 | 99 | Privacy-9045 | Privacy-2864 | Z |
| John | 77 | D | P | Me |
| John | 88 | E | N | U |
| John | 44 | Ve | Q | V |
| John | 55 | G | R | X |
| Alice | 66 | A  | N | Me |

>[!NOTE] Seules les cellules des lignes contenant user=Mary et une étiquette DEL-PERSON sont impactées. Dans la pratique, la variable contenant A_ID serait probablement une prop ou une eVar, et sa valeur de remplacement serait une chaîne commençant par « Privacy- » suivi d’un numéro aléatoire (GUID), plutôt que de remplacer la valeur numérique par une valeur numérique aléatoire différente.

| user=Mary<br>expandIDs=true | user=Mary<br>expandIDs=true | user=Mary<br>expandIDs=true | user=Mary<br>expandIDs=true | user=Mary<br>expandIDs=true |
|--- |---|---|---|---|
| **MyProp1** | **AAID** | **MyEvar1** | **MyEvar2** | **MyEvar3** |
| Privacy-5782 | 09 | Privacy-0859 | Privacy-8183 | Privacy-9152 |
| Privacy-5782 | 16 | Privacy-6104 | Privacy-2911 | Privacy-6821 |
| Privacy-5782 | 83 | Privacy-2714 | Privacy-0219 | Privacy-4395 |
| John | 09 | D | Privacy-8454 | Privacy-8216 |
| John | 16 | E | Privacy-2911 | Privacy-2930 |
| John | 44 | Ve | Q | V |
| John | 55 | G | R | X |
| Alice | 66 | A  | N | Me |

Prenez note des points suivants :

* Les cellules des lignes contenant `user=Mary` et une étiquette `DEL-DEVICE` ou `DEL-PERSON` sont impactées, ainsi que les cellules comportant une étiquette `DEL-DEVICE` des lignes contenant un identifiant visiteur présent dans une ligne contenant `user=Mary`.
* `MyEvar2` est mis à jour dans les quatrième et cinquième lignes, car celles-ci contiennent les mêmes valeurs d’identifiant visiteur que les première et deuxième lignes. Dès lors, l’extension d’ID les inclut pour les suppressions de niveau appareil.
* Les valeurs de `MyEvar2` des deuxième et cinquième lignes correspondent avant et après la suppression. En revanche, après la suppression, la valeur N présente dans la dernière ligne ne correspond plus, car cette dernière n’a pas été mise à jour suite à la demande de suppression.
* `MyEvar3` se comporte très différemment avec l’extension d’ID, car sans extension d’ID, aucun `ID-DEVICES` ne correspondait. Désormais, `AAID` correspond dans les cinq premières lignes.
