---
description: Le dictionnaire de données d’Analysis Workspace permet aux utilisateurs de cataloguer et de suivre les différents composants d’Analysis Workspace, y compris leur utilisation prévue, qui sont approuvés, qui sont des doublons, etc.
title: Présentation du dictionnaire de données
feature: Components
role: User, Admin
hide: true
hidefromtoc: true
source-git-commit: d8442f1ec8f35fbcda98b35070936677813ce330
workflow-type: tm+mt
source-wordcount: '532'
ht-degree: 0%

---

# Présentation du dictionnaire de données

{{release-limited-testing}}

Le dictionnaire de données dans Analysis Workspace permet aux utilisateurs et aux administrateurs de suivre et de mieux comprendre les composants dans leur environnement Analytics.

Les administrateurs d’Analytics sont chargés de traiter les informations sur chaque composant du dictionnaire de données afin de les mettre à la disposition des utilisateurs.

## Avantages pour les utilisateurs

Le dictionnaire de données permet aux utilisateurs de mieux comprendre chaque composant disponible.

Les informations disponibles dans le dictionnaire de données incluent :

* Fonction d’un composant et utilisation prévue

* Composants généralement utilisés avec celui que vous affichez

* Composants similaires à ceux que vous affichez

* si un composant est approuvé par l’administrateur système ;

Pour plus d’informations sur l’accès au dictionnaire de données et pour plus d’informations sur les informations qu’il contient, voir [Affichage des informations sur les composants dans le dictionnaire de données](/help/analyze/analysis-workspace/components/data-dictionary/view-data-dictionary.md).

## Avantages pour les administrateurs

Le dictionnaire de données permet aux administrateurs système de suivre et de traiter les composants dans leur environnement Analytics.

Voici quelques-unes des façons dont les administrateurs d’Analytics peuvent utiliser le dictionnaire de données :

* Identifiez les composants en double qui doivent être consolidés.

* Identifiez les composants qui ne collectent aucune donnée afin qu’ils puissent être mis à jour ou supprimés.

* Identifiez les composants qui ne sont pas encore approuvés.

* Mettez à jour les descriptions des composants directement dans Analysis Workspace. Toutes les mises à jour apportées aux descriptions de composant dans le dictionnaire de données sont répercutées dans la suite de rapports.

   De même, toutes les mises à jour apportées aux descriptions de composants dans la suite de rapports sont répercutées dans Analysis Workspace.

   Pour plus d’informations sur l’ajout de descriptions de composant dans Analysis Workspace ou dans une suite de rapports, voir [Ajout de descriptions de composant](/help/analyze/analysis-workspace/components/add-component-descriptions.md).

## Accès au dictionnaire de données

Vous pouvez accéder au dictionnaire de données de l’une des manières suivantes dans Analysis Workspace :

* Dans la **Dictionnaire de données** dans le rail de gauche.

   ![Icône du dictionnaire de données dans le rail de gauche](assets/data-dictionary-access-icon.png)

* Dans la **Dictionnaire de données** dans la fenêtre contextuelle d’informations d’un composant.

   ![Icône du dictionnaire de données dans la fenêtre contextuelle d’informations](assets/data-dictionary-access-infopopover.png)
<!--update screenshot; this was taken from a mock-->

* Dans le menu : [!UICONTROL **Aide**] > [!UICONTROL **Dictionnaire de données**].

Pour plus d’informations sur les différentes options disponibles dans le dictionnaire de données, voir [Affichage des informations sur les composants dans le dictionnaire de données](/help/analyze/analysis-workspace/components/data-dictionary/view-data-dictionary.md).

## Mise à jour et traitement du dictionnaire de données

Les administrateurs d’Analytics sont chargés de conserver un dictionnaire de données sain pour leur entreprise, comme décrit dans la section [Surveillance de l’intégrité du dictionnaire de données](/help/analyze/analysis-workspace/components/data-dictionary/monitor-data-dictionary-health.md).

Dans le cadre de ce processus, les administrateurs d’Analytics peuvent modifier des informations sur chaque composant du dictionnaire de données, comme décrit dans la section [Modifier les entrées de composant dans le dictionnaire de données](/help/analyze/analysis-workspace/components/data-dictionary/edit-entries-data-dictionary.md).

## Déplacer, minimiser ou fermer le dictionnaire de données

Lorsque vous ouvrez le dictionnaire de données (comme décrit à la section [Accès au dictionnaire de données](#access-the-data-dictionary)), il s’affiche sous la forme d’une fenêtre au-dessus d’Analysis Workspace.

Vous pouvez manipuler la fenêtre du dictionnaire de données de l’une des manières suivantes :

* Faites-le glisser dans n’importe quelle zone d’Analysis Workspace

   Si vous fermez et rouvrez Analysis Workspace, la fenêtre du dictionnaire de données reste à l’emplacement où vous l’avez déplacé pour la dernière fois. <!--True?-->

* Réduire

   Une fois réduit, le dictionnaire de données s’affiche sous la forme d’un onglet bleu dans le coin inférieur droit d’Analysis Workspace.

   Lorsque vous sélectionnez l’onglet bleu, le dictionnaire de données s’ouvre sur le composant que vous avez consulté le plus récemment.

* Fermez-la
