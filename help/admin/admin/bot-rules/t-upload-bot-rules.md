---
description: Pour importer des règles de robots en vrac, vous pouvez télécharger un fichier CSV qui les définit.
seo-description: Pour importer des règles de robots en vrac, vous pouvez télécharger un fichier CSV qui les définit.
seo-title: Télécharger des règles de robots
solution: Analytics
subtopic: Règles de robots
title: Télécharger des règles de robots
topic: Outils d’administration
uuid: bd 70 c 199-5817-437 e -980 d -6 d 8 f 95 f 95 f 2 c
translation-type: tm+mt
source-git-commit: 93d6c7698216b3064f5417dbcfb33184efc2c132

---


# Télécharger des règles de robots

Pour importer des règles de robots en vrac, vous pouvez télécharger un fichier CSV qui les définit.

Créez un fichier CSV avec les colonnes suivantes, en respectant l’ordre indiqué :

<table id="table_770891EF9E4A49F695977BB6446736B5"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> Nom du robot</code> </p> </td> 
   <td colname="col2"> <p> <code>Début IP</code> </p> </td> 
   <td colname="col3"> <p> <code>Fin IP</code> </p> </td> 
   <td colname="col4"> <p> <code> Règle de correspondance de l’agent (contient ou commence par)</code> </p> </td> 
   <td colname="col5"> <p> <code>Agent - Inclure (100 caractères max.)</code> </p> </td> 
   <td colname="col6"> <p> <code>Agent - Exclure (255 caractères max.)</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

Vous pouvez définir trois types de règles de robots :

* L’agent utilisateur contient ou commence par
* Correspondance d’une seule adresse IP ou d’un seul caractère générique
* Correspondance d’une plage d’adresses IP

Chaque ligne du fichier d’importation ne peut contenir que l’une des définitions de robot suivantes :

* **L’agent utilisateur contient ou commence par** : indiquez une seule chaîne d’agent utilisateur avec laquelle établir une correspondance dans la colonne Agent - Inclure. Indiquez le type de correspondance à effectuer en indiquant *contient* ou *commence par* dans le champ Règle de correspondance de l’agent. An optional value can be included in the Agent Exclude column that defines one or more pipe-delimited ( `|` ) strings that the Agent does not contain. Les correspondances de chaînes ne sont pas sensibles à la casse. Les colonnes Début IP et Fin IP doivent, toutes deux, être vides.

* **Correspondance d'adresse IP ou de caractère générique unique**: Pour faire correspondre une seule adresse IP ( `10.10.10.1`) ou adresse IP générique ( `10.10.*.*`), placez la même valeur dans les colonnes Début IP et Fin IP. Règle de correspondance de l’agent, Agent - Inclure et Agent - Exclure doivent être vides.

* **Correspondance de plage IP** : définissez une plage d’adresses IP à l’aide des colonnes Début IP et Fin IP. Wildcards can be used to match IP ranges, for example `10.10.10.*` to `10.10.20.*`. Règle de correspondance de l’agent, Agent - Inclure et Agent - Exclure doivent être vides.

## Combinaison de plusieurs règles avec l’opérateur « OU »

Pour établir une correspondance avec un robot à l’aide d’une combinaison de règles associées par un opérateur « OU » (par exemple, agent utilisateur OU adresse IP), indiquez un nom identique pour toutes les règles à combiner dans le champ du nom de robot. Les correspondances « ET » ne sont pas prises en charge.

## Remplacer toutes les règles par un fichier de téléchargement

Cochez la case **[!UICONTROL Remplacer les règles existantes]pour supprimer toutes les règles existantes et les remplacer par celles définies dans le fichier de téléchargement.**

## Exporter des règles

Le bouton **[!UICONTROL Exporter le fichier de robot téléchargé]exporte toutes les règles définies dans l’interface utilisateur au format CSV.**
