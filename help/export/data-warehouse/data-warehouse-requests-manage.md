---
description: Découvrez comment afficher, dupliquer et redéfinir les priorités des requêtes Data Warehouse.
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

Vous pouvez afficher et gérer les requêtes Data Warehouse que vous avez effectuées. Seuls les administrateurs peuvent afficher et gérer les demandes effectuées par d’autres utilisateurs de leur entreprise.

Les sections suivantes décrivent les activités que vous pouvez effectuer lors de la gestion des requêtes.

## Afficher les requêtes

Par défaut, vous ne pouvez afficher que les requêtes que vous créez, sauf si les utilisateurs et utilisatrices ont choisi de rendre leurs requêtes visibles par d’autres membres de l’organisation (comme décrit dans les paramètres généraux des requêtes [Data Warehouse](/help/export/data-warehouse/create-request/dw-general-settings.md)). Les administrateurs système peuvent afficher toutes les demandes.

Pour afficher les requêtes Data Warehouse :

1. Dans Adobe Analytics, sélectionnez [!UICONTROL **Outils**] > [!UICONTROL **Data Warehouse**].

   La page Data Warehouse affiche toutes les requêtes que vous avez effectuées. Les données sont affichées dans chaque colonne. Vous pouvez [configurer les colonnes](#configure-columns) visibles.

   <!-- add screenshot of main page -->

<!-- describe columns? -->

1. (Facultatif) Cliquez sur le nom de la requête pour afficher une boîte de dialogue qui affiche les informations suivantes : <!-- Check this -->

   * Lorsqu’une demande a commencé à être traitée

   * Taux limité : votre organisation a trop de requêtes Data Warehouse en cours d’exécution. La requête est suspendue jusqu’à ce que d’autres requêtes de données soient terminées.

## Requêtes de modification

Tenez compte des points suivants lors de la modification des requêtes :

* Seules les requêtes configurées pour s’exécuter selon un planning peuvent être modifiées.

* Tous les champs associés à la demande ne peuvent pas être modifiés. Les champs qui ne peuvent pas être modifiés apparaissent grisés.

* Les administrateurs qui modifient la demande d’un autre utilisateur doivent choisir un nouveau compte et un nouvel emplacement auxquels ils peuvent accéder.

Pour modifier une demande planifiée :

1. Dans Adobe Analytics, sélectionnez [!UICONTROL **Outils**] > [!UICONTROL **Data Warehouse**].

1. Sur la page Data Warehouse, sélectionnez la requête à modifier.

   ![Gérer une requête](assets/dw-manage-request.png)

1. Sélectionnez [!UICONTROL **Modifier**].

1. Modifiez la requête selon vos besoins. Les options de configuration estompées ne peuvent pas être modifiées.

   Pour plus d’informations sur chaque option de configuration, voir [ Création d’une requête Data Warehouse ](/help/export/data-warehouse/create-request/t-dw-create-request.md).

1. Sélectionnez [!UICONTROL **Enregistrer les modifications**].

## Afficher l’historique d’une demande

Vous pouvez afficher l’historique de toutes les requêtes Data Warehouse que vous avez effectuées.

1. Dans Adobe Analytics, sélectionnez [!UICONTROL **Outils**] > [!UICONTROL **Data Warehouse**].

1. Sur la page Data Warehouse , sélectionnez la requête dont vous souhaitez afficher l’historique.

   ![Gérer une requête](assets/dw-manage-request.png)

1. Sélectionnez [!UICONTROL **Afficher l’historique**].

   La page [!UICONTROL **Afficher la requête Data Warehouse**] affiche une liste des diffusions de rapports individuelles associées à la requête.

   Sélectionnez l’icône **Configurer la colonne** ![Configurer la colonne](assets/configure-column-icon.png) pour masquer ou afficher les colonnes qui ne sont pas affichées par défaut.

   ![Page d’historique des demandes](assets/dw-request-history.png)

   Les colonnes suivantes sont disponibles :

   | Colonne | Description |
   |---------|----------|
   | [!UICONTROL **Date de création**] | Date et heure de création du rapport.<p>Elle s’affiche dans le fuseau horaire de l’utilisateur qui a initié la demande.</p> |
   | [!UICONTROL **Date de début**] | Date et heure de début du rapport.<p>Elle s’affiche dans le fuseau horaire de l’utilisateur qui a initié la demande.</p> |
   | [!UICONTROL **Date de fin**] | Date et heure auxquelles le rapport s’est terminé.<p>Elle s’affiche dans le fuseau horaire de l’utilisateur qui a initié la demande.</p> |
   | [!UICONTROL **Date de mise à jour**] | Date et heure de la dernière mise à jour du rapport.<p>Elle s’affiche dans le fuseau horaire de l’utilisateur qui a initié la demande.</p> |
   | [!UICONTROL **Statut**] | Statut de la diffusion du rapport. Les statuts possibles sont les suivants :<ul><li>[!UICONTROL **Créé**] : le rapport a été créé mais n’a pas encore été traité.</li><li>[!UICONTROL **En attente**] : le rapport est en attente de traitement.</li><li>[!UICONTROL **Traitement**] : le rapport est en cours de traitement.</li><li>[!UICONTROL **Terminé**] : le rapport est terminé et est maintenant disponible.</li><li>[!UICONTROL **Planifié**] : le rapport est planifié, mais n’a pas encore commencé.</li><li>[!UICONTROL **Annulé**] : le rapport a été annulé par l&#39;utilisateur.</li><li>[!UICONTROL **Erreur - Traitement** :] le rapport a rencontré une erreur et n’a pas pu être traité.</li><li>[!UICONTROL **Erreur - Échec de l’envoi**] : le rapport a été généré avec succès, mais n’a pas pu être remis. Vérifiez la [configuration de la destination](/help/export/data-warehouse/create-request/dw-request-report-destinations.md), puis renvoyez le rapport.</li></ul>. |
   | [!UICONTROL **De**] | Date de début de la période globale incluse dans le rapport.<p>Elle s’affiche dans le fuseau horaire de la suite de rapports.</p> |
   | [!UICONTROL **À**] | Date de fin de la période globale incluse dans le rapport. <p>Elle s’affiche dans le fuseau horaire de la suite de rapports.</p> |
   | [!UICONTROL **ID de requête hérité**] | Identifiant utilisé pour identifier un rapport dans l’interface Data Warehouse héritée. Cet identifiant peut être nécessaire lors du contact avec l’assistance clientèle d’Adobe. |
   | [!UICONTROL **Identifiant du rapport**] | Identifiant utilisé pour identifier un rapport dans l’interface Data Warehouse actuelle. Cet identifiant peut être nécessaire lors du contact avec l’assistance clientèle d’Adobe. |


1. Sélectionnez une diffusion de rapport, puis l&#39;une des options suivantes :

   | Option | Fonction |
   |---------|----------|
   | [!UICONTROL **Détails de la destination**] | Affiche les détails du compte et de l’emplacement associés à la requête. Il s’agit du compte et de l’emplacement qui ont été configurés précédemment, comme décrit dans [Configurer une destination de rapport pour une requête Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md). |
   | [!UICONTROL **Annuler le rapport**] | Annule le rapport. Vous ne pouvez pas annuler des rapports dont le statut est [!UICONTROL **Terminé**] ou [!UICONTROL **Annulé**]. |
   | [!UICONTROL **Réexécuter le rapport**] | Réexécute le rapport avec les données telles qu’elles étaient lors de son envoi initial. Vous pouvez réexécuter un rapport présentant l’un des statuts suivants : [!UICONTROL **Annulé**], [!UICONTROL **Terminé**], [!UICONTROL **Erreur - Traitement**] ou [!UICONTROL **Erreur - Échec de l’envoi**]. |
   | [!UICONTROL **Renvoyer le rapport**] | Renvoie le fichier de rapport précédemment généré. Vous pouvez renvoyer un rapport dont le statut est l’un des suivants : [!UICONTROL **Terminé**] ou [!UICONTROL **Erreur - Échec de l’envoi**]. |

## Copier des requêtes

Lorsque vous copiez une demande, toutes les options de configuration sont copiées à partir de la demande d’origine.

1. Dans Adobe Analytics, sélectionnez [!UICONTROL **Outils**] > [!UICONTROL **Data Warehouse**].

1. Sur la page Data Warehouse, sélectionnez la requête à copier.

   ![Gérer une requête](assets/dw-manage-request.png)

1. Sélectionnez [!UICONTROL **Copier**].

   La page Copier la requête Data Warehouse s’affiche. Toutes les options de configuration sont copiées à partir de la requête d’origine.

1. Mettez à jour toutes les options de configuration associées à la requête.

   Pour plus d’informations sur chaque option de configuration, voir [ Création d’une requête Data Warehouse ](/help/export/data-warehouse/create-request/t-dw-create-request.md).

1. Sélectionnez [!UICONTROL **Enregistrer les modifications**].

## Annuler les requêtes

Seules les requêtes configurées pour s’exécuter selon un planning peuvent être annulées.

Pour annuler une demande planifiée :

1. Dans Adobe Analytics, sélectionnez [!UICONTROL **Outils**] > [!UICONTROL **Data Warehouse**].

1. Sur la page Data Warehouse, sélectionnez la requête à modifier.

   ![Gérer une requête](assets/dw-manage-request.png)

1. Sélectionnez [!UICONTROL **Annuler**].

   La demande ne s’exécutera plus à l’heure planifiée.

## Configurer les colonnes

Vous pouvez configurer les informations affichées pour chaque requête en ajoutant ou en supprimant des colonnes.

1. Sélectionnez l’icône **Configurer les colonnes** dans le coin supérieur droit de la page Data Warehouse.

   ![Configurer les colonnes](assets/dw-configure-columns.png)

   Les colonnes suivantes sont disponibles :

   | Colonne disponible | Description |
   |---------|----------|
   | Nom de la demande | Nom de la personne qui a créé la demande. |
   | Suite de rapports | Suite de rapports associée à la requête. |
   | Demandé par | L’utilisateur qui a créé la demande. |
   | Date de la demande | Date à laquelle la requête a été effectuée. |
   | État | Les statuts suivants sont disponibles :<ul><li><p>**Terminé** : la demande s’est exécutée correctement.</p></li><li><p>**Annulé** : la demande a été annulée par l&#39;utilisateur.</p></li><li><p>**Planifié** : la demande est configurée pour s’exécuter selon un planning.</p></li><li><p>**Échec** : la requête n’a pas abouti. Si la requête continue d’échouer, contactez le service clientèle.</p></li></ul> |

   {style="table-layout:auto"}

1. Assurez-vous que toutes les colonnes que vous souhaitez afficher sont sélectionnées. Les colonnes sélectionnées s’affichent sur la page Data Warehouse et affichent les informations pertinentes.

## Filtrer et trier les requêtes

1. Sélectionnez l’icône **Filtrer** dans le rail de gauche de la page Data Warehouse.

   ![Filtrer les requêtes](assets/dw-filter.png)

1. Développez les sections [!UICONTROL **Suites de rapports**], [!UICONTROL **Propriétaire**] ou [!UICONTROL **Statut**], puis sélectionnez le mode de filtrage des requêtes.

## Rechercher des requêtes

1. Dans le champ de recherche en haut de la page Data Warehouse, indiquez le nom de la requête à afficher.

   Les requêtes sont filtrées au fur et à mesure que vous les saisissez.