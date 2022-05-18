---
title: Gestion des annotations
description: Comment gérer les annotations dans l’espace de travail.
role: User, Admin
feature: Annotations
exl-id: 37a538cc-9ea7-4cb1-8ee8-e8e474ad5b08
source-git-commit: 645baf99161d93b5e9d2436978d35c1fb5ee35e7
workflow-type: tm+mt
source-wordcount: '677'
ht-degree: 65%

---

# Gestion des annotations

Le gestionnaire [!UICONTROL Composants] > [!UICONTROL Annotations] offre de nombreuses façons de gérer les annotations, comme le partage, le filtrage, le balisage, l’approbation, la copie, la suppression et le marquage en tant que favoris.

Le gestionnaire d’[!UICONTROL Annotations] vous présente toutes les annotations que vous possédez, qui ont été incluses dans tous vos projets et qui ont été partagées avec vous.

>[!NOTE]
>
>Les [!UICONTROL Annotations] que vous avez créées uniquement pour un projet spécifique n’apparaissent pas dans le gestionnaire.

## Interface utilisateur du gestionnaire d’annotations

![](assets/annotation-mgr.png)

| Élément de lʼinterface utilisateur | Description |
| --- | --- | 
| [!UICONTROL Titre et description] | Fournis dans le créateur d’annotations. Pour modifier le titre et la description, cliquez sur le lien du titre : il vous ramène au créateur d’annotations. |
| [!UICONTROL Suite de rapports] | La ou les suites de rapports auxquelles cette annotation s’applique. |
| [!UICONTROL Propriétaire] | Indique qui possède l’annotation. En tant que non administrateur, vous ne pouvez consulter que les annotations que vous possédez ou celles qui ont été partagées avec vous. |
| [!UICONTROL Période appliquée] | La date ou la période à laquelle cette annotation s’applique. |
| [!UICONTROL Partagé avec] | Répertorie le nombre d’individus ou de groupes avec lesquels vous avez partagé l’annotation. Cliquez pour plus de détails. |
| [!UICONTROL Date de modification] | Affiche la date et l’heure de la dernière modification de l’annotation. |

## Modification des annotations

La modification d’une annotation signifie que vous pouvez ajuster les périodes, les couleurs, la portée ou le fait qu’elle s’applique ou non à toutes les suites de rapports ou à tous les projets. Vous pouvez modifier les annotations de deux manières différentes :

* Dans un graphique linéaire, pointez sur l’annotation et cliquez sur l’icône représentant un crayon dans la fenêtre contextuelle.

* Dans le [!UICONTROL Gestionnaire d’annotations], cliquez sur le titre de l’annotation.

Ces deux options vous permettent de revenir dans la [!UICONTROL Créateur d’annotations]. Vous pouvez y effectuer les réglages nécessaires et enregistrer la nouvelle version.

## Partage des annotations

Lors du partage d’annotations ou de l’utilisation d’annotations partagées avec vous, tenez compte des points suivants :

* Supposons que vous créiez un projet avec des annotations de projet uniquement, puis que vous le partagiez avec un autre utilisateur. Ces annotations s’affichent, mais elles ne peuvent pas être modifiées ni supprimées par une personne avec laquelle vous partagez le projet.

* Si vous enregistrez une annotation et la partagez directement avec un utilisateur, ce dernier ne peut la modifier/la supprimer que s’il dispose des droits d’administrateur.

* Pour récapituler, si le projet est partagé avec vous, il s’affichera uniquement dans ce projet. Si l’annotation est partagée directement avec vous, elle s’affiche dans tous les projets où elle peut être affichée.

## Annotations et fuseaux horaires

Toutes les annotations sont créées avec un horodatage, mais aucune information sur les heures ou les fuseaux horaires. Au moment du rapport, le fuseau horaire de la suite de rapports du panneau est toujours appliqué. Ainsi, une annotation créée pour le jour de Noël a lieu le 25 décembre, quel que soit le fuseau horaire de la suite de rapports dans laquelle vous vous trouvez.

Autre exemple : le Nouvel An. Chaque heure, un fuseau horaire différent déclenche des feux d&#39;artifice au début de l&#39;année. A 10h heure des Rocheuses, la côte Est des États-Unis est en train de déclencher des feux car il est déjà 12h heure de l&#39;Est.

## Autres tâches d’annotation

Le gestionnaire d’annotations permet aux administrateurs de modifier, d’ajouter, de baliser, de supprimer, de renommer, d’approuver, de copier, d’exporter et de filtrer les annotations. Il n’est pas visible par les utilisateurs qui ne sont pas administrateurs.

Sélectionnez simplement une ou plusieurs annotations pour faire apparaître la barre des tâches.

| Tâche | Description |
| --- | --- |
| [!UICONTROL Ajouter] | Permet d’accéder au créateur d’annotations où vous pouvez créer des annotations. |
| [!UICONTROL Balises] | Tous les utilisateurs peuvent créer des balises pour les annotations et en appliquer une ou plusieurs à une annotation. Cependant, vous ne pouvez afficher les balises que pour les annotations que vous détenez. Quels types de balises devriez-vous créer ? Vous trouverez ci-dessous quelques suggestions de balises utiles :<ul><li>Des balises basées sur des noms d’équipe, par exemple Marketing des réseaux sociaux, Marketing des appareils mobiles</li><li>Les balises Projet (balises d’analyse), telles que l’analyse de la page d’accès</li><li>Les balises Catégorie : Hommes ; géographie</li><li>Les balises Workflow : Traité pour (une division spéciale) ; Approuvé.</li></ul> |
| [!UICONTROL Supprimer] | La suppression d’une annotation la supprime de tout projet de votre entreprise. |
| [!UICONTROL Renommer] | Modifier le nom d’une annotation la renomme dans tous les projets auxquels elle a été appliquée. |
| [!UICONTROL Copier] | Permet de créer une copie distincte avec son propre identifiant d’annotation, mais avec le même nom et la même définition. |
| [!UICONTROL Exporter dans un fichier CSV] | Exportez la définition d’annotation dans un fichier .csv. |
| [!UICONTROL Filtrer] (rail de gauche) | Filtrez par balises, suite de rapports, propriétaires et autres filtres (À moi, Approuvés, Favoris, Partagés avec moi et Tout afficher). |
