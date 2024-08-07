---
title: Gestion des annotations
description: Comment gérer les annotations dans l’espace de travail.
role: User, Admin
feature: Annotations
exl-id: 37a538cc-9ea7-4cb1-8ee8-e8e474ad5b08
source-git-commit: 4f0bd39b64535be8ba55e97d65177f6ef291ef6c
workflow-type: tm+mt
source-wordcount: '563'
ht-degree: 61%

---

# Gestion des annotations

Le [!UICONTROL gestionnaire d’annotations] vous présente toutes les annotations que vous possédez ou qui ont été partagées avec vous. Les annotations spécifiques au projet n’apparaissent pas ici. Vous pouvez utiliser cette interface pour partager, filtrer, baliser, copier, supprimer et marquer vos annotations comme favorites. Les administrateurs peuvent gérer et approuver les annotations.

**[!UICONTROL Composants]** > **[!UICONTROL Annotations]**

## Interface utilisateur du gestionnaire d’annotations

![](assets/annotation-mgr.png)

| Élément de lʼinterface utilisateur | Description |
| --- | --- | 
| [!UICONTROL Titre et description] | Fournis dans le créateur d’annotations. Pour modifier le titre et la description, cliquez sur le lien du titre : il vous ramène au créateur d’annotations. |
| [!UICONTROL Suite de rapports] | Suites de rapports auxquelles cette annotation s’applique. |
| [!UICONTROL Propriétaire] | Indique qui possède l’annotation. En tant que non administrateur, vous ne pouvez consulter que les annotations que vous possédez ou celles qui ont été partagées avec vous. |
| [!UICONTROL Période appliquée] | La date ou la période à laquelle cette annotation s’applique. |
| [!UICONTROL Partagé avec] | Répertorie le nombre d’individus ou de groupes avec lesquels vous avez partagé l’annotation. Cliquez pour plus de détails. |
| [!UICONTROL Date de modification] | Affiche la date et l’heure de la dernière modification de l’annotation. |

{style="table-layout:auto"}

## Modification des annotations

La modification d’une annotation signifie que vous pouvez ajuster les plages de dates, les couleurs, la portée ou s’il s’applique à toutes les suites de rapports ou tous les projets. Vous pouvez modifier les annotations de deux manières différentes :

* Dans un graphique linéaire, pointez sur l’annotation et cliquez sur l’icône représentant un crayon dans la fenêtre contextuelle.
* Dans le [!UICONTROL Gestionnaire d’annotations], cliquez sur le titre de l’annotation.

Ces deux options vous redirigent vers le [!UICONTROL Créateur d’annotations]. Vous pouvez y effectuer les réglages nécessaires et enregistrer la nouvelle version.

## Partage des annotations

Lors du partage d’annotations ou de l’utilisation d’annotations partagées avec vous, tenez compte des points suivants :

* Si vous créez un projet avec des annotations de projet uniquement, puis partagez le projet avec un autre utilisateur, les annotations ne peuvent pas être modifiées ni supprimées par quiconque avec lequel vous le partagez.
* Si vous enregistrez une annotation et la partagez directement avec un utilisateur, ce dernier ne peut la modifier/la supprimer que s’il dispose des droits d’administrateur.
* Si un projet est partagé avec vous avec une annotation propre au projet, il s’affiche uniquement dans ce projet. Si l’annotation est partagée directement avec vous, elle s’affiche dans tous les projets où elle peut être affichée.

## Annotations et fuseaux horaires

Toutes les annotations sont créées avec un horodatage, mais sans informations sur les heures ou le fuseau horaire. Au moment du rapport, le fuseau horaire de la suite de rapports du panneau est toujours appliqué. Par exemple, une annotation créée pour le jour de Noël se produit le 25 décembre, quel que soit le fuseau horaire de la suite de rapports dans laquelle vous vous trouvez.

## Autres tâches d’annotation

Le gestionnaire d’annotations permet aux administrateurs de modifier, d’ajouter, de baliser, de supprimer, de renommer, d’approuver, de copier, d’exporter et de filtrer les annotations. Il n’est pas visible par les utilisateurs qui ne sont pas administrateurs.

D’autres options sont disponibles lorsque vous sélectionnez au moins une annotation :

| Tâche | Description |
| --- | --- |
| [!UICONTROL Ajouter] | Permet d’accéder au créateur d’annotations où vous pouvez créer des annotations. |
| [!UICONTROL Balise] | Tous les utilisateurs peuvent créer des balises pour les annotations et en appliquer une ou plusieurs à une annotation. Cependant, vous ne pouvez afficher les balises que pour les annotations que vous détenez. |
| [!UICONTROL Supprimer] | La suppression d’une annotation la supprime de tout projet de votre entreprise. |
| [!UICONTROL Renommer] | Modifier le nom d’une annotation la renomme dans tous les projets auxquels elle a été appliquée. |
| [!UICONTROL Copier] | Permet de créer une copie distincte avec son propre identifiant d’annotation, mais avec le même nom et la même définition. |
| [!UICONTROL Exporter dans un fichier CSV] | Exportez la définition d’annotation dans un fichier .csv. |
| [!UICONTROL Filtrer] (rail de gauche) | Filtrez par balises, suite de rapports, propriétaires et autres filtres (À moi, Approuvés, Favoris, Partagés avec moi et Tout afficher). |

{style="table-layout:auto"}
