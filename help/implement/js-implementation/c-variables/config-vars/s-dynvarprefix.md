---
description: Les variables dynamiques vous permettent de copier des valeurs d’une variable vers une autre sans entrer les valeurs complètes à plusieurs reprises dans les demandes d’image sur votre site.
keywords: Mise en œuvre d’Analytics
seo-description: Les variables dynamiques vous permettent de copier des valeurs d’une variable vers une autre sans entrer les valeurs complètes à plusieurs reprises dans les demandes d’image sur votre site.
solution: null
title: Variables dynamiques
translation-type: tm+mt
source-git-commit: b38ba4222951d957c607cd764224028527835c7e

---


# s.dynamicVariablePrefix {#concept_38C1F2452DDB47FCA8F458BE1398E276}

La variable permet au déploiement de marquer les variables qui doivent être renseignées de manière dynamique.

Les cookies, en-têtes de requête et paramètres de chaîne de requête d’image peuvent être renseignés de cette manière.

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|---|---|---|---|
| N/D | D= | Quelconque | D= |

## Syntaxe et valeurs possibles

```js
s.prop1="D=User-Agent”
```

OU UTILISER UN INDICATEUR PERSONNALISE POUR LES VARIABLES DYNAMIQUES

```js
s.dynamicVariablePrefix=".."
```

## Exemples

```js
s.prop1="D=User-Agent”
```

OU UTILISER UN INDICATEUR PERSONNALISE POUR LES VARIABLES DYNAMIQUES

```js
s.dynamicVariablePrefix=".."
```

```js
s.prop1="..User-Agent"
```

## Pièges, questions et conseils

* Vous pouvez utiliser des variables dynamiques afin de réduire sensiblement la longueur totale de l’URL en copiant des valeurs dans d’autres variables.

* Vous pouvez utiliser des variables dynamiques pour collecter, dans des en-têtes et des cookies, des données qui autrement ne seraient pas disponibles dans le cadre de la collecte de données.
