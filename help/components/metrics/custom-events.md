---
title: Événements personnalisés
description: Le nombre d’accès comprenant un événement personnalisé.
feature: Metrics
exl-id: 9ae3ff53-8634-466a-a9f6-786c1e62c2fa
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 83%

---

# Événements personnalisés

*Cette page d’aide décrit le fonctionnement des événements personnalisés en tant que mesure. Pour plus d’informations sur le fonctionnement des événements personnalisés en tant que variable d’implémentation, consultez [Présentation des événements](/help/implement/vars/page-vars/events/events-overview.md) dans le guide d’utilisation de la mise en œuvre.*

Événement personnalisé [mesures](overview.md) indique le nombre d’accès pour lesquels un événement personnalisé donné a été défini dans une demande d’image. Ces mesures sont essentielles pour de nombreuses implémentations, car elles fournissent des informations sur les événements spécifiques à chaque organisation.

## Méthode de calcul de cette mesure

Les événements personnalisés sont calculés différemment selon leur type. Vous pouvez vérifier le type d’un événement sous [Événements de succès](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/c-success-events/success-event.md) dans les paramètres de la suite de rapports.

* **Événements de compteur** : le paramètre d’événement par défaut. La plupart des événements sont des événements de compteur. Tient compte du nombre d’accès pour lesquels l’événement personnalisé correspondant `event1` - `event1000` existe dans la variable [`events`](/help/implement/vars/page-vars/events/events-overview.md).
* **Événements numériques** : additionne la valeur numérique attribuée à l’événement dans la variable `events`.
* **Événements de devise** : applique une conversion de devise basée sur le taux de change du jour, puis additionne la valeur numérique attribuée à chaque accès dans la variable `events`.

Le nombre d’événements disponibles dépend du contrat Analytics de votre organisation. La plupart des organisations utilisant des contrats non hérités disposent de 1 000 événements personnalisés. Contactez l’équipe chargée de votre compte Adobe si vous n’êtes pas sûr du nombre d’événements personnalisés disponibles.

Adobe recommande vivement d’enregistrer la manière dont vous utilisez chaque événement dans le [document de conception de solution](/help/implement/prepare/solution-design.md) de votre entreprise.
