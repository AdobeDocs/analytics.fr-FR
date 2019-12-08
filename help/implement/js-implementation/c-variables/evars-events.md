---
description: 'Si vous souhaitez effectuer le suivi d’informations supplémentaires, mais que vous ne disposez pas de suffisamment de variables pour ce faire, vous avez désormais accès à d’autres eVars et événements de réussite. '
keywords: Analytics Implementation;evars;events;evars number;how many evars;how many events
title: eVars et événements supplémentaires
topic: Developer and implementation
uuid: 6f53069b-6941-40f1-9db6-2d1839822b8f
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# eVars et événements supplémentaires

Si vous souhaitez effectuer le suivi d’informations supplémentaires, mais que vous ne disposez pas de suffisamment de variables pour ce faire, vous avez désormais accès à d’autres eVars et événements de réussite :

> [!NOTE] Le code H JavaScript ne prend pas en charge ces eVars et événements supplémentaires.

## Droits en matière de dimensions et d’événements personnalisés {#section_869EC3D8A5614036A9C586F2B74FA7DC}

| Produit Adobe Analytics |  |  |  |
|---|---|---|---|
| Adobe Analytics – Foundation | 75 propriétés | 200 eVars | 1 000 événements |
| Adobe Analytics – [Select](https://www.adobe.com/data-analytics-cloud/analytics/select.html) | 75 propriétés | 200 eVars | 1 000 événements |
| Adobe Analytics – [Prime](https://www.adobe.com/data-analytics-cloud/analytics/prime.html) | 75 propriétés | 200 eVars | 1 000 événements |
| Adobe Analytics – [Ultimate](https://www.adobe.com/data-analytics-cloud/analytics/ultimate.html) | 75 propriétés | 250 eVars | 1 000 événements |

## Spécification des variables et événements {#section_DEA51A22BCBB4B92BDD25814AAD296E4}

* Si vous utilisez ces versions d’[!DNL AppMeasurement], les variables peuvent être renseignées dans la bibliothèque de collection des données :

   * AppMeasurement pour JavaScript version 1.4+
   * AppMeasurement pour Flash version 3.9+
   * AppMeasurement pour Java version 1.2.8+
   * AppMeasurement pour Silverlight/.NET version 1.4.2+
   * AppMeasurement pour PHP version 1.2.2+

* Si vous exécutez une version antérieure du code, ou JavaScript H.*, vous pouvez renseigner les données contextuelles et utiliser des règles de traitement pour renseigner les variables.
* Toutes les versions de code de collection de données peuvent renseigner les événements 101 à 1 000.
* Les règles de traitement peuvent être utilisées pour renseigner les eVars 76 à 250 d’après les données contextuelles ou d’autres variables.

## Questions fréquentes {#section_E915B03236BD47DCA065F1FC5A6E30C6}

* **Toutes les interfaces Adobe Analytics auront-elles un accès immédiat à ces nouvelles variables ?** Les interfaces suivantes ont un accès immédiat : [!UICONTROL Analysis Workspace], [!UICONTROL Reports &amp; Analytics], [!UICONTROL Report Builder], [!UICONTROL Ad Hoc Analysis], API et [!UICONTROL Data Workbench].

* **Ces eVars et événements supplémentaires s’afficheront-ils automatiquement dans mes flux de données ?** Les flux de données auront accès aux nouvelles variables et aux nouveaux événements une fois qu’ils seront activés. Les nouvelles colonnes d’eVars n’apparaîtront pas tant que vous n’aurez pas choisi de les inclure. Toutefois, les nouveaux événements s’affichent dans la colonne event_list dès qu’ils sont activés et la table de recherche des événements contient les noms d’événement de ces ID d’événement. N’activez pas les nouveaux événements si vous n’êtes pas prêt à les consommer dans les flux de données.

* **Comment demander de nouvelles colonnes de flux de données ?** Pour demander de nouvelles colonnes, reportez-vous à la section [Configuration des flux de données](https://marketing.adobe.com/resources/help/en_US/sc/clickstream/datafeeds_configure.html).

* **Comment procéder si je suis actuellement un client Analytics Ultimate, mais que je souhaite revenir à Analytics Prime alors que j’ai actuellement 200 eVars activées ?** Adobe ne désactivera pas vos eVars existantes, mais vous ne pourrez pas en activer davantage. Si vous désactivez des eVars, vous ne pouvez pas les réactiver tant que vous dépassez la limite d’Analytics Prime de 200 eVars activées.

