---
description: Les variables dynamiques vous permettent de copier des valeurs d’une variable vers une autre sans entrer les valeurs complètes à plusieurs reprises dans les demandes d’image sur votre site.
keywords: Mise en œuvre d’Analytics
seo-description: Les variables dynamiques vous permettent de copier des valeurs d’une variable vers une autre sans entrer les valeurs complètes à plusieurs reprises dans les demandes d’image sur votre site.
solution: null
title: Variables dynamiques
translation-type: tm+mt
source-git-commit: b38ba4222951d957c607cd764224028527835c7e

---


# s.trackDownLoadLinks

Définissez la variable sur « true » si vous souhaitez effectuer le suivi de liens vers des fichiers téléchargeables de votre site.

If  is 'true,'  is used to determine which links are downloadable files.*`trackDownloadLinks`**`linkDownloadFileTypes`*

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|---|---|---|---|
| N/D | N/D | N/D | True |

La variable *`trackDownloadLinks`* ne doit être définie sur « false » que si le site ne comporte aucun lien vers des fichiers téléchargeables ou si vous n’êtes pas intéressé par le suivi des clics effectués sur des fichiers de ce type. If *`trackDownloadLinks`* is 'true,' when a file download link is clicked, data is immediately sent to [!DNL Analytics]. Les données envoyées avec un lien de téléchargement sont notamment l’URL de téléchargement du lien et les données de mise en correspondance des clics des visiteurs relatives à ce lien. Si la variable *`trackDownloadLinks`* is 'false,' then visitor click map data for links to downloadable files on your site is likely to be under reported.

## Syntaxe et valeurs possibles

La syntaxe de la variable *`trackDownloadLinks`* doit être définie sur « true » ou « false ».

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

* When *`trackDownloadLinks`* is 'false,' links that people use to download files on your site are likely to be under reported in visitor click map.

* When *`trackDownloadLinks`* is 'true,' data is sent each time a visitor clicks a file download link.