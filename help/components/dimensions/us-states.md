---
title: États américains
description: L'état américain du visiteur.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 0%

---


# État des États-Unis

La dimension &quot;Etat des Etats-Unis&quot; fait état de l&#39;état du visiteur aux Etats-Unis d&#39;Amérique. Elle est similaire à la dimension [Régions](regions.md) , sauf que cette dimension est propre aux États-Unis. L’utilisation de cette dimension est utile si vous souhaitez obtenir des informations plus granulaires que [Pays](countries.md) mais pas aussi granulaires que [Villes](cities.md).

## Renseigner cette dimension avec des données

Cette dimension fait référence aux règles de recherche internes à Adobe. La valeur de recherche est basée sur l’adresse IP envoyée avec l’accès. Adobe travaille en partenariat avec [Digital Element](https://www.digitalelement.com/) pour gérer les recherches entre l’adresse IP et le pays. Cette dimension est prête à l’emploi pour toutes les implémentations.

>[!TIP]
>
>Si votre entreprise applique des règles strictes de confidentialité lorsque l’ [obscurcissement d’une adresse](/help/admin/admin/general-acct-settings-admin.md) IP ne suffit pas, vous pouvez demander de désactiver entièrement les données de géolocalisation. Contactez le service à la clientèle avec l’identifiant de la suite de rapports et demandez de désactiver la fonction &quot;Géographie&quot; pour la suite de rapports.

## Éléments de dimension

Les éléments de dimension incluent les régions et le pays dans lequel la région réside. Les exemples de valeurs incluent `"California"`, `"Texas"`ou `"Virginia"`. L’élément de dimension `"Unspecified"` inclut tout le trafic international en dehors des États-Unis.

## Différences entre l’emplacement signalé et l’emplacement réel

Dans la mesure où cette dimension est basée sur l’adresse IP, certains scénarios peuvent montrer une différence entre l’emplacement signalé et l’emplacement réel :

* **Adresses IP représentant des serveurs proxy** d’entreprise : Ces visiteurs peuvent apparaître comme du trafic provenant du réseau d’entreprise de l’utilisateur, qui peut être un autre emplacement si l’utilisateur travaille à distance.
* **Adresses** IP mobiles : Le ciblage des adresses IP mobiles fonctionne à différents niveaux selon l’emplacement et le réseau. Un certain nombre d&#39;opérateurs réorientent le trafic IP par l&#39;intermédiaire de points de présence centralisés ou régionaux.
* **Utilisateurs** de FAI par satellite : Il est difficile d’identifier l’emplacement spécifique de ces utilisateurs, car ils semblent généralement provenir de l’emplacement de liaison montante.
* **IP** militaires et gouvernementales : Représente le personnel qui voyage dans le monde entier et qui arrive par son lieu d&#39;origine, plutôt que la base ou le bureau où il est actuellement stationné.
