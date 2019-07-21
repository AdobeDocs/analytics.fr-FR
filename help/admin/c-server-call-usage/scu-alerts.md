---
description: Ajoutez ou gérez toutes les alertes d’utilisation du serveur. Lorsque vous configurez une alerte, elle s’applique à toutes les suites de rapports de toutes les sociétés de connexion associées à une société de facturation.
seo-description: Ajoutez ou gérez toutes les alertes d’utilisation du serveur. Lorsque vous configurez une alerte, elle s’applique à toutes les suites de rapports de toutes les sociétés de connexion associées à une société de facturation.
seo-title: Alertes d'utilisation des appels au serveur
title: Alertes d'utilisation des appels au serveur
uuid: 701 fd 542-5 b 24-42 df -97 a 0-08 e 10929 fa 48
translation-type: tm+mt
source-git-commit: f608acafd77fd6469f553f30c45f54484028890a

---


# Alertes d'utilisation des appels au serveur

Lorsque vous configurez une alerte, elle s’applique à toutes les suites de rapports de toutes les sociétés de connexion associées à une société de facturation.

## Aperçu

A new alert category called **[!UICONTROL Server Calls Usage Alert]** is part of the the existing [Alert Management](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/intellligent_alerts.html) user interface.

It is pre-populated with **1 default alert** that appears within any login company that has access to the Server Call Usage feature. Ces alertes déclenchent une notification adressée à tous les administrateurs de la société de connexion si l'un des critères suivants est satisfait :

* "toute" utilisation de l’appel au serveur qui "est supérieure ou égale" à 100 % pour n’importe quel type d’appel au serveur que vous avez sélectionné, OU
* "toute" utilisation de l’appel au serveur qui "est supérieure ou égale" à 90 % pour n’importe quel type d’appel au serveur que vous avez sélectionné, OU
* "toute" utilisation de l’appel au serveur qui "est supérieure ou égale" à 75 % pour n’importe quel type d’appel au serveur que vous avez sélectionné, ET "la période d’utilisation passée" "est inférieure ou égale" à 75 % de la période d’utilisation.

![](assets/alerts.png)

Vous pouvez accéder aux alertes d’utilisation des appels au serveur de deux façons :

* cliquez sur **[!UICONTROL Gérer les alertes]dans le coin supérieur droit de l’onglet Utilisation actuelle ou Suite de rapports d’utilisation ; ou**
* Navigate to **[!UICONTROL Components]** &gt; **[!UICONTROL Alerts]** in Adobe Analytics.

## Créer des alertes d’utilisation des appels au serveur {#section_2A2882C6D48D47C1944D52FB7C766BEC}

Pour créer des alertes supplémentaires :

1. Cliquez sur **[!UICONTROL + Ajouter]** et sélectionnez **[!UICONTROL Alertes d’utilisation de l’appel au serveur]**.

   ![](assets/server_call_alert.png)

1. Définissez l’alerte.

   ![](assets/sc_alert.png)

   * **Titre**: Attribuez un nom explicite. Vous ne pouvez pas enregistrer une alerte sans nom.
   * **Granularité** temporelle : Fait référence à la fréquence de vérification de l'alerte. *Pour l’instant, nous ne prenons en charge que la granularité hebdomadaire.* Cela signifie que l’alerte sera vérifiée de façon hebdomadaire et analysera les données de la période d’utilisation actuelle.
   * **Destinataires**: Indiquez n'importe quelle personne de l'organisation qui doit recevoir un courriel lorsque l'alerte déclenche le seuil spécifié.
   * **Date d'expiration**: Par défaut, la date d'expiration est d'une année à compter de la date de création d'alerte.
   * **Envoyer une alerte lorsque**:

      * L'une de ces mesures Déclencheur
Ajoute le type d'appel du serveur sous forme de mesure et spécifiez le seuil d'alerte en sélectionnant le modificateur et le seuil :
         * est supérieur ou égal
         * est inférieur ou égal
      * Avec
spécification du seuil et de la condition (est supérieur ou égal ou est inférieur ou égal à) pour la période d'utilisation.

1. Cliquez sur **[!UICONTROL Enregistrer]**.

## Gérer des alertes d’utilisation de l’appel au serveur {#section_8FF98170763C4B5CBEC6DD43F893177A}

![](assets/alert_mgmt.png)

Pour gérer des alertes :

1. Cochez la case à côté d’une ou de plusieurs alertes. Les actions pour gérer les alertes apparaissent en haut.
1. Effectuez une ou plusieurs actions :

   | Action | Définition |
   |--- |--- |
   | + Ajouter | Accédez au [Générateur d’alertes](../../admin/c-server-call-usage/scu-alerts.md) en cliquant sur [!UICONTROL + Ajouter] |
   | Baliser | Ajoutez des balises aux alertes pour les organiser et les utiliser plus facilement. |
   | Supprimer | Vous pouvez supprimer toutes les alertes sauf les alertes par défaut. |
   | Renommer | Vous pouvez renommer toutes les alertes sauf les alertes par défaut. |
   | Approuver | Approuvez les alertes pour les rendre "officielles". |
   | Activer/Désactiver | Vous pouvez activer ou désactiver toutes les alertes sauf les alertes par défaut. |
   | Renouveler | Lorsqu’une ou plusieurs alertes sont sélectionnées, elles peuvent être renouvelées. Cela prolonge leur date d’expiration d’un an à partir du moment où vous avez cliqué sur l’option [!UICONTROL Renouveler], quelle que soit leur date d’expiration d’origine. |
   | Exporter dans un fichier CSV | Reportez-vous à [Télécharger le rapport d’utilisation](../../admin/c-server-call-usage/report-suite-usage.md). |

