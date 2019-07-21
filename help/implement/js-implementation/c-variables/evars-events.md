---
description: 'Si vous souhaitez effectuer le suivi d''autres informations, mais ne disposez pas de suffisamment de variables, vous avez maintenant accès à d''autres evars et événements de réussite. '
keywords: Implémentation d'Analytics ; evars ; events ; evars number ; nombre d'evars ; nombre d'événements
seo-description: 'Si vous souhaitez effectuer le suivi d''autres informations, mais ne disposez pas de suffisamment de variables, vous avez maintenant accès à d''autres evars et événements de réussite. '
seo-title: Evars et événements supplémentaires
solution: Analytics
title: Evars et événements supplémentaires
topic: Développeur et mise en œuvre
uuid: 6 f 53069 b -6941-40 f 1-9 db 6-2 d 1839822 b 8 f
translation-type: tm+mt
source-git-commit: 76d0ce11d9b560e0df866be9e753804b6fa4bb3d

---


# Evars et événements supplémentaires

Si vous souhaitez effectuer le suivi d’autres informations, alors que vous n’avez pas suffisamment de variables, vous avez maintenant accès à d’autres eVar et événements de succès :

>[!NOTE]
>
>Le code H JavaScript ne prend pas en charge ces evars et événements supplémentaires.

## Droits en matière de dimensions et d’événements personnalisés {#section_869EC3D8A5614036A9C586F2B74FA7DC}

| Produit Adobe Analytics |  |  |  |
|---|---|---|---|
| Adobe Analytics – Foundation | 75 propriétés | 200 eVars | 1 000 événements |
| Adobe Analytics – [Select](https://www.adobe.com/data-analytics-cloud/analytics/select.html) | 75 propriétés | 200 eVars | 1 000 événements |
| Adobe Analytics – [Prime](https://www.adobe.com/data-analytics-cloud/analytics/prime.html) | 75 propriétés | 200 eVars | 1 000 événements |
| Adobe Analytics – [Ultimate](https://www.adobe.com/data-analytics-cloud/analytics/ultimate.html) | 75 propriétés | 250 eVars | 1 000 événements |

## Spécification des variables et événements {#section_DEA51A22BCBB4B92BDD25814AAD296E4}

* Variables can be populated in the data collection library if you are using these versions of [!DNL AppMeasurement]:

   * AppMeasurement pour JavaScript version 1.4+
   * AppMeasurement pour Flash version 3.9+
   * AppMeasurement pour Java version 1.2.8+
   * AppMeasurement pour Silverlight/.NET version 1.4.2+
   * AppMeasurement pour PHP version 1.2.2+

* Si vous exécutez une version antérieure du code, ou JavaScript H.*, vous pouvez renseigner les données contextuelles et utiliser des règles de traitement pour renseigner les variables.
* Toutes les versions de code de collection de données peuvent renseigner les événements 101 à 1 000.
* Les règles de traitement peuvent être utilisées pour renseigner les eVars 76 à 250 d’après les données contextuelles ou d’autres variables.

## Questions fréquentes {#section_E915B03236BD47DCA065F1FC5A6E30C6}

* **Toutes les interfaces Adobe Analytics auront-elles un accès immédiat à ces nouvelles variables ?** Ces interfaces bénéficieront d'un accès immédiat : [!UICONTROL Analysis Workspace], [!UICONTROL Rapports et analyses], Créateur [!UICONTROL de rapports], [!UICONTROL Publicité - Analyses ad hoc], API et Outils [!UICONTROL de données].

* **Ces eVars et événements supplémentaires s’afficheront-ils automatiquement dans mes flux de données ?** Les flux de données auront accès aux nouvelles variables et aux nouveaux événements une fois qu’ils seront activés. Les nouvelles colonnes d’eVars n’apparaîtront pas tant que vous n’aurez pas choisi de les inclure. Toutefois, les nouveaux événements apparaîtront dans la colonne event_list dès qu’ils seront activés ; la table de recherche des événements contient les noms d’événement pour ces identifiants d’événement. N’activez pas les nouveaux événements si vous n’êtes pas prêt à les consommer dans les flux de données.

* **Comment demander de nouvelles colonnes de flux de données ?** Pour demander de nouvelles colonnes, reportez-vous à la section [Configuration des flux de données](https://marketing.adobe.com/resources/help/en_US/sc/clickstream/datafeeds_configure.html).

* **Comment procéder si je suis actuellement un client Analytics Ultimate, mais que je souhaite revenir à Analytics Prime alors que j’ai actuellement 200 eVars activées ?** Adobe ne désactivera pas vos eVars existantes, mais vous ne pourrez pas en activer davantage. Si vous désactivez des eVars, vous ne pouvez pas les réactiver tant que vous dépassez la limite d’Analytics Prime de 200 eVars activées.

