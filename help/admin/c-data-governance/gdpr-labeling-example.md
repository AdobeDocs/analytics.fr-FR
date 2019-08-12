---
description: valeur nulle
seo-description: valeur nulle
seo-title: Exemple d’étiquetage
title: Exemple d’étiquetage
uuid: a 9 a 5 b 937-dbde -4 f 0 f-a 171-005 ef 4 c 79 df 9
translation-type: tm+mt
source-git-commit: edafa9ca8dc34bd1f3af8c56b4f23c4a983aa677

---


# Exemple d’étiquetage

## Exemple de données d’accès

Supposons que vous avez les données d’accès suivantes :

* La première ligne contient les étiquettes pour chaque variable.
* La deuxième ligne correspond au nom de la variable. Si elle comporte une étiquette d’identification, elle contient l’espace de noms attribué entre parenthèses.
* Les données d’accès commencent à partir de la troisième ligne.

| Étiquettes | I2<br>ID-PERSONDEL<br>-PERSONACC<br>-PERSONNE | I 2<br>ID-DEVICEDEL<br>-DEVICEACC<br>-ALL | I 2<br>DEL-PERSONACC<br>-PERSONNE | I 2<br>DEL-DEVICEDEL<br>-PERSONACC<br>-ALL | I 2<br>ID-DEVICEDEL<br>-DEVICEACC<br>-ALL |
|---|---|---|---|---|---|
| **Nom de variable**<br>**(espace de nommage)** | **Myprop 1**<br>**(utilisateur)** | **Identifiant visiteur**<br>**(AAID)** | **MyEvar1** | **MyEvar2** | **MyEvar3**<br>**(xyz)** |
| Données d’accès | Mary | 77 | A | M | X |
|  | Mary | 88 | B | N | Y |
|  | Mary | 99 | C | O | Z |
|  | John | 77 | D | P | W |
|  | John | 88 | E | N | U |
|  | John | 44 | F | Q | V |
|  | John | 55 | G | R | X |
|  | Alice | 66 | A | N | Z |

## Exemple de demande d’accès

Si je soumets une demande d’accès, le fichier récapitulatif contiendra les valeurs indiquées dans le tableau ci-dessous. Une demande peut renvoyer un fichier d’appareil, un fichier de personne ou les deux. Deux fichiers récapitulatifs sont renvoyés uniquement si un ID de personne est utilisé et que « expandIDs » a la valeur « true ».

| Valeurs de l’API | Valeurs de l’API | Type de fichier renvoyé | Data in <br>Summary Access File | Data in <br>Summary Access File | Data in <br>Summary Access File | Data in <br>Summary Access File | Data in <br>Summary Access File |
|--- |--- |--- |---|---|---|---|---|
| **Espace de noms/ID** | **expandIDs** |  | **MyProp1** | **Identifiant visiteur** | **MyEvar1** | **MyEvar2** | **MyEvar3** |
| AAID=77 | false | périphérique | Variable non présente | 77 | Variable non présente | M, P | X, W |
| AAID=77 | true | périphérique | Variable non présente | 77 | Variable non présente | M, P | X, W |
| user=Mary | false | Personne | Mary | 77, 88, 99 | A, B, C | M, N, O | X, Y, Z |
| user=Mary | true | Personne | Mary | 77, 88, 99 | A, B, C | M, N, O | X, Y, Z |
| user=Mary | true | périphérique | non présente | 77, 88 | non présente | N, P | U, W |
| user=Mary AAID=66 | true | Personne | Mary | 77, 88, 99 | A, B, C | M, N, O | X, Y, Z |
| user=Mary AAID=66 | true | périphérique | non présente | 66, 77, 88 | non présente | N, P | U, W, Z |
| xyz=X | false | périphérique | non présente | 55, 77 | non présente | M, R | X |
| xyz=X | true | périphérique | non présente | 55, 77 | non présente | M, P, R | W, X |

Notez que le paramètre des expandIDs n’influence pas le résultat lorsqu’un ID de cookie est utilisé.

## Exemple de demande de suppression

Avec une demande de suppression qui utilise les valeurs de l’API de la première ligne du tableau, le tableau d’accès sera mis à jour comme suit :

| AAID=77 expandIDs value<br>does not matter | AAID=77 expandIDs value<br>does not matter | AAID=77 expandIDs value<br>does not matter | AAID=77 expandIDs value<br>does not matter | AAID=77 expandIDs value<br>does not matter |
|---|---|---|---|---|
| **MyProp1** | **AAID** | **MyEvar1** | **MyEvar2** | **MyEvar3** |
| Mary | 42 | A | GDPR-7398 | GDPR-9152 |
| Mary | 88 | B | N | Y |
| Mary | 99 | C | O | Z |
| John | 42 | D | GDPR-1866 | GDPR-8216 |
| John | 88 | E | N | U |
| John | 44 | F | Q | V |
| John | 55 | G | R | X |
| Alice | 66 | A | N | W |

>[!NOTE] Seules les cellules des lignes contenant AAID = 77 et une étiquette DEL-DEVICE sont affectées.

| user = maryexpandids<br>= false | user = maryexpandids<br>= false | user = maryexpandids<br>= false | user = maryexpandids<br>= false | user = maryexpandids<br>= false |
|--- |---|---|---|---|
| **MyProp1** | **AAID** | **MyEvar1** | **MyEvar2** | **MyEvar3** |
| GDPR-0523 | 77 | GDPR-1866 | GDPR-3681 | X |
| GDPR-0523 | 88 | GDPR-2178 | GDPR-1975 | Y |
| GDPR-0523 | 99 | GDPR-9045 | GDPR-2864 | Z |
| John | 77 | D | P | W |
| John | 88 | E | N | U |
| John | 44 | F | Q | V |
| John | 55 | G | R | X |
| Alice | 66 | A | N | W |

>[!NOTE] Seules les cellules sur les lignes contenant un libellé user = Mary et un libellé DEL-PERSON sont affectées. Dans la pratique, la variable contenant A_ID serait probablement une prop ou une eVar, et sa valeur de remplacement serait une chaîne commençant par « GDPR- » suivi d’un numéro aléatoire (GUID), plutôt que de remplacer la valeur numérique par une valeur numérique aléatoire différente.

| user=Mary<br>expandIDs=true | user = maryexpandids<br>= true | user = maryexpandids<br>= true | user = maryexpandids<br>= true | user = maryexpandids<br>= true |
|--- |---|---|---|---|
| **MyProp1** | **AAID** | **MyEvar1** | **MyEvar2** | **MyEvar3** |
| GDPR-5782 | 09 | GDPR-0859 | GDPR-8183 | GDPR-9152 |
| GDPR-5782 | 16 | GDPR-6104 | GDPR-2911 | GDPR-6821 |
| GDPR-5782 | 83 | GDPR-2714 | GDPR-0219 | GDPR-4395 |
| John | 09 | D | GDPR-8454 | GDPR-8216 |
| John | 16 | E | GDPR-2911 | GDPR-2930 |
| John | 44 | F | Q | V |
| John | 55 | G | R | X |
| Alice | 66 | A | N | W |

Tenez compte des points suivants :

* Cells on rows containing `user=Mary` and a `DEL-DEVICE` or `DEL-PERSON` label are impacted, as well as cells with a `DEL-DEVICE` label on rows containing any Visitor ID that occurred on a row containing `user=Mary`.
* `MyEvar2` est mis à jour dans les quatrième et cinquième lignes, car celles-ci contiennent les mêmes valeurs d’identifiant visiteur que les première et deuxième lignes. Dès lors, l’extension d’ID les inclut pour les suppressions de niveau appareil.
* The values of `MyEvar2` in rows two and five match both before and after the delete, but after the delete no longer matches the value N that occurs in the last row, because that row was not updated as part of the delete request.
* `MyEvar3` se comporte très différemment avec l’extension d’ID, car sans extension d’ID, aucun ne correspondait. `ID-DEVICES` Now `AAID` matches on the first five rows.
