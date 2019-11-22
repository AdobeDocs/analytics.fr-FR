---
description: Les variables de page renseignent directement un rapport (pageName, props de liste, variables de liste, etc.).
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: Variables de page
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 47291fb3d55ab3eb5ef181770bf2078c7ea55bc4

---


# timestamp

Cette variable permet de personnaliser l’horodatage d’un accès tout comme les bibliothèques AppMeasurement pour d’autres plateformes.


<!-- 

timestamp.xml

 -->

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|---|---|---|---|
| 4 octets | Date/Heure | Ne sont pas renseignés directement. | Définie par les serveurs de collecte de données. |

**Syntaxe** {#section_1DF752B1202C4412A301AC7CC10874DF}

```js
s.timestamp="UNIX or ISO-8601 format timestamp"
```

La variable *`timestamp`* doit être au format présenté dans la section suivante.

>[!IMPORTANT]
>
>Avant de pouvoir utiliser la variable *`timestamp`*, il faut que votre suite de rapports ait été horodatée par l’assistance clientèle. Une fois la prise en charge de l’horodatage activée, tous les accès envoyés à cette suite à partir de JavaScript doivent être horodatés manuellement (à l’aide de *`s.timestamp`*), sans quoi ces accès ne seront pas enregistrés.
>
>De plus, si vous activez la prise en charge de l’horodatage sur une suite de rapports afin de prendre en charge le suivi hors ligne, tous les accès envoyés à cette suite à partir de JavaScript doivent également être horodatés manuellement (à l’aide de *`s.timestamp`*). Vous ne pouvez pas envoyer à la même suite de rapports des accès horodatés et non horodatés.
>
>Vous pouvez également utiliser le paramètre [Horodatages facultatifs](/help/implement/js-implementation/timestamps-overview.md) pour mélanger les données horodatées et non horodatées dans une même suite de rapports globale, envoyer les données horodatées depuis une application mobile à une suite de rapports globale, puis mettre à niveau les applications afin d’employer les horodatages sans avoir à créer une suite de rapports.

**Formats des horodatages** {#section_C12CBCECCD7047D38EF63A5800761CE9}

Les horodatages doivent être au format UNIX (secondes depuis le 1er janvier 1970) ou ISO-8601, avec les restrictions suivantes pour le format ISO-8601 pris en charge :

* La date et l’heure doivent être précisées, séparées par « T ».
* La date doit être une date civile complète (année, mois et jour). . Les dates de semaine et les dates ordinales ne sont pas prises en charge.
* La date peut avoir un format standard ou étendu (`YYYY-MM-DD` ou `YYYYMMDD`), mais elle doit inclure l’heure et les minutes. Les secondes sont facultatives (`HH:MM`, `HH:MM:SS`, `HHMM` ou `HHMMSS`). Les minutes et secondes fractionnaires peuvent être précisées, mais la partie fractionnaire est ignorée.

* Un fuseau horaire facultatif peut être spécifié au format standard ou étendu (`±HH`, `±HH:MM`, `±HH`, `±HHMM` ou Z).

Les horodatages UNIX sont toujours pris en charge (secondes depuis le 1er janvier 1970).

**Exemples** {#section_FA19C53D70DE4CF2AF259A5B968B84C3}

```js
s.timestamp=Math.round((new Date()).getTime()/1000);
```

```js
s.timestamp="2012-04-20T12:49:31-0700";
```

La liste suivante contient des exemples d’horodatages au format ISO-8601 valide :

```
2013-01-01T12:30:05+06:00 
2013-01-01T12:30:05Z 
2013-01-01T12:30:05 
2013-01-01T12:30
```

**Paramètres de configuration** {#section_5275D206F2CB4009B3681E8C4457124A}

Avant d’utiliser cette variable, le service à la clientèle doit permettre à une suite de rapports d’accepter les horodatages personnalisés. Une fois que les horodatages sont activés, tous les accès envoyés à la suite de rapports doivent contenir un horodatage pour ne pas être ignorés.

**Pièges, questions et conseils** {#section_EFDE8F67D13C4775A461E0B00D30AFD7}

* Les horodatages servent principalement à effectuer le suivi des données hors connexion sur les plateformes mobiles. En règle générale, les horodatages personnalisés sont désactivés, à moins que vous ne collectiez des données d’application Web et hors connexion dans une même suite de rapports.
* Les données sont horodatées lorsque les données hors ligne sont activées dans le SDK mobile (paramètre par défaut) ou lorsqu’une suite de rapports est configurée pour accepter les données horodatées. Les données collectées hors ligne peuvent être envoyées des heures ou des semaines après la date à laquelle l’événement a eu lieu. Ces accès peuvent être placés en file d’attente dans la plateforme Analytics pendant plus longtemps (minutes ou heures) que les accès sans horodatage :

   * Pour les données horodatées envoyées très près de l’heure actuelle, le délai probable est de 10 à 15 minutes.
   * Pour les données horodatées envoyées depuis hier, le délai probable est d’environ 2 heures.
   * Pour les données horodatées envoyées qui sont plus anciennes qu’hier, chaque jour ajoute environ 2 heures de délai, jusqu’à un maximum de 48 heures.

