---
description: valeur nulle
seo-description: valeur nulle
seo-title: Exemple d’étiquetage
title: Exemple d’étiquetage
uuid: a 9 a 5 b 937-dbde -4 f 0 f-a 171-005 ef 4 c 79 df 9
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Exemple d’étiquetage

## Exemple de données d’accès {#section_94DE6BC0026F46D7AD7061C5625C8D52}

Supposons que vous avez les données d’accès suivantes :

* La première ligne contient les étiquettes pour chaque variable.
* La deuxième ligne correspond au nom de la variable. Si elle comporte une étiquette d’identification, elle contient l’espace de noms attribué entre parenthèses.
* Les données d’accès commencent à partir de la troisième ligne.

<!-- Meike, I converted html tables for fix elusive validation error. Bob -->

| Étiquettes | I2<br>ID-PERSONDEL<br>-PERSONACC<br>-PERSONNE | I2<br>ID-DEVICE<br>DEL-DEVICE<br>ACC-ALL | I2<br>DEL-PERSON<br>ACC-PERSON | I2<br>DEL-DEVICE<br>DEL-PERSON<br>ACC-ALL | I2<br>ID-DEVICE<br>DEL-DEVICE<br>ACC-ALL |
|:---:|:---:|:---:|:---:|:---:|:---:|
| Variable Name<br>(Namespace) | MyProp1<br>(user) | Visitor ID<br>(AAID) | MyEvar1 | MyEvar2 | MyEvar3<br>(xyz) |
| Données d’accès | Mary | 77 | A | M | X |
| Mary | 88 | B | N | Y |
| Mary | 99 | C | O | Z |
| John | 77 | D | P | W |
| John | 88 | E | N | U |
| John | 44 | F | Q | V |
| John | 55 | G | R | X |
| Alice | 66 | A | N | Z |


## Exemple de demande d’accès {#section_BDA817FD2415420DAAC835825484BA9D}

Si je soumets une demande d’accès, le fichier récapitulatif contiendra les valeurs indiquées dans le tableau ci-dessous. Une demande peut renvoyer un fichier d’appareil, un fichier de personne ou les deux. Deux fichiers récapitulatifs sont renvoyés uniquement si un ID de personne est utilisé et que « expandIDs » a la valeur « true ».

| Valeurs de l’API | Type de fichier renvoyé | Données du fichier d’accès récapitulatif |
|--- |--- |--- |
| Espace de noms/ID | expandIDs |  | MyProp1 | Visitor ID | MyEvar1 | MyEvar2 | MyEvar3 |
| AAID=77 | false | périphérique | Variable non présente | 77 | Variable non présente | M, P | X, W |
| AAID=77 | true | périphérique | 77 | M, P | X, W |
| user=Mary | false | Personne | Mary | 77, 88, 99 | A, B, C | M, N, O | X, Y, Z |
| user=Mary | true | Personne | Mary | 77, 88, 99 | A, B, C | M, N, O | X, Y, Z |
| périphérique | non présente | 77, 88 | non présente | N, P | U, W |
| user=Mary AAID=66 | true | Personne | Mary | 77, 88, 99 | A, B, C | M, N, O | X, Y, Z |
| périphérique | non présente | 66, 77, 88 | non présente | N, P | U, W, Z |
| xyz=X | false | périphérique | non présente | 55, 77 | non présente | M, R | X |
| xyz=X | true | périphérique | non présente | 55, 77 | non présente | M, P, R | W, X |

Notez que le paramètre des expandIDs n’influence pas le résultat lorsqu’un ID de cookie est utilisé.

## Exemple de demande de suppression {#section_6C75F70F5D574BE7AA540981E8B7EA26}

Avec une demande de suppression qui utilise les valeurs de l’API de la première ligne du tableau, le tableau d’accès sera mis à jour comme suit :

| AAID = 77 La valeur expandids n'a pas d'importance |
|--- |
| MyProp1 | AAID | MyEvar1 | MyEvar2 | MyEvar3 |
| Mary | 42 | A | GDPR-7398 | GDPR-9152 |
| Mary | 88 | B | N | Y |
| Mary | 99 | C | O | Z |
| John | 42 | D | GDPR-1866 | GDPR-8216 |
| John | 88 | E | N | U |
| John | 44 | F | Q | V |
| John | 55 | G | R | X |
| Alice | 66 | A | N | W |

>[!NOTE]
>
>Seules les cellules des lignes contenant AAID = 77 et une étiquette DEL-DEVICE sont affectées.

| user = Mary expandids = false |
|--- |
| MyProp1 | AAID | MyEvar1 | MyEvar2 | MyEvar3 |
| GDPR-0523 | 77 | GDPR-1866 | GDPR-3681 | X |
| GDPR-0523 | 88 | GDPR-2178 | GDPR-1975 | Y |
| GDPR-0523 | 99 | GDPR-9045 | GDPR-2864 | Z |
| John | 77 | D | P | W |
| John | 88 | E | N | U |
| John | 44 | F | Q | V |
| John | 55 | G | R | X |
| Alice | 66 | A | N | W |

>[!NOTE]
>
>Seules les cellules sur les lignes contenant un libellé user = Mary et un libellé DEL-PERSON sont affectées. Dans la pratique, la variable contenant A_ID serait probablement une prop ou une eVar, et sa valeur de remplacement serait une chaîne commençant par « GDPR- » suivi d’un numéro aléatoire (GUID), plutôt que de remplacer la valeur numérique par une valeur numérique aléatoire différente.

| user=Mary expandIDs=true |
|--- |
| MyProp1 | AAID | MyEvar1 | MyEvar2 | MyEvar3 |
| GDPR-5782 | 09 | GDPR-0859 | GDPR-8183 | GDPR-9152 |
| GDPR-5782 | 16 | GDPR-6104 | GDPR-2911 | GDPR-6821 |
| GDPR-5782 | 83 | GDPR-2714 | GDPR-0219 | GDPR-4395 |
| John | 09 | D | GDPR-8454 | GDPR-8216 |
| John | 16 | E | GDPR-2911 | GDPR-2930 |
| John | 44 | F | Q | V |
| John | 55 | G | R | X |
| Alice | 66 | A | N | W |

Tenez compte des points suivants :

* Les cellules des lignes contenant user=Mary et une étiquette DEL-DEVICE ou DEL-PERSON sont impactées, ainsi que les cellules comportant une étiquette DEL-DEVICE des lignes contenant un identifiant visiteur présent dans une ligne contenant user=Mary.
* MyEvar2 est mis à jour dans les quatrième et cinquième lignes, car celles-ci contiennent les mêmes valeurs d’identifiant visiteur que les première et deuxième lignes. Dès lors, l’extension d’ID les inclut pour les suppressions de niveau appareil.
* Les valeurs de MyEvar2 des deuxième et cinquième lignes correspondent avant et après la suppression. En revanche, après la suppression, la valeur N présente dans la dernière ligne ne correspond plus, car cette dernière n’a pas été mise à jour suite à la demande de suppression.
* MyEvar3 se comporte très différemment avec l’extension d’ID, car sans extension d’ID, aucun ID-DEVICES ne correspondait. Désormais, AAID correspond dans les cinq premières lignes.
