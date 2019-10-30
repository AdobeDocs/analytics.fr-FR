---
description: Les variables dynamiques vous permettent de copier des valeurs d’une variable vers une autre sans entrer les valeurs complètes à plusieurs reprises dans les demandes d’image sur votre site.
keywords: Mise en œuvre d’Analytics
seo-description: Les variables dynamiques vous permettent de copier des valeurs d’une variable vers une autre sans entrer les valeurs complètes à plusieurs reprises dans les demandes d’image sur votre site.
solution: null
title: Variables dynamiques
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# s.trackExternalLinks

Si la variable est définie sur « true »,  et  sont utilisés pour déterminer si le lien sur lequel l’utilisateur a cliqué est un lien de sortie.

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|---|---|---|---|
| N/D | N/D | N/D | True |

La variable *`trackExternalLinks`* ne doit être définie sur « false » que si votre site ne comporte aucun lien de sortie ou si vous n’êtes pas intéressé par le suivi des clics effectués sur ces liens. On désigne sous le nom de lien de sortie tout lien qui permet à un visiteur de quitter votre site. Si la variable *`trackExternalLinks`* est définie sur « true », des données sont immédiatement envoyées lorsque vous cliquez sur un lien de sortie. Les données envoyées avec un lien de sortie sont notamment l’URL et le nom du lien, ainsi que les données de mise en correspondance des clics des visiteurs relatives à ce lien. Si la variable *`trackExternalLinks`* est définie sur « false », il est probable que les données de mise en correspondance des clics des visiteurs relatives aux liens de sortie de votre site soient sous-estimées.

## Syntaxe et valeurs possibles

La variable *`trackExternalLinks`* doit être définie sur « true » ou « false ».

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

* Lorsque la variable *`trackExternalLinks`* est définie sur « false », il est probable que les liens que les visiteurs utilisent pour quitter votre site soient sous-estimés dans la mise en correspondance des clics des visiteurs.

* Lorsque la variable *`trackExternalLinks`* est définie sur « true », des données sont envoyées chaque fois qu’un visiteur clique sur un lien de sortie (avant le chargement de la cible du lien).
