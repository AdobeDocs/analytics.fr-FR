---
title: Révision ciblée (après chaque mise à jour de site web)
description: Suivez ces étapes pour vous assurer que votre implémentation reste dénuée d’erreurs et conforme à vos indicateurs clés de performance.
feature: Implementation Basics
exl-id: e38f92b6-bd6e-4835-a8e5-0f29ac962066
source-git-commit: 89088d11846e2d3eac83a834658e4755141655e5
workflow-type: tm+mt
source-wordcount: '491'
ht-degree: 74%

---

# Révision ciblée (après chaque mise à jour de site web)

Pourquoi devriez-vous passer en revue votre implémentation plusieurs fois par an ? Parce qu’ainsi, vous pouvez résoudre les problèmes liés à la qualité des données à un stade précoce. Si vous effectuez régulièrement cette révision ciblée après chaque mise à jour de site web, vous constaterez que votre [Révisions complètes](/help/implement/review/full-review.md) sont beaucoup plus faciles. Vous éviterez également que les petits problèmes ne se transforment en problèmes de données massives susceptibles d’éroder la confiance des parties prenantes.

## 1. Démarrez avec vos 5 principaux indicateurs clés de performance

Connaître vos 5 principaux indicateurs clés de performances (KPI) vous aidera à déterminer les mesures et dimensions associées que vous devez examiner. Si vous n’avez pas actualisé vos indicateurs clés de performance au cours des 6 derniers mois ou si votre entreprise n’a pas encore créé ces indicateurs, suivez [ces instructions](/help/implement/review/define-kpis.md).

## 2. Assurez-vous que vos mesures et variables d’indicateurs clés de performance fonctionnent toujours correctement

Rappelez-vous qu’au fil du temps, les mises à jour du code peuvent avoir des ramifications inattendues. Vérifiez que toutes les mesures et dimensions associées à vos [cinq principaux indicateurs clés de performance](/help/implement/review/define-kpis.md) fonctionnent toujours correctement. Idéalement, ceci est fait juste après la publication d’un site web ; si vous ne l’avez pas fait au cours des derniers mois, faites-le. *now*. Pour ce faire :

* Créez des tableaux de bord pour afficher les vues de tendances horaires de ces mesures et variables importantes (ou définissez des [alertes intelligentes](https://experienceleague.adobe.com/docs/analytics/components/alerts/intellligent-alerts.html) pour chaque mesure). Ensuite, surveillez-les pendant un ou deux jours pour vous assurer que vous obtenez les données attendues et que celles-ci sont correctes. Recherchez les points d’inflexion. Soyez prêt à résoudre immédiatement les problèmes critiques. Si vous constatez des incohérences, consultez la couche de données, les règles du gestionnaire de balises et les règles de traitement pour en savoir plus.
* Exécutez à nouveau [Analytics Health Dashboard](https://assets.adobe.com/public/9549dbe7-765a-4899-77b8-85cbba1a4252) pour surveiller les tendances générales des mesures et variables de vos indicateurs clés de performance.

*Pour plus d’informations concernant les manières de vous assurer que vos mesures et variables fonctionnent correctement, [consultez les conseils](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-discussions/my-five-best-tips-for-keeping-adobe-analytics-humming/td-p/388608) de Sarah Owen, Adobe Analytics Champion.*

## 3. Examinez attentivement les données de la section mise à jour de votre site

Assurez-vous que la dernière mise à jour du site n’a pas eu d’incidence négative sur la collecte de données pour cette section du site : passez en revue tous les codes et variables qui correspondent à la section pour vous assurer que le nouveau suivi fonctionne comme prévu.

## 4. Mettez votre documentation à jour

Si vous avez récemment ajouté ou modifié des mesures ou des variables, vous devez mettre à jour votre document d’exigences de l’entreprise (BRD) et votre document de référence pour la conception de solution (SDR).

Si vous ne disposez pas de la documentation de votre mise en oeuvre, exportez une liste de variables et créez votre BRD ou votre SDR à l’aide de [ce modèle](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/implementation/implementation-basics/creating-a-business-requirements-document.html?lang=fr#implementation).

## 5. Résolvez immédiatement les problèmes liés à la qualité des données

Évaluez la situation et élaborez un plan pour rectifier les données. Apportez ensuite les modifications nécessaires, mettez à jour votre documentation et informez les parties prenantes des modifications effectuées.

*Regardez cette vidéo de 2 minutes dans laquelle Sarah Owen, championne d’Adobe Analytics, indique quels sont les meilleurs moments pour intégrer les révisions d’implémentation à votre planning chargé :*

>[!VIDEO](https://video.tv.adobe.com/v/328340/?quality=12&learn=on)
