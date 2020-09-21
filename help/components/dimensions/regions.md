---
title: Régions
description: La région géographique du visiteur.
translation-type: ht
source-git-commit: fdc77997c8aea07cc7db1d06c5c0c2cd2f2abbd9
workflow-type: ht
source-wordcount: '381'
ht-degree: 100%

---


# Régions

La dimension « Régions » indique la région géographique du visiteur. Il s’agit d’une zone géographique plus petite qu’un pays, mais plus grande qu’une ville. Dans certains pays, une région est un état, une province ou une préfecture. Dans d’autres, il peut s’agir d’un pays constitutif, d’un département ou d’une région métropolitaine. L’utilisation de cette dimension est utile si vous souhaitez obtenir des informations plus granulaires que les [pays](countries.md), mais pas aussi granulaires que les [villes](cities.md).

## Renseignement de cette dimension avec des données

Cette dimension fait référence aux règles de recherche internes à Adobe. La valeur de recherche est basée sur l’adresse IP envoyée avec l’accès. Adobe travaille en partenariat avec [Digital Element](https://info.digitalelement.com/fr/) pour gérer les recherches entre l’adresse IP et le pays. Cette dimension est prête à l’emploi pour toutes les implémentations.

>[!TIP]
>
>Si votre entreprise suit des réglementations de confidentialité strictes dans lesquelles l’[obscurcissement d’adresse IP](/help/admin/admin/general-acct-settings-admin.md) ne suffit pas, vous pouvez demander la désactivation totale des données de géolocalisation. Contactez l’assistance clientèle avec l’identifiant de la suite de rapports et demandez la désactivation de l’option « Géographie » pour la suite de rapports.

## Éléments de dimension

Les éléments de dimension comprennent les régions et le pays dans lequel se trouve la région. Les exemples de valeurs comprennent `"California (United States)"`, `"Tokyo (Japan)"` ou `"Sao Paulo (Brazil)"`.

Certains éléments de dimension peuvent inclure `"AOL"`, un fournisseur d’accès Internet. Un point d’accès est attribué aux abonnés à ce service en fonction du pays où leur numéro de compte est établi. Les utilisateurs d’AOL utilisent l’adresse IP de ce point d’accès. Cette dimension étant basée sur l’adresse IP, la géolocalisation du point d’accès est utilisée à la place de l’emplacement réel du visiteur.

## Différences entre l’emplacement signalé et l’emplacement réel

Dans la mesure où cette dimension est basée sur l’adresse IP, certains scénarios peuvent montrer une différence entre l’emplacement signalé et l’emplacement réel :

* **Adresses IP représentant des serveurs proxy d’entreprise** : ces visiteurs peuvent apparaître sous la forme de trafic transitant par le réseau d’entreprise de l’utilisateur, qui peut être un emplacement différent si l’utilisateur travaille à distance.
* **Adresses IP de mobiles** : le ciblage des adresses IP de mobiles fonctionne à différents niveaux en fonction de l’emplacement et du réseau. Plusieurs opérateurs renvoient le trafic IP via des points de présence centralisés ou régionaux.
* **Utilisateurs de FAI par satellite** : identifier l’emplacement spécifique de ces utilisateurs s’avère difficile, dans la mesure où ils semblent généralement provenir de l’emplacement de la liaison montante.
* **Adresses IP militaires et gouvernementales** : cette catégorie englobe généralement les membres du personnel qui voyagent autour du globe et accèdent aux sites par le biais de leur point d’origine, plutôt qu’au départ de la base ou du bureau où ils se trouvent actuellement.
