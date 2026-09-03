---
title: Recettes
description: La valeur monétaire des produits achetés dans l’ensemble des commandes.
feature: Metrics
exl-id: a70e4d93-704b-46ac-9cec-31ea20d3dcb5
TQID: https://experienceleague.adobe.com/GJsQWf7h-TihzyNUN6e3VGzOUNyxYD1esuvXet5LM1c
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 112
ht-degree: 74%

---

# Recettes

La mesure « Chiffre d’affaires » [Revenue](overview.md) indique le montant monétaire des produits achetés dans toutes les commandes. Cette mesure est essentielle pour les sites d’e-commerce, car elle permet de mesurer la conversion. Vous pouvez combiner cette mesure avec n’importe quelle dimension pour déterminer les éléments de dimension ayant contribué au chiffre d’affaires. Par exemple, vous pouvez afficher les principales campagnes (à l’aide de la dimension [Code de suivi](../dimensions/tracking-code.md)) ou les principaux termes de recherche interne (avec [eVar](../dimensions/evar.md)).

## Méthode de calcul de cette mesure

Chaque accès dont la variable [`events`](/help/implement/vars/page-vars/events/event-purchase.md) contient `purchase`, additionnez les champs « Prix » dans la variable [`products`](/help/implement/vars/page-vars/products.md).

Cette mesure repose sur la variable [currencyCode](/help/implement/vars/config-vars/currencycode.md) si la devise de la page est différente de la devise d’origine de la suite de rapports.
