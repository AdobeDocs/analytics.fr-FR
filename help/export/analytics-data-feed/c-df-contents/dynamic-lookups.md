---
title: Recherches dynamiques
description: Découvrez ce que sont les recherches dynamiques et comment les activer. Inclut les opérateurs, les attributs mobiles et les types de système d’exploitation.
exl-id: 12327239-06a2-4092-b27d-b94da39abf30
feature: Data Feeds
TQID: 'https://experienceleague.adobe.com/mjETTk3o2-H60wOWr6svwUtIY00-dsmDfnfd-mxtrdU'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
subfeature_v2:
  - id: ede9f3ba-4ee4-4497-9d8e-e9da5848bda0
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 306
ht-degree: 20%

---

# Recherches dynamiques

Les recherches dynamiques vous permettent de recevoir des fichiers de recherche supplémentaires dans votre flux de données qui ne seraient pas disponibles autrement. Ce paramètre permet d’envoyer les tables de recherche suivantes avec chaque fichier de flux de données :

* **Nom de l’opérateur** : fournit un contexte supplémentaire pour la colonne `carrier`. Le nom de fichier inclus est `carrier.tsv`.
* **Attributs mobiles** : fournit un contexte supplémentaire pour la colonne `mobile_id`, y compris toutes les fonctionnalités suivies pour chaque appareil mobile. Le nom de fichier inclus est `mobile_attributes.tsv`.
* **Type de système d’exploitation** : fournit un autre contexte pour la colonne `os`. `operating_systems.tsv` et `operating_system_type.tsv` utilisent tous deux la colonne `os` comme clé, mais seule `operating_system_type.tsv` est une recherche dynamique.

## Activer les recherches dynamiques {#enable-dynamic-lookups}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_datafeed_dynamic_lookups"
>title="Activer les recherches dynamiques"
>abstract="Sélectionnez cette option pour recevoir des fichiers de recherche supplémentaires dans votre flux de données, car ils ne seraient pas disponibles autrement. Ce paramètre permet d’envoyer les tables de recherche suivantes avec chaque fichier de flux de données :<ul><li>Nom de l’opérateur</li><li>Attributs mobiles</li><li>Type de système d’exploitation</li></ul>"

<!-- markdownlint-enable MD034 -->

Si vous souhaitez recevoir les fichiers Lookup mentionnés, vous devez remplir toutes les conditions préalables suivantes :

* La colonne clé doit être incluse dans le flux de données.
   * Par `carrier.tsv`, vous devez inclure `carrier`.
   * Par `mobile_attributes.tsv`, vous devez inclure `mobile_id`.
   * Par `operating_system_type.tsv`, vous devez inclure `os`.
* Les colonnes suivantes doivent être **exclues**. Si l’une de ces colonnes est incluse dans le flux de données, la recherche dynamique `mobile_attributes.tsv` n’est pas incluse.
   * `user_agent`
   * `ch_hdr`
   * `ch_js`

Une fois que votre flux de données répond aux exigences d’inclusion et d’exclusion des colonnes, contactez l’assistance clientèle en indiquant l’identifiant du flux de données et en demandant l’activation des recherches dynamiques.

## Référence d’en-tête de recherche

Les en-têtes de colonne de ces fichiers de recherche ne changent pas au fil du temps. Par conséquent, les en-têtes ne sont pas inclus dans chaque fichier de flux de données. Utilisez ces en-têtes de colonne comme référence ou téléchargez leur fichier `.tsv` respectif.

+++**Nom du transporteur**
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
Téléchargez [Operating_system_type_headers.tsv](assets/operating_system_type_headers.tsv) ou référencez les en-têtes ci-dessous.

`os`
`Operating System Type`
+++
