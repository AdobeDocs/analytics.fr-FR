---
description: Les variables dynamiques vous permettent de copier des valeurs d’une variable vers une autre sans entrer les valeurs complètes à plusieurs reprises dans les demandes d’image sur votre site.
keywords: Mise en œuvre d’Analytics
seo-description: Les variables dynamiques vous permettent de copier des valeurs d’une variable vers une autre sans entrer les valeurs complètes à plusieurs reprises dans les demandes d’image sur votre site.
solution: null
title: Variables dynamiques
translation-type: tm+mt
source-git-commit: b38ba4222951d957c607cd764224028527835c7e

---


# s.trackExternalLinks

Si est défini sur "true" et sont utilisés pour déterminer si un lien sur lequel l’utilisateur a cliqué est un lien de sortie.

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|---|---|---|---|
| N/D | N/D | N/D | True |

La variable *`trackExternalLinks`* ne doit être définie sur « false » que si votre site ne comporte aucun lien de sortie ou si vous n’êtes pas intéressé par le suivi des clics effectués sur ces liens. On désigne sous le nom de lien de sortie tout lien qui permet à un visiteur de quitter votre site. Si la variable *`trackExternalLinks`* is 'true,' then when you click an exit link, tracking data is immediately sent. Les données envoyées avec un lien de sortie sont notamment l’URL et le nom du lien, ainsi que les données de mise en correspondance des clics des visiteurs relatives à ce lien. Si la variable *`trackExternalLinks`* is 'false,' then visitor click map data for exit links on your site is likely to be under reported.

## Syntaxe et valeurs possibles

La syntaxe de la variable *`trackExternalLinks`* doit être définie sur « true » ou « false ».

```
js
s.trackExternalLinks=true|false
```

## Exemples

```
js
s.trackExternalLinks=true 
```

```
js
s.trackExternalLinks=false
```

## Paramètres de configuration

Aucun

## Pièges, questions et conseils

* When *`trackExternalLinks`* is 'false,' links that take people away from your site are likely to be under reported in visitor click map.

* When *`trackExternalLinks`* is 'true,' data is sent each time a visitor clicks on an exit link (before link target loads).
