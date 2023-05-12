---
description: Découvrez comment utiliser le gestionnaire des activités de rapport pour diagnostiquer et corriger les problèmes de capacité pendant les heures de pointe de la création de rapports.
title: Gestionnaire des activités de rapport
feature: Admin Tools
mini-toc-levels: 3
exl-id: f638c6a9-1c2c-4936-a787-281269f95afc
source-git-commit: 646eb5aeefb17ded89a7041df6f6ad927b799f3f
workflow-type: tm+mt
source-wordcount: '954'
ht-degree: 95%

---

# Gestionnaire des activités de rapport

{{release-limited-testing}}

Le [!UICONTROL gestionnaire des activités de rapport] vous permet d’afficher la capacité de création de rapports pour chaque suite de rapports de votre entreprise. En tant qu’administrateur, il vous offre une visibilité détaillée sur la consommation de rapports et vous permet de diagnostiquer et de résoudre facilement les problèmes de capacité pendant les heures de pointe de la création de rapports.

Lorsque votre entreprise atteint la capacité de demande de création de rapports et que ses performances en matière de création de rapports se dégradent, vous pouvez désormais diagnostiquer automatiquement les problèmes de création de rapports sans intervention de l’assistance clientèle ou de l’ingénierie d’Adobe. Vous pouvez facilement gérer les files d’attente de création de rapports dans une seule interface et agir immédiatement pour améliorer l’expérience de vos utilisateurs. Cet outil :

* Vous informe en temps réel de votre capacité de création de rapports actuelle dans l’ensemble de vos suites de rapports.
* Fournit des informations détaillées sur les requêtes de création de rapport en cours, qu’elles soient en file d’attente ou en cours.
* Vous permet d’optimiser la file d’attente de la création de rapports en établissant des priorités pour certaines d’entre elles et en annulant d’autres requêtes de création de rapport afin de libérer de la capacité. En d’autres termes, vous pouvez demander en temps réel : ce rapport est-il nécessaire à ce moment-là, ou puis-je l’annuler au profit de rapports plus urgents ?

## Accéder au Gestionnaire des activités de rapports

Dans Adobe Analytics, les administrateurs accèdent à **[!UICONTROL Administration]** > **[!UICONTROL Gestionnaire des activités de rapports]**.

## Autorisations

Vous avez besoin de l’autorisation d’administrateur produit Analytics (dans Adobe Admin Console) pour gérer les activités de rapports.

![autorisation](/help/admin/admin/assets/rep-mgr-permission.png)

## Afficher la file d’attente des rapports

Lors de l’ouverture de la page d’aperçu du gestionnaire des [!UICONTROL activités de rapports], une liste de vos suites de rapports de base activées s’affiche.

![file d’attente des rapports](/help/admin/admin/assets/reporting-activity1.png)

| Élément de lʼinterface utilisateur | Description |
| --- | --- |
| **[!UICONTROL Suite de rapports]** | La suite de rapports de base dont vous surveillez l’activité de création de rapports. |
| **[!UICONTROL Suite de rapports virtuelle]** | Affiche toutes les suites de rapports virtuelles qui se trouvent dans cette suite de rapports de base. Les suites de rapports virtuelles rendent les demandes de création de rapports plus complexes en raison de niveaux supplémentaires de filtrage et de segmentation appliqués. Toutes les requêtes provenant des suites de rapports virtuelles sont combinées et descendent dans la suite de rapports de base.<p>Par exemple, si vous avez dix requêtes provenant de cinq suites de rapports virtuelles, il s’agit de 50 requêtes au niveau de la suite de rapports de base. De cette façon, vous pouvez atteindre la capacité maximale très rapidement. |
| **[!UICONTROL Capacité d’utilisation]** | Quel pourcentage de la capacité de création de rapports de la suite de rapports est utilisé en temps réel. |
| **[!UICONTROL Statut]** | Quatre indicateurs de statut possibles : <ul><li>**Rouge - [!UICONTROL À capacité maximale]** : La suite de rapports est à son maximum en termes de capacité de création de rapports. (100 %) </li><li>**Jaune - [!UICONTROL Proche de la capacité maximale]** : Cette suite de rapports risque d’atteindre sa capacité maximale. (90 % - 99 %)</li><li>**Vert - [!UICONTROL Très bien]** : Il y a encore beaucoup de capacité de création de rapports. (0 % - 89 %)</li><li>**Gris - [!UICONTROL Statut en attente/Non activé]** : Capacité de rapports non disponible.</li></ul> |

{style="table-layout:auto"}

### Autres actions relatives aux activités de rapports

* Cliquez sur **[!UICONTROL Actualiser]** en haut à droite pour actualiser les résultats.
* Cliquez sur l’étoile à gauche du nom de la suite de rapports pour marquer cette suite de rapports comme favori.
* Cliquez sur **[!UICONTROL Favoris]** en haut à gauche pour afficher vos favoris.
* Effectuez une recherche sur les suites de rapports par nom ou par identifiant dans la barre de recherche.
* Filtrez les suites de rapports selon leur statut.

## Affichez l’activité de rapports pour des suites de rapports individuelles

Cliquez sur le lien de titre d’une suite de rapports pour laquelle vous souhaitez afficher les détails.

![suite de rapports](/help/admin/admin/assets/indiv-report-ste.png)

### Graphique linéaire {#line}

Le graphique linéaire montre l’activité de création de rapports pour la suite de rapports sélectionnée au cours des deux dernières heures.

* L’axe des abscisses affiche les données de capacité de création de rapports sur les deux dernières heures.
* L’axe Y affiche par minute la capacité d’utilisation des rapports en % pour la suite de rapports sélectionnée.
* Vous pouvez pointer sur le graphique en courbes pour afficher les points dans le temps où le pourcentage de capacité d’utilisation représenté sera le % le plus élevé pour cette minute.

   ![détail](/help/admin/admin/assets/detail.png)

### Filtre

Vous pouvez filtrer le tableau par application (voir la liste dans le tableau ci-dessous), par utilisateur et par projet.

![filtre](/help/admin/admin/assets/filter.png)

### Synthèse des chiffres {#summary}

![filtre](/help/admin/admin/assets/summary_numbers.png)

La synthèse des chiffres affiche les informations suivantes :

| Synthèse des chiffres | Description |
| --- | --- |
| [!UICONTROL Utilisateurs] | Nombre d’utilisateurs qui envoient actuellement des demandes de création de rapports à cette suite de rapports. |
| [!UICONTROL Projets] | Projets d’espace de travail, classeurs de Report Builder, etc. |
| [!UICONTROL Requêtes] | Nombre de requêtes en cours d’exécution. |
| [!UICONTROL Temps d’attente moyen] | Temps d’attente moyen pour toutes les requêtes en cours d’exécution. |
| [!UICONTROL Capacité d’utilisation] | Capacité d’utilisation actuelle de cette suite de rapports. |

{style="table-layout:auto"}

### Tableau sur les détails des suites de rapports {#details}

Le tableau détaillé ci-dessous présente des détails sur la suite de rapports.

| Colonne | Description |
| --- | --- |
| [!UICONTROL ID de requête] | Peut être utilisé à des fins de dépannage. |
| [!UICONTROL Durée d’exécution] | Durée d’exécution de la requête. |
| [!UICONTROL Temps d’attente] | Durée pendant laquelle la requête a été en attente avant d’être traitée. Généralement à « 0 » lorsque la capacité est suffisante. |
| [!UICONTROL Heure de début] | Lorsque le traitement de la requête a commencé (heure locale de l’administrateur). |
| [!UICONTROL Application] | Les applications prises en charge par le [!UICONTROL Gestionnaire des activités de rapport] sont les suivantes : <ul><li>Interface utilisateur d’Analysis Workspace</li><li>Projets planifiés d’espace de travail</li><li>Report Builder</li><li>Interface utilisateur de Builder : Segment, Mesures calculées, Annotations, Audiences, etc.</li><li>Appels d’API à partir de la version d’API 1.4 ou 2.0</li><li>Alertes intelligentes</li></ul> |
| [!UICONTROL Utilisateur] | L’utilisateur qui a lancé la requête. |
| [!UICONTROL Projet] | Noms de projets d’espace de travail enregistrés, ID de rapport API, etc. (Les métadonnées peuvent varier d’une application à l’autre.) |
| [!UICONTROL Limites mensuelles] | Nombre de limites mensuelles qu’une requête traverse. Cela ajoute à la complexité de la requête. |
| [!UICONTROL Colonnes] | Le nombre de mesures et de répartitions dans l’espace de travail pour évaluer la complexité de la requête. |
| [!UICONTROL Segments] | Nombre de segments appliqués à cette requête. Cela ajoute à la complexité de la requête. |
| [!UICONTROL Statut] | Indicateurs de statut : <ul><li>**En cours d’exécution** : la demande est en cours de traitement.</li><li>**En attente** : la demande est en attente de traitement.</li></ul> |

{style="table-layout:auto"}

## Annuler des demandes de création de rapports {#cancel}

Pour annuler une requête

1. Cochez la case à gauche d’un ou de plusieurs **[!UICONTROL ID de requête]** dans le tableau, puis cliquez sur **[!UICONTROL Annuler les requêtes]** en bas.

   Vous pouvez également annuler des requêtes en bloc en affichant les détails par [!UICONTROL Utilisateur], [!UICONTROL Projet] ou [!UICONTROL Application]. Les demandes ultérieures pour un projet, un utilisateur ou une application qui n’étaient pas dans la file d’attente ou en cours d’exécution au moment de l’annulation peuvent encore apparaître lorsque l’activité est actualisée.

1. Dans la fenêtre **[!UICONTROL Annuler x requête]** qui s’affiche, vous pouvez modifier le message d’annulation, si nécessaire.
1. Cliquez sur **[!UICONTROL Continuer]**.

   ![annuler-requête](/help/admin/admin/assets/cancel-query.png)

Par exemple, les utilisateurs de l’application dans l’espace de travail verront apparaître l’avertissement suivant dans leurs projets :

![avertissement-utilisateur-annulation](/help/admin/admin/assets/cancel-user-facing.png)

## Questions fréquentes {#faq}

| Question | Réponse |
| --- | --- |
| Puis-je acheter de la capacité de création de rapports supplémentaire ? | Cette fonctionnalité sera disponible dans un avenir proche. |

{style="table-layout:auto"}
