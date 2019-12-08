---
description: AppMeasurement pour JavaScript est une nouvelle bibliothèque qui fournit les mêmes fonctionnalités de base que le fichier s_code.js ; elle est toutefois plus légère et plus rapide sur les sites pour mobiles comme sur les sites pour Bureau.
keywords: appmeasurement;Analytics Implementation;javascript;appmeasurement for javascript;initialization;retrieve appmeasurement instance;clear vars;clearvars;appmeasurement utilities;appmeasurement instance;appmeasurement benefits
subtopic: JavaScript AppMeasurement
title: AppMeasurement pour JavaScript
topic: Developer and implementation
uuid: dc71ad7a-92bd-40cd-8fab-707f6f8472e2
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# AppMeasurement pour JavaScript

[!DNL AppMeasurement] pour JavaScript est une nouvelle bibliothèque qui fournit les mêmes fonctionnalités de base que le fichier s_code.js ; elle est toutefois plus légère et plus rapide sur les sites pour mobiles comme sur les sites pour ordinateur.

## Informations à connaître avant la migration {#section_B8E7B39E8469468883BA0B41234F21C4}

La liste suivante contient les modifications que vous devez connaître avant de passer à cette nouvelle version d’[!DNL AppMeasurement] :

* Certains modules externes ne sont plus pris en charge. Reportez-vous à la section [Prise en charge des modules externes dans AppMeasurement](/help/implement/js-implementation/c-appmeasurement-js/plugins-support.md).
* La bibliothèque ne prend pas en charge la sélection de comptes dynamique ([dynamicAccountList](/help/implement/js-implementation/c-variables/configuration-variables.md), [dynamicAccountMatch](/help/implement/js-implementation/c-variables/configuration-variables.md) et [dynamicAccountSelection](/help/implement/js-implementation/c-variables/configuration-variables.md)).

* La bibliothèque et le code de page peuvent être déployés dans la balise `<head>`.
* Les modules Media et Integrate sont pris en charge à l’aide du code de module mis à jour qui se trouve dans le package de téléchargement d’[!DNL AppMeasurement] pour JavaScript. Le module Survey n’est pas pris en charge.
* Le code de page existant est compatible avec la nouvelle version.
* La bibliothèque fournit des utilitaires natifs pour obtenir des paramètres de requête, lire et écrire des cookies et effectuer le suivi avancé des liens.

## Questions fréquentes {#section_9BD41B08F7B54197B230937714B9357A}

Reportez-vous à la section [Questions fréquentes](/help/implement/faq.md) pour en savoir plus sur les performances, le suivi vidéo, les services mobiles, etc.

## Processus d’initialisation {#section_F6D5680F6D134B6AB1F01C6235860635}

Appel de `s_gi()`, transmission de l’identifiant de suite de rapports pour initialiser une instance [!DNL AppMeasurement] :

```js
var s_account="INSERT-RSID-HERE"
var s=s_gi(s_account)
```

Si `s_gi` est appelé, si une instance [!DNL AppMeasurement] n’existe pas pour l’attribut `s_account` spécifié, une nouvelle instance est créée. Sinon, l’instance existante est renvoyée. Ceci permet d’éviter la création d’objets en double pour le même compte.

## Récupération d’une instance AppMeasurement {#section_6F05C96DCAB24C8C9B4B91C5739630A6}

Dans votre code, appelez la fonction [globale s_gi()](/help/implement/js-implementation/function-s-gi.md) pour récupérer une instance [!DNL AppMeasurement] existante.

## Utilitaires {#section_0F47694DD0214645A24C94AB6A4142A0}

JavaScript [!DNL AppMeasurement] fournit les utilitaires intégrés suivants :

* [Util.cookieRead](/help/implement/js-implementation/util-cookieread.md)
* [Util.cookieWrite](/help/implement/js-implementation/util-cookiewrite.md)
* [Util.getQueryParam](/help/implement/js-implementation/util-getqueryparam.md)

## Effacement des variables {#section_597C411E7EDB42BC9A6A0508C9D57147}

Une nouvelle méthode `clearVars` est disponible pour effacer les valeurs suivantes de l’objet d’instance :

* `props`
* `eVars`
* `hier`
* `list`
* `events`
* `eventList`
* `products`
* `productsList`
* `channel`
* `purchaseID`
* `transactionID`
* `state`
* `zip`
* `campaign`

Par exemple :

```js
s.clearVars()
```

## Avantages {#section_091E5A28E89E438E8A54A95F55165743}

* 3 à 7 fois plus rapide que le code H.25.
* Décompressée : 21 Ko uniquement ; 8 Ko dans un fichier gzip (code H.25 : 33 Ko décompressé et 13 Ko dans un fichier gzip).
* Prise en charge native de plusieurs modules externes courants ().
* Suffisamment petite et rapide pour être utilisée sur les sites pour mobiles et suffisamment robuste pour être utilisée sur les sites pour Bureau, ce qui vous permet d’exploiter une seule et même bibliothèque dans tous les environnements Web.

