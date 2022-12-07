---
title: Pays
description: Le pays d’où provient l’accès.
feature: Dimensions
exl-id: 47704b08-215d-4d2d-bcd4-1789e308c1c6
source-git-commit: 146d622f370fd7469a8e5f0f2fe68cb31fa91844
workflow-type: tm+mt
source-wordcount: '308'
ht-degree: 77%

---

# Pays

La dimension « Pays » indique le pays d’où provient l’accès. Cette dimension est utile pour déterminer les pays les plus fréquents depuis lesquels les visiteurs accèdent à votre site. Vous pouvez utiliser ces données pour vous concentrer sur les efforts marketing dans ces pays ou vous assurer que l’expérience de votre site est optimale dans les pays qui ont des langues Principales différentes.

## Renseignement de cette dimension avec des données

Cette dimension fait référence aux règles de recherche internes à Adobe. La valeur de recherche est basée sur l’adresse IP envoyée avec l’accès. Adobe travaille en partenariat avec [Digital Element](https://www.digitalelement.com/) pour gérer les recherches entre l’adresse IP et le pays. Cette dimension est prête à l’emploi pour toutes les implémentations.

## Éléments de dimension

Les éléments de dimension incluent les pays du monde entier. Les exemples de valeurs comprennent `"United States"`, `"United Kingdom"` ou `"India"`.

## Différences entre l’emplacement signalé et l’emplacement réel

Dans la mesure où cette dimension est basée sur l’adresse IP, certains scénarios peuvent montrer une différence entre l’emplacement signalé et l’emplacement réel :

* **Adresses IP représentant des serveurs proxy d’entreprise** : ces visiteurs peuvent apparaître sous la forme de trafic transitant par le réseau d’entreprise de l’utilisateur, qui peut être un emplacement différent si l’utilisateur travaille à distance.
* **Adresses IP de mobiles** : le ciblage des adresses IP de mobiles fonctionne à différents niveaux en fonction de l’emplacement et du réseau. Plusieurs opérateurs renvoient le trafic IP via des points de présence centralisés ou régionaux.
* **Utilisateurs de FAI par satellite** : identifier l’emplacement spécifique de ces utilisateurs s’avère difficile, dans la mesure où ils semblent généralement provenir de l’emplacement de la liaison montante.
* **Adresses IP militaires et gouvernementales** : cette catégorie englobe généralement les membres du personnel qui voyagent autour du globe et accèdent aux sites par le biais de leur point d’origine, plutôt qu’au départ de la base ou du bureau où ils se trouvent actuellement.
* **Proxys qui obscurcissent les adresses IP pour des raisons de confidentialité**: Des services comme Apple Private Relay masquent la véritable adresse IP en envoyant aléatoirement des données par le biais d’un intermédiaire ou d’un proxy. Ce proxy remplace ensuite une autre adresse IP avant le transfert vers Adobe.
