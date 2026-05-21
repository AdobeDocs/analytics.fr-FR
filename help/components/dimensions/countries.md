---
title: Pays
description: Le pays d’où provient l’accès.
feature: Dimensions
exl-id: 47704b08-215d-4d2d-bcd4-1789e308c1c6
TQID: https://experienceleague.adobe.com/qEG8tKa7eEuYV6XgYSlf4Y8FPaCiyWxPmdtL6KkKm94
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: d2311670-43bd-4c2e-bc98-1da2aaba9cef
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 324
ht-degree: 65%

---

# Pays

La dimension « Pays »[&#x200B; indique &#x200B;](overview.md) pays d’où provient l’accès. Cette dimension est utile pour déterminer les pays les plus fréquents depuis lesquels les visiteurs accèdent à votre site. Vous pouvez utiliser ces données pour vous concentrer sur les efforts de marketing dans ces pays ou vous assurer que l’expérience de votre site est optimale dans les pays qui ont des langues principales différentes.

## Renseignement de cette dimension avec des données

Cette dimension fait référence aux règles de recherche internes à Adobe. La valeur de recherche est basée sur l’adresse IP envoyée avec l’accès. Adobe travaille en partenariat avec [Digital Element](https://www.digitalelement.com/) pour gérer les recherches entre l’adresse IP et le pays.

* Pour les implémentations d’AppMeasurement, cette dimension est prête à l’emploi.
* Pour les implémentations de Web SDK, activez [!UICONTROL Recherche géographique] lors de la [configuration d’un flux de données](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=fr).

## Éléments de dimension

Les éléments de dimension incluent les pays du monde entier. Les exemples de valeurs comprennent `"United States"`, `"United Kingdom"` ou `"India"`.

## Différences entre l’emplacement signalé et l’emplacement réel

Dans la mesure où cette dimension est basée sur l’adresse IP, certains scénarios peuvent montrer une différence entre l’emplacement signalé et l’emplacement réel :

* **Adresses IP représentant des serveurs proxy d’entreprise** : ces visiteurs peuvent apparaître sous la forme de trafic transitant par le réseau d’entreprise de l’utilisateur, qui peut être un emplacement différent si l’utilisateur travaille à distance.
* **Adresses IP de mobiles** : le ciblage des adresses IP de mobiles fonctionne à différents niveaux en fonction de l’emplacement et du réseau. Certains transporteurs relient le trafic IP par des points de présence centralisés ou régionaux.
* **Utilisateurs de FAI par satellite** : identifier l’emplacement spécifique de ces utilisateurs s’avère difficile, dans la mesure où ils semblent généralement provenir de l’emplacement de la liaison montante.
* **Adresses IP militaires et gouvernementales** : cette catégorie englobe généralement les membres du personnel qui voyagent autour du globe et accèdent aux sites par le biais de leur point d’origine, plutôt qu’au départ de la base ou du bureau où ils se trouvent actuellement.
* **Proxys qui obscurcissent les adresses IP pour des raisons de confidentialité** : des services comme Apple Private Relay masquent l’adresse IP réelle en envoyant des données de manière aléatoire par le biais d’un intermédiaire ou d’un proxy. Ce proxy remplace ensuite une adresse IP différente avant le transfert vers Adobe.
