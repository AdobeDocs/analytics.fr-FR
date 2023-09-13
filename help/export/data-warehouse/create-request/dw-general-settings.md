---
description: Description de la procédure de création d’une demande Data Warehouse.
title: Paramètres généraux de la demande de Data Warehouse
feature: Data Warehouse
source-git-commit: 0abf0c76f38b481c0b72d113fe49e0da03ddd8cd
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 27%

---

# Paramètres généraux de la demande de Data Warehouse

>[!AVAILABILITY]
>
>Certaines des fonctionnalités de Data Warehouse décrites dans cet article (ainsi que d’autres articles de Data Warehouse de cette section) sont disponibles uniquement dans la phase de test limité de la version et peuvent ne pas être encore disponibles dans votre environnement.
>
>Pour plus d’informations sur les fonctionnalités qui ne sont pas encore disponibles pour tous les clients, ainsi que pour plus d’informations sur le calendrier de publication de ces fonctionnalités, voir la section [notes de mise à jour](/help/release-notes/latest.md).
>
>Cette note sera supprimée lorsque la fonctionnalité sera disponible. Pour plus d’informations sur le processus de publication d’Analytics, consultez [Versions des fonctionnalités Adobe Analytics](/help/release-notes/releases.md).

Plusieurs options de configuration sont disponibles lors de la création d’une requête de Data Warehouse. Les informations suivantes décrivent comment configurer les paramètres généraux de la requête.

Pour plus d’informations sur la façon de commencer à créer une requête, ainsi que des liens vers d’autres options de configuration importantes, voir [Création d’une requête de Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

Pour configurer les paramètres généraux d’une demande de Data Warehouse :

1. Commencez à créer une requête de Data Warehouse dans Adobe Analytics en sélectionnant **[!UICONTROL Outils]** > **[!UICONTROL Data Warehouse]** > [!UICONTROL **Ajouter**].

   Pour plus d’informations, voir [Création d’une requête de Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

1. Sur la page Nouvelle requête de Data Warehouse , sélectionnez le [!UICONTROL **Paramètres généraux**] .

   ![Onglet Destination du rapport](assets/dw-general-settings.png)

1. Renseignez les champs suivants :

   | Option | Fonction |
   |---------|----------|
   | Nom de la demande | Ce nom apparaît sur la page du Data Warehouse principal lors de la gestion des requêtes. |
   | Périodes | Sélectionnez la période à inclure dans le rapport. <p>Vous pouvez choisir des dates personnalisées ou une période prédéfinie. Les plages de paramètres prédéfinis dépendent de la date d’envoi du rapport.</p><p>Les options de paramètres prédéfinis suivantes sont disponibles :</p><ul><li>Today</li><li>Hier</li><li>7 derniers jours</li><li>30 derniers jours</li><li>Cette semaine</li><li>Semaine dernière</li><li>2 dernières semaines</li><li>3 dernières semaines</li><li>4 dernières semaines</li><li>Ce mois-ci</li><li>Mois dernier</li><li>Dernière heure</li><li>Today</li><li>Today</li></ul> |
   | Granularité | <!--what does this setting do? It's not the schedule/frequency... --> Granularité temporelle. Les valeurs valides sont Aucune, Horaire, Journalière, Hebdomadaire, Mensuelle, Trimestrielle et Annuelle.<p>Les rapports de granularité nécessitent une durée de traitement plus longue. Dans le cas d’une granularité mensuelle pour une année complète, les rapports sont traités beaucoup plus rapidement si vous envoyez une demande de rapport pour chaque mois.</p> |

   {style="table-layout:auto"}

1. Poursuivez la configuration de votre requête de Data Warehouse sur le [!UICONTROL **Créer votre rapport**] . Pour plus d’informations, voir [Création d’un rapport pour une demande de Data Warehouse](/help/export/data-warehouse/create-request/dw-request-build-report.md).