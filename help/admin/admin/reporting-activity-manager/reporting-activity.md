---
description: Découvrez comment utiliser le gestionnaire des activités de rapport pour diagnostiquer et corriger les problèmes de capacité pendant les heures de pointe de la création de rapports.
title: Gestionnaire des activités de rapport
feature: Admin Tools
mini-toc-levels: 3
exl-id: f638c6a9-1c2c-4936-a787-281269f95afc
source-git-commit: 75d8705170169a0ef9f1ee59b12e4bb2c3afac7a
workflow-type: tm+mt
source-wordcount: '1989'
ht-degree: 14%

---

# Afficher l’activité de rapport dans le Gestionnaire des activités de rapport

Le [!UICONTROL gestionnaire des activités de rapport] permet aux administrateurs de diagnostiquer et de résoudre rapidement les problèmes de capacité de rapport pendant les heures de pointe de la création de rapports.

Pour plus d’informations sur le gestionnaire des activités de rapport, y compris les principaux avantages et les exigences d’autorisation, voir [Présentation du gestionnaire des activités de rapport](/help/admin/admin/reporting-activity-manager/reporting-activity-overview.md).

## Afficher l’activité de rapport pour toutes les suites de rapports {#view-all-report-suites}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_tools_reportingactivitymanager_connections"
>title="Connexions"
>abstract="Ce tableau présente les connexions pour lesquelles vous disposez des droits de gestion de l’activité de création de rapports. Des informations sur chaque connexion sont disponibles dans chaque colonne du tableau."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="tools_reportingactivitymanager_connections"
>title="Connexions"
>abstract="Ce tableau présente les connexions pour lesquelles vous disposez des droits de gestion de l’activité de création de rapports. Des informations sur chaque connexion sont disponibles dans chaque colonne du tableau."

<!-- markdownlint-enable MD034 -->

1. Dans Adobe Analytics, accédez à **[!UICONTROL Admin]** > **[!UICONTROL Gestionnaire des activités de rapports]**.

   Une liste de vos suites de rapports de base activées s’affiche.

   ![file d’attente des rapports](assets/reporting-activity1.png)

1. (Facultatif) Vous pouvez rechercher ou filtrer la liste des suites de rapports :

   * Utilisez le champ de recherche pour rechercher une suite de rapports spécifique. Commencez à saisir le nom ou l’identifiant de la suite de rapports et la liste des mises à jour au fur et à mesure que vous tapez.

   * Sélectionnez l’icône [!UICONTROL **Filtre**] ![Icône Filtre](assets/filter-icon.png) pour développer la liste des options de filtre. Vous pouvez filtrer par [!UICONTROL **Favoris**] ou [!UICONTROL **Statut**].

     Pour marquer une suite de rapports comme favori, sélectionnez l’icône en forme d’étoile à gauche du nom de la suite de rapports.

     <!-- (does this option still exist?) 1. (Optional) Select **[!UICONTROL Refresh]** at the top-right to refresh the data. -->

1. Affichez les informations d’utilisation de chaque suite de rapports. Les données affichées dans le tableau représentent l’activité de création de rapports pour la suite de rapports au moment du dernier chargement de la page.

   Les colonnes suivantes sont disponibles :

   | Élément de lʼinterface utilisateur | Description |
   | --- | --- |
   | **[!UICONTROL Suite de rapports]** | La suite de rapports de base dont vous surveillez l’activité de création de rapports. |
   | **[!UICONTROL Suites de rapports virtuelles]** | Affiche toutes les suites de rapports virtuelles qui se trouvent dans cette suite de rapports de base. Les suites de rapports virtuelles rendent les demandes de création de rapports plus complexes en raison de niveaux supplémentaires de filtrage et de segmentation appliqués. Toutes les requêtes provenant des suites de rapports virtuelles sont combinées dans la suite de rapports de base. |
   | **[!UICONTROL Utilisation des capacités]** | Pourcentage de la capacité de création de rapports de la suite de rapports qui est utilisé, en temps réel. <p>**Remarque** une capacité d’utilisation de 100 % ne signifie pas nécessairement que vous devez commencer immédiatement à annuler les demandes de création de rapports. Une capacité d’utilisation de 100 % peut être saine si le temps d’attente moyen est raisonnable. D’un autre côté, une capacité d’utilisation de 100 % peut suggérer un problème si le nombre de requêtes en file d’attente augmente également.</p> |
   | **[!UICONTROL Demandes mises en file d’attente]** | Nombre de requêtes en attente de traitement. <!-- ??? --> |
   | **[!UICONTROL Temps d’attente dans la file]** | Temps d’attente moyen avant que les requêtes ne commencent à être traitées. <!-- ???? --> |
   | **[!UICONTROL Statut]** | Les statuts possibles sont les suivants : <ul><li>[!UICONTROL **Actif**] (bleu) : des rapports ont été exécutés sur la suite de rapports au cours des 2 dernières heures. Les données affichées dans le tableau représentent la capacité de création de rapports de la suite de rapports au moment du dernier chargement de la page.</li><li>[!UICONTROL **Inactif**] (gris) : aucun rapport n’a été exécuté sur la suite de rapports au cours des 2 dernières heures. Aucune donnée n’est donc affichée pour la suite de rapports.</li></ul> |

   {style="table-layout:auto"}

## Affichage de l’activité de création de rapports pour une seule suite de rapports

1. Dans Adobe Analytics, sélectionnez [!UICONTROL **Admin**] > [!UICONTROL **Gestionnaire des activités de rapports**].

1. Sélectionnez le titre lié de la suite de rapports pour laquelle vous souhaitez afficher les détails.

   Les données des activités de rapport s’affichent pour la suite de rapports que vous avez sélectionnée.

   <!-- Need to update this screenshot: ![report suite](assets/indiv-report-ste.png) -->

1. (Facultatif) Lorsqu’une connexion se charge pour la première fois dans le gestionnaire des activités de rapports, les données affichées représentent les mesures d’utilisation actuelles. Pour afficher les mesures mises à jour après le chargement initial, cliquez sur le bouton [!UICONTROL **Actualiser**] pour actualiser manuellement la page.

1. Utilisez les graphiques et les tableaux disponibles pour comprendre l’activité de création de rapports dans la suite de rapports.

   * [Afficher les graphiques](#view-graphs)

   * [Afficher le tableau](#view-table)

### Afficher les graphiques

Les graphiques suivants sont disponibles pour vous aider à mieux comprendre l’activité qui se produit dans la suite de rapports.

Si les graphiques ne sont pas visibles, cliquez sur le bouton [!UICONTROL **Afficher les graphiques**].

#### Graphique d’utilisation {#utilization}

Le graphique Utilisation présente l’utilisation des rapports pour la suite de rapports sélectionnée au cours des deux dernières heures.

Passez la souris sur le graphique pour afficher les points dans le temps où le pourcentage de capacité d’utilisation a été le plus élevé pendant cette minute.

* **Axe X** : capacité d’utilisation des rapports au cours des deux dernières heures.
* **Axe Y** : pourcentage de capacité d’utilisation des rapports, par minute.

  ![graphique d’utilisation](assets/utilization-graph.png)

#### Graphique Utilisateurs distincts

Le graphique Utilisateurs distincts affiche l’activité de création de rapports pour la suite de rapports sélectionnée au cours des 2 dernières heures.

Passez la souris sur le graphique pour afficher les points dans le temps où le nombre maximal d’utilisateurs et d’utilisatrices a été le plus élevé pendant cette minute.

* **Axe X** : activité de création de rapports sur la dernière période de 2 heures.
* **Axe Y** : nombre d’utilisateurs et d’utilisatrices qui ont envoyé des demandes de création de rapports, par minute.

  ![Graphique Utilisateurs distincts](assets/distinct-users-graph.png)

#### Graphique Demandes

Le graphique Demandes indique le nombre de demandes traitées et mises en file d’attente pour la suite de rapports sélectionnée au cours des 2 dernières heures.

Passez la souris sur le graphique pour afficher les points dans le temps où le nombre maximal de requêtes a été le plus élevé pendant cette minute.

* **Axe X** : nombre de requêtes traitées et terminées au cours des dernières 2 heures.
* **Axe Y** : nombre de demandes traitées (en vert) et de demandes mises en file d’attente (en violet), par minute.

  ![Graphique Utilisateurs distincts](assets/requests-graph.png)

#### Graphique de file d’attente

Le graphique File d’attente indique le temps d’attente moyen des demandes de création de rapports dans la file d’attente (en secondes) pour la suite de rapports sélectionnée au cours des deux dernières heures.

Passez la souris sur le graphique pour afficher les points dans le temps où le temps d’attente moyen maximal a été le plus élevé pendant cette minute.

* **Axe X** : temps d’attente moyen des demandes de création de rapports dans la file d’attente au cours de la dernière période de 2 heures.
* **Axe Y** : temps d’attente moyen (en secondes).

  ![Graphique Utilisateurs distincts](assets/queueing-graph.png)

### Afficher le tableau {#view-table}

Lors de l’affichage du tableau, tenez compte des points suivants :

* Vous pouvez choisir d’afficher les données en choisissant l’un des onglets suivants en haut du tableau de données : [!UICONTROL **Requête**], [!UICONTROL **Utilisateur**], [!UICONTROL **Projet**] ou [!UICONTROL **Application**].

* Vous pouvez rechercher ou filtrer la liste des connexions :

   * Utilisez le champ de recherche pour rechercher une connexion spécifique. Commencez à saisir le nom ou l’identifiant de la connexion et la liste des connexions est mise à jour au fur et à mesure que vous tapez.

   * Sélectionnez l’icône [!UICONTROL **Filtre**] ![Icône Filtre](assets/filter-icon.png) pour développer la liste des options de filtre. Vous pouvez filtrer par [!UICONTROL **Statut**], [!UICONTROL **Complexité**], [!UICONTROL **Application**], [!UICONTROL **Utilisateur**] ou [!UICONTROL **Projet**].

   * Vous pouvez sélectionner [!UICONTROL **Masquer les graphiques**] pour afficher uniquement le tableau.

![onglets de tableau](assets/report-activity-tabs.png)

#### Afficher les données par demande

Lorsque vous sélectionnez l’onglet [!UICONTROL **Requête**], les colonnes suivantes sont disponibles dans le tableau :

| Colonne | Description |
| --- | --- |
| [!UICONTROL **ID de requête**] | Identifiant unique pouvant être utilisé à des fins de dépannage. Pour copier l’ID, sélectionnez la demande, puis sélectionnez l’option [!UICONTROL **Copier les ID de la demande**]. |
| [!UICONTROL **Exécution temporelle**] | Durée d’exécution de la requête. |
| [!UICONTROL **Heure de début**] | Date à laquelle le traitement de la demande a commencé (en fonction de l’heure locale de l’administrateur). |
| [!UICONTROL **Temps d’attente**] | Durée pendant laquelle la demande a été en attente avant d’être traitée. Cette valeur est généralement égale à « 0 » lorsqu’il y a suffisamment de capacité. |
| [!UICONTROL **Application**] | Les applications prises en charge par le [!UICONTROL Gestionnaire des activités de rapport] sont les suivantes : <ul><li>Interface utilisateur d’Analysis Workspace</li><li>Projets planifiés d’espace de travail</li><li>Report Builder</li><li>Interface utilisateur de Builder : Segment, Mesures calculées, Annotations, Audiences, etc.</li><li>Appels d’API à partir de la version d’API 1.4 ou 2.0</li><li>Alertes</li><li>Partager des liens avec tout le monde</li><li>Toute autre application qui interroge le moteur de création de rapports Analytics</li></ul> |
| [!UICONTROL **Utilisateur ou utilisatrice**] | L’utilisateur qui a initié la requête. <p>**Remarque :** si la valeur de cette colonne est [!UICONTROL **Non reconnu**], cela signifie que l’utilisateur se trouve dans une société de connexion pour laquelle vous ne disposez pas des autorisations administratives.</p> |
| [!UICONTROL **Projet**] | Noms de projets d’espace de travail enregistrés, ID de rapport API, etc. (Les métadonnées peuvent varier d’une application à l’autre.) |
| [!UICONTROL **Statut**] | Indicateurs de statut : <ul><li>**En cours d’exécution** : la demande est en cours de traitement.</li><li>**En attente** : la demande est en attente de traitement.</li></ul> |
| [!UICONTROL **Complexité**] | Le traitement de toutes les demandes ne prend pas le même temps. La complexité de la demande peut vous donner une idée générale du temps nécessaire pour traiter la demande. <p>Valeurs possibles :</p> <ul><li>[!UICONTROL **Faible**]</li><li>[!UICONTROL **Medium**]</li><li>[!UICONTROL **Élevé**]</li></ul>Cette valeur est influencée par les valeurs des colonnes suivantes :<ul><li>[!UICONTROL **Limites mensuelles**]</li><li>[!UICONTROL **Colonnes**]</li><li>[!UICONTROL **Segments**]</li></ul> |
| [!UICONTROL **Limites mensuelles**] | Nombre de mois inclus dans une demande. L’ajout de limites de mois ajoute à la complexité de la requête. |
| [!UICONTROL **Colonnes**] | Le nombre de mesures et de répartitions dans la requête. L’ajout de colonnes ajoute à la complexité de la requête. |
| [!UICONTROL **Segments**] | Nombre de segments appliqués à la requête. Plus de segments ajoute à la complexité de la requête. |

{style="table-layout:auto"}

#### Afficher les données par utilisateur

Lorsque vous sélectionnez l’onglet [!UICONTROL **Utilisateur**], les colonnes suivantes sont disponibles dans le tableau :

| Colonne | Description |
| --- | --- |
| [!UICONTROL **Utilisateur ou utilisatrice**] | L’utilisateur qui a initié la requête. Si la valeur de cette colonne est [!UICONTROL **Non reconnu**], cela signifie que l’utilisateur se trouve dans une société de connexion pour laquelle vous ne disposez pas d’autorisations administratives. |
| [!UICONTROL **Nombre de requêtes**] | Nombre de requêtes initiées par l’utilisateur ou l’utilisatrice. |
| [!UICONTROL **Nombre de projets**] | Nombre de projets associés à l’utilisateur. <!-- ??? --> |
| [!UICONTROL **Application**] | Les applications prises en charge par le [!UICONTROL Gestionnaire des activités de rapport] sont les suivantes : <ul><li>Interface utilisateur d’Analysis Workspace</li><li>Projets planifiés d’espace de travail</li><li>Report Builder</li><li>Interface utilisateur de Builder : Segment, Mesures calculées, Annotations, Audiences, etc.</li><li>Appels d’API à partir de la version d’API 1.4 ou 2.0</li><li>Alertes</li><li>Partager des liens avec tout le monde</li><li>Toute autre application qui interroge le moteur de création de rapports Analytics</li></ul> |
| [!UICONTROL **Complexité moyenne**] | Complexité moyenne des requêtes initiées par l’utilisateur. <p>Le traitement de toutes les demandes ne prend pas le même temps. La complexité de la demande peut vous donner une idée générale du temps nécessaire pour traiter la demande.</p><p>La valeur de cette colonne est basée sur un score déterminé par les valeurs des colonnes suivantes :</p><ul><li>[!UICONTROL **Limites mensuelles moyennes**]</li><li>[!UICONTROL **Colonnes moy**]</li><li>[!UICONTROL **Segments moyens**]</li></ul> |
| [!UICONTROL **Limites mensuelles moyennes**] | Nombre moyen de mois inclus dans les demandes. L’ajout de limites de mois ajoute à la complexité de la requête. |
| [!UICONTROL **Colonnes moy**] | Nombre moyen de mesures et de répartitions dans les requêtes incluses. L’ajout de colonnes ajoute à la complexité de la requête. |
| [!UICONTROL **Segments moyens**] | Nombre moyen de segments appliqués aux requêtes incluses. Plus de segments ajoute à la complexité de la requête. |

{style="table-layout:auto"}

#### Afficher les données par projet

Lorsque vous sélectionnez l’onglet [!UICONTROL **Projet**], les colonnes suivantes sont disponibles dans le tableau :

| Colonne | Description |
| --- | --- |
| [!UICONTROL **Projet**] | Projet dans lequel les demandes ont été initiées. |
| [!UICONTROL **Nombre de requêtes**] | Nombre de requêtes associées au projet. |
| [!UICONTROL **Nombre d’utilisateurs**] | Nombre d’utilisateurs associés au projet. <!-- ??? --> |
| [!UICONTROL **Application**] | Les applications prises en charge par le [!UICONTROL Gestionnaire des activités de rapport] sont les suivantes : <ul><li>Interface utilisateur d’Analysis Workspace</li><li>Projets planifiés d’espace de travail</li><li>Report Builder</li><li>Interface utilisateur de Builder : Segment, Mesures calculées, Annotations, Audiences, etc.</li><li>Appels d’API à partir de la version d’API 1.4 ou 2.0</li><li>Alertes</li><li>Partager des liens avec tout le monde</li><li>Toute autre application qui interroge le moteur de création de rapports Analytics</li></ul> |
| [!UICONTROL **Complexité moyenne**] | Complexité moyenne des requêtes incluses dans le projet. <p>Le traitement de toutes les demandes ne prend pas le même temps. La complexité de la demande peut vous donner une idée générale du temps nécessaire pour traiter la demande.</p><p>La valeur de cette colonne est basée sur un score déterminé par les valeurs des colonnes suivantes :</p><ul><li>[!UICONTROL **Limites mensuelles moyennes**]</li><li>[!UICONTROL **Colonnes moy**]</li><li>[!UICONTROL **Segments moyens**]</li></ul> |
| [!UICONTROL **Limites mensuelles moyennes**] | Nombre moyen de mois inclus dans les demandes. L’ajout de limites de mois ajoute à la complexité de la requête. |
| [!UICONTROL **Colonnes moy**] | Nombre moyen de mesures et de répartitions dans les requêtes incluses. L’ajout de colonnes ajoute à la complexité de la requête. |
| [!UICONTROL **Segments moyens**] | Nombre moyen de segments appliqués aux requêtes incluses. Plus de segments ajoute à la complexité de la requête. |

{style="table-layout:auto"}

#### Afficher les données par application

Lorsque vous sélectionnez l&#39;onglet [!UICONTROL **Application**], les colonnes suivantes sont disponibles dans le tableau :

| Colonne | Description |
| --- | --- |
| [!UICONTROL **Application**] | Application dans laquelle les requêtes ont été initiées. |
| [!UICONTROL **Nombre de requêtes**] | Nombre de requêtes associées à l’application. |
| [!UICONTROL **Nombre d’utilisateurs**] | Nombre d’utilisateurs associés à l’application. <!--???--> |
| [!UICONTROL **Nombre de projets**] | Nombre de projets associés à l’application. <!--???--> |
| [!UICONTROL **Complexité moyenne**] | Complexité moyenne des requêtes associées à l’application. <p>Le traitement de toutes les demandes ne prend pas le même temps. La complexité de la demande peut vous donner une idée générale du temps nécessaire pour traiter la demande.</p><p>La valeur de cette colonne est basée sur un score déterminé par les valeurs des colonnes suivantes :</p>La valeur de cette colonne est basée sur un score déterminé par les valeurs des colonnes suivantes :<ul><li>[!UICONTROL **Limites mensuelles moyennes**]</li><li>[!UICONTROL **Colonnes moy**]</li><li>[!UICONTROL **Segments moyens**]</li></ul> |
| [!UICONTROL **Limites mensuelles moyennes**] | Nombre moyen de mois inclus dans les demandes. L’ajout de limites de mois ajoute à la complexité de la requête. |
| [!UICONTROL **Colonnes moy**] | Nombre moyen de mesures et de répartitions dans les requêtes incluses. L’ajout de colonnes ajoute à la complexité de la requête. |
| [!UICONTROL **Segments moyens**] | Nombre moyen de segments appliqués aux requêtes incluses. Plus de segments ajoute à la complexité de la requête. |

{style="table-layout:auto"}

<!--

## Frequently asked questions {#faq}

| Question | Answer |
| --- | --- |
|  |  |

{style="table-layout:auto"}

-->