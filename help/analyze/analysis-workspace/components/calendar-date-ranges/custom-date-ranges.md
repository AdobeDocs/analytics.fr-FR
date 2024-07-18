---
description: Créez des périodes personnalisées dans Analysis Workspace et enregistrez-les sous la forme de composants de type Heure.
keywords: Analysis Workspace
title: Création de périodes personnalisées
feature: Calendar
role: User, Admin
exl-id: 586bb120-3f20-452c-9867-0b93d2e794bc
source-git-commit: 1ec261929c1a1b62b1aeb8f01189fe5f2368fa14
workflow-type: tm+mt
source-wordcount: '438'
ht-degree: 57%

---

# Création de périodes personnalisées

Vous pouvez créer des plages de dates personnalisées dans Analysis Workspace et les enregistrer en tant que composants Heure .

Pour plus d’informations sur l’ajout de plages de dates existantes à un projet, consultez la [présentation du calendrier et des plages de dates](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md).

Pour créer une période personnalisée :

1. Dans Adobe Analytics, sélectionnez **[!UICONTROL Composants]** > **[!UICONTROL Plages de dates]**.

   ![page de période](assets/date-ranges.png)

1. Sélectionnez [!UICONTROL **Créer une plage de dates**].

1. Dans le créateur de plages de dates, spécifiez les informations suivantes :

   | Option | Description |
   |---------|----------|
   | [!UICONTROL **Titre**] | Titre de la période tel qu’il apparaîtra lorsque les utilisateurs la sélectionneront dans Analysis Workspace. |
   | [!UICONTROL **Description**] | Description de la période. |
   | [!UICONTROL **Balises**] | Toutes les balises que vous souhaitez appliquer à la période. |
   | [!UICONTROL **Période**] | Permet de sélectionner une période personnalisée. Par défaut, les 30 derniers jours sont sélectionnés. |
   | [!UICONTROL **Paramètre prédéfini**] | Faites votre choix parmi une liste de plages de dates prédéfinies, telles que [!UICONTROL **Hier**], [!UICONTROL **7 derniers jours**], [!UICONTROL **30 derniers jours**], etc. |
   | [!UICONTROL **Heure de début**] | Heure de la journée à laquelle la période commence. |
   | [!UICONTROL **Heure de fin**] | Heure de la journée à laquelle la période se termine. |
   | [!UICONTROL **Utiliser des dates roulantes**] | Grâce aux dates de déploiement, vous pouvez générer un rapport dynamique qui recherche une période donnée, en amont ou en aval, en fonction de la date d’exécution du rapport. Si, par exemple, vous souhaitez générer en décembre un rapport sur toutes les commandes passées le mois dernier (d’après le champ Date de création), les commandes passées en novembre seront incluses dans le rapport. Si vous exécutez ce même rapport en janvier, vous verrez les commandes passées en décembre.<ul><li>**[!UICONTROL Aperçu de la date]** : indique la période englobée par le calendrier variable.</li><li>**[!UICONTROL Début]** : choisissez parmi aujourd’hui, semaine en cours, mois en cours, trimestre en cours et année en cours.</li><li>**[!UICONTROL Fin]** : choisissez parmi aujourd’hui, semaine en cours, mois en cours, trimestre en cours et année en cours.</li></ul><br>Sélectionné par défaut. |

1. Sélectionnez [!UICONTROL **Enregistrer**].

## Exemple : période pour &quot;deux mois auparavant&quot; {#section_C4109C57CB444BB2A79CC8082BD67294}

La période personnalisée suivante présente une période pour « deux mois auparavant », avec une visualisation Synthèse des changements présentant le changement directionnel.

![](assets/date-range-two-months-ago.png)

La plage de dates personnalisée s’affiche au haut du panneau du composant [!UICONTROL Plage de dates] dans votre projet :

![](assets/date-range-panel-two-months-ago.png)

Vous pouvez la faire glisser dans une colonne le long d’une plage de dates variable mensuelle personnalisée, en utilisant pour comparaison le paramètre prédéfini Mois dernier. Ajoutez une visualisation Synthèse des changements et sélectionnez les totaux de chaque colonne pour afficher le changement directionnel :

![](assets/date-range-two-months-table.png)

## Exemple : utilisation d’une période variable de 7 jours {#section_7EF63B2E9FF54D2E9144C4F76956A8DD}

Vous pouvez créer une plage de dates qui spécifie un créneau variable de 7 jours qui se termine il y a une semaine :

![](assets/create_date_range.png)

Utilisez *`rolling daily`*.

* Le paramètre Début correspondrait à *`current day minus 6 days`*.

* Le paramètre Fin correspondrait à *`current day minus 7 days`*.

Cette période peut être un composant que vous faites glisser sur un tableau à structure libre.
