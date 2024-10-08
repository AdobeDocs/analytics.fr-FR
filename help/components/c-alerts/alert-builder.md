---
description: Utilisation des alertes dans Analysis Workspace.
title: Présentation du Générateur d’alertes
feature: Alerts
exl-id: 82e51357-4a32-4db1-bc56-95a72dbaa1be
source-git-commit: 815e50e30fa6a0bce1bf78f33843070f96f52de8
workflow-type: tm+mt
source-wordcount: '629'
ht-degree: 36%

---

# Créer des alertes

>[!NOTE]
>
>L’utilisation d’alertes avec détection des anomalies (également appelée _Alertes intelligentes_) est disponible uniquement pour les organisations qui disposent d’un package Adobe Analytics Select, Prime ou Ultimate.

Les alertes dans Adobe Analytics vous permettent d’être averti en fonction de pourcentages ou de points de données modifiés. Selon votre package Adobe Analytics, vous pouvez également utiliser des alertes pour les déclencher en fonction des seuils d’anomalie. (Les alertes d’utilisation des appels au serveur sont un autre type d’alerte disponible uniquement pour les administrateurs d’Analytics. Ces alertes vous informent du risque ou de l’occurrence d’un dépassement de vos données d’engagement et de consommation d’appels au serveur. Pour plus d’informations, voir [Alertes d’utilisation des appels au serveur](/help/admin/admin/c-server-call-usage/scu-alerts.md).)

Pour plus d’informations sur la présentation des alertes, voir [Présentation des alertes](/help/components/c-alerts/intellligent-alerts.md).

Pour créer une alerte :

1. Commencez à créer une alerte en accédant au créateur d’alertes. Vous pouvez accéder au générateur d’alertes de l’une des façons suivantes :

   * Ouvrez un projet dans Analysis Workspace, puis sélectionnez **[!UICONTROL Composants]** > **[!UICONTROL Créer une alerte]**.
   * Ouvrez un projet dans Analysis Workspace, puis utilisez le raccourci suivant :

     `ctrl (or cmd) + shift + a`
   * Ouvrez un projet dans Analysis Workspace, sélectionnez une ou plusieurs lignes dans un tableau à structure libre, puis cliquez avec le bouton droit de la souris et sélectionnez **[!UICONTROL Créer une alerte d’après la sélection]**.

     Le créateur d’alertes est ainsi prérempli instantanément afin de créer une alerte avec les mesures et filtres corrects.
   * Créez une alerte [ à partir du gestionnaire d’alertes ](/help/components/c-alerts/alert-manager.md#create-alerts).

   Le créateur d’alertes s’affiche. Les personnes qui ont créé des segments ou calculé des mesures dans Analytics connaissent bien cette interface :

   ![](assets/alert-builder.png)

1. Définissez les options suivantes pour configurer l’alerte :

   | Option | Description |
   |---------|----------|
   | [!UICONTROL **Titre**] | Spécifiez le nom de l’alerte. Le nom de l’alerte doit contenir le nom du rapport ou le seuil des mesures. |
   | [!UICONTROL **Description (facultatif)**] | Spécifiez une description pour l’alerte. |
   | [!UICONTROL **Granularité du temps**] | Sélectionnez la fréquence à laquelle vous souhaitez vérifier la mesure : Quotidienne, Hebdomadaire ou Mensuelle.<p><b>Remarque :</b>Pour les vues de données avec un calendrier personnalisé, la granularité mensuelle n’est pas prise en charge dans le Générateur d’alertes.<!--true?--></p> |
   | [!UICONTROL **Destinataires**] | Spécifiez où envoyer l’alerte. Une alerte peut être envoyée à un utilisateur ou à un groupe Analytics, à une adresse e-mail brute ou à un numéro de téléphone.<p><b>Important :</b>Le numéro de téléphone doit être précédé d’un &quot;+&quot; et d’un [code de pays](https://countrycode.org/).</p><p>Le courrier électronique qu’un utilisateur recevrait une fois qu’une alerte a été déclenchée ressemble à ceci :</p><p>![](assets/alerts-email.PNG)</p> |
   | [!UICONTROL **Date d’expiration**] | Définissez la date et l’heure d’expiration de l’alerte. |
   | [!UICONTROL **Envoyer une alerte lorsque**] | [!UICONTROL **L’un de ces déclencheurs de mesures**] : faites glisser et déposez des mesures (y compris des mesures calculées) ici pour créer des déclencheurs pour l’alerte.<p>Un message **&quot;composants incompatibles&quot;** s’affiche si toutes les mesures, dimensions ou segments de l’alerte ne sont pas compatibles avec la vue de données actuellement sélectionnée.</p><p>Déterminez le seuil que la mesure doit dépasser avant l’envoi d’une alerte. Vous pouvez définir un seuil, puis l’une des conditions suivantes :</p><ul><li>il existe une anomalie</li><li>l’anomalie est supérieure à celle prévue</li><li>l’anomalie est inférieure à celle prévue</li><li>est supérieur ou égal</li><li>est inférieur ou égal</li><li>change de</li><li>Le seuil peut être défini à 90 %, 95 %, 99 %, 99,75 % ou 99,90 %.</li></ul><p>[!UICONTROL **Avec tous ces filtres**] : faites glisser et déposez des segments ou des dimensions pour ajouter des filtres. Par exemple, l’ajout d’un segment &quot;Appareils mobiles uniquement&quot; signifie que la règle se déclenche uniquement pour les appareils mobiles. Vous pouvez ajouter d’autres filtres à l’aide d’une instruction ET. Pour ajouter des règles AND ou OR, cliquez sur l’icône d’engrenage.</p><p>Voir [Alertes - cas pratiques](/help/components/c-alerts/alerts-use-cases.md) par exemple cas d’utilisation.</p> |
   | [!UICONTROL **Aperçu**] | Dans l’aperçu interactif des alertes, vous pouvez déterminer à quelle fréquence, approximativement, une alerte sera déclenchée en fonction d’une expérience antérieure.<p>Si, par exemple, vous définissez une granularité temporelle quotidienne, l’aperçu indique que, pour une certaine mesure, l’alerte aurait été déclenchée x fois durant les 30 ou 31 derniers jours.</p><p>Pour réduire le nombre d’alertes déclenchées, réglez le seuil dans le [Gestionnaire d’alertes](/help/components/c-alerts/alert-manager.md).</p><p>![](assets/alert_preview.png)</p> |

1. Sélectionnez [!UICONTROL **Enregistrer**].
