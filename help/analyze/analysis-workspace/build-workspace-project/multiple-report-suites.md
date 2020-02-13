---
title: Plusieurs suites de rapports dans Workspace
description: Découvrez comment et pourquoi créer des projets dans Workspace avec plusieurs suites de rapports
translation-type: tm+mt
source-git-commit: 1736ada89b02c95aa749ff14165d491fd878a251

---


# Plusieurs suites de rapports dans Workspace

>[!IMPORTANT]
>Plusieurs suites de rapports dans Workspace sont actuellement en version limitée.

Vous pouvez désormais créer des projets dans Analysis Workspace à l’aide de données provenant de plusieurs suites de rapports. Les suites de rapports sont désormais sélectionnées au niveau du panneau. Vous pouvez donc choisir une suite de rapports différente pour chaque panneau du même projet Workspace.

Cette fonctionnalité est utile si vous souhaitez, par exemple,

* Comparez les données de deux régions différentes et les données résident dans deux suites de rapports différentes. Vous pouvez créer des tableaux et des visualisations pour comparer les données côte à côte.

* Créez un tableau de bord de mesures et de visualisations pour créer des rapports à d’autres organisations. Vous pouvez désormais extraire des données de diverses suites de rapports dans le même projet.

## Panneau actif

Cette fonctionnalité présente le concept de &quot;panneau actif&quot; par rapport à &quot;panneau inactif&quot;. Le panneau actif est reconnaissable par la bordure bleue claire autour. Il suffit de cliquer à l’intérieur d’un panneau pour activer ce panneau.

>[!IMPORTANT]
>Vous pouvez faire glisser des composants **uniquement dans le panneau** actif, même si d’autres panneaux possèdent la même suite de rapports. Si vous souhaitez modifier le panneau tout en le faisant glisser et en le déposant, vous pouvez utiliser un raccourci : appuyez sur `shift` la touche lorsque vous faites glisser le curseur pour transformer un panneau inactif en panneau actif.

| Tâche | Panneau actif | Panneau Inactif |
|---|---|---|
| Modifier la suite de rapports | Oui | Non |
| Faire glisser et déposer des composants | Oui | Non |
| Glisser-déposer des visualisations | Oui | Non |

## Utilisation de plusieurs suites de rapports

![](assets/mrs-ui.png)

1. Créez un projet avec 2 panneaux ou plus dans Workspace.

1. Faites glisser des composants (mesures, dimensions, segments, plages de dates) dans le panneau. Assurez-vous que les panneaux contiennent des données et des visualisations propres à leur suite de rapports.


   >[!NOTE]
   >Il arrive qu’un message &quot;Suite de rapports incompatible&quot; s’affiche lors du chargement d’un projet (ou lors du passage à une suite de rapports) lorsque tous les composants inclus dans le projet ne sont pas inclus dans la suite de rapports. Les composants manquants sont répertoriés. Suivez [ces instructions](https://helpx.adobe.com/enterprise/using/manage-products-and-profiles.html#createproductprofiles) pour définir les autorisations sur les mesures/dimensions requises.

   ![](assets/incompat-rs.png)

   Vous disposez de 3 options pour gérer cette incompatibilité :
   * Poursuivez avec certains composants manquants. Cela n’entraînera aucune donnée pour ces composants et/ou des visualisations vides.
   * Annuler.
   * Modifier la suite de rapports.

1. Modifiez le panneau en une autre suite de rapports et notez comment le libellé du composant (suite de rapports active) et les composants répertoriés sont mis à jour en fonction de la nouvelle suite de rapports.

1. Utilisez le raccourci clavier (`shift` lorsque vous faites glisser la souris) pour transformer un panneau inactif en panneau actif.

1. (Facultatif) Vous pouvez également accéder à d’autres créateurs de composants Analytics et vous assurer qu’ils affichent désormais une étiquette de suite de rapports indiquant

   * Emplacement de création d’un segment : Créateur [de segments](https://docs.adobe.com/content/help/en/analytics/components/segmentation/segmentation-workflow/seg-build.html).
   * Où une mesure calculée sera créée : Créateur [de mesures](https://docs.adobe.com/content/help/en/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html)calculées.
   * Où une alerte sera créée : Générateur [d’alertes](https://docs.adobe.com/content/help/en/analytics/components/alerts/alert-builder.html).