---
description: Découvrez comment utiliser le Gestionnaire des activités de rapport pour diagnostiquer et corriger les problèmes de capacité pendant les heures de pointe de la création de rapports.
title: Annuler les demandes de création de rapport dans le gestionnaire des activités de rapports
feature: Admin Tools
exl-id: 37a2fa8f-7804-4220-a508-ec66996b3801
role: Admin
source-git-commit: 815e50e30fa6a0bce1bf78f33843070f96f52de8
workflow-type: ht
source-wordcount: '1438'
ht-degree: 100%

---

# Annuler les demandes de création de rapport dans le gestionnaire des activités de rapports

Le [!UICONTROL gestionnaire des activités de rapport] permet aux administrateurs et administratrices de diagnostiquer et d’annuler rapidement les demandes de création de rapports afin de résoudre les problèmes de capacité de création de rapports pendant les heures de pointe de la création de rapports.

Tenez compte des points suivants lors de l’annulation de demandes de création de rapports :

* Vous pouvez annuler des demandes spécifiques, annuler toutes les demandes d’une personne spécifique ou annuler toutes les demandes liées à un projet spécifique.

  Lorsque vous annulez une demande, l’action est enregistrée dans les [Journaux](/help/admin/admin/logs.md). La colonne [!UICONTROL **Type d’événement**] s’affiche sous la forme [!UICONTROL **Action d’administration**] et une description de l’annulation est disponible dans la colonne [!UICONTROL **Événement**].

* Lorsque vous annulez des demandes, vous pouvez également choisir de limiter les demandes suivantes pour une période donnée.

  Lorsque vous limitez une demande ultérieure, l’action est enregistrée dans les [Journaux](/help/admin/admin/logs.md). La colonne [!UICONTROL **Type d’événement**] s’affiche sous la forme [!UICONTROL **Action d’administration**] et une description de la restriction est disponible dans la colonne [!UICONTROL **Événement**].

* Vous ne pouvez pas annuler une demande si la colonne [!UICONTROL **Utilisateur ou utilisatrice**] d’une demande indique [!UICONTROL **Non reconnu**]. Dans ce cas, cela signifie que la personne se trouve dans une société de connexion pour laquelle vous ne disposez pas des autorisations administratives.

Pour plus d’informations sur le Gestionnaire des activités de rapport, y compris les principaux avantages et les exigences d’autorisation, voir [Vue d’ensemble du Gestionnaire des activités de rapport](/help/admin/admin/reporting-activity-manager/reporting-activity-overview.md).

## Annuler des demandes spécifiques de création de rapports

Vous pouvez annuler des demandes individuelles qui consomment une grande quantité de capacité de création de rapports.

1. Dans Adobe Analytics, accédez à **[!UICONTROL Administration]** > **[!UICONTROL Gestionnaire des activités de rapports]**.

1. Sélectionnez la suite de rapports dans laquelle vous souhaitez annuler les demandes de création de rapports. <!--double-check this step-->

   Pour plus d’informations sur les données disponibles dans cette page, voir [Afficher l’activité de rapport dans le Gestionnaire des activités de rapport](/help/admin/admin/reporting-activity-manager/reporting-activity.md).

1. Sélectionnez l’onglet [!UICONTROL **Demandes**], puis une ou plusieurs demandes.

   <!-- add screenshot -->

1. Sélectionnez [!UICONTROL **Annuler les demandes**].

   La boîte de dialogue [!UICONTROL **Annuler _x_ demandes de rapport**] s’affiche.

1. Le champ Message d’annulation affiche le message qui s’affiche pour les utilisateurs et utilisatrices lorsque leurs demandes sont annulées. Un message par défaut est fourni. Vous pouvez mettre à jour le message par défaut pour fournir des détails supplémentaires.

1. (Facultatif) Pour restreindre les demandes futures pour une période donnée, procédez comme suit :

   1. Activez l’option pour [!UICONTROL **Restreindre les demandes ultérieures**].

      ![Restreindre les demandes ultérieures](assets/restrict-subsequent-requests.png)

   1. Choisissez l’une des options suivantes :

      | Option | Fonction |
      |---------|----------|
      | [!UICONTROL **Utilisateur ou utilisatrice et projet**] | Les utilisateurs et utilisatrices associés aux demandes sélectionnées seront temporairement limités dans l’exécution des demandes de creation de rapports pour les projets associés. |
      | [!UICONTROL **Utilisateur ou utilisatrice**] | Les utilisateurs et utilisatrices associés aux demandes sélectionnées ne pourront temporairement pas effectuer des demandes de création de rapports. |
      | [!UICONTROL **Projet**] | Les projets associés aux demandes sélectionnées seront temporairement exclus de toutes les demandes de création de rapports. |
      | [!UICONTROL **Restreint pour**] | Choisissez la durée pendant laquelle les demandes seront restreintes. Vous pouvez choisir 1 minute (par défaut), 5 minutes, 10 minutes, 15 minutes ou 30 minutes. <!-- double-check this --><p>Vous ne pouvez pas supprimer une restriction plus tôt une fois qu’elle a été définie.</p> |

      {style="table-layout:auto"}

1. Sélectionnez [!UICONTROL **Continuer avec l’annulation**].

   Une notification s’affiche dans Analysis Workspace pour informer les utilisateurs et utilisatrices que la demande a été annulée. Pour plus d’informations sur la façon dont cela s’affiche dans Analysis Workspace, consultez [Expérience d’accès des utilisateurs et utilisatrices à un rapport annulé](#experience-when-users-access-a-cancelled-report).

## Annuler les demandes par utilisateur ou utilisatrice

Vous pouvez annuler toutes les demandes associées à une ou plusieurs personnes.

1. Dans Adobe Analytics, accédez à **[!UICONTROL Administration]** > **[!UICONTROL Gestionnaire des activités de rapport]**.

1. Sélectionnez la suite de rapports dans laquelle vous souhaitez annuler les demandes de création de rapports. <!--double-check this step-->

   Pour plus d’informations sur les données disponibles dans cette page, voir [Afficher l’activité de rapport dans le Gestionnaire des activités de rapport](/help/admin/admin/reporting-activity-manager/reporting-activity.md).

1. Sélectionnez l’onglet [!UICONTROL **Utilisateurs et utilisatrices**], puis sélectionnez une ou plusieurs personnes.

   <!-- add screenshot -->

1. Sélectionnez [!UICONTROL **Annuler les demandes**].

   La boîte de dialogue [!UICONTROL **Annuler _x_ demandes de rapport de x personnes**] s’affiche.

1. Le champ Message d’annulation affiche le message qui s’affiche pour les utilisateurs et utilisatrices lorsque leurs demandes sont annulées. Un message par défaut est fourni. Vous pouvez mettre à jour le message par défaut pour fournir des détails supplémentaires.

1. (Facultatif) Pour restreindre les demandes futures pour une période donnée, procédez comme suit :

   1. Activez l’option pour [!UICONTROL **Restreindre les demandes ultérieures**].

      ![Restreindre les demandes ultérieures par utilisateur ou utilisatrice](assets/restrict-subsequent-requests-user.png)

   1. Choisissez l’une des options suivantes :

      | Option | Fonction |
      |---------|----------|
      | [!UICONTROL **Utilisateur ou utilisatrice et projet**] | Les utilisateurs et utilisatrices sélectionnés ne pourront temporairement pas faire de demandes de rapport pour les projets associés. |
      | [!UICONTROL **Utilisateur ou utilisatrice**] | Les utilisateurs et utilisatrices sélectionnés ne pourront temporairement pas faire de demandes de création de rapports. |
      | [!UICONTROL **Projet**] | Les projets associés aux utilisateurs et utilisatrices sélectionnés ne pourront pas faire l’objet de demandes de création de rapports d’un utilisateur ou d’une utilisatrice. |
      | [!UICONTROL **Restreint pour**] | Choisissez la durée pendant laquelle les demandes seront restreintes. Vous pouvez choisir 1 minute (par défaut), 5 minutes, 10 minutes, 15 minutes ou 30 minutes. <!--double-check this--> <p>Vous ne pouvez pas supprimer une restriction plus tôt une fois qu’elle a été définie.</p> |

      {style="table-layout:auto"}

1. Sélectionnez [!UICONTROL **Continuer avec l’annulation**].

   Une notification s’affiche dans Analysis Workspace pour informer les utilisateurs et utilisatrices que la demande a été annulée. Pour plus d’informations sur la façon dont cela s’affiche dans Analysis Workspace, consultez [Expérience d’accès des utilisateurs et utilisatrices à un rapport annulé](#experience-when-users-access-a-cancelled-report).

## Annuler les demandes par projet

Vous pouvez annuler toutes les demandes associées à un ou plusieurs projets.

1. Dans Adobe Analytics, accédez à **[!UICONTROL Administration]** > **[!UICONTROL Gestionnaire des activités de rapport]**.

1. Sélectionnez la suite de rapports dans laquelle vous souhaitez annuler les demandes de création de rapports. <!--double-check this step-->

   Pour plus d’informations sur les données disponibles dans cette page, voir [Afficher l’activité de rapport dans le Gestionnaire des activités de rapport](/help/admin/admin/reporting-activity-manager/reporting-activity.md).

1. Sélectionnez l’onglet [!UICONTROL **Projets**], puis sélectionnez un ou plusieurs projets.

   <!-- add screenshot -->

1. Sélectionnez [!UICONTROL **Annuler des demandes**].

   La boîte de dialogue [!UICONTROL **Annuler _x_ demandes de création de rapports de x projets**] s’affiche.

1. Le champ Message d’annulation affiche le message qui s’affiche pour les utilisateurs et utilisatrices lorsque leurs demandes sont annulées. Un message par défaut est fourni. Vous pouvez mettre à jour le message par défaut pour fournir des détails supplémentaires.

1. (Facultatif) Pour restreindre les demandes futures pour une période donnée, procédez comme suit :

   1. Activez l’option pour [!UICONTROL **Restreindre les demandes ultérieures**].

      ![Restreindre les demandes ultérieures par projet](assets/restrict-subsequent-requests-project.png)

   1. Choisissez l’une des options suivantes :

      | Option | Fonction |
      |---------|----------|
      | [!UICONTROL **Utilisateur ou utilisatrice et projet**] | Les projets sélectionnés seront temporairement exclus de toute demande de création de rapports de la part des utilisateurs et utilisatrices associés. |
      | [!UICONTROL **Utilisateur ou utilisatrice**] | Les utilisateurs et utilisatrices associés aux projets sélectionnés ne pourront temporairement pas effectuer des demandes de création de rapports. |
      | [!UICONTROL **Projet**] | Les projets sélectionnés seront temporairement exclus de toute demande de création de rapports émanant d’un utilisateur ou d’une utilisatrice. |
      | [!UICONTROL **Restreint pour**] | Choisissez la durée pendant laquelle les demandes seront restreintes. Vous pouvez choisir 1 minute (par défaut), 5 minutes, 10 minutes, 15 minutes ou 30 minutes. <!--double-check this--> <p>Vous ne pouvez pas supprimer une restriction plus tôt une fois qu’elle a été définie.</p> |

      {style="table-layout:auto"}

1. Sélectionnez [!UICONTROL **Continuer avec l’annulation**].

   Une notification s’affiche dans Analysis Workspace pour informer les utilisateurs et utilisatrices que la demande a été annulée. Pour plus d’informations sur la façon dont cela s’affiche dans Analysis Workspace, consultez [Expérience d’accès des utilisateurs et utilisatrices à un rapport annulé](#experience-when-users-access-a-cancelled-report).

## Annuler les demandes par application

Vous pouvez annuler toutes les demandes associées à une ou plusieurs applications. Lors de l’annulation de demandes associées à une application, vous pouvez choisir de restreindre davantage les demandes associées à cette application pendant une période donnée.

Les applications comprennent les suivantes :

* Interface utilisateur d’Analysis Workspace
* Projets planifiés d’espace de travail
* Report Builder
* Interface utilisateur de Builder : Segment, Mesures calculées, Annotations, Audiences, etc.
* Appels d’API à partir de la version d’API 1.4 ou 2.0
* Alertes
* Liens de partage avec tout le monde
* Toute autre application interrogeant le moteur de création de rapports Analytics

Pour annuler des demandes par application, procédez comme suit :

1. Dans Adobe Analytics, accédez à **[!UICONTROL Administration]** > **[!UICONTROL Gestionnaire des activités de rapport]**.

1. Sélectionnez la connexion sur laquelle vous souhaitez annuler les demandes de création de rapports. <!--double-check this step-->

   Pour plus d’informations sur les données disponibles dans cette page, voir [Afficher l’activité de rapport dans le Gestionnaire des activités de rapport](/help/admin/admin/reporting-activity-manager/reporting-activity.md).

1. Sélectionnez l’onglet [!UICONTROL **Applications**], puis une ou plusieurs applications.

   <!-- add screenshot -->

1. Sélectionnez [!UICONTROL **Annuler des demandes**].

   La boîte de dialogue [!UICONTROL **Annuler _x_ demandes de création de rapports de x projets**] s’affiche.

1. Le champ Message d’annulation affiche le message qui s’affiche pour les utilisateurs et utilisatrices lorsque leurs demandes sont annulées. Un message par défaut est fourni. Vous pouvez mettre à jour le message par défaut pour fournir des détails supplémentaires.

1. (Facultatif) Pour restreindre les demandes futures pour une période donnée, procédez comme suit :

   1. Activez l’option pour [!UICONTROL **Restreindre les demandes ultérieures**].

      ![Restreindre les demandes ultérieures par application](assets/restrict-subsequent-requests-application.png)

   1. Choisissez l’une des options suivantes :

      | Option | Fonction |
      |---------|----------|
      | [!UICONTROL **Utilisateur ou utilisatrice et projet**] | Les applications sélectionnées seront temporairement exclues de toute demande de création de rapports de la part des utilisateurs et utilisatrices et des projets associés.<p>Il s’agit de l’option la moins contraignante.</p> |
      | [!UICONTROL **Utilisateur ou utilisatrice**] | Les utilisateurs et utilisatrices associés aux applications sélectionnées ne pourront temporairement pas effectuer des demandes de création de rapports. |
      | [!UICONTROL **Projet**] | Les projets associés aux applications sélectionnées ne pourront pas faire l’objet de demandes de création de rapports d’un utilisateur ou d’une utilisatrice. |
      | [!UICONTROL **Restreint pour**] | Choisissez la durée pendant laquelle les demandes seront restreintes. Vous pouvez choisir 1 minute (par défaut), 5 minutes, 10 minutes, 15 minutes ou 30 minutes. <!--double-check this--> <p>Vous ne pouvez pas supprimer une restriction plus tôt une fois qu’elle a été définie.</p> |

      {style="table-layout:auto"}

1. Sélectionnez [!UICONTROL **Continuer avec l’annulation**].

   Une notification s’affiche dans l’application (dans Analysis Workspace, par exemple) pour informer les utilisateurs et utilisatrices que la demande a été annulée. Pour plus d’informations sur la façon dont cela s’affiche dans Analysis Workspace, consultez [Expérience d’accès des utilisateurs et utilisatrices à un rapport annulé](#experience-when-users-access-a-cancelled-report).

## Expérience d’accès des utilisateurs et utilisatrices à un rapport annulé

Dans Analysis Workspace, les utilisateurs et utilisatrices voient les messages suivants lorsqu’ils tentent d’accéder à un rapport ou à une visualisation faisant l’objet d’une annulation :

### Message sur le projet

Lorsque les utilisateurs et utilisatrices tentent d’accéder à un projet faisant l’objet d’une annulation, un message les informe que le rapport est temporairement restreint :

![Message d’annulation du projet](assets/workspace-canceled-report.png)

### Message sur la visualisation

Lorsque les utilisateurs et utilisatrices tentent d’accéder à une visualisation faisant l’objet d’une annulation, un message s’affiche pour les informer que le traitement des données pour le rapport est temporairement limité :

![Message d’annulation de la visualisation](assets/workspace-cancelled-visualization.png)
