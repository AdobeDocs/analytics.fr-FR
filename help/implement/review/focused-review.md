---
title: Révision ciblée (après chaque publication du site Web)
description: Suivez ces étapes pour vous assurer que votre mise en oeuvre reste exempte d’erreurs et conforme à vos IPC.
translation-type: tm+mt
source-git-commit: ad7274dbed3b85ca24cd92bf3a0d36d1f2e3597b
workflow-type: tm+mt
source-wordcount: '514'
ht-degree: 0%

---


# Révision ciblée (après chaque publication du site Web)

Pourquoi passez-vous en revue votre mise en oeuvre tous les quelques mois ? Vous pouvez donc résoudre n&#39;importe quel problème de qualité des données tant qu&#39;elles sont encore petites. Si vous effectuez régulièrement cette révision ciblée après chaque publication du site Web, vous constaterez que vos [examens complets](/help/implement/review/full-review.md) bisannuels sont beaucoup plus faciles. Vous éviterez également que les petits problèmes ne se transforment en problèmes de mégadonnées qui pourraient éroder la confiance des parties prenantes.

## 1. Début avec vos 5 principaux indicateurs de performance clés.

Connaître les 5 principaux indicateurs de performances (IPC) vous aidera à déterminer les mesures et dimensions associées que vous devez examiner. Si vous n&#39;avez pas actualisé vos IPC au cours des 6 derniers mois ou si votre entreprise n&#39;a pas encore créé d&#39;IPC, suivez [ces instructions](/help/implement/review/define-kpis.md).

## 2. Assurez-vous que vos mesures et variables IPC fonctionnent toujours correctement.

N&#39;oubliez pas que les mises à jour du code au fil du temps peuvent avoir des ramifications inattendues. Vous souhaitez vous assurer que toutes les mesures et dimensions associées à vos [5 principaux IPC](/help/implement/review/define-kpis.md) fonctionnent toujours correctement. Idéalement, cela devrait être fait juste après la publication d&#39;un site Web ; si vous ne l’avez pas fait au cours des derniers mois, faites-le *maintenant*. Pour ce faire :

* Créez des tableaux de bord pour afficher les vues de tendances horaires de ces mesures et variables critiques (ou configurez [des alertes intelligentes](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/virtual-analyst/intelligent-alerts/intellligent-alerts.html#analysis-workspace) pour chaque mesure). Ensuite, surveillez-les pendant un jour ou deux pour vous assurer que vous obtenez les données attendues et que les données sont correctes. Recherchez les points d&#39;inflexion. Soyez prêt à résoudre immédiatement les problèmes critiques. Si vous constatez des incohérences, consultez la couche de données, les règles du gestionnaire de balises et les règles de traitement pour en savoir plus.
* Réexécutez le [Tableau de bord d’intégrité d’Analytics](https://assets.adobe.com/public/9549dbe7-765a-4899-77b8-85cbba1a4252) pour surveiller les tendances générales de vos mesures et variables d’indicateurs de performance clés.
   *Pour plus d’informations sur la manière de vous assurer que vos mesures et variables fonctionnent correctement,  [lisez ces ](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-discussions/my-five-best-tips-for-keeping-adobe-analytics-humming/td-p/388608) conseils de Sarah Owen, championne d’Adobe Analytics.*

## 3. Examinez attentivement les données de la section mise à jour de votre site.

Assurez-vous que la dernière version du site n’a pas eu d’incidence négative sur la collecte de données pour cette section du site : vérifiez tous les codes et variables qui correspondent à cette section pour vous assurer que le nouveau suivi fonctionne comme prévu.

## 4. Mettez à jour votre documentation.

Si vous avez récemment ajouté ou modifié des mesures ou des variables, vous devez mettre à jour votre Document des besoins professionnels (BRD) et votre référence de conception de solution (DTS).

Si vous ne disposez pas de la documentation de votre implémentation, exportez une liste de variables et créez votre BRD ou votre DTS à l’aide de [ce modèle](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/implementation/implementation-basics/creating-a-business-requirements-document.html?lang=en#implementation).

## 5. Réparez immédiatement les lacunes que vous constatez dans la qualité de vos données.

Évaluer la situation et élaborer un plan pour corriger les données. Apportez ensuite les modifications nécessaires, mettez à jour votre documentation et informez vos parties prenantes des modifications que vous avez apportées.

*Regardez cette vidéo de 2 minutes de Sarah Owen, championne d&#39;Adobe Analytics, qui décrit les moments naturels où vous pouvez intégrer les révisions de votre mise en oeuvre à votre programme chargé :*

>[!VIDEO](https://video.tv.adobe.com/v/328340/?quality=12&learn=on)
