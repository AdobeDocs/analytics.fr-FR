---
description: Découvrez comment utiliser le Gestionnaire des activités de création de rapports pour diagnostiquer et corriger les problèmes de capacité pendant les heures de pointe de la création de rapports.
title: Responsable des activités de rapport
feature: Admin Tools
hide: true
hidefromtoc: true
source-git-commit: 70cfad1a04d17e1007178f32af73988be503fe90
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 1%

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

## Gestion de la file d’attente des rapports

Lors de l’ouverture du Gestionnaire d’activités de création de rapports, une liste des suites de rapports de base s’affiche. Les suites de rapports virtuelles ne sont pas incluses dans cette vue.

![file d&#39;attente des rapports](assets/reporting-activity1.png)

Les suites de rapports virtuelles rendent les demandes de création de rapports plus complexes en raison de niveaux supplémentaires de filtrage et de segmentation appliqués. Toutes les requêtes provenant des suites de rapports virtuelles sont combinées et descendent dans la suite de rapports de base. Ainsi, si vous avez 10 requêtes provenant de 5 suites de rapports virtuelles, il s’agit de 50 requêtes au niveau de la suite de rapports de base. De cette façon, vous pouvez atteindre la capacité très rapidement.

Voici une vue d’une suite de rapports virtuelle dont la capacité de création de rapports s’affiche en temps réel :

![suites de rapports virtuelles](assets/reporting-activity-vrs.png)

Actualisez la page pour modifier les résultats.

## Incidences sur les rapports Workspace





