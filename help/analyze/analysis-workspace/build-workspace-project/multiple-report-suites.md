---
title: Suites de rapports multiples
description: Découvrez comment et pourquoi créer des projets dans Workspace avec plusieurs suites de rapports.
feature: Workspace Basics
role: User, Admin
exl-id: 0429ddd9-935f-44ef-ae1e-97bb02e6e2df
source-git-commit: 8f7c6a0d1477b599b05aeb7b74c4ee96531d294d
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 75%

---

# Suites de rapports multiples

Vous pouvez créer des projets dans Analysis Workspace avec des données provenant de plusieurs suites de rapports. Les suites de rapports sont sélectionnées au niveau du panneau. Vous pouvez donc choisir une suite de rapports différente pour chaque panneau au sein d’un même projet Workspace.

Cette fonctionnalité est utile si vous souhaitez :

* Comparer les données de deux régions différentes et que les données sont dans deux suites de rapports différentes. Vous pouvez créer des tableaux et des visualisations pour comparer les données côte à côte.

* Créer un tableau de bord de mesures et de visualisations pour envoyer des rapports à d’autres organisations. Vous pouvez extraire des données de différentes suites de rapports dans dans le même projet.


>[!BEGINSHADEBOX]

Reportez-vous à la section ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Plusieurs suites de rapports](https://video.tv.adobe.com/v/32843?quality=12&learn=on){target="_blank"} pour une vidéo de démonstration.

>[!ENDSHADEBOX]


## Application de suites de rapports à tous les panneaux

Vous pouvez appliquer une suite de rapports à tous les panneaux en même temps en cliquant avec le bouton droit de la souris sur l’en-tête d’un panneau et en sélectionnant **[!UICONTROL Application d’une suite de rapports à tous les panneaux]**.

![](assets/apply-rs-all-panels.png)

## Panneau actif

Le panneau actif est reconnaissable par la bordure bleue claire qui l’entoure. Il vous suffit de sélectionner à l’intérieur d’un panneau pour le transformer en panneau actif.

>[!TIP]
>
>Vous pouvez faire glisser et déposer vers n’importe quel panneau situé dans la même suite de rapports que votre panneau actif. En faisant glisser le panneau vers un panneau inactif de la même suite de rapports, le panneau devient actif.
>

## Utilisation de plusieurs suites de rapports

![](assets/mrs-ui.png)

1. Créez un projet avec 2 panneaux ou plus dans Workspace.

1. Faites glisser et déposez des composants (mesures, dimensions, segments, périodes) dans le panneau. Assurez-vous que les panneaux contiennent des données et des visualisations propres à leur suite de rapports.


   >[!NOTE]
   >
   >Parfois, une bannière s’affiche lors du chargement d’un projet (ou du changement de suite de rapports) pour lequel tous les composants ne sont pas inclus dans la suite de rapports. Les composants manquants sont répertoriés. Suivez [ces instructions](/help/admin/admin-console/permissions/product-profile.md) pour définir les autorisations requises sur les mesures et dimensions.
   >

   ![](assets/incompat-rs.png)

   Vous disposez de 3 options pour gérer cette incompatibilité :
   * Activer les dimensions/mesures requises.
   * Modifier la suite de rapports.
   * Poursuivre sans certains composants. Cela ne générera aucune donnée pour ces composants et/ou des visualisations vides.

1. Modifier le panneau pour une autre suite de rapports et noter comment le libellé du composant (suite de rapports active) et les composants répertoriés sont mis à jour en fonction de cette modification.

1. Utiliser un raccourci clavier (`shift` lorsque vous faites glisser un composant) pour changer de panneau actif.

1. (Facultatif) Vous pouvez également accéder à d’autres créateurs de composants Analytics et vous assurer qu’ils affichent désormais un libellé de suite de rapports indiquant :

   * Où un segment sera créé : [Créateur de segments](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-build.html?lang=fr).
   * Où une mesure calculée sera créée : [Créateur de mesures calculées](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html?lang=fr).
   * Où une alerte sera créée : [Générateur d’alertes](https://experienceleague.adobe.com/docs/analytics/components/alerts/alert-builder.html?lang=fr).
