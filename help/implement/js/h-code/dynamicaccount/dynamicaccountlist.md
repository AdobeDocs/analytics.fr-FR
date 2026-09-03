---
title: dynamicAccountList
description: Permet de définir une logique sur la manière dont votre mise en œuvre détermine sa suite de rapports.
feature: Implementation Basics
exl-id: ccff24a1-4b9a-4f62-adb5-09ab60e9b93e
role: Developer
TQID: https://experienceleague.adobe.com/qqkQoYsBWdTDOIkNfregm4k11CoDEl3dOJ3HNCMIo3s
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 157cc2bde1047063014aff39319d5cfaa1de9b5c
workflow-type: tm+mt
source-wordcount: 268
ht-degree: 89%

---

# s.dynamicAccountList

>[!IMPORTANT]
>
>Les comptes dynamiques sont uniquement pris en charge à l’aide des mises en œuvre JavaScript héritées (code H). Ces variables ne sont actuellement pas prises en charge dans les bibliothèques AppMeasurement ou la collecte de données Adobe Experience Platform.

La variable `s.dynamicAccountList` détermine dynamiquement la valeur de `s_account`. Si `dynamicAccountSelection` est défini sur `true`, la variable `dynamicAccountMatch` est comparée à `dynamicAccountList`. Si une correspondance est trouvée, l’identifiant de suite de rapports correspondant est utilisé.

## Syntaxe

Cette variable est une chaîne automatiquement analysée par le fichier JavaScript.

```JavaScript
s.dynamicAccountList = "[rsid]=[valuetomatch],[rsid2]=[valuetomatch]";
```

Une entrée valide est une liste de paires rsid et valeur séparées par des points-virgules. Chaque liste contient les éléments suivants :

* Un ou plusieurs identifiants de suite de rapports (séparés par des virgules)
* Un signe égal
* Une ou plusieurs chaînes à faire correspondre (séparées par des virgules)

La chaîne accepte uniquement les caractères ASCII standard. N’incluez pas d’espaces.

## Exemples

Pour tous les exemples suivants, l’URL de la page est `https://example.com/path2/?prod_id=12345`, la variable `dynamicAccountSelection` est définie sur `true` et la variable `s_account` sur `examplersid`.

```js
// In this example, the report suite that receives data is examplersid1.
s.dynamicAccountMatch = "window.location.hostname";
s.dynamicAccountList = "examplersid2=www2.example.com;examplersid1=example.com";

// In this example, the report suite that receives data is examplersid2.
s.dynamicAccountMatch = "window.location.pathname";
s.dynamicAccountList = "examplersid2=path2;examplersid3=path3";

// In this example, no rules match so it resorts to the default rsid in s_account, examplersid.
s.dynamicAccountMatch = "window.location.pathname";
s.dynamicAccountList = "examplersid4=path4;examplersid5=path5";
```

## Pièges, questions et conseils

* Les règles répertoriées dans cette variable sont appliquées de gauche à droite. Si la variable `dynamicAccountMatch` correspond à plusieurs règles, celle qui est située le plus à gauche est utilisée pour déterminer la suite de rapports. Par conséquent, déplacez vos règles plus génériques vers la droite de la liste.
* Si aucune correspondance n’est trouvée, la suite de rapports par défaut dans `s_account` est utilisée.
* Si votre page est enregistrée sur le disque dur d’un utilisateur ou traduite au moyen d’un moteur de traduction web (c’est le cas des pages traduites par Google, par exemple), il y a de fortes chances que la sélection de comptes dynamique ne fonctionne pas.
* Les règles `dynamicAccountSelection` s’appliquent uniquement à la section de l’URL spécifiée dans `dynamicAccountMatch`.
* Utilisez le débogueur Adobe CX Enterprise pour tester la suite de rapports de destination.
