---
title: Ressources d’en-tête de flux de données
description: Fichiers d’en-tête statique utilisés dans certains flux de données.
translation-type: tm+mt
source-git-commit: 07a9c983b0efa6e75765c1222cf056769417a341
workflow-type: tm+mt
source-wordcount: '122'
ht-degree: 0%

---


# Ressources d’en-tête de flux de données

Certains flux de données ne se limitent pas à des tables `hit_data.tsv` de recherche. Ces fichiers de données supplémentaires dépendent des paramètres du flux et n’incluent généralement pas de fichier d’en-tête dans le flux lui-même. Les listes et téléchargements suivants sont des références pour ces fichiers de données supplémentaires.

## Attributs mobiles

Les attributs mobiles affichent les propriétés du périphérique mobile dans l’accès. Ce fichier apparaît lorsque :

* Les recherches dynamiques sont activées. Un délégué du service d’assistance de votre entreprise peut contacter le service d’assistance clientèle avec l’ID de flux souhaité pour activer les recherches dynamiques.
* La `mobile_id` colonne est incluse.
* La `user_agent` colonne est exclue. Cette exclusion est requise en raison d&#39;accords de licence avec DeviceAtlas.

Téléchargez `mobile_attributes_headers.tsv`ou référencez la liste ici :

* `mobile_id`
* `Manufacturer`
* `Device`
* `Device Type`
* `Operating System`
* `Diagonal Screen Size`
* `Screen Height`
* `Screen Width`
* `Cookie Support`
* `Color Depth`
* `MP3 Audio Support`
* `AAC Audio Support`
* `AMR Audio Support`
* `Midi Monophonic Audio Support`
* `Midi Polyphonic Audio Support`
* `QCELP Audio Support`
* `GIF87 Image Support`
* `GIF89a Image Support`
* `PNG Image Support`
* `JPG Image Support`
* `3GPP Video Support`
* `MPEG4 Video Support`
* `3GPP2 Video Support`
* `WMV Video Support`
* `MPEG4 Part 2 Video Support`
* `Stream MP4 AAC LC Video Support`
* `Stream 3GP H264 Level 10b Video Support`
* `Stream 3GP AAC LC Video Support`
* `3GP AAC LC Video Support`
* `Stream MP4 H264 Level 11 Video Support`
* `Stream MP4 H264 Level 13 Video Support`
* `Stream 3GP H264 Level 12 Video Support`
* `Stream 3GP H264 Level 11 Video Support`
* `Stream 3GP H264 Level 10 Video Support`
* `Stream 3GP H264 Level 13 Video Support`
* `3GP AMR NB Video Support`
* `3GP AMR WB Video Support`
* `MP4 H264 Level 11 Video Support`
* `3GP H263 Video Support`
* `MP4 H264 Level 13 Video Support`
* `Stream 3GP H263 Video Support`
* `Stream 3GP AMR WB Video Support`
* `3GP H264 Level 10b Video Support`
* `MP4 ACC LC Video Support`
* `Stream 3GP AMR NB Video Support`
* `3GP H264 Level 10 Video Support`
* `3GP H264 Level 13 Video Support`
* `3GP H264 Level 11 Video Support`
* `3GP H264 Level 12 Video Support`
* `Stream HTTP Live Streaming Video Support`