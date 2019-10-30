---
description: Les variables dynamiques vous permettent de copier des valeurs d’une variable vers une autre sans entrer les valeurs complètes à plusieurs reprises dans les demandes d’image sur votre site.
keywords: Mise en œuvre d’Analytics
seo-description: Les variables dynamiques vous permettent de copier des valeurs d’une variable vers une autre sans entrer les valeurs complètes à plusieurs reprises dans les demandes d’image sur votre site.
solution: null
title: Variables dynamiques
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

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