---
description: Description de la procédure de création d’une requête Data Warehouse.
title: Configuration des options de rapport pour une requête de Data Warehouse
feature: Data Warehouse
exl-id: b273bddb-431c-44d9-82a5-cb088829b3a3
source-git-commit: 4e4b5e1c362778223be01f78b173a698c53f9b32
workflow-type: tm+mt
source-wordcount: '453'
ht-degree: 22%

---

# Configuration des options de rapport pour une requête de Data Warehouse

Plusieurs options de configuration sont disponibles lors de la création d’une requête Data Warehouse. Les informations suivantes expliquent comment configurer les options de rapport pour la requête.

Pour plus d’informations sur la façon de commencer à créer une requête, ainsi que des liens vers d’autres options de configuration importantes, voir [Créer une requête Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

Pour configurer les options de rapport pour une demande de Data Warehouse :

1. Si vous ne l’avez pas déjà fait, commencez à créer une requête dans Adobe Analytics en sélectionnant **[!UICONTROL Outils]** > **[!UICONTROL Data Warehouse]** > [!UICONTROL **Ajouter**].

   Pour plus d’informations, voir [Créer une requête Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

1. Sur la page Nouvelle requête de Data Warehouse, sélectionnez l’onglet [!UICONTROL **Options de rapport**] .

   ![Onglet Destination du rapport](assets/dw-report-options.png) <!-- update screenshot to include Sort by metrics -->

1. Renseignez les champs suivants :

   | Option | Fonction |
   |---------|----------|
   | [!UICONTROL **Nom de fichier**] | Identifie le rapport. <p>Si l’un des caractères spéciaux suivants est utilisé dans le nom de fichier, la requête ne peut pas être enregistrée : <code> ! &quot; # $ &amp; ’ ( ) * + , / : ; > = &lt; ? @ [ ] \ ^ &grave; { } \| ~</code> </p><p>Le caractère % ne peut être utilisé que s’il est suivi de &quot;R&quot;, &quot;rsid&quot; ou &quot;id&quot;, comme suit : <code>%R</code>, <code>%rsid</code>et <code>%id</code>.</p> |
   | [!UICONTROL **Ajouter la période du rapport au nom de fichier**] | Ajoute la plage de dates au nom du fichier de rapport. <p>Par exemple, si vous demandez des données du 1er mai 2024 au 7 mai 2024, le nom du fichier comprend la plage de dates 20240501 - 20240507.</p> |
   | [!UICONTROL **CSV**] | Diffuse des rapports au format CSV pour l’affichage des données dans une feuille de calcul. |
   | [!UICONTROL **Tableau (TDE)**] | Fournit des rapports au format de fichier TDE (Tableau Data Extract), qui peut être utilisé pour visualiser les données et les couches dans les données additionnelles de Tableau. |
   | [!UICONTROL **Envoyer le rapport sous forme de fichier compressé (ZIP)**] | Diffuse les rapports au format compressé (ZIP). Nous vous recommandons d’activer cette option lorsque vous utilisez l’e-mail comme [destination de rapport](/help/export/data-warehouse/create-request/dw-request-report-destinations.md). |
   | [!UICONTROL **Renvoyer toutes les lignes**] | Lorsque cette option est activée, toutes les lignes sont incluses dans le rapport. Désactivez cette option pour spécifier le nombre de lignes à inclure. |
   | [!UICONTROL **Début des commentaires de rapport**] | Ajoutez tous les commentaires que vous souhaitez inclure au rapport. Les commentaires apparaissent au début du rapport. |
   | [!UICONTROL **Tri par mesures**] | Fournit des rapports de ventilation avec classement en Data Warehouse, triés par valeur de mesure décroissante. Le tri par mesure permet d’interpréter plus facilement les rapports de Data Warehouse. Il est aussi plus facile de comparer ces rapports à d’autres rapports de répartition des analyses.<p>Pour plus d’informations, voir [Tri par mesure](/help/export/data-warehouse/sorting-by-metric.md).</p> |
   | [!UICONTROL **Envoyer un fichier manifeste**] | Inclut des métadonnées sur les fichiers inclus dans le rapport.<!-- What kind of metadata is included in the manifest file? --> |
   | [!UICONTROL **Envoyer un fichier de signature numérique**] | Permet aux destinataires du rapport de vérifier que le fichier provient bien d’un Adobe et qu’il n’a pas été modifié. |
   | [!UICONTROL **Envoyez un fichier vide lorsqu’il n’y a pas de données dans le rapport**] | Envoie un rapport même si le rapport ne contient aucune donnée. |

   {style="table-layout:auto"}

1. Continuez à configurer votre demande de Data Warehouse sur l’onglet [!UICONTROL **Options de planification**] . Pour plus d’informations, voir [Configuration des options de planification pour une requête de Data Warehouse](/help/export/data-warehouse/create-request/dw-request-scheduling.md).
