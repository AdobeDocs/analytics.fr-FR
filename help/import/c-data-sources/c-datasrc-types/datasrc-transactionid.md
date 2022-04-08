---
title: Sources de données des ID de transaction
description: Découvrez le processus général d’utilisation des sources de données des ID de transaction.
feature: Data Sources
exl-id: 5f26b15c-8d9c-46d5-860f-13fdfa21af2e
source-git-commit: 79294cfc6f86e5a41a39504099cd730f53668725
workflow-type: ht
source-wordcount: '531'
ht-degree: 100%

---

# Sources de données des ID de transaction

Les sources de données des ID de transaction vous permettent non seulement d’afficher côte à côte des données en ligne et hors ligne, mais également de lier les données. Elles nécessitent l’utilisation de la variable [`transactionID`](/help/implement/vars/page-vars/transactionid.md) dans votre implémentation Analytics.

Lorsque vous envoyez un accès en ligne contenant une valeur `transactionID`, Adobe prend un « instantané » de toutes les variables définies ou qui persistent à ce moment-là. Si un ID de transaction correspondant transféré via les sources de données est trouvé, les données hors ligne et en ligne sont alors liées.

Pour utiliser les transactions, l’accès en ligne avec un ID de transaction doit avoir été envoyé et traité avant l’envoi des données de la source de données de transaction avec cet ID de transaction. L’accès en ligne contient des variables (eVars, etc.), mais pas d’événements, qui se trouvaient sur l’accès en ligne enregistré avec les informations d’ID de transaction.

Lorsqu’un accès à la source de données de transaction est envoyé, l’ID de transaction sur l’accès à la transaction de la source de données recherche les variables, etc. (et non les événements) qui étaient associés à l’accès en ligne d’origine avec cet ID de transaction. Il utilise ces variables sur l’accès à la transaction de la source de données, s’il n’y avait aucune valeur pour une variable transmise sur l’accès à la transaction de la source de données.

## Exemple

Si un accès en ligne avec l’ID de transaction 1256 est transmis et placé dessus, `evar1=blue`, `evar2=water` et `event1` sont définies, puis les données de transaction pour l’ID de transaction 1256 sont enregistrées avec `evar1=blue`, `evar2=water`. Aucune valeur d’événement n’est enregistrée dans les informations de transaction.

Supposons maintenant qu’un accès à la transaction d’une source de données soit ensuite transmis par le système avec l’ID de transaction 1256 et `evar1=yellow`, `evar3=mountain` et `event2` définies. Le système trouve les données de transaction enregistrées et définit `evar2=water` dans l’accès à la transaction de la source de données (puisque c’est ce qui a été défini sur l’accès d’origine). Il ne le définit pas sur `evar1=blue` (comme c’était le cas lors de l’accès d’origine), car une valeur pour `evar1` (jaune) était déjà définie sur l’accès à la transaction de la source de données.  Ainsi, l’accès à la transaction de la source de données entraîne la présence de `evar1=yellow`, `evar2=water` (de l’accès en ligne d’origine) et `evar3=mountain`. `event2` est défini pour ces trois valeurs d’eVar : événement de l’accès à la transaction de la source de données.

Aucune valeur de l’accès à la transaction de la source de données n’obtient `event1` défini lors du traitement de l’accès à la transaction de la source de données.

## Processus global des sources de données des ID de transaction

Utilisez le processus générique suivant pour commencer à utiliser des sources de données d’ID de transaction :

1. Créez une source de données (Catégorie « générique » et « Source de données générique (ID de transaction) »).
1. Suivez l’assistant de configuration des sources de données pour obtenir un emplacement FTP afin de charger des données et de télécharger un fichier de modèle de sources de données.
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
