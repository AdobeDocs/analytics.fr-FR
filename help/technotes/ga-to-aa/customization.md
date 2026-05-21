---
title: Personnalisation des rapports dans Adobe Analytics
description: Découvrez comment personnaliser des rapports dans Adobe Analytics
feature: Third-party Integration
exl-id: 8ea6ec3a-cfc6-4c14-966b-d245949451c7
TQID: https://experienceleague.adobe.com/vvVKR7JKV12zgIic0rso4OihH5kyAoZBV983R3VmOic
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
  - id: dcae653e-62c6-4cc8-84e6-ee110b848296
  - id: e3e906cf-5493-4e0a-9a33-bf0ac37393d6
  - id: e93b8c4c-c5f7-45f8-9abe-9b710f53f502
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 609
ht-degree: 94%

---

# Personnalisation des rapports

Sur les plateformes tierces, telles que Google Analytics, plusieurs options de personnalisation sont disponibles. Ces personnalisations permettent à l’utilisateur de créer des tableaux de bord, des rapports personnalisés, des rapports enregistrés et des alertes personnalisées. Comme Analysis Workspace permet aux utilisateurs de créer des rapports à partir d’un canevas vierge, la plupart des personnalisations sont directement intégrées à l’outil.

Cette page part du principe que l’utilisateur maîtrise les bases de l’utilisation d’[!UICONTROL Analysis Workspace]. Voir [Création d’un rapport de base dans Analysis Workspace pour les utilisateurs de Google Analytics](reports/create-report.md) si vous ne connaissez pas encore l’outil dans Adobe Analytics.

## Tableaux de bord

L’architecture d’[!UICONTROL Analysis Workspace] est similaire au concept des widgets des tableaux de bord. Les projets d’[!UICONTROL Analysis Workspace] sont équivalents aux tableaux de bord de Google Analytics. Les visualisations d’[!UICONTROL Analysis Workspace] sont équivalentes aux widgets de Google Analytics.

### Ajout de contenu à un projet

1. Cliquez sur l’icône [!UICONTROL Visualisations] à gauche et faites glisser la visualisation de votre choix sur l’espace de travail.
2. Cliquez sur l’icône [!UICONTROL Composants] à gauche et faites glisser les dimensions et mesures de votre choix sur la visualisation pour y renseigner des données.
3. Faites glisser les bords de la visualisation pour la redimensionner, et faites glisser le titre de la visualisation pour le déplacer.

Tous les widgets de Google Analytics sont disponibles dans [!UICONTROL Analysis Workspace] :

* Le **widget Mesure** est à peu près équivalent à la visualisation [!UICONTROL Synthèse des chiffres].
* Le **widget Chronologie** est à peu près équivalent à la visualisation [!UICONTROL Ligne].
* Le **widget Geomap** est à peu près équivalent à la visualisation [!UICONTROL Carte].
* Le **widget Tableau** est à peu près équivalent à la visualisation [!UICONTROL Tableau à structure libre].
* Le **widget circulaire** est à peu près équivalent à la visualisation [!UICONTROL Anneau].
* Le **widget Barre** est peu près équivalent à la visualisation [!UICONTROL Barre].

[!UICONTROL Analysis Workspace] inclut de nombreuses autres options de visualisation pour présenter les données de la manière la plus adaptée à vos besoins de création de rapports. Pour plus d’informations, voir [Visualisations dans Analysis Workspace](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md) dans le guide d’utilisation.

### Partage de projets

Une fois que vous avez terminé d’ajouter du contenu à un projet, vous pouvez le partager.

* Pour partager le projet avec vos collègues, accédez à **[!UICONTROL Partager > Partager le projet]**. Les destinataires sont d’autres utilisateurs de votre entreprise qui possèdent des comptes Adobe Analytics.
* Pour partager votre projet via un lien, accédez à **[!UICONTROL Partager > Obtenir le lien du projet]**. Notez que cela nécessite également une connexion à Adobe Analytics au sein de votre entreprise.

### Exportation de projets

Outre le format PDF, [!UICONTROL Analysis Workspace] propose une exportation au format CSV.

1. Cliquez sur *[!UICONTROL Partager]* > *[!UICONTROL Envoyer le fichier maintenant]*. Une fenêtre modale s’ouvre.
2. Précisez le type de fichier et les destinataires.
3. Cliquez sur [!UICONTROL Envoyer maintenant].

## Rapports personnalisés

Lors de la création d’un rapport personnalisé dans Google Analytics, les champs requis sont similaires au processus de création d’une visualisation dans l’espace de travail. Les définitions de dimensions, de mesures et de filtres sont similaires dans toutes les plateformes. Dans Analysis Workspace, au lieu de sélectionner des dimensions et des mesures dans une liste, les dimensions et les mesures sont glissées sur un tableau à structure libre.

### Mesures calculées dans les rapports personnalisés

Les rapports personnalisés sont l’un des rares domaines de Google Analytics qui autorise l’utilisation de mesures calculées. Comme Analysis Workspace fonctionne comme un canevas, les mesures calculées fonctionnent rétroactivement et dans n’importe quel contexte.

Pour créer une mesure calculée :

1. Cliquez sur l’icône **+** près de la liste des mesures pour ouvrir le [!UICONTROL créateur de mesures calculées].
2. Attribuez un nom à votre mesure calculée et spécifiez un format.
3. Faites glisser les composants de mesure vers dans la zone de définition, puis utilisez les listes déroulantes entre chaque composant pour désigner un opérateur.
4. Une fois que la mesure calculée contient la formule souhaitée, cliquez sur Enregistrer pour revenir à votre espace de travail.
5. Faites glisser la mesure calculée nouvellement définie sur l’espace de travail.

   Pour en savoir plus sur les [mesures calculées](/help/components/calculated-metrics/cm-overview.md), voir le guide d’utilisation des composants.

## Alertes personnalisées

Les alertes sont disponibles sur les deux plateformes. Dans Adobe Analytics, utilisez le menu de navigation de l’en-tête et accédez à *[!UICONTROL Composants]* > *[!UICONTROL Alertes]*. Voir [Présentation des alertes](/help/components/alerts/alerts-overview.md) dans le Guide de l’utilisateur des composants pour plus d’informations.
