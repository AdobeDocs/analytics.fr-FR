---
title: Ordre de traitement des données dans Adobe Analytics
description: Découvrez l’ordre des composants et services qui traitent les données dans Adobe Analytics.
source-git-commit: 0881efeb2ce4f7af96f42bc925e43ce5ba1f64a2
workflow-type: tm+mt
source-wordcount: '588'
ht-degree: 0%

---

# Ordre de traitement des données dans Adobe Analytics

Adobe offre de nombreuses façons de modifier ou de manipuler les données avant qu’elles n’apparaissent dans les rapports. Cette page affiche l’ordre dans lequel les différentes fonctionnalités d’Adobe Analytics traitent les données. Vous pouvez utiliser cette liste pour résoudre les incohérences entre les données ou déterminer la meilleure fonctionnalité à utiliser lorsque des ajustements des données sont nécessaires.

![Ordre de traitement](assets/processing-order.png)

## Données avant envoi à Adobe

Avant d’envoyer les données à Adobe, elles sont généralement compilées côté client à l’aide de l’une des méthodes suivantes :

* **AppMeasurement**: Fichier JavaScript hébergé sur votre site et référencé sur chaque page. Les données sont envoyées directement à Adobe Analytics.
* **SDK Web Adobe Experience Platform**: Fichier JavaScript hébergé sur votre site et référencé sur chaque page. Les données sont envoyées à Adobe Experience Edge.
* **Balises dans la collecte de données Adobe Experience Cloud**: Fichier JavaScript référencé sur chaque page, contenant les règles créées dans l’interface utilisateur de collecte de données. L’extension Adobe Analytics offre un moyen plus facile de mettre en oeuvre AppMeasurement. L’extension SDK Web offre un moyen plus facile de mettre en oeuvre le SDK Web.

Si vous envoyez des données à Adobe Experience Edge, vous pouvez les configurer pour transférer des données à Adobe Analytics (ainsi que de nombreuses autres solutions Adobe Experience Cloud). Quelle que soit la méthode de mise en oeuvre, une demande d’image contenant les variables souhaitées est finalement envoyée aux serveurs de collecte de données d’Adobe.

## Données en arrivant aux serveurs de collecte de données Adobe Analytics

Une fois les données envoyées à Adobe Analytics, les fonctionnalités suivantes ajustent les données selon les besoins :

1. **Tables de recherche**: Dimensions qui reposent sur des tables de recherche interne par Adobe (par exemple, [Navigateur](/help/components/dimensions/browser.md) ) correspond à sa valeur correspondante.
2. [**Variables dynamiques**](/help/implement/vars/page-vars/dynamic-variables.md): Si une variable dynamique est vue dans une partie d’une demande d’image, la valeur est copiée et traitée comme une valeur indépendante à l’avenir.
3. [**Règles de robots**](/help/admin/admin/bot-removal/bot-rules.md): Appliquez un filtrage de robots standard ou personnalisé pour exclure ces données des rapports.
4. [**Règles de traitement**](/help/admin/admin/c-processing-rules/processing-rules.md): Règles personnalisées appliquées à vos données par votre organisation. Inclut le mappage de [Variables de données contextuelles](/help/implement/vars/page-vars/contextdata.md) à sa variable respective.
5. **Règles VISTA**: Règles flexibles personnalisées appliquées à vos données par un consultant Adobe. Les règles VISTA peuvent éventuellement s’exécuter avant ou après les règles de traitement, selon les besoins de votre entreprise. La plupart des règles VISTA s’exécutent généralement après les règles de traitement, mais chaque organisation est configurée différemment. Pour plus d’informations sur les règles VISTA existantes, contactez votre gestionnaire de compte d’Adobe.
6. [**Règles de traitement des canaux marketing**](/help/components/c-marketing-channels/c-rules.md): Vous pouvez utiliser [Règles de traitement](/help/admin/admin/c-processing-rules/processing-rules.md) pour préparer les données à utiliser dans les règles de traitement des canaux marketing.
7. **Données de géolocalisation**: Dimensions qui reposent sur la recherche d’adresses IP (par exemple, la variable [Pays](/help/components/dimensions/countries.md) ) sont renseignées.
8. [**Obscurcissement d’IP**](/help/admin/admin/general-acct-settings-admin.md): Si votre entreprise a choisi d’obscurcir les adresses IP dans les données brutes, cela se fait une fois toutes les autres fonctions de traitement terminées.

À ce stade, l’accès individuel est enregistré dans les tableaux de données de la suite de rapports. Après la norme [latence](latency.md) est disponible dans les rapports.

## Modification des données après leur traitement

Les données dans Adobe Analytics sont pour la plupart permanentes ; cependant, certaines fonctionnalités permettent d’ajuster ou de supprimer des données sélectives :

* [**API de réparation des données**](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/data-repair/): Modifiez certaines colonnes ou supprimez les lignes de données de votre choix.
* [**Gouvernance des données**](/help/admin/c-data-governance/an-gdpr-workflow.md): Acceptez les demandes d’accès à des informations personnelles pour supprimer définitivement les données.
* [**Classifications**](/help/components/classifications/c-classifications.md): Créez des dimensions d’après des règles ou des données téléchargées qui vous permettent d’organiser les données différemment. Les données de la suite de rapports sous-jacente ne sont pas modifiées. Vous pouvez donc modifier ou remplacer librement les données de classification.
* [**Suites de rapports virtuelles**](/help/components/vrs/vrs-about.md): Créez une autre vue de suite de rapports qui peut modifier le délai d’expiration de la visite ou autoriser [Analyses entre appareils](/help/components/cda/overview.md).
