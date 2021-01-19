---
title: Révision ciblée (après chaque mise à jour de site web)
description: Suivez ces étapes pour vous assurer que votre implémentation reste dénuée d’erreurs et conforme à vos indicateurs clés de performance.
translation-type: tm+mt
source-git-commit: 912e5077889a02c3bf0dea9b079d213bb20f9424
workflow-type: tm+mt
source-wordcount: '514'
ht-degree: 83%

---


# Révision ciblée (après chaque mise à jour de site web)

Pourquoi devriez-vous passer en revue votre implémentation plusieurs fois par an ? Parce qu’ainsi, vous pouvez résoudre les problèmes liés à la qualité des données à un stade précoce. En effectuant régulièrement cette révision ciblée après chaque mise à jour de site web, vous constaterez que vos [révisions intégrales](/help/implement/review/full-review.md) semestrielles seront beaucoup plus simples. Vous éviterez également de laisser les petits problèmes liés aux données se transformer en problèmes majeurs pouvant éroder la confiance des parties prenantes.

## 1. Démarrez avec vos 5 principaux indicateurs clés de performance

Connaître vos 5 principaux indicateurs clés de performances (KPI) vous aidera à déterminer les mesures et dimensions associées que vous devez examiner. Si vous n’avez pas actualisé vos indicateurs clés de performance au cours des 6 derniers mois ou si votre entreprise n’en a pas encore créés, suivez [ces instructions](/help/implement/review/define-kpis.md).

## 2. Assurez-vous que vos mesures et variables d’indicateurs clés de performance fonctionnent toujours correctement

Rappelez-vous qu’au fil du temps, les mises à jour du code peuvent avoir des ramifications inattendues. Vous souhaitez vous assurer que toutes les mesures et dimensions associées à vos [5 principaux IPC](/help/implement/review/define-kpis.md) fonctionnent toujours correctement. Idéalement, cela devrait être fait juste après une mise à jour de site web. Si vous ne l’avez pas fait au cours des derniers mois, faites-le *dès maintenant*. Pour ce faire :

* Créez des tableaux de bord pour afficher les vues de tendances horaires de ces mesures et variables critiques (ou configurez [des alertes intelligentes](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/virtual-analyst/intelligent-alerts/intellligent-alerts.html#analysis-workspace) pour chaque mesure). Ensuite, surveillez-les pendant un jour ou deux pour vous assurer que vous obtenez les données attendues et que les données sont correctes. Recherchez les points d’inflexion. Soyez prêt à résoudre immédiatement les problèmes critiques. Si vous constatez des incohérences, consultez la couche de données, les règles du gestionnaire de balises et les règles de traitement pour en savoir plus.
* Réexécutez le [Tableau de bord d’intégrité d’Analytics](https://assets.adobe.com/public/9549dbe7-765a-4899-77b8-85cbba1a4252) pour surveiller les tendances générales de vos mesures et variables d’indicateurs de performance clés.

*Pour plus d’informations concernant les manières de vous assurer que vos mesures et variables fonctionnent correctement, [consultez les conseils](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-discussions/my-five-best-tips-for-keeping-adobe-analytics-humming/td-p/388608) de Sarah Owen, championne d’Adobe Analytics.*

## 3. Examinez attentivement les données de la section mise à jour de votre site

Assurez-vous que la dernière mise à jour du site n’a pas eu d’incidence négative sur la collecte de données pour cette section du site : passez en revue tous les codes et variables qui correspondent à la section pour vous assurer que le nouveau suivi fonctionne comme prévu.

## 4. Mettez votre documentation à jour

Si vous avez récemment ajouté ou modifié des mesures ou des variables, vous devez mettre à jour votre document d’exigences de l’entreprise (BRD) et votre document de référence pour la conception de solution (SDR).

Si la documentation relative à votre implémentation est indisponible, exportez une liste de variables et créez votre BRD ou votre SDR à l’aide de [ce modèle](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/implementation/implementation-basics/creating-a-business-requirements-document.html?lang=fr#implementation).

## 5. Résolvez immédiatement les problèmes liés à la qualité des données

Évaluez la situation et élaborez un plan pour rectifier les données. Apportez ensuite les modifications nécessaires, mettez à jour votre documentation et informez les parties prenantes des modifications effectuées.

*Regardez cette vidéo de 2 minutes dans laquelle Sarah Owen, championne d’Adobe Analytics, indique quels sont les meilleurs moments pour intégrer les révisions d’implémentation à votre planning chargé :*

>[!VIDEO](https://video.tv.adobe.com/v/328340/?quality=12&learn=on)
