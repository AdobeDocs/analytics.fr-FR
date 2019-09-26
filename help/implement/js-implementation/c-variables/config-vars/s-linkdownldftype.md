---
description: Les variables dynamiques vous permettent de copier des valeurs d’une variable vers une autre sans entrer les valeurs complètes à plusieurs reprises dans les demandes d’image sur votre site.
keywords: Mise en œuvre d’Analytics
seo-description: Les variables dynamiques vous permettent de copier des valeurs d’une variable vers une autre sans entrer les valeurs complètes à plusieurs reprises dans les demandes d’image sur votre site.
solution: null
title: Variables dynamiques
translation-type: tm+mt
source-git-commit: 60dd1b300035e5149f53870239de85fb3174a77a

---


# s.linkDownloadFileTypes

La variable est une liste d’extensions de fichiers séparées par des virgules.

Si votre site contient des liens pointant vers des fichiers associés à l’une de ces extensions, les URL de ces liens s’afficheront dans le rapport [!UICONTROL Téléchargements de fichiers]

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|--- |--- |--- |--- |
| N/D | N/D | Trafic &gt; Trafic du site &gt; Téléchargements de fichiers | "exe,zip,wav,mp3,mov,mpg,avi,wmv,doc,pdf,xls" |

La variable  variable is only relevant when  is set to 'True.'*`linkDownloadFileTypes`**`trackDownloadLinks`*

Seuls les clics avec le bouton gauche effectués sur un lien sont comptabilisés dans le rapport [!UICONTROL Téléchargements de fichiers]. Tous les téléchargements de fichiers qui démarrent automatiquement lors du chargement d’une page, ou qui sont uniquement téléchargés à la suite d’une redirection, ne sont pas comptabilisés dans le rapport [!UICONTROL Téléchargements de fichiers]. Lorsque vous cliquez sur un fichier avec le bouton droit et sélectionnez ensuite l’option « Enregistrer la cible sous... », il n’est pas comptabilisé dans le rapport [!UICONTROL Téléchargements de fichiers].

La variable *`linkDownloadFileTypes`* peut être utilisée pour effectuer le suivi des clics vers des flux RSS. If you have links to RSS feeds with a .xml or other extension, appending ",xml" to the  list allows you to see how often each RSS link is clicked.*`linkDownloadFileTypes`*

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