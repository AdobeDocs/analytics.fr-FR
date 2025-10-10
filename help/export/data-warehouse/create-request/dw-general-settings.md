---
description: Description de la procédure de création d’une requête Data Warehouse.
title: Paramètres généraux des requêtes Data Warehouse
feature: Data Warehouse
exl-id: f564d5a9-78a2-431e-987a-78c4b0b9d31e
source-git-commit: 1e1a26b8595ca026fb049322125a6f91d9d5513c
workflow-type: tm+mt
source-wordcount: '399'
ht-degree: 34%

---

# Paramètres généraux des requêtes Data Warehouse

Plusieurs options de configuration sont disponibles lors de la création d’une requête Data Warehouse. Les informations suivantes décrivent comment configurer les paramètres généraux de la requête.

Pour plus d’informations sur la façon de commencer à créer une requête, ainsi que des liens vers d’autres options de configuration importantes, voir [Créer une requête Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

Pour configurer les paramètres généraux d’une requête Data Warehouse :

1. Commencez à créer une requête Data Warehouse dans Adobe Analytics en sélectionnant **[!UICONTROL Outils]** > **[!UICONTROL Data Warehouse]** > [!UICONTROL **Ajouter**].

   Pour plus d’informations, voir [Créer une requête Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

1. Sur la page Nouvelle requête Data Warehouse , sélectionnez l’onglet [!UICONTROL **Paramètres généraux**].

   ![Onglet de destination du rapport](assets/dw-general-settings.png)

1. Renseignez les champs suivants :

   | Option | Fonction |
   |---------|----------|
   | Nom de la demande | Ce nom apparaît sur la page Data Warehouse principale lors de la gestion des requêtes. |
   | Périodes | Sélectionnez la période à inclure dans le rapport. <p>Vous pouvez choisir des dates personnalisées ou une période prédéfinie. Les plages prédéfinies sont relatives à la date d’envoi du rapport.</p><p>Les options de paramètre prédéfini suivantes sont disponibles :</p><ul><li>Today</li><li>Hier</li><li>7 derniers jours</li><li>30 derniers jours</li><li>Cette semaine</li><li>Semaine dernière</li><li>2 dernières semaines</li><li>3 dernières semaines</li><li>4 dernières semaines</li><li>Ce mois-ci</li><li>Mois dernier</li><li>Dernière heure</li></ul> |
   | Granularité | Granularité temporelle. Les valeurs valides sont Aucune, Horaire, Journalière, Hebdomadaire, Mensuelle, Trimestrielle et Annuelle.<p>Les rapports de granularité nécessitent une durée de traitement plus longue. Dans le cas d’une granularité mensuelle pour une année complète, les rapports sont traités beaucoup plus rapidement si vous envoyez une demande de rapport pour chaque mois.</p><p>**Remarque :** lors de l’application de la granularité dans une requête Data Warehouse, la colonne « Date » est ajoutée au rapport. Selon la granularité sélectionnée, le format de date change comme suit :</p><ul><li>**Granularité horaire** :<ul> <li>**Format** : `mmmm d, yyyy` De `H` Heures</li><li>**Exemple** : 1Er Janvier 20XX, Heure 0 </li></ul><li>**Granularité quotidienne** :<ul> <li>**Format** : `mmmm d, yyyy`</li><li>**Exemple** : 1er janvier 20XX</li></ul><li>**Granularité hebdomadaire** :<ul> <li>**Format** : Semaine `w, yyyy`</li><li>**Exemple** : Semaine 1, 20XX </li></ul><li>**Granularité mensuelle** :<ul> <li>**Format** : `mmmm yyyy`</li><li>**Exemple** : 20XX Janvier </li></ul><li>**Granularité trimestrielle** :<ul> <li>**Format** : `q` Trimestre `yyyy`</li><li>**Exemple** : 1er trimestre 20XX </li></ul><li>**Granularité annuelle** :<ul> <li>**Format** : `yyyy`</li><li>**Exemple** : 20XX</li></ul> |
   | Mettre à la disposition des utilisateurs de votre organisation | Toutes les requêtes Data Warehouse ne sont visibles que par vous et par tous les administrateurs système. Activez cette option si vous souhaitez que la requête soit visible par tous les membres de votre organisation. <p>L’activation de cette option est utile si vous souhaitez que d’autres utilisateurs et utilisatrices de votre organisation vous aident à créer ou mettre à jour la demande.</p> |

   {style="table-layout:auto"}

1. Continuez à configurer votre requête Data Warehouse dans l’onglet [!UICONTROL **Créer votre rapport**]. Pour plus d’informations, voir [Création d’un rapport pour une requête Data Warehouse](/help/export/data-warehouse/create-request/dw-request-build-report.md).
