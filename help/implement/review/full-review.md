---
title: Révision intégrale
description: Passez votre implémentation en revue tous les 6 mois pour vous assurer qu’elle reste en phase avec les besoins de l’entreprise et les indicateurs clés de performance.
feature: Implementation Basics
exl-id: 235fc86e-e1b0-4b1a-a270-0dfba457a832
source-git-commit: 89088d11846e2d3eac83a834658e4755141655e5
workflow-type: tm+mt
source-wordcount: '385'
ht-degree: 80%

---

# Révision intégrale (pour une révision semestrielle de l’implémentation)

Pourquoi devriez-vous passer votre implémentation en revue tous les 6 mois ? Pour vous assurer que cette implémentation reste en phase avec les besoins de votre société ! Vous souhaitez également résoudre tous les problèmes liés à la qualité des données lorsqu’ils sont petits et avant qu’ils ne se transforment en problèmes majeurs de données susceptibles d’éroder la confiance des parties prenantes. Outre ces révisions intégrales conduites tous les 6 mois, vous devriez également effectuer des [révisions ciblées](/help/implement/review/focused-review.md) après chaque mise à jour de site web.

## 1. Assurez-vous que l’implémentation est toujours en phase avec les besoins de votre société

Rencontrez le propriétaire de l’entreprise et/ou les analystes pour passer en revue l’évolution des besoins de l’entreprise. Si votre implémentation ne satisfait pas certains besoins ou opportunités de mesure, déterminez comment mettre à jour vos indicateurs clés de performance et vos plans de mesure. N’oubliez pas d’enregistrer vos modifications dans vos [BRD et SDR](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/implementation/implementation-basics/creating-a-business-requirements-document.html?lang=fr#implementation).

## 2. Assurez-vous que vos mesures et vos variables fonctionnent toujours correctement

Passez brièvement en revue toutes vos mesures et variables selon leur ordre d’importance pour l’entreprise afin de vous assurer que les données sont collectées correctement. Démarrez par les mesures et variables les plus importantes : celles qui sont associées à vos [5 principaux indicateurs clés de performance](https://experienceleague.adobe.com/docs/analytics/implementation/review/define-kpis.html?lang=fr#review). Pour ce faire :

* Créer des tableaux de bord pour afficher les vues de tendances mensuelles de vos mesures et variables (ou configurer [alertes intelligentes](https://experienceleague.adobe.com/docs/analytics/components/alerts/intellligent-alerts.html) pour chacune d’elles) afin de vous assurer que vous obtenez les données attendues et que celles-ci sont correctes. Si vous constatez des incohérences, passez en revue la couche de données, les règles du gestionnaire de balises et les règles de traitement pour en savoir plus.
* Exécutez à nouveau [Analytics Health Dashboard](https://assets.adobe.com/public/9549dbe7-765a-4899-77b8-85cbba1a4252) pour surveiller les tendances générales de vos mesures et variables.

Ne laissez pas votre implémentation gonflée par les mesures et variables dont vous n’avez pas besoin. Désactivez les mesures ou variables dont l’entreprise n’a plus besoin ou qu’elle n’utilise plus. Vous voudrez peut-être les supprimer ou les réutiliser ultérieurement.

## 3. Actualisez vos indicateurs clés de performance

Maintenant que vous disposez d’une vision actualisée des objectifs de l’entreprise, vérifiez que vous avez effectivement choisi les 5 indicateurs clés de performances (KPI) les *plus* importants. Vous ne pouvez en choisir que 5 ! Ces indicateurs clés de performance peuvent être des mesures comme le chiffre d’affaires ou des mesures calculées comme les revenus par visite. Les mesures peuvent également comporter des variables. Pour plus d’informations, consultez [Définition des 5 principaux indicateurs clés de performance](/help/implement/review/define-kpis.md).
