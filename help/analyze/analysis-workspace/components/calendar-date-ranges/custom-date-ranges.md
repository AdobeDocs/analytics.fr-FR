---
description: Créez des périodes personnalisées dans Analysis Workspace et enregistrez-les sous la forme de composants de type Heure.
keywords: Analysis Workspace
title: Création de périodes personnalisées
feature: Calendar
role: User, Admin
exl-id: 586bb120-3f20-452c-9867-0b93d2e794bc
source-git-commit: 10ae8213b8745439ab5968853f655a1176b8c38a
workflow-type: tm+mt
source-wordcount: '248'
ht-degree: 100%

---

# Création de périodes personnalisées

Créez des périodes personnalisées dans Analysis Workspace et enregistrez-les sous la forme de composants de type Heure.

**[!UICONTROL Composants]** > **[!UICONTROL Nouvelle période]**

Une période s’applique au niveau du panneau. Pour ajouter une période au projet, cliquez sur **Panneaux** > *`<select panel>`*, puis spécifiez une nouvelle période.

## Période pour « deux mois auparavant »  {#section_C4109C57CB444BB2A79CC8082BD67294}

La période personnalisée suivante présente une période pour « deux mois auparavant », avec une visualisation Synthèse des changements présentant le changement directionnel.

![](assets/date-range-two-months-ago.png)

La plage de dates personnalisée s’affiche au haut du panneau du composant [!UICONTROL Plage de dates] dans votre projet :

![](assets/date-range-panel-two-months-ago.png)

Vous pouvez la faire glisser dans une colonne le long d’une plage de dates variable mensuelle personnalisée, en utilisant pour comparaison le paramètre prédéfini Mois dernier. Ajoutez une visualisation Synthèse des changements et sélectionnez les totaux de chaque colonne pour afficher le changement directionnel :

![](assets/date-range-two-months-table.png)

## Utiliser une période variable de sept jours {#section_7EF63B2E9FF54D2E9144C4F76956A8DD}

Une plage de dates s’applique au niveau du panneau. Pour ajouter une plage de dates au projet, cliquez sur **Actions** > **Ajouter le panneau**, puis spécifiez une nouvelle plage de dates.

Dans le créateur de périodes, créez une période personnalisée qui s’affichera dans le panneau Composants avec les autres périodes.

Par exemple, vous pouvez créer une plage de dates qui spécifie un créneau variable de 7 jours qui s’est terminé il y a une semaine :

![](assets/create_date_range.png)

Sélectionnez l’option   *`rolling daily`*.

* Le paramètre Début correspondrait à *`current day minus 14 days`*.

* Le paramètre Fin correspondrait à *`current day minus 7 days`*.

Cette période peut être un composant que vous faites glisser sur un tableau à structure libre.
