---
title: Graphique du périphérique
description: Comprendre les conditions préalables et les limites de l’assemblage de données à l’aide du graphique de périphérique.
translation-type: tm+mt
source-git-commit: eb2bee26dd58dcff13b4ddf41c6f6ab337d8d374
workflow-type: tm+mt
source-wordcount: '430'
ht-degree: 41%

---


# Graphique du périphérique

L’Analytics sur plusieurs périphériques fournit deux méthodes distinctes pour assembler les données. Cette méthode utilise le graphique coopératif Adobe Experience Platform Identity Service ou le graphique privé pour assembler les données. CDA communique régulièrement avec le graphique de l&#39;appareil pour relier les appareils.

## Différences entre graphique coopératif et graphique privé

Adobe offre deux types de graphiques de périphériques dans le cadre du service d’ID :

* **Graphique** coopératif : Référentiel des ID de périphérique hachés auquel tout client peut contribuer et référencer. Comme ce type de graphique de périphérique est collaboratif, il correspond généralement à plus de périphériques qu’un graphique privé.
* **Graphique** privé : Référentiel des ID de périphérique hachés auxquels seule votre organisation fait référence.

## Conditions préalables spécifiques au graphique du périphérique

Si vous prévoyez d’implémenter l’Analytics sur plusieurs périphériques à l’aide de la méthode de graphique de périphérique, les éléments suivants sont requis. Collaborez avec les équipes de votre entreprise et votre gestionnaire de compte Adobe pour vous assurer que vous remplissez toutes les conditions suivantes.

>[!IMPORTANT] Si vous ne remplissez pas toutes les conditions préalables requises, vous risquez de ne pas pouvoir activer les analyses entre appareils ou de ne pas obtenir de résultats satisfaisants lors du regroupement de données.

* Toutes les conditions préalables sont répertoriées dans la page [](overview.md)d’aperçu.
* Votre entreprise doit utiliser le graphique Co-op ou Privé du service d’identité d’Adobe Experience Platform. Consultez la [page d’accueil](https://docs.adobe.com/content/help/fr-FR/device-co-op/using/home.html) du guide de l’utilisateur Device Co-op.
* Votre mise en oeuvre doit utiliser la dernière version du service d’identification des Experience Cloud. Consultez la [page d’accueil](https://docs.adobe.com/content/help/fr-FR/id-service/using/home.html) du guide de l’utilisateur du service d’identité d’Experience Cloud. La plupart des implémentations utilisant Adobe Experience Platform Launch disposent déjà probablement d’un ECID déployé.
* Your implementation must call the `setCustomerIDs` function (or SDK equivalent) whenever an individual can be identified, such as when a user logs in or opens an email. Cette exigence s’applique à toutes les plates-formes, y compris les applications mobiles si elles sont utilisées. Voir [`setCustomerIDs`](https://docs.adobe.com/content/help/fr-FR/id-service/using/id-service-api/methods/setcustomerids.html) dans le guide de l’utilisateur du service d’identité d’Experience Cloud.

## Limites spécifiques au graphique du périphérique

* Les identifiants Analytics hérités ne sont pas pris en charge. Seuls les visiteurs avec un Experience Cloud ID sont regroupés.
* Si votre entreprise utilise un graphique privé, les nouveaux périphériques peuvent prendre jusqu’à 24 heures pour être assemblés.
* Si votre organisation utilise le graphique Co-op, les nouveaux périphériques qui visitent votre site peuvent prendre jusqu&#39;à deux semaines pour être assemblés. Le niveau de groupement dans les analyses entre appareils pour les deux dernières semaines est généralement inférieur à celui des plages de dates datant de plus de deux semaines.
* Les graphiques d’appareils tiers ne sont pas pris en charge.

## Étapes suivantes

Once your organization meets all requirements met and understands the limitations, you can start [Setting up Cross-Device Analytics](setup.md).

