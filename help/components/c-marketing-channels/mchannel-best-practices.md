---
title: Bonnes pratiques pour la mise en œuvre des canaux marketing Adobe Analytics
description: Mise à jour des bonnes pratiques relatives à l’utilisation des canaux marketing avec Attribution et Customer Journey Analytics
feature: Marketing Channels
exl-id: a0ab818d-7165-4f34-bc43-1ed8d6215800
TQID: https://experienceleague.adobe.com/mKq-l0nm-MFJjcvWoIwUfQ2QM-dYD6VlcfH-CszsUv8
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 669
ht-degree: 78%

---

# Attribution avec les canaux marketing - Bonnes pratiques

[Les canaux marketing](/help/components/c-marketing-channels/c-getting-started-mchannel.md) sont une fonctionnalité très utile et puissante d’Adobe Analytics. Les conseils actuels concernant la mise en œuvre des canaux marketing ont été prodigués à un moment où ni [Attribution](/help/analyze/analysis-workspace/attribution/overview.md) ni [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html?lang=fr#cja-usecases) n’existaient.

Afin de garantir une mise en œuvre durable de vos canaux marketing et une cohérence en matière de rapports avec Attribution et Customer Journey Analytics, nous vous proposons de consulter nos nouvelles bonnes pratiques. Si vous utilisez déjà des canaux marketing, vous pouvez choisir les meilleures options parmi ces nouveaux conseils. Si vous découvrez les canaux marketing, nous vous conseillons de respecter toutes les nouvelles bonnes pratiques.

Lorsque les canaux marketing ont été introduits pour la première fois, ils ne disposaient que des dimensions Première touche et Dernière touche. Les dimensions Première touche/Dernière touche explicites ne sont plus nécessaires avec la version actuelle de l’attribution. Adobe fournit des dimensions « Canal marketing » et « Détails sur les canaux marketing » génériques afin que vous puissiez les utiliser avec le modèle d’attribution de votre choix. Ces dimensions génériques se comportent de la même manière que les dimensions de canal Dernière touche, mais sont étiquetées différemment pour éviter toute confusion lors de l’utilisation de canaux marketing avec un modèle d’attribution différent.

Étant donné que les dimensions de canal marketing dépendent d’une définition de visite traditionnelle (définie par leurs règles de traitement), la définition de visite ne peut pas être modifiée à l’aide de suites de rapports virtuelles. Ces pratiques révisées permettent d’obtenir des intervalles de recherche en amont clairs et contrôlés avec Attribution et Adobe Analytics.

## Bonne pratique n° 1 : utiliser Attribution pour une analyse contrôlée

Nous vous recommandons d’utiliser [Attribution](/help/analyze/analysis-workspace/attribution/overview.md) au lieu de l’attribution de canal marketing existante pour affiner votre analyse de ce dernier. Suivez les autres bonnes pratiques pour garantir la cohérence et la fiabilité des contrôles de vos analyses avec Attribution.

![](assets/attribution.png)

* La configuration des dimensions Canal marketing et Détails du canal marketing établit les points de contact à évaluer, en fonction de chaque instance du canal marketing.
* Pour l’analyse des mesures, votre entreprise doit s’aligner sur un ou plusieurs modèles d’attribution. Enregistrez les mesures personnalisées avec ce modèle pour une réutilisation facile.
* Par défaut, les données sont attribuées à l’aide de la Dernière touche et du paramètre de la période d’engagement des visiteurs. Les modèles de mesure Attribution offrent un meilleur contrôle sur les intervalles de recherche en amont et une plus grande variété, y compris l’[attribution algorithmique](/help/analyze/analysis-workspace/attribution/algorithmic.md#analysis-workspace).

## Bonne pratique n° 2 : aucune définition des canaux Direct et Actualisation de session

Les canaux Direct et Interne/Actualisation de session ne sont pas recommandés pour une utilisation avec des modèles d’attribution personnalisés.

Que se passe-t-il si Direct et Actualisation de session sont déjà configurés pour votre organisation ? Dans ce cas, Adobe vous recommande de [créer une classification](/help/admin/tools/manage-rs/edit-settings/marketing-channels/classifications-mchannel.md) pour Première touche/Dernière touche et de ne pas classer les canaux Direct et Actualisation de session. La dimension classifiée génère des résultats d’attribution similaires au cas où ces canaux n’auraient jamais été configurés.

![](assets/direct-session-refresh.png)

Si vous désactivez ces canaux et supprimez leurs règles de traitement des canaux marketing, les résultats diffèrent légèrement de l’approche de classification. La valeur `None` représente les visites qui ne correspondaient à aucune règle de traitement des canaux marketing. Des différences peuvent apparaître lorsqu’une visite qui ne correspond à aucun canal suit une visite qui correspond à un canal.

Vous pouvez toujours utiliser des modèles d’attribution personnalisés pour appliquer des intervalles de recherche en amont et des modèles d’attribution dans les deux cas.

## Bonne pratique n° 3 : activer Remplacer le canal Dernière touche pour tous les canaux.

Les modèles d’attribution personnalisés utilisés avec la dimension Canal marketing dans Workspace fonctionnent mieux lorsque ce paramètre est activé. Lorsque ce paramètre est activé, une instance de canal marketing est comptabilisée lorsqu’un nouveau canal/détail est rencontré. Vous devez l’activer pour tous les canaux, à l’exception des canaux Direct ou Interne/Actualisation de session. Nous ne recommandons plus l’utilisation de ces canaux avec les modèles d’attribution personnalisés.

![](assets/override.png)

## Bonne pratique n° 4 : réduire la période d’engagement des visiteurs et visiteuses

Définir la période d’engagement des visiteurs et visiteuses sur un minimum de « 1 jour » réduit la probabilité de valeurs persistantes. Puisque les modèles d’attribution personnalisés (AIQ) permettent des intervalles de recherche en amont flexibles, nous vous recommandons de définir ce paramètre sur la valeur minimale afin d’en minimiser l’impact.

![](assets/expiration.png)

## Bonne pratique n° 5 : les règles de traitement des canaux marketing ne doivent exister que pour les canaux activés

Assurez-vous de supprimer toutes les règles de traitement des canaux marketing pour les canaux désactivés. Les règles ne doivent exister que pour les canaux marketing qui sont activés.
