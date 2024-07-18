---
title: Recherches dynamiques
description: Découvrez les recherches dynamiques et comment les activer. Inclut les opérateurs, les attributs mobiles et les types de système d’exploitation.
exl-id: 12327239-06a2-4092-b27d-b94da39abf30
feature: Data Feeds
source-git-commit: 6b8366b451be1612331f517ee80fd57744deafdc
workflow-type: tm+mt
source-wordcount: '266'
ht-degree: 1%

---

# Recherches dynamiques

Les recherches dynamiques vous permettent de recevoir des fichiers de recherche supplémentaires dans votre flux de données, sinon ils ne sont pas disponibles. Ce paramètre permet d’envoyer les tables de recherche suivantes avec chaque fichier de flux de données :

* **Nom de l’opérateur** : fournit un contexte supplémentaire pour la colonne `carrier`. Le nom de fichier inclus est `carrier.tsv`.
* **Attributs mobiles** : fournit un contexte supplémentaire pour la colonne `mobile_id`, y compris toutes les fonctionnalités suivies pour chaque appareil mobile. Le nom de fichier inclus est `mobile_attributes.tsv`.
* **Type de système d’exploitation** : fournit un autre contexte pour la colonne `os`. `operating_systems.tsv` et `operating_system_type.tsv` utilisent tous les deux la colonne `os` comme clé, mais seul `operating_system_type.tsv` est une recherche dynamique.

## Activation des recherches dynamiques

Si vous souhaitez recevoir les fichiers de recherche mentionnés, vous devez respecter toutes les conditions préalables suivantes :

* La colonne clé doit être incluse dans le flux de données.
   * Pour `carrier.tsv`, vous devez inclure `carrier`.
   * Pour `mobile_attributes.tsv`, vous devez inclure `mobile_id`.
   * Pour `operating_system_type.tsv`, vous devez inclure `os`.
* Les colonnes suivantes doivent être **excluded**. Si l’une de ces colonnes est incluse dans le flux de données, la recherche dynamique `mobile_attributes.tsv` n’est pas incluse.
   * `user_agent`
   * `ch_hdr`
   * `ch_js`

Une fois que votre flux de données répond aux exigences d’inclusion et d’exclusion des colonnes, contactez l’assistance clientèle avec l’identifiant du flux de données et demandez-en d’activer les recherches dynamiques.

## Référence de l’en-tête de recherche

Les en-têtes de colonne de ces fichiers de recherche ne changent pas au fil du temps. Par conséquent, les en-têtes ne sont pas inclus dans chaque fichier de flux de données. Utilisez ces en-têtes de colonne comme référence ou téléchargez leur fichier `.tsv` respectif.

+++**Nom de l’opérateur**
Téléchargez [carrier_headers.tsv](assets/carrier_headers.tsv) ou référencez les en-têtes ci-dessous.

`carrier`
`Carrier Name`
+++

+++**Attributs mobiles**
Téléchargez [mobile_attributes_headers.tsv](assets/mobile_attributes_headers.tsv) ou référencez les en-têtes ci-dessous.

`mobile_id`
`Manufacturer`
`Device`
`Device Type`
`Operating System`
`Diagonal Screen Size`
`Screen Height`
`Screen Width`
`Cookie Support`
`Color Depth`
`MP3 Audio Support`
`AAC Audio Support`
`AMR Audio Support`
`Midi Monophonic Audio Support`
`Midi Polyphonic Audio Support`
`QCELP Audio Support`
`GIF87 Image Support`
`GIF89a Image Support`
`PNG Image Support`
`JPG Image Support`
`3GPP Video Support`
`MPEG4 Video Support`
`3GPP2 Video Support`
`WMV Video Support`
`MPEG4 Part 2 Video Support`
`Stream MP4 AAC LC Video Support`
`Stream 3GP H264 Level 10b Video Support`
`Stream 3GP AAC LC Video Support`
`3GP AAC LC Video Support`
`Stream MP4 H264 Level 11 Video Support`
`Stream MP4 H264 Level 13 Video Support`
`Stream 3GP H264 Level 12 Video Support`
`Stream 3GP H264 Level 11 Video Support`
`Stream 3GP H264 Level 10 Video Support`
`Stream 3GP H264 Level 13 Video Support`
`3GP AMR NB Video Support`
`3GP AMR WB Video Support`
`MP4 H264 Level 11 Video Support`
`3GP H263 Video Support`
`MP4 H264 Level 13 Video Support`
`Stream 3GP H263 Video Support`
`Stream 3GP AMR WB Video Support`
`3GP H264 Level 10b Video Support`
`MP4 ACC LC Video Support`
`Stream 3GP AMR NB Video Support`
`3GP H264 Level 10 Video Support`
`3GP H264 Level 13 Video Support`
`3GP H264 Level 11 Video Support`
`3GP H264 Level 12 Video Support`
`Stream HTTP Live Streaming Video Support`
+++

+++**Type de système d’exploitation**
Téléchargez [operating_system_type_headers.tsv](assets/operating_system_type_headers.tsv) ou référencez les en-têtes ci-dessous.

`os`
`Operating System Type`
+++
