---
title: Sources de données des ID de transaction
description: Découvrez le processus général d’utilisation des sources de données des ID de transaction.
translation-type: ht
source-git-commit: c6f84f470dcf97f49ce7dc9d2c5dd8c65cc6cf67

---


# Sources de données des ID de transaction

Les sources de données des ID de transaction vous permettent non seulement d’afficher côte à côte des données en ligne et hors ligne, mais également de lier les données. Elles nécessitent l’utilisation de la variable [`transactionID`](/help/implement/vars/page-vars/transactionid.md) dans votre implémentation Analytics.

Lorsque vous envoyez un accès en ligne contenant une valeur `transactionID`, Adobe prend un « instantané » de toutes les variables définies ou qui persistent à ce moment-là. Si un ID de transaction correspondant transféré via les sources de données est trouvé, les données hors ligne et en ligne sont alors liées. Peu importe quelle source de données est affichée en premier.

## Processus global des sources de données des ID de transaction

Utilisez le processus générique suivant pour commencer à utiliser des sources de données d’ID de transaction :

1. Créez une source de données (Catégorie « générique » et « Source de données générique (ID de transaction) »).
1. Suivez l’assistant de configuration du flux de données pour obtenir un emplacement FTP afin de transférer des données et télécharger un fichier de modèle de sources de données.
1. Mettez à jour votre implémentation pour inclure la variable `transactionID`.
1. Transférez un fichier de sources de données sur le site FTP avec un fichier `.fin`.

## Exemple de fichier de transfert et de code d’implémentation

Si vous avez transféré le fichier de sources de données suivant et implémenté le code suivant sur votre site, les données sont liées dans les rapports. Le fichier de sources de données utilise eVar1 et event1, tandis que l’implémentation en ligne utilise eVar2 et event2. Comme l’ID de transaction correspond, vous pouvez voir les données event2 pour eVar1 et les données event1 pour eVar2.

### Exemple de fichier

Téléchargez le modèle, mettez à jour les valeurs, puis transférez-le vers l’emplacement FTP des sources de données :

| `#` | `Example eVar1 name` | `Example event 1 name` | `1` |
|---|---|---|---|
| `Date` | `Evar 1` | `Event 1` | `transactionID` |
| `01/01/2020/12/00/00` | `Example eVar1 value` | `1` | `1234` |

### Exemple de code d’implémentation

Pour une explication plus détaillée sur l’ID de transaction, voir [`transactionID`](/help/implement/vars/page-vars/transactionid.md) dans le guide de mise en œuvre.

```js
var s = s_gi("examplersid");
s.eVar2 = "Example eVar2 value";
s.events = "event2";
s.transactionID = "1234";
s.t();
```
