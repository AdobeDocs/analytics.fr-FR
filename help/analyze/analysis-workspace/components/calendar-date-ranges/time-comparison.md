---
description: 'Dans Analysis Workspace, appliquez une comparaison des dates commune à partir de n’importe quelle colonne contenant une période, par exemple : année par année, trimestre par trimestre, mois par mois, etc.'
title: Comparaison des dates
feature: Calendar
role: User, Admin
exl-id: ea7a42ef-89de-4f70-b468-8a5cf69fea05
source-git-commit: d7a6867796f97f8a14cd8a3cfad115923b329c7c
workflow-type: ht
source-wordcount: '747'
ht-degree: 100%

---

# Comparaison des dates

Dans Analysis Workspace, appliquez une comparaison des dates commune à partir de n’importe quelle colonne contenant une période, par exemple : année par année, trimestre par trimestre, mois par mois, etc.


>[!BEGINSHADEBOX]

Voir ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Comparaison des dates](https://video.tv.adobe.com/v/30753?quality=12&learn=on){target="_blank"} pour une vidéo de démonstration.

>[!ENDSHADEBOX]



## Comparer des périodes {#section_C4E36BFE0F5C4378A74E705747C9DEE4}

>[!NOTE]
>L’option [!UICONTROL Comparer des périodes] tire parti des mesures calculées avancées. Par conséquent, elle est disponible uniquement pour les clients qui disposent des SKU Select, Prime et Ultimate d’Analytics.

Une analyse ne peut pas avoir lieu sans contexte. Il arrive souvent que ce contexte découle d’une période précédente. Par exemple, la question « Dans quelle mesure notre situation est-elle meilleure ou pire qu’à la même époque l’année dernière ? » est essentielle pour bien comprendre vos activités. La comparaison des dates inclut automatiquement une colonne « différence », qui présente le pourcentage de changement par rapport à une période donnée.

1. Créez un tableau à structure libre, avec les dimensions et mesures à comparer sur une certaine période.
1. Cliquez avec le bouton droit de la souris dans une ligne de tableau, puis sélectionnez **[!UICONTROL Comparer des périodes]**.

   ![](assets/compare-time.png)

   >[!NOTE]
   >
   >Cette option contextuelle est désactivée pour les lignes de mesures, de périodes et de dimension temporelle.

1. Selon la façon dont sont définies les périodes du tableau, les options de comparaison suivantes sont disponibles :

   | Option | Description |
   |---|---|
   | **[!UICONTROL Semaine/Mois/Trimestre/Année précédent(e) à cette période]** | Compare les données à la semaine/au mois/etc. précédant immédiatement cette plage de dates. |
   | **[!UICONTROL Cette semaine/Ce mois/Ce trimestre/Cette année l’an dernier à cette période]** | Compare les données à la même période il y a un an. |
   | **[!UICONTROL Période personnalisée à cette période]** | Permet de sélectionner une période personnalisée. |

   >[!NOTE]
   >
   >Lorsque vous sélectionnez un nombre de jours personnalisé (par exemple, du 7 au 20 octobre, soit 14 jours), seules deux options sont proposées : **[!UICONTROL 14 jours précédant cette période]** et **[!UICONTROL Période personnalisée à cette période]**.

1. La comparaison qui en résulte ressemble à ceci :

   ![](assets/compare-time-result.png)

   Les lignes dans la colonne Pourcentage de changement sont en rouge pour les valeurs négatives et en vert pour les valeurs positives.

1. (Facultatif) Comme dans n’importe quel autre projet Analysis Workspace, vous pouvez créer des visualisations en fonction de ces comparaisons temporelles. Voici par exemple un graphique en barres :

   ![](assets/compare-time-barchart.png)

   Pour afficher le pourcentage de changement dans ce graphique en barres, le paramètre [!UICONTROL Pourcentages] doit être activé dans les [!UICONTROL Paramètres de visualisation].

## Ajout d’une colonne de périodes à la comparaison {#section_93CC2B4F48504125BEC104046A32EB93}

Vous pouvez désormais ajouter une période à chaque colonne d’un tableau, ce qui permet d’ajouter une période différente de celle configurée pour votre calendrier. Cette fonctionnalité offre un autre moyen de comparer les dates.

1. Cliquez avec le bouton droit de la souris dans le tableau, puis sélectionnez **[!UICONTROL Ajouter une colonne de périodes]**.

   ![](assets/add-time-period-column.png)

1. Selon la façon dont sont définies les périodes du tableau, les options de comparaison suivantes sont disponibles :

   | Option | Description |
   |---|---|
   | **[!UICONTROL Semaine/Mois/Trimestre/Année précédent(e) à cette période]** | Ajoute une colonne avec la semaine/le mois/etc. précédant immédiatement cette plage de dates. |
   | **[!UICONTROL Cette semaine/Ce mois/Ce trimestre/Cette année l’an dernier à cette période]** | Ajoute la même période il y a un an. |
   | **[!UICONTROL Période personnalisée à cette période]** | Permet de sélectionner une période personnalisée. |

   >[!NOTE]
   >
   >Lorsque vous sélectionnez un nombre de jours personnalisé (par exemple, du 7 au 20 octobre, soit 14 jours), seules deux options sont proposées : **[!UICONTROL 14 jours précédant cette période]** et **[!UICONTROL Période personnalisée à cette période]**.

1. La période sera insérée en haut de la colonne sélectionnée :

   ![](assets/add-time-period-column2.png)

1. Vous pouvez ajouter autant de colonnes que vous le souhaitez, et mélanger et associer différentes périodes :

   ![](assets/add-time-period-column4.png)

1. Vous pouvez également trier chaque colonne, ce qui change l’ordre des jours selon la colonne utilisée pour le tri.

## Aligner les dates de colonnes pour commencer sur la même ligne {#section_5085E200082048CB899C3F355062A733}

Vous pouvez également aligner les dates de chaque colonne afin qu’elles commencent à partir de la même ligne.

Exemple : si vous alignez les dates dans le cadre d’une comparaison d’un mois à l’autre entre octobre et septembre 2016, la colonne de gauche commence au 1er octobre et la colonne de droite au 1er septembre :

![](assets/add-time-period-column3.png)

>[!NOTE]
>
>Tenez compte des points suivants lorsque vous utilisez cette option :
>
>* Ce paramètre est activé par défaut pour tous les nouveaux projets.
>
>* Ce paramètre s’applique à l’ensemble du tableau. Par exemple, si vous modifiez ce paramètre pour une répartition au sein du tableau, le paramètre sera modifié pour l’ensemble du tableau.
>

Pour activer ce paramètre, s’il n’est pas déjà activé, procédez comme suit :

1. Dans le tableau où vous souhaitez aligner les dates des colonnes, sélectionnez l’icône **Paramètres** dans l’en-tête du tableau.

1. Dans l’onglet [!UICONTROL **Paramètres**], sélectionnez **[!UICONTROL Aligner les dates de chaque colonne pour que toutes commencent sur la même ligne (s’applique à l’ensemble du tableau)]**.

![](assets/date-comparison-setting.png)


