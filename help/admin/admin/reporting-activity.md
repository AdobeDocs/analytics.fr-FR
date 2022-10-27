---
description: Découvrez comment utiliser le Gestionnaire des activités de création de rapports pour diagnostiquer et corriger les problèmes de capacité pendant les heures de pointe de la création de rapports.
title: Responsable des activités de rapport
feature: Admin Tools
mini-toc-levels: 3
hide: true
hidefromtoc: true
source-git-commit: 123a2131be1a3cb23246e2ba591be645c7025b26
workflow-type: tm+mt
source-wordcount: '659'
ht-degree: 7%

---


# Responsable des activités de rapport

>[!NOTE]
>
>Cette fonctionnalité est actuellement en test bêta.

Le Gestionnaire d’activités de création de rapports vous permet d’afficher la capacité de création de rapports pour chaque suite de rapports de votre entreprise. En tant qu’administrateur, il vous offre une visibilité détaillée sur la création de rapports de la consommation et vous permet de diagnostiquer et de résoudre facilement les problèmes de capacité pendant les heures de pointe de la création de rapports. Lorsque votre entreprise atteint la capacité de demande de création de rapports et que ses performances en matière de création de rapports se dégradent, vous pouvez désormais diagnostiquer automatiquement les problèmes de création de rapports sans intervention de l’assistance clientèle ou de l’ingénierie d’Adobe. Vous pouvez facilement gérer les files d’attente de rapports dans une seule interface et agir immédiatement &#x200B; &#x200B; pour améliorer l’expérience de vos utilisateurs. Cet outil :

* Vous informe sur votre capacité de création de rapports actuelle dans vos suites de rapports.
* Fournit des informations détaillées sur les requêtes de rapport en cours, qu’elles soient en file d’attente ou en cours.
* Vous permet d’optimiser la file d’attente des rapports en établissant des priorités pour certaines d’entre elles et en annulant d’autres requêtes de rapport afin de libérer de la capacité. En d’autres termes, vous pouvez demander en temps réel : ce rapport est-il nécessaire à ce moment-là ou puis-je l&#39;annuler au profit de rapports plus urgents ?

## Accès au Gestionnaire des activités de création de rapports

Dans Adobe Analytics, les administrateurs accèdent à **[!UICONTROL Administration]** > **[!UICONTROL Gestionnaire des activités de création de rapports]**.

## Affichage de la file d’attente des rapports

Lors de l’ouverture de la page d’aperçu du Gestionnaire des activités de création de rapports , une liste de vos suites de rapports de base activées s’affiche.

![file d&#39;attente des rapports](assets/reporting-activity1.png)

| Élément de lʼinterface utilisateur | Description |
| --- | --- |
| **[!UICONTROL Suite de rapports]** | Suite de rapports de base dont vous surveillez l’activité de création de rapports. |
| **[!UICONTROL Suite de rapports virtuelle]** | Affiche toutes les suites de rapports virtuelles qui se trouvent dans cette suite de rapports de base. Les suites de rapports virtuelles rendent les demandes de création de rapports plus complexes en raison de niveaux supplémentaires de filtrage et de segmentation appliqués. Toutes les requêtes provenant des suites de rapports virtuelles sont combinées et descendent dans la suite de rapports de base.<p>Par exemple, si vous avez 10 requêtes provenant de 5 suites de rapports virtuelles, il s’agit de 50 requêtes au niveau de la suite de rapports de base. De cette façon, vous pouvez atteindre la capacité très rapidement. |
| **[!UICONTROL Capacité d’utilisation]** | En pourcentage, la capacité de création de rapports de la suite de rapports est utilisée, en temps réel. |
| **[!UICONTROL État]** | Quatre indicateurs de statut possibles : <ul><li>**Rouge - [!UICONTROL À la capacité]**: La suite de rapports est limitée en termes de capacité de création de rapports.</li><li>**Jaune - [!UICONTROL Capacité locale]**: Cette suite de rapports risque d’atteindre sa capacité maximale.</li><li>**Vert - [!UICONTROL Très bien]**: Il existe de nombreuses capacités de reporting.</li><li>**[!UICONTROL Statut en attente]**: ?</li><li>**Gris - Non disponible**: La suite de rapports n’est pas configurée pour la capacité de création de rapports.</li></ul> |

### Autres actions relatives aux activités de création de rapports

* Cliquez sur **[!UICONTROL Actualiser]** en haut à droite pour actualiser les résultats.
* Cliquez sur l’étoile à gauche du nom de la suite de rapports pour marquer cette suite de rapports comme favori.
* Vérifier **[!UICONTROL Favoris]** en haut à gauche pour afficher vos favoris.
* Effectuez une recherche sur les suites de rapports par nom ou par identifiant dans la barre de recherche.
* Filtrez les suites de rapports selon leur état.

## Afficher l’activité de création de rapports pour des suites de rapports individuelles

Cliquez sur le lien de titre d’une suite de rapports pour laquelle vous souhaitez afficher les détails.

![suite de rapports](assets/indiv-report-ste.png)

### Graphique linéaire

Le graphique linéaire montre l’activité de création de rapports pour la suite de rapports sélectionnée au cours des deux dernières heures.

* L’axe X affiche les données de capacité de reporting sur les deux dernières heures.
* L’axe des ordonnées affiche le temps d’attente moyen d’une requête, en secondes.
* Vous pouvez pointer sur le graphique en courbes pour afficher les points dans la durée et le temps d’attente moyen de cet instant.

   ![detail](assets/detail.png)

### Filtre

Vous pouvez filtrer le tableau par application (voir la liste dans le tableau ci-dessous), par utilisateur et par projet.

![Filtre](assets/filter.png)

### Numéros de résumé

![Filtre](assets/summary_numbers.png)

Les numéros de résumé affichent les informations suivantes :

| Numéro du résumé | Description |
| --- | --- |
| Utilisateurs | Nombre d’utilisateurs qui envoient actuellement des demandes de création de rapports à cette suite de rapports. |
| Projets |  |
| Requêtes |  |
| Temps d’attente moyen |  |
| Capacité d’utilisation | Capacité d’utilisation actuelle de cette suite de rapports. |

{style=&quot;table-layout:auto&quot;}

### Tableau

Le tableau détaillé ci-dessous affiche

| Colonne | Description |
| --- | --- |
| ID de requête |  |
| Heure d’exécution |  |
| Temps d’attente |  |
| Heure de début |  |
| Application | Les applications prises en charge par le Gestionnaire d’activités de création de rapports sont les suivantes : <ul><li>Interface utilisateur d’Analysis Workspace</li><li>Projets planifiés Workspace</li><li>Report Builder</li><li>Interface utilisateur du créateur : Segment, Mesures calculées, Annotations, Audiences, etc.</li></ul> |
| Utilisateur |  |
| Projet |  |
| Limites mensuelles |
| Colonnes |  |
| Segments |  |
| État |  |

{style=&quot;table-layout:auto&quot;}


