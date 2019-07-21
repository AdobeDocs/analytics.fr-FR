---
description: Cette section décrit les fichiers qui figurent dans une diffusion de flux de données.
keywords: Flux de données ; tâche ; contenu ; manifest ; fichier ; recherche ; données d'accès ; contenu de diffusion
seo-description: Cette section décrit les fichiers qui figurent dans une diffusion de flux de données.
seo-title: Contenu du flux de données - présentation
solution: Analytics
subtopic: flux de données
title: Contenu du flux de données - présentation
topic: Reports and Analytics
uuid: 82 a 86314-4841-4133-a 0 dc -4 e 7 c 6 cd 14 fc 1
translation-type: tm+mt
source-git-commit: 7fe23291d8ee9675181065025692108aee3ea9a5

---


# Contenu du flux de données - présentation

Cette section décrit les fichiers qui figurent dans une diffusion de flux de données.

## Fichier de manifeste {#section_044BBDE2906D49518F8264CD4832D429}

Le fichier de manifeste contient les informations suivantes sur chaque fichier qui compose le jeu de données téléchargé :

* nom du fichier,
* taille du fichier,
* hachage MD5,
* nombre d’enregistrements dans le fichier.

Le fichier de manifeste utilise le même format qu’un fichier de manifeste JAR Java.

The manifest file is always delivered last as a separate `.txt` file, so that its existence indicates that the complete data set for that request period has already been delivered. La dénomination des fichiers de manifeste applique le schéma suivant :

```
<report_suite_id>_YYYY_MM_DD.txt
```

Un fichier de manifeste type contient des données semblables à celles indiquées ci-dessous :

```
Datafeed-Manifest-Version: 1.0
 Lookup-Files: 1
 Data-Files: 1
 Total-Records: 611

 Lookup-File: bugzilla_2012-09-09-lookup_data.tar.gz
 MD5-Digest: af6de42d8b945d4ec1cf28360085308
 File-Size: 63750

 Data-File: 01-bugzilla_2012-09-09.tsv.gz
 MD5-Digest: 9c70bf783cb3d0095a4836904b72c991
 File-Size: 122534
 Record-Count: 611
```

Chaque fichier de manifeste contient un en-tête qui indique le nombre total de fichiers de recherche et de fichiers de données, ainsi que le total des enregistrements dans tous les fichiers de données. Cet en-tête est suivi de plusieurs sections qui contiennent des informations pour chaque fichier inclus dans la remise du flux de données.

Some feeds are configured to receive a `rsid_YYYY-MM-DD.fin` file instead of a `.txt` manifest. The `.fin` indicates that the upload is complete, but it contains no metadata about the upload.

## Fichiers de recherche {#section_B5863537A48D47D78D0F7274838923C1}

Les fichiers de recherche ne contiennent pas de données d’accès. Il s’agit de fichiers supplémentaires qui fournissent les en-têtes de colonne pour les données d’accès, ainsi que des fichiers de recherche permettant de convertir, en valeurs réelles, les identifiants qui figurent dans le flux de données. Par exemple, une valeur de « 497 » dans la colonne du navigateur indique que l’accès provient de « Microsoft Internet Explorer 8 ».

Note that the `column_headers.tsv` and `event_list.tsv` are specific to the data feed and report suite. D’autres fichiers, tels que `browser.tsv`, sont génériques.

La remise des fichiers de recherche s’effectue dans une archive .zip compressée selon la syntaxe suivante :

```
<report_suite_id>_<YYYY-mm-dd>-<HHMMSS>-lookup_data.<compression_suffix>
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

## Fichiers de données d’accès {#section_B0745236104E41F2BA625D24AB442636}

Hit data is provided in a [!DNL hit_data.tsv] file. La quantité de données qu’il contient est déterminée par le format de remise (horaire ou quotidien et un seul ou plusieurs fichiers). Ce fichier ne contient que des données d’accès. Les en-têtes de colonne sont remis séparément avec les fichiers de recherche. Chaque ligne de ce fichier contient un seul appel de serveur.

## Contenu de la remise {#section_994B43D1E71A4EFDB2E4183C0929A397}

>[!NOTE]
>
>Les fichiers sont codés selon la norme ISO -8859-1.

Les fichiers effectivement livrés par Adobe dépendent du type de flux de données que vous avez configuré. Pour obtenir une description des fichiers remis, trouvez la configuration qui correspond à votre flux de données dans le tableau suivant.

L’heure (HHMMSS) renseignée dans un nom de fichier indique toujours le début de la période des données, quelle que soit la date de production ou de téléchargement du fichier en question.

<table id="table_DBF34F39D29D4DA2B2689029CDA24B92"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Format de remise </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Quotidien, un seul fichier </td> 
   <td colname="col2"> <p>Une fois les données collectées pour une journée, vous recevrez une livraison contenant les éléments suivants : </p> 
    <ul id="ul_D630D73D0DBA440FA704CF31856243C7"> 
     <li id="li_717873DBBF264422A39217E1A8829742">Un seul fichier de données compressé </li> 
     <li id="li_9F75D42FD56E4CC89C4683D32E59337B">Un fichier de manifeste </li> 
    </ul> <p>Le fichier de données remis porte le nom suivant : </p> 
    <code>&lt; report_ suite &gt;_ &lt; AAAA-mm-jj &gt;.&lt;compression_suffix&gt;
    </code> <p> Où <code>&lt;compression_suffix&gt;</code> est <code>tar.gz</code> ou <code>zip</code>. </p> <p>Une fois extrait, le fichier de données contient un seul fichier <span class="filepath">hit_data.tsv</span> avec toutes les données relatives à cette journée, ainsi que les fichiers de recherche compressés décrits ci-dessus. </p> <p>Le fichier de données d’accès varie considérablement en fonction du nombre de variables utilisées de manière active et du trafic sur la suite de rapports. Cependant, la taille d’une ligne de données est, en moyenne, de 500 octets (format compressé) ou de 2 Ko (format non compressé). Vous pouvez multiplier cette valeur par le nombre d’appels serveur pour obtenir une estimation approximative de la taille du fichier de flux de données. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Quotidien, plusieurs fichiers </td> 
   <td colname="col2"> <p>Une fois les données collectées pour une journée, vous recevrez une livraison contenant les éléments suivants : </p> 
    <ul id="ul_4B873D3F6F18467890C36AE8E86F49DA"> 
     <li id="li_227315384B954A5784FA370D9B30E2AF">Un ou plusieurs fichiers de données, découpés en blocs de 2 Go </li> 
     <li id="li_4169D889CEA3446CB5FAA08FD60AA0D0">Un fichier de manifeste </li> 
    </ul> <p>Chaque fichier de données remis porte le nom suivant : </p> 
    <code>&lt; index &gt;-&lt; report suite &gt;_ &lt; AAAA-mm-jj &gt;.&lt;compression_suffix&gt;
    </code> <p> Où <code>&lt;index&gt;</code> est un index de fichier d’incrémentation compris entre <i>1</i> et <i>n</i>, étant donné <i>n</i> fichiers, et <code>&lt;compression_suffix&gt;</code> est <code>tar.gz</code> ou <code>zip</code>. </p> <p>Une fois extrait, chaque fichier de données contient un seul fichier <span class="filepath">hit_data.tsv</span> comprenant approximativement 2 Go de données non compressées, ainsi que les fichiers de recherche compressés décrits ci-dessus. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Horaire, un seul fichier </td> 
   <td colname="col2"> <p>Une fois les données collectées pour une heure, vous recevrez une livraison contenant les éléments suivants : </p> 
    <ul id="ul_29B06981A4F74D2AA1171D733C5FB1F4"> 
     <li id="li_072BBC4BA9B84C61B4E8EFA35F54707B">Un seul fichier de données </li> 
     <li id="li_E2D05E9DAE814309B6BC91798BB29FBB">Un fichier de manifeste </li> 
    </ul> <p>Le fichier de données remis porte le nom suivant : </p> 
    <code>&lt; report_ suite &gt;_ &lt; AAAA-mm-jj &gt;-&lt; HHMMSS &gt;.&lt;compression_suffix&gt;
    </code> <p> Où <code>&lt;compression_suffix&gt;</code> est <code>tar.gz</code> ou <code>zip</code>. </p> <p>Une fois extrait, le fichier de données contient un seul fichier <span class="filepath">hit_data.tsv</span> avec l’ensemble des données relatives à cette heure. Les fichiers de recherche compressés décrits ci-dessus ne sont livrés qu’avec les données correspondant à la première heure de chaque jour. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Horaire, plusieurs fichiers </td> 
   <td colname="col2"> <p>Une fois les données collectées pour une heure, vous recevrez une livraison contenant les éléments suivants : </p> 
    <ul id="ul_A739BA12B66547A28BA45E0B9B747B16"> 
     <li id="li_C0DF059D1E6843C8A38E24CA1B59D99C">Un ou plusieurs fichiers de données, découpés en blocs de 2 Go </li> 
     <li id="li_604266DA9B8A4000905C44C95DA65D14">Un fichier de manifeste </li> 
    </ul> <p>Chaque fichier de données remis porte le nom suivant : </p> 
    <code>&lt; index &gt;-&lt; report suite &gt;_ &lt; AAAA-mm-jj &gt;-&lt; HHMMSS &gt;. tsv.&lt;compression_suffix&gt;
    </code> <p>Où <code>&lt;index&gt;</code> est un index de fichier d’incrémentation compris entre <i>1</i> et <i>n</i>, étant donné <i>n</i> fichiers, et <code>&lt;compression_suffix&gt;</code> est <code>gz</code> ou <code>zip</code>. </p> <p>Une fois extrait, chaque fichier de données contient un seul fichier <span class="filepath">hit_data.tsv</span> comprenant approximativement 2 Go de données non compressées. Les fichiers de recherche compressés décrits ci-dessus ne sont livrés qu’avec les données correspondant à la première heure de chaque jour. </p> </td> 
  </tr> 
 </tbody> 
</table>

