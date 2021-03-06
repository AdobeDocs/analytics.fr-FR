---
title: Graphique d’appareil
description: Découvrez les conditions préalables et les limites du regroupement de données à l’aide du graphique d’appareil.
exl-id: b8408a7d-6aff-4fff-b535-f10d422bcf0d
source-git-commit: 3f4d8df911c076a5ea41e7295038c0625a4d7c85
workflow-type: tm+mt
source-wordcount: '425'
ht-degree: 100%

---

# Graphique d’appareil

Analytics sur l’ensemble des appareils offre deux méthodes distinctes pour regrouper les données. Cette méthode utilise le graphique Privé ou le graphique Co-op d’Adobe Experience Platform Identity Service pour regrouper les données. Les analyses entre appareils communiquent régulièrement avec le graphique d’appareil pour relier les appareils.

## Différences entre le graphique Co-op et le graphique Privé

Adobe offre deux types de graphiques d’appareil dans le cadre du service d’ID :

* **Graphique Co-op** : un référentiel d’ID d’appareils hachés auquel tout client peut contribuer et qu’il peut référencer. Comme ce type de graphique d’appareil est collaboratif, il correspond généralement à plus d’appareils qu’un graphique privé.
* **Graphique Privé** : un référentiel d’ID d’appareils hachés auquel seule votre entreprise fait référence.

## Conditions préalables spécifiques au graphique d’appareil

Si vous avez l’intention de mettre en œuvre des analyses entre appareils à l’aide de la méthode de graphique d’appareil, les conditions suivantes doivent être remplies. Collaborez avec les équipes de votre entreprise et votre gestionnaire de compte Adobe pour vous assurer que vous remplissez toutes les conditions suivantes.

>[!WARNING]
>
>Si vous ne remplissez pas toutes les conditions préalables requises, vous risquez de ne pas pouvoir activer les analyses entre appareils ou de ne pas obtenir de résultats satisfaisants lors du regroupement de données.

* Toutes les conditions préalables sont répertoriées dans la [page d’aperçu](overview.md).
* Votre entreprise doit utiliser le graphique Co-op ou Privé du service d’identité d’Adobe Experience Platform. Consultez la [page d’accueil](https://experienceleague.adobe.com/docs/device-co-op/using/home.html?lang=fr) du guide de l’utilisateur Device Co-op.
* Votre mise en œuvre doit utiliser la dernière version du service Experience Cloud ID. Consultez la [page d’accueil](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=fr) du guide de l’utilisateur du service d’identité d’Experience Cloud. La plupart des implémentations utilisant des balises dans Adobe Experience Platform disposent probablement déjà d’un ECID déployé.
* Votre implémentation doit appeler la fonction `setCustomerIDs` (ou SDK équivalent) chaque fois qu’une personne peut être identifiée, par exemple lorsqu’un utilisateur se connecte ou ouvre un courrier électronique. Cette exigence s’applique à toutes les plates-formes, y compris les applications mobiles si elles sont utilisées. Voir [`setCustomerIDs`](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/methods/setcustomerids.html?lang=fr) dans le guide de l’utilisateur du service d’identité d’Experience Cloud.

## Limites spécifiques au graphique d’appareil

* Les identifiants Analytics hérités ne sont pas pris en charge. Seuls les visiteurs avec un Experience Cloud ID sont regroupés.
* Si votre entreprise utilise un graphique Privé, les nouveaux appareils peuvent mettre jusqu’à 24 heures pour être regroupés.
* Si votre entreprise utilise le graphique Co-op, les nouveaux appareils qui visitent le site peuvent prendre jusqu’à deux semaines pour être regroupés. Le niveau de groupement dans les analyses entre appareils pour les deux dernières semaines est généralement inférieur à celui des périodes datant de plus de deux semaines.
* Les graphiques d’appareils tiers ne sont pas pris en charge.

## Étapes suivantes

Une fois que toutes les conditions requises sont remplies et que vous avez compris les limites, vous pouvez commencer à [configurer les analyses entre appareils](setup.md).
