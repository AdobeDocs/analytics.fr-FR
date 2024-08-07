---
description: Le Gestionnaire de segments offre plusieurs manières d’organiser les segments, par exemple le partage, le filtrage, le marquage, l’approbation, la copie, la suppression et le marquage en tant que favoris.
title: Gestion des segments (Gestionnaire de segments)
feature: Segmentation
exl-id: be182a55-23cb-415f-a7d0-3c1efeead1a1
source-git-commit: df9c6d59ef5f5c43d0e1ef822bd23bc0e09ff20e
workflow-type: tm+mt
source-wordcount: '749'
ht-degree: 32%

---

# Gestionnaire de segments

Le Gestionnaire de segments offre plusieurs manières d’organiser les segments, par exemple le partage, le filtrage, le marquage, l’approbation, la copie, la suppression et le marquage en tant que favoris.

Le Gestionnaire de segments Analytics vous présente tous les segments que vous possédez et qui ont été partagés avec vous. Les utilisateurs de niveau administrateur peuvent consulter tous les segments de l’entreprise. Cet aperçu présente l’interface utilisateur et les fonctionnalités du Gestionnaire de segments.

![Gestionnaire de segments](assets/segments-manager.png)

## Accès au Gestionnaire de segments

1. Dans Adobe Analytics, sélectionnez l’onglet **[!UICONTROL Composants]**, puis sélectionnez **[!UICONTROL Segments]**.

   Ou

   Dans un rapport existant, sélectionnez l’icône Segments ![](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg) dans le volet de navigation de gauche, puis sélectionnez **[!UICONTROL Gérer]**.

## Actions disponibles dans le Gestionnaire de segments

Dans le Gestionnaire de segments, vous pouvez :

* [Filtrer des segments](/help/components/segmentation/segmentation-workflow/t-seg-filter.md)

* [Marquage des segments comme favoris](/help/components/segmentation/segmentation-workflow/t-seg-favorite.md)

* [Approbation des segments](/help/components/segmentation/segmentation-workflow/seg-approve.md)

* [Balisage des segments](/help/components/segmentation/segmentation-workflow/seg-tag.md)

* [Partage des segments](/help/components/segmentation/segmentation-workflow/t-seg-share.md)

* Exportez un segment dans un fichier CSV.

* [Copier des segments](/help/components/segmentation/segmentation-workflow/seg-copy.md)

* [Suppression des segments](/help/components/segmentation/segmentation-workflow/seg-delete.md)

## Configuration des colonnes

Vous pouvez configurer les informations affichées pour chaque segment dans le Gestionnaire de segments en configurant les colonnes qui s’affichent.

Pour configurer les colonnes visibles dans le Gestionnaire de segments :

1. Dans Adobe Analytics, sélectionnez l’onglet **[!UICONTROL Composants]**, puis sélectionnez **[!UICONTROL Segments]**.

1. Dans le Gestionnaire de segments, sélectionnez l’icône **Personnaliser les colonnes** ![Icône Personnaliser les colonnes](assets/customize-columns-icon.png), puis sélectionnez les colonnes à afficher dans le Gestionnaire de segments.

   Les colonnes suivantes sont disponibles :

   | Titre de la colonne | Description |
   |---|---|
   | Titre et description | Ces valeurs sont fournies dans le créateur de segments. Pour modifier le titre et la description, cliquez sur le lien du titre pour ouvrir le créateur de segments. |
   | Favoris | Affiche des icônes d’étoile en regard de chaque segment, ce qui vous permet de marquer les segments comme favoris. Pour plus d’informations, voir [Marquage des segments comme favoris](/help/components/segmentation/segmentation-workflow/t-seg-favorite.md). |
   | Suites de rapports | Cette colonne indique dans quelle suite de rapports le segment a été enregistré en dernier. |
   | Propriétaire | Indique qui possède le segment. En tant que non administrateur, vous ne pouvez consulter que les segments que vous possédez ou ceux qui ont été partagés avec vous. |
   | Balises (non cochées dans le sélecteur de colonnes, de ce fait, la colonne n’apparaît pas) | Les balises qui ont été appliquées au segment, soit par vous, soit par des personnes qui ont partagé le segment avec vous. |
   | Partagé avec | Répertorie les individus ou les groupes (administrateur uniquement) ou toutes les personnes (administrateur uniquement) avec lesquelles vous avez partagé le segment. <p>Lorsqu’un segment est partagé par vous ou avec vous, une icône de partage s’affiche en regard du nom du segment.</p> |
   | Date de modification | Affiche la date de la dernière modification du segment. |
   | Utilisation dans | Indique le nombre de composants dans lesquels le segment est actuellement utilisé. <p>Par exemple, si le segment est utilisé dans 40 projets et 2 alertes, la valeur de cette colonne s’affiche sous la forme [!UICONTROL **42 composants**].</p> <p>Sélectionnez la valeur de cette colonne pour voir la répartition de l’emplacement d’utilisation du segment (par exemple, [!UICONTROL **Projets (40)**], [!UICONTROL **Alertes (2)**]).</p><p>Les segments peuvent être utilisés dans l’un des types de composants suivants :</p> <ul><li>Alertes</li><li>Projets</li><li>Projets planifiés</li><li>Mesures calculées</li></ul><p>Ces informations peuvent vous aider à déterminer si un composant est utile aux utilisateurs de votre entreprise, où il est utilisé et s’il doit être supprimé ou modifié.</p><p>Tenez compte des points suivants lorsque vous affichez cette colonne :</p><ul><li>Ces informations n’incluent pas l’utilisation de l’API, du Report Builder ou du Data Warehouse.</li><li>La colonne [!UICONTROL **Utilisé dans**] ne s’affiche pas par défaut. [Configurez les colonnes](#configure-columns) pour les afficher.</li><li>Si cette colonne ne contient pas de données pour un composant donné mais qu’elle a une date [!UICONTROL **Dernière utilisation**], le composant peut avoir été utilisé dans une analyse sans avoir été enregistré.</li><li>Ces informations sont disponibles uniquement pour les administrateurs système.</li></ul><p>Vous pouvez utiliser le [dictionnaire de données](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md) avec ces informations pour vous aider à suivre et à mieux comprendre comment les composants sont utilisés dans votre organisation.</p> |
   | Dernière utilisation | Affiche la date de la dernière utilisation du segment dans l’un des types de composants suivants : <ul><li>Alertes</li><li>Mesures calculées</li><li>Projets</li><li>Projets planifiés</li><li>Segments</li></ul> <p>Ces informations peuvent vous aider à déterminer si un composant est utile aux utilisateurs de votre entreprise, où il est utilisé et s’il doit être supprimé ou modifié.</p><p>Tenez compte des points suivants lorsque vous affichez cette colonne :</p><ul><li>Ces informations n’incluent pas l’utilisation de l’API, du Report Builder ou du Data Warehouse.</li><li>Pour certains composants, cette colonne peut ne pas contenir de données si le composant a été utilisé pour la dernière fois avant septembre 2023.</li><li>Ces informations sont disponibles uniquement pour les administrateurs système.</li></ul><p>Vous pouvez utiliser le [dictionnaire de données](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md) avec ces informations pour vous aider à suivre et à mieux comprendre comment les composants sont utilisés dans votre organisation. |

   {style="table-layout:auto"}

## Vidéo pratique {#section_B3C5DA22DC5248DBA17C56E03DA2D4F2}

Cette [vidéo d’Adobe Analytics](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/components/segmentation/segment-management-and-sharing.html?lang=fr) explique brièvement comment utiliser le Gestionnaire de segments.


