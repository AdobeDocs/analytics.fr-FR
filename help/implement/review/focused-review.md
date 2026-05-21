---
title: Révision ciblée (après chaque mise à jour de site web)
description: Suivez ces étapes pour vous assurer que votre implémentation reste dénuée d’erreurs et conforme à vos indicateurs clés de performance.
feature: Implementation Basics
exl-id: e38f92b6-bd6e-4835-a8e5-0f29ac962066
role: Admin, Leader
TQID: https://experienceleague.adobe.com/C57qRRa4-WDgJDgvtLebgy-0DAPvMUreSrGfuA67N4o
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2:
  - id: e93b8c4c-c5f7-45f8-9abe-9b710f53f502
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
topic_v2:
  - id: b4dd41a7-ccf8-4e9d-918e-acaab534a307
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 535
ht-degree: 62%

---

# Révision ciblée (après chaque mise à jour de site web)

Pourquoi devriez-vous passer en revue votre implémentation plusieurs fois par an ? Parce qu’ainsi, vous pouvez résoudre les problèmes liés à la qualité des données à un stade précoce. Si vous effectuez régulièrement cette révision ciblée après chaque mise à jour de site web, vous constaterez que vos [révisions complètes](/help/implement/review/full-review.md) semestrielles sont beaucoup plus faciles. Vous empêcherez également les petits problèmes de se transformer en problèmes de mégadonnées qui pourraient éroder la confiance des parties prenantes.

## &#x200B;1. Commencez par vos 5 principaux indicateurs clés de performance

Connaître vos 5 principaux indicateurs clés de performances (KPI) vous aidera à déterminer les mesures et dimensions associées que vous devez examiner. Si vous n’avez pas actualisé vos KPI au cours des 6 derniers mois ou si votre entreprise n’a pas encore créé d’KPI, suivez [ces instructions](/help/implement/review/define-kpis.md).

## &#x200B;2. Assurez-vous que vos mesures et variables d’indicateurs clés de performance fonctionnent toujours correctement

Rappelez-vous qu’au fil du temps, les mises à jour du code peuvent avoir des ramifications inattendues. Vérifiez que toutes les mesures et dimensions associées à vos [cinq principaux indicateurs clés de performance](/help/implement/review/define-kpis.md) fonctionnent toujours correctement. Idéalement, faites cela juste après une mise à jour de site web. Si vous ne l’avez pas fait au cours des derniers mois, faites-le *maintenant*. Pour ce faire :

* Créez des tableaux de bord pour afficher les vues de tendances horaires de ces mesures et variables importantes (ou définissez des [alertes](/help/components/alerts/alerts-overview.md) pour chaque mesure). Ensuite, surveillez-les pendant un jour ou deux pour vous assurer que vous obtenez les données attendues et que celles-ci sont correctes. Recherchez les points d’inflexion. Soyez prêt à résoudre immédiatement les problèmes critiques. Si vous constatez des incohérences, consultez la couche de données, les règles du gestionnaire de balises et les règles de traitement pour en savoir plus.
* Exécutez à nouveau [Analytics Health Dashboard](https://express.adobe.com/page/tnNQGNlfzta3b/) pour surveiller les tendances générales des mesures et variables de vos indicateurs clés de performance.

*Pour plus d’informations concernant les manières de vous assurer que vos mesures et variables fonctionnent correctement, [consultez les conseils](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-discussions/my-five-best-tips-for-keeping-adobe-analytics-humming/td-p/388608?profile.language=fr) de Sarah Owen, Adobe Analytics Champion.*

## &#x200B;3. Examinez minutieusement les données de la section mise à jour de votre site

Assurez-vous que la dernière mise à jour du site n’a pas eu d’incidence négative sur la collecte de données pour cette section du site : passez en revue tous les codes et variables qui correspondent à la section pour vous assurer que le nouveau suivi fonctionne comme prévu.

## &#x200B;4. Mise à jour de la documentation

Si vous avez récemment ajouté ou modifié des mesures ou des variables, vous devez mettre à jour votre document d’exigences de l’entreprise (BRD) et votre document de référence pour la conception de solution (SDR).

Si vous ne disposez pas de la documentation relative à votre implémentation, exportez une liste de variables et créez votre BRD ou votre SDR à l’aide de [ce modèle](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/implementation/implementation-basics/creating-a-business-requirements-document.html?lang=fr#implementation).

## &#x200B;5. Combler immédiatement les lacunes que vous découvrez dans la qualité de vos données

Évaluez la situation et élaborez un plan pour rectifier les données. Apportez ensuite les modifications nécessaires, mettez à jour votre documentation et informez les parties prenantes des modifications effectuées.

*Regardez cette vidéo de 2 minutes dans laquelle Sarah Owen, championne d’Adobe Analytics, indique quels sont les meilleurs moments pour intégrer les révisions d’implémentation à votre planning chargé :*


>[!BEGINSHADEBOX]

Voir ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Vérification de votre implémentation](https://video.tv.adobe.com/v/3440171?captions=fre_fr&quality=12&learn=on){target="_blank"} pour une vidéo de démonstration.

>[!ENDSHADEBOX]


