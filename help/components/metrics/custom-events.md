---
title: Événements personnalisés
description: Nombre d’accès pour lesquels un événement personnalisé existe.
translation-type: tm+mt
source-git-commit: 554ced510600a4d5866e89806b058b5d2d9a3edf
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 19%

---


# Événements personnalisés

*Cette page d’aide décrit le fonctionnement des événements personnalisés en tant que mesure. Pour plus d’informations sur le fonctionnement des événements personnalisés en tant que variable d’implémentation, voir Présentation[des](/help/implement/vars/page-vars/events/events-overview.md)Événements dans le guide de l’utilisateur Mise en oeuvre.*

Les mesures de événement personnalisé indiquent le nombre d’accès pour lesquels un événement personnalisé donné a été défini dans une demande d’image. Ces mesures sont vitales pour de nombreuses implémentations, car elles fournissent des informations sur les événements spécifiques à chaque organisation.

## Méthode de calcul de cette mesure

Les événements personnalisés sont calculés différemment selon leur type. Vous pouvez vérifier un type de événement sous événements [de](../../admin/admin/c-success-events/success-event.md) réussite dans les paramètres de la suite de rapports.

* **événements** de compteur : Paramètre de événement par défaut. La plupart des événements sont des événements de compteur. Compte le nombre d’accès pour lesquels le événement personnalisé correspondant `event1` - `event1000` existe dans la [`events`](/help/implement/vars/page-vars/events/events-overview.md) variable.
* **événements** numériques : Indique la valeur numérique affectée au événement dans la `events` variable.
* **événements** de devise : Applique la conversion de devise au taux de change de ce jour, puis additionne la valeur numérique affectée à chaque accès dans la `events` variable.

Le nombre d’événements disponibles dépend du contrat Analytics de votre organisation. La plupart des organisations utilisant des contrats non hérités disposent de 1 000 événements personnalisés. Contactez le gestionnaire de compte de votre organisation si vous ne savez pas combien d’événements personnalisés vous sont accessibles.

Adobe recommande vivement d’enregistrer la manière dont vous utilisez chaque événement dans le document [de conception de](/help/implement/prepare/solution-design.md)solution de votre entreprise.
