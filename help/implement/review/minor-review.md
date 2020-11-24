---
title: Examen de la mise en oeuvre mineure (après chaque publication du site Web)
description: Suivez ces étapes pour vous assurer que votre mise en oeuvre reste exempte d’erreurs et conforme à vos IPC.
translation-type: tm+mt
source-git-commit: 82064e267729b6995402bd122c6f71b3d38967a3
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 0%

---


# Examen de la mise en oeuvre mineure (après chaque publication du site Web)

Pourquoi devriez-vous examiner votre mise en oeuvre après chaque publication de site Web ? Parce que vous devez vous assurer que vos mises à jour de code n’ont pas de ramifications inattendues et que vous devez résoudre tous les problèmes de qualité des données tant qu’elles sont encore petites. Si vous effectuez régulièrement cette révision mineure après chaque publication du site Web, vous constaterez que vos révisions [](/help/implement/review/major-review.md) majeures (tous les 6 mois) sont beaucoup plus faciles. Vous éviterez également que les petits problèmes ne se transforment en problèmes de mégadonnées qui pourraient éroder la confiance des parties prenantes.

## 1. Quel a été l&#39;impact de la publication sur les données de cette section du site ?

Effectuer des tests d&#39;unité complets : Examinez tout le code et toutes les variables qui correspondent à la section du site que vous venez de mettre à jour pour vous assurer que le nouveau suivi fonctionne comme prévu.

## 2. Mise à jour de votre documentation

Mettez à jour votre Document des besoins commerciaux (BRD) et votre référence de conception de solution (DTS) avec les variables que vous avez ajoutées/modifiées pour prendre en compte le lancement.

Vous ne disposez pas de la documentation relative à votre mise en oeuvre ? Exportez une liste de variables et créez votre BRD ou votre DTS à l’aide de [ce modèle](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/implementation/implementation-basics/creating-a-business-requirements-document.html?lang=en#implementation).

## 3. Début avec vos 5 principaux indicateurs de performance clés

Connaître les 5 principaux indicateurs de performances (IPC) vous aidera à déterminer les mesures et dimensions associées que vous devez examiner. Si vous n’avez pas actualisé vos IPC au cours des 6 derniers mois ou si votre entreprise n’a pas encore créé d’IPC, suivez [ces instructions](/help/implement/review/define-kpis.md).

## 4. Toutes les mesures et variables des IPC fonctionnent-elles toujours bien après la publication ?

N&#39;oubliez pas que toute mise à jour du code peut avoir des ramifications inattendues. Vous souhaitez vous assurer que toutes les mesures et dimensions associées aux 5 principaux indicateurs de performance clés [](/help/implement/review/define-kpis.md) fonctionnent toujours correctement. Pour ce faire :

* **Créez des tableaux de bord** pour afficher les vues de tendances horaires de ces mesures et variables critiques. Vous pouvez également configurer des alertes intelligentes pour chaque mesure) et les surveiller pendant un jour ou deux après la publication, afin de vous assurer que vous obtenez les données attendues et que les données sont correctes. Recherchez les points d&#39;inflexion. Soyez prêt à résoudre immédiatement les problèmes critiques. Si vous constatez des incohérences qui ne semblent pas correctes, recherchez dans votre couche de données, les règles du gestionnaire de balises et les règles de traitement pourquoi.
* **Réexécutez le Tableau de bord** d’intégrité d’Analytics pour surveiller les tendances générales de vos mesures et variables d’indicateurs de performance clés.
Pour plus d’informations sur la manière de vous assurer que vos mesures et variables fonctionnent correctement, consultez les conseils de Sarah Owen, championne de Adobe Analytics.

## 5. Existe-t-il des lacunes dans la qualité de vos données ?

Évaluer la situation et élaborer un plan pour corriger les données. Apportez ensuite les modifications nécessaires, mettez à jour votre documentation et informez vos parties prenantes des modifications que vous avez apportées.

Regardez cette vidéo de Sarah Owen, championne d&#39;Adobe Analytics, sur les périodes naturelles où vous pouvez intégrer les révisions de votre mise en oeuvre à votre calendrier chargé :

>[!VIDEO](https://video.tv.adobe.com/v/328340/?quality=12&learn=on)
