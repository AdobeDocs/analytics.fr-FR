---
description: Les variables dynamiques vous permettent de copier des valeurs d’une variable vers une autre sans entrer les valeurs complètes à plusieurs reprises dans les demandes d’image sur votre site.
keywords: Analytics Implementation
solution: null
title: Variables dynamiques
translation-type: tm+mt
source-git-commit: f1ebe5e89f62957c8bcc829be4b1a97463210f93

---


# s.trackDownLoadLinks

Définissez la variable sur « true » si vous souhaitez effectuer le suivi de liens vers des fichiers téléchargeables de votre site.

Si la valeur *`trackDownloadLinks`* est « true », *`linkDownloadFileTypes`* est utilisé pour déterminer les liens qui sont des fichiers téléchargeables.

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|---|---|---|---|
| N/D | N/D | N/D | True |

La variable *`trackDownloadLinks`* ne doit être définie sur « false » que si le site ne comporte aucun lien vers des fichiers téléchargeables ou si vous n’êtes pas intéressé par le suivi des clics effectués sur des fichiers de ce type. Si la variable *`trackDownloadLinks`* est « true », des données sont immédiatement envoyées à [!DNL Analytics] lorsqu’un utilisateur clique sur un lien de téléchargement de fichier. Les données envoyées avec un lien de téléchargement sont notamment l’URL de téléchargement du lien et les données de mise en correspondance des clics des visiteurs relatives à ce lien. Si la variable *`trackDownloadLinks`* est définie sur « false », il est probable que les données de mise en correspondance des clics des visiteurs relatives aux liens pointant vers des fichiers téléchargeables de votre site soient sous-estimées.

## Syntaxe et valeurs possibles

La variable *`trackDownloadLinks`* doit être définie sur « true » ou « false ».

## Exemples

```
js
s.trackDownloadLinks=true 
```

```
js
s.trackDownloadLinks=false
```

## Paramètres de configuration

Aucun

## Pièges, questions et conseils

* Lorsque la variable *`trackDownloadLinks`* est définie sur « false », il est probable que les liens utilisés par les visiteurs pour télécharger des fichiers sur votre site soient sous-estimés dans la mise en correspondance des clics des visiteurs.

* Lorsque la variable *`trackDownloadLinks`* est définie sur « true », des données sont envoyées chaque fois qu’un visiteur clique sur un lien de téléchargement de fichier.

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