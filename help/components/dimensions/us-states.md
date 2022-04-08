---
title: États américains
description: État américain du visiteur.
feature: Dimensions
exl-id: d4506e59-c1ff-4348-912d-c1ad73278f56
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: ht
source-wordcount: '329'
ht-degree: 100%

---

# État américain

La dimension « État américain » indique l’état américain du visiteur. Elle est similaire à la dimension [Régions](regions.md), sauf que cette dimension est propre aux États-Unis. L’utilisation de cette dimension est utile si vous souhaitez obtenir des informations plus granulaires que les [pays](countries.md), mais pas aussi granulaires que les [villes](cities.md).

## Renseignement de cette dimension avec des données

Cette dimension fait référence aux règles de recherche internes à Adobe. La valeur de recherche est basée sur l’adresse IP envoyée avec l’accès. Adobe travaille en partenariat avec [Digital Element](https://www.digitalelement.com/) pour gérer les recherches entre l’adresse IP et le pays. Cette dimension est prête à l’emploi pour toutes les implémentations.

## Éléments de dimension

Les éléments de dimension comprennent les régions et le pays dans lequel se trouve la région. Les exemples de valeurs comprennent `"California"`, `"Texas"` ou `"Virginia"`. L’élément de dimension `"Unspecified"` inclut tout le trafic international en dehors des États-Unis.

Cette dimension peut inclure `"AOL"`, un fournisseur d’accès Internet. Un point d’accès est attribué aux abonnés à ce service. Les utilisateurs d’AOL utilisent l’adresse IP de ce point d’accès. Cette dimension étant basée sur l’adresse IP, la géolocalisation du point d’accès est utilisée à la place de l’emplacement réel du visiteur.

## Différences entre l’emplacement signalé et l’emplacement réel

Dans la mesure où cette dimension est basée sur l’adresse IP, certains scénarios peuvent montrer une différence entre l’emplacement signalé et l’emplacement réel :

* **Adresses IP représentant des serveurs proxy d’entreprise** : ces visiteurs peuvent apparaître sous la forme de trafic transitant par le réseau d’entreprise de l’utilisateur, qui peut être un emplacement différent si l’utilisateur travaille à distance.
* **Adresses IP de mobiles** : le ciblage des adresses IP de mobiles fonctionne à différents niveaux en fonction de l’emplacement et du réseau. Plusieurs opérateurs renvoient le trafic IP via des points de présence centralisés ou régionaux.
* **Utilisateurs de FAI par satellite** : identifier l’emplacement spécifique de ces utilisateurs s’avère difficile, dans la mesure où ils semblent généralement provenir de l’emplacement de la liaison montante.
* **Adresses IP militaires et gouvernementales** : cette catégorie englobe généralement les membres du personnel qui voyagent autour du globe et accèdent aux sites par le biais de leur point d’origine, plutôt qu’au départ de la base ou du bureau où ils se trouvent actuellement.
