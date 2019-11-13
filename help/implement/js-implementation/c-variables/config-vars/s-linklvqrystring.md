---
description: Les variables dynamiques vous permettent de copier des valeurs d’une variable vers une autre sans entrer les valeurs complètes à plusieurs reprises dans les demandes d’image sur votre site.
keywords: Mise en œuvre d’Analytics
seo-description: Les variables dynamiques vous permettent de copier des valeurs d’une variable vers une autre sans entrer les valeurs complètes à plusieurs reprises dans les demandes d’image sur votre site.
solution: null
title: Variables dynamiques
translation-type: tm+mt
source-git-commit: 8c06a54ccd652f3f915af3af040e9cc69f01d0c1

---


# s.linkLeaveQueryString

Par défaut, les chaînes de requête sont exclues de tous les rapports.

Pour certains liens de sortie et de téléchargement, la partie importante de l’URL peut se trouver dans la chaîne de requête, comme illustré dans l’exemple d’URL ci-dessous.

```js
https://www.mycompany.com/download.asp?filename=myfile.exe
```

Le nom du fichier de téléchargement peut être défini dans la chaîne de requête et, par conséquent, cette dernière est nécessaire pour une meilleure précision du rapport [!UICONTROL Téléchargements de fichiers].

La variable *`linkLeaveQueryString`* détermine si la chaîne de requête doit être incluse dans les rapports [!UICONTROL Liens de sortie] et [!UICONTROL Téléchargements de fichiers].

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|--- |--- |--- |--- |
| N/D | N/D | Téléchargements de fichiers de liens de sortie | false |

*Remarque : Ce paramètre`linkLeaveQueryString=true`inclut tous les paramètres de chaîne de requête pour tous les liens de sortie et de téléchargement.*

## du lien personnalisé

```js
s.linkLeaveQueryString=[false/true]
```

## Exemples

```js
s.linkLeaveQueryString=false
```

## Valeurs possibles

```js
s.linkLeaveQueryString=false
```

```js
s.linkLeaveQueryString=true
```

## Paramètres de configuration

Aucune configuration n’est nécessaire pour cette variable.

## Pièges, questions et conseils

* Si vous définissez `s.linkLeaveQueryString=true`, tous les paramètres de chaîne de requête sont inclus pour l’ensemble des liens de sortie et de téléchargement.
* La variable `linkLeaveQueryString` n’a aucune incidence sur les URL de page enregistrées, la mise en correspondance des clics des visiteurs ou les rapports [!UICONTROL Chemin].

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