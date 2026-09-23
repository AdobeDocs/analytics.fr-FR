---
title: Régions
description: La zone géographique du visiteur
feature: Dimensions
exl-id: 95ab4c7e-71e8-490f-88a4-25201331d848
TQID: https://experienceleague.adobe.com/Yjy-VGZ0alwfMR408QClnOEIB2z-rfgH5XCn9K0bE1A
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
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
    internal-label: Privacy
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '422'
ht-degree: 73%
---
# Régions

La [dimension](overview.md) « Régions » indique la région géographique du visiteur. Il s’agit d’une zone géographique plus petite qu’un pays, mais plus grande qu’une ville. Dans certains pays, une région est un État, une province ou une préfecture. Dans d’autres, il peut s’agir d’un pays constitutif, d’un département ou d’une région métropolitaine. L’utilisation de cette dimension est utile si vous souhaitez obtenir des informations plus granulaires que les [pays](countries.md), mais pas aussi granulaires que les [villes](cities.md).

## Renseignement de cette dimension avec des données

Adobe dérive cette dimension côté serveur de l’adresse IP du visiteur, en la comparant à une table de recherche interne. Adobe s’associe à [Digital Element](https://www.digitalelement.com/) pour gérer les recherches entre l’adresse IP et la région. Aucune variable à définir. Cette dimension est prête à l’emploi pour toutes les implémentations.

| Propriété | Valeur |
| --- | --- |
| **Variable** | Aucune (dérivée de l’adresse IP du visiteur) |
| **Champ Web SDK/XDM** | Aucune (dérivée de l’adresse IP du visiteur) |
| **Paramètre de requête** | S.O. |
| **Balise XML** | S.O. |
| **Limite d’octets** | S.O. |
| **Persistance** | S.O. |

## Éléments de dimension

Les éléments de dimension comprennent les zones géographiques et le pays auquel chacune appartient. Les exemples de valeurs comprennent `"California (United States)"`, `"Tokyo (Japan)"` ou `"Sao Paulo (Brazil)"`.

Certains éléments de dimension peuvent inclure `"AOL"`, un fournisseur d’accès Internet. Un point d’accès est attribué aux abonnés à ce service en fonction du pays où leur numéro de compte est établi. Les utilisateurs d’AOL utilisent l’adresse IP de ce point d’accès. Cette dimension étant basée sur l’adresse IP, la géolocalisation du point d’accès est utilisée à la place de l’emplacement réel du visiteur.

## Différences entre l’emplacement signalé et l’emplacement réel

Étant donné que cette dimension repose sur l’adresse IP, certains scénarios peuvent faire apparaître un écart entre l’emplacement signalé et l’emplacement réel :

* **Adresses IP représentant des serveurs proxy d’entreprise** : ces visiteurs peuvent apparaître sous la forme de trafic transitant par le réseau d’entreprise de l’utilisateur, qui peut être un emplacement différent si l’utilisateur travaille à distance.
* **Adresses IP de mobiles** : le ciblage des adresses IP de mobiles fonctionne à différents niveaux en fonction de l’emplacement et du réseau. Plusieurs opérateurs renvoient le trafic IP via des points de présence centralisés ou régionaux.
* **Utilisateurs de FAI par satellite** : identifier l’emplacement spécifique de ces utilisateurs s’avère difficile, dans la mesure où ils semblent généralement provenir de l’emplacement de la liaison montante.
* **Adresses IP militaires et gouvernementales** : cette catégorie englobe généralement les membres du personnel qui voyagent autour du globe et accèdent aux sites par le biais de leur point d’origine, plutôt qu’au départ de la base ou du bureau où ils se trouvent actuellement.
* **Proxys qui obscurcissent les adresses IP pour des raisons de confidentialité** : des services comme Apple Private Relay masquent l’adresse IP réelle en envoyant des données de manière aléatoire par le biais d’un intermédiaire ou d’un proxy. Ce proxy remplace ensuite une adresse IP différente avant le transfert vers Adobe.
