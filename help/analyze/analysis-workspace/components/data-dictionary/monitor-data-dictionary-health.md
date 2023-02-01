---
description: Les administrateurs sont chargés de surveiller l’intégrité du dictionnaire de données. Cela inclut le fait de savoir si les composants collectent des données, sont approuvés, contiennent des descriptions et sont exempts de doublons.
title: Surveillance de l’intégrité du dictionnaire de données
feature: Components
role: Admin
source-git-commit: 5bfbc3059526527e35f26b750d048efebee68e9e
workflow-type: tm+mt
source-wordcount: '236'
ht-degree: 0%

---

# Surveillance de l’intégrité du dictionnaire de données

{{release-limited-testing}}

Les administrateurs d’Analytics sont chargés de conserver un dictionnaire de données sain.

## Caractéristiques d’un dictionnaire de données sain

Un dictionnaire de données sain est celui où tous les composants :

* Sont utilisés et collectent des données

* Contenir des descriptions utiles pour que les utilisateurs sachent comment les utiliser au mieux

* sont exempts de doublons superflus ;

* sont approuvées par l’administrateur ;

## Vérifiez l’intégrité de votre dictionnaire de données.

Pour identifier les problèmes d’intégrité dans votre dictionnaire de données :

1. Ouvrez un projet Analysis Workspace.

1. Sélectionnez l’icône du dictionnaire de données sur le côté gauche d’Analysis Workspace. (Les autres méthodes d’accès au dictionnaire de données sont décrites dans &quot;Accès au dictionnaire de données&quot; dans [Présentation du dictionnaire de données](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md).)

   La fenêtre Dictionnaire de données s’affiche.

   ![Vue d’administration du dictionnaire de données](assets/data-dictionary-admin.png)

1. Assurez-vous que la bonne suite de rapports est sélectionnée dans le menu déroulant.

1. Sur le [!UICONTROL **Santé du dictionnaire**] onglet, sélectionnez [!UICONTROL **Affichage**] en regard de l’une des options suivantes :

   * [!UICONTROL **descriptions manquantes des composants**]

   * [!UICONTROL **composants comportent des doublons**]

   * [!UICONTROL **Les composants ne comportent aucune donnée connectée**]

   Selon ce que vous sélectionnez, le filtre approprié est appliqué au dictionnaire de données et seuls les composants appropriés sont affichés.

1. Modifiez l’un des composants pour améliorer l’intégrité du dictionnaire de données. Pour plus d’informations sur la modification d’un composant dans le dictionnaire de données, voir [Modifier les entrées de composant dans le dictionnaire de données](/help/analyze/analysis-workspace/components/data-dictionary/edit-entries-data-dictionary.md).