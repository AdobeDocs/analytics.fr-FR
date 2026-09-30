---
title: Révision intégrale
description: Examinez votre implémentation tous les 6 mois pour vous assurer qu’elle reste alignée sur les besoins de l’entreprise et les KPI.
feature: Implementation Basics
exl-id: 235fc86e-e1b0-4b1a-a270-0dfba457a832
role: Admin, Leader
TQID: 'https://experienceleague.adobe.com/YQL-V84ZWAr8NqRp1snYZBgl7-3iIhhxWkWh6KTFKNM'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
    internal-label: Dashboards
  - id: a421fb65-2c82-457a-921c-28c46b697a39
    internal-label: Analytics basics
subfeature_v2:
  - id: e93b8c4c-c5f7-45f8-9abe-9b710f53f502
    internal-label: Alerts
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
  - id: c24fe15a-643a-47bd-8278-5e027df49785
    internal-label: Implementation basics
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
    internal-label: Leader
topic_v2:
  - id: b4dd41a7-ccf8-4e9d-918e-acaab534a307
    internal-label: Data quality
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '404'
ht-degree: 73%
---
# Révision intégrale (pour une révision semestrielle de l’implémentation)

Pourquoi devriez-vous passer votre implémentation en revue tous les 6 mois ? Parce que vous devez vous assurer que votre implémentation reste alignée sur les besoins de votre entreprise ! Il faut aussi s&#39;attaquer aux problèmes de qualité des données avant qu&#39;ils ne deviennent des problèmes majeurs qui pourraient miner la confiance des intervenants. Outre ces révisions intégrales conduites tous les 6 mois, vous devriez également effectuer des [révisions ciblées](/help/implement/review/focused-review.md) après chaque mise à jour de site web.

## &#x200B;1. Assurez-vous que votre implémentation reste entièrement alignée sur les besoins de votre entreprise

Rencontrez le propriétaire de l’entreprise et/ou les analystes pour passer en revue l’évolution des besoins de l’entreprise. Si votre implémentation ne satisfait pas certains besoins ou opportunités de mesure, déterminez comment mettre à jour vos KPI et vos plans de mesure. N’oubliez pas d’enregistrer vos modifications dans vos [BRD et SDR](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/implementation/implementation-basics/creating-a-business-requirements-document.html?lang=fr#implementation).

## &#x200B;2. Assurez-vous que vos mesures et variables fonctionnent toujours correctement

Passez brièvement en revue toutes vos mesures et variables selon leur ordre d’importance pour l’entreprise afin de vous assurer que les données sont collectées correctement. Démarrez par les mesures et variables les plus importantes : celles qui sont associées à vos [5 principaux indicateurs clés de performance](/help/implement/review/define-kpis.md#review). Pour ce faire :

* Créez des tableaux de bord pour afficher les vues de tendances mensuelles de vos mesures et variables (ou définissez des [alertes](/help/components/alerts/alerts-overview.md) pour chacune) afin de vous assurer que vous obtenez les données attendues et que celles-ci sont correctes. Si vous constatez des incohérences, examinez votre couche de données, les règles du gestionnaire de balises et les règles de traitement afin d’en déterminer la cause.
* Exécutez à nouveau [Analytics Health Dashboard](https://assets.adobe.com/public/8ff304bb-18e0-434b-54d1-39199422ba1c) pour surveiller les tendances générales de vos mesures et variables.

Ne laissez pas votre implémentation se surcharger de mesures et de variables dont vous n’avez pas besoin. Désactivez les mesures ou variables dont l’entreprise n’a plus besoin ou qu’elle n’utilise plus. Vous voudrez peut-être les supprimer ou les réutiliser ultérieurement.

## &#x200B;3. Actualiser vos indicateurs de performance clés

Maintenant que vous disposez d’une vision actualisée des objectifs de l’entreprise, vérifiez que vous avez effectivement choisi les 5 indicateurs clés de performances (KPI) les *plus* importants. Vous ne pouvez en choisir que 5 ! Ces KPI peuvent être des mesures, comme le chiffre d’affaires, ou des mesures calculées, comme le chiffre d’affaires par visite. Les mesures peuvent également comporter des variables. Pour plus d’informations, consultez [Définition des 5 principaux indicateurs clés de performance](/help/implement/review/define-kpis.md).
