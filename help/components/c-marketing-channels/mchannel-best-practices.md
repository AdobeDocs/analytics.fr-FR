---
title: Meilleures pratiques pour la mise en oeuvre des Canaux Adobe Analytics Marketing
description: Mise à jour des meilleures pratiques pour l’utilisation des Canaux marketing avec Attribution IQ et Customer Journey Analytics
translation-type: tm+mt
source-git-commit: 9f978ecaa86eed450c80ab5a864f321b6223ba8c
workflow-type: tm+mt
source-wordcount: '545'
ht-degree: 4%

---


# Attribution IQ avec les Canaux marketing - Bonnes pratiques

[Les ](/help/components/c-marketing-channels/c-getting-started-mchannel.md) canaux marketing sont une caractéristique précieuse et puissante de l’Adobe Analytics. Les directives actuelles concernant la mise en oeuvre du Canal marketing ont été formulées à un moment où il n&#39;existait ni [Attribution IQ](https://experienceleague.corp.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/overview.html?lang=en#analysis-workspace) ni [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html?lang=fr#cja-usecases).

Afin d’assurer la mise en oeuvre future de vos Canaux marketing et de garantir la cohérence des rapports avec l’Attribution IQ et le Customer Journey Analytics, nous publions un ensemble de bonnes pratiques mises à jour. Si vous utilisez déjà Marketing Canaux, vous pouvez choisir les meilleures options parmi ces nouvelles directives. Si vous découvrez les Canaux marketing, nous vous conseillons de respecter toutes les nouvelles pratiques recommandées.

Lorsque les Canaux marketing ont été introduits pour la première fois, ils ne contenaient que les dimensions Première touche et Dernière touche. Les dimensions Première touche/Dernière touche explicites ne sont plus nécessaires avec la version actuelle de l’attribution. Adobe fournit des dimensions génériques &quot;Canal marketing&quot; et &quot;Détails du Canal marketing&quot; afin que vous puissiez les utiliser avec le modèle d’attribution souhaité. Ces dimensions génériques se comportent de la même manière que les dimensions du Canal Dernière touche, mais sont étiquetées différemment afin d’éviter toute confusion lors de l’utilisation de Canaux marketing avec un modèle d’attribution différent.

Comme les dimensions du Canal marketing dépendent d’une définition de visite traditionnelle (définie par leurs règles de traitement), leur définition de visite ne peut pas être modifiée à l’aide des suites de rapports virtuelles. Ces pratiques révisées permettent des fenêtres de recherche claires et contrôlées avec Attribution IQ et CJA.

## Bonne pratique no 1 : Exploitation de l&#39;Attribution IQ pour une analyse contrôlée

Nous vous recommandons d’utiliser [Attribution IQ](https://experienceleague.corp.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/overview.html?lang=en#analysis-workspace) au lieu de l’attribution de Canal marketing existante pour affiner votre analyse de Canal marketing. Suivez les autres bonnes pratiques pour assurer la cohérence et des contrôles robustes de votre analyse avec Attribution IQ.

## Bonne pratique no 2 : Aucune définition de canal Direct et Session Refresh

Les canaux d’actualisation directe et interne/de session ne sont pas recommandés pour une utilisation avec des modèles d’attribution personnalisés (Attribution IQ).

Que se passe-t-il si votre entreprise a déjà configuré Direct et Session Refresh ? Dans ce cas, nous vous recommandons de créer une classification pour vos Canaux marketing et de ne pas classer ces deux canaux. La dimension classifiée produira les mêmes résultats d’Attribution IQ que si ces canaux n’avaient jamais été configurés.

## Bonne pratique no 3 : Activer le remplacement du Canal Dernière touche pour tous les canaux

Les modèles d’attribution personnalisés utilisés avec la dimension Canal marketing dans Workspace fonctionnent mieux lorsque ce paramètre est activé. Si ce paramètre est activé, une instance de Canal marketing est comptabilisée lorsqu’un nouveau canal/détail est rencontré. Vous devez l’activer pour tous les canaux, à l’exception de l’actualisation directe ou interne/session, que nous ne recommandons plus d’utiliser avec des modèles d’attribution personnalisés (Attribution IQ).

## Bonne pratique no 4 : Réduire la période d’engagement des Visiteurs

La définition de la période d’engagement du Visiteur sur une période minimale d’un jour réduit la probabilité de persistance des valeurs. Etant donné que les modèles d’attribution personnalisés (AIQ) autorisent des fenêtres de recherche en amont flexibles, nous vous recommandons de définir la valeur minimale afin de minimiser l’impact de ce paramètre.

## Bonne pratique no 5 : Les règles de traitement des Canaux marketing ne doivent exister que pour les canaux activés.

Veillez à supprimer toutes les règles de traitement des Canaux marketing pour les canaux désactivés. Les règles ne doivent exister que pour les Canaux marketing cochés comme activés.
