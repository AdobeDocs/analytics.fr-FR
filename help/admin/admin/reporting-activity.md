---
description: Découvrez comment utiliser le Gestionnaire des activités de création de rapports pour diagnostiquer et corriger les problèmes de capacité pendant les heures de pointe de la création de rapports.
title: Responsable des activités de rapport
feature: Admin Tools
mini-toc-levels: 3
hide: true
hidefromtoc: true
source-git-commit: 77b3e8a1f8ebb1459eeac83f098cab92f671efe6
workflow-type: tm+mt
source-wordcount: '464'
ht-degree: 3%

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
| **[!UICONTROL État]** | Quatre indicateurs de statut possibles : <ul><li>**Rouge - À capacité**: La suite de rapports est limitée en termes de capacité de création de rapports.</li><li>**Jaune - Nourrir la capacité**: Cette suite de rapports risque d’atteindre sa capacité maximale.</li><li>**Vert : tout à fait bon**: Il existe de nombreuses capacités de reporting.</li><li>**[!UICONTROL Statut en attente]**: ?</li><li>**Gris - Non disponible**: La suite de rapports n’est pas configurée pour la capacité de création de rapports.</li></ul> |

### Actions d’activité de création de rapports

* Cliquez sur **[!UICONTROL Actualiser]** en haut à droite pour actualiser les résultats.
* Cliquez sur l’étoile à gauche du nom de la suite de rapports pour marquer cette suite de rapports comme favori.
* Vérifier **[!UICONTROL Favoris]** en haut à gauche pour afficher vos favoris.
* Effectuez une recherche sur les suites de rapports par nom ou par identifiant dans la barre de recherche.
* Filtrez les suites de rapports selon leur état.

## Afficher l’activité de création de rapports pour des suites de rapports individuelles



