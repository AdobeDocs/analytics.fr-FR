---
description: Questions fréquentes sur les flux de données
keywords: Flux de données ; tâche ; colonne "Pré" ; colonne "Post" ; respect de la casse
title: FAQ sur les flux de données
exl-id: 1bbf62d5-1c6e-4087-9ed9-8f760cad5420
translation-type: tm+mt
source-git-commit: c6d4095fdf86be52c7921aed84b9229ac3b27f82
workflow-type: tm+mt
source-wordcount: '420'
ht-degree: 58%

---

# FAQ sur les flux de données

Questions fréquentes sur les flux de données.

## Quelle est la différence entre les colonnes comportant un préfixe `post_` et celle ne comportant pas de préfixe `post_` ?

Les colonnes sans le préfixe `post_` contiennent les données telles qu’elles ont été envoyées lors de la collecte de données. Les colonnes comportant le préfixe `post_` contiennent la valeur après traitement. La persistance de la variable, les règles de traitement, les règles VISTA, la conversion de la devise ou une autre logique côté serveur sont des exemples pouvant modifier une valeur appliqués par Adobe. Adobe recommande d’utiliser la version `post_` d’une colonne dans la mesure du possible.

Si une colonne ne contient pas de version `post_` (par exemple, `visit_num`), alors la colonne peut être considérée comme une colonne « Post ».

## Comment les flux de données gèrent-ils le respect de la casse ?

Dans Adobe Analytics, la plupart des variables sont considérées comme ne respectant pas la casse à des fins de création de rapports. Par exemple, les valeurs « neige », « Neige », « NEIGE » et « nEige » sont toutes considérées comme étant la même valeur. Le respect de la casse est préservé dans les flux de données.

Si vous observez différentes variations de la casse entre des colonnes « Post » et non « Post » (par exemple, « neige » dans la colonne « Pré » et « Neige » dans la colonne « Post »), cela signifie que votre implémentation utilise des valeurs à la fois en majuscules et en minuscules sur votre site. Les différences de casse dans la colonne « Post » étaient précédemment transmises puis stockées dans un cookie virtuel ou étaient traitées à peu près en même temps pour cette suite de rapports.

## Les robots sont-ils filtrés par les règles de robots d’Admin Console incluses dans les flux de données ?

Les flux de données n’incluent pas les robots filtrés par les [règles de robots d’Admin Console](https://docs.adobe.com/content/help/fr-FR/analytics/admin/admin-tools/bot-removal/bot-removal.html).

## Pourquoi vois-je plusieurs valeurs `000` dans la colonne de flux de données `event_list` ou `post_event_list` ?

Certains éditeurs de feuilles de calcul, en particulier Microsoft Excel, arrondissent automatiquement de très grands nombres. La colonne `event_list` contient de nombreux nombres délimités par des virgules, ce qui peut parfois entraîner un traitement par Excel en nombre important. Il arrondit les derniers chiffres à `000`.

Adobe recommande de ne pas ouvrir automatiquement les fichiers `hit_data.tsv` dans Microsoft Excel. Utilisez plutôt la boîte de dialogue Importer des données d’Excel et assurez-vous que tous les champs sont traités comme du texte.

## Pourquoi ne puis-je pas extraire des fichiers &quot;horaires&quot; à partir de données qui datent de plus de 7 jours ?

Pour les données de plus de 7 jours, les fichiers &quot;Horaire&quot; d’une journée sont combinés dans un seul fichier &quot;Quotidien&quot;.

Exemple : Un nouveau flux de données est créé le 9 mars 2021 et les données du 1er janvier 2021 au 9 mars sont fournies sous la forme &quot;Horaire&quot;. Cependant, les fichiers &quot;Horaire&quot; antérieurs au 2 mars 2021 sont combinés en un seul fichier &quot;Quotidien&quot;. Vous pouvez extraire des fichiers &quot;Horaire&quot; uniquement à partir de données qui datent de moins de 7 jours à compter de la date de création. Dans ce cas, du 2 mars au 9 mars.
