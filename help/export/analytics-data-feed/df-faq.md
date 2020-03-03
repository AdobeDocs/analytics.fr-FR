---
description: Questions fréquentes sur les flux de données
keywords: Data Feed;job;pre column;post column;case sensitivity
title: FAQ sur les flux de données
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# FAQ sur les flux de données

Questions fréquentes sur les flux de données.

## Quelle est la différence entre les colonnes comportant un préfixe `post_` et celle ne comportant pas de préfixe `post_` ?

Les colonnes sans le préfixe `post_` contiennent les données telles qu’elles ont été envoyées lors de la collecte de données. Les colonnes comportant le préfixe `post_` contiennent la valeur après traitement. La persistance de la variable, les règles de traitement, les règles VISTA, la conversion de la devise ou une autre logique côté serveur sont des exemples pouvant modifier une valeur appliqués par Adobe. Adobe recommande d’utiliser la version `post_` d’une colonne dans la mesure du possible.

Si une colonne ne contient pas de version `post_` (par exemple, `visit_num`), alors la colonne peut être considérée comme une colonne « Post ».

## Comment les flux de données gèrent-ils le respect de la casse ?

Dans Adobe Analytics, la plupart des variables sont considérées comme ne respectant pas la casse à des fins de création de rapports. Par exemple, les valeurs « neige », « Neige », « NEIGE » et « nEige » sont toutes considérées comme étant la même valeur. Le respect de la casse est préservé dans les flux de données.

Si vous observez différentes variations de la casse entre des colonnes « Post » et non « Post » (par exemple, « neige » dans la colonne « Pré » et « Neige » dans la colonne « Post »), cela signifie que votre implémentation utilise des valeurs à la fois en majuscules et en minuscules sur votre site. Les différences de casse dans la colonne « Post » étaient précédemment transmises puis stockées dans un cookie virtuel ou étaient traitées à peu près en même temps pour cette suite de rapports.