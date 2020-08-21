---
title: Événements personnalisés
description: Le nombre d’accès comprenant un événement personnalisé.
translation-type: ht
source-git-commit: 554ced510600a4d5866e89806b058b5d2d9a3edf
workflow-type: ht
source-wordcount: '221'
ht-degree: 100%

---


# Événements personnalisés

*Cette page d’aide décrit le fonctionnement des événements personnalisés en tant que mesure. Pour plus d’informations sur le fonctionnement des événements personnalisés en tant que variable d’implémentation, consultez[Présentation des événements](/help/implement/vars/page-vars/events/events-overview.md)dans le guide d’utilisation de la mise en œuvre.*

Les mesures d’événements personnalisés indiquent le nombre d’accès pour lesquels un événement personnalisé donné a été défini dans une demande d’image. Ces mesures sont essentielles pour de nombreuses implémentations, car elles fournissent des informations sur les événements spécifiques à chaque organisation.

## Méthode de calcul de cette mesure

Les événements personnalisés sont calculés différemment selon leur type. Vous pouvez vérifier le type d’un événement sous [Événements de succès](../../admin/admin/c-success-events/success-event.md) dans les paramètres de la suite de rapports.

* **Événements de compteur** : le paramètre d’événement par défaut. La plupart des événements sont des événements de compteur. Tient compte du nombre d’accès pour lesquels l’événement personnalisé correspondant `event1` - `event1000` existe dans la variable [`events`](/help/implement/vars/page-vars/events/events-overview.md).
* **Événements numériques** : additionne la valeur numérique attribuée à l’événement dans la variable `events`.
* **Événements de devise** : applique une conversion de devise basée sur le taux de change du jour, puis additionne la valeur numérique attribuée à chaque accès dans la variable `events`.

Le nombre d’événements disponibles dépend du contrat Analytics de votre organisation. La plupart des organisations utilisant des contrats non hérités disposent de 1 000 événements personnalisés. Contactez le gestionnaire de compte de votre organisation si vous ne savez pas combien d’événements personnalisés vous sont accessibles.

Adobe recommande vivement d’enregistrer la manière dont vous utilisez chaque événement dans le [document de conception de solution](/help/implement/prepare/solution-design.md) de votre entreprise.
