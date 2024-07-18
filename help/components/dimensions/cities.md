---
title: Villes
description: Ville d’où provient l’accès.
feature: Dimensions
exl-id: c04525bb-50d6-4d28-b5dc-335d089e184b
source-git-commit: e32821dd3f30404166554b8437c508172e4764e5
workflow-type: tm+mt
source-wordcount: '367'
ht-degree: 73%

---

# Villes

La [dimension](overview.md) des &quot;villes&quot; indique la ville d’où provient l’accès. Cette dimension est utile pour déterminer les villes les plus fréquentes depuis lesquelles les visiteurs accèdent à votre site. Vous pouvez utiliser ces données pour concentrer vos efforts publicitaires, comme des panneaux ou des spots publicitaires, sur ces villes.

## Renseignement de cette dimension avec des données

Cette dimension fait référence aux règles de recherche internes à Adobe. La valeur de recherche est basée sur l’adresse IP envoyée avec l’accès. Adobe travaille en partenariat avec [Digital Element](https://www.digitalelement.com/) pour gérer les recherches entre l’adresse IP et la ville.

* Pour les implémentations AppMeasurement, cette dimension est prête à l’emploi.
* Pour les implémentations de SDK Web, activez [!UICONTROL Recherche géographique] lors de la [configuration d’une banque de données](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=fr).

## Éléments de dimension

Les éléments de dimension incluent les villes du monde entier. Les exemples de valeurs comprennent `"New York (New York, United States)"`, `"Bangalore (Karnataka, India)"` ou `"London (London, United Kingdom)"`.

Certains éléments de dimension peuvent inclure `"AOL"`, un fournisseur d’accès Internet. Un point d’accès est attribué aux abonnés à ce service en fonction du pays où leur numéro de compte est établi. Les utilisateurs d’AOL utilisent l’adresse IP de ce point d’accès. Cette dimension étant basée sur l’adresse IP, la géolocalisation du point d’accès est utilisée à la place de l’emplacement réel du visiteur.

## Différences entre l’emplacement signalé et l’emplacement réel

Dans la mesure où cette dimension est basée sur l’adresse IP, certains scénarios peuvent montrer une différence entre l’emplacement signalé et l’emplacement réel :

* **Adresses IP représentant des serveurs proxy d’entreprise** : ces visiteurs peuvent apparaître sous la forme de trafic transitant par le réseau d’entreprise de l’utilisateur, qui peut être un emplacement différent si l’utilisateur travaille à distance.
* **Adresses IP de mobiles** : le ciblage des adresses IP de mobiles fonctionne à différents niveaux en fonction de l’emplacement et du réseau. Certains opérateurs renvoient le trafic IP par le biais de points de présence centralisés ou régionaux.
* **Utilisateurs de FAI par satellite** : identifier l’emplacement spécifique de ces utilisateurs s’avère difficile, dans la mesure où ils semblent généralement provenir de l’emplacement de la liaison montante.
* **Adresses IP militaires et gouvernementales** : cette catégorie englobe généralement les membres du personnel qui voyagent autour du globe et accèdent aux sites par le biais de leur point d’origine, plutôt qu’au départ de la base ou du bureau où ils se trouvent actuellement.
* **Les proxies qui obscurcissent les adresses IP pour des raisons de confidentialité** : des services comme Apple Private Relay masquent la véritable adresse IP en envoyant aléatoirement des données par le biais d’un intermédiaire ou d’un proxy. Ce proxy remplace ensuite une autre adresse IP avant le transfert vers Adobe.
