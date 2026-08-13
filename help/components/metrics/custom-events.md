---
title: Événements personnalisés
description: Le nombre d’accès comprenant un événement personnalisé.
feature: Metrics
exl-id: 9ae3ff53-8634-466a-a9f6-786c1e62c2fa
TQID: https://experienceleague.adobe.com/1D8ONiUuG3T6DqM7HygbBbf0Y4ja5ej1Hfy8-hKo0yg
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 223
ht-degree: 91%

---

# Événements personnalisés

*Cette page d’aide décrit le fonctionnement des événements personnalisés en tant que mesure. Pour plus d’informations sur le fonctionnement des événements personnalisés en tant que variable d’implémentation, consultez [Présentation des événements](/help/implement/vars/page-vars/events/events-overview.md) dans le guide d’utilisation de la mise en œuvre.*

Événement personnalisé [mesures](overview.md) indique le nombre d’accès pour lesquels un événement personnalisé donné a été défini dans une demande d’image. Ces mesures sont essentielles pour de nombreuses implémentations, car elles fournissent des informations sur les événements spécifiques à chaque organisation.

## Méthode de calcul de cette mesure

Les événements personnalisés sont calculés différemment selon leur type. Vous pouvez vérifier le type d’un événement sous [Événements de succès](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/c-success-events/success-event.md) dans les paramètres de la suite de rapports.

* **Événements de compteur** : le paramètre d’événement par défaut. La plupart des événements sont des événements de compteur. Tient compte du nombre d’accès pour lesquels l’événement personnalisé correspondant `event1` - `event1000` existe dans la variable [`events`](/help/implement/vars/page-vars/events/events-overview.md).
* **Événements numériques** : additionne la valeur numérique attribuée à l’événement dans la variable `events`.
* **Événements de devise** : applique une conversion de devise basée sur le taux de change du jour, puis additionne la valeur numérique attribuée à chaque accès dans la variable `events`.

Le nombre d’événements disponibles dépend du contrat Analytics de votre organisation. La plupart des organisations utilisant des contrats non hérités disposent de 1 000 événements personnalisés. Contactez l’équipe Adobe en charge des comptes si vous ne savez pas combien d’événements personnalisés vous sont accessibles.

Adobe recommande vivement d’enregistrer la manière dont vous utilisez chaque événement dans le [document de conception de solution](/help/implement/prepare/solution-design.md) de votre entreprise.
