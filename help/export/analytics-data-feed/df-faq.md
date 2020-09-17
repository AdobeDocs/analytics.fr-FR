---
description: Questions fréquentes sur les flux de données
keywords: Data Feed;job;pre column;post column;case sensitivity
title: FAQ sur les flux de données
translation-type: tm+mt
source-git-commit: a94b8e090b9a3c75a57fd396cac8486bba2e5d79
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 66%

---


# FAQ sur les flux de données

Questions fréquentes sur les flux de données.

## Quelle est la différence entre les colonnes comportant un préfixe `post_` et celle ne comportant pas de préfixe `post_` ?

Les colonnes sans le préfixe `post_` contiennent les données telles qu’elles ont été envoyées lors de la collecte de données. Les colonnes comportant le préfixe `post_` contiennent la valeur après traitement. La persistance de la variable, les règles de traitement, les règles VISTA, la conversion de la devise ou une autre logique côté serveur sont des exemples pouvant modifier une valeur appliqués par Adobe. Adobe recommande d’utiliser la version `post_` d’une colonne dans la mesure du possible.

Si une colonne ne contient pas de version `post_` (par exemple, `visit_num`), alors la colonne peut être considérée comme une colonne « Post ».

## Comment les flux de données gèrent-ils le respect de la casse ?

Dans Adobe Analytics, la plupart des variables sont considérées comme ne respectant pas la casse à des fins de création de rapports. Par exemple, les valeurs « neige », « Neige », « NEIGE » et « nEige » sont toutes considérées comme étant la même valeur. Le respect de la casse est préservé dans les flux de données.

Si vous observez différentes variations de la casse entre des colonnes « Post » et non « Post » (par exemple, « neige » dans la colonne « Pré » et « Neige » dans la colonne « Post »), cela signifie que votre implémentation utilise des valeurs à la fois en majuscules et en minuscules sur votre site. Les différences de casse dans la colonne « Post » étaient précédemment transmises puis stockées dans un cookie virtuel ou étaient traitées à peu près en même temps pour cette suite de rapports.

## Les robots sont-ils filtrés par les règles de robots de la console d’administration incluses dans les flux de données ?

Les flux de données n’incluent pas les robots filtrés par les règles [de robots de la console](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/bot-removal/bot-removal.html)d’administration.

## Pourquoi vois-je plusieurs `000` valeurs dans la colonne `event_list` ou `post_event_list` du flux de données ?

Certains éditeurs de feuilles de calcul, en particulier Microsoft Excel, arrondissent automatiquement de très grands nombres. La `event_list` colonne contient de nombreux nombres délimités par des virgules, ce qui peut entraîner un traitement par Excel de ce nombre. Il arrondit les derniers chiffres à `000`.

adobe recommande de ne pas ouvrir automatiquement `hit_data.tsv` les fichiers dans Microsoft Excel. Utilisez plutôt la boîte de dialogue Importer des données d’Excel et assurez-vous que tous les champs sont traités comme du texte.
