---
description: Découvrez comment créer des alertes dans Analysis Workspace.
title: Création d’alertes
feature: Alerts
exl-id: 82e51357-4a32-4db1-bc56-95a72dbaa1be
source-git-commit: 7945499ab49b488985ff70956c0ee0cd521b1421
workflow-type: tm+mt
source-wordcount: '1026'
ht-degree: 69%

---

# Créer des alertes {#create-alerts}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_alerts_timegranularity"
>title="Granularité temporelle"
>abstract="La granularité temporelle fait référence à la fréquence de vérification de l’alerte."

<!-- markdownlint-enable MD034 -->

>[!NOTE]
>
>L’utilisation d’alertes avec détection des anomalies (également appelées _Alertes intelligentes_) n’est disponible que pour les organisations qui disposent d’un package Adobe Analytics Prime ou Ultimate.

Les alertes dans Journey Analytics envoient un avertissement en fonction des modifications de pourcentages ou de points de données spécifiques. Selon votre package Adobe Analytics, vous pouvez également déclencher des alertes en fonction des seuils d’anomalie. Les alertes d’utilisation des appels au serveur sont un autre type d’alerte disponible uniquement pour les administrateurs et administratrices Analytics. Ces alertes vous avertissent du risque ou de l’occurrence d’une surcharge dans les données de consommation et d’engagement des appels au serveur. Pour plus d’informations, voir [Alertes d’utilisation des appels au serveur](/help/admin/admin/c-server-call-usage/scu-alerts.md).

Pour plus d’informations sur les alertes, voir [Présentation des alertes](intellligent-alerts.md).

Pour créer une alerte, procédez comme suit :

1. Utilisez l’une des méthodes suivantes pour créer une alerte :

   * Ouvrez un projet dans Analysis Workspace, puis sélectionnez **[!UICONTROL Composants]** > **[!UICONTROL Créer une alerte]**.
   * Ouvrez un projet dans Analysis Workspace, puis utilisez le raccourci suivant : ***cmd + shift + a*** (macOS) ou ***ctrl + shift + a*** (Windows).
   * Ouvrez un projet dans Analysis Workspace, sélectionnez un ou plusieurs éléments de ligne dans un tableau à structure libre, puis cliquez avec le bouton droit et sélectionnez **[!UICONTROL Créer une alerte à partir de la sélection]**. Cette action préremplit instantanément le [créateur d’alertes](alert-builder.md) pour créer une alerte avec les mesures et filtres corrects.
   * Créez une alerte [à partir du gestionnaire d’alertes](/help/components/c-alerts/alert-manager.md#create-alerts).

   Le créateur d’alertes s’affiche. Cette interface est familière avec l’interface permettant de créer des segments ou des mesures calculées dans Analytics.



## Créateur d’alertes

L’interface du créateur d’alertes est similaire à l’interface que vous utilisez pour créer des segments ou des mesures calculées dans Customer Journey Analytics :

![Interface du créateur d’alertes](assets/alert-builder.png)

Spécifiez les informations suivantes dans le créateur d’alertes pour une alerte :

| Élément | Description |
|---------|----------|
| **[!UICONTROL Titre]** | Spécifiez le nom de l’alerte. Le nom de l’alerte doit contenir le nom du rapport ou le seuil des mesures. |
| **[!UICONTROL Description (facultatif)]** | Spécifiez une description de l’alerte. |
| **[!UICONTROL Granularité temporelle]** | Spécifiez quand vérifier la mesure : chaque jour, chaque semaine ou chaque mois.<p> |
| **[!UICONTROL Destinataires]** | Spécifiez où envoyer l’alerte. Une alerte peut être envoyée à un utilisateur ou à un groupe Analytics, à une adresse e-mail brute ou à un numéro de téléphone.<p><b>Important</b> : le numéro de téléphone doit être précédé d’un `+` et d’un [code du pays](https://countrycode.org/).</p><p>Exemple de l’e-mail qu’un utilisateur reçoit :</p><p>![E-mail d’alerte](assets/alerts-email.PNG)</p> |
| **[!UICONTROL Date d’expiration]** | Définissez la date et l’heure d’expiration de l’alerte. |
| **[!UICONTROL Délai]** | Le temps nécessaire pour que les données soient complètes et disponibles pour faire l’objet de rapports dans Customer Journey Analytics varie selon l’entreprise, allant généralement de 3 à 9 heures après l’heure de l’événement de données. Pour que les alertes soient précises, les données d’événement d’une plage d’événements donnée doivent être complètes, ce qui signifie qu’Adobe ne reçoit plus de données d’événement pour la plage d’événements spécifiée.<p>Pour tenir compte de ce délai d’ingestion, les alertes sont envoyées avec un délai par défaut de 9 heures.</p><p>Vous pouvez régler le délai par défaut de 9 heures sur une valeur comprise entre 0 et 24 heures. Toutefois, si vous réduisez le délai en dessous de 9 heures, cela peut signifier que vous signalez des données incomplètes, ce qui entraîne des informations d’alerte inexactes.</p><p>Tenez compte de ce qui suit lors de la configuration du paramètre de délai :</p><ul><li>**Comprendre la disponibilité et l’exhaustivité des données** : toutes les données par lot ne sont ingérées dans un jeu de données Experience Platform qu’après une période de 3 à 9 heures. Pour que les alertes soient exactes, l’ingestion des données doit être terminée et toutes les données par lot disponibles dans le jeu de données.</li><li>**Déterminer le temps nécessaire pour que vos données soient complètes et disponibles dans le jeu de données** : les délais d’ingestion des données varient selon l’organisation. Assurez-vous que le délai que vous choisissez pour la diffusion des alertes est identique ou inférieur au temps nécessaire pour que les données par lot soient disponibles dans le jeu de données Platform<!--add link? -->.</li><p>**Conseil :** le moyen le plus précis de connaître le temps nécessaire pour que toutes les données par lot soient terminées et ingérées dans le jeu de données Platform est de consulter l’équipe d’ingénierie des données de votre organisation.</p><p>Vous pouvez également obtenir une idée générale du temps nécessaire à la diffusion par lots dans votre organisation pour être disponible dans le jeu de données Experience Platform. Création du tableau à structure libre suivant dans Analysis Workspace :</p><ol><li>Dans un tableau à structure libre d’Analysis Workspace, ajoutez une mesure [!UICONTROL **Événements**] et une dimension [!UICONTROL **Jour**].</li><li>Répartissez la dimension [!UICONTROL **Jour**] à l’aide d’une dimension [!UICONTROL **Heures**].<p>Les heures sans données indiquent 0.</p></li></ol><li>**Tenez compte des erreurs dans vos calculs** : si vous réduisez le délai par défaut, configurez le délai pour qu’il soit supérieur d’au moins une heure au temps nécessaire à votre organisation pour que l’ingestion des données soit complète. Par exemple, s’il y a un délai de 3 heures avant la fin de l’ingestion des données, vous devez définir le délai sur 4 heures.</li> |
| **[!UICONTROL Envoyer une alerte lorsque]** | [!UICONTROL **L’une de ces mesures déclenche**] : faites glisser et déposez les mesures (y compris les mesures calculées) ici pour créer des déclencheurs pour l’alerte.<p>Un message **« composants incompatibles »** s’affiche si certains composants (mesures/dimensions/segments) de l’alerte ne sont pas compatibles avec la vue de données actuellement sélectionnée.</p><p>Déterminez le seuil que la mesure doit dépasser avant l’envoi d’une alerte. Vous pouvez définir un seuil, puis l’une des conditions suivantes :</p><ul><li>il existe une anomalie</li><li>l’anomalie est supérieure à celle prévue</li><li>l’anomalie est inférieure à celle prévue</li><li>est supérieur ou égal</li><li>est inférieur ou égal</li><li>change de</li><li>Le seuil peut être défini à 90 %, 95 %, 99 %, 99,75 % ou 99,90 %.</li></ul><p>[!UICONTROL **Avec tous ces filtres**] : faites glisser et déposez des segments ou des dimensions pour ajouter des filtres à l’alerte. Par exemple, l’ajout d’un segment *Appareils mobiles uniquement* signifie que la règle se déclenche uniquement pour les appareils mobiles. Vous pouvez ajouter des filtres supplémentaires à l’aide d’une instruction ET. Pour ajouter des règles AND ou OR, cliquez sur l’icône d’engrenage.</p><p>Consultez [Alertes - cas d’utilisation](alerts-use-cases.md) pour des exemples de cas d’utilisation.</p> |
| **[!UICONTROL Aperçu]** | L’aperçu d’alerte interactif vous indique la fréquence approximative à laquelle une alerte se déclenche en fonction de votre expérience passée.<p>Si, par exemple, vous définissez une granularité temporelle quotidienne, l’aperçu indique que, pour une certaine mesure, l’alerte aurait été déclenchée x fois durant les 30 ou 31 derniers jours.</p><p>Si vous constatez qu’un trop grand nombre d’alertes est déclenché, vous pouvez ajuster le seuil dans le [Gérer les alertes](alert-manager.md).</p><p>![](assets/alert-preview.png){width="50%"}</p> |

<!--

   ![](assets/alert-builder.png)

1. Specify the following options to configure the alert:

   | Option | Description | 
   |---------|----------|
   | [!UICONTROL **Title**]  | Specify a name for the alert. The alert name might contain the name of the report or the metrics threshold. | 
   | [!UICONTROL **Description (optional)**] | Specify a description for the alert. | 
   | [!UICONTROL **Time granularity**] | Select how often you want the metric to be checked: Hourly, Daily, Weekly, or Monthly.<p><b>Note:</b> For report suites with a custom calendar, monthly granularity in the Alert Builder is not supported.<!--true?--</p | 
   | [!UICONTROL **Recipients**] | Specify where the alert can be sent. An alert can be sent to an Analytics user, an Analytics group, a raw email address, or to a phone number.<p><b>Important:</b> The phone number must be preceded by `+` and a [country code](https://countrycode.org/).</p><p>The e-mail that a user would receive once an alert has been triggered looks similar to:</p><p>![](assets/alerts-email.PNG)</p> | 
   | [!UICONTROL **Expiration date**] | Set the date and time when you want the alert to expire. | 
   | [!UICONTROL **Send an alert when**] | [!UICONTROL **Any of these metrics trigger**]: Drag and drop metrics (including calculated metrics) here to create triggers for the alert.<p>An **"incompatible components"** message appears if not all the metrics, dimensions, or segments in the alert are compatible with the currently selected data view.</p><p>Determine the threshold that the metric must exceed before an alert is set. You can set this value to a threshold and then to one of the following conditions:</p><ul><li>anomaly exists</li><li>anomaly is above expected</li><li>anomaly is below expected</li><li>is above or equals</li><li>is below or equals</li><li>changes by</li><li>You can set a threshold of 90%, 95%, 99%, 99.75%, and 99.9%.</li></ul><p>[!UICONTROL **With all of these filters**]: Drag and drop segments or dimensions to add filters. For example, adding a *Mobile Devices Only* segment would mean that the rule triggers only for mobile devices. You can add additional filters by using an AND statement. You can add AND or OR rules by clicking the gear icon.</p><p>See [Alerts - use cases](/help/components/c-alerts/alerts-use-cases.md) for example.</p> | 
   | [!UICONTROL **Preview**] | The interactive alert preview shows you how often, approximately, an alert will fire based on past experience.<p>For example, if you set the time granularity to daily, the preview can tell you that the alert would have been triggered for a certain metric x times during the last 30 or 31 days. The preview approximation window is established by the alert frequency setting. For daily alert frequencies, the preview window approximates the previous 30 days. For weekly alert frequencies, the preview window approximates the last 12 weeks. For monthly alert frequencies, the preview window approximates the previous 12 months.</p><p>If you find that too many alerts will be triggered, you can adjust the threshold in the [Alert Manager](/help/components/c-alerts/alert-manager.md).</p><p>![](assets/alert_preview.png)</p> |

1. Select [!UICONTROL **Save**].

-->