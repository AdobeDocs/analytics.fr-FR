---
description: Les variables dynamiques vous permettent de copier des valeurs d’une variable vers une autre sans entrer les valeurs complètes à plusieurs reprises dans les demandes d’image sur votre site.
keywords: Mise en œuvre d’Analytics
seo-description: Les variables dynamiques vous permettent de copier des valeurs d’une variable vers une autre sans entrer les valeurs complètes à plusieurs reprises dans les demandes d’image sur votre site.
solution: null
title: Variables dynamiques
translation-type: tm+mt
source-git-commit: b38ba4222951d957c607cd764224028527835c7e

---


# s.dynamicAccountList

[!DNL AppMeasurement] pour JavaScript peut sélectionner, de manière dynamique, la suite de rapports à laquelle envoyer les données. La variable contient les règles utilisées pour déterminer la suite de rapports de destination.

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|---|---|---|---|
| N/D | N/D | N/D | "" |

Cette variable est utilisée conjointement avec les variables *`dynamicAccountSelection`* and *`dynamicAccountMatch`* variables. The rules in  are applied if  is set to 'true,' and they apply to the section of the URL specified in .*`dynamicAccountList`**`dynamicAccountSelection`**`dynamicAccountMatch`*

If none of the rules in  matches the URL of the page, the report suite identified in  is used. *`dynamicAccountList`*`s_account` Les règles répertoriées dans cette variable sont appliquées de gauche à droite. Si l’URL de la page correspond à plusieurs règles, celle qui est située le plus à gauche est utilisée pour déterminer la suite de rapports. Par conséquent, vos règles plus génériques doivent être déplacées vers la droite de la liste.

In the following examples, the page URL is  and  is set to true and  is set to `www.mycompany.com/path1/?prod_id=12345``dynamicAccountSelection`**`s_account``mysuitecom.`

| Valeur DynamicAccountList | Valeur DynamicAccountMatch | Suite de rapports qui recevra les données |
|---|---|---|
| `mysuite2=www2.mycompany.com;mysuite1=mycompany.com` | window.location.host | mysuite1 |
| "mysuite1=path4,path1;mysuite2=path2" | window.location.pathname | mysuite1, mysuite2 |
| "mysuite1=path5" | window.location.pathname | mysuitecom, mysuite1 |
| "myprodsuite=prod_id" | window.location.search?window.location.search:"?") | myprodsuite |

## Syntaxe et valeurs possibles

La syntaxe de la variable `dynamicAccountList`est une liste de paires nom=valeurs (règles) séparées par des virgules. Chaque entrée de la liste doit contenir les éléments suivants :

* Un ou plusieurs identifiants de suite de rapports (séparés par des virgules)
* Un signe égal (=)
* Un ou plusieurs filtres URL (séparés par des virgules)

```js
s.dynamicAccountList=rs1[,rs2]=domain1.com[,domain2.com/path][;...]
```

La chaîne accepte uniquement les caractères ASCII standard (pas d’espaces).

## Exemples

```js
s.dynamicAccountList="mysuite2=www2.mycompany.com;mysuite1=mycompany.com"
```

```js
s.dynamicAccountList="ms1,ms2=site1.com;ms1,ms3=site3.com"
```

## Paramètres de configuration

Aucun

## Pièges, questions et conseils

* La sélection de comptes dynamique n’est pas prise en charge par [AppMeasurement pour JavaScript](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasurement-js/appmeasure-mjs.html).

* Si l’URL de la page correspond à plusieurs règles, celle qui est située le plus à gauche est utilisée.
* Si aucune correspondance n’est trouvée, la suite de rapports par défaut est utilisée.
* Si votre page est enregistrée sur le disque dur d’un utilisateur ou traduite au moyen d’un moteur de traduction Web (c’est le cas des pages traduites par Google, par exemple), il y a de fortes chances que la sélection de comptes dynamique ne fonctionne pas. Pour effectuer un suivi plus précis, renseignez la variable `s_account` côté serveur.
* The `dynamicAccountSelection` rules apply only to the section of the URL specified in `dynamicAccountMatch`.

* When using dynamic account selection, be sure to update  every time you obtain a new domain.*`dynamicAccountList`*
* Utilisez le [!DNL DigitalPulse Debugger] pour tenter d’identifier la suite de rapports de destination. The `dynamicAccountSelection` variable always overrides the value of `s_account`.
