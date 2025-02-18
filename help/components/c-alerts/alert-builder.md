---
description: Utilisation des alertes dans Analysis Workspace.
title: Présentation du Générateur d’alertes
feature: Alerts
exl-id: 82e51357-4a32-4db1-bc56-95a72dbaa1be
source-git-commit: 966bd9a05e6c344a62ce3f0b12df8a99ff3d7ece
workflow-type: tm+mt
source-wordcount: '695'
ht-degree: 25%

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
>L’utilisation d’alertes avec détection des anomalies (également appelées _Alertes intelligentes_) n’est disponible que pour les organisations qui disposent d’un package Adobe Analytics Prime ou Ultimate.

Dans Adobe Analytics, les alertes vous permettent d’être averti en fonction des pourcentages modifiés ou de points de données spécifiques. Selon votre package Adobe Analytics, vous pouvez également utiliser des alertes à déclencher en fonction des seuils d’anomalie. Les alertes d’utilisation des appels au serveur sont un autre type d’alerte disponible uniquement pour les administrateurs et administratrices Analytics. Ces alertes vous avertissent du risque ou de l’occurrence d’une surcharge dans les données de consommation et d’engagement des appels au serveur. Pour plus d’informations, voir [Alertes d’utilisation des appels au serveur](/help/admin/admin/c-server-call-usage/scu-alerts.md).

Pour plus d’informations sur les alertes, voir [Présentation des alertes](/help/components/c-alerts/intellligent-alerts.md).

Pour créer une alerte :

1. Commencez à créer une alerte en accédant au créateur d’alertes. Vous pouvez accéder au créateur d’alertes de l’une des manières suivantes :

   * Ouvrez un projet dans Analysis Workspace, puis sélectionnez **[!UICONTROL Composants]** > **[!UICONTROL Créer une alerte]**.
   * Ouvrez un projet dans Analysis Workspace, puis utilisez le raccourci suivant : ***ctrl (ou cmd) + maj + a***.
   * Ouvrez un projet dans Analysis Workspace, sélectionnez un ou plusieurs éléments de ligne dans un tableau à structure libre, puis cliquez avec le bouton droit et sélectionnez **[!UICONTROL Créer une alerte à partir de la sélection]**. Cette action préremplit instantanément le créateur d’alertes pour créer une alerte avec les mesures et filtres corrects.
   * Créez une alerte [à partir du gestionnaire d’alertes](/help/components/c-alerts/alert-manager.md#create-alerts).

   Le créateur d’alertes s’affiche. Cette interface est familière avec l’interface de création de segments ou de mesures calculées dans Analytics :

   ![](assets/alert-builder.png)

1. Spécifiez les options suivantes pour configurer l’alerte :

   | Option | Description |
   |---------|----------|
   | [!UICONTROL **Titre**] | Spécifiez le nom de l’alerte. Le nom de l’alerte doit contenir le nom du rapport ou le seuil des mesures. |
   | [!UICONTROL **Description (facultatif)**] | Spécifiez une description pour l’alerte. |
   | [!UICONTROL **Granularité temporelle**] | Sélectionnez la fréquence à laquelle vous souhaitez que la mesure soit vérifiée : Horaire, Quotidien, Hebdomadaire ou Mensuel.<p><b>Remarque :</b> pour les suites de rapports avec un calendrier personnalisé, la granularité mensuelle dans le créateur d’alertes n’est pas prise en charge.<!--true?--></p> |
   | [!UICONTROL **Destinataires**] | Spécifiez où envoyer l’alerte. Une alerte peut être envoyée à un utilisateur ou à un groupe Analytics, à une adresse e-mail brute ou à un numéro de téléphone.<p><b>Important :</b> le numéro de téléphone doit être précédé d’un `+` et d’un [code de pays](https://countrycode.org/).</p><p>L’e-mail qu’un utilisateur recevrait une fois qu’une alerte a été déclenchée ressemble à ce qui suit :</p><p>![](assets/alerts-email.PNG)</p> |
   | [!UICONTROL **Date d’expiration**] | Définissez la date et l’heure d’expiration de l’alerte. |
   | [!UICONTROL **Envoyer une alerte quand**] | [!UICONTROL **Déclencheur de l’une de ces mesures**] : faites glisser et déposez les mesures (y compris les mesures calculées) ici pour créer des déclencheurs pour l’alerte.<p>Un message **« composants incompatibles »** s’affiche si toutes les mesures, dimensions ou segments de l’alerte ne sont pas compatibles avec la vue de données actuellement sélectionnée.</p><p>Déterminez le seuil que la mesure doit dépasser avant l’envoi d’une alerte. Vous pouvez définir un seuil, puis l’une des conditions suivantes :</p><ul><li>il existe une anomalie</li><li>l’anomalie est supérieure à celle prévue</li><li>l’anomalie est inférieure à celle prévue</li><li>est supérieur ou égal</li><li>est inférieur ou égal</li><li>change de</li><li>Le seuil peut être défini à 90 %, 95 %, 99 %, 99,75 % ou 99,90 %.</li></ul><p>[!UICONTROL **Avec tous ces filtres**] : faites glisser et déposez des segments ou des dimensions pour ajouter des filtres. Par exemple, l’ajout d’un segment « Appareils mobiles uniquement » signifie que la règle se déclenche uniquement pour les appareils mobiles. Vous pouvez ajouter des filtres supplémentaires à l’aide d’une instruction AND. Pour ajouter des règles AND ou OR, cliquez sur l’icône d’engrenage.</p><p>Voir [Alertes - cas d’utilisation](/help/components/c-alerts/alerts-use-cases.md) par exemple.</p> |
   | [!UICONTROL **Aperçu**] | Dans l’aperçu interactif des alertes, vous pouvez déterminer à quelle fréquence, approximativement, une alerte sera déclenchée en fonction d’une expérience antérieure.<p>Par exemple, si vous définissez la granularité temporelle sur quotidienne, l’aperçu peut vous indiquer que l’alerte aurait été déclenchée pour une certaine mesure x fois au cours des 30 ou 31 derniers jours. La fenêtre de prévisualisation de l’approximation est établie par le paramètre de fréquence d’alerte. Pour la fréquence d’alerte quotidienne, la fenêtre de prévisualisation correspond approximativement aux 30 jours précédents. Pour la fréquence d’alerte hebdomadaire, la fenêtre d’aperçu correspond à peu près aux 12 dernières semaines. Pour la fréquence d’alerte mensuelle, la fenêtre de prévisualisation est proche de celle des 12 mois précédents.</p><p>Si vous constatez qu’un trop grand nombre d’alertes sera déclenché, vous pouvez ajuster le seuil dans le [Gestionnaire d’alertes](/help/components/c-alerts/alert-manager.md).</p><p>![](assets/alert_preview.png)</p> |

1. Sélectionnez [!UICONTROL **Enregistrer**].
