---
description: Cette section décrit les fichiers qui figurent dans une diffusion de flux de données.
keywords: Data Feed;job;contents;manifest;file;lookup;hit data;delivery contents
subtopic: data feeds
title: Contenu du flux de données - Aperçu
topic: Reports and analytics
uuid: 82a86314-4841-4133-a0dc-4e7c6cd14fc1
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Contenu du flux de données - Aperçu

Cette section décrit les fichiers qui figurent dans une diffusion de flux de données.

## Fichier de manifeste

Le fichier de manifeste contient les informations suivantes sur chaque fichier qui compose le jeu de données téléchargé :

* Nom du fichier
* Taille du fichier
* hachage MD5,
* Nombre d’enregistrements contenus dans le fichier

Le fichier de manifeste utilise le même format qu’un fichier de manifeste JAR Java.

The manifest file is always delivered last as a separate `.txt` file, so that its existence indicates that the complete data set for that request period has already been delivered. La dénomination des fichiers de manifeste applique le schéma suivant :

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

Some feeds are configured to receive a `.fin` file instead of a `.txt` manifest. The `.fin` indicates that the upload is complete, but it contains no metadata about the upload.

## Fichiers de recherche

Certaines colonnes de flux de données génèrent un nombre qui correspond à sa valeur réelle. Les fichiers de recherche sont utilisés pour faire correspondre un nombre d’une colonne de flux de données à une valeur réelle. Par exemple, une valeur de "497" dans la colonne de données d’ `browser` accès indique que l’accès provient de "Microsoft Internet Explorer 8" si vous y regardez `browser.tsv`.

Note that the `column_headers.tsv` and `event_list.tsv` are specific to the data feed and report suite. D’autres fichiers, tels que `browser.tsv`, sont génériques.

La remise des fichiers de recherche s’effectue dans une archive .zip compressée selon la syntaxe suivante :

```text
[rsid]_[YYYY-mm-dd]-lookup_data.[compression_suffix]
```

* [!DNL column_headers.tsv] (personnalisé pour ce flux de données)
* [!DNL browser.tsv]
* [!DNL browser_type.tsv]
* [!DNL color_depth.tsv]
* [!DNL connection_type.tsv]
* [!DNL country.tsv]
* [!DNL javascript_version.tsv]
* [!DNL languages.tsv]
* [!DNL operating_systems.tsv]
* [!DNL plugins.tsv]
* [!DNL resolution.tsv]
* [!DNL referrer_type.tsv]
* [!DNL search_engines.tsv]
* [!DNL event_lookup.tsv] (personnalisé pour ce flux de données)

## Fichiers de données d’accès

Hit data is provided in a [!DNL hit_data.tsv] file. La quantité de données qu’il contient est déterminée par le format de remise (horaire ou quotidien et un seul ou plusieurs fichiers). Ce fichier ne contient que des données d’accès. Les en-têtes de colonne sont remis séparément avec les fichiers de recherche. Chaque ligne de ce fichier contient un seul appel de serveur.

Les fichiers distribués par Adobe varient selon le type de flux de données que vous avez configuré. Tous les fichiers sont codés selon la norme ISO-8859-1.

* `[rsid]` fait référence à l’identifiant de la suite de rapports d’où provient le flux de données.
* `[index]` est utilisée uniquement dans plusieurs flux de fichiers et fait référence à l’ordre correct des fichiers paginés.
* `[YYYY-mm-dd]` fait référence au jour de début du flux de données.
* `[HHMMSS]` est utilisée uniquement dans les flux horaires et fait référence à l’heure de début du flux de données.
* `[compression_suffix]` fait référence au type de compression utilisé. En règle générale, les flux de données sont compressés dans `tar.gz` ou `zip` dans des fichiers.

### Quotidien, un seul fichier

Une fois les données collectées pendant une journée, vous recevez un seul fichier de données compressé et un fichier manifeste. Le fichier de données est nommé :

`[rsid]_[YYYY-mm-dd].[compression_suffix]`

Une fois extrait, le fichier de données contient un seul `hit_data.tsv` fichier avec toutes les données de cette journée, ainsi que des fichiers de recherche pour toutes les colonnes requises.

### Quotidien, plusieurs fichiers

Une fois les données collectées pendant une journée, vous recevez un ou plusieurs fichiers de données compressés et un fichier manifeste. Le fichier de données est nommé :

`[index]-[rsid]_[YYYY-mm-dd].[compression_suffix]`

Une fois extrait, chaque fichier de données contient un seul fichier `hit_data.tsv` contenant environ 2 Go de données non compressées, ainsi que des fichiers de recherche pour toutes les colonnes requises.

### Horaire, un seul fichier

Une fois les données collectées pendant une heure, vous recevez un seul fichier de données compressé et un fichier manifeste. Le fichier de données est nommé :

`[rsid]_[YYYY-mm-dd]-[HHMMSS].[compression_suffix]`

Une fois extrait, le fichier de données contient un seul `hit_data.tsv` fichier avec toutes les données de cette heure, ainsi que des fichiers de recherche pour toutes les colonnes requises.

### Horaire, plusieurs fichiers

Une fois les données collectées pendant une heure, vous recevez un ou plusieurs fichiers de données compressés et un fichier manifeste. Le fichier de données est nommé :

`[index]-[rsid]_[YYYY-mm-dd]-[HHMMSS].[compression_suffix]`

Une fois extrait, chaque fichier de données contient un seul fichier `hit_data.tsv` contenant environ 2 Go de données non compressées, ainsi que des fichiers de recherche pour toutes les colonnes requises.

## Taille du fichier de données

La taille du fichier de données d’accès varie considérablement selon le nombre de variables activement utilisées et le volume de trafic envoyé à la suite de rapports. Cependant, la taille d’une ligne de données est, en moyenne, de 500 octets (format compressé) ou de 2 Ko (format non compressé). Le fait de multiplier cette valeur par le nombre d’appels serveur peut fournir une estimation approximative de la taille d’un fichier de flux de données. Une fois que votre entreprise a commencé à recevoir des fichiers de flux de données, vous pouvez obtenir un nombre plus précis en divisant le nombre de lignes dans `hit_data.tsv` par la taille totale du fichier.
