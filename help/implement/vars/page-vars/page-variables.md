---
title: Variables de page
description: Définissez des valeurs sur une page individuelle.
feature: Appmeasurement Implementation
exl-id: 321d0db2-61a3-478e-ab51-8e06c7b2bb7b
role: Admin, Developer
TQID: https://experienceleague.adobe.com/mWfMumcPTklFPKUiGIOatDbC0WKW5RDYH56rXTFk3ZY
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: d4db20e3498d54162806b3fdef0b34f45c93a6ff
workflow-type: tm+mt
source-wordcount: 148
ht-degree: 47%

---

# Vue d’ensemble des variables de page

Les variables de page déterminent les valeurs des dimensions et des mesures dans les rapports.

Les listes suivantes sont des variables fréquemment utilisées dans les implémentations :

* [`pageName`](pagename.md) : Nom de la page.
* [`campaign`](campaign.md) : Définissez cette variable sur un paramètre de chaîne de requête pour le suivi de campagne.
* [`events`](events/events-overview.md) : Renseignez les mesures à utiliser dans les rapports.
* [`products`](products.md) : si vous disposez d’un site d’e-commerce, définissez cette variable lorsqu’un visiteur ou une visiteuse consulte ou achète un produit.

## Variables de page retirées

Les variables de page suivantes sont retirées. Ils sont documentés ici à titre de référence si vous les rencontrez dans une implémentation héritée.

* **`hier`** : implémentation de variables de hiérarchie (`hier1`-`hier5`) pour capturer la structure d’un site à des fins de création de rapports. Il est supprimé et n’est pas une dimension disponible dans Analysis Workspace. Utilisez plutôt des [eVars](evar.md) et des classifications.
* **`state`** : capturé l’État américain qu’un visiteur a saisi, généralement par le biais d’un formulaire de livraison ou de facturation. Utilisez plutôt la dimension [[!UICONTROL &#x200B; États américains &#x200B;]](/help/components/dimensions/us-states.md), qu’Adobe renseigne automatiquement à partir de l’emplacement géographique du visiteur.
