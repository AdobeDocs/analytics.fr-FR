---
description: Cette section décrit les fichiers qui figurent dans une diffusion de flux de données.
keywords: Flux de données;tâche;contenu;manifeste;fichier;recherche;données d’accès;diffusion du contenu
subtopic: data feeds
title: Contenu du flux de données - Aperçu
feature: Data Feeds
exl-id: 7456ed99-c2f3-4b19-a63e-6b4e457e7d55
source-git-commit: 6b8366b451be1612331f517ee80fd57744deafdc
workflow-type: tm+mt
source-wordcount: '1002'
ht-degree: 69%

---

# Contenu du flux de données - Aperçu

Les sections suivantes décrivent comment accéder aux fichiers trouvés dans une diffusion de flux de données et les comprendre.

## Accès au contenu des flux de données

Pour accéder au contenu d’un flux de données :

1. Connectez-vous au site de destination des flux de données.

   Il s’agit du site de destination que vous configurez lors de la création du flux de données, par exemple un compartiment Amazon S3 ou Google Cloud Platform.

1. Téléchargez le fichier de flux de données compressé sur votre machine locale.

1. Décompressez le fichier comprimé à l’aide d’un programme qui prend en charge les extensions de fichier `.tar.gz`.

1. Ouvrez le fichier `hit_data.tsv` dans votre application de tableur ou de base de données de votre choix pour afficher les données brutes pour cette journée. —>

## Fichier de manifeste {#feed-manifest}

Le fichier de manifeste contient les informations suivantes sur chaque fichier qui compose le jeu de données téléchargé :

* Nom du fichier
* Taille du fichier
* Hachage MD5
* Nombre d’enregistrements dans le fichier.

Le fichier de manifeste utilise le même format qu’un fichier de manifeste JAR Java.

Le fichier de manifeste est toujours livré sous la forme d’un fichier `.txt` distinct. Par conséquent, son existence indique que l’ensemble du jeu de données relatif à cette période de demande a été livré. La dénomination des fichiers de manifeste applique le schéma suivant :

```text
[rsid]_[YYYY-mm-dd].txt
```

Un fichier de manifeste type contient des données semblables à celles indiquées ci-dessous :

```text
Datafeed-Manifest-Version: 1.0
 Lookup-Files: 1
 Data-Files: 1
 Total-Records: 611

 Lookup-File: rsid_date-lookup_data.tar.gz
 MD5-Digest: af6de42d8b945d4ec1cf28360085308
 File-Size: 63750

 Data-File: 01-rsid_date.tsv.gz
 MD5-Digest: 9c70bf783cb3d0095a4836904b72c991
 File-Size: 122534
 Record-Count: 611
```

Chaque fichier de manifeste contient un en-tête qui indique le nombre total de fichiers de recherche et de fichiers de données, ainsi que le total des enregistrements dans tous les fichiers de données. Cet en-tête est suivi de plusieurs sections qui contiennent des informations pour chaque fichier inclus dans la remise du flux de données.

Certains flux sont configurés en vue de recevoir un fichier `.fin` plutôt qu’un manifeste `.txt`. `.fin` indique que le chargement est terminé, mais que les métadonnées qu’il contient sont dans un format plus ancien.

## Fichiers de recherche

Certaines colonnes de flux de données sortent un nombre qui correspond à sa valeur réelle. Les fichiers de recherche sont utilisés pour faire correspondre un nombre d’une colonne de flux de données à sa valeur réelle. Par exemple, une valeur « 497 » dans la colonne de données d’accès `browser` indique que l’accès provient de « Microsoft Internet Explorer 8 » si vous recherchez dans `browser.tsv`.

Notez que les fichiers `column_headers.tsv` et `event_list.tsv` sont spécifiques au flux de données et à la suite de rapports. D’autres fichiers, tels que `browser.tsv`, sont génériques.

La remise des fichiers de recherche s’effectue dans une archive .zip compressée selon la syntaxe suivante :

```text
[rsid]_[YYYY-mm-dd]-lookup_data.[compression_suffix]
```

* **`column_headers.tsv`** : une seule ligne contenant les en-têtes de colonne pour `hit_data.tsv`.
* **`browser.tsv`** : mappe l’identifiant du navigateur (la colonne de flux `browser`) au nom convivial du navigateur.
* **`browser_type.tsv`** : mappe l’ID de navigateur (la colonne de flux `browser`) au type de navigateur.
* **`color_depth.tsv`** : mappe l’identifiant de profondeur de couleur (colonne de flux `color`) à l’intensité de couleur.
* **`connection_type.tsv`** : mappe l’ID de type de connexion (colonne de flux `connection_type`) au type de connexion.
* **`country.tsv`** : mappe l’ID de pays (la colonne de flux `country`) au nom du pays.
* **`javascript_version.tsv`** : mappe l’ID de version JavaScript (colonne de flux `javascript`) à la version JavaScript.
* **`languages.tsv`** : mappe l’ID de langue (la colonne de flux `language`) à la langue.
* **`operating_systems.tsv`** : mappe l’identifiant du système d’exploitation (la colonne de flux `os`) au nom du système d’exploitation.
* **`plugins.tsv`** : mappe les identifiants du module externe (la colonne de flux `plugin`) à chaque nom de module externe respectif.
* **`resolution.tsv`** : mappe l’ID de résolution (colonne de flux `resolution`) à la résolution de l’écran.
* **`referrer_type.tsv`** : mappe l’ID de type de référent (colonne de flux `ref_type`) au type de référent.
* **`search_engines.tsv`** : associe l’identifiant du moteur de recherche (la colonne de flux `search_engine`) au nom du moteur de recherche.
* **`event.tsv`** : associe chaque ID d’événement (la colonne de flux `event_list`) à son nom d’événement respectif.

## Fichiers de données d’accès

Les données d’accès sont fournies dans un fichier `hit_data.tsv`. La quantité de données qu’il contient est déterminée par le format de remise (horaire ou quotidien et un seul ou plusieurs fichiers). Ce fichier ne contient que des données d’accès. Les en-têtes de colonne sont remis séparément avec les fichiers de recherche. Chaque ligne de ce fichier contient un seul appel de serveur.

Les fichiers livrés par Adobe dépendent du type de flux de données que vous avez configuré. Tous les fichiers sont chiffrés selon la norme ISO-8859-1.

* `[rsid]` fait référence à l’identifiant de suite de rapports d’où le flux de données provient.
* `[index]` n’est utilisé que pour les flux de plusieurs fichiers et fait référence à l’ordre correct des fichiers paginés.
* `[YYYY-mm-dd]` fait référence à la date de départ relative au flux de données.
* `[HHMMSS]` n’est utilisé que dans les flux horaires et fait référence à l’heure de départ du flux de données.
* `[compression_suffix]` fait référence au type de compression utilisé. En règle générale, les flux de données sont compressés en fichiers `tar.gz` ou `zip`.
* `[format_suffix]` fait référence au type de format de fichier. En règle générale, le format de fichier de flux de données est `.tsv`.

### Quotidien, un seul fichier

Lorsque les données sont collectées pour une journée, vous recevez un fichier de données compressé unique et un fichier de manifeste. Le fichier de données s’intitule :

`[rsid]_[YYYY-mm-dd].[compression_suffix]`

Après extraction, le fichier de données contient un fichier `hit_data.tsv` unique qui contient toutes les données pour cette journée, ainsi que les fichiers de recherche pour toutes les colonnes demandées.

### Quotidien, plusieurs fichiers

Lorsque les données sont collectées pour une journée, vous recevez un ou plusieurs fichiers de données compressés et un fichier de manifeste. Le fichier de données s’intitule :

`[index]-[rsid]_[YYYY-mm-dd].[compression_suffix]`

Après extraction, chaque fichier de données contient un fichier `[index]-[rsid]_[YYYY-mm-dd].[format_suffix]` unique qui contient environ 2 Go de données non compressées, ainsi que des fichiers de recherche pour toutes les colonnes demandées.

### Horaire, un seul fichier

Lorsque les données sont collectées pour une heure, vous recevez un fichier de données compressé unique et un fichier de manifeste. Le fichier de données s’intitule :

`[rsid]_[YYYYmmdd]-[HHMMSS].[compression_suffix]`

Après extraction, le fichier de données contient un fichier `hit_data.tsv` unique qui contient toutes les données pour cette heure, ainsi que les fichiers de recherche pour toutes les colonnes demandées.

### Horaire, plusieurs fichiers

Lorsque les données sont collectées pour une heure, vous recevez un ou plusieurs fichiers de données compressés et un fichier de manifeste. Les fichiers de données sont nommés :

`[index]-[rsid]_[YYYYmmdd]-[HHMMSS].[format_suffix].[compression_suffix]`

Une fois extrait, chaque fichier de données contient un seul fichier `[index]-[rsid]_[YYYYmmdd]-[HHMMSS].[format_suffix]` contenant environ 2 Go de données non compressées, ainsi que des fichiers de recherche pour toutes les colonnes demandées.

## Taille du fichier de données

Le fichier de données d’accès varie considérablement en fonction du nombre de variables utilisées de manière active et du trafic envoyé vers la suite de rapports. Cependant, la taille d’une ligne de données est, en moyenne, de 500 octets (format compressé) ou de 2 Ko (format non compressé). Vous pouvez multiplier cette valeur par le nombre d’appels au serveur pour obtenir une estimation approximative de la taille du fichier de flux de données. Lorsque votre entreprise commence à recevoir des fichiers de flux de données, vous pouvez obtenir un nombre plus précis en divisant le nombre de lignes dans `hit_data.tsv` par la taille totale du fichier.