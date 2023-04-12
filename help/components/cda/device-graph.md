---
title: Graphique d’appareil
description: Découvrez les conditions préalables et les limites du regroupement de données à l’aide du graphique d’appareil.
exl-id: b8408a7d-6aff-4fff-b535-f10d422bcf0d
source-git-commit: 34ba0e09cd909951a777b0ad3da080958633f97e
workflow-type: tm+mt
source-wordcount: '321'
ht-degree: 62%

---

# Graphique d’appareil

Les analyses entre appareils peuvent utiliser le graphique privé pour regrouper les données. Le graphique privé est un référentiel d’identifiants d’appareils hachés propres à votre entreprise. Les analyses entre appareils communiquent régulièrement avec le graphique d’appareil pour relier les appareils.

## Conditions préalables spécifiques au graphique d’appareil

Si vous avez l’intention de mettre en œuvre des analyses entre appareils à l’aide de la méthode de graphique d’appareil, les conditions suivantes doivent être remplies. Collaborez avec les équipes de votre entreprise et votre équipe de compte d’Adobe pour vous assurer que vous remplissez toutes les conditions suivantes.

>[!WARNING]
>
>Si vous ne remplissez pas toutes les conditions préalables requises, vous risquez de ne pas pouvoir activer les analyses entre appareils ou de ne pas obtenir de résultats satisfaisants lors du regroupement de données.

* Toutes les conditions préalables sont répertoriées dans la [page d’aperçu](overview.md).
* Votre entreprise doit utiliser la variable [Graphique privé du service Adobe Experience Platform Identity](https://business.adobe.com/products/experience-platform/identity-service.html). Voir aussi [Page d’accueil](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=fr) dans le guide d’utilisation d’Identity Service.
* Votre mise en oeuvre doit utiliser la dernière version du service d’ID Experience Cloud (ECID). Voir [Page d’accueil](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=fr) dans le guide d’utilisation du service d’ID. La plupart des mises en oeuvre qui utilisent [Balises](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=fr) dans Adobe Experience Platform, le service d’ID est probablement déjà déployé.
* Votre implémentation doit appeler la fonction `setCustomerIDs` (ou SDK équivalent) chaque fois qu’une personne peut être identifiée, par exemple lorsqu’un utilisateur se connecte ou ouvre un courrier électronique. Cette exigence s’applique à toutes les plates-formes, y compris les applications mobiles si elles sont utilisées. Voir [`setCustomerIDs`](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/methods/setcustomerids.html?lang=fr) dans le guide d’utilisation du service d’ID.

## Limites spécifiques au graphique d’appareil

* Les identifiants Analytics hérités ne sont pas pris en charge. Seuls les visiteurs avec un Experience Cloud ID sont regroupés.
* Si votre entreprise utilise un graphique Privé, les nouveaux appareils peuvent mettre jusqu’à 24 heures pour être regroupés.
* Les graphiques d’appareils tiers ne sont pas pris en charge.

## Étapes suivantes

Une fois que toutes les conditions requises sont remplies et que vous avez compris les limites, vous pouvez commencer à [configurer les analyses entre appareils](setup.md).
