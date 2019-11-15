---
description: Les variables dynamiques vous permettent de copier des valeurs d’une variable vers une autre sans entrer les valeurs complètes à plusieurs reprises dans les demandes d’image sur votre site.
keywords: Analytics Implementation
solution: null
title: Variables dynamiques
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---



# s.doPlugins

La variable est une référence à la fonction. Elle permet d’appeler la fonction à l’emplacement approprié dans le fichier JavaScript.

La fonction *`s_doPlugins`* est appelée dès que l’une des conditions suivantes se présente :

* La fonction *`t()`* est appelée
* La fonction *`tl()`* est appelée
* Clic sur un lien de sortie ou de téléchargement
* Clic sur un élément de page suivi par la mise en correspondance des clics des visiteurs

La fonction *`doPlugins`* sert à exécuter des routines personnalisées dans le but de rassembler ou de modifier des données. Si vous utilisez un autre objet que « s », assurez-vous que la fonction *`s_doPlugins`* est correctement renommée. Par exemple, si le nom de votre objet est s_mc, la fonction *`s_doPlugins`* doit être appelée s_mc_doPlugins.

## Syntaxe et valeurs possibles

La fonction *`s_doPlugins`* ne doit pas être placée entre guillemets et la valeur *`doPlugins`* doit toujours être affectée au nom exact de la fonction *`s_doPlugins`* (si cette fonction est renommée).

```js
s.doPlugins=s_doPlugins;
```

## Exemples

```js
s.doPlugins=s_doPlugins;
```

```js
s_mc.doPlugins=s_mc_doPlugins;
```

## Paramètres de configuration

Aucun

## Pièges, questions et conseils

* Le partage de contenu avec d’autres clients ou l’extraction de contenu de ces mêmes clients est la seule raison pouvant justifier le changement de nom d’un objet (de s en s_mc, par exemple). En renommant la fonction *`s_doPlugins`* [!UICONTROL s_mc_doPlugins], vous avez la garantie que le fichier JavaScript d’un autre client ne remplacera pas votre fonction *`doPlugins`*.

* Si vous commencez inopinément à extraire du contenu d’un autre client Adobe et que votre fonction *`s_doPlugins`* est remplacée, il est possible de simplement renommer la fonction *`s_doPlugins`* sans modifier le nom de l’objet. La meilleure solution consiste certes à utiliser un nom d’objet différent de celui des autres fichiers JavaScript de la même page, mais cela n’est pas obligatoire.
