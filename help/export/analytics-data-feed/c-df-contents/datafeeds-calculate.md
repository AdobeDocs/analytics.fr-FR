---
description: Décrit la méthode de calcul de mesures courantes à l’aide de flux de données.
keywords: Flux de données;traitement;mesures;colonne « pre »;colonne « post »;robots;filtrage par date;chaîne d’événement;courant;formules
title: Mesures calculées
feature: Data Feeds
exl-id: f9b0d637-7a6e-416a-adff-3c7e533bfac7
source-git-commit: adee2f1013cfd2ae231e3133b5a5327b8792bd16
workflow-type: tm+mt
source-wordcount: '499'
ht-degree: 76%

---

# Utilise les flux de données pour calculer des mesures courantes

Décrit la méthode de calcul de mesures courantes à l’aide de flux de données.

>[!NOTE]
>
>Les accès normalement exclus d’Analysis Workspace sont inclus dans les flux de données. Envisagez d’ajouter les conditions suivantes à vos requêtes si elles sont pertinentes :
>
>* **`exclude_hit`** : Analysis Workspace inclut uniquement les données où `exclude_hit = 0`.
>* **`customer_perspective`** : Analysis Workspace inclut uniquement les données où `customer_perspective = 0`, sauf si vous utilisez une suite de rapports virtuelle qui inclut des accès en arrière-plan mobiles.
>* **`hit_source`** : les données provenant de sources de données peuvent contenir des différences entre les données brutes et Analysis Workspace. Si vous souhaitez exclure les accès des sources de données, excluez toutes les lignes où `hit_source = 5,7,8,9`.

## Pages vues

1. Comptez le nombre de lignes où se trouve une valeur `post_pagename` ou `post_page_url`.

## Occurrences

1. Compter le nombre total de lignes.

## Visites

1. Concaténez `post_visid_high`, `post_visid_low`, `visit_num`et `visit_start_time_gmt`.
1. Comptez le nombre unique de valeurs.

>[!TIP]
>
>Les irrégularités Internet, les irrégularités système ou l’utilisation d’identifiants visiteur personnalisés peuvent rarement utiliser les mêmes valeurs `visit_num` pour des visites différentes. Bien que cela soit facultatif, utilisez `visit_start_time_gmt` lors du comptage des visites pour vous assurer que ces visites sont comptabilisées.

## Visiteurs et visiteuses

Toutes les méthodes utilisées par Adobe pour identifier les visiteurs uniques (identifiant visiteur personnalisé, service d’Experience Cloud ID, etc.) sont toutes calculées en fin de compte comme une valeur dans `post_visid_high` et `post_visid_low`. Vous pouvez utiliser la concaténation de ces deux colonnes comme norme d’identification des visiteurs uniques, quelle que soit la manière dont ils ont été identifiés comme tels. Si vous souhaitez comprendre la méthode utilisée par Adobe pour identifier un visiteur unique, utilisez la colonne `post_visid_type`.

1. Concaténez `post_visid_high` et `post_visid_low`.
2. Comptez le nombre unique de valeurs.

## Liens personnalisés, de téléchargement ou de sortie

1. Comptez le nombre de lignes où :
   * `post_page_event = 100` représente les liens personnalisés
   * `post_page_event = 101` représente les liens de téléchargement
   * `post_page_event = 102` représente les liens de sortie

## Événements personnalisés

Toutes les mesures sont comptabilisées dans la colonne `post_event_list` en tant que nombres entiers délimités par des virgules. Utilisez `event.tsv` pour faire correspondre les valeurs numériques à l’événement souhaité. Par exemple, `post_event_list = 1,200` indique que l’accès contenait un événement d’achat et l’événement personnalisé 1.

1. Comptez le nombre de fois où la valeur de recherche d’événement apparaît dans `post_event_list`.

## Durée

Les accès doivent d’abord être regroupés par visite, puis classés selon le nombre d’accès au cours de la visite.

1. Concaténez `post_visid_high`, `post_visid_low`, `visit_num`et `visit_start_time_gmt`.
2. Triez en fonction de cette valeur concaténée, puis appliquez un tri secondaire par `visit_page_num`.
3. Si un accès n’est pas le dernier d’une visite, soustrayez la valeur `post_cust_hit_time` de la valeur `post_cust_hit_time` de l’accès suivant.
4. Ce nombre correspond à la durée passée (en secondes) au cours de cet accès. Il est possible d’appliquer des filtres pour se concentrer sur les éléments ou les événements de dimension.

## Commandes, unités et chiffre d’affaires

Si la valeur `currency` d’un accès ne correspond pas à la devise d’une suite de rapports, elle est convertie en utilisant le taux de conversion de ce jour. La colonne `post_product_list` utilise la valeur de la devise convertie, de sorte que tous les accès utilisent la même devise dans cette colonne.

1. Excluez toutes lignes où `duplicate_purchase = 1`.
2. N’incluez que les lignes où `event_list` contient l’événement d’achat.
3. Parcourez la colonne `post_product_list` pour extraire toutes les données de prix. La colonne `post_product_list` est formatée de la même manière que la variable `s.products`.
4. Calculez la mesure souhaitée :
   * Comptez le nombre de lignes pour calculer les commandes
   * Additionnez le nombre de `quantity` dans la chaîne du produit pour calculer les unités
   * Additionnez le nombre de `price` dans la chaîne du produit pour calculer le chiffre d’affaires
