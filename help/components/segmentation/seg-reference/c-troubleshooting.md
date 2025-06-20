---
description: Dépannage et correction des problèmes liés aux segments.
title: Dépannage de la segmentation
feature: Segmentation
exl-id: ca51110e-1ba7-4182-b5b2-baf9b0c017af
source-git-commit: 002ce0f001796187c01fc955b79ac967ba36da9a
workflow-type: tm+mt
source-wordcount: '220'
ht-degree: 99%

---

# Résolution des problèmes de segmentation

## Erreur : « Éléments incompatibles dans ce segment » {#incompatible}

Cette erreur survient lorsque vous essayez d’enregistrer un segment dans le dossier de l’entrepôt de données et que celui-ci contient des éléments non compatibles avec Data Warehouse. Pour résoudre cette erreur, suivez l’une des deux étapes suivantes :

* enregistrez le segment dans un dossier différent ;
* supprimez ou modifiez les portions incompatibles du segment.

## Pourquoi mon segment ne renvoie-t-il aucune donnée ?  {#no-data}

Raisons possibles :

* Imbrication de conteneurs ; par exemple, lorsqu’un conteneur Visiteur est imbriqué sous un conteneur Visite.
* Le rapport ne prend pas en charge la segmentation.
* Aucune donnée ne correspond aux critères de segmentation.

## Pourquoi ne puis-je pas voir un segment que j’ai créé dans le Gestionnaire de segments ?  {#invisible}

Raisons possibles :

* Certaines dimensions sont disponibles uniquement dans Data Warehouse, et non dans le Gestionnaire de segments.
* Le segment n’est vérifié que pour une suite de rapports spécifique.
* Il est possible qu’un segment partagé ait été supprimé par un autre utilisateur.
* Chargement des segments impossible en raison d’un problème lié au centre de données ou au cache du navigateur.
* Le segment n’a pas été enregistré.
* L’adresse IP est peut-être bloquée du côté de l’utilisateur.

## Pourquoi les données de page affichées après avoir appliqué un segment semblent-elles incorrectes ?  {#page-data}

Raisons possibles :

* Les règles/opérateurs sont incorrects pour le résultat requis.
* Application incorrecte des conteneurs sur le segment.
* Les variables de trafic utilisées pour la segmentation ne sont pas configurées correctement ou ont expiré.
