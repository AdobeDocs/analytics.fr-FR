---
description: Les catégories de sources de données identifient différents types de sources de données ayant une fonctionnalité similaire.
subtopic: Data sources
title: Types et catégories de données - Aperçu
topic-fix: Developer and implementation
uuid: b5004cdc-b68a-4a82-a159-a7cd7b8bfe21
exl-id: d459fd06-a0fe-49e6-8624-b42f0c60ee6e
source-git-commit: 0b31585f5a928d68083764b80f3a08927b407387
workflow-type: ht
source-wordcount: '903'
ht-degree: 100%

---

# Types et catégories de données - Aperçu

Les catégories de sources de données identifient différents types de sources de données ayant une fonctionnalité similaire.

Les catégories permettent de grouper les sources de données du point de vue de l’utilisateur. Lors de la création d’une source de données au moyen de l’interface utilisateur [!DNL Data Sources], sélectionnez tout d’abord une catégorie de source de données, puis un type spécifique de source de données. Chaque catégorie contient des types de sources de données compatibles avec des types de données similaires. [!DNL Data Sources] fournit les catégories de sources de données suivantes :

## Utilisation du site Web {#web-usage}

| Source de données | Type de traitement | Description |
| --- | --- | --- |
| [!UICONTROL Fichiers journaux du serveur Web] | [Journal Web](/help/import/c-data-sources/c-datasrc-types/datasrc-web-log.md) | La plupart des serveurs Web génèrent des fichiers journaux qui enregistrent chaque page présentée. A l’aide de cette source de données, vous pouvez traiter les fichiers journaux à partir des données de la plupart des serveurs Web et les ajouter à vos rapports. |
| [!UICONTROL Téléchargement massif dans Advertising Cloud] | [Conversion](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Permet des téléchargements massifs manuels et automatisés par Excel dans [!DNL Advertising Cloud]. |
| [!UICONTROL Source de données de trafic au niveau du site] | [Trafic](/help/import/c-data-sources/c-datasrc-types/datasrc-traffic.md) | Importe des données de trafic pour l’ensemble du site Web. [!UICONTROL Pages vues], par exemple. |
| [!UICONTROL Source de données de trafic pour ventilation] | [Trafic](/help/import/c-data-sources/c-datasrc-types/datasrc-traffic.md) | Importe les données de trafic ventilées par une autre variable de site Web. Par exemple : [!UICONTROL Pages vues] ventilées par [!UICONTROL produit]. |

## Campagnes publicitaires {#ad-campaigns}

| Source de données | Type de traitement | Description |
| --- | --- | --- |
| [!UICONTROL Serveur de publicités génériques] | [Conversion](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Vous permet d’intégrer des impressions et d’autres mesures de premier plan relatives aux activités de votre serveur d’annonces publicitaires dans les rapports marketing. Il s’agit de la source de données du serveur d’annonces générique qui doit être utilisée si votre serveur d’annonces spécifique n’est pas pris en charge. |
| [!UICONTROL Serveur générique de campagnes par e-mail] | [Conversion](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Vous permet d’intégrer des mesures à partir de votre serveur de campagne par e-mail dans les rapports marketing.  Les mesures couramment intégrées sont, par exemple, le nombre de messages envoyés, de messages distribués et de messages lus. Il s’agit de la source de données de campagnes par messagerie électronique générique qui doit être utilisée si votre serveur de campagnes par messagerie électronique spécifique n’est pas pris en charge. |
| [!UICONTROL Service de paiement par clic générique] | [Conversion](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Vous permet d’importer les données concernant vos performances de paiement par clic, y compris les impressions, les clics et les coûts.  Il s’agit de la source de données de paiement par clic générique qui doit être utilisée si votre service de paiement par clic spécifique n’est pas pris en charge. |

## Gestion des relations client {#crm}

| Source de données | Type de traitement | Description |
| --- | --- | --- |
| [!UICONTROL Centre d’appels générique] | [Conversion](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Vous permet d’intégrer des informations relatives à votre centre d’appels dans les rapports marketing. Les mesures généralement importées incluent le nombre d’appels, le temps passé au téléphone, l’agent et le nombre total des ventes.  Il s’agit de la source de données de centre d’appels générique qui doit être utilisée si votre logiciel de centre d’appels spécifique n’est pas pris en charge. |
| [!UICONTROL Application générique du Service clientèle] | [Conversion](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Vous permet d’intégrer des informations issues des logiciels du Service clientèle dans les rapports marketing. Elle propose des mesures telles que le nombre de nouveaux incidents, le nombre d’incidents résolus et le temps consacré à la résolution d’incidents.  Il s’agit de la source de données d’assistance à la clientèle générique qui doit être utilisée si votre application spécifique n’est pas prise en charge. |

## Satisfaction de la clientèle {#csat}

| Source de données | Type de traitement | Description |
| --- | --- | --- |
| [!UICONTROL Données d’enquête générique] | [Conversion](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Vous permet d’intégrer dans les rapports marketing les résultats de l’enquête provenant d’un outil tiers affichant le degré de satisfaction générale de votre clientèle quant à son interaction avec votre site.  Il s’agit de la source de données d’enquête générique qui doit être utilisée si votre service d’enquête spécifique n’est pas pris en charge. |

## Performances du site {#performance}

| Source de données | Type de traitement | Description |
| --- | --- | --- |
| [!UICONTROL Vitesse générique de téléchargement du site] | [Conversion](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Vous permet d’intégrer vos données à partir d’une application ou d’un service qui contrôle la vitesse de téléchargement de vos données. Il s’agit de la source de données de vitesse de téléchargement générique qui doit être utilisée si votre logiciel ou service spécifique n’est pas pris en charge. |

## Générique {#generic}

| Source de données | Type de traitement | Description |
| --- | --- | --- |
| [!UICONTROL Source de données générique (données récapitulatives uniquement)] | [Conversion](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Utilisez cette source de données lorsqu’aucune correspondance n’est plus proche pour le type de données à importer dans les rapports et analyses marketing. |
| [!UICONTROL Source de données générique (traitement complet)] | Traitement complet | Adobe a mis fin à l’utilisation des sources de données à traitement complet le 31 juillet 2022. [En savoir plus](/help/import/c-data-sources/c-datasrc-types/datasrc-fullproc-eol.md). Adobe recommande d’utiliser putôt l’[API Bulk Data Insertion (BDIA)](https://www.adobe.io/apis/experiencecloud/analytics/docs.html?lang=fr). |
| [!UICONTROL Source de données générique (ID de transaction)] | <ul><li>ID de transaction</li><li>Identifiant visiteur</li></ul> | Vous permet de lier n’importe quel événement hors ligne à un événement en ligne. L’[!UICONTROL ID de transaction] agit comme une clé entre les événements hors ligne et ceux en ligne. |

## Achats en ligne {#purchases}

| Source de données | Type de traitement | Description |
| --- | --- | --- |
| [!UICONTROL Retours de produits] | [Conversion](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Vous permet d’importer des données sur le retour de produits pour les associer à un ID d’achat afin que vous puissiez identifier les moteurs de recherche, les mots-clés, les campagnes et autres attributs plus susceptibles de générer des retours. |
| [!UICONTROL Coût du produit] | [Conversion](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Vous permet d’indiquer le coût réel des produits achetés et expédiés à partir de votre site Web en associant le coût ou la valeur à des produits individuels afin que vous puissiez créer des rapports précis sur les campagnes, les mots-clés et les promotions internes les plus rentables pour votre site Web. |
| [!UICONTROL Statut de la commande] | [Conversion](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Vous permet d’utiliser des mesures qui permettent d’identifier le statut de chaque commande passée, y compris celles annulées, expédiées, clôturées ou supposées frauduleuses. Les rapports d’état de la commande peuvent identifier les méthodes d’acquisition qui génèrent le taux d’achèvement le plus élevé. |

## Prospects et devis {#leads}

| Source de données | Type de traitement | Description |
| --- | --- | --- |
| [!UICONTROL Génération de piste] | [Conversion](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Vous permet de transférer des informations sur les résultats des pistes pour chaque piste générée sur votre site Web, y compris le revenu réel généré.  Après l&#39;attribution précise du revenu aux ID de pistes, vous pouvez identifier vos campagnes et promotions les plus rentables. |
| [!UICONTROL Devis en ligne] | [Conversion](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Vous permet de transférer des informations sur les résultats des pistes pour chaque piste générée sur votre site Web, y compris le revenu réel généré.  Après l&#39;attribution précise du revenu aux ID de pistes, vous pouvez identifier vos campagnes et promotions les plus rentables. |
| [!UICONTROL Données du centre d’appels] | [Conversion](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Vous permet de transférer les transactions du centre d’appels afin que vous puissiez identifier les tactiques (campagnes, promotions, etc.) qui incitent les clients à décrocher leur téléphone. |
