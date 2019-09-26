---
description: Les variables dynamiques vous permettent de copier des valeurs d’une variable vers une autre sans entrer les valeurs complètes à plusieurs reprises dans les demandes d’image sur votre site.
keywords: Mise en œuvre d’Analytics
seo-description: Les variables dynamiques vous permettent de copier des valeurs d’une variable vers une autre sans entrer les valeurs complètes à plusieurs reprises dans les demandes d’image sur votre site.
solution: null
title: Variables dynamiques
translation-type: tm+mt
source-git-commit: b38ba4222951d957c607cd764224028527835c7e

---


# s.dynamicAccountMatch

La variable utilise l’objet DOM pour récupérer la section de l’URL à laquelle s’appliquent toutes les règles indiquées dans 

This variable is only valid when *`dynamicAccountSelection`* is set to 'True.' Comme la valeur par défaut est [!DNL window.location.host], cette variable n’est pas requise pour le bon fonctionnement de la [!UICONTROL sélection de compte dynamique]. For additional information, see dynamicAccountList.[](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasurement-js/appmeasure-mjs.html)

The rules found in  are applied to the value of . `dynamicAccountList``dynamicAccountMatch` If  only contains  (default), the rules in  apply only to the domain of the page.`dynamicAccountMatch`[!DNL window.location.host]`dynamicAccountList`

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|---|---|---|---|
| N/D | N/D | N/D | window.location.host |

## Syntaxe et valeurs possibles

La syntaxe de la variable `dynamicAccountMatch` est généralement renseignée par le consultant Adobe qui fournit le fichier AppMeasurement pour JavaScript. Les valeurs répertoriées ci-dessous peuvent cependant être appliquées à tout moment.

```js
s.dynamicAccountMatch=[DOM object]
```

| Description | Valeur |
|---|---|
| Domaine (par défaut) | window.location.host |
| Chemin d’accès | window.location.pathname |
| Chaîne de requête | (window.location.search?window.location.search:"?") |
| Domaine et chemin d’accès | window.location.host+window.location.pathname |
| Chemin et chaîne de requête | window.location.pathname+(window.location.search?window.location.search:"?") |
| URL complète | window.location.href |

## Exemples

```js
s.dynamicAccountMatch=window.location.pathname
```

```js
s.dynamicAccountMatch=window.location.host+window.location.pathname
```

## Paramètres de configuration

Aucun

## Pièges, questions et conseils

* La sélection de comptes dynamique n’est pas prise en charge par [AppMeasurement pour JavaScript](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasurement-js/appmeasure-mjs.html).

* Lorsque des pages sont enregistrées sur un disque dur, [!DNL window.location.host] est vide. Ces pages vues sont alors envoyées à la suite de rapports par défaut (dans `s_account`).

* •Lorsqu’une page est traduite au moyen d’un moteur de traduction Web, tel que Google, la [!UICONTROL sélection de compte dynamique] ne fonctionne pas comme prévu. Pour effectuer un suivi plus précis, renseignez la variable [!UICONTROL s_account ] côté serveur.
