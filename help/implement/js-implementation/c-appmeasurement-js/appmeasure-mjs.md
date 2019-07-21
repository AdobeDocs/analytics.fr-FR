---
description: 'AppMeasurement pour JavaScript est une nouvelle bibliothèque qui fournit les mêmes fonctionnalités de base que le fichier s_code.js ; elle est toutefois plus légère et plus rapide sur les sites pour mobiles comme sur les sites pour Bureau. '
keywords: appmeasurement ; Implémentation d'Analytics ; javascript ; appmeasurement for javascript ; initialisation ; récupérer l'instance appmeasurement ; clear vars ; clearvars ; utilitaires d'appmeasurement ; appmeasurement instance ; avantages d'appmeasurement
seo-description: 'AppMeasurement pour JavaScript est une nouvelle bibliothèque qui fournit les mêmes fonctionnalités de base que le fichier s_code.js ; elle est toutefois plus légère et plus rapide sur les sites pour mobiles comme sur les sites pour Bureau. '
seo-title: AppMeasurement pour JavaScript
solution: Analytics
subtopic: AppMeasurement pour JavaScript
title: AppMeasurement pour JavaScript
topic: Développeur et mise en œuvre
uuid: dc 71 ad 7 a -92 bd -40 cd -8 fab -707 f 6 f 8472 e 2
translation-type: tm+mt
source-git-commit: 76d0ce11d9b560e0df866be9e753804b6fa4bb3d

---


# AppMeasurement pour JavaScript

[!DNL AppMeasurement] pour JavaScript est une nouvelle bibliothèque qui fournit les mêmes fonctionnalités de base que le fichier s_code.js ; elle est toutefois plus légère et plus rapide sur les sites pour mobiles comme sur les sites pour ordinateur.

## Informations à connaître avant la migration {#section_B8E7B39E8469468883BA0B41234F21C4}

The following list contains changes you need to understand before switching to this new [!DNL AppMeasurement] version:

* Certains modules externes ne sont plus pris en charge. See [AppMeasurement Plug-in Support](../../../implement/js-implementation/c-appmeasurement-js/plugins-support.md#concept_E31A189BC8A547738666EB5E00D2252A).
* The library does not support dynamic account selection ([dynamicAccountList](/help/implement/js-implementation/c-variables/configuration-variables.md), [dynamicAccountMatch](/help/implement/js-implementation/c-variables/configuration-variables.md), and [dynamicAccountSelection](/help/implement/js-implementation/c-variables/configuration-variables.md)).

* The library and page code can be deployed inside the `<head>` tag.
* The Media and Integrate modules are supported using updated module code that is in the JavaScript [!DNL AppMeasurement] download package. Le module Survey n’est pas pris en charge.
* Le code de page existant est compatible avec la nouvelle version.
* La bibliothèque fournit des utilitaires natifs pour obtenir des paramètres de requête, lire et écrire des cookies et effectuer le suivi avancé des liens.

## Questions fréquentes {#section_9BD41B08F7B54197B230937714B9357A}

See the [FAQ](../../../implement/faq.md#concept_9BBC230E01114318BE9C08724F2040D3) for information about performance, video tracking, mobile, and more.

## Processus d’initialisation {#section_F6D5680F6D134B6AB1F01C6235860635}

Call `s_gi()`, passing the report suite ID to initialize an [!DNL AppMeasurement] instance:

```js
var s_account="INSERT-RSID-HERE"
var s=s_gi(s_account)
```

When `s_gi` is called, if an [!DNL AppMeasurement] instance does not exist for the specified `s_account`, a new instance is created. Sinon, l’instance existante est renvoyée. Ceci permet d’éviter la création d’objets en double pour le même compte.

## Récupération d’une instance AppMeasurement {#section_6F05C96DCAB24C8C9B4B91C5739630A6}

Throughout your code, call the global [s_gi() function](../../../implement/js-implementation/function-s-gi.md#concept_50EE6629F61A478BB67781408FBA04BD) to retrieve an existing [!DNL AppMeasurement] instance.

## Utilitaires {#section_0F47694DD0214645A24C94AB6A4142A0}

JavaScript [!DNL AppMeasurement] provides the following built-in utilities:

* [Util.cookieRead](../../../implement/js-implementation/util-cookieread.md#concept_33BD774A90504F2C8094DDC16D47440D)
* [Util.cookieWrite](../../../implement/js-implementation/util-cookiewrite.md#concept_9BE4F7D9CDAE4445B9AF3212BC7E61F2)
* [Util.getQueryParam](../../../implement/js-implementation/util-getqueryparam.md#concept_763AD2621BB44A3990204BE72D3C9FA5)

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

