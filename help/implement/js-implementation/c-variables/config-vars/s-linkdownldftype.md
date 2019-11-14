---
description: Les variables dynamiques vous permettent de copier des valeurs d’une variable vers une autre sans entrer les valeurs complètes à plusieurs reprises dans les demandes d’image sur votre site.
keywords: Analytics Implementation
solution: null
title: Variables dynamiques
translation-type: tm+mt
source-git-commit: f1ebe5e89f62957c8bcc829be4b1a97463210f93

---


# s.linkDownloadFileTypes

La variable est une liste d’extensions de fichiers séparées par des virgules.

Si votre site contient des liens pointant vers des fichiers associés à l’une de ces extensions, les URL de ces liens s’afficheront dans le rapport [!UICONTROL Téléchargements de fichiers].

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|--- |--- |--- |--- |
| N/D | N/D | Trafic &gt; Trafic du site &gt; Téléchargements de fichiers | "exe,zip,wav,mp3,mov,mpg,avi,wmv,doc,pdf,xls" |

La variable *`linkDownloadFileTypes`* n’est pertinente que lorsque la variable *`trackDownloadLinks`* est définie sur « true ».

Seuls les clics avec le bouton gauche effectués sur un lien sont comptabilisés dans le rapport [!UICONTROL Téléchargements de fichiers]. Tous les téléchargements de fichiers qui démarrent automatiquement lors du chargement d’une page, ou qui sont uniquement téléchargés à la suite d’une redirection, ne sont pas comptabilisés dans le rapport [!UICONTROL Téléchargements de fichiers]. Lorsque vous cliquez sur un fichier avec le bouton droit et sélectionnez ensuite l’option « Enregistrer la cible sous... », il n’est pas comptabilisé dans le rapport [!UICONTROL Téléchargements de fichiers].

La variable *`linkDownloadFileTypes`* peut être utilisée pour effectuer le suivi des clics vers des flux RSS. Si vous avez des liens vers des flux RSS avec une extension .xml ou autre, l’ajout de « ,xml » à la liste *`linkDownloadFileTypes`* vous permet de voir la fréquence de clics sur chaque lien RSS.

## Syntaxe et valeurs possibles

Inclure uniquement les extensions de fichiers (sans espaces).

```js
s.linkDownloadFileTypes="type1[,type2[,type3[...]]]"
```

Toute extension de fichier peut être incluse dans la liste. Veillez à ne pas inclure d’extensions de fichier courantes, telles que htm ou aspx, dans *`linkDownloadFileTypes`*. Cela risquerait, en effet, d’entraîner l’envoi d’une demande d’image supplémentaire pour chaque clic, laquelle serait facturée comme un appel au serveur principal.

## Exemples

```js
s.linkDownloadFileTypes="exe,zip,wav,mp3,mov,mpg,avi,wmv,doc,pdf,xls"
```

```js
s.linkDownloadFileTypes="exe,zip,wav,mp3,mov,mpg,avi,wmv,doc,pdf,xls,xml"
```

## Paramètres de configuration*

Aucun

## Pièges, questions et conseils

* Seuls les clics avec le bouton gauche effectués sur les fichiers de téléchargement entraînent l’apparition de l’URL dans le rapport [!UICONTROL Téléchargements de fichiers].
* L’insertion d’une extension de fichier courante dans *`linkDownloadFileTypes`* peut entraîner une augmentation sensible du nombre total d’appels au serveur envoyés aux serveurs d’Adobe.
* Les liens vers des redirections côté serveur ou des pages HTML qui lancent automatiquement le téléchargement d’un fichier ne sont pas comptabilisés, sauf si l’extension de fichier figure dans *`linkDownloadFileTypes`*.
* Les liens qui utilisent le langage JavaScript (tels que javascript:openLink( )) ne sont pas comptabilisés dans les téléchargements de fichiers.

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