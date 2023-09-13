---
description: Description de la procédure de création d’une demande Data Warehouse.
title: Configuration des options de rapport pour une requête de Data Warehouse
feature: Data Warehouse
source-git-commit: 3b116cb8d0d3f3eb86b512d712f37b29876f2b22
workflow-type: tm+mt
source-wordcount: '493'
ht-degree: 19%

---

# Configuration des options de rapport pour une requête de Data Warehouse

>[!AVAILABILITY]
>
>Certaines des fonctionnalités de Data Warehouse décrites dans cet article (ainsi que d’autres articles de Data Warehouse de cette section) sont disponibles uniquement dans la phase de test limité de la version et peuvent ne pas être encore disponibles dans votre environnement.
>
>Pour plus d’informations sur les fonctionnalités qui ne sont pas encore disponibles pour tous les clients, ainsi que pour plus d’informations sur le calendrier de publication de ces fonctionnalités, voir la section [notes de mise à jour](/help/release-notes/latest.md).
>
>Cette note sera supprimée lorsque la fonctionnalité sera disponible. Pour plus d’informations sur le processus de publication d’Analytics, consultez [Versions des fonctionnalités Adobe Analytics](/help/release-notes/releases.md).

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
   | [!UICONTROL **Nom du fichier**] | Identifie le rapport. |
   | [!UICONTROL **Ajout de la plage de dates du rapport au nom de fichier**] | Ajoute la plage de dates au nom du fichier de rapport. <p>Par exemple, si vous demandez des données du 1er mai 2024 au 7 mai 2024, le nom du fichier comprend la plage de dates 20240501 - 20240507.</p> |
   | [!UICONTROL **CSV**] | Diffuse des rapports au format CSV pour l’affichage des données dans une feuille de calcul. |
   | [!UICONTROL **Tableau (TDE)**] | Fournit des rapports au format de fichier TDE (Tableau Data Extract), qui peut être utilisé pour visualiser les données et les couches dans les données additionnelles de Tableau. |
   | [!UICONTROL **Envoi du rapport sous forme de fichier compressé (ZIP)**] | Diffuse les rapports au format compressé (ZIP). Nous vous recommandons d’activer cette option lorsque vous utilisez l’e-mail comme [destination du rapport](/help/export/data-warehouse/create-request/dw-request-report-destinations.md). |
   | [!UICONTROL **Renvoyer toutes les lignes**] | Lorsque cette option est activée, toutes les lignes sont incluses dans le rapport. Désactivez cette option pour spécifier le nombre de lignes à inclure. |
   | [!UICONTROL **Début des commentaires sur le rapport**] | Ajoutez tous les commentaires que vous souhaitez inclure au rapport. Les commentaires apparaissent au début du rapport. |
   | [!UICONTROL **Trier par mesures**] | Fournit des rapports de répartition avec classement dans Data Warehouse, triés par valeurs de mesure décroissantes. Le tri par mesure permet d’interpréter plus facilement les rapports de Data Warehouse. Il est aussi plus facile de comparer ces rapports à d’autres rapports de répartition des analyses.<p>Pour plus d’informations, voir [Tri par mesure](/help/export/data-warehouse/sorting-by-metric.md).</p> |
   | [!UICONTROL **Envoyer un fichier manifeste**] | Inclut des métadonnées sur les fichiers inclus dans le rapport.<!-- What kind of metadata is included in the manifest file? --> |
   | [!UICONTROL **Envoyer un fichier de signature numérique**] | Permet aux destinataires du rapport de vérifier que le fichier provient bien d’un Adobe et qu’il n’a pas été modifié. |
   | [!UICONTROL **Envoyer un fichier vide lorsqu’il n’y a pas de données dans le rapport**] | Envoie un rapport même si le rapport ne contient aucune donnée. |

   {style="table-layout:auto"}

1. Poursuivez la configuration de votre requête de Data Warehouse sur le [!UICONTROL **Options de planification**] . Pour plus d’informations, voir [Configuration des options de planification pour une requête de Data Warehouse](/help/export/data-warehouse/create-request/dw-request-scheduling.md).