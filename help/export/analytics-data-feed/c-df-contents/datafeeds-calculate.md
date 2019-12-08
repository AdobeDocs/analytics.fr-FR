---
description: Décrit la méthode de calcul de mesures courantes à l’aide de flux de données.
keywords: Data Feed;job;metrics;pre column;post column;bots;date filtering;event string;common;formulas
title: Mesures calculées
topic: Reports and analytics
uuid: a45ea5bb-7c83-468f-b94a-63add78931d7
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Utiliser des flux de données pour calculer des mesures courantes

Décrit la méthode de calcul de mesures courantes à l’aide de flux de données.

> [!IMPORTANT] Les accès normalement exclus d’Adobe Analytics sont inclus dans les flux de données. Utilisez `exclude_hit > 0` pour supprimer les accès exclus des requêtes sur des données brutes. Les données sources de données sont également incluses dans les flux de données. Si vous souhaitez exclure les sources de données, excluez toutes les lignes avec `hit_source = 5,7,8,9`.

## Pages vues

1. Comptez le nombre de lignes où se trouve une valeur `post_pagename` ou `post_page_url`.

## Visites

1. Concaténer `post_visid_high`, `post_visid_low`, `visit_num`et `visit_start_time_gmt`.
1. Comptez le nombre unique de valeurs.

> [!NOTE] Les irrégularités Internet, les irrégularités système ou l’utilisation d’identifiants visiteur personnalisés peuvent rarement utiliser les mêmes `visit_num` valeurs pour différentes visites. Utilisez-la `visit_start_time_gmt` lors du comptage des visites pour vous assurer que ces visites sont comptabilisées.

## Visiteurs

Toutes les méthodes qu’Adobe utilise pour identifier les visiteurs uniques (identifiant visiteur personnalisé, service d’ID d’expérience Cloud, etc.) sont toutes, en fin de compte, calculées comme une valeur dans `post_visid_high` et `post_visid_low`. La concaténation de ces deux colonnes peut servir de norme pour identifier les visiteurs uniques, quelle que soit la manière dont ils ont été identifiés comme visiteurs uniques. Si vous souhaitez comprendre la méthode utilisée par Adobe pour identifier un visiteur unique, utilisez la colonne `post_visid_type`.

1. Concaténer `post_visid_high` et `post_visid_low`.
2. Comptez le nombre unique de valeurs.

## Liens personnalisés, de téléchargement ou de sortie

1. Comptez le nombre de lignes où :
   * `post_page_event = 100` pour les liens personnalisés
   * `post_page_event = 101` pour les liens de téléchargement
   * `post_page_event = 102` pour les liens de sortie

## Événements personnalisés

Toutes les mesures sont comptées dans la `post_event_list` colonne comme des entiers délimités par des virgules. Utilisez `event.tsv` pour faire correspondre des valeurs numériques à l’événement souhaité. Par exemple, `post_event_list = 1,200` indique que l’accès contenait un événement d’achat et un événement personnalisé 1.

1. Count the number of times the event lookup value appears in `post_event_list`.

## Durée

Les accès doivent d’abord être regroupés par visite, puis classés en fonction du nombre d’accès au sein de la visite.

1. Concaténer `post_visid_high`, `post_visid_low`, `visit_num`et `visit_start_time_gmt`.
2. Triez par cette valeur concaténée, puis appliquez un tri secondaire par `visit_page_num`.
3. Si un accès n’est pas le dernier d’une visite, soustrayez la `post_cust_hit_time` valeur de la `post_cust_hit_time` valeur de l’accès suivant.
4. Ce nombre correspond au temps passé (en secondes) pour l’accès. Les filtres peuvent être appliqués pour se concentrer sur les valeurs de dimension ou les événements.

## Commandes, unités et recettes

Si la `currency` valeur d’un accès ne correspond pas à la devise d’une suite de rapports, elle est convertie à l’aide du taux de conversion de ce jour. La colonne `post_product_list` utilise la valeur de devise convertie, de sorte que tous les accès utilisent la même devise dans cette colonne.

1. Exclude all rows where `duplicate_purchase = 1`.
2. N’incluez que les lignes où `event_list` contient l’événement d’achat.
3. Parcourez la `post_product_list` colonne pour extraire toutes les données de prix. La `post_product_list` colonne est formatée de la même manière que la `s.products` variable.
4. Calculez la mesure de votre choix :
   * Compter le nombre de lignes pour calculer les commandes
   * Somme du nombre de `quantity` dans la chaîne de produit pour calculer les unités
   * Somme du nombre de `price` dans la chaîne de produit pour calculer les recettes
