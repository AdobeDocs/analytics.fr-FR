---
description: Découvrez comment afficher, dupliquer et reclasser par priorité les requêtes de Data Warehouse.
title: Gérer les demandes de Data Warehouse
feature: Data Warehouse
uuid: cdeb764f-56f9-43ec-9228-8ed5a2b58909
exl-id: a399d366-8402-4f4f-9b9f-14b218cd074a
source-git-commit: d929e97a9d9623a8255f16729177d812d59cec05
workflow-type: tm+mt
source-wordcount: '1148'
ht-degree: 4%

---

# Gérer les demandes de Data Warehouse

Vous pouvez afficher et gérer les demandes de Data Warehouse que vous avez effectuées. Seuls les administrateurs peuvent afficher et gérer les requêtes effectuées par d’autres utilisateurs de leur entreprise.

Les sections suivantes décrivent les activités que vous pouvez effectuer lors de la gestion des requêtes.

## Affichage des requêtes

Par défaut, vous pouvez afficher uniquement les requêtes que vous créez, sauf si les utilisateurs ont choisi de rendre leurs requêtes visibles par d’autres personnes de l’organisation (comme décrit dans la section [Paramètres généraux de requête du Data Warehouse](/help/export/data-warehouse/create-request/dw-general-settings.md)). Les administrateurs système peuvent afficher toutes les requêtes.

Pour afficher les requêtes de Data Warehouse :

1. Dans Adobe Analytics, sélectionnez [!UICONTROL **Outils**] > [!UICONTROL **Data Warehouse**].

   La page du Data Warehouse affiche toutes les requêtes que vous avez effectuées. Les données sont affichées dans chaque colonne. Vous pouvez [ configurer les colonnes ](#configure-columns) visibles.

   <!-- add screenshot of main page -->

<!-- describe columns? -->

1. (Facultatif) Cliquez sur le nom de la requête pour afficher une boîte de dialogue qui affiche les informations suivantes : <!-- Check this -->

   * Lorsque le traitement d’une requête a commencé

   * Taux limité : votre entreprise comporte trop de demandes de Data Warehouse en cours d’exécution. La requête est suspendue jusqu’à ce que d’autres requêtes de données soient terminées.

## Modifier des requêtes

Tenez compte des points suivants lors de la modification de requêtes :

* Seules les requêtes configurées pour s’exécuter selon un calendrier peuvent être modifiées.

* Tous les champs associés à la requête ne peuvent pas être modifiés. Les champs qui ne peuvent pas être modifiés sont grisés.

* Les administrateurs qui modifient la requête d’un autre utilisateur doivent choisir un nouveau compte et un nouvel emplacement auxquels ils peuvent accéder.

Pour modifier une requête planifiée :

1. Dans Adobe Analytics, sélectionnez [!UICONTROL **Outils**] > [!UICONTROL **Data Warehouse**].

1. Sur la page du Data Warehouse, sélectionnez la requête à modifier.

   ![Gérer une requête](assets/dw-manage-request.png)

1. Sélectionnez [!UICONTROL **Modifier**].

1. Modifiez la requête selon vos besoins. Les options de configuration réduites ne peuvent pas être modifiées.

   Pour plus d’informations sur chaque option de configuration, voir [Création d’une requête de Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

1. Sélectionnez [!UICONTROL **Enregistrer les modifications**].

## Affichage de l’historique d’une requête

Vous pouvez afficher l’historique des demandes de Data Warehouse que vous avez effectuées.

1. Dans Adobe Analytics, sélectionnez [!UICONTROL **Outils**] > [!UICONTROL **Data Warehouse**].

1. Sur la page du Data Warehouse, sélectionnez la requête dont vous souhaitez afficher l’historique.

   ![Gérer une requête](assets/dw-manage-request.png)

1. Sélectionnez [!UICONTROL **Afficher l&#39;historique**].

   La page [!UICONTROL **Afficher la requête du Data Warehouse**] affiche la liste des diffusions de rapports individuelles associées à la requête.

   Sélectionnez l&#39;icône **Configurer la colonne** ![Icône Configurer la colonne](assets/configure-column-icon.png) pour masquer ou afficher les colonnes qui ne sont pas affichées par défaut.

   ![Page d’historique des requêtes](assets/dw-request-history.png)

   Les colonnes suivantes sont disponibles :

   | Colonne | Description |
   |---------|----------|
   | [!UICONTROL **Date de création**] | Date et heure de création du rapport.<p>Celui-ci s’affiche dans le fuseau horaire de l’utilisateur qui a initié la requête.</p> |
   | [!UICONTROL **Date de début**] | Date et heure de début du rapport.<p>Celui-ci s’affiche dans le fuseau horaire de l’utilisateur qui a initié la requête.</p> |
   | [!UICONTROL **Date d’achèvement**] | Date et heure auxquelles le rapport s’est terminé.<p>Celui-ci s’affiche dans le fuseau horaire de l’utilisateur qui a initié la requête.</p> |
   | [!UICONTROL **Date de mise à jour**] | Date et heure de la dernière mise à jour du rapport.<p>Celui-ci s’affiche dans le fuseau horaire de l’utilisateur qui a initié la requête.</p> |
   | [!UICONTROL **Statut**] | Statut de la diffusion du rapport. Les statuts possibles sont les suivants :<ul><li>[!UICONTROL **Créé**] : le rapport a été créé mais n’a pas encore été traité.</li><li>[!UICONTROL **En attente**] : le rapport attend d’être traité.</li><li>[!UICONTROL **Traitement**] : le rapport est en cours de traitement.</li><li>[!UICONTROL **Completed**] : le rapport est terminé et est désormais disponible.</li><li>[!UICONTROL **Planifié**] : le rapport est planifié, mais n’a pas encore commencé.</li><li>[!UICONTROL **Annulé**] : le rapport a été annulé par l’utilisateur.</li><li>[!UICONTROL **Erreur - Traitement** : &#x200B;] Le rapport a rencontré une erreur et n’a pas pu être traité.</li><li>[!UICONTROL **Erreur - Échec de l’envoi**] : le rapport a été généré avec succès mais n’a pas pu être remis. Vérifiez la [configuration de votre destination](/help/export/data-warehouse/create-request/dw-request-report-destinations.md), puis renvoyez le rapport.</li></ul>. |
   | [!UICONTROL **De**] | Date de début de la période globale incluse dans le rapport.<p>Il s’affiche dans le fuseau horaire de la suite de rapports.</p> |
   | [!UICONTROL **À**] | Date de fin de la période globale incluse dans le rapport. <p>Il s’affiche dans le fuseau horaire de la suite de rapports.</p> |
   | [!UICONTROL **ID de requête hérité**] | Identifiant utilisé pour identifier un rapport dans l’interface de Data Warehouse héritée. Cet identifiant peut être nécessaire lorsque vous contactez l’assistance clientèle d’Adobe. |
   | [!UICONTROL **ID de rapport**] | Identifiant utilisé pour identifier un rapport dans l’interface de Data Warehouse actuelle. Cet identifiant peut être nécessaire lorsque vous contactez l’assistance clientèle d’Adobe. |


1. Sélectionnez une diffusion de rapport, puis l&#39;une des options suivantes :

   | Option | Fonction |
   |---------|----------|
   | [!UICONTROL **Détails de la destination**] | Affiche les détails du compte et de l’emplacement associés à la requête. Il s’agit du compte et de l’emplacement configurés précédemment, comme décrit dans la section [Configuration d’une destination de rapport pour une requête de Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md). |
   | [!UICONTROL **Annuler le rapport**] | Annule le rapport. Vous ne pouvez pas annuler les rapports dont l’état est [!UICONTROL **Completed**] ou [!UICONTROL **Annuler**]. |
   | [!UICONTROL **Réexécuter le rapport**] | Exécute à nouveau le rapport avec les données telles qu’elles étaient lors de son envoi initial. Vous pouvez réexécuter un rapport ayant l’un des états suivants : [!UICONTROL **Annulé**], [!UICONTROL **Terminé**], [!UICONTROL **Erreur - Traitement**] ou [!UICONTROL **Erreur - Échec de l’envoi**]. |
   | [!UICONTROL **Renvoyer le rapport**] | Renvoie le fichier de rapport qui a été généré précédemment. Vous pouvez renvoyer un rapport dont l’un des états est le suivant : [!UICONTROL **Completed**] ou [!UICONTROL **Error - Failure To Send**]. |

## Copie de requêtes

Lorsque vous copiez une requête, toutes les options de configuration sont copiées à partir de la requête d’origine.

1. Dans Adobe Analytics, sélectionnez [!UICONTROL **Outils**] > [!UICONTROL **Data Warehouse**].

1. Sur la page du Data Warehouse, sélectionnez la requête à copier.

   ![Gérer une requête](assets/dw-manage-request.png)

1. Sélectionnez [!UICONTROL **Copier**].

   La page Copier la requête du Data Warehouse s’affiche. Toutes les options de configuration sont copiées à partir de la requête d’origine.

1. Mettez à jour toutes les options de configuration associées à la requête.

   Pour plus d’informations sur chaque option de configuration, voir [Création d’une requête de Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

1. Sélectionnez [!UICONTROL **Enregistrer les modifications**].

## Annuler les requêtes

Seules les requêtes configurées pour s’exécuter selon un calendrier peuvent être annulées.

Pour annuler une requête planifiée :

1. Dans Adobe Analytics, sélectionnez [!UICONTROL **Outils**] > [!UICONTROL **Data Warehouse**].

1. Sur la page du Data Warehouse, sélectionnez la requête à modifier.

   ![Gérer une requête](assets/dw-manage-request.png)

1. Sélectionnez [!UICONTROL **Annuler**].

   La requête ne s’exécutera plus à l’heure planifiée.

## Configuration des colonnes

Vous pouvez configurer les informations affichées pour chaque requête en ajoutant ou en supprimant des colonnes.

1. Sélectionnez l&#39;icône **Configurer les colonnes** dans le coin supérieur droit de la page du Data Warehouse.

   ![Configurer des colonnes](assets/dw-configure-columns.png)

   Les colonnes suivantes sont disponibles :

   | Colonne disponible | Description |
   |---------|----------|
   | Nom de la demande | Nom de la personne qui a créé la requête. |
   | Suite de rapports | Suite de rapports associée à la requête. |
   | Demandé par | L’utilisateur qui a créé la requête. |
   | Date de la demande | Date à laquelle la demande a été faite. |
   | État | Les statuts suivants sont disponibles :<ul><li><p>**Completed** : la requête s’est exécutée avec succès.</p></li><li><p>**Annulé** : la demande a été annulée par l’utilisateur.</p></li><li><p>**Planifié** : la requête est configurée pour s’exécuter selon un calendrier.</p></li><li><p>**Failed** : la demande n’a pas abouti. Si la demande échoue toujours, contactez le service clientèle.</p></li></ul> |

   {style="table-layout:auto"}

1. Assurez-vous que toutes les colonnes à afficher sont sélectionnées. Les colonnes sélectionnées apparaissent sur la page du Data Warehouse et affichent les informations pertinentes.

## Filtrage et tri des requêtes

1. Sélectionnez l’icône **Filtre** dans le rail gauche de la page du Data Warehouse.

   ![Filtrer les requêtes](assets/dw-filter.png)

1. Développez les sections [!UICONTROL **Suites de rapports**], [!UICONTROL **Propriétaire**] ou [!UICONTROL **État**] , puis sélectionnez la manière dont vous souhaitez filtrer les requêtes.

## Recherche de requêtes

1. Dans le champ de recherche situé en haut de la page du Data Warehouse, indiquez le nom de la requête à afficher.

   Les requêtes sont filtrées au fur et à mesure que vous tapez.