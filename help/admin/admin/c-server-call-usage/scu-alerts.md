---
description: Ajoutez ou gérez toutes les alertes d’utilisation du serveur. Lorsque vous configurez une alerte, elle s’applique à toutes les suites de rapports de toutes les sociétés de connexion associées à une société de facturation.
title: Alerte d’utilisation des appels au serveur
feature: Server Call Usage
exl-id: 35926566-c570-4ed2-9bbc-0906518bcf64
role: Admin
source-git-commit: 58e1d3025b455de7fa07037b3b0659330c8324c7
workflow-type: tm+mt
source-wordcount: '513'
ht-degree: 96%

---

# Alertes d’utilisation des appels au serveur

Lorsque vous configurez une alerte, elle s’applique à toutes les suites de rapports de toutes les sociétés de connexion associées à une société de facturation.

Les alertes d’utilisation des appels au serveur font partie de l’interface utilisateur des [alertes](/help/analyze/analysis-workspace/c-intelligent-alerts/alert-manager.md).

Elle contient déjà **une alerte par défaut** qui apparaît dans toutes les sociétés de connexion qui ont accès à la fonctionnalité d’utilisation de l’appel au serveur. Cette alerte déclenche l’envoi d’une notification à tous les administrateurs de la société de connexion si l’un des critères suivants est rempli :

* &quot;toute&quot; utilisation de l’appel au serveur qui &quot;est supérieure ou égale&quot; à 100 % pour n’importe quel type d’appel au serveur que vous avez sélectionné, OU
* &quot;toute&quot; utilisation de l’appel au serveur qui &quot;est supérieure ou égale&quot; à 90% pour n’importe quel type d’appel au serveur que vous avez sélectionné, OU
* &quot;toute&quot; utilisation de l’appel au serveur qui &quot;est supérieure ou égale&quot; à 75 % pour n’importe quel type d’appel au serveur que vous avez sélectionné, ET &quot;la période d’utilisation passée&quot; &quot;est inférieure ou égale&quot; à 75 % de la période d’utilisation.

![](/help/admin/admin/c-server-call-usage/assets/alerts.png)

Vous pouvez accéder aux alertes d’utilisation des appels au serveur de deux façons :

* cliquez sur **[!UICONTROL Gérer les alertes]** dans le coin supérieur droit de l’onglet Utilisation actuelle ou Suite de rapports d’utilisation ; ou
* accédez à **[!UICONTROL Composants]** > **[!UICONTROL Alertes]** dans Adobe Analytics.

## Créer des alertes d’utilisation des appels au serveur {#create}

Pour créer des alertes supplémentaires :

1. Cliquez sur **[!UICONTROL + Ajouter]** et sélectionnez **[!UICONTROL Alertes d’utilisation de l’appel au serveur]**.

   ![](/help/admin/admin/c-server-call-usage/assets/server_call_alert.png)

1. Définissez l’alerte.

   ![](/help/admin/admin/c-server-call-usage/assets/sc_alert.png)

   * **Titre** : spécifiez un nom explicite. Vous ne pouvez pas enregistrer une alerte sans nom.
   * **Granularité du temps** : indique la fréquence de vérification de l’alerte. *Pour l’instant, nous ne prenons en charge que la granularité hebdomadaire.* Cela signifie que l’alerte sera vérifiée de façon hebdomadaire et analysera les données de la période d’utilisation actuelle.
   * **Destinataires** : indique toutes les personnes de l’organisation qui doivent recevoir un courrier électronique lorsqu’une alerte déclenche le seuil spécifié.
   * **Date d’expiration** : par défaut, la date d’expiration est fixée à un an à compter de la date de création de l’alerte.
   * **Envoyer une alerte lorsque** :

      * Pour l’un de ces déclencheurs de mesure
Ajoute le type d’appel au serveur en tant que mesure et spécifie le seuil de l’alerte en sélectionnant le modificateur et le seuil :
         * est supérieur ou égal
         * est inférieur ou égal
      * Avec
Spécifie le seuil et la condition (est supérieur ou égal ou est inférieur ou égal) pour la période d’utilisation passée.

1. Cliquez sur **[!UICONTROL Enregistrer]**.

## Gérer des alertes d’utilisation de l’appel au serveur {#manage}

![](/help/admin/admin/c-server-call-usage/assets/alert_mgmt.png)

Pour gérer des alertes :

1. Cochez la case à côté d’une ou de plusieurs alertes. Les actions pour gérer les alertes apparaissent en haut.
1. Effectuez une ou plusieurs actions :

   | Action | Définition |
   |--- |--- |
   | + Ajouter | Accédez au [Générateur d’alertes](/help/admin/admin/c-server-call-usage/scu-alerts.md) en cliquant sur [!UICONTROL + Ajouter] |
   | Baliser | Ajoutez des balises aux alertes pour les organiser et les utiliser plus facilement. |
   | Supprimer | Vous pouvez supprimer toutes les alertes sauf les alertes par défaut. |
   | Renommer | Vous pouvez renommer toutes les alertes sauf les alertes par défaut. |
   | Approuver | Approuvez les alertes pour les rendre &quot;officielles&quot;. |
   | Activer/Désactiver | Vous pouvez activer ou désactiver toutes les alertes sauf les alertes par défaut. |
   | Renouvellement | Lorsqu’une ou plusieurs alertes sont sélectionnées, elles peuvent être renouvelées. Cela prolonge leur date d’expiration d’un an à partir du moment où vous avez cliqué sur l’option [!UICONTROL Renouveler], quelle que soit leur date d’expiration d’origine. |
   | Exporter dans un fichier CSV | Reportez-vous à [Télécharger le rapport d’utilisation](/help/admin/admin/c-server-call-usage/report-suite-usage.md). |

   {style="table-layout:auto"}
