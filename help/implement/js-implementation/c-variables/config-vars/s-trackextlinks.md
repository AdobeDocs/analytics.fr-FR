---
description: Les variables dynamiques vous permettent de copier des valeurs d’une variable vers une autre sans entrer les valeurs complètes à plusieurs reprises dans les demandes d’image sur votre site.
keywords: Mise en œuvre d’Analytics
seo-description: Les variables dynamiques vous permettent de copier des valeurs d’une variable vers une autre sans entrer les valeurs complètes à plusieurs reprises dans les demandes d’image sur votre site.
solution: null
title: Variables dynamiques
translation-type: tm+mt
source-git-commit: 8c06a54ccd652f3f915af3af040e9cc69f01d0c1

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

## Suivi automatique des liens de sortie et des téléchargements de fichiers

Il est possible de configurer le fichier JavaScript pour un suivi automatique des téléchargements de fichiers et des liens de sortie en fonction des paramètres qui définissent les types des fichiers téléchargés et les liens de sortie.

Les paramètres de contrôle du suivi automatique sont les suivants :

```
s.trackDownloadLinks=true 
s.trackExternalLinks=true 
s.linkDownloadFileTypes="exe,zip,wav,mp3,mov,mpg,avi,doc,pdf,xls" 
s.linkInternalFilters="javascript:,mysite.com,[more filters here]" 
s.linkLeaveQueryString=false 
```

Les paramètres `trackDownloadLinks` and `trackExternalLinks` determine if automatic file download and exit link tracking are enabled. Lorsqu’il est activé, tout lien dont le type de fichier correspond à l’une des valeurs dans `linkDownloadFileTypes` est automatiquement suivi en tant que téléchargement de fichier. Tout lien dont l’URL ne contient aucune des valeurs dans `linkInternalFilters` est automatiquement suivi comme lien de sortie.

In JavaScript H.25.4 (released February 2013), automatic exit link tracking was updated to always ignore links with `HREF` attributes that start with `#`, `about:`, or `javascript:`.

### Exemple 1

Les types de fichiers `.jpg` et `.aspx` ne sont pas inclus dans `linkDownloadFileTypes` ci-dessus. Par conséquent, aucun clic sur ces types n’est automatiquement suivi et rapporté comme des téléchargements de fichiers.

The parameter `linkLeaveQueryString` modifies the logic used to determine exit links. When `linkLeaveQueryString`=false, exit links are determined using only the domain, path, and file portion of the link URL. When `linkLeaveQueryString`=true, the query string portion of the link URL is also used to determine an exit link.

### Exemple 2

Avec les paramètres suivants, l’exemple ci-dessous sera compté comme un lien de sortie :

```
//JS file  
s.linkInternalFilters="javascript:,mysite.com" 
s.linkLeaveQueryString=false 
 
//HTML file 
<a href='https://othersite.com/index.html?r=mysite.com'>Visit Other Site!</a> 
```

### Exemple 3

Avec les paramètres suivants, le lien ci-dessous n’est pas comptabilisé comme un lien de sortie :

```
//JS file  
s.linkInternalFilters="javascript:,mysite.com" 
s.linkLeaveQueryString=true 
 
//HTML  
<a href='https://othersite.com/index.html?r=mysite.com'>Visit Other Site</a> 
```

*Remarque : Un lien unique peut uniquement être suivi comme téléchargement de fichier ou lien de sortie, et le téléchargement de fichier a la priorité. Si un lien est à la fois un lien de sortie et un téléchargement de fichier en fonction des paramètres`linkDownloadFileTypes`et`linkInternalFilters`, il est suivi et signalé comme un téléchargement de fichier et non comme un lien de sortie.*