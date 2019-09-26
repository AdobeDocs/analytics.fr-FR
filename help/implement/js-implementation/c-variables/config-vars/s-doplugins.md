---
description: Les variables dynamiques vous permettent de copier des valeurs d’une variable vers une autre sans entrer les valeurs complètes à plusieurs reprises dans les demandes d’image sur votre site.
keywords: Mise en œuvre d’Analytics
seo-description: Les variables dynamiques vous permettent de copier des valeurs d’une variable vers une autre sans entrer les valeurs complètes à plusieurs reprises dans les demandes d’image sur votre site.
solution: null
title: Variables dynamiques
translation-type: tm+mt
source-git-commit: 60dd1b300035e5149f53870239de85fb3174a77a

---



# s.doPlugins

La variable est une référence à la fonction . Elle permet d’appeler la fonction à l’emplacement approprié dans le fichier JavaScript.

The *`s_doPlugins`* function is called each time any of the following occurs:

* La *`t()`* fonction est appelée
* La *`tl()`* fonction est appelée
* Clic sur un lien de sortie ou de téléchargement
* Clic sur un élément de page suivi par la mise en correspondance des clics des visiteurs

La fonction *`doPlugins`* sert à exécuter des routines personnalisées dans le but de rassembler ou de modifier des données. If you are using an object name other than "s," make sure that the *`s_doPlugins`* is renamed appropriately. For example, if your object name is s_mc, the  function should be called s_mc_doPlugins.*`s_doPlugins`*

## Syntaxe et valeurs possibles

La syntaxe de la variable *`s_doPlugins`* ne doit pas être entre guillemets et *`doPlugins`* doit toujours être affectée au nom exact de la *`s_doPlugins`* fonction (si cette fonction est renommée).

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

* Le partage de contenu avec d’autres clients ou l’extraction de contenu de ces mêmes clients est la seule raison pouvant justifier le changement de nom d’un objet (de s en s_mc, par exemple). En renommant la fonction *`s_doPlugins`* function to [!UICONTROL s_mc_doPlugins] ensures that another client's JavaScript file does not overwrite your *`doPlugins`* function.

* If you unexpectedly start pulling in content from another Adobe customer, and your  function is being overwritten, it is possible to simply rename the  function without changing the object name. *`s_doPlugins`**`s_doPlugins`* La meilleure solution consiste certes à utiliser un nom d’objet différent de celui des autres fichiers JavaScript de la même page, mais cela n’est pas obligatoire.