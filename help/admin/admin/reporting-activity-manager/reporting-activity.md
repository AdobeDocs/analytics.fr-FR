---
description: Découvrez comment utiliser le gestionnaire des activités de rapport pour diagnostiquer et corriger les problèmes de capacité pendant les heures de pointe de la création de rapports.
title: Gestionnaire des activités de rapport
feature: Admin Tools
mini-toc-levels: 3
exl-id: f638c6a9-1c2c-4936-a787-281269f95afc
source-git-commit: 0e03379550808e5be3e86f0f9ddbbedd026d4910
workflow-type: tm+mt
source-wordcount: '1593'
ht-degree: 24%

---

# Afficher l’activité de création de rapports dans le Gestionnaire d’activités de création de rapports

{{release-limited-testing}}

La variable [!UICONTROL Gestionnaire des activités de création de rapports] permet aux administrateurs de diagnostiquer et de corriger rapidement les problèmes de capacité de création de rapports pendant les périodes de pointe de la création de rapports.

Pour plus d’informations sur la gestion des activités de création de rapports, y compris les principaux avantages et les exigences en matière d’autorisation, voir [Présentation d’Activity Manager dans les rapports](/help/admin/admin/reporting-activity-manager/reporting-activity-overview.md).

## Afficher l’activité de création de rapports pour toutes les suites de rapports {#view-all-report-suites}

1. Dans Adobe Analytics, accédez à **[!UICONTROL Administration]** > **[!UICONTROL Gestionnaire des activités de création de rapports]**.

   Une liste de vos suites de rapports de base activées s’affiche.

   ![file d’attente des rapports](/help/admin/admin/assets/reporting-activity1.png)

1. (Facultatif) Vous pouvez rechercher ou filtrer la liste des suites de rapports :

   * Utilisez le champ de recherche pour rechercher une suite de rapports spécifique. Commencez à saisir le nom ou l’identifiant de la suite de rapports et la liste des mises à jour des suites de rapports au fur et à mesure que vous tapez.

   * Sélectionnez la variable [!UICONTROL **Filtrer**] icon ![Icône Filtrer](assets/filter-icon.png) pour développer la liste des options de filtrage. Vous pouvez filtrer par [!UICONTROL **Favoris**] ou [!UICONTROL **État**].

     Pour marquer une suite de rapports comme favori, sélectionnez l’icône en forme d’étoile à gauche du nom de la suite de rapports.

<!-- (does this option still exist?) 1. (Optional) Select **[!UICONTROL Refresh]** at the top-right to refresh the data. -->

1. Affichez les informations sur l’utilisation de chaque suite de rapports. Vous pouvez sélectionner un en-tête de colonne pour trier le tableau en fonction de cette colonne.

   Les colonnes suivantes sont disponibles :

   | Élément de lʼinterface utilisateur | Description |
   | --- | --- |
   | **[!UICONTROL Suite de rapports]** | La suite de rapports de base dont vous surveillez l’activité de création de rapports. |
   | **[!UICONTROL Suites de rapports virtuelles]** | Affiche toutes les suites de rapports virtuelles qui se trouvent dans cette suite de rapports de base. Les suites de rapports virtuelles rendent les demandes de création de rapports plus complexes en raison de niveaux supplémentaires de filtrage et de segmentation appliqués. Toutes les requêtes provenant des suites de rapports virtuelles sont combinées et descendent dans la suite de rapports de base.<p>Par exemple, si vous avez dix requêtes provenant de cinq suites de rapports virtuelles, il s’agit de 50 requêtes au niveau de la suite de rapports de base. De cette façon, vous pouvez atteindre la capacité maximale très rapidement. |
   | **[!UICONTROL Utilisation des capacités]** | Pourcentage de la capacité de rapport de la suite de rapports utilisée, en temps réel. <p>**Remarque** Même une capacité d’utilisation de 100 % ne signifie pas nécessairement que vous devriez commencer à annuler les demandes de création de rapports. La capacité d’utilisation de 100 % peut être saine si le temps d’attente moyen est raisonnable. La capacité d’utilisation de 100 % peut indiquer un problème si le nombre de requêtes en file d’attente augmente également.</p> |
   | **[!UICONTROL Requêtes en attente]** | Nombre de demandes en attente de traitement. <!-- ??? --> |
   | **[!UICONTROL Durée de la file d’attente]** | Temps d’attente moyen pour chaque demande à traiter. <!-- ???? --> |
   | **[!UICONTROL Statut]** | Les états possibles sont les suivants : <ul><li>[!UICONTROL **Actif**] (bleu) : les rapports ont été exécutés sur la suite de rapports et leur activité est surveillée.</li><li>[!UICONTROL **Inactif**] (gris) : aucun rapport n’a jamais été exécuté sur la suite de rapports. Cet état s’affiche uniquement lors de la création des suites de rapports.</li></ul> |

   {style="table-layout:auto"}

## Afficher une activité de rapport pour une seule suite de rapports

1. Dans Adobe Analytics, sélectionnez [!UICONTROL **Administration**] > [!UICONTROL **Gestionnaire des activités de création de rapports**].

1. Sélectionnez le titre associé de la suite de rapports pour laquelle vous souhaitez afficher les détails.

   Les données d’activité de création de rapports s’affichent pour la suite de rapports que vous avez sélectionnée.

   <!-- Need to update this screenshot: ![report suite](assets/indiv-report-ste.png) -->

1. Utilisez les graphiques et les tableaux disponibles pour comprendre l’activité de création de rapports dans la suite de rapports.

   * [Affichage des graphiques](#view-graphs)

   * [Afficher le tableau](#view-data-in-the-table)

### Affichage des graphiques

Les graphiques suivants sont disponibles pour vous aider à mieux comprendre l’activité en cours dans la suite de rapports. Si les graphiques ne sont pas visibles, sélectionnez la variable [!UICONTROL **Afficher les graphiques**] bouton .

#### Graphique d’utilisation {#utilization}

Le graphique Utilisation montre l’utilisation des rapports pour la suite de rapports sélectionnée au cours des deux dernières heures.

* L’axe X affiche la capacité d’utilisation des rapports au cours des deux dernières heures.
* L’axe des ordonnées affiche le pourcentage de capacité d’utilisation des rapports, par minute.
* Vous pouvez survoler le graphique avec la souris pour afficher les points dans lesquels le pourcentage de capacité d’utilisation a été le plus élevé au cours de cette minute.

  ![graphique d’utilisation](assets/utilization-graph.png)

#### Graphique Utilisateurs distincts

Le graphique Utilisateurs distincts présente l’activité de création de rapports pour la suite de rapports sélectionnée au cours des deux dernières heures.

* L’axe X affiche une période de 2 heures.
* L’axe des ordonnées indique le nombre d’utilisateurs qui ont effectué des demandes de création de rapports, par minute.
* Vous pouvez survoler le graphique avec la souris afin d’afficher les points dans le temps où le nombre maximal d’utilisateurs a été atteint au cours de cette minute.

  ![Graphique Utilisateurs distincts](assets/distinct-users-graph.png)

<!--

#### Requests graph

The Requests graph shows the number of processed and completed requests for the selected report suite over the last 2 hours. 

* The x-axis shows a 2-hour time frame.
* The y-axis shows the number of processed requests (in purple) and completed requests (in green), by minute.
* You can hover over the chart to view points in time where the maximum number of requests was highest for that minute.

   ![Distinct Users graph](assets/requests-graph.png)

#### Queueing graph

The Queueing graph shows the average queue wait time (in seconds) for reporting requests for the selected report suite over the last 2 hours. 

* The x-axis shows a 2-hour time frame.
* The y-axis shows the average wait time (in seconds).
* You can hover over the chart to view points in time where the maximum average wait time was highest for that minute.

   ![Distinct Users graph](assets/queueing-graph.png)

-->

### Afficher le tableau {#view-table}

Vous pouvez choisir d’afficher les données en sélectionnant l’un des onglets suivants en haut du tableau de données : [!UICONTROL **Requête**], [!UICONTROL **Utilisateur**], [!UICONTROL **Projet**], ou [!UICONTROL **Application**].

>[!TIP]
>
>Vous pouvez sélectionner [!UICONTROL **Masquage des graphiques**] pour afficher uniquement le tableau.

![onglets de tableau](assets/indiv-report-ste-table-tabs.png)

#### Afficher les données par requête

Lorsque vous sélectionnez la variable [!UICONTROL **Requête**] , les colonnes suivantes sont disponibles dans le tableau :

| Colonne | Description |
| --- | --- |
| [!UICONTROL **ID de demande**] | Peut être utilisé à des fins de dépannage. |
| [!UICONTROL **Durée d’exécution**] | Durée d’exécution de la requête. |
| [!UICONTROL **Heure de début**] | Lorsque le traitement de la demande a commencé (en fonction de l’heure locale de l’administrateur). |
| [!UICONTROL **Temps d’attente**] | Durée pendant laquelle la requête a été en attente avant d’être traitée. Généralement à « 0 » lorsque la capacité est suffisante. |
| [!UICONTROL **Application**] | Les applications prises en charge par le [!UICONTROL Gestionnaire des activités de rapport] sont les suivantes : <ul><li>Interface utilisateur d’Analysis Workspace</li><li>Projets planifiés d’espace de travail</li><li>Report Builder</li><li>Interface utilisateur de Builder : Segment, Mesures calculées, Annotations, Audiences, etc.</li><li>Appels d’API à partir de la version d’API 1.4 ou 2.0</li><li>Alertes intelligentes</li></ul> |
| [!UICONTROL **Utilisateur**] | L’utilisateur qui a initié la requête. Si la valeur de cette colonne est [!UICONTROL **Non reconnu**], cela signifie que l’utilisateur se trouve dans une société de connexion dans laquelle vous ne disposez pas d’autorisations d’administration. |
| [!UICONTROL **Projet**] | Noms de projets d’espace de travail enregistrés, ID de rapport API, etc. (Les métadonnées peuvent varier d’une application à l’autre.) |
| [!UICONTROL **Statut**] | Indicateurs de statut : <ul><li>**En cours d’exécution** : la demande est en cours de traitement.</li><li>**En attente** : la demande est en attente de traitement.</li></ul> |
| [!UICONTROL **Complexité**] | Toutes les demandes ne nécessitent pas le même temps de traitement. La complexité de la requête peut vous aider à obtenir une idée générale du temps nécessaire au traitement de la requête. Valeurs possibles : <ul><li>[!UICONTROL **Faible**]</li><li>[!UICONTROL **Méthode**]</li><li>[!UICONTROL **Élevé**]</li></ul>Cette valeur est influencée par les valeurs des colonnes suivantes :<ul><li>[!UICONTROL **Limites des mois**]</li><li>[!UICONTROL **Colonnes**]</li><li>[!UICONTROL **Segments**]</li></ul> |
| [!UICONTROL **Limites mensuelles**] | Nombre de mois inclus dans une requête. Cela ajoute à la complexité de la requête. |
| [!UICONTROL **Colonnes**] | Nombre de mesures et de ventilations dans la requête. Cela ajoute à la complexité de la requête. |
| [!UICONTROL **Segments**] | Le nombre de segments appliqués à la requête. Cela ajoute à la complexité de la requête. |

{style="table-layout:auto"}

#### Affichage des données par utilisateur

Lorsque vous sélectionnez la variable [!UICONTROL **Utilisateur**] , les colonnes suivantes sont disponibles dans le tableau :

| Colonne | Description |
| --- | --- |
| [!UICONTROL **Utilisateur**] | L’utilisateur qui a initié la requête. Si la valeur de cette colonne est [!UICONTROL **Non reconnu**], cela signifie que l’utilisateur se trouve dans une société de connexion dans laquelle vous ne disposez pas d’autorisations d’administration. |
| [!UICONTROL **Nombre de demandes**] | Nombre de requêtes initiées par l’utilisateur. |
| [!UICONTROL **Nombre de projets**] | Nombre de projets associés à l’utilisateur. <!-- ??? --> |
| [!UICONTROL **Application**] | Les applications prises en charge par le [!UICONTROL Gestionnaire des activités de rapport] sont les suivantes : <ul><li>Interface utilisateur d’Analysis Workspace</li><li>Projets planifiés d’espace de travail</li><li>Report Builder</li><li>Interface utilisateur de Builder : Segment, Mesures calculées, Annotations, Audiences, etc.</li><li>Appels d’API à partir de la version d’API 1.4 ou 2.0</li><li>Alertes intelligentes</li></ul> |
| [!UICONTROL **Complexité moyenne**] | La complexité moyenne des requêtes initiées par l’utilisateur. <p>Toutes les demandes ne nécessitent pas le même temps de traitement. La complexité de la requête peut vous aider à obtenir une idée générale du temps nécessaire au traitement de la requête.</p><p>La valeur de cette colonne est basée sur un score déterminé par les valeurs des colonnes suivantes :</p><ul><li>[!UICONTROL **Limites mensuelles Moy.**]</li><li>[!UICONTROL **Colonnes moy.**]</li><li>[!UICONTROL **Segments moy.**]</li></ul> |
| [!UICONTROL **Limites mensuelles Moy.**] | Nombre moyen de mois inclus dans les requêtes. Cela ajoute à la complexité moyenne de la requête. |
| [!UICONTROL **Colonnes moy.**] | Nombre moyen de mesures et de ventilations dans les requêtes incluses. Cela ajoute à la complexité moyenne. |
| [!UICONTROL **Segments moy.**] | Nombre moyen de segments appliqués aux requêtes incluses. Cela ajoute à la complexité moyenne. |

{style="table-layout:auto"}

#### Affichage des données par projet

Lorsque vous sélectionnez la variable [!UICONTROL **Projet**] , les colonnes suivantes sont disponibles dans le tableau :

| Colonne | Description |
| --- | --- |
| [!UICONTROL **Projet**] | Projet dans lequel les requêtes ont été lancées. |
| [!UICONTROL **Nombre de demandes**] | Nombre de requêtes associées au projet. |
| [!UICONTROL **Nombre d’utilisateurs**] | Nombre d’utilisateurs associés au projet. <!-- ??? --> |
| [!UICONTROL **Application**] | Les applications prises en charge par le [!UICONTROL Gestionnaire des activités de rapport] sont les suivantes : <ul><li>Interface utilisateur d’Analysis Workspace</li><li>Projets planifiés d’espace de travail</li><li>Report Builder</li><li>Interface utilisateur de Builder : Segment, Mesures calculées, Annotations, Audiences, etc.</li><li>Appels d’API à partir de la version d’API 1.4 ou 2.0</li><li>Alertes intelligentes</li></ul> |
| [!UICONTROL **Complexité moyenne**] | La complexité moyenne des demandes incluses dans le projet. <p>Toutes les demandes ne nécessitent pas le même temps de traitement. La complexité de la requête peut vous aider à obtenir une idée générale du temps nécessaire au traitement de la requête.</p><p>La valeur de cette colonne est basée sur un score déterminé par les valeurs des colonnes suivantes :</p><ul><li>[!UICONTROL **Limites mensuelles Moy.**]</li><li>[!UICONTROL **Colonnes moy.**]</li><li>[!UICONTROL **Segments moy.**]</li></ul> |
| [!UICONTROL **Limites mensuelles Moy.**] | Nombre moyen de mois inclus dans les requêtes. Cela ajoute à la complexité moyenne de la requête. |
| [!UICONTROL **Colonnes moy.**] | Nombre moyen de mesures et de ventilations dans les requêtes incluses. Cela ajoute à la complexité moyenne. |
| [!UICONTROL **Segments moy.**] | Nombre moyen de segments appliqués aux requêtes incluses. Cela ajoute à la complexité moyenne. |

{style="table-layout:auto"}

#### Affichage des données par application

Lorsque vous sélectionnez la variable [!UICONTROL **Application**] , les colonnes suivantes sont disponibles dans le tableau :

| Colonne | Description |
| --- | --- |
| [!UICONTROL **Application**] | L’application dans laquelle les requêtes ont été lancées. |
| [!UICONTROL **Nombre de demandes**] | Nombre de requêtes associées à l’application. |
| [!UICONTROL **Nombre d’utilisateurs**] | Nombre d’utilisateurs associés à l’application. <!--???--> |
| [!UICONTROL **Nombre de projets**] | Nombre de projets associés à l’application. <!--???--> |
| [!UICONTROL **Complexité moyenne**] | La complexité moyenne des demandes associées à l’application. <p>Toutes les demandes ne nécessitent pas le même temps de traitement. La complexité de la requête peut vous aider à obtenir une idée générale du temps nécessaire au traitement de la requête.</p><p>La valeur de cette colonne est basée sur un score déterminé par les valeurs des colonnes suivantes :</p>La valeur de cette colonne est basée sur un score déterminé par les valeurs des colonnes suivantes :<ul><li>[!UICONTROL **Limites mensuelles Moy.**]</li><li>[!UICONTROL **Colonnes moy.**]</li><li>[!UICONTROL **Segments moy.**]</li></ul> |
| [!UICONTROL **Limites mensuelles Moy.**] | Nombre moyen de mois inclus dans les requêtes. Cela ajoute à la complexité moyenne de la requête. |
| [!UICONTROL **Colonnes moy.**] | Nombre moyen de mesures et de ventilations dans les requêtes incluses. Cela ajoute à la complexité moyenne. |
| [!UICONTROL **Segments moy.**] | Nombre moyen de segments appliqués aux requêtes incluses. Cela ajoute à la complexité moyenne. |

{style="table-layout:auto"}

<!--

### Filter

You can filter the table by Application (see list in the table below), by User, and by Project.

![filter](/help/admin/admin/assets/filter.png)

### Summary Numbers {#summary}

![filter](/help/admin/admin/assets/summary_numbers.png)

The Summary Numbers show the following information:

| Summary Number | Description |
| --- | --- |
| [!UICONTROL **Users**] | The number of users that are currently sending reporting requests to this report suite. |
| [!UICONTROL **Projects**] | Workspace projects, Report Builder workbooks, etc.  | 
| [!UICONTROL **Queries**] | The number of queries currently running. |
| [!UICONTROL **Average Wait Time**] | The average wait time for all running queries.  |
| [!UICONTROL **Usage Capacity**] | The current usage capacity for this report suite. |

{style="table-layout:auto"}

-->


