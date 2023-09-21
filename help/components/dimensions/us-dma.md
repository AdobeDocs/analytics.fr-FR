---
title: DMA États-Unis
description: Zone de marché désignée de l’accès.
feature: Dimensions
exl-id: 156d5755-2e93-4240-bde3-1d537422b7bf
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '307'
ht-degree: 80%

---

# DMA États-Unis

La &quot;DMA des États-Unis&quot; [dimension](overview.md) indique la zone de marché désignée (DMA) du visiteur. Elle est basée sur les marchés des médias compilés par [Nielsen](https://markets.nielsen.com/us/en/contact-us/intl-campaigns/dma-maps/).

## Renseignement de cette dimension avec des données

Cette dimension fait référence aux règles de recherche internes à Adobe. La valeur de recherche est basée sur l’adresse IP envoyée avec l’accès. Adobe collabore avec Nielsen pour gérer les recherches entre l’adresse IP et la DMA. Cette dimension est prête à l’emploi pour toutes les implémentations.

## Éléments de dimension

Les éléments de dimension comprennent la DMA et le code DMA du visiteur. Le code à 3 chiffres n’est pas un code postal, mais le code DMA de Nielsen. Les exemples de valeurs comprennent `"Dallas-Ft. Worth (623)"`, `"New York (501)"` ou `"Los Angeles (803)"`. L’élément de dimension `"No Metro (0)"` inclut tout le trafic international en dehors des États-Unis.

## Différences entre l’emplacement signalé et l’emplacement réel

Dans la mesure où cette dimension est basée sur l’adresse IP, certains scénarios peuvent montrer une différence entre l’emplacement signalé et l’emplacement réel :

* **Adresses IP représentant des serveurs proxy d’entreprise** : ces visiteurs peuvent apparaître sous la forme de trafic transitant par le réseau d’entreprise de l’utilisateur, qui peut être un emplacement différent si l’utilisateur travaille à distance.
* **Adresses IP de mobiles** : le ciblage des adresses IP de mobiles fonctionne à différents niveaux en fonction de l’emplacement et du réseau. Plusieurs opérateurs renvoient le trafic IP via des points de présence centralisés ou régionaux.
* **Utilisateurs de FAI par satellite** : identifier l’emplacement spécifique de ces utilisateurs s’avère difficile, dans la mesure où ils semblent généralement provenir de l’emplacement de la liaison montante.
* **Adresses IP militaires et gouvernementales** : cette catégorie englobe généralement les membres du personnel qui voyagent autour du globe et accèdent aux sites par le biais de leur point d’origine, plutôt qu’au départ de la base ou du bureau où ils se trouvent actuellement.
* **Proxys qui obscurcissent les adresses IP pour des raisons de confidentialité**: des services comme Apple Private Relay masquent la véritable adresse IP en envoyant aléatoirement des données par le biais d’un intermédiaire ou d’un proxy. Ce proxy remplace ensuite une autre adresse IP avant le transfert vers Adobe.
