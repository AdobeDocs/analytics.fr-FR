---
description: Description de la procédure de création d’une demande Data Warehouse.
title: Configuration des options de rapport pour une requête de Data Warehouse
feature: Data Warehouse
source-git-commit: 42c95198a4d4389308c78c312b5bb37572350cc1
workflow-type: tm+mt
source-wordcount: '404'
ht-degree: 16%

---

# Configuration des options de rapport pour une requête de Data Warehouse

{{release-limited-testing}}

Plusieurs options de configuration sont disponibles lors de la création d’une requête de Data Warehouse. Les informations suivantes expliquent comment configurer les options de rapport pour la requête.

Pour plus d’informations sur la façon de commencer à créer une requête, ainsi que des liens vers d’autres options de configuration importantes, voir [Création d’une requête de Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

Pour configurer les options de rapport pour une demande de Data Warehouse :

1. Commencez à créer une requête dans Adobe Analytics en sélectionnant **[!UICONTROL Outils]** > **[!UICONTROL Data Warehouse]** > [!UICONTROL **Ajouter**].

   Pour plus d’informations, voir [Création d’une requête de Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

1. Sur la page Nouvelle requête de Data Warehouse , sélectionnez le [!UICONTROL **Options de rapport**] .

   ![Onglet Destination du rapport](assets/dw-report-options.png) <!-- update screenshot to include Sort by metrics -->

1. Renseignez les champs suivants :

   | Option | Fonction |
   |---------|----------|
   | Nom du fichier | Identifie le rapport. |
   | Ajout de la plage de dates du rapport au nom de fichier | Ajoute la plage de dates au nom du fichier de rapport. <p>Par exemple, si vous demandez des données du 1er mai 2024 au 7 mai 2024, le nom du fichier comprend la plage de dates 20240501 - 20240507.</p> |
   | CSV | Diffuse des rapports au format CSV pour l’affichage des données dans une feuille de calcul. |
   | Tableau (TDE) | Fournit des rapports au format de fichier TDE (Tableau Data Extract), qui peut être utilisé pour visualiser les données et les couches dans les données additionnelles de Tableau. |
   | Envoi du rapport sous forme de fichier compressé (ZIP) | Diffuse les rapports au format compressé (ZIP). Nous vous recommandons d’activer cette option lorsque vous utilisez l’e-mail comme [destination du rapport](/help/export/data-warehouse/create-request/dw-request-report-destinations.md). |
   | Nombre de lignes dans le tableau | Nombre de lignes pouvant être incluses dans le rapport. Utilisez 0 pour inclure toutes les lignes (il s’agit de la sélection par défaut). <!-- when would you want to limit the rows? To improve performance? Do we have recommendations? --> |
   | Commentaires | Ajoutez tous les commentaires que vous souhaitez inclure au rapport. Les commentaires apparaissent au début du rapport. |
   | Trier par mesures | Fournit des rapports de répartition avec classement dans Data Warehouse, triés par valeurs de mesure décroissantes. Le tri par mesure permet d’interpréter plus facilement les rapports de Data Warehouse. Il est aussi plus facile de comparer ces rapports à d’autres rapports de répartition des analyses.<p>Pour plus d’informations, voir [Tri par mesure](/help/export/data-warehouse/sorting-by-metric.md).</p> |
   | Envoyer le fichier manifeste | Inclut des métadonnées sur les fichiers inclus dans le rapport.<!-- What kind of metadata is included in the manifest file? --> |
   | Envoi d’un fichier de signature numérique | Permet aux destinataires du rapport de vérifier que le fichier provient bien d’un Adobe et qu’il n’a pas été modifié. |
   | Envoyer un fichier vide lorsqu’il n’y a pas de données dans le rapport | Envoie un rapport même si le rapport ne contient aucune donnée. |

   {style="table-layout:auto"}

1. Poursuivez la configuration de votre requête de Data Warehouse sur le [!UICONTROL **Options de planification**] . Pour plus d’informations, voir [Configuration des options de planification pour une requête de Data Warehouse](/help/export/data-warehouse/create-request/dw-request-scheduling.md).