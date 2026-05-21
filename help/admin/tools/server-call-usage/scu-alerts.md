---
description: Ajoutez ou gérez toutes les alertes d’utilisation du serveur. Lorsque vous configurez une alerte, elle s’applique à toutes les suites de rapports de toutes les sociétés de connexion associées à une société de facturation.
title: Alerte d’utilisation des appels au serveur
feature: Server Call Usage
exl-id: 35926566-c570-4ed2-9bbc-0906518bcf64
role: Admin
TQID: https://experienceleague.adobe.com/aF3SxS36Y1xQN-saS6NTRJoN6H5XwgCx2iRmWPvUPm0
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: e93b8c4c-c5f7-45f8-9abe-9b710f53f502
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 517
ht-degree: 75%

---

# Alertes d’utilisation des appels au serveur

Lorsque vous configurez une alerte, elle s’applique à toutes les suites de rapports de toutes les sociétés de connexion associées à une société de facturation.

Les alertes d’utilisation des appels au serveur font partie de l’interface utilisateur [Alertes](/help/components/alerts/alert-manager.md).

Elle contient déjà **une alerte par défaut** qui apparaît dans toutes les sociétés de connexion qui ont accès à la fonctionnalité d’utilisation de l’appel au serveur. Cette alerte déclenche l’envoi d’une notification à tous les administrateurs de la société de connexion si l’un des critères suivants est rempli :

* &quot;toute&quot; utilisation de l’appel au serveur qui &quot;est supérieure ou égale&quot; à 100 % pour n’importe quel type d’appel au serveur que vous avez sélectionné, OU
* &quot;toute&quot; utilisation de l’appel au serveur qui &quot;est supérieure ou égale&quot; à 90% pour n’importe quel type d’appel au serveur que vous avez sélectionné, OU
* &quot;toute&quot; utilisation de l’appel au serveur qui &quot;est supérieure ou égale&quot; à 75 % pour n’importe quel type d’appel au serveur que vous avez sélectionné, ET &quot;la période d’utilisation passée&quot; &quot;est inférieure ou égale&quot; à 75 % de la période d’utilisation.

![](/help/admin/tools/server-call-usage/assets/alerts.png)

Vous pouvez accéder aux alertes d’utilisation des appels au serveur de deux façons :

* cliquez sur **[!UICONTROL Gérer les alertes]** dans le coin supérieur droit de l’onglet Utilisation actuelle ou Suite de rapports d’utilisation ; ou
* accédez à **[!UICONTROL Composants]** > **[!UICONTROL Alertes]** dans Adobe Analytics.

## Créer des alertes d’utilisation des appels au serveur {#create}

Pour créer des alertes supplémentaires :

1. Cliquez sur **[!UICONTROL + Ajouter]** et sélectionnez **[!UICONTROL Alertes d’utilisation de l’appel au serveur]**.

   ![](/help/admin/tools/server-call-usage/assets/server_call_alert.png)

1. Définissez l’alerte.

   ![](/help/admin/tools/server-call-usage/assets/sc_alert.png)

   * **Titre** : spécifiez un nom explicite. Vous ne pouvez pas enregistrer une alerte sans nom.
   * **Granularité du temps** : indique la fréquence de vérification de l’alerte. *Pour le moment, nous ne prenons en charge que la granularité hebdomadaire.* Cela signifie que l’alerte sera vérifiée toutes les semaines et que les données de la période d’utilisation actuelle seront réexaminées.
   * **Destinataires** : indique toutes les personnes de l’organisation qui doivent recevoir un courrier électronique lorsqu’une alerte déclenche le seuil spécifié.
   * **Date d’expiration** : par défaut, la date d’expiration est fixée à un an à compter de la date de création de l’alerte.
   * **Envoyer une alerte lorsque** :

      * Déclencheur de l’une de ces mesures
Ajoutez le type d’appel/s au serveur en tant que mesure et spécifiez le seuil d’alerte en sélectionnant le modificateur et le seuil :
         * est supérieur ou égal
         * est inférieur ou égal
      * Avec
Spécifiez le seuil et la condition (supérieur ou égal à ou inférieur ou égal à) pour la période d’utilisation passée.

1. Cliquez sur **[!UICONTROL Enregistrer]**.

## Gérer des alertes d’utilisation de l’appel au serveur {#manage}

![](/help/admin/tools/server-call-usage/assets/alert_mgmt.png)

Pour gérer des alertes :

1. Cochez la case à côté d’une ou de plusieurs alertes. Les actions pour gérer les alertes apparaissent en haut.
1. Effectuez une ou plusieurs actions :

   | Action | Définition |
   |--- |--- |
   | + Ajouter | Accédez au [Générateur d’alertes](/help/admin/tools/server-call-usage/scu-alerts.md) en cliquant sur [!UICONTROL + Ajouter] |
   | Baliser | Ajoutez des balises aux alertes pour les organiser et les utiliser plus facilement. |
   | Supprimer | Vous pouvez supprimer toutes les alertes sauf les alertes par défaut. |
   | Renommer | Vous pouvez renommer toutes les alertes sauf les alertes par défaut. |
   | Approuver | Approuvez les alertes pour les rendre &quot;officielles&quot;. |
   | Activer/Désactiver | Vous pouvez activer ou désactiver toutes les alertes sauf les alertes par défaut. |
   | Renouvellement | Lorsqu’une ou plusieurs alertes sont sélectionnées, elles peuvent être renouvelées. Cela étend leurs dates d’expiration à un an à compter du jour où l’utilisateur a cliqué sur [!UICONTROL Renouveler], quelle que soit leur date d’expiration d’origine. |
   | Exporter dans un fichier CSV | Reportez-vous à [Télécharger le rapport d’utilisation](/help/admin/tools/server-call-usage/report-suite-usage.md). |

   {style="table-layout:auto"}
