---
title: Sources de données d’ID de transaction
description: Découvrez le processus général d’utilisation des sources de données d’ID de transaction.
translation-type: tm+mt
source-git-commit: c6f84f470dcf97f49ce7dc9d2c5dd8c65cc6cf67

---


# Sources de données d’ID de transaction

Les sources de données d’ID de transaction vous permettent non seulement de côte à côte des données en ligne et hors ligne, mais également de lier les données ensemble. Elle nécessite l’utilisation de la [`transactionID`](/help/implement/vars/page-vars/transactionid.md) variable dans votre implémentation Analytics.

Lorsque vous envoyez un accès en ligne contenant une `transactionID` valeur, Adobe prend un &quot;instantané&quot; de toutes les variables définies ou conservées à ce moment-là. Si un ID de transaction correspondant transféré via la fonctionnalité Sources de données est trouvé, les données hors ligne et en ligne sont liées. Peu importe quelle source de données est vue en premier.

## Flux global de travaux des sources de données d’ID de transaction

Utilisez le flux de travail générique suivant pour  à l’aide des sources de données d’ID de transaction :

1. Créez une source de données (type de &quot;générique&quot; et &quot;source de données générique (ID de transaction)&quot;).
1. Suivez l’assistant de configuration du flux de données pour obtenir un emplacement FTP pour télécharger des données et un fichier de modèle de sources de données.
1. Mettez à jour votre implémentation pour inclure la `transactionID` variable.
1. Téléchargez un fichier de sources de données sur le site FTP avec un `.fin` fichier.

## Exemple de fichier de transfert et de code d’implémentation

Si vous avez téléchargé le fichier de sources de données suivant et mis en oeuvre le code suivant sur votre site, les données sont liées dans les  du. Le fichier de sources de données utilise eVar1 et le1, tandis que l’implémentation en ligne utilise eVar2 et le 2. Puisque l’ID de transaction correspond, vous pouvez voir les données 2 pour eVar1 et les données1 pour eVar2.

### Exemple de fichier

Téléchargez le modèle, mettez à jour les valeurs, puis téléchargez-le vers l’emplacement FTP des sources de données :

| `#` | `Example eVar1 name` | `Example event 1 name` | `1` |
|---|---|---|---|
| `Date` | `Evar 1` | `Event 1` | `transactionID` |
| `01/01/2020/12/00/00` | `Example eVar1 value` | `1` | `1234` |

### Exemple de code de mise en oeuvre

Pour une explication plus détaillée sur l’ID de transaction, voir [`transactionID`](/help/implement/vars/page-vars/transactionid.md) Dans le guide de l’utilisateur Mise en oeuvre.

```js
var s = s_gi("examplersid");
s.eVar2 = "Example eVar2 value";
s.events = "event2";
s.transactionID = "1234";
s.t();
```
