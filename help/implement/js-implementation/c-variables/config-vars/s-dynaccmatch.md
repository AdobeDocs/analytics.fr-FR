---
description: Les variables dynamiques vous permettent de copier des valeurs d’une variable vers une autre sans entrer les valeurs complètes à plusieurs reprises dans les demandes d’image sur votre site.
keywords: Analytics Implementation
solution: null
title: Variables dynamiques
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# s.dynamicAccountMatch

La variable utilise l’objet DOM pour récupérer la section de l’URL à laquelle s’appliquent toutes les règles indiquées dans.

Cette variable n’est valide que lorsque *`dynamicAccountSelection`* est définie sur « True ». Comme la valeur par défaut est [!DNL window.location.host], cette variable n’est pas requise pour le bon fonctionnement de la [!UICONTROL sélection de compte dynamique]. Pour plus d’informations, voir [dynamicAccountList](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasurement-js/appmeasure-mjs.html).

Les règles trouvées dans `dynamicAccountList` sont appliquées à la valeur de `dynamicAccountMatch`. Si `dynamicAccountMatch` ne contient que [!DNL window.location.host] (par défaut), les règles de `dynamicAccountList` la section s’appliquent uniquement au domaine de la page.

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|---|---|---|---|
| N/D | N/D | N/D | window.location.host |

## Syntaxe et valeurs possibles

La variable `dynamicAccountMatch` est généralement renseignée par le consultant Adobe qui fournit le fichier AppMeasurement pour JavaScript. Les valeurs répertoriées ci-dessous peuvent cependant être appliquées à tout moment.

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

* La sélection de compte dynamique n’est pas prise en charge par [AppMeasurement pour JavaScript](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasurement-js/appmeasure-mjs.html).

* Lorsque des pages sont enregistrées sur un disque dur, [!DNL window.location.host] est vide. Ces pages vues sont alors envoyées à la suite de rapports par défaut (dans `s_account`).

* •Lorsqu’une page est traduite au moyen d’un moteur de traduction Web, tel que Google, la [!UICONTROL sélection de compte dynamique] ne fonctionne pas comme prévu. Pour effectuer un suivi plus précis, renseignez la variable [!UICONTROL s_account]côté serveur.
