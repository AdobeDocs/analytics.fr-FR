---
title: DMA États-Unis
description: Zone de marché désignée de l’accès.
translation-type: tm+mt
source-git-commit: 52e00470df0f0c6bff84b26c1548e64ff5114fb8
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 1%

---


# DMA États-Unis

La dimension &quot;DMA US&quot; signale la zone de marché désignée (DMA) du visiteur. Il est basé sur les marchés des médias compilés par [Nielsen](https://www.nielsen.com/us/en/intl-campaigns/dma-maps/).

## Renseigner cette dimension avec des données

Cette dimension fait référence aux règles de recherche internes à Adobe. La valeur de recherche est basée sur l’adresse IP envoyée avec l’accès. Adobe collabore avec Nielsen pour gérer les recherches entre l’adresse IP et la DMA. Cette dimension est prête à l’emploi pour toutes les implémentations.

> [!TIP] Si votre entreprise applique des règles strictes de confidentialité lorsque l’ [obscurcissement d’une adresse](/help/admin/admin/general-acct-settings-admin.md) IP ne suffit pas, vous pouvez demander de désactiver entièrement les données de géolocalisation. Contactez le service à la clientèle avec l’identifiant de la suite de rapports et demandez de désactiver la fonction &quot;Géographie&quot; pour la suite de rapports.

## Valeurs de dimension

Les valeurs de dimension comprennent le code DMA et DMA du visiteur. Le code à 3 chiffres n’est pas un code postal, mais plutôt le code DMA de Nielsen. Les exemples de valeurs incluent `"Dallas-Ft. Worth (623)"`, `"New York (501)"`ou `"Los Angeles (803)"`. La valeur de dimension `"No Metro (0)"` inclut tout le trafic international en dehors des États-Unis.

## Différences entre l’emplacement signalé et l’emplacement réel

Dans la mesure où cette dimension est basée sur l’adresse IP, certains scénarios peuvent montrer une différence entre l’emplacement signalé et l’emplacement réel :

* **Adresses IP représentant des serveurs proxy** d’entreprise : Ces visiteurs peuvent apparaître comme du trafic provenant du réseau d’entreprise de l’utilisateur, qui peut être un autre emplacement si l’utilisateur travaille à distance.
* **Adresses** IP mobiles : Le ciblage des adresses IP mobiles fonctionne à différents niveaux selon l’emplacement et le réseau. Un certain nombre d&#39;opérateurs réorientent le trafic IP par l&#39;intermédiaire de points de présence centralisés ou régionaux.
* **Utilisateurs** de FAI par satellite : Il est difficile d’identifier l’emplacement spécifique de ces utilisateurs, car ils semblent généralement provenir de l’emplacement de liaison montante.
* **IP** militaires et gouvernementales : Représente le personnel qui voyage dans le monde entier et qui arrive par son lieu d&#39;origine, plutôt que la base ou le bureau où il est actuellement stationné.
