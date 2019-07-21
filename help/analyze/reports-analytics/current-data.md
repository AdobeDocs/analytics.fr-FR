---
description: Grâce à l’option Inclure les données actives des Reports & Analytics, vous pouvez afficher les données d’analyse les plus récentes, souvent avant même qu’elles ne soient entièrement traitées et finalisées. Les données actives présentent la plupart des mesures en quelques minutes, ce qui vous permet de disposer d’informations exploitables pour une prise de décisions rapide.
seo-title: Données actives
solution: Analytics
subtopic: Données actives
title: Données actives
topic: Présentation
uuid: 601 d 3695-be 13-4 b 7 f -9 df 0-de 01 c 8 bd 64 ee
translation-type: tm+mt
source-git-commit: 1fdd14497171dbf5850ec1b1d873a06931d58435

---


# Données actives

Grâce à l’option Inclure les données actives des Reports &amp; Analytics, vous pouvez afficher les données d’analyse les plus récentes, souvent avant même qu’elles ne soient entièrement traitées et finalisées. Les données actives présentent la plupart des mesures en quelques minutes, ce qui vous permet de disposer d’informations exploitables pour une prise de décisions rapide.

Elle est visible comme une option dans les paramètres d'un rapport :

![Capture d'écran de données actives](assets/current_data.png)

Les données actives sont activées par défaut sur tous les rapports qui les prennent en charge. Si vous préférez afficher toutes les mesures après le traitement complet des données, plusieurs options sont disponibles :

* Utilisez Analysis Workspace, qui utilise des données entièrement traitées.
* Cliquez sur « Non » dans le paramètre de rapport de données actuel pour utiliser uniquement les données entièrement traitées.
* Supprimez l'élément d'autorisation « Données actives » d'un profil de produit dans la console d'administration pour empêcher les utilisateurs non administrateurs d'afficher cette option. See [Analytics Tools permission items](../../admin/admin-console/permissions/analytics-tools.md) in the Admin user guide for more information.

En raison de la priorité de la disponibilité des données, les données actives ne peuvent pas être utilisées avec les segments, les classifications, les ventilations, le cheminement et certaines mesures. Si l'une de ces fonctionnalités est utilisée, les données actives sont forcées à « Non » dans le rapport et un avis jaune s'affiche pour expliquer pourquoi les données actives n'est pas disponible.

![Avis de données actuel](assets/current_data_notice.png)

## Latence type des données actives

Les mesures apparaissent dans l’une des trois périodes suivantes. Cliquez sur l’icône de l’horloge en regard du commutateur « Inclure les données actives » pour afficher la valeur de latence réelle de chaque mesure sur un rapport.

| Période | Mesures |
| --- | --- |
| Moins de 10 minutes | Instances et pages vues sur les variables de trafic |
| Entre 10 et 35 minutes | Événements de conversion, instances et pages vues sur les variables de conversion |
| Entre 45 et 120 minutes | Toutes les autres données, telles que les visites, les visiteurs uniques et la participation |

Certaines des données affichées dans la vue des données actives n'ayant pas été entièrement traitées, vous pouvez constater une différence entre les valeurs rapportées dans la vue des données actives et la vue finalisée. Dans les rapports de tendance, la différence de données est généralement inférieure à 1 %.

## Mesures calculées

Les mesures calculées peuvent être créées à l’aide de mesures ayant une valeur de latence différente. Il se peut donc que certaines valeurs récentes soient calculées à l’aide de données incomplètes dans la vue des données actives.

For example, you create the calculated metric 'Page Views per Visit using the formula `Page Views divided by Visits`. Les pages vues s'affichent généralement sous 10 minutes et les visites s'affichent généralement sous 2 heures ; les mesures calculées dans cette fenêtre de latence sont calculées à l'aide de mesures incomplètes. Si vous publiez une nouvelle page qui reçoit 4 000 accès de 4 000 visites différentes sur une période de 2 heures, la différence de latence entre ces mesures peut entraîner des calculs incomplets.

Cette différence de données est plus visible lorsque vous créez des rapports sur les nouvelles valeurs ou sur des périodes courtes. Lorsqu'un rapport utilise des périodes plus longues, les différences de latence qui se produisent au cours des dernières heures de la création de rapports ne peuvent pas avoir d'impact perceptible sur les mesures calculées.

Si vous avez calculé des mesures susceptibles d'être affectées par ces différences, désactivez les données actives ou utilisez des mesures avec la même fenêtre de latence attendue.

## Rapports téléchargés

Lorsque vous téléchargez un rapport dont la vue des données actives est activée, il est mis en file d’attente, généré, puis renvoyé au navigateur. Si les données sont collectées pendant la génération du rapport, ces données apparaissent dans le rapport. Cette période peut conduire au rapport téléchargé dont les données sont légèrement plus nombreuses.
