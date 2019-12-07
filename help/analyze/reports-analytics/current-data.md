---
description: Grâce à l’option Inclure les données actives des Reports & Analytics, vous pouvez afficher les données d’analyse les plus récentes, souvent avant même qu’elles ne soient entièrement traitées et finalisées. Les données actives présentent la plupart des mesures en quelques minutes, ce qui vous permet de disposer d’informations exploitables pour une prise de décisions rapide.
subtopic: Current Data
title: Données actives
topic: Reports
uuid: 601d3695-be13-4b7f-9df0-de01c8bd64ee
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Données actives

Grâce à l’option Inclure les données actives des Reports &amp; Analytics, vous pouvez afficher les données d’analyse les plus récentes, souvent avant même qu’elles ne soient entièrement traitées et finalisées. Les données actives présentent la plupart des mesures en quelques minutes, ce qui vous permet de disposer d’informations exploitables pour une prise de décisions rapide.

Elle est visible sous forme d’option dans les paramètres d’un rapport :

![Capture d’écran des données actives](assets/current_data.png)

Les données actives sont activées par défaut sur tous les rapports qui les prennent en charge. Si vous préférez afficher toutes les mesures une fois les données entièrement traitées, vous disposez de plusieurs options :

* Utilisez Analysis Workspace, qui utilise des données entièrement traitées.
* Cliquez sur Non dans le paramètre du rapport de données actuel pour n’utiliser que les données entièrement traitées.
* Supprimez l’élément d’autorisation "Données actives" d’un profil de produit dans la Console d’administration afin d’empêcher les utilisateurs non administrateurs de voir cette option. Pour plus d’informations, voir les éléments [d’autorisation Outils](/help/admin/admin-console/permissions/analytics-tools.md) Analytics dans le guide de l’utilisateur Admin.

En raison de la définition des priorités de la disponibilité des données, les données actives ne peuvent actuellement pas être utilisées avec les segments, les classifications, les ventilations, le cheminement et certaines mesures. Si l’une de ces fonctionnalités est utilisée, les données actives sont obligées de "Non" dans le rapport et un message jaune s’affiche, expliquant pourquoi les données actives ne sont pas disponibles.

![Avis de données actuel](assets/current_data_notice.png)

## Latence type des données actives

Les mesures apparaissent dans l’une des trois périodes suivantes. Cliquez sur l’icône de l’horloge en regard du commutateur « Inclure les données actives » pour afficher la valeur de latence réelle de chaque mesure sur un rapport.

| Période | Mesures |
| --- | --- |
| Moins de 10 minutes | Instances et pages vues sur les variables de trafic |
| Entre 10 et 35 minutes | Evénements de conversion, Instances et pages vues sur les variables de conversion |
| Entre 45 et 120 minutes | Toutes les autres données, telles que les visites, les visiteurs uniques et la participation |

Certaines données affichées dans la vue de données active n’ayant pas été entièrement traitées, vous pouvez constater une différence entre les valeurs rapportées dans la vue de données active et la vue finalisée. Dans les rapports de tendance, la différence de données est généralement inférieure à 1 %.

## Mesures calculées

Les mesures calculées peuvent être créées à l’aide de mesures ayant une valeur de latence différente. Il se peut donc que certaines valeurs récentes soient calculées à l’aide de données incomplètes dans la vue des données actives.

Par exemple, vous créez la mesure calculée "Pages vues par visite" à l’aide de la formule `Page Views divided by Visits`. Les pages vues s’affichent généralement en moins de 10 minutes et les visites en moins de 2 heures ; les mesures calculées dans cette fenêtre de latence sont calculées à l’aide de mesures incomplètes. Si vous publiez une nouvelle page qui obtient 4 000 accès de 4 000 visites différentes sur une période de 2 heures, la différence de latence entre ces mesures peut entraîner des calculs incomplets.

Cette différence de données est plus visible lorsque vous créez des rapports sur de nouvelles valeurs ou lorsque vous utilisez de courtes périodes. Lorsqu’un rapport utilise des plages de dates plus longues, il est peu probable que les différences de latence survenant au cours des dernières heures de création de rapports aient un impact notable sur les mesures calculées.

Si vous avez calculé des mesures susceptibles d’être affectées par ces différences, désactivez les données actives ou utilisez les mesures avec la même fenêtre de latence prévue.

## Rapports téléchargés

Lorsque vous téléchargez un rapport dont la vue des données actives est activée, il est mis en file d’attente, généré, puis renvoyé au navigateur. Si des données sont collectées pendant la génération du rapport, elles apparaissent dans le rapport. Cette fenêtre de temps peut conduire au rapport téléchargé avec un peu plus de données.
