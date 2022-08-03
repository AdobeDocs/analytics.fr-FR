---
description: Permet de visualiser facilement les données de comparaison dans Analysis Workspace, par exemple en créant des comparaisons avec le mois dernier, l’année dernière, etc.
title: Visualisation des diagrammes en courbes
feature: Visualizations
role: User, Admin
source-git-commit: 04a314e93a77ecf5687e771e143bf68ba911b32b
workflow-type: tm+mt
source-wordcount: '241'
ht-degree: 7%

---


# Graphique combo

>[!NOTE]
>
>Cette fonctionnalité fait actuellement l’objet de [tests limités](/help/release-notes/releases.md).

Le [!UICONTROL Graphique en courbes] la visualisation facilite la création rapide d’une visualisation de comparaison sans avoir à créer d’abord un tableau. Vous pouvez facilement afficher les tendances de vos données dans une combinaison ligne/barre.

Utilisation d’un diagramme de type Combo pour

* Comparez les commandes de cette semaine aux commandes en même temps le mois dernier (et l’année dernière), le tout en quelques clics.

* Analysez et comparez rapidement plusieurs mesures (comme [!UICONTROL Visiteurs uniques] et [!UICONTROL Recettes]) les uns par rapport aux autres sur le même graphique.

* Analyse d’une mesure par rapport à une fonction (telle que [!UICONTROL Moyenne cumulée]) sur un horizon temporel.

## Création d’un diagramme Combo

1. Dans la liste déroulante Visualisations du rail de gauche, faites glisser le [!UICONTROL Graphique en courbes] visualisation dans un panneau vierge.

   ![](assets/combo-chart-build.png)

1. Dans les listes déroulantes, sélectionnez une dimension pour l’axe X et une mesure pour l’axe Y.

1. Sélectionnez le type de [!UICONTROL Comparaison des lignes] vous voulez utiliser.

   | Type de comparaison de lignes | Définition |
   | --- | --- |
   | Période | Type de comparaison le plus courant : comparaison de cette période à il y a 4 semaines, par exemple. Si vous avez sélectionné Période, effectuez une sélection secondaire pour déterminer à quelle période vous souhaitez comparer.<p>![](assets/combo-time-period.png) |
   | Mesure supplémentaire | Vous pouvez, par exemple, comparer des [!UICONTROL Recettes] à une autre mesure. |
   | Fonction | Vous pouvez introduire une fonction telle que [!UICONTROL Moyenne] dans la comparaison. |

1. Cliquez sur **[!UICONTROL Créer]**.

   La sortie ressemblera à ceci :

   ![](assets/combo-output.png)





