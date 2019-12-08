---
description: Questions fréquentes sur les flux de données
keywords: Data Feed;job;pre column;post column;case sensitivity
title: FAQ sur les flux de données
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# FAQ sur les flux de données

Questions fréquentes sur les flux de données.

## Quelle est la différence entre les colonnes avec un `post_` préfixe et les colonnes sans `post_` préfixe ?

Les colonnes sans préfixe `post_` contiennent des données exactement comme elles ont été envoyées à la collecte de données. Les colonnes avec un `post_` préfixe contiennent la valeur après traitement. Les exemples qui peuvent modifier une valeur sont la persistance de variable, les règles de traitement, les règles VISTA, la conversion de devise ou toute autre logique côté serveur appliquée par Adobe. Dans la mesure du possible, Adobe recommande d’utiliser la `post_` version d’une colonne.

If a column does not contain a `post_` version (for example, `visit_num`), then the column can be considered a post column.

## Comment les flux de données gèrent-ils la sensibilité à la casse ?

Dans Adobe Analytics, la plupart des variables sont considérées comme non sensibles à la casse à des fins de création de rapports. Par exemple, 'neige', 'Neige', 'NEIGE' et 'sNow' sont tous considérés comme la même valeur. Le respect de la casse est conservé dans les flux de données.

Si vous constatez différentes variantes de casse de la même valeur entre les colonnes non-publication et publication (par exemple, "neige" dans la colonne "Pré" et "Neige" dans la colonne "Post"), votre implémentation utilise des valeurs en majuscules et en minuscules sur votre site. Les différences de casse dans la colonne « Post » étaient précédemment transmises puis stockées dans un cookie virtuel ou étaient traitées à peu près en même temps pour cette suite de rapports.