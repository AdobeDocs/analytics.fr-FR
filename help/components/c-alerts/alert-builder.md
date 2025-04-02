---
description: Utilisation des alertes dans Analysis Workspace.
title: Vue d’ensemble du créateur d’alertes
feature: Alerts
exl-id: 82e51357-4a32-4db1-bc56-95a72dbaa1be
source-git-commit: 966bd9a05e6c344a62ce3f0b12df8a99ff3d7ece
workflow-type: ht
source-wordcount: '695'
ht-degree: 100%

---

# Créer des alertes {#create-alerts}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_alerts_timegranularity"
>title="Granularité temporelle"
>abstract="La granularité temporelle fait référence à la fréquence de vérification de l’alerte et à ce qui sera inclus."

<!-- markdownlint-enable MD034 -->

>[!NOTE]
>
>L’utilisation d’alertes avec détection des anomalies (également appelées _Alertes intelligentes_) n’est disponible que pour les organisations qui disposent d’un package Adobe Analytics Prime ou Ultimate.

Les alertes dans Journey Analytics envoient un avertissement en fonction des modifications de pourcentages ou de points de données spécifiques. Selon votre package Adobe Analytics, vous pouvez également déclencher des alertes en fonction des seuils d’anomalie. Les alertes d’utilisation des appels au serveur sont un autre type d’alerte disponible uniquement pour les administrateurs et administratrices Analytics. Ces alertes vous avertissent du risque ou de l’occurrence d’une surcharge dans les données de consommation et d’engagement des appels au serveur. Pour plus d’informations, voir [Alertes d’utilisation des appels au serveur](/help/admin/admin/c-server-call-usage/scu-alerts.md).

Pour plus d’informations sur les alertes, voir [Vue d’ensemble des alertes](/help/components/c-alerts/intellligent-alerts.md).

Pour créer une alerte, procédez comme suit :

1. Commencez à créer une alerte en accédant au créateur d’alertes. Vous pouvez accéder au créateur d’alertes de l’une des manières suivantes :

   * Ouvrez un projet dans Analysis Workspace, puis sélectionnez **[!UICONTROL Composants]** > **[!UICONTROL Créer une alerte]**.
   * Ouvrez un projet dans Analysis Workspace, puis utilisez le raccourci suivant : ***Ctrl (ou Cmd)+Maj+A***.
   * Ouvrez un projet dans Analysis Workspace, sélectionnez un ou plusieurs éléments de ligne dans un tableau à structure libre, puis cliquez avec le bouton droit et sélectionnez **[!UICONTROL Créer une alerte à partir de la sélection]**. Le créateur d’alertes est ainsi automatiquement prérenseigné afin de créer une alerte avec les mesures et filtres corrects.
   * Créez une alerte [à partir du gestionnaire d’alertes](/help/components/c-alerts/alert-manager.md#create-alerts).

   Le créateur d’alertes s’affiche. Cette interface est semblable à l’interface de création de segments ou de mesures calculées dans Analytics :

   ![](assets/alert-builder.png)

1. Spécifiez les options suivantes pour configurer l’alerte :

   | Option | Description |
   |---------|----------|
   | [!UICONTROL **Titre**] | Spécifiez le nom de l’alerte. Le nom de l’alerte doit contenir le nom du rapport ou le seuil des mesures. |
   | [!UICONTROL **Description (facultatif)**] | Spécifiez une description pour l’alerte. |
   | [!UICONTROL **Granularité temporelle**] | Spécifiez la fréquence de vérification de la mesure : chaque heure, chaque jour, chaque semaine ou chaque mois.<p><b>Remarque :</b> pour les suites de rapports avec un calendrier personnalisé, la granularité mensuelle dans le créateur d’alertes n’est pas prise en charge.<!--true?--></p> |
   | [!UICONTROL **Destinataires**] | Spécifiez où envoyer l’alerte. Une alerte peut être envoyée à un utilisateur ou à un groupe Analytics, à une adresse e-mail brute ou à un numéro de téléphone.<p><b>Important :</b> le numéro de téléphone doit être précédé de `+` et d’un [indicatif de pays](https://countrycode.org/).</p><p>L’e-mail qu’une personne reçoit une fois qu’une alerte a été déclenchée ressemble à celui-ci :</p><p>![](assets/alerts-email.PNG)</p> |
   | [!UICONTROL **Date d’expiration**] | Définissez la date et l’heure d’expiration de l’alerte. |
   | [!UICONTROL **Envoyer une alerte lorsque**] | [!UICONTROL **L’une de ces mesures déclenche**] : faites glisser et déposez les mesures (y compris les mesures calculées) ici pour créer des déclencheurs pour l’alerte.<p>Un message **« composants incompatibles »** s’affiche si certains composants (mesures, dimensions ou segments) de l’alerte ne sont pas compatibles avec la vue de données actuellement sélectionnée.</p><p>Déterminez le seuil que la mesure doit dépasser avant l’envoi d’une alerte. Vous pouvez définir un seuil, puis l’une des conditions suivantes :</p><ul><li>il existe une anomalie</li><li>l’anomalie est supérieure à celle prévue</li><li>l’anomalie est inférieure à celle prévue</li><li>est supérieur ou égal</li><li>est inférieur ou égal</li><li>change de</li><li>Le seuil peut être défini à 90 %, 95 %, 99 %, 99,75 % ou 99,90 %.</li></ul><p>[!UICONTROL **Avec tous ces filtres**] : faites glisser et déposez des segments ou des dimensions pour ajouter des filtres. Par exemple, ajoutez un segment « Appareils mobiles seulement » afin de signifier que la règle se déclenche uniquement pour les appareils mobiles. Vous pouvez ajouter des filtres supplémentaires à l’aide d’une instruction AND. Pour ajouter des règles AND ou OR, cliquez sur l’icône d’engrenage.</p><p>Voir [Alertes - cas d’utilisation](/help/components/c-alerts/alerts-use-cases.md) par exemple.</p> |
   | [!UICONTROL **Aperçu**] | Dans l’aperçu interactif des alertes, vous pouvez déterminer à quelle fréquence, approximativement, une alerte sera déclenchée en fonction d’une expérience antérieure.<p>Si, par exemple, vous définissez une granularité temporelle quotidienne, l’aperçu indique que, pour une certaine mesure, l’alerte aurait été déclenchée x fois durant les 30 ou 31 derniers jours. La fenêtre d’aperçu de l’approximation est établie par le paramètre de fréquence d’alerte. Pour la fréquence d’alerte quotidienne, la fenêtre d’aperçu correspond approximativement aux 30 jours précédents. Pour la fréquence d’alerte hebdomadaire, la fenêtre d’aperçu correspond à peu près aux 12 dernières semaines. Pour la fréquence d’alerte mensuelle, la fenêtre d’aperçu correspond à peu près aux 12 mois précédents.</p><p>Pour réduire le nombre d’alertes déclenchées, réglez le seuil dans le [Gestionnaire d’alertes](/help/components/c-alerts/alert-manager.md).</p><p>![](assets/alert_preview.png)</p> |

1. Sélectionnez [!UICONTROL **Enregistrer**].
