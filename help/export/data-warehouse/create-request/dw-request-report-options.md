---
description: Description de la procédure de création d’une requête Data Warehouse.
title: Configuration des options de rapport pour une requête Data Warehouse
feature: Data Warehouse
exl-id: b273bddb-431c-44d9-82a5-cb088829b3a3
source-git-commit: 4e4b5e1c362778223be01f78b173a698c53f9b32
workflow-type: tm+mt
source-wordcount: '453'
ht-degree: 22%

---

# Configuration des options de rapport pour une requête Data Warehouse

Plusieurs options de configuration sont disponibles lors de la création d’une requête Data Warehouse. Les informations suivantes décrivent comment configurer les options de rapport pour la requête.

Pour plus d’informations sur la façon de commencer à créer une requête, ainsi que des liens vers d’autres options de configuration importantes, voir [Créer une requête Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

Pour configurer les options de rapport d’une requête Data Warehouse :

1. Si vous ne l’avez pas déjà fait, commencez à créer une requête dans Adobe Analytics en sélectionnant **[!UICONTROL Outils]** > **[!UICONTROL Data Warehouse]** > [!UICONTROL **Ajouter**].

   Pour plus d’informations, voir [Créer une requête Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

1. Sur la page Nouvelle requête Data Warehouse , sélectionnez l’onglet [!UICONTROL **Options du rapport**] .

   ![Onglet Destination du rapport](assets/dw-report-options.png) <!-- update screenshot to include Sort by metrics -->

1. Renseignez les champs suivants :

   | Option | Fonction |
   |---------|----------|
   | [!UICONTROL **Nom du fichier**] | Identifie le rapport. <p>Si l’un des caractères spéciaux suivants est utilisé dans le nom de fichier, la requête ne peut pas être enregistrée : <code> !  » # $ &amp; &#39; ( ) * + , / : ; > = &lt; ? @ [ ] \ ^ ` { } \| ~</code> </p><p>Le caractère % ne peut être utilisé que s&#39;il est suivi de « R », « rsid » ou « id », comme suit : <code>%R</code>, <code>%rsid</code>, et <code>%id</code>.</p> |
   | [!UICONTROL **Ajouter une période de rapport au nom de fichier**] | Ajoute la période au nom du fichier de rapport. <p>Par exemple, si vous demandez des données du 1er mai 2024 au 7 mai 2024, le nom de fichier inclut la période 20240501 - 20240507.</p> |
   | [!UICONTROL **CSV**] | Diffuse les rapports au format CSV afin d’afficher les données dans une feuille de calcul. |
   | [!UICONTROL **Tableau (TDE)**] | Fournit des rapports dans un format de fichier TDE (Tableau Data Extract), qui peut être utilisé pour visualiser les données et la couche dans les données supplémentaires dans Tableau. |
   | [!UICONTROL **Envoyer le rapport sous forme de fichier compressé (ZIP)**] | Diffuse les rapports au format compressé (ZIP). Nous vous recommandons d’activer cette option lorsque vous utilisez l’e-mail comme [ destination du rapport ](/help/export/data-warehouse/create-request/dw-request-report-destinations.md). |
   | [!UICONTROL **Renvoyer toutes les lignes**] | Lorsqu’elle est activée, toutes les lignes sont incluses dans le rapport. Désactivez cette option pour spécifier le nombre de lignes à inclure. |
   | [!UICONTROL **Début des commentaires du rapport**] | Ajoutez les commentaires que vous souhaitez inclure dans le rapport. Les commentaires apparaissent au début du rapport. |
   | [!UICONTROL **Trier par mesures**] | Fournit des rapports de répartition classés dans Data Warehouse, triés par valeur de mesure décroissante. Le tri par mesure permet d’interpréter plus facilement les rapports de Data Warehouse. Il est aussi plus facile de comparer ces rapports à d’autres rapports de répartition des analyses.<p>Pour plus d’informations, voir [Trier par mesure](/help/export/data-warehouse/sorting-by-metric.md).</p> |
   | [!UICONTROL **Envoyer un fichier manifeste**] | Inclut des métadonnées sur les fichiers inclus dans le rapport.<!-- What kind of metadata is included in the manifest file? --> |
   | [!UICONTROL **Envoyer un fichier de signature numérique**] | Permet aux destinataires du rapport de vérifier que le fichier provient bien d’Adobe et qu’il n’a pas été modifié. |
   | [!UICONTROL **Envoyer un fichier vide quand le rapport ne contient aucune donnée**] | Envoie un rapport même s’il ne contient aucune donnée. |

   {style="table-layout:auto"}

1. Continuez à configurer votre requête Data Warehouse dans l’onglet [!UICONTROL **Options de planification**]. Pour plus d’informations, voir [Configuration des options de planification pour une requête Data Warehouse](/help/export/data-warehouse/create-request/dw-request-scheduling.md).
