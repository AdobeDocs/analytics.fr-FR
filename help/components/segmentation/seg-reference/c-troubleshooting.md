---
description: Dépannage et correction des problèmes liés aux segments.
title: Dépannage de la segmentation
feature: Segmentation
exl-id: ca51110e-1ba7-4182-b5b2-baf9b0c017af
source-git-commit: d85e6990998e3c153ef969d8dc7f3a4835f683bf
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 50%

---

# Résolution des problèmes de segmentation

<!-- Looks like this is not part anymore of the current UI.

## Error: "Incompatible elements in this segment" {#incompatible}

This error occurs when you try to save a segment in the Data Warehouse folder where the segment contains elements not compatible with Data Warehouse. To resolve this error, do one of two things:

* Save the segment in a different folder 
* Remove or change the incompatible portions of the segment.

-->

## Pourquoi mon segment ne renvoie-t-il aucune donnée ?  {#no-data}

Raisons possibles :

* Imbrication inverse : par exemple, imbrication d’un conteneur ![Utilisateur](/help/assets/icons/User.svg) **[!UICONTROL Visiteur]** sous un conteneur ![Visite](/help/assets/icons/Visit.svg) **[!UICONTROL Visite]**.
* Le rapport ne prend pas en charge la segmentation.
* Aucune donnée ne correspond aux critères de segmentation.

## Pourquoi ne puis-je pas voir le segment que j’ai créé dans le Gestionnaire de segments ? {#invisible}

Raisons possibles :

* Certaines dimensions sont disponibles uniquement dans Data Warehouse et non dans le gestionnaire de segments.
* Le segment n’est vérifié que pour une suite de rapports spécifique.
* Il est possible qu’un segment partagé ait été supprimé par un autre utilisateur.
* Les segments n’ont pas pu être chargés en raison d’un problème de cache du centre de données ou du navigateur.
* Le segment n’a pas été enregistré.
* L’adresse IP est peut-être bloquée du côté de l’utilisateur.

## Pourquoi les données affichées après avoir appliqué un segment semblent-elles incorrectes ? {#page-data}

Raisons possibles :

* Les règles ou les opérateurs sont incorrects pour le résultat requis.
* Utilisation incorrecte des conteneurs dans le segment.
* Les variables de trafic utilisées pour la segmentation ne sont pas configurées correctement ou ont expiré.
