---
title: Ordre de traitement des données dans Adobe Analytics
description: Découvrez l’ordre des composants et services qui traitent les données dans Adobe Analytics.
exl-id: a8dc9c12-07d3-4dc8-b2df-136f7a7a1e77
feature: Data Configuration and Collection
source-git-commit: 6c947812d4fd8bc2ee951a5933c6e3b6d8ca1a6b
workflow-type: tm+mt
source-wordcount: '1040'
ht-degree: 35%

---

# Ordre de traitement des données dans Adobe Analytics

Adobe offre de nombreuses façons de modifier ou de manipuler les données avant qu’elles n’apparaissent dans les rapports. Cette page indique l’ordre dans lequel différentes fonctionnalités d’Adobe Analytics traitent les données. Vous pouvez utiliser cette liste pour résoudre les incohérences entre les données ou déterminer la meilleure fonctionnalité à utiliser lorsque des ajustements des données sont nécessaires.

![Traitement de l’image de l’ordre](assets/processing-order.png)

## Données avant envoi à Adobe

Avant d’envoyer les données à Adobe, elles sont généralement compilées côté client à l’aide de l’une des méthodes suivantes :

* **AppMeasurement** : fichier JavaScript hébergé sur votre site et référencé sur chaque page. Les données sont envoyées directement à Adobe Analytics.
* **SDK Web Adobe Experience Platform** : fichier JavaScript hébergé sur votre site et référencé sur chaque page. Les données sont envoyées à Adobe Experience Platform Edge Network.
* **Balises dans la collecte de données Adobe Experience Platform** : fichier JavaScript référencé sur chaque page, contenant les règles créées dans l’interface utilisateur de la collecte de données. L’extension Adobe Analytics offre un moyen plus simple de mettre en œuvre AppMeasurement. L’extension SDK Web offre un moyen plus facile de mettre en œuvre le SDK Web.
* **API** : AppMeasurement et Edge Network offrent toutes deux des méthodes de programmation pour envoyer des données à Adobe. AppMeasurement propose l’[API Data Insertion](https://developer.adobe.com/analytics-apis/docs/1.4/guides/data-insertion/) et l’[API Bulk Data Insertion](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/) ; Edge Network propose l’[API Data Collection](https://developer.adobe.com/data-collection-apis/docs/).

Si vous envoyez des données à Edge Network, vous pouvez le configurer pour transférer des données à Adobe Analytics (ainsi qu’à de nombreuses autres solutions Adobe Experience Cloud). Quelle que soit la méthode d’implémentation, les données d’accès collectées arrivent finalement aux serveurs de traitement d’Adobe Analytics dans un format qu’elles peuvent analyser.

## Pré-traitement dans la collection Adobe Analytics

Lorsque les données arrivent à Adobe Analytics, elles entrent dans une phase de pré-traitement :

1. [**Variables dynamiques**](/help/implement/vars/page-vars/dynamic-variables.md) : si une variable dynamique est vue dans une partie d’une demande d’image, la valeur sera copiée et traitée comme une valeur indépendante à l’avenir.
1. [**obscurcissement d’IP (dernier octet)**](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md) : si votre suite de rapports est configurée pour obscurcir uniquement le dernier octet, cet obscurcissement s’applique ici. Notez que l’obscurcissement des adresses IP (suppression de l’adresse IP) se produit ultérieurement dans le pipeline de traitement.
1. **Tables de recherche** : dimensions qui reposent sur des tables de recherche interne Adobe (par exemple, la dimension [Navigateur](/help/components/dimensions/browser.md)) sont mises en correspondance avec la valeur associée.
1. [**Exclusion d’IP**](/help/admin/tools/exclude-ip.md) : toutes les adresses IP que vous excluez explicitement du compte rendu des performances sont marquées lors de cette étape.
1. [**Règles de robots**](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/bot-rules.md) : appliquez un filtrage de robots standard ou personnalisé pour exclure ces données des rapports.
1. **Données de géolocalisation** : les dimensions reposant sur la recherche d’adresses IP (par exemple, la dimension [Pays](/help/components/dimensions/countries.md)) sont renseignées.
1. [**Règles de traitement**](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md) : règles personnalisées appliquées à vos données par votre organisation. Inclut le mappage de [variables de données contextuelles](/help/implement/vars/page-vars/contextdata.md) à leurs variables Analytics respectives.
1. [**Règles VISTA**](vista.md) : règles flexibles personnalisées appliquées à vos données par un consultant Adobe. Les règles VISTA peuvent éventuellement s’exécuter avant ou après les règles de traitement, selon les besoins de votre entreprise. La plupart des règles VISTA s’exécutent généralement après les règles de traitement, mais chaque organisation est configurée différemment. Pour plus d’informations sur les règles VISTA existantes, contactez l’équipe chargée de votre compte Adobe.
1. **Conversion de devise** : si l’accès contient une [`currencyCode`](/help/implement/vars/config-vars/currencycode.md) différente de la devise de la suite de rapports, toutes les variables de devise applicables sont converties à l’aide du taux de change du jour en cours.
1. [**Code postal**](/help/components/dimensions/zip-code.md) : la dimension « Code postal » est renseignée en fonction des paramètres de la suite de rapports.

## Étape « Mid-value » du pipeline de collecte de données

Lorsque le prétraitement est terminé, plusieurs fonctionnalités utilisent cette forme de données partiellement traitées, connue sous le nom de « valeurs moyennes ». Avant que ces données ne soient envoyées n’importe où, un traitement spécifique aux valeurs moyennes est appliqué :

1. [**Règles de traitement des canaux marketing au niveau des accès**](/help/admin/tools/manage-rs/edit-settings/marketing-channels/mc-proc-rules.md) : ces règles de traitement sont spécifiquement exécutées pour le connecteur Source Analytics. Puisqu’il n’existe encore aucun contexte de niveau visite ou visiteur, ces règles de traitement supposent qu’un accès n’est pas le premier accès d’une visite. Les résultats de l’exécution des règles de traitement d’un accès sont disponibles dans `channel.typeAtSource` et `channel._id`.
1. [**obscurcissement d’adresse IP (supprimer l’adresse IP)**](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md) : si votre suite de rapports est configurée pour obscurcir complètement une adresse IP, cet obscurcissement s’applique ici (uniquement pour les valeurs moyennes).

À ce stade, les données de valeur moyenne sont envoyées à leur fonctionnalité respective :

* [**API Livestream**](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/livestream/) : connectez une application au service Livestream d’Adobe pour obtenir un flux de données au fur et à mesure de leur collecte.
* [**Connecteur Source Analytics**](https://experienceleague.adobe.com/fr/docs/experience-platform/sources/connectors/adobe-applications/analytics) : ingestion des données de suite de rapports Adobe Analytics dans un jeu de données Adobe Experience Platform.
* [**Rapports en temps réel**](/help/components/c-real-time-reporting/realtime.md) : fournit jusqu’à trois rapports en temps réel configurables dans Analysis Workspace.

## Traitement au niveau des visites et des visiteurs

Jusqu’à présent, un accès donné n’a aucune connaissance ni aucun contexte des accès collectés avant ou après lui. Cette étape du traitement renseigne les champs de niveau visite et visiteur.

1. [**Visite + définition du visiteur**](/help/implement/id/overview.md) : l’accès est identifié en fonction des variables de visiteur qu’il contient.
1. [**Nombre de visites**](/help/components/dimensions/visit-number.md) : le nombre de visites est calculé en fonction des autres visites du visiteur identifié.
1. **Déduplication des événements** : si l’accès contient un [`purchaseID`](/help/implement/vars/page-vars/purchaseid.md) en double ou [sérialisation des événements](/help/implement/vars/page-vars/events/event-serialization.md), ces identifiants sont vérifiés et marqués respectivement.
1. [**Règles de traitement des canaux marketing au niveau des visites**](/help/admin/tools/manage-rs/edit-settings/marketing-channels/mc-proc-rules.md) : chaque accès s’exécute dans les règles de traitement des canaux marketing et les détails de son canal + de son canal sont déterminés si l’accès correspond à une règle. Ces règles renseignent les dimensions [Canal marketing](/help/components/dimensions/marketing-channel.md) et [Détails du canal marketing](/help/components/dimensions/marketing-detail.md) disponibles dans Analysis Workspace.
1. **Persistance des variables** : pour les dimensions ayant une persistance (telles que [eVars](/help/components/dimensions/evar.md)), cette valeur est déterminée à cette étape. En règle générale, la plupart des valeurs `post` sont définies ici.
1. **ID de transaction** : si l’accès contient une nouvelle valeur de [`transactionID`](/help/implement/vars/page-vars/transactionid.md), un « instantané » de toutes les valeurs prises en charge est stocké. Lorsqu’un chargement de source de données contient un ID de transaction correspondant, toutes les valeurs prises en charge à partir de cet instantané sont incluses dans cette ligne de source de données.
1. [**obscurcissement d’adresse IP (supprimer l’adresse IP)**](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md) : si votre suite de rapports est configurée pour obscurcir complètement une adresse IP, cet obscurcissement s’applique ici une fois tous les autres traitements terminés.

À ce stade, l’accès individuel est enregistré dans les tableaux de données de la suite de rapports. Après l’intervalle de [Latence](latency.md) standard, il est disponible dans les rapports.

## Modification des données après leur traitement

Les données dans Adobe Analytics sont pour la plupart permanentes. Cependant, certaines fonctionnalités permettent d’ajuster ou de supprimer des données sélectives 

* [**API de réparation des données**](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/data-repair/) : modifiez certaines colonnes ou supprimez les lignes de données de votre choix.
* [**Gouvernance des données**](/help/technotes/privacy/privacy-overview.md) : accédez aux demandes de confidentialité pour supprimer définitivement des données.
* [**Classifications**](/help/components/classifications/classifications-overview.md) : créez des dimensions d’après des règles ou des données téléchargées qui vous permettent d’organiser les données différemment. Les données sous-jacentes de la suite de rapports ne sont pas modifiées. Vous pouvez donc modifier ou remplacer librement les données de classification.
* [**Suites de rapports virtuelles**](/help/components/vrs/vrs-about.md) : créez une autre vue de suite de rapports qui peut modifier le délai d’expiration de la visite.
