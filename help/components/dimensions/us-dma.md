---
title: DMA États-Unis
description: Zone de marché désignée du hit.
feature: Dimensions
exl-id: 156d5755-2e93-4240-bde3-1d537422b7bf
TQID: https://experienceleague.adobe.com/ijUlnHJ7gP4Jq1g0SzaUVHWbiMki1rgEMd1Pz4sttmU
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
subfeature_v2:
  - id: d2311670-43bd-4c2e-bc98-1da2aaba9cef
    internal-label: Appmeasurement implementation
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
    internal-label: Privacy
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '361'
ht-degree: 55%
---
# DMA États-Unis

La dimension « DMA US » [DMA](overview.md) indique la zone de marché désignée (DMA) du visiteur. Elle est basée sur les marchés des médias compilés par [Nielsen](https://www.nielsen.com/dma-regions/).

## Renseignement de cette dimension avec des données

Adobe dérive cette dimension côté serveur de l’adresse IP du visiteur, en la comparant à une table de recherche interne. Adobe s’associe à Nielsen pour gérer les recherches entre l’adresse IP et la DMA. Aucune variable à définir.

| Propriété | Valeur |
| --- | --- |
| **Variable** | Aucune (dérivée de l’adresse IP du visiteur) |
| **Champ Web SDK/XDM** | Aucune (dérivée de l’adresse IP du visiteur) |
| **Paramètre de requête** | S.O. |
| **Balise XML** | S.O. |
| **Limite d’octets** | S.O. |
| **Persistance** | S.O. |

* Pour les implémentations d’AppMeasurement, cette dimension est prête à l’emploi.
* Pour les implémentations de Web SDK, activez [!UICONTROL Recherche géographique] lors de la [configuration d’un flux de données](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=fr).

## Éléments de dimension

Les éléments Dimension incluent les codes DMA et DMA du visiteur. Le code à 3 chiffres n’est pas un code postal, mais le code DMA de Nielsen. Les exemples de valeurs comprennent `"Dallas-Ft. Worth (623)"`, `"New York (501)"` ou `"Los Angeles (803)"`. L’élément de dimension `"No Metro (0)"` inclut tout le trafic international en dehors des États-Unis.

## Différences entre l’emplacement signalé et l’emplacement réel

Étant donné que cette dimension repose sur l’adresse IP, certains scénarios peuvent faire apparaître un écart entre l’emplacement signalé et l’emplacement réel :

* **Adresses IP représentant des serveurs proxy d’entreprise** : ces visiteurs peuvent apparaître sous la forme de trafic transitant par le réseau d’entreprise de l’utilisateur, qui peut être un emplacement différent si l’utilisateur travaille à distance.
* **Adresses IP de mobiles** : le ciblage des adresses IP de mobiles fonctionne à différents niveaux en fonction de l’emplacement et du réseau. Certains transporteurs relient le trafic IP par des points de présence centralisés ou régionaux.
* **Utilisateurs de FAI par satellite** : identifier l’emplacement spécifique de ces utilisateurs s’avère difficile, dans la mesure où ils semblent généralement provenir de l’emplacement de la liaison montante.
* **Adresses IP militaires et gouvernementales** : cette catégorie englobe généralement les membres du personnel qui voyagent autour du globe et accèdent aux sites par le biais de leur point d’origine, plutôt qu’au départ de la base ou du bureau où ils se trouvent actuellement.
* **Proxys qui obscurcissent les adresses IP pour des raisons de confidentialité** : des services comme Apple Private Relay masquent l’adresse IP réelle en envoyant des données de manière aléatoire par le biais d’un intermédiaire ou d’un proxy. Ce proxy remplace ensuite une adresse IP différente avant le transfert vers Adobe.
