---
title: Qu’est-ce que le Report Builder Hub dans Adobe Analytics ?
description: Décrit les composants du centre Report Builder
role: User
feature: Report Builder
type: Documentation
solution: Analytics
source-git-commit: eedabc6295f9b918e1e00b93993680e676c216c3
workflow-type: tm+mt
source-wordcount: '494'
ht-degree: 61%

---

# Centre Report Builder

Utilisez le centre Report Builder pour créer, mettre à jour, supprimer et gérer des blocs de données.

Le hub de Report Builder contient les boutons Créer et Gérer, la liste COMMANDES et les panneaux d’édition RAPIDE.

<img src="./assets/hub51.png" alt="Centre Report Builder"/>


## Boutons Créer, Gérer et Planifier

Utilisez les boutons Créer, Gérer et Planifier pour créer de nouveaux blocs de données, gérer des blocs de données existants ou planifier des blocs de données.

## Panneau COMMANDES

Utilisez le panneau COMMANDES pour accéder aux commandes compatibles avec les cellules sélectionnées ou à une action précédente.

### Commandes

| Commandes affichées | Disponible lorsque… | Rôle |
|------|------------------|--------|
| Créer un bloc de données | Une ou plusieurs cellules sont sélectionnées dans le classeur. | Sert à créer un bloc de données |
| Modifier le bloc de données | La ou les cellules sélectionnées font partie d’un seul bloc de données. | Sert à modifier un bloc de données |
| Actualiser le bloc de données | La sélection contient au moins un bloc de données. La commande actualise uniquement les blocs de données de la sélection. | Sert à actualiser un ou plusieurs blocs de données |
| Actualiser tous les blocs de données | Le classeur contient un ou plusieurs blocs de données. | Sert à actualiser TOUS les blocs de données dans le classeur |
| Envoyer le classeur |   | Envoyez un classeur selon un calendrier. |
| Copier le bloc de données | La cellule ou la plage de cellules sélectionnée fait partie d’un ou de plusieurs blocs de données. | Sert à copier un bloc de données |
| Supprimer le bloc de données | La ou les cellules sélectionnées font partie d’un seul bloc de données. | Sert à supprimer un bloc de données |

## Panneau ÉDITION RAPIDE

Lorsque vous sélectionnez un ou plusieurs blocs de données dans une feuille de calculs, Report Builder affiche le panneau ÉDITION RAPIDE. Vous pouvez utiliser le panneau ÉDITION RAPIDE pour modifier les paramètres d’un seul ou de plusieurs blocs de données en même temps.

![Panneau Modification rapide en Report Builder](./assets/hub2.png)

Les modifications effectuées à l’aide des sections Édition rapide s’appliquent à tous les blocs de données sélectionnés.

### Suites de rapports

Les blocs de données extraient des données d’une suite de rapports sélectionnée. Si plusieurs blocs de données sont sélectionnés dans une feuille de calcul et qu’ils n’extraient pas de données de la même suite de rapports, le lien **Suites de rapports** affiche *Multiple*.

Lorsque vous modifiez la suite de rapports, tous les blocs de données de la sélection adoptent la nouvelle suite de rapports. Les composants du bloc de données sont associés à la nouvelle suite de rapports en fonction de l’ID, par exemple, la correspondance avec ```evars```. Si un composant est introuvable dans un bloc de données, un message d’avertissement s’affiche et le composant est supprimé du bloc de données.

Pour modifier la suite de rapports, sélectionnez une nouvelle suite de rapports dans le menu déroulant.

![Hub de Report Builder affichant le menu déroulant de la suite de rapports.](./assets/image16.png)

### Période

**[!UICONTROL Période]** affiche la période des blocs de données sélectionnés. Si plusieurs blocs de données sont sélectionnés avec plusieurs plages de dates, le lien **[!UICONTROL Plage de dates]** affiche *Multiple*.

### Filtres

Le lien **Filtres** affiche une liste récapitulative des filtres utilisés par les blocs de données sélectionnés. Si plusieurs blocs de données sont sélectionnés avec plusieurs filtres appliqués, le lien **Filtres** affiche *Multiple*.
